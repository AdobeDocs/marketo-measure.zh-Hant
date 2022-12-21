---
unique-page-id: 18874606
description: UTM參數 —  [!DNL Marketo Measure]  — 產品檔案
title: UTM參數
exl-id: 2b20f3c4-1f39-4ac5-bad1-cb1d630d60e9
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '948'
ht-degree: 0%

---

# UTM參數 {#utm-parameters}

標籤URL是擷取數位行銷工作相關資料的簡單而有效方式。 這是將參數新增至收集及記錄資料之URL結尾的程式。 最常用的參數為Google支援的Urchin追蹤模組(UTM)。 可用的UTM主要有五個：媒體、來源、促銷活動、內容和詞語。 下一節會更詳細地討論這些問題。

UTM參數可手動新增至URL，或透過特定平台（例如AdWords）的自動標籤附加。 自動標籤會自動化將參數附加至URL的程式。 此外， [URL產生器](https://ga-dev-tools.appspot.com/campaign-url-builder/){target=&quot;_blank&quot;}可加速手動標籤URL。 使用URL產生器時，您只需指定要用於每個參數的值，產生器就會為您設定URL格式。

## 什麼是UTM參數？ {#what-are-utm-parameters}

若要了解UTM參數如何運作，請查看沒有UTM的典型URL:

`http://www.adobe.com`

現在，讓我們查看包含UTM的URL。

`http://www.adobe.com?utm_medium=socialmedia&utm_source =facebook&utm_campaign=seasonal-sale&utm_content=photo-400x700px`

如您所見，第二個連結包含更多文字。 UTM參數一律位於頂層網域（此範例中為.com）之後，並以問號開頭。 之後，參數的順序並不重要，但建議遵循一致的命名慣例。 必須在每個參數之間放置&amp;符號，以分隔每個UTM。 現在，我們可以更詳細地說明每個參數代表什麼。

了解 [設定UTM參數的最佳實務](/help/channel-tracking-and-setup/online-channels/best-practices-for-setting-up-utm-parameters.md).

**utm_medium**

* Medium可識別您用來行銷公司的工具。
* 它回答了以下問題：「他們怎麼對你？」
* 它表示最高層的通道。
* 社交媒體、電子郵件、有機搜尋和付費搜尋都是潛在中型值的範例。
* 此參數會將資料對應至 [!DNL Marketo Measure] 「中」欄位。
* _[!DNL Marketo Measure]最佳實務：_ 請勿使用此欄位來呼叫子管道，否則在實際管道上產生報表時可能會遇到問題。 使用它來識別您的行銷工具或管道。 例如，如果您想使用電子郵件來行銷您的產品，媒體為電子郵件。

**utm_source**

* 來源可識別流量來源的子管道。
* 它回答了以下問題：「這人從哪來？」
* 在社交媒體範例中，流量來源是使用的社交媒體平台。
   * 在此範例中， [!DNL Facebook] 是來源值。 其他範例包括Twitter和Instagram。 如果UTM介質為 [!DNL Paid Search]，則UTM來源可以是AdWords或BingAds。

* 此參數會對應至 [!DNL Marketo Measure] SFDC中的「接觸點源」欄位。
* _[!DNL Marketo Measure]最佳實務：_ 此參數會追蹤您的流量來源，因此不適合使用它來指出廣告類型，例如重新定位、贊助等。 最好用來追蹤較高層級的子通道。 記住，你在回答「我的流量來自哪裡？」 您正在尋找反向連結。 在此範例中，UTM來源是您的廣告所在的位置（而非實際網頁，因為這會在標籤外部自動追蹤）。 如果您追蹤的是滴漏電子郵件促銷活動，則滴漏電子郵件是來源。

**utm_campaign**

* 促銷活動可用來識別特定的行銷活動。
* 它回答了以下問題：「他們為什麼來找你？」
* 使用此標籤來表示廣告促銷活動的名稱，如中所存在 [!DNL Google AdWords] 或 [!DNL BingAds]，或指出您從內部識別促銷活動的名稱。 您甚至可以使用此標籤來指定其他資訊，例如地理位置或廣告網路類型。
* 此參數會對應至 [!DNL Marketo Measure] SFDC中的「廣告促銷活動名稱」欄位。
* _[!DNL Marketo Measure]最佳實務_:在決定行銷活動名稱時，請避免在字詞之間使用標點符號或空格，因為使用這些符號可能會導致瀏覽器編碼錯誤。 為獲得最佳結果，請改用底線。

**utm_content**

* 如果您想要追蹤單一網頁上存在的多個行銷文章，請使用UTM內容參數。 例如，如果您有「要求示範」按鈕和「註冊參加每週電子報」按鈕，並想知道哪個按鈕產生最多流量，您可以為每個按鈕命名，並使用UTM內容標籤來追蹤它們。 每段「內容」的名稱是標籤的值。
* 此參數會對應至 [!DNL Marketo Measure] SFDC中的「廣告內容」欄位。
* _[!DNL Marketo Measure]最佳實務_:這是選用值，但 [!DNL Marketo Measure] 建議使用它。 此標籤與您要追蹤之廣告或行銷文章的標題相關聯。 如果您使用影像廣告，請務必將影像的尺寸寫入其標題。

**utm_term**

* 術語與UTM Content參數類似。 詞語非常適合用來識別付費促銷活動廣告中的關鍵字。 如果您使用自動標籤功能，則會為您完成此操作。 如果您沒有使用廣告平台的自動標籤功能，請務必小心新增您要追蹤的所有關鍵字。
* 此參數會對應至 [!DNL Marketo Measure] SFDC中的「關鍵字文本」欄位。
* _[!DNL Marketo Measure]最佳實務_:UTM詞語標籤是選用的，但非常適合追蹤關鍵字。 仔細檢查拼寫，避免使用特殊字元。 如果需要多個字詞，請嘗試使用底線或完全沒有空格。

每個參數都會收集與指派值相關的資訊。 每個標籤的值可讓您追蹤和排序所有數位行銷活動，並回答下列問題：哪裡，怎麼，為什麼？

這是UTM參數的圖表 [!DNL Marketo Measure] 參數及其系結至的對應接觸點欄位：

| **UTM參數** | **對應 [!DNL Marketo Measure] 欄位** |
|---|---|
| utm_medium | 中 |
| utm_source | 接觸點來源 |
| utm_campaign | 廣告促銷活動名稱 |
| utm_content | 廣告內容 |
| utm_term | 關鍵字文字 |
