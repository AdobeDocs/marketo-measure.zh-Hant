---
unique-page-id: 18874680
description: "[!DNL Facebook] API - [!DNL Marketo Measure]"
title: '"[!DNL Facebook] API」'
exl-id: d6d18545-baae-4103-b0a6-c3de681ec833
feature: APIs, Integration, UTM Parameters
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 0%

---

# [!DNL Facebook] API {#facebook-api}

## 簡介 {#introduction}

與我們的AdWords相似&amp; [!DNL Bing Ads] 整合，我們的 [!DNL Facebook] 整合會執行兩個基本動作：

* 全部自動標籤 [!DNL Facebook] 廣告搭配 [!DNL Marketo Measure] 引數(_bf)
* 下載所有作用中Facebook廣告的廣告成本資訊

## 如何設定 [!DNL Facebook] 整合 {#how-to-configure-the-facebook-integration}

至於設定，在內有七個步驟需要完成 [!DNL Marketo Measure] 應用程式。

1. 瀏覽至 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} 並登入。
1. 在我的帳戶底下選取 **[!UICONTROL Settings]**.
1. 在整合底下選取 **[!UICONTROL Connections]**.
1. 選取 **[!UICONTROL Set Up New Ads Connection]** 且快顯視窗會出現。 選取 **[!UICONTROL Facebook]** 並使用您的Facebook憑證登入。

   >[!NOTE]
   >
   >連線至的人 [!DNL Facebook Ads] 帳戶必須是 [!DNL Facebook Ads] 帳戶。

1. 一次 [!DNL Marketo Measure] 已連線至您的Facebook帳戶，請按一下帳戶旁的鉛筆圖示。
1. 在此檢視中，移動「自動標籤？」 切換至「是」。 然後選取中找到的核取方塊 [!UICONTROL Learn More] 區段以同意條款與條件。 確定 [!UICONTROL Auto-tagging] 切換仍設為&#39;[!UICONTROL Yes]&#39;.

## 連線帳戶 {#connecting-the-account}

![](assets/1.gif)

## 啟用自動標籤 {#enabling-autotagging}

>[!NOTE]
>
>如果您啟用自動標籤，我們會重設所有已標籤廣告的轉換歷史記錄和社交證明。 我們強烈建議 [將此資料匯出為CSV檔](https://www.facebook.com/business/help/205067636197240) 然後再啟用自動標籤。

![](assets/2-2.png)

啟用整合後， [!DNL Marketo Measure] 將開始將廣告層級成本下載至 [!DNL Marketo Measure Marketing ROI] 控制面板。

為了讓整合正常運作，您必須在您的上啟用自動標籤 [!DNL Facebook] 帳戶。 這可讓我們的系統在所有廣告連結上新增_bf引數。 此程式會將新引數新增至您已新增至的任何其他追蹤引數之上 [!DNL Facebook] 廣告。

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
   <td><p>[[!DNL Facebook] 行銷活動ID]</p></td> 
  </tr> 
  <tr> 
   <td><p>廣告行銷活動名稱 </p></td> 
   <td><p>[[!DNL Facebook] 促銷活動名稱]，或是[utm_campaign] （若提供）</p></td> 
  </tr> 
  <tr> 
   <td><p>廣告群組ID</p></td> 
   <td><p>[[!DNL Facebook] 廣告集Id]</p></td> 
  </tr> 
  <tr> 
   <td><p>廣告群組名稱</p></td> 
   <td><p>[[!DNL Facebook] 廣告集名稱]</p></td> 
  </tr> 
  <tr> 
   <td><p>接觸點來源</p></td> 
   <td><p>"[!DNL Facebook]"，或是[utm_source] （若提供）</p></td> 
  </tr> 
  <tr> 
   <td><p>中</p></td> 
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
   <td><p>[[!DNL Facebook] 廣告ID]</p></td> 
  </tr> 
  <tr> 
   <td><p>Ad_Name (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] 廣告名稱]</p></td> 
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
   <td><p>[[!DNL Facebook] 帳戶#]</p></td> 
  </tr> 
  <tr> 
   <td><p>Account_Name (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] 帳戶名稱]</p></td> 
  </tr> 
 </tbody> 
</table>

## 常見問題集 {#faq}

**問：什麼 [!DNL Facebook] 廣告支援者 [!DNL Marketo Measure]？**

答：輪播，單一影像。 目前不是影片、投影片或集合。

**問：什麼是社交證明？**

答：社交校訂是可見的參與，例如，贊、點選、評論和分享。

**問：發生下列情況時會發生什麼事 [!DNL Marketo Measure] 標籤廣告嗎？**

答： [!DNL Facebook] 不允許編輯廣告，因此 [!DNL Marketo Measure] 需要刪除包含目的地URL的創意內容，然後使用新引數重新建立廣告。

**問：為什麼 [!DNL Marketo Measure] 全部更新 [!DNL Facebook] 廣告？**

答：此 [!DNL Marketo Measure] 此程式會標籤所有廣告，以防廣告重新啟用。

**問：連線使用者需要什麼許可權？**

答：ads_management，電子郵件

**問：匯入支出資料需要多久的時間？**

答：1小時

**問：匯入廣告資料需要多久的時間？**

答：4小時
