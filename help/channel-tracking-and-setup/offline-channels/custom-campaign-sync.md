---
unique-page-id: 18874588
description: 自訂促銷活動同步 —  [!DNL Marketo Measure]  — 產品檔案
title: 自訂促銷活動同步
exl-id: 66f0e4e3-c1b6-443e-8ffa-06b67862b855
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 0%

---

# 自訂促銷活動同步 {#custom-campaign-sync}

今天，安裝 [!DNL Marketo Measure] 套件中，您可以指出要納入哪些促銷活動作為合格接觸點。 這有許多障礙，就像以前一樣。 一旦 [!DNL Marketo Measure] 套件已安裝在CRM中，您的安全性團隊可能需要一段時間才能核准。 此外，在Campaign物件上使用單一選擇清單缺乏彈性。 有了這項新功能，開始使用促銷活動和促銷活動成員記錄時，不需要安裝套件。 可以建立規則，以明確定義可建立哪些記錄，以明確定義哪些記錄符合條件。

## 需求 {#requirements}

* 促銷活動同步功能適用於所有層級
* 若要匯入資料，您仍需將CRM連線至您的 [!DNL Marketo Measure] 帳戶

## 運作方式 {#how-it-works}

1. 有了AccountAdmin權限，您可以導覽至 **[!UICONTROL Settings]** > **[!UICONTROL Campaigns]** 請參閱同步促銷活動成員規則UI。
1. 按一下 **+** 圖示以開始建立規則。

   ![](assets/1-1.png)

1. 您可以選擇從 [!UICONTROL Campaign] 或 [!UICONTROL Campaign Member] 欄位。 請使用預期要驗證的運算子和值來填寫規則的其餘部分。 在以下範例中，我們依名稱檢查特定促銷活動。

   ![](assets/2-1.png)

   >[!NOTE]
   >
   >公式欄位無法在規則中使用，且不會出現在選取清單中。 因為公式在背景計算，而不修改記錄， [!DNL Marketo Measure] 無法檢測記錄是否符合規則。

1. 選擇接觸點日期。 輸入大括弧後，可能的日期清單將出現 `{`  — 然後，您可以選取要選擇套用至從規則建立的所有接觸點的日期。

   ![](assets/3-1.png)

   >[!NOTE]
   >
   >如果您使用自訂促銷活動同步規則， [!DNL Marketo Measure] 不會閱讀您使用「大量更新接觸點日期」按鈕所進行的任何更新。

1. 按一下核取記號，然後視需要為其他促銷活動新增其他規則。

   ![](assets/4-1.png)

   >[!NOTE]
   >
   >現在，隨著CRM同步定義規則，所聲明的規則自然會開始產生衝突。 如果選擇繼續使用自訂促銷活動同步 _和_ CRM同步類型，建立規則是關鍵，因此CRM同步類型不會被忽略。

   ![](assets/5-1.png)

   >[!NOTE]
   >
   >如果您考慮最終停止 [!UICONTROL CRM Sync Type]，建立不參考「同步類型」但 _stal_ 維護目前的CRM接觸點。 如果/當進行切換時，規則仍然有效。

以下是看起來的樣子，這樣就不會遺失任何現有的CRM接觸點：

## 驗證 {#validation}

您可以輕鬆檢查Campaign中的「購買者接觸點」和「購買者歸因接觸點」記錄，以確保規則正常運作。 這是一個蝙蝠 [!DNL Marketo Measure] 以適當的動態接觸點日期建立，從促銷活動提取。 「建立日期」欄位位於其下方的影像中。

![](assets/6-1.png)

## 測試 {#testing}

1. 「促銷活動同步」功能隨附測試功能，讓您可以檢查您建立的規則是否實際符合促銷活動條件。 首先，按一下 [!UICONTROL Test] 按鈕。 必須先儲存規則，您才能開始測試。

   ![](assets/7-1.png)

   將會出現快顯視窗，供您輸入要測試的促銷活動ID（來自CRM的15或18個字元）。 重點是從您嘗試同步的CRM輸入促銷活動ID，以確保它符合您建立的規則。

   ![](assets/8-1.png)

1. 按一下 [!UICONTROL Test]，您會看到促銷活動的名稱，以及符合接觸點資格的促銷活動成員數目。 下方會顯示一個表格，顯示符合促銷活動ID的所有規則。 只會顯示符合項目。

   ![](assets/9.png)

1. 您也可以按一下成員計數，查看屬於促銷活動規則資格一部分的銷售機會和聯繫人及其Id的清單。 這只是一個範例集，最多會顯示50個，讓您了解哪些記錄符合資格。

   ![](assets/10.png)
