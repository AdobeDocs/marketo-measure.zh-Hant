---
unique-page-id: 35586069
description: 確保Marketo Measure Js中GDPR的同意 — Marketo Measure — 產品檔案
title: 確保Marketo Measure Js中的GDPR同意
exl-id: 9afc5e4d-cf97-4c49-b9ee-ee1cc99c1f90
source-git-commit: c7d3bbce1f0c6a99409822c06c43961c93cd9458
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# 確保Marketo Measure Js中的GDPR同意 {#ensuring-consent-for-gdpr-in-marketo-measure-js}

一般資料保護規範(GDPR)是歐盟一項於2018年5月25日生效的法規。

## 概觀 {#overview}

GDPR的目的在於加強歐盟(EU)和歐洲經濟區(EEA)內資料主體對於其個人資料的使用與保護方式的權利。 個人資料是指與已識別或可識別的自然人相關的任何資訊。 GDPR適用於歐盟內外向歐盟和EEA內的資料主體行銷商品或服務，及/或追蹤其行為的任何組織。 如果您在歐洲與涉及處理個人資料的資料主體有業務往來，本法規適用於您。 對不遵守規定的人處以高額罰款；單次違規的最高罰款金額為2000萬歐元，即全球年營業額的4%，以其中的更高者為準。

依預設， [!DNL bizible.js] 收集使用者的analytics資料，除非已特別設定以等待同意。 當 [!DNL bizible.js] 設定為等待使用者同意，則不會建立任何cookie或傳送任何analytics資料，直到達到同意為止。

## 如何等待同意 {#how-to-wait-for-consent}

有兩種方式可設定 [!DNL bizible.js] 等待同意。

選項1 — 取代預設值 [!DNL bizible.js] 指令碼標籤：

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-consent-button-id="ConsentButtonId"></script>`

**如果您使用 [!DNL Google Tag Manager] 安裝指令碼**，請記住GTM會移除資料屬性，因此請改用下列指令碼：

`<span id="bizible-settings" data-consent-button-id="ConsentButtonId"></span>`
`<script type="text/javascript" src=https://cdn.bizible.com/scripts/bizible.js async=""></script>`

>[!NOTE]
>
>在這種情況下， [!DNL bizible.js] 會將點按上事件附加至id為「ConsentButtonId」的HTML元素。

按一下此HTML元素時， [!DNL bizible.js] 會建立Cookie，以記住已收到使用者同意，並照常開始收集analytics資料。

**-或-**

選項2 — 取代預設值 [!DNL bizible.js] 指令碼標籤：

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-requires-user-consent="true"></script>`

這說明 [!DNL bizible.js] 若要在取得同意前不進行追蹤，可使用下列JS API完成：

*視窗[&#39;Bizible&#39;] =視窗[&#39;Bizible&#39;] || { _queue: []，推送：函式(o, p){此。_queue.push({類型：o，資料：p });} };*

*Bizible.Push(&#39;Consent&#39;, true);*

**如果您使用 [!DNL Google Tag Manager] 安裝指令碼**，請記住GTM會移除資料屬性，因此請改用下列指令碼：

`<span id="bizible-settings" data-requires-user-consent="true"></span>`
`<script type="text/javascript" src=https://cdn.bizible.com/scripts/bizible.js async=""></script>`

>[!NOTE]
>
>bizible.js將建立Cookie，記住已收到使用者同意，且只有在呼叫JS API後，才會照常開始收集analytics資料。

相反地，客戶也可以使用此API來撤回使用者的同意：

`window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) { this._queue.push({ type: o, data: p }); } };`

`Bizible.Push('Consent', false);`

執行此程式碼時，會刪除所有 [!DNL bizible.js] 之前已建立，只有在使用者重新同意時才會繼續收集analytics資料。
