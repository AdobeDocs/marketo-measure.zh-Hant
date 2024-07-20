---
unique-page-id: 18874606
description: UTM引數 —  [!DNL Marketo Measure]
title: UTM引數
exl-id: 2b20f3c4-1f39-4ac5-bad1-cb1d630d60e9
feature: UTM Parameters
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 0%

---

# UTM引數 {#utm-parameters}

標籤URL是擷取數位行銷工作相關資料的簡單有效方式。 是將引數新增至收集及記錄資料之URL結尾的程式。 最常使用的引數是Google支援的Urchin追蹤模組(UTM)。 有五個主要的UTM引數可供使用：Medium、Source、Campaign、Content和Term。 下一節將更詳細地討論這些內容。

UTM引數可以手動新增至URL，或透過特定平台（例如AdWords ）的自動標籤進行附加。 自動標籤會自動執行將引數附加至URL的程式。 也可選擇[URL建置器](https://ga-dev-tools.web.app/campaign-url-builder/){target="_blank"}以手動加速標籤URL。 使用URL產生器時，您只需指定要用於每個引數的值，產生器就會格式化您的URL。

## 什麼是UTM引數？ {#what-are-utm-parameters}

若要瞭解UTM引數如何運作，讓我們看看不含UTM的典型URL：

`http://www.adobe.com`

現在，讓我們檢視具有UTM的URL：

`http://www.adobe.com?utm_medium=socialmedia&utm_source =facebook&utm_campaign=seasonal-sale&utm_content=photo-400x700px`

第二個連結包含更多文字。 UTM引數一律位於最上層網域（此範例中為.com）後面，並以問號開頭。 之後，引數的順序並不重要，但建議遵循一致的命名慣例。 必須在每個引數之間放置&amp;符號，以分隔每個UTM。 現在，我們可以更詳細地瞭解每個引數代表什麼。

瞭解[設定UTM引數的最佳實務](/help/channel-tracking-and-setup/online-channels/best-practices-for-setting-up-utm-parameters.md)。

**utm_medium**

* Medium會識別您用來將公司推向市場的工具。
* 此文章回答的問題是：「他們如何接近您？」
* 它代表最高級別的管道。
* 社群媒體、電子郵件、有機搜尋和付費搜尋都是Medium潛在值的範例。
* 此引數會將資料對應至[!DNL Marketo Measure] &#39;Medium&#39;欄位。
* _[!DNL Marketo Measure]最佳實務：_&#x200B;請勿使用此欄位來呼叫子管道，否則在實際管道上產生報表時可能會遇到困難。 用它來識別您的行銷工具或管道。 例如，如果您想要使用電子郵件來行銷您的產品，媒體就是電子郵件。

**utm_source**

* Source會識別作為流量來源的子管道。
* 此報告回答以下問題：「這個人來自何處？」
* 在社群媒體範例中，流量的來源是使用中的社群媒體平台。
   * 在此範例中，[!DNL Facebook]是Source值。 其他範例為Twitter和Instagram。 另一方面，如果UTM Medium是[!DNL Paid Search]，則UTM Source可以是AdWords或BingAds。

* 此引數對應至SFDC中的[!DNL Marketo Measure]「接觸點Source」欄位。
* _[!DNL Marketo Measure]最佳實務：_&#x200B;此引數會追蹤您流量的來源，因此不適合用來指出廣告型別，例如重新鎖定目標、贊助等。 它最好用於追蹤較高層級的子管道。 請記住，您回答的問題為「我的流量來自何處？」 您在尋找反向連結。 在此範例中，UTM Source是廣告所在的位置（而非實際網頁，因為系統會自動在標籤外部追蹤該網頁）。 如果您追蹤的是滴答式電子郵件行銷活動，則滴答式電子郵件為來源。

**utm_campaign**

* Campaign用於識別特定的行銷活動。
* 此報告回答以下問題：「他們為什麼找您？」
* 使用此標籤表示廣告行銷活動的名稱，如同[!DNL Google AdWords]或[!DNL BingAds]中的名稱，或表示您內部識別行銷活動的名稱。 您甚至可以使用此標籤來指定其他資訊，例如地理位置或廣告網路型別。
* 此引數對應至SFDC中的[!DNL Marketo Measure]「廣告促銷活動名稱欄位」。
* _[!DNL Marketo Measure]最佳實務_：在判斷行銷活動名稱時，請避免使用標點符號或字詞之間的空白空格，因為使用這些符號可能會導致瀏覽器編碼錯誤。 為達到最佳效果，請改用底線。

**utm_content**

* 當您想要追蹤存在於單一網頁上的多個行銷片段時，請使用UTM內容引數。 例如，如果您有「要求示範」按鈕和「註冊我們的每週電子報」按鈕，且想知道哪個按鈕產生最多流量，您可以命名每個按鈕，並使用UTM內容標籤來追蹤它們。 每段「內容」的名稱是標籤的值。
* 此引數對應至SFDC中的[!DNL Marketo Measure]「廣告內容」欄位。
* _[!DNL Marketo Measure]最佳實務_：這是選擇性值，但[!DNL Marketo Measure]建議使用它。 此標籤與您要追蹤的廣告或行銷專案的標題相關聯。 如果您使用影像廣告，請務必在其標題中寫入影像的尺寸。

**utm_term**

* 辭彙與UTM內容引數類似。 辭彙非常適合用於識別付費行銷活動廣告中的關鍵字。 如果您使用自動標籤功能，這是為您完成的。 如果您未使用廣告平台的自動標籤功能，請務必小心新增您要追蹤的所有關鍵字。
* 此引數對應至SFDC中的[!DNL Marketo Measure] &#39;關鍵字文字&#39;欄位。
* _[!DNL Marketo Measure]最佳實務_： UTM Term標籤是選用的，但非常適合用於追蹤關鍵字。 仔細檢查拼字並避免使用特殊字元。 如果需要一個以上的單字，請嘗試使用底線或完全不使用空格。

每個引數都會收集與指定值相關的資訊。 每個標籤的值可讓您追蹤及排序所有數位行銷活動，並回答以下問題：哪裡、如何以及為什麼？

以下是UTM引數[!DNL Marketo Measure]剖析與其繫結的對應接觸點欄點陣圖表：

| **UTM引數** | **對應的[!DNL Marketo Measure]欄位** |
|---|---|
| utm_medium | 中 |
| utm_source | 接觸點Source |
| utm_campaign | 廣告行銷活動名稱 |
| utm_content | 廣告內容 |
| utm_term | 關鍵字文字 |
