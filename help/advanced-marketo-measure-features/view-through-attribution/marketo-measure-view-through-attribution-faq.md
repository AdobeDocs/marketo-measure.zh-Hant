---
unique-page-id: 18874652
description: '"[!DNL Marketo Measure] 檢視歸因常見問題集 —  [!DNL Marketo Measure]  — 產品檔案」'
title: '"[!DNL Marketo Measure] 檢視歸因常見問題集」'
exl-id: d20e88f3-3ff8-4381-a4b8-6862798caa74
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 9%

---

# [!DNL Marketo Measure] 檢視歸因常見問題集 {#marketo-measure-view-through-attribution-faq}

## 透過歸因檢視什麼？ {#what-is-view-through-attribution}

此 [!DNL Marketo Measure] 透過歸因檢視功能，可在歸因模型中包含廣告曝光次數。

## 透過歸因檢視為何重要？ {#why-is-view-through-attribution-important}

過去，在歸因分析中，行銷人員很難考慮重新目標定位或曝光廣告。 潛在客戶可能會陸續接觸到重新定位的廣告，但他們不太可能實際點選其中一個廣告，並在同一工作階段中填寫表單。 我們的「透過歸因檢視」解決方案現在能追蹤某人是否曾接觸到曝光廣告。 此接觸點將附加至個別記錄，並持續到潛在客戶成為客戶為止。 透過這些資訊，行銷人員現在將能更深入了解其重新目標定位廣告的效能。

## 設定此設定時有何參與？ {#what-is-involved-in-setting-this-up}

為了 [!DNL Marketo Measure] 若要開始測量廣告曝光次數，需在Doubleclick促銷活動管理員中放置曝光標籤。 實作標籤後，曝光數會儲存在記錄中，我們會處理其餘的。 如果您想透過歸因測量檢視，請洽詢您的成功經理。

## 支援哪些廣告平台？ {#which-ad-platforms-are-supported}

我們目前支援Doubleclick促銷活動管理員。

## 如何計算歸因？ {#how-is-the-attribution-calculated}

我們仔細分析曝光資料及其對所有階段和行銷管道之轉換的影響。 分佈會依模型而異，如下表所示：

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><br></th> 
   <th>首次接觸</th> 
   <th>銷售機會建立</th> 
   <th>U形</th> 
   <th>W形</th> 
   <th>完整路徑</th> 
   <th>自訂模型</th> 
  </tr> 
  <tr> 
   <td><strong>曝光數</strong></td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>10%</td> 
   <td>10%</td> 
   <td>10%</td> 
   <td>自訂</td> 
  </tr> 
  <tr> 
   <td><strong>FT</strong></td> 
   <td>100%</td> 
   <td>0%</td> 
   <td>35%</td> 
   <td>26.6%</td> 
   <td>20%</td> 
   <td>自訂</td> 
  </tr> 
  <tr> 
   <td><strong>LC</strong></td> 
   <td>0%</td> 
   <td>100%</td> 
   <td>35%</td> 
   <td>26.6%</td> 
   <td>20%</td> 
   <td>自訂</td> 
  </tr> 
  <tr> 
   <td><strong>OC</strong></td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>26.6%</td> 
   <td>20%</td> 
   <td>自訂</td> 
  </tr> 
  <tr> 
   <td><strong>已關閉</strong></td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>20%</td> 
   <td>自訂</td> 
  </tr> 
  <tr> 
   <td><strong>中間</strong></td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>20%</td> 
   <td>10%</td> 
   <td>10%</td> 
   <td>自訂</td> 
  </tr> 
 </tbody> 
</table>

## 在Salesforce中會是什麼樣子？ {#what-will-this-look-like-in-salesforce}

[!DNL Marketo Measure] 會在顯示廣告公開的任何Lead上建立單一曝光接觸點。 即使使用者第一次來到您的網站(FT)並填寫表格(LC)，我們仍能對應該使用者。 接觸點將包含廣告資訊，例如廣告促銷活動名稱/ID、廣告ID、廣告內容、網站名稱/ID、版位名稱/ID、行銷管道、地理、反向連結頁面等。

閱覽歸因模型取決於用戶端及其資料。
