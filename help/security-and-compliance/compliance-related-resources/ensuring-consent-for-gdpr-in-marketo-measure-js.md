---
unique-page-id: 35586069
description: 在Marketo Measure Js中確保GDPR的同意 — Marketo Measure — 產品檔案
title: 在Marketo Measure Js中確保GDPR的同意
exl-id: 9afc5e4d-cf97-4c49-b9ee-ee1cc99c1f90
feature: Tracking
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 0%

---

# 在Marketo Measure Js中確保GDPR的同意 {#ensuring-consent-for-gdpr-in-marketo-measure-js}

一般資料保護規範(GDPR)是一項歐盟法規，於2018年5月25日生效。

## 概觀 {#overview}

GDPR的目的是加強歐盟(EU)和歐洲經濟區(EEA)內資料主體對其個人資料的使用和保護方式的權利。 「個人資料」是指與已識別或可識別的自然人相關的任何資訊。 GDPR適用於歐盟內或歐盟以外任何向歐盟及EEA內的資料主體行銷商品或服務及/或追蹤其行為的組織。 如果您與歐洲資料主體有業務往來，涉及處理其個人資料，此法規即適用於您。 違規者將受到嚴厲的處罰，違規者會被處以鉅額罰款；單次違規的最高罰款為2,000萬歐元，或全球每年營業額的4%，以金額較大者為準。

根據預設， [!DNL bizible.js] 收集使用者的analytics資料，除非將其設定為等待同意。 時間 [!DNL bizible.js] 設為等待使用者同意，在取得同意前不會建立任何cookie或傳送任何analytics資料。

## 如何等待同意 {#how-to-wait-for-consent}

有兩種設定方式 [!DNL bizible.js] 以等待同意。

選項1 — 取代預設值 [!DNL bizible.js] 指令碼標籤：

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-consent-button-id="ConsentButtonId"></script>`

**如果您使用 [!DNL Google Tag Manager] 安裝指令碼**，請記住GTM會移除資料屬性，因此請改用下列指令碼：

`<span id="bizible-settings" data-consent-button-id="ConsentButtonId"></span>`
`<script type="text/javascript" src=https://cdn.bizible.com/scripts/bizible.js async=""></script>`

>[!NOTE]
>
>在這種情況下， [!DNL bizible.js] 附加點按事件至ID為「ConsentButtonId」的HTML元素。

當按一下此HTML元素時， [!DNL bizible.js] 建立Cookie以記住已收到使用者的同意，並照常開始收集分析資料。

**— 或 —**

選項2 — 取代預設值 [!DNL bizible.js] 指令碼標籤：

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-requires-user-consent="true"></script>`

這會告訴 [!DNL bizible.js] 達到同意前不會追蹤，這可以用下列JS API完成：

*視窗[&#39;Bizible&#39;] = window[&#39;Bizible&#39;] || { _queue： []，推播：函式(o， p) {這個。_queue.push({ type： o， data： p })； } }；*

*Bizible。 Push(&#39;Consent&#39;， true)；*

**如果您使用 [!DNL Google Tag Manager] 安裝指令碼**，請記住GTM會移除資料屬性，因此請改用下列指令碼：

`<span id="bizible-settings" data-requires-user-consent="true"></span>`
`<script type="text/javascript" src=https://cdn.bizible.com/scripts/bizible.js async=""></script>`

>[!NOTE]
>
>bizible.js將建立Cookie以記住，已收到使用者的同意，並只在呼叫JS API後，才照常開始收集分析資料。

相反地，客戶也可以使用此API來撤銷使用者的同意：

`window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) { this._queue.push({ type: o, data: p }); } };`

`Bizible.Push('Consent', false);`

此程式碼執行時，會刪除符合以下條件的所有Cookie： [!DNL bizible.js] 之前已建立，且僅在使用者同意時才會恢復analytics資料的收集。
