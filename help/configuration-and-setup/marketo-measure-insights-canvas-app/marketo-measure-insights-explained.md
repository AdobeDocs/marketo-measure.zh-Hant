---
unique-page-id: 18874676
description: '"[!DNL Marketo Measure] 深入分析說明 —  [!DNL Marketo Measure]  — 產品檔案」'
title: '"[!DNL Marketo Measure] 已說明的深入分析」'
exl-id: d479a15f-4c92-4302-8ce8-6487645012e1
feature: Reporting
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 0%

---

# [!DNL Marketo Measure] 已說明的深入分析 {#marketo-measure-insights-explained}

瞭解 [!DNL Marketo Measure] 前瞻分析檢視於 [!DNL Salesforce]，包括不同圖示代表什麼以及如何使用功能。 此功能非常有助於檢視潛在客戶、聯絡人或帳戶的前20個工作階段。

一旦某人由 [!DNL Marketo Measure] javascript並在您的網站上填寫表單，該人員將成為您系統中的銷售機會，我們會將他們的數位行銷資料推送至您的Salesforce (SFDC)組織。 發生此情況時，您會看到內填入的接觸點資料 [!DNL Marketo Measure] 潛在客戶/聯絡人/商機/帳戶物件的潛在客戶深入分析區段（畫布應用程式） 。

首先，您會在深入分析的中間部分看到此人在您的網站上參與的工作階段數量。 您可以隨意捲動這些工作階段並導覽。

![](assets/1.png)

如果您按一下深入分析中上角的「全部」，即可檢視所有工作階段的統計資料。 您將瞭解各個工作階段的日期、造成這些事件的頻道或來源，以及指定更多資訊的一組圖示。

您首先會看到FT或LC圖示。 這些代表所列工作階段的接觸點位置。 具體來說，FT代表「首次接觸」，而LC代表「建立銷售機會」。 您可以有多個工作階段，但只有一個接觸點可以是FT或LC。 您永遠找不到與一個人相關聯的多個FT或LC。

看起來像紙張的圖示表示頁面檢視發生在工作階段中。 每個工作階段都可能包含此圖示。

![](assets/2.png)

看起來像燒杯的圖示表示已發生A/B測試實驗。 我們目前整合Optimizy和VWO。 透過這項整合，我們能夠推送使用者在其特定工作階段中看到的實驗與變數。

![](assets/3.png)

如果按一下任何特定作業階段（按一下作業階段的實際日期或分組作業階段的中上部，即可執行此操作），您將會看到作業階段的詳細資訊。 在每個工作階段中，您可以看到使用者看見的所有特定頁面，依日期和時間排序。

![](assets/4.png)

在每個工作階段的右側，您可以看到我們正在推送的更多精細行銷資料 [!DNL Marketo Measure] SFDC中的欄位 在此範例中，您可以看到廣告群組、廣告內容、促銷活動、關鍵字、媒體。 您也可以向下捲動以檢視更多 [!DNL Marketo Measure] 我們提供的資料。

最後，某人擁有大量工作階段後，您便可以在內使用部分篩選器 [!UICONTROL Insights] 以尋找他們在您網站上的參與的特定部分。 篩選依據 [!UICONTROL Touchpoint Position] 例如。

您也可以依頁面檢視、AB測試或Forms來搜尋。
