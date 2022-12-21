---
unique-page-id: 18874745
description: AJAX表單處理 —  [!DNL Marketo Measure]  — 產品檔案
title: AJAX表單處理
exl-id: 042e42ff-d8d9-4380-b878-aba4934bc4a0
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# AJAX表單處理 {#ajax-form-handling}

若要手動將客戶轉換報告至 [!DNL Marketo Measure]，我們提供了一個非常簡單的API供您使用。 如果您的網站上有我們的追蹤程式碼，這兩個Javascript API都會自動開放使用。 不需要做任何特殊的事情來存取。

## 案例1 — 具有AJAX提交的HTML表單 {#scenario-html-form-with-an-ajax-submit}

使用包含AJAX的表單（或其他機制）從用戶端提交轉換日期至我們的伺服器時， [!DNL Marketo Measure] 可能不知道客戶透過我們監控的任何標準路徑進行的轉換。 在此案例中，我們可以運用簡單的API（於下方提供）。

如果您處理自己的表單提交，可明確呼叫 [!DNL Marketo Measure] 從Javascript中。 [!DNL Marketo Measure] 會從表單中收集所有相關資訊，並以非同步方式張貼至我們的伺服器。

**以下是使用JQuery的程式碼範例（假設表單上的ID為「formId」）:**

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// Give Marketo Measure the JQuery Selector for the form and we'll collect the data automatically.  
Bizible.Push('Form',$('#*formId*'));
```

**以下是未使用JQuery的程式碼範例（假設表單上的ID為「formId」）:**

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// Give Marketo Measure the Form ID and we'll collect the data automatically.
Bizible.Push('Form','MyFormID');
```

## 方案2 — 以非HTML表單收集的銷售機會資訊 {#scenario-lead-information-collected-in-a-non-html-form}

如果使用Javascript或沒有html表單的簡單文字欄位來收集轉換銷售機會的資訊，此解決方案將適用於您。 以下共用是要在此案例中使用的API:

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// If your site is using Ajax, or you are running a secure site, it is best to send us the data directly.  
Bizible.Push('User', {
eMail: 'user@gmail.com' // required  
});  
```

在此程式碼中， [!UICONTROL email] 欄位為必填。 [!DNL Marketo Measure] 會將此資料非同步地發佈至我們的伺服器。

## 案例3 — 從感謝頁面回報使用者資訊 {#scenario-report-user-information-from-the-thank-you-page}

在某些情況下，將銷售機會資訊報告給 [!DNL Marketo Measure] 在表單提交後，即可從感謝頁面取得。 報告此資訊最簡單的方式是將隱藏元素新增至含有表單提交資訊的頁面， [!DNL Bizible.js] 會在「感謝」頁面載入時閱讀此資訊。

**例如：**

```html
<div id="bizible.reportUser" style="display:none"  
data-email="user@gmail.com">  
```

隱藏的元素是div、指令碼或任何其他標籤類型均不重要。 [!DNL Marketo Measure] 尋找id=&quot;bizible.reportUser&quot;以讀取資訊。
