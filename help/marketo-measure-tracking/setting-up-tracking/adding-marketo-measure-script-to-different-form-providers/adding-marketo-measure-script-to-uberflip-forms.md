---
unique-page-id: 18874749
description: 正在新增 [!DNL Marketo Measure] 指令碼至 [!DNL Uberflip] Forms - [!DNL Marketo Measure]
title: 正在新增 [!DNL Marketo Measure] 指令碼至 [!DNL Uberflip] Forms
exl-id: fb123e15-523d-4931-b4c1-705fe49be3d0
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 0%

---

# 正在新增[!DNL Marketo Measure]指令碼至[!DNL Uberflip] Forms {#adding-marketo-measure-script-to-uberflip-forms}

如果您目前使用[!DNL Uberflip]管理您的內容，請務必採取這些必要步驟，以確定[!DNL Marketo Measure]正在追蹤這些表單提交。 您在[!DNL Uberflip]的成功管理員也應該能夠協助您完成此工作。

1. 將此指令碼新增至[!DNL Uberflip]的[!UICONTROL Custom Code>HTML]區段。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 請確定此[!DNL Marketo Measure]前導碼會在頁面載入和AJAX頁面變更時引發。 在[!UICONTROL Custom Code>JS]區段中執行此動作

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   將此序言新增至下方的[!DNL Hubs.onLoad]和[!DNL Hubs.onPageChange]個AJAX JavaScript事件鉤點。 (注意：在這些事件勾點中，您也可能有其他程式碼。 請務必也加入前言。)

   `Hubs.onLoad = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

   `Hubs.onPageChange = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

1. 建立並定義在提交表單CTA時將資料推送到Bizible的函式。 這會進入[!UICONTROL Custom Code>JavaScript]區段。 （注意：此函式僅需要Uberflip提供的ctaData引數，但您可以包含其他引數ctaId和ctaName ，以防使用者想要自訂其程式碼以一併傳遞此資料）。

   `function bizibleFormCode(ctaId, ctaData, ctaName) {`
   `var email = ctaData["email"];`
   `if(email){`
   `Bizible.Push('User', {`
   `eMail: email, // required`
   `}); }`

   `}`

1. 在提交表單CTA時，請確定您的[!DNL Marketo Measure]函式已按照以下執行。 這是在[!UICONTROL Custom Code>JS]區段內完成。 (注意：Hubs.onCtaFormSubmitSuccess JavaScript事件勾點中可能有其他程式碼，請確定您也包含此函式呼叫)。

   `Hubs.onCtaFormSubmitSuccess = function (ctaId, ctaData, ctaName) {`
   `bizibleFormCode(ctaId, ctaData, ctaName);`\
   `}`
