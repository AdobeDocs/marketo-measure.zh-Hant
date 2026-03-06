---
description: Marketo Measure使用者的隱私權要求指引
title: 隱私請求
exl-id: 883e475f-9868-412a-b505-230556f38484
feature: APIs, Tracking
source-git-commit: 7a4661c8d42214d32e5360dc45d6d880b08ef37c
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 26%

---


# 隱私請求 {#privacy-requests}

本檔案概述如何管理您可透過[!DNL Privacy Service] UI和&#x200B;**[!DNL Privacy Service]API**&#x200B;傳送給[!DNL Marketo Measure]的個別資料隱私權請求。

您可以透過兩種方式提交個別請求，以從[!DNL Marketo Measure]存取和刪除消費者資料：

* 透過[[!DNL Privacy Service] UI](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=zh-Hant){target="_blank"}。
* 透過&#x200B;**[!DNL Privacy Service]API**。 請參閱檔案[這裡](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=zh-Hant){target="_blank"}和API參考[這裡](https://developer.adobe.com/experience-platform-apis/references/privacy-service/){target="_blank"}。

[Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hant){target="_blank"}支援兩種請求：資料存取和資料刪除。

讓我們看看如何建立存取和刪除請求。

## 傳送Marketo Measure請求的必要設定 {#required-setup-to-send-requests-for-marketo-measure}

若要要求存取和刪除[!DNL Marketo Measure]的資料，您必須：

1. 識別下列項目：

   答： IMS 組織 ID

   b. 您要對其採取動作之人員的電子郵件地址

   IMS 組織 ID 是 24 個字元的英數字串，通常會加上 @AdobeOrg。 如果您的行銷團隊或內部 Adobe 系統管理員不知道您組織的 IMS 組織 ID，請寄信至 gdprsupport@adobe.com 與 Adobe 客戶服務團隊連絡。 您需先取得 IMS 組織 ID，才能向隱私權 API 提交請求。

1. 在[!DNL Privacy Service]中，您可以將存取和刪除要求提交至[!DNL Marketo Measure]，並檢查現有要求的狀態。

## 在 [!DNL Marketo Measure] JSON 請求中的必填欄位值 {#required-field-values-in-marketo-measure-json-requests}

&quot;companyContexts&quot;：

* &quot;namespace&quot;：**imsOrgID**
* &quot;value&quot;： `<Your IMS Org ID Value>`

&quot;users&quot;：

* &quot;action&quot;： [!UICONTROL access]或刪除
* &quot;userIDs&quot;：
   * &quot;namespace&quot;：電子郵件
   * &quot;type&quot;：標準
   * &quot;value&quot;： `<Data Subject's Email Address>`

&quot;include&quot;：

* **marketoMeasure** (適用於此請求的Adobe產品)

&quot;regulation&quot;：

* **gdpr**、**ccpa**、**pdpa**、**lgpd_bra**&#x200B;或&#x200B;**nzpa_nzl** （適用於此要求的隱私權法規）

## 範例一：GDPR刪除請求 {#gdpr-delete-request}

JSON要求

```json
{
  "companyContexts": [
    {
      "namespace": "imsOrgID",
      "value": "1231659F56A68A8B7F000101@AdobeOrg"
    }
  ],
  "users": [
    {
      "action": [
        "delete"
      ],
      "userIDs": [
        {
          "namespace": "email",
          "type": "standard",
          "value": "john.doe@adobe.com"
        }
      ]
    }
  ],
  "include": [
    "marketoMeasure"
  ],
  "regulation": "gdpr",
}
```

JSON回應

```json
{
  "requestId": "16331241037112570RX-245",
  "totalRecords": 1,
  "jobs": [
    {
      "jobId": "997b01e3-9568-402c-904b-b4e60a437875",
      "customer": {
        "user": {
          "action": [
            "delete"
          ],
          "userIDs": [
            {
              "namespace": "email",
              "value": "john.doe@adobe.com",
              "type": "standard",
              "namespaceId": 6,
              "isDeletedClientSide": false
            }
          ]
        }
      }
    }
  ]
}
```

## 範例二：CCPA存取要求 {#ccpa-access-request}

JSON要求

```json
{
  "companyContexts": [
    {
      "namespace": "imsOrgID",
      "value": "1231659F56A68A8B7F000101@AdobeOrg"
    }
  ],
  "users": [
    {
      "action": [
        "access"
      ],
      "userIDs": [
        {
          "namespace": "email",
          "type": "standard",
          "value": "john.doe@adobe.com"
        }
      ]
    }
  ],
  "include": [
    "marketoMeasure"
  ],
  "regulation": "ccpa",
}
```

JSON回應

```json
{
  "requestId": "16329573462631890RX-207",
  "totalRecords": 1,
  "jobs": [
    {
      "jobId": "3115e42d-011b-47ab-a2b0-ed4356af4d3e",
      "customer": {
        "user": {
          "action": [
            "access"
          ],
          "userIDs": [
            {
              "namespace": "email",
              "value": "john.doe@adobe.com",
              "type": "standard",
              "namespaceId": 6,
              "isDeletedClientSide": false
            }
          ]
        }
      }
    }
  ]
}
```
