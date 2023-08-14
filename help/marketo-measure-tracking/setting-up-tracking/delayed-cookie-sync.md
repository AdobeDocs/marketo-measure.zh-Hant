---
unique-page-id: 30082018
description: 延遲的Cookie同步 —  [!DNL Marketo Measure]  — 產品檔案
title: 延遲的Cookie同步
exl-id: 394053ed-5642-48e4-b83c-c483a58ebbd7
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# 延遲的Cookie同步 {#delayed-cookie-sync}

此預設的修改 [!DNL Marketo Measure] Javascript可提供 [!DNL bizible.js] API支援，因此您可以設定JS以暫時儲存訪客的使用者活動，但不會將資訊傳送至 [!DNL Marketo Measure] 伺服器，直到使用者同意為止。

## 操作說明 {#how-to}

取代預設值 [!DNL bizible.js] 包含以下專案的指令碼標籤：

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-consent-button-id="ConsentButtonId"></script>`

data-consent-button-id=&quot;ConsentButtonId&quot;屬性會告知 [!DNL bizible.js] ，以便在按一下具有該id的HTML元素前不會傳送分析資料。

或者，客戶可設定 [!UICONTROL data-consent-button-id] 不存在（例如「foobar」），並使用以下API來告知 [!DNL bizible.js] 使用者已同意：

`window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`
`Bizible.Push("Consent", true });`

>[!NOTE]
>
>使用者同意會儲存至Cookie中，這表示一旦使用者同意，就不需要在任何後續頁面上執行此呼叫。

## 限制 {#limitation}

因為 [!DNL bizible.js] 暫時將未傳送的Web活動儲存在客戶的第一方Cookie中，且第一方Cookie的大小有限，在任何指定時間只能儲存三個未傳送的請求。

如果已經有三個擱置中的請求，則會忽略任何後續活動；這是為了保留第一個頁面檢視，其中包含重要的反向連結資訊。
