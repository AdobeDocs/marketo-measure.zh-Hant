---
unique-page-id: 18874652
description: '[!DNL Marketo Measure]透過歸因常見問題集檢視 —  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure]透過歸因常見問題集檢視'
exl-id: d20e88f3-3ff8-4381-a4b8-6862798caa74
feature: Attribution
source-git-commit: 48962b999fdd16fe96d18708ec301e64a39bc76e
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 3%

---

# [!DNL Marketo Measure]透過歸因常見問題集檢視 {#marketo-measure-view-through-attribution-faq}

## 透過歸因檢視什麼？ {#what-is-view-through-attribution}

[!DNL Marketo Measure] [!UICONTROL View Through Attribution]功能包括在歸因模型中包含廣告印象的功能。

>[!IMPORTANT]
>
>基於隱私權疑慮，第三方Cookie即將推出。 Google Chrome於2024年第3季度宣佈淘汰第三方Cookie，實際標誌著此追蹤形式的結束。 因此，Adobe淘汰依賴第三方Cookie的Marketo Measure功能；特別是跨網域追蹤和瀏覽歸因，後者使用Google/DoubleClick曝光數Cookie。 Marketo Measure的其他功能將不會受到影響。 第一方Cookie使用量也不受影響。 根據Google排程，上述兩個功能的預計淘汰日期為2024年6月1日。 在此日期之前收集的相關資料仍可供Adobe客戶使用。

## [!UICONTROL View Through Attribution]為何重要？ {#why-is-view-through-attribution-important}

過去，行銷人員很難在歸因分析中說明重新鎖定目標或曝光數廣告。 潛在客戶可能會不時接觸到重新定位的廣告，但他們不太可能在同一個工作階段中實際按一下這些廣告之一并填寫表格。 我們的「透過歸因檢視」解決方案現在能夠追蹤某人是否接觸到曝光廣告。 此接觸點將會附加至個別記錄，並持續進行到潛在客戶成為客戶為止。 有了這些資訊，行銷人員現在就能更深入瞭解重新鎖定目標廣告的效能。

## 設定此專案涉及哪些內容？ {#what-is-involved-in-setting-this-up}

為了讓[!DNL Marketo Measure]開始測量廣告曝光，需要在Doubleclick Campaign Manager中放置曝光標籤。 實施標籤後，曝光數會儲存在記錄中，我們會處理剩餘的部分。 如果您有興趣透過歸因測量檢視，請洽詢成功經理。

## 支援哪些廣告平台？ {#which-ad-platforms-are-supported}

我們目前支援[!DNL Doubleclick]行銷活動管理員。

## 歸因如何計算？ {#how-is-the-attribution-calculated}

我們仔細分析了曝光資料，及其對所有階段和行銷管道轉換的影響。 分佈會因模型而異，如下表所示：

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
   <td><strong>靠中間</strong></td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>20%</td> 
   <td>10%</td> 
   <td>10%</td> 
   <td>自訂</td> 
  </tr> 
 </tbody> 
</table>

## 在[!DNL Salesforce?]中看起來是什麼樣子 {#what-will-this-look-like-in-salesforce}

[!DNL Marketo Measure]將在任何公開至顯示廣告的Lead上建立單一曝光接觸點。 即使使用者第一次造訪您的網站(FT)並填寫表格(LC)，我們仍可對應使用者。 接觸點將包含廣告資訊，例如，廣告促銷活動名稱/ID、廣告ID、廣告內容、網站名稱/ID、版位名稱/ID、行銷管道、地理、反向連結頁面等。

檢視歸因模型取決於使用者端及其資料。
