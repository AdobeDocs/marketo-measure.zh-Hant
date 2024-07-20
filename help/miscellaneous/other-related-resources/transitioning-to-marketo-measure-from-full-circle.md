---
unique-page-id: 18874535
description: 正在從完整圓圈轉換為 [!DNL Marketo Measure]  - [!DNL Marketo Measure]
title: 正在從完整圓圈轉換為 [!DNL Marketo Measure]
exl-id: fd471771-33e2-413a-b155-02ba6e32e10c
feature: Attribution, Fundamentals
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 0%

---

# 正在從完整圓圈轉換為[!DNL Marketo Measure] {#transitioning-to-marketo-measure-from-full-circle}

正在從完整圓圈移動到[!DNL Marketo Measure]？ 您並不孤單。 以下是應牢記的最大考量事項，以及我們從進行切換的其他客戶那裡學到的經驗教訓。

## 行銷活動型追蹤與多Source追蹤的比較 {#campaign-based-tracking-vs-multi-source-tracking}

[!UICONTROL Full Circle]中的所有互動會透過CRM行銷活動成員資格進行追蹤。 透過[!DNL Marketo Measure]，購買歷程是透過我們的JavaScript、CRM行銷活動會員資格和CRM活動記錄的組合來編譯。 從「為了使我們的歸因報表正常運作，必須在CRM行銷活動中追蹤所有互動」轉移到「為了使我們的歸因報表正常運作，必須在CRM行銷活動中追蹤此互動子集」可能會很棘手。

一般而言，以下是[!DNL Marketo Measure]如何建立主要互動型別的接觸點記錄：

* 您的網站上的表單填寫： [!DNL Marketo Measure] JavaScript
* 您網站上的頁面檢視：唯有此頁面檢視推動指定的CRM里程碑（例如銷售機會或建立機會）時，才會由[!DNL Marketo Measure] JavaScript建立
* 離線互動，例如會議或商展： CRM行銷活動會籍
* 在網際網路上，非您網站的任何地方發生的數位互動（例如於產生清單上傳的第三方網站上主持的網路研討會）： CRM促銷活動會籍
* 與銷售團隊的互動：CRM活動記錄

如果您熟悉CRM行銷活動管理，且偏好維持現有程式，那就好。 繼續追蹤CRM行銷活動中的所有互動並不會影響[!DNL Marketo Measure]。 您可以設計只從所需行銷活動子集建立接觸點的邏輯，以避免接觸點重複。

## 可見性與歸因 {#visibility-vs-attribution}

透過大多數Full Circle設定，您可以看到個人與行銷或銷售工作的每次互動。 頁面檢視、重複的頁面造訪、三聯式行銷活動的成員資格 — 全部為完整圓形。 如果檢視頁面300次，Full Circle會建立300個重複的行銷活動，並為您提供每個行銷活動的成員資格。 [!DNL Marketo Measure]沒有，這是我們有意為之的設計決定。

[!DNL Marketo Measure]旨在為您提供歸因故事，呈現有意義的互動，並在最具影響力的接觸點之間適當地分配權重。 例如，[!DNL Marketo Measure]架構不會將頁面檢視（沒有表單填滿）顯示為例行接觸點。 獨立頁面檢視不太可能會對推動購買歷程產生影響，但若是指定的CRM里程碑之前的最新互動（例如銷售機會或商機建立），我們會建立接觸點。 我們不想向您顯示一切。 我們希望從歸因的角度顯示重要內容。

請與您的[!DNL Marketo Measure]代表合作，針對您的團隊將無法再使用的資料設定適當的期望。

## [!DNL Marketo Measure]以前的資料 {#pre-marketo-measure-data}

標準建議是從您部署[!DNL Marketo Measure] JavaScript之日起開始報告和資料收集，對於前Full Circle客戶而言，這會增加一倍。 請思考上述兩個區段：您習慣於看到較高的資料數量，而您已習慣於來自CRM行銷活動會籍的所有資料。 如果您選擇加入[!DNL Marketo Measure]實作之前的部分或全部資料，您將不會比較整個JavaScript實作日期的Apples與Apples。

儘管如此，我們當然瞭解許多客戶需要此歷史資料；特別是如果您有較長的銷售週期（超過90天），您可能想要讓[!DNL Marketo Measure]能看見pre-[!DNL Marketo Measure]資料。 請與您的[!DNL Marketo Measure]代表仔細討論，並永遠記住，在實施日期之間發生歪曲，可能會導致管道效能或參與度出現改善或下降，以及其他可能錯誤的推斷。

## 摘要 {#in-summary}

您公司情況良好，我們已協助其他許多客戶處理這些變更。 請與您的[!DNL Marketo Measure]代表合作，以瞭解上述影響以及您可能有的任何其他問題。
