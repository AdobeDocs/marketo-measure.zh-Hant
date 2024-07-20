---
unique-page-id: 18874745
description: AJAX表單處理 —  [!DNL Marketo Measure]
title: AJAX表單處理
exl-id: 042e42ff-d8d9-4380-b878-aba4934bc4a0
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 0%

---

# AJAX表單處理 {#ajax-form-handling}

若要手動將客戶轉換報告給[!DNL Marketo Measure]，您可以使用一個簡單的API。 如果您的網站上具有追蹤程式碼，這兩個JavaScript API都可在您的網站上自動使用。 無需執行任何特殊操作即可存取。

## 案例1 — 具有AJAX提交的HTML表單 {#scenario-html-form-with-an-ajax-submit}

使用包含AJAX （或其他機制）的表單將轉換日期從使用者端提交至我們的伺服器時，[!DNL Marketo Measure]可能不知道客戶透過我們監控的任何標準路徑進行的轉換。 在這個案例中，我們可以使用簡單的API （如下所示）。

如果您處理自己的表單提交，可以明確從JavaScript呼叫[!DNL Marketo Measure]。 [!DNL Marketo Measure]會從表單收集所有相關資訊，並以非同步方式張貼至我們的伺服器。

**以下是使用JQuery的程式碼範例（假設表單上的ID為「formId」）：**

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// Give Marketo Measure the JQuery Selector for the form and we'll collect the data automatically.  
Bizible.Push('Form',$('#*formId*'));
```

**以下是未使用JQuery的程式碼範例（假設表單上的ID為「formId」）：**

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// Give Marketo Measure the Form ID and we'll collect the data automatically.
Bizible.Push('Form','MyFormID');
```

## 案例2 — 以非HTML表單收集的潛在客戶資訊 {#scenario-lead-information-collected-in-a-non-html-form}

如果轉換的潛在客戶的資訊是使用JavaScript或沒有html表單的簡單文字欄位收集而來，此解決方案即適合您。 以下共用是此情境使用的API：

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// If your site is using Ajax, or you are running a secure site, it is best to send us the data directly.  
Bizible.Push('User', {
eMail: 'user@gmail.com' // required  
});  
```

在此程式碼中，[!UICONTROL email]欄位為必填。 [!DNL Marketo Measure]以非同步方式將此資料張貼至我們的伺服器。

## 案例3 — 從感謝頁面報告使用者資訊 {#scenario-report-user-information-from-the-thank-you-page}

有時，在提交表單後，從感謝頁面將潛在客戶資訊報告給[!DNL Marketo Measure]會更方便。 報告此資訊最簡單的方法是將隱藏元素新增至包含表單提交資訊的頁面，當「感謝您」頁面載入時，[!DNL Bizible.js]會讀取此資訊。

**例如：**

```html
<div id="bizible.reportUser" style="display:none"  
data-email="user@gmail.com">  
```

隱藏元素是div、指令碼或任何其他標籤型別並不重要。 [!DNL Marketo Measure]會尋找id=&quot;bizible.reportUser&quot;以讀取資訊。
