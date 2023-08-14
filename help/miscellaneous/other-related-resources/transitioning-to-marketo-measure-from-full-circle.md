---
unique-page-id: 18874535
description: 正在轉換為 [!DNL Marketo Measure] 從完整圓形 —  [!DNL Marketo Measure]  — 產品檔案
title: 正在轉換為 [!DNL Marketo Measure] 從完整圓形
exl-id: fd471771-33e2-413a-b155-02ba6e32e10c
feature: Attribution, Fundamentals
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 0%

---

# 正在轉換為 [!DNL Marketo Measure] 從完整圓形 {#transitioning-to-marketo-measure-from-full-circle}

從完整圓形移動到 [!DNL Marketo Measure]？ 您並不孤單。 以下是應牢記的最大考量事項，以及我們從進行切換的其他客戶那裡學到的經驗教訓。

## 促銷活動型追蹤和多來源追蹤的比較 {#campaign-based-tracking-vs-multi-source-tracking}

中的所有互動 [!UICONTROL Full Circle] 會透過CRM行銷活動會籍進行追蹤。 替換為 [!DNL Marketo Measure]，購買歷程是透過我們的JavaScript、CRM行銷活動會員資格和CRM活動記錄的組合來編譯。 從「為了使我們的歸因報表正常運作，必須在CRM行銷活動中追蹤所有互動」轉移到「為了使我們的歸因報表正常運作，只需在CRM行銷活動中追蹤此互動子集」可能會很棘手。

一般而言，以下說明方法 [!DNL Marketo Measure] 建立主要互動型別的接觸點記錄：

* 您的網站上的表單填寫： [!DNL Marketo Measure] Javascript
* 您網站上的頁面檢視：建立者 [!DNL Marketo Measure] 只有當此頁面檢視推動指定的CRM里程碑（例如銷售機會或建立機會）時，才會使用Javascript
* 離線互動，例如會議或商展： CRM行銷活動會籍
* 在網際網路上，非您網站的任何地方發生的數位互動（例如於產生清單上傳的第三方網站上主持的網路研討會）： CRM促銷活動會籍
* 與您的銷售團隊互動：CRM活動記錄

如果您對CRM行銷活動管理感到滿意，且偏好維持現有程式，則沒問題。 不會造成傷害 [!DNL Marketo Measure] 以繼續追蹤CRM行銷活動中的所有互動。 您可以設計只從所需行銷活動子集建立接觸點的邏輯，以避免接觸點重複。

## 可見性與歸因 {#visibility-vs-attribution}

透過大多數Full Circle設定，您可以看到個人與行銷或銷售工作的每一次互動。 頁面檢視、重複的頁面造訪、重複和三重行銷活動的成員資格 — 完整圓形會呈現所有這些專案。 如果檢視頁面300次，Full Circle會建立300個重複的行銷活動，並為您提供每個行銷活動的成員資格。 [!DNL Marketo Measure] 不會，這是我們有意為之的設計決策。

[!DNL Marketo Measure] 旨在為您提供歸因故事，該故事可呈現有意義的互動，並適當地分配最具影響力接觸點的權重。 例如， [!DNL Marketo Measure] framework不會將頁面檢視（沒有表單填色）顯示為例行接觸點。 獨立頁面檢視不太可能會對推動購買歷程產生影響，但若是指定的CRM里程碑之前的最新互動（例如銷售機會或商機建立），我們將建立接觸點。 我們不想向您顯示一切。 我們希望從歸因的角度顯示重要內容。

使用您的 [!DNL Marketo Measure] 代表針對您的團隊將無法再使用的資料設定適當的期望。

## 預先[!DNL Marketo Measure] 資料 {#pre-marketo-measure-data}

標準建議是從您部署之日起開始報告和資料收集 [!DNL Marketo Measure] JavaScript向前推進，對於前Full Circle客戶來說更是如此。 請思考上述兩個區段：您已習慣看到較高的資料數量，並已習慣所有來自CRM行銷活動會籍的資料。 如果您選擇納入之前的部分或全部資料 [!DNL Marketo Measure] 實作期間，您不會比較JavaScript實作日期內的Apples和Apples。

儘管如此，我們當然瞭解許多客戶需要這項歷史資料，尤其是如果您有較長的銷售週期（超過90天），您可能會想要提供 [!DNL Marketo Measure] 能見度預先設定[!DNL Marketo Measure] 資料。 請與您仔細討論 [!DNL Marketo Measure] 代表，並務必記住，在實施日期之間發生偏差可能導致管道效能或參與度出現改善或下降，以及其他潛在錯誤的推斷。

## 摘要 {#in-summary}

您公司情況良好，我們已協助其他許多客戶處理這些變更。 使用您的 [!DNL Marketo Measure] 代表瞭解上述影響，以及您可能有的任何其他問題。
