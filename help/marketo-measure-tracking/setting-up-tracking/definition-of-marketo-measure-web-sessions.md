---
unique-page-id: 18874564
description: 定義 [!DNL Marketo Measure] 網路工作階段 —  [!DNL Marketo Measure]
title: 定義 [!DNL Marketo Measure] Web工作階段
exl-id: ddf4f19d-2024-413a-b0ae-4efd468c24de
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 0%

---

# 定義 [!DNL Marketo Measure] Web工作階段 {#definition-of-marketo-measure-web-sessions}

瞭解如何 [!DNL Marketo Measure] 會定義Web工作階段。

A **網頁工作階段** 是指在特定時間內個人與您的網站的互動。 作業會在使用者登陸您的網站時開始。

例如，Haley會造訪adobe.com。 她造訪網站會開始工作階段。 當Haley離開網站時，透過關閉標籤/網頁瀏覽器或導覽離開網站，工作階段結束。

一位使用者無法同時開啟多個工作階段。 如果Haley開啟 [!DNL adobe.com] 在10個個別標籤中，僅建立與她造訪網站相關的工作階段。

## 如何 [!DNL Marketo Measure] 定義新的工作階段？ {#how-does-marketo-measure-define-a-new-session}

有幾個因素可決定工作階段何時結束，以及新工作階段何時開始。 兩種主要方式 [!DNL Marketo Measure] 可以結束的工作階段包括：

* **時間型到期日**
* **頻道型到期日**

## 基於時間的到期 {#time-based-expiration}

**工作階段持續多長時間？**

[!DNL Marketo Measure] 工作階段將在網站閒置30分鐘後結束。 例如：

Haley造訪adobe.com時，工作階段開始。 她瀏覽網站幾分鐘，然後離開電腦，但讓網站保持開啟狀態。 30分鐘未活動後，工作階段結束。

目前， [!DNL Marketo Measure] 僅將頁面導覽和表單提交視為活動。 在網頁上捲動或暫留在頁面上的元素上不被視為活動。 因此，如果Haley造訪adobe.com閱讀部落格，而閱讀部落格需要一小時，即使她捲動頁面上的內容，網路工作階段仍會在30分鐘後結束。

## 頻道型有效期 {#channel-based-expiration}

[!DNL Marketo Measure] 每當使用者從不同數位行銷頻道或外部網站造訪您的網站時，就會開始新的工作階段。 其中包括：

* 引用網站
* 社交管道([!DNL Facebook]， [!DNL LinkedIn]，等等)
* 付費或有機搜尋管道([!DNL Google/Bing])

**反向連結網站和社交管道**

每當訪客從反向連結網站或社交頻道造訪您的網站時，就會開始新的工作階段。

假設Haley在LinkedIn上，按一下 [!DNL Marketo Measure] 張貼並重新導向至Adobe網站。 接著，在捲動時 [!DNL Facebook]，Haley看到另一個 [!DNL Marketo Measure] 貼文。 當她按一下這篇文章，然後被重新導向到Adobe網站時，就會產生第一個相關的網路工作階段 [!DNL LinkedIn] 結束，以及與以下專案相關的新工作階段 [!DNL Facebook] 開始。

**付費或有機搜尋頻道**

每當使用者透過付費或有機搜尋管道造訪您的網站時，新工作階段就會開始。 如果Haley透過有機搜尋造訪Adobe網站，接著透過Google上的付費廣告立即造訪您的網站，則會建立兩個不同的工作階段。

**網站直接流量**

如果訪客透過在網址列中鍵入您網站的URL來造訪您的網站，並不一定會導致新工作階段開始。

如果Haley的第一個網頁工作階段因反向連結網站、社交頻道或付費/有機搜尋頻道的造訪而開始，接著她透過Web直接造訪網站，則不會導致新的工作階段開始。

_但是_，如果Haley的第一個網頁工作階段源自Web Direct，接著她透過造訪網站 _外部/轉介網站_，第一個工作階段會結束，並開啟與外部/轉介網站相關的新工作階段。

## Google Analytics工作階段 {#google-analytics-sessions}

與以下方式有一些相似之處 [!DNL Marketo Measure] 和Google Analytics會定義工作階段。 如需Google Analytics如何定義工作階段的詳細資訊，請造訪： [https://support.google.com/analytics/answer/2731565?hl=en](https://support.google.com/analytics/answer/2731565?hl=en){target="_blank"}
