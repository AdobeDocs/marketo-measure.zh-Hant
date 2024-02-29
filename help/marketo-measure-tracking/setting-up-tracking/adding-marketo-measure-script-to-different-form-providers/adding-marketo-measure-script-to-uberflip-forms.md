---
unique-page-id: 18874749
description: 新增 [!DNL Marketo Measure] 編寫指令碼至 [!DNL Uberflip] FORMS - [!DNL Marketo Measure]
title: 新增 [!DNL Marketo Measure] 編寫指令碼至 [!DNL Uberflip] Forms
exl-id: fb123e15-523d-4931-b4c1-705fe49be3d0
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# 新增 [!DNL Marketo Measure] 編寫指令碼至 [!DNL Uberflip] Forms {#adding-marketo-measure-script-to-uberflip-forms}

如果您目前使用 [!DNL Uberflip] 若要管理您的內容，請務必採取以下必要步驟，以確保 [!DNL Marketo Measure] 正在追蹤這些表單提交。 您的成功經理，位於 [!DNL Uberflip] 您也應該能夠協助處理這個問題。

1. 將此指令碼新增至 [!DNL Uberflip]的 [!UICONTROL Custom Code>HTML] 區段。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 確定這一點 [!DNL Marketo Measure] 前導碼會在頁面載入和AJAX頁面變更時引發。 執行以下動作的時間範圍 [!UICONTROL Custom Code>JS] 區段

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   您會將此序言新增至 [!DNL Hubs.onLoad] 和 [!DNL Hubs.onPageChange] AJAX Javascript事件鉤點如下。 (注意：在這些事件鉤點中，您也可能有其他程式碼。 請務必也加入前言。)

   `Hubs.onLoad = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

   `Hubs.onPageChange = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

1. 建立並定義函式，在表單CTA提交時推送資料至Bizible。 這將會放入 [!UICONTROL Custom Code>Javascript] 區段。 （注意：此函式僅需要Uberflip提供的ctaData引數，但您可以包含其他引數ctaId和ctaName ，以防使用者想要自訂其程式碼以一併傳遞此資料）。

   `function bizibleFormCode(ctaId, ctaData, ctaName) {`
   `var email = ctaData["email"];`
   `if(email){`
   `Bizible.Push('User', {`
   `eMail: email, // required`
   `}); }`

   `}`

1. 表單CTA提交時，請確保 [!DNL Marketo Measure] 函式執行於下方。 這是在「 」中完成的 [!UICONTROL Custom Code>JS] 區段。 （注意：您可能在Hubs.onCtaFormSubmitSuccess javascript事件勾點中有其他程式碼，只要確定您也包含此函式呼叫即可）。

   `Hubs.onCtaFormSubmitSuccess = function (ctaId, ctaData, ctaName) {`
   `bizibleFormCode(ctaId, ctaData, ctaName);`\
   `}`
