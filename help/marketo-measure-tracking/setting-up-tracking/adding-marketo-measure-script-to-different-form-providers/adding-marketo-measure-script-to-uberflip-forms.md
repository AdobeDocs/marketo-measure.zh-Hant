---
unique-page-id: 18874749
description: 新增 [!DNL Marketo Measure] 指令碼至 [!DNL Uberflip] Forms - [!DNL Marketo Measure]  — 產品檔案
title: 新增 [!DNL Marketo Measure] 指令碼至 [!DNL Uberflip] Forms
exl-id: fb123e15-523d-4931-b4c1-705fe49be3d0
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 0%

---

# 新增 [!DNL Marketo Measure] 指令碼至 [!DNL Uberflip] Forms {#adding-marketo-measure-script-to-uberflip-forms}

如果您目前使用 [!DNL Uberflip] 若要管理您的內容，請務必採取這些必要步驟，確保 [!DNL Marketo Measure] 追蹤這些表單提交。 您的成功經理： [!DNL Uberflip] 也應該能幫你。

1. 將此指令碼添加到 [!DNL Uberflip]&#39;s [!UICONTROL Custom Code>HTML] 區段。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 確保 [!DNL Marketo Measure] 頁面載入和AJAX頁面變更時會觸發前導程式碼。 在 [!UICONTROL Custom Code>JS] 節

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   您將在 [!DNL Hubs.onLoad] 和 [!DNL Hubs.onPageChange] AJAX Javascript事件下方的鈎點。 (注意：這些事件鈎點中也可能有其他程式碼。 只要確保你也加入序言。)

   `Hubs.onLoad = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

   `Hubs.onPageChange = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

1. 建立並定義函式，在表單CTA提交時將資料推送至Bizible。 這會進入 [!UICONTROL Custom Code>Javascript] 區段。 (注意：此函式只需要Uberflip提供的ctaData參數，但若使用者想要自訂其程式碼以傳遞此資料，您可以包含其他參數ctaId和ctaName。)

   `function bizibleFormCode(ctaId, ctaData, ctaName) {`
   `var email = ctaData["email"];`
   `if(email){`
   `Bizible.Push('User', {`
   `eMail: email, // required`
   `}); }`

   `}`

1. 提交表單CTA時，請確定您的 [!DNL Marketo Measure] 函式會依下方執行。 這是在 [!UICONTROL Custom Code>JS] 區段。 (注意：Hubs.onCtaFormSubmitSuccess Javascript事件連結中可能有其他程式碼，只要確定您也包含此函式呼叫即可。)

   `Hubs.onCtaFormSubmitSuccess = function (ctaId, ctaData, ctaName) {`
   `bizibleFormCode(ctaId, ctaData, ctaName);`\
   `}`
