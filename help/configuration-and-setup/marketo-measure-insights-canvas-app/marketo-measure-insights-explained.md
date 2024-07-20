---
unique-page-id: 18874676
description: '[!DNL Marketo Measure]深入分析說明 —  [!DNL Marketo Measure]'
title: "[!DNL Marketo Measure]深入分析已說明"
exl-id: d479a15f-4c92-4302-8ce8-6487645012e1
feature: Reporting
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# [!DNL Marketo Measure]深入分析說明 {#marketo-measure-insights-explained}

瞭解[!DNL Salesforce]中的[!DNL Marketo Measure]深入分析檢視，包括不同的圖示代表什麼以及如何使用功能。 此功能非常有助於檢視潛在客戶、聯絡人或帳戶的前20個工作階段。

在[!DNL Marketo Measure] JavaScript追蹤某人並在您的網站上填寫表單後，該人員就會成為您系統中的銷售機會，其數位行銷資料會傳送至您的Salesforce (SFDC)組織。 發生此情況時，您會看到接觸點資料已填入Lead/Contact/Opportunity/Account Objects的[!DNL Marketo Measure] Lead Insights區段(Canvas App)中。

首先，您可在深入分析的中間部分中看到訪客在您網站上的工作階段數量。 您可以隨意捲動這些工作階段並導覽。

![](assets/1.png)

如果您按一下深入分析中上部的「全部」，您可以檢視所有工作階段的統計資料。 您可在此瞭解個別工作階段的日期、造成這些事件的頻道或來源，以及指定更多資訊的一組圖示。

您首先看到的是FT或LC圖示。 這些代表所列工作階段的接觸點位置。 具體來說，FT代表「首次接觸」，而LC代表「建立銷售機會」。 您可以有多個工作階段，但只有一個接觸點可以是FT或LC。 您永遠找不到與一個人相關聯的多個FT或LC。

看起來像紙張的圖示表示頁面檢視發生在工作階段中。 每個工作階段都可能包含此圖示。

![](assets/2.png)

看起來像燒杯的圖示表示已發生A/B測試實驗。 我們目前整合Optimizy和VWO。 透過這項整合，我們能夠推送使用者在其特定工作階段中看到的實驗與變數。

![](assets/3.png)

如果按一下任何特定作業階段（按一下作業階段的實際日期或分組作業階段的中上部，即可執行此操作），您將能夠檢視作業階段詳細資訊。 在每個工作階段中，您可以看到使用者看見的所有特定頁面，依日期和時間排序。

![](assets/4.png)

在每個工作階段的右側，您可以看到推送SFDC中[!DNL Marketo Measure]欄位的更多精細行銷資料。 在此範例中，您可以看到廣告群組、廣告內容、促銷活動、關鍵字、Medium。 您也可以向下捲動，檢視我們提供的[!DNL Marketo Measure]資料。

最後，某人擁有大量工作階段後，您就可以在[!UICONTROL Insights]中使用一些篩選器，尋找其在您網站上的特定參與部分。 例如，您可以依[!UICONTROL Touchpoint Position]篩選。

您也可以依頁面檢視、AB測試或Forms來搜尋。
