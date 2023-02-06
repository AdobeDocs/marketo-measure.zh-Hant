---
unique-page-id: 18874680
description: '"[!DNL Facebook] API - [!DNL Marketo Measure]  — 產品檔案」'
title: "[!DNL Facebook] API"
exl-id: d6d18545-baae-4103-b0a6-c3de681ec833
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 1%

---

# [!DNL Facebook] API {#facebook-api}

## 簡介 {#introduction}

類似我們的AdWords &amp; [!DNL Bing Ads] 整合，我們 [!DNL Facebook] 整合可執行兩項基本動作：

* 自動標籤全部 [!DNL Facebook] 具有 [!DNL Marketo Measure] 參數(_bf)
* 下載所有作用中Facebook廣告的廣告成本資訊

## 如何設定 [!DNL Facebook] 整合 {#how-to-configure-the-facebook-integration}

至於設定，在 [!DNL Marketo Measure] 應用程式。

1. 導覽至 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} 並登入。
1. 在「我的帳戶」下選擇 **[!UICONTROL Settings]**.
1. 在整合下選取 **[!UICONTROL Connections]**.
1. 選擇 **[!UICONTROL Set Up New Ads Connection]** 彈出畫面隨即顯示。 選擇 **[!UICONTROL Facebook]** 並使用您的Facebook憑證登入。

   >[!NOTE]
   >
   >連接 [!DNL Facebook Ads] 帳戶必須是 [!DNL Facebook Ads] 帳戶。

1. 一次 [!DNL Marketo Measure] 連線至您的Facebook帳戶，請按一下帳戶旁的鉛筆圖示。
1. 在此檢視中，移動「自動標籤？」 切換為「是」。 然後選取位於 [!UICONTROL Learn More] 一節，以同意條款與條件。 請確定 [!UICONTROL Auto-tagging] 切換仍設為「[!UICONTROL Yes]&#39;。

## 連接帳戶 {#connecting-the-account}

![](assets/1.gif)

## 啟用自動標籤 {#enabling-autotagging}

>[!NOTE]
>
>如果您啟用自動標籤，我們會重設所有標籤廣告的轉換歷史記錄和社交證明。 強烈建議 [將此資料匯出為CSV](https://www.facebook.com/business/help/205067636197240) 啟用自動標籤之前。

![](assets/2-2.png)

啟用整合後， [!DNL Marketo Measure] 會開始將廣告層級成本下載至 [!DNL Marketo Measure Marketing ROI] 控制面板。

為了讓整合正常運作，您必須在 [!DNL Facebook] 帳戶。 這可讓我們的系統在所有廣告連結上新增_bf參數。 此程式會在您已新增至的任何其他追蹤參數之上新增參數 [!DNL Facebook] 廣告。

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
   <td><p>廣告促銷活動Id</p></td> 
   <td><p>[[!DNL Facebook] 促銷活動Id]</p></td> 
  </tr> 
  <tr> 
   <td><p>廣告促銷活動名稱 </p></td> 
   <td><p>[[!DNL Facebook] 促銷活動名稱]，或[utm_campaign]（若有提供）</p></td> 
  </tr> 
  <tr> 
   <td><p>廣告群組Id</p></td> 
   <td><p>[[!DNL Facebook] 廣告集Id]</p></td> 
  </tr> 
  <tr> 
   <td><p>廣告群組名稱</p></td> 
   <td><p>[[!DNL Facebook] 廣告集名稱]</p></td> 
  </tr> 
  <tr> 
   <td><p>接觸點來源</p></td> 
   <td><p>"[!DNL Facebook]「，或[utm_source]（如果提供）</p></td> 
  </tr> 
  <tr> 
   <td><p>中</p></td> 
   <td><p>"Social"或[utm_medium]（若有提供）</p></td> 
  </tr> 
  <tr> 
   <td><p>廣告Id或Creative_Unique_Id(Data Warehouse)</p></td> 
   <td><p>[從utm_content生成的自定義ID]</p></td> 
  </tr> 
  <tr> 
   <td><p>廣告內容或Creative_Name(Data Warehouse)</p></td> 
   <td><p>[utm_content]（如果提供）</p></td> 
  </tr> 
  <tr> 
   <td><p>關鍵字文字或關鍵字名稱(Data Warehouse)</p></td> 
   <td><p>[utm_term]（如果提供）</p></td> 
  </tr> 
  <tr> 
   <td><p>Ad_Unique_Id(Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] 廣告Id]</p></td> 
  </tr> 
  <tr> 
   <td><p>Ad_Name(Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] 廣告名稱]</p></td> 
  </tr> 
  <tr> 
   <td><p>Keyword_Unique_Id(Data Warehouse)</p></td> 
   <td><p>[從utm_term生成的自定義ID]</p></td> 
  </tr> 
  <tr> 
   <td><p>Ad_Provider(Data Warehouse)</p></td> 
   <td><p>"[!DNL Facebook]"</p></td> 
  </tr> 
  <tr> 
   <td><p>Account_Unique_ID(Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] 帳戶 #]</p></td> 
  </tr> 
  <tr> 
   <td><p>Account_Name(Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] 帳戶名稱]</p></td> 
  </tr> 
 </tbody> 
</table>

## 常見問題集 {#faq}

**問：什麼 [!DNL Facebook] 廣告受支援 [!DNL Marketo Measure]?**

答：輪播，單一影像。 目前不是影片、投影片或集合。

**問：什麼是社交證據？**

答：Social校樣是可見的參與，例如按贊、點按、留言和分享。

**問：當 [!DNL Marketo Measure] 標籤廣告？**

答： [!DNL Facebook] 不允許編輯廣告 [!DNL Marketo Measure] 需要刪除包含目標URL的創意內容，然後使用新參數重新建立廣告。

**問：為什麼 [!DNL Marketo Measure] 全部更新 [!DNL Facebook] 廣告？**

答：此 [!DNL Marketo Measure] 程式是標籤所有廣告，以備重新啟用時使用。

**問：連線的使用者需要什麼權限？**

答：ads_management，電子郵件

**問：匯入支出資料需要多久的時間？**

答：1小時

**問：匯入廣告資料需要多久時間？**

答：4小時
