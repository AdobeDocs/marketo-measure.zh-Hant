---
unique-page-id: 18874564
description: ' [!DNL Marketo Measure] Web工作階段的定義 —  [!DNL Marketo Measure]'
title: ' [!DNL Marketo Measure] 個Web工作階段的定義'
exl-id: ddf4f19d-2024-413a-b0ae-4efd468c24de
feature: Tracking
source-git-commit: 9a5e267b4b268d067fbbe89a00a4da96752a44db
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 0%

---

# [!DNL Marketo Measure]個Web工作階段的定義 {#definition-of-marketo-measure-web-sessions}

瞭解[!DNL Marketo Measure]如何定義Web工作階段。

**網頁工作階段**&#x200B;是指某人在特定時間內與您網站的互動。 作業會在使用者登陸您的網站時開始。

例如，Haley會造訪adobe.com。 她造訪網站會開始工作階段。 當Haley離開網站時，透過關閉標籤/網頁瀏覽器或導覽離開網站，工作階段結束。

一位使用者無法同時開啟多個工作階段。 如果Haley在10個個別索引標籤中開啟[!DNL adobe.com]，則與其網站造訪相關的工作階段僅建立一次。

## [!DNL Marketo Measure]如何定義新的工作階段？ {#how-does-marketo-measure-define-a-new-session}

有幾個因素可決定工作階段何時結束，以及新工作階段何時開始。 [!DNL Marketo Measure]工作階段結束的兩個主要方式為：

* **基於時間的到期**
* **頻道型到期日**

## 基於時間的到期 {#time-based-expiration}

### 舊版行為 {#legacy-behavior}

**工作階段持續多久？**

[!UICONTROL Marketo Measure]工作階段將在網站閒置30分鐘後結束。 例如：

Haley造訪adobe.com時，工作階段開始。 她瀏覽網站幾分鐘，然後離開電腦，但讓網站保持開啟狀態。 30分鐘未使用後，工作階段結束。

目前，[!UICONTROL Marketo Measure]僅將頁面導覽和表單提交視為活動。 在網頁上捲動或暫留在頁面上的元素上不被視為活動。 因此，如果Haley造訪adobe.com閱讀部落格，而閱讀部落格需要一小時，即使她捲動頁面上的內容，網路工作階段仍會在30分鐘後結束。

### 新行為 {#new-behavior}

對於新使用者，這將是預設行為。

現有使用者可以在&#x200B;**設定** > **每次接觸歸因** > **工作階段管道結轉**&#x200B;下開啟切換，即可採用新的行為。 此設定一經啟用即無法還原。

閒置30分鐘後建立新工作階段時，如果新工作階段在七天內開始，則會延續先前工作階段的管道。 此結轉僅適用於直接造訪（無反向連結或內部反向連結）。 如果閒置超過七天，新工作階段的管道會預設為「直接/其他」。 例如，如果Haley從Google造訪landingpage.com ，未活動超過30分鐘，且在7天內回訪，則新工作階段將保留Google管道。 不過，如果同一位使用者透過不同頻道重新瀏覽頁面，則非直接頻道不會由先前的Google頻道覆寫。

只有管道可以結轉，排除行銷活動或反向連結詳細資料。 這是因為管道分類是由Marketo Measure處理，而其他資料點則是分別收集。

**社交登入**

當訪客透過Google、Microsoft或Apple使用社交登入時，工作階段將合併為一個持續的工作階段。 例如，如果訪客從LinkedIn登陸頁面、完成Google社交登入並到達感謝頁面，則全部會計為單一工作階段。 如果沒有「工作階段管道結轉」切換開關，社交登入將會因外部反向連結而建立個別工作階段。

## 頻道型有效期 {#channel-based-expiration}

[!DNL Marketo Measure]會在使用者從不同數位行銷頻道或外部網站造訪您的網站時，開始新的工作階段。 其中包括：

* 引用網站
* 社交頻道（[!DNL Facebook]、[!DNL LinkedIn]等）
* 付費或有機搜尋管道([!DNL Google/Bing])

**轉介網站和社交管道**

每當訪客從反向連結網站或社交頻道造訪您的網站時，就會開始新的工作階段。

假設Haley在LinkedIn上，按一下[!DNL Marketo Measure]個貼文，然後被重新導向至Adobe網站。 接著，在捲動[!DNL Facebook]時，Haley看到另一個[!DNL Marketo Measure]貼文。 當她按一下此貼文，並重導至Adobe網站時，這會造成與[!DNL LinkedIn]相關的第一個網頁工作階段結束，且與[!DNL Facebook]相關的新工作階段開始。

**付費或有機搜尋管道**

每當使用者透過付費或有機搜尋管道造訪您的網站時，新工作階段就會開始。 如果Haley透過有機搜尋造訪Adobe網站，接著透過Google上的付費廣告立即造訪您的網站，則會建立兩個不同的工作階段。

**網頁直接流量**

如果訪客透過在網址列中鍵入您網站的URL來造訪您的網站，並不一定會導致新工作階段開始。

如果Haley的第一個網頁工作階段因反向連結網站、社交頻道或付費/有機搜尋頻道的造訪而開始，接著她透過Web直接造訪網站，則不會導致新的工作階段開始。

_但是_，如果Haley的第一個網頁工作階段來自Web Direct，然後她透過&#x200B;_外部/轉介網站_&#x200B;造訪網站，則第一個工作階段會結束，並開啟與外部/轉介網站相關的新工作階段。

## Google Analytics工作階段 {#google-analytics-sessions}

[!DNL Marketo Measure]和Google Analytics定義工作階段的方式有一些相似之處。 如需Google Analytics如何定義工作階段的詳細資訊，請造訪： [https://support.google.com/analytics/answer/2731565?hl=en](https://support.google.com/analytics/answer/2731565?hl=en){target="_blank"}
