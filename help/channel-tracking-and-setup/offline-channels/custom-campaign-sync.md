---
unique-page-id: 18874588
description: 自訂行銷活動同步 —  [!DNL Marketo Measure]
title: 自訂Campaign同步
exl-id: 66f0e4e3-c1b6-443e-8ffa-06b67862b855
feature: Channels
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 0%

---

# 自訂Campaign同步 {#custom-campaign-sync}

現在，如果已安裝[!DNL Marketo Measure]套件，您可以指出要納入哪些行銷活動作為合格的接觸點。 由於先前已有多個障礙存在，因此必須加以克服。 在CRM中安裝[!DNL Marketo Measure]套件之後，您的安全性團隊可能需要一些時間才能核准。 此外，在Campaign物件上使用單一挑選清單時缺乏彈性。 有了這項新功能，就不需要安裝套件即可開始使用Campaign和Campaign成員記錄。 可以建立規則，以明確定義可以建立的記錄，以明確定義哪些記錄是符合資格的。

## 需求 {#requirements}

* Campaign同步可用於所有層級
* 若要匯入資料，您仍需將CRM連線至您的[!DNL Marketo Measure]帳戶

## 運作方式 {#how-it-works}

1. 透過AccountAdmin許可權，您可以導覽至「**[!UICONTROL Settings]** > **[!UICONTROL Campaigns]**」並檢視「同步促銷活動成員」規則UI。
1. 按一下&#x200B;**+**&#x200B;圖示以開始建立規則。

   ![](assets/1-1.png)

1. 您可以選擇從[!UICONTROL Campaign]或[!UICONTROL Campaign Member]欄位建立規則。 使用我們想要驗證的運運算元和值填寫規則的其餘部分。 在下列範例中，我們會依名稱檢查特定Campaign。

   ![](assets/2-1.png)

   >[!NOTE]
   >
   >公式欄位無法在規則中使用，也不會出現在選擇清單中。 因為公式會在背景計算且不會修改記錄，[!DNL Marketo Measure]無法偵測記錄是否符合規則。

1. 選擇接觸點日期。 在您輸入大括弧`{`後，可能的日期清單就會顯示 — 然後您可以選取要選擇套用至所有從規則建立的接觸點的日期。

   ![](assets/3-1.png)

   >[!NOTE]
   >
   >如果您使用自訂Campaign同步規則，[!DNL Marketo Measure]將不會讀取您使用大量更新接觸點日期按鈕所做的任何更新。

1. 按一下核取記號，然後視需要為其他行銷活動新增其他規則。

   ![](assets/4-1.png)

   >[!NOTE]
   >
   >現在規則已與CRM同步功能一起定義，接著所述的規則自然會開始衝突。 如果選擇繼續使用自訂Campaign同步處理&#x200B;_和_ CRM同步處理型別，請務必建立規則，以免忽略您的CRM同步處理型別。

   ![](assets/5-1.png)

   >[!NOTE]
   >
   >如果您考慮最終停止[!UICONTROL CRM Sync Type]的使用者，最好建立不參照「同步型別」但&#x200B;_仍然_&#x200B;維持目前CRM接觸點的規則。 如此一來，進行切換時，規則仍可運作。

以下是看起來會如何的範例，如此就不會遺失任何現有的CRM接觸點：

## 驗證 {#validation}

您可以在Campaign中輕鬆檢查購買者接觸點和Buyer Attribution Touchpoint記錄，確保規則正常運作。 以下是[!DNL Marketo Measure]使用適當的動態接觸點日期建立、從行銷活動提取的BAT。 「建立日期」欄位位於下圖。

![](assets/6-1.png)

## 測試 {#testing}

1. Campaign同步功能隨附測試功能，可讓您檢查您建立的規則是否實際符合Campaign條件。 按一下[!UICONTROL Test]按鈕以開始。 必須先儲存規則，才能開始測試。

   ![](assets/7-1.png)

   畫面上會出現快顯視窗，您可於其中輸入行銷活動ID （CRM中的15或18個字元）以進行測試。 這主要是要輸入您嘗試同步之CRM的促銷活動ID，確保符合您建立的規則。

   ![](assets/8-1.png)

1. 按一下[!UICONTROL Test]之後，您將會看到適用於接觸點的促銷活動名稱和促銷活動成員數目。 下表會顯示與您的行銷活動ID相符的所有規則。 只會顯示相符專案。

   ![](assets/9.png)

1. 您也可以按一下「成員」計數，以檢視屬於Campaign規則適用性一部分的「銷售機會」和「聯絡人」及其ID清單。 這只是一個範例集，會顯示最多50筆記錄，讓您瞭解哪些記錄符合條件。

   ![](assets/10.png)
