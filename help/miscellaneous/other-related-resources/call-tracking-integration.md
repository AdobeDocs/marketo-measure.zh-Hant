---
unique-page-id: 18874592
description: 呼叫追蹤整合 —  [!DNL Marketo Measure]  — 產品檔案
title: 呼叫追蹤整合
exl-id: bc35a789-e056-4456-9038-306ed34c2a8e
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 0%

---

# 呼叫追蹤整合 {#call-tracking-integration}

我們與 [!DNL CallTrackingMetrics] 是用來合併網路工作階段與電話呼叫。 電話呼叫被視為提交至的表單 [!DNL Marketo Measure]. 它會將評分給予網路工作階段，否則只會被視為網路造訪，因為沒有實際的表單提交。

## 呼叫追蹤說明 {#call-tracking-explained}

一般意義上的「呼叫追蹤」是來自公司(例如 [!DNL CallTrackingMetrics], [!DNL DiaglogTech], [!DNL Invoca]，或 [!DNL CallRail]，舉幾個例子。 不重複電話號碼會根據使用者來自的不同行銷管道或行銷活動而顯示給使用者。 這可讓行銷人員了解這些管道或行銷活動的成效。

![](assets/1.png)

## 之前和之後 {#before-and-after}

查看下面的流程圖，了解如何 [!DNL Marketo Measure] 用於處理電話呼叫，而不與CallTrackingMetrics整合。 發生的電話未追蹤，因此被視為網路工作階段，未建立任何接觸點。 直到使用者完成表單的下次造訪，接觸點才最終填入。

透過整合，您可以看到網路工作階段實際上已系結至電話呼叫。 下一個表單填入最後會是PostLC接觸，仍會在歷程中受到追蹤。

![](assets/2.png)

## 運作方式 {#how-it-works}

CallTrackingMetrics必須在其結尾執行一些開發工作，才能順利運作。 使用他們放置在您網站上的javascript, CallTrackingMetrics可從 [!DNL Marketo Measure] cookie。 此「[!DNL BizibleId]「 」，則會由CallTrackingMetrics儲存。

訪客造訪您的網站並進行電話呼叫時， CallTrackingMetrics即應將該資料推送至 [!DNL Salesforce]  通常， [!DNL Salesforce Task] 已建立並填入電話號碼、主旨、類型等資料，現在則 [!DNL BizibleId]

此 [!DNL BizibleId] 是隨6.7+版安裝的欄位 [!DNL Marketo Measure] 行銷歸因套件。

以下是任務記錄的示例，其中 [!DNL BizibleId] 填入。

![](assets/3.png)

當 [!DNL Marketo Measure] 查找具有已知 [!DNL BizibleId] 值填入， [!DNL Marketo Measure] 可將該使用者對應至具有該使用者的網路工作階段 [!DNL BizibleId] 並將該工作階段歸因於電話呼叫，而非網路造訪。

## 接觸點 {#the-touchpoint}

當 [!DNL Marketo Measure] 可以匯入/下載任務，我們會連同網路工作階段一起處理該詳細資料。 在大多數情況下，它可與反向連結或廣告合併。 在下列範例中，訪客透過付費Google廣告找到該業務，並進行電話呼叫。

此 [!UICONTROL Touchpoint] 從任務提取「呼叫」類型（從上面的螢幕截圖中提取），該螢幕截圖在建立任務時也由CallTrackingMetrics填入。

![](assets/4.png)

## 報表 {#reporting}

接觸點類型值 [!DNL Marketo Measure] 推播通常是網路造訪、網頁表單或網路聊天，但若是呼叫追蹤量度接觸點，接觸點類型將是電話呼叫。 這可協助行銷人員了解哪些管道吸引最多的電話呼叫，並為其組織創造收入。

![](assets/5.png)

## 常見問題集 {#faq}

**為什麼我的接觸點類型是網路造訪？**

接觸點類型從「任務」。「類型」欄位中填入。 如果Task.Type欄位為空，則 [!DNL Marketo Measure] 會自動將「接觸點類型」設為「網站造訪」。 填入Task.Type欄位後 [!DNL Marketo Measure] 會讀取該值，並據此填入接觸點類型。

**電話呼叫會填入哪些其他欄位？**

「接觸點類型」和「媒體」都包含從Task.Type提取的資料。 所有其他資料點則從網頁追蹤和javascript資料中提取。

**為什麼此電話呼叫沒有系結至網路工作階段？**

首先，檢查「任務」，確認 [!DNL BizibleId] 填入。 如果沒有值，則不會，也無法為其建立接觸點。 這需要以CallTrackingMetrics呈報。

如果有值，請注意，我們只將所有網站工作階段視為30分鐘。 如果在中午12:17點點按了Google廣告（網站上的工作階段開始），但是直到下午1:05才發生電話呼叫，我們將不會合併網路工作階段和電話呼叫。 相反， [!DNL Marketo Measure] 將建立獨立 [!DNL Salesforce Task] 追蹤電話呼叫的接觸點，但不會有任何網路工作階段資料。

![](assets/6.png)

## 夥伴關係 {#partnerships}

[!DNL Marketo Measure] 目前有一個正式的呼叫追蹤合作夥伴，該合作夥伴已與我們進行「官方」整合程式，包括共同行銷和產品培訓。 這一個合作夥伴是CallTrackingMetrics。
