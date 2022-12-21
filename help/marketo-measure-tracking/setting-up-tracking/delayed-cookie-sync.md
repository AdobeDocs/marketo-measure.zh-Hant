---
unique-page-id: 30082018
description: 延遲的Cookie同步 —  [!DNL Marketo Measure]  — 產品檔案
title: 延遲的Cookie同步
exl-id: 394053ed-5642-48e4-b83c-c483a58ebbd7
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# 延遲的Cookie同步 {#delayed-cookie-sync}

此修改為預設 [!DNL Marketo Measure] Javascript提供 [!DNL bizible.js] API支援，因此您可以設定JS來暫時儲存訪客的使用者活動，但不會將資訊傳送至 [!DNL Marketo Measure] 伺服器，直到使用者同意為止。

## 作法 {#how-to}

取代預設值 [!DNL bizible.js] 指令碼標籤中包含下列項目：

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-consent-button-id="ConsentButtonId"></script>`

data-consent-button-id=&quot;ConsentButtonId&quot;屬性會告訴 [!DNL bizible.js] 若要在點選具有該id的HTML元素前，不傳送分析資料。

或者，客戶可以設定 [!UICONTROL data-consent-button-id] 不存在（例如&quot;foobar&quot;），並使用下列API來指示 [!DNL bizible.js] 用戶已同意：

`window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`
`Bizible.Push("Consent", true });`

>[!NOTE]
>
>使用者同意會儲存至Cookie，這表示使用者一旦同意，就不需要在任何後續頁面上執行此呼叫。

## 限制 {#limitation}

因為 [!DNL bizible.js] 會暫時將未傳送的Web活動儲存在客戶的第一方Cookie中，而且第一方Cookie的大小有限，則在任何指定時間都只能儲存三個未傳送的請求。

如果已有三個待處理請求，則會忽略任何後續活動；這是為了保留包含有價值反向連結資訊的第一個頁面檢視。
