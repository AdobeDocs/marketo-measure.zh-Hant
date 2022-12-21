---
unique-page-id: 18874564
description: 定義 [!DNL Marketo Measure] 網路會議 —  [!DNL Marketo Measure]  — 產品檔案
title: 定義 [!DNL Marketo Measure] 網路會議
exl-id: ddf4f19d-2024-413a-b0ae-4efd468c24de
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---

# 定義 [!DNL Marketo Measure] 網路會議 {#definition-of-marketo-measure-web-sessions}

了解如何 [!DNL Marketo Measure] 定義網路工作階段。

A **網站工作階段** 是指某個人在特定時間內與您網站的互動。 工作階段從使用者登陸您的網站時開始。

例如，Haley造訪adobe.com。 她到網站的參觀開始了一個會議。 海利離開網站時，關閉標籤/網頁瀏覽器或離開網站導覽，工作階段結束。

一個用戶不能同時開啟多個會話。 如果海莉開啟 [!DNL adobe.com] 在10個不同的標籤中，只建立了一個與她造訪網站相關的工作階段。

## 如何 [!DNL Marketo Measure] 定義新工作階段？ {#how-does-marketo-measure-define-a-new-session}

有些項目可決定工作階段何時結束，以及新工作階段何時開始。 兩種主要方式 [!DNL Marketo Measure] 工作階段可結束為：

* **基於時間的到期**
* **管道型到期**

## 基於時間的過期 {#time-based-expiration}

**工作階段會持續多久？**

[!DNL Marketo Measure] 工作階段會在網站上閒置30分鐘後結束。 例如：

海莉造訪adobe.com時，會開始一次作業。 她瀏覽了幾分鐘，然後離電腦遠了一步，但網站卻保持開放。 閒置30分鐘後，工作階段會結束。

目前， [!DNL Marketo Measure] 只會將頁面導覽和表單提交視為活動。 捲動網頁或暫留在頁面上的元素時，不視為活動。 因此，如果海莉去adobe.com看一篇部落格文章，花了一個小時才讀完，即使她捲動了網頁上的內容，她的網路會在30分鐘後結束。

## 管道型有效期 {#channel-based-expiration}

[!DNL Marketo Measure] 每當使用者從不同的數位行銷管道或外部網站造訪您的網站時，就會開始新的工作階段。 這包括：

* 轉介網站
* 社交管道([!DNL Facebook], [!DNL LinkedIn]等)
* 付費或自然搜尋管道([!DNL Google/Bing])

**轉介網站與社交管道**

每當訪客從反向連結網站或社交管道造訪您的網站時，就會開始新的工作階段。

假設海莉在LinkedIn，點擊 [!DNL Marketo Measure] 貼文後會重新導向至Adobe網站。 然後，在滾動時 [!DNL Facebook]海莉又看到了 [!DNL Marketo Measure] 貼文。 當她點按此貼文並被重新導向至Adobe網站時，就會產生與 [!DNL LinkedIn] 結束時，以及與 [!DNL Facebook] 開始。

**付費或自然搜尋管道**

每當使用者透過付費或自然搜尋管道造訪您的網站時，就會開始新的工作階段。 如果海莉透過有機搜尋來到Adobe網站，接著透過Google的付費廣告立即造訪您的網站，則會建立兩個不同的工作階段。

**Web直接流量**

如果訪客在位址列中輸入您網站的URL來造訪您的網站，並不一定會導致新的工作階段開始。

如果海莉的第一個網路工作階段是因為來自反向連結網站、社交管道或付費/有機搜尋管道的造訪而開始，然後她直接透過網路造訪網站，就不會導致新的工作階段開始。

_不過_，如果海莉的第一次網路會話源自Web Direct，那麼她將通過 _外部/轉介網站_，則第一個工作階段會結束，並開啟與外部/反向連結網站相關的新工作階段。

## Google Analytics工作階段 {#google-analytics-sessions}

這些方法有些相似之處 [!DNL Marketo Measure] 和Google Analytics定義工作階段。 如需Google Analytics如何定義工作階段的詳細資訊，請造訪： [https://support.google.com/analytics/answer/2731565?hl=en](http://support.google.com/analytics/answer/2731565?hl=en){target=&quot;_blank&quot;}
