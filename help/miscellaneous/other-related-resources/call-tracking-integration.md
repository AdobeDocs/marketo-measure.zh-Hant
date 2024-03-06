---
unique-page-id: 18874592
description: 呼叫追蹤整合 —  [!DNL Marketo Measure]
title: 呼叫追蹤整合
exl-id: bc35a789-e056-4456-9038-306ed34c2a8e
feature: Tracking, Integration
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 0%

---

# 呼叫追蹤整合 {#call-tracking-integration}

我們與整合 [!DNL CallTrackingMetrics] 旨在將網頁工作階段與電話通話合併。 系統會將電話視為提交的表單 [!DNL Marketo Measure]. 這會將Web工作階段的評分給予原本只會視為Web造訪，因為沒有實際提交的表單。

## 說明呼叫追蹤 {#call-tracking-explained}

一般來說，「來電追蹤」是來自下列公司的產品 [!DNL CallTrackingMetrics]， [!DNL DiaglogTech]， [!DNL Invoca]，或 [!DNL CallRail]，僅舉幾例。 系統會根據使用者來自的不同行銷管道或促銷活動，向使用者顯示唯一的電話號碼。 這可讓行銷人員檢視這些管道或行銷活動的執行情形。

![](assets/1.png)

## 之前和之後 {#before-and-after}

請看下方的流程圖，瞭解運作方式 [!DNL Marketo Measure] 用於處理通話，但未與CallTrackingMetrics整合。 所發生的電話通話遭取消追蹤，因此被視為網路工作階段，且未為其建立接觸點。 直到使用者下一次完成表單的造訪時，接觸點才會最終填入。

透過整合，您可以看到網頁工作階段實際上繫結至一個電話。 下一個表單填寫最終成為PostLC觸控，並且仍在歷程中受到追蹤。

![](assets/2.png)

## 運作方式 {#how-it-works}

CallTrackingMetrics必須在其終端執行一些開發工作，才能正常運作。 CallTrackingMetrics可透過其放置於您網站上的JavaScript從擷取_biz_uid [!DNL Marketo Measure] Cookie。 此&quot;[!DNL BizibleId]&quot;會由CallTrackingMetrics儲存。

訪客造訪您的網站並撥打電話時，CallTrackingMetrics的職責是將該資料推送至 [!DNL Salesforce].  通常 [!DNL Salesforce Task] 建立時會填入電話號碼、主旨、型別等資料，而現在則會填入 [!DNL BizibleId]

此 [!DNL BizibleId] 是隨6.7+版安裝的 [!DNL Marketo Measure] 行銷歸因套件。

以下範例為含有的Task記錄 [!DNL BizibleId] 已填入。

![](assets/3.png)

時間 [!DNL Marketo Measure] 尋找具有已知的Task記錄 [!DNL BizibleId] 已填入的值， [!DNL Marketo Measure] 可將該使用者對應至具有相同頁面的Web工作階段 [!DNL BizibleId] 並將該工作階段歸因於電話呼叫，而非網頁造訪。

## 接觸點 {#the-touchpoint}

時間 [!DNL Marketo Measure] 可以匯入/下載工作，我們會隨著網頁作業階段處理該詳細資訊。 通常可與反向連結或廣告合併。 在下列範例中，訪客透過付費Google廣告找到企業並撥打電話。

此 [!UICONTROL Touchpoint] 型別「Call」是從上方熒幕擷圖的「任務」提取，建立任務時也會由CallTrackingMetrics填入。

![](assets/4.png)

## 報告 {#reporting}

接觸點型別 [!DNL Marketo Measure] 推播通常是「網頁瀏覽」、「網頁表單」或「網頁聊天」，但若是CallTrackingMetrics接觸點，接觸點型別則為「電話」。 這可協助行銷人員檢視哪些頻道吸引的電話次數最多，並為其組織帶來收入。

![](assets/5.png)

## 常見問題集 {#faq}

**為什麼我的接觸點型別為Web造訪？**

「接觸點型別」會從「Task.Type」欄位填入。 如果Task.Type欄位為空白，則 [!DNL Marketo Measure] 會自動將接觸點型別設定為「網頁造訪」。 填入Task.Type欄位後 [!DNL Marketo Measure] 會讀取該值並據此填入接觸點型別。

**接觸點會從電話中填入哪些其他欄位？**

「接觸點型別」和「媒體」都包含從Task.Type中擷取的資料。 所有其他資料點都會從網路追蹤和JavaScript資料中提取。

**為什麼這個電話未與網路工作階段繫結？**

首先，檢查任務以確定有 [!DNL BizibleId] 已填入。 如果沒有值，我們就無法為其建立接觸點。 需要以CallTrackingMetrics將此問題呈報。

請注意，如果有值，我們只會將所有網路工作階段視為30分鐘。 如果Google廣告是在中午12:17 （網站上的工作階段開始）點選，但直到下午1:05才發生電話呼叫，則不會合併網頁工作階段和電話呼叫。 而是 [!DNL Marketo Measure] 建立單獨的 [!DNL Salesforce Task] 用於追蹤電話通話的接觸點，但不會有任何Web工作階段資料。

![](assets/6.png)

## 合作關係 {#partnerships}

[!DNL Marketo Measure] 目前有一個正式的呼叫追蹤合作夥伴，該合作夥伴已與我們進行「正式」整合程式，其中包括共同行銷和產品培訓。 此合作夥伴為CallTrackingMetrics。
