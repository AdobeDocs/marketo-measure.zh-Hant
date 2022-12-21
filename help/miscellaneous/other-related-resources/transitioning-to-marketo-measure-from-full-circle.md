---
unique-page-id: 18874535
description: 轉換到 [!DNL Marketo Measure] 從全圈 —  [!DNL Marketo Measure]  — 產品檔案
title: 轉換到 [!DNL Marketo Measure] 從全圓
exl-id: fd471771-33e2-413a-b155-02ba6e32e10c
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 0%

---

# 轉換到 [!DNL Marketo Measure] 從全圓 {#transitioning-to-marketo-measure-from-full-circle}

使從「完整圓形」移至 [!DNL Marketo Measure]? 你不是孤身一人。 以下是您需記住的最大考量，以及我們從做出變更的其他客戶那裡學到的經驗。

## 行銷活動型追蹤與多來源追蹤 {#campaign-based-tracking-vs-multi-source-tracking}

中的所有互動 [!UICONTROL Full Circle] 會透過CRM促銷活動成員資格來追蹤。 使用 [!DNL Marketo Measure]，則會透過JavaScript、CRM促銷活動成員資格及CRM活動記錄的組合來編譯購買歷程。 從「CRM促銷活動中必須追蹤所有互動，才能讓歸因報表正常運作」轉向「在CRM促銷活動中只需要追蹤這個互動子集，我們的歸因報表才能正常運作」，可能會很棘手。

一般來說，這是 [!DNL Marketo Measure] 為主要互動類型建立接觸點記錄：

* 網站上的表單填入： [!DNL Marketo Measure] Javascript
* 您網站上的頁面檢視：建立者 [!DNL Marketo Measure] 僅當此頁面檢視驅動指定的CRM里程碑時（如銷售機會或商機建立），才使用Javascript
* 離線互動，例如會議或商展：CRM行銷活動成員資格
* 網際網路上非您網站之處發生的數位互動（例如，由第三方網站托管並產生清單上傳的網路研討會）:CRM行銷活動成員資格
* 與銷售團隊的互動：CRM活動記錄

如果您熟悉CRM行銷活動管理，並偏好保留現有流程，那就好。 沒傷 [!DNL Marketo Measure] 以繼續追蹤CRM促銷活動中的所有互動。 您可以設計僅從所需的促銷活動子集建立接觸點的邏輯，以避免接觸點重複。

## 可見度與歸因的比較 {#visibility-vs-attribution}

透過最完整的社交圈設定，您可以查看每個人與您的行銷或銷售成果的互動。 頁面檢視、重複的頁面瀏覽、重複和一式三次促銷活動的成員資格 — 「完整社交圈」會呈現所有這些。 如果您檢視頁面300次，「完整社交圈」會建立300個重複的促銷活動，並為您提供每個促銷活動的成員資格。 [!DNL Marketo Measure] 不是的，這是我們有意識的設計決定。

[!DNL Marketo Measure] 旨在提供歸因故事，讓內容呈現有意義的互動，並在最具影響力的接觸點之間適當分配權重。 例如， [!DNL Marketo Measure] 框架不會將頁面檢視（沒有表單填入）顯示為例行接觸點。 獨立頁面檢視不太可能對推動購買歷程產生影響，但如果這是指定CRM里程碑（例如銷售機會或商機建立）之前的最新互動，我們將建立接觸點。 我們不想給你看。 從歸因的角度，我們想向您展示重要的內容。

與您的 [!DNL Marketo Measure] 代表可針對您的團隊將不再提供哪些資料設定適當的期望。

## 前 — [!DNL Marketo Measure] 資料 {#pre-marketo-measure-data}

標準建議是從您部署 [!DNL Marketo Measure] JavaScript會前進，而前任「完整社交圈」客戶的流量會加倍。 請思考上述兩節：您習慣看到數量較多的資料，也習慣了來自CRM促銷活動成員資格的所有資料。 如果您選擇加入您之前的部分或所有資料 [!DNL Marketo Measure] 實作時，您不會在整個JavaScript實作日期間比較apples和apples。

話雖如此，我們當然明白，許多客戶需要這些歷史資料；尤其是如果您的銷售週期較長（超過90天），您可能想要提供 [!DNL Marketo Measure] 預先[!DNL Marketo Measure] 資料。 請與您的 [!DNL Marketo Measure] 代表，並請務必記住，跨實施日期的扭曲可能會導致管道效能改善或參與下降，以及其他可能不正確的推斷。

## 摘要 {#in-summary}

您是一家好公司，我們幫助了許多其他客戶處理這些更改。 與您的 [!DNL Marketo Measure] 以了解上述影響，以及您可能有的任何其他問題。
