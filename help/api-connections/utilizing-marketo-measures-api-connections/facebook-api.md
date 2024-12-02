---
unique-page-id: 18874680
description: '[!DNL Facebook] API - [!DNL Marketo Measure]'
title: '[!DNL Facebook] API'
exl-id: d6d18545-baae-4103-b0a6-c3de681ec833
feature: APIs, Integration, UTM Parameters
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 0%

---

# [!DNL Facebook] API {#facebook-api}

## 簡介 {#introduction}

與我們的AdWords和[!DNL Bing Ads]整合類似，我們的[!DNL Facebook]整合會執行兩個基本動作：

* 使用[!DNL Marketo Measure]引數(_bf)自動標籤所有[!DNL Facebook]廣告
* 下載所有作用中Facebook廣告的廣告成本資訊

## 如何設定[!DNL Facebook]整合 {#how-to-configure-the-facebook-integration}

至於設定，[!DNL Marketo Measure]應用程式中有七個步驟要完成。

1. 導覽至[experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}並登入。
1. 在「我的帳戶」底下選取&#x200B;**[!UICONTROL Settings]**。
1. 在整合底下選取&#x200B;**[!UICONTROL Connections]**。
1. 選取「**[!UICONTROL Set Up New Ads Connection]**」，即會出現快顯視窗。 選取&#x200B;**[!UICONTROL Facebook]**&#x200B;並使用您的Facebook認證登入。

   >[!NOTE]
   >
   >連線[!DNL Facebook Ads]帳戶的人員必須是[!DNL Facebook Ads]帳戶內的管理員。

1. 在將[!DNL Marketo Measure]連線至您的Facebook帳戶後，按一下帳戶旁的鉛筆圖示。
1. 在此檢視中，移動「自動標籤？」 切換至「是」。 然後選取[!UICONTROL Learn More]區段中的核取方塊以同意條款與條件。 確定[!UICONTROL Auto-tagging]切換仍設為&#39;[!UICONTROL Yes]&#39;。

## 連線帳戶 {#connecting-the-account}

![](assets/1.gif)

## 啟用自動標籤 {#enabling-autotagging}

>[!NOTE]
>
>如果您啟用自動標籤，我們會重設所有已標籤廣告的轉換歷史記錄和社交證明。 強烈建議您在啟用自動標籤前[將此資料匯出為CSV](https://www.facebook.com/business/help/205067636197240)。

![](assets/2-2.png)

啟用整合後，[!DNL Marketo Measure]將開始將廣告層級成本下載至[!DNL Marketo Measure Marketing ROI]儀表板。

為了讓整合正確運作，您必須在[!DNL Facebook]帳戶上啟用自動標籤。 這可讓我們的系統在所有廣告連結上新增_bf引數。 此程式會在您已經新增至[!DNL Facebook]廣告的任何其他追蹤引數之上，新增新的引數。

![](assets/3.gif)

## 欄位對應 {#field-mapping}

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><p><strong>接觸點欄位</strong></p></th> 
   <th><p><strong>值</strong></p></th> 
  </tr> 
  <tr> 
   <td><p>廣告行銷活動ID</p></td> 
   <td><p>[[!DNL Facebook]行銷活動ID]</p></td> 
  </tr> 
  <tr> 
   <td><p>廣告行銷活動名稱 </p></td> 
   <td><p>[[!DNL Facebook]行銷活動名稱]，或是[utm_campaign] （若提供）</p></td> 
  </tr> 
  <tr> 
   <td><p>廣告群組ID</p></td> 
   <td><p>[[!DNL Facebook]廣告集Id]</p></td> 
  </tr> 
  <tr> 
   <td><p>廣告群組名稱</p></td> 
   <td><p>[!DNL Facebook]廣告集名稱</p></td> 
  </tr> 
  <tr> 
   <td><p>接觸點Source</p></td> 
   <td><p>"[!DNL Facebook]"或[utm_source] （若提供）</p></td> 
  </tr> 
  <tr> 
   <td><p>媒體</p></td> 
   <td><p>"Social"，或[utm_medium] （若提供）</p></td> 
  </tr> 
  <tr> 
   <td><p>廣告Id或Creative_Unique_Id (Data Warehouse)</p></td> 
   <td><p>[從utm_content產生的自訂ID]</p></td> 
  </tr> 
  <tr> 
   <td><p>廣告內容或Creative_Name (Data Warehouse)</p></td> 
   <td><p>[utm_content] （若提供）</p></td> 
  </tr> 
  <tr> 
   <td><p>關鍵字文字或Keyword_Name (Data Warehouse)</p></td> 
   <td><p>[utm_term] （若提供）</p></td> 
  </tr> 
  <tr> 
   <td><p>Ad_Unique_Id (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook]廣告識別碼]</p></td> 
  </tr> 
  <tr> 
   <td><p>Ad_Name (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook]廣告名稱]</p></td> 
  </tr> 
  <tr> 
   <td><p>Keyword_Unique_Id (Data Warehouse)</p></td> 
   <td><p>[從utm_term產生的自訂ID]</p></td> 
  </tr> 
  <tr> 
   <td><p>Ad_Provider (Data Warehouse)</p></td> 
   <td><p>"[!DNL Facebook]"</p></td> 
  </tr> 
  <tr> 
   <td><p>Account_Unique_ID (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook]帳戶號碼]</p></td> 
  </tr> 
  <tr> 
   <td><p>Account_Name (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook]帳戶名稱]</p></td> 
  </tr> 
 </tbody> 
</table>

## 常見問題集 {#faq}

**問：[!DNL Marketo Measure]支援哪些[!DNL Facebook]廣告？**

答：輪播，單一影像。 目前不是影片、投影片或集合。

**問：什麼是社交校訂？**

答：社交校訂是可見的參與，例如，贊、點選、評論和分享。

**問：[!DNL Marketo Measure]標籤廣告會發生什麼情況？**

答： [!DNL Facebook]不允許編輯廣告，因此[!DNL Marketo Measure]需要刪除包含目的地URL的創意，然後使用新引數重新建立廣告。

**問：為什麼[!DNL Marketo Measure]會更新所有[!DNL Facebook]廣告？**

答： [!DNL Marketo Measure]程式會標籤所有廣告，以備重新啟用。

**問：連線的使用者需要什麼許可權？**

答：ads_management，電子郵件

**問：匯入支出資料需要多久的時間？**

答：1小時

**問：匯入廣告資料需要多久的時間？**

答：4小時
