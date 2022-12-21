---
unique-page-id: 18874648
description: Google Analytics轉換與購買者接觸點之間的差異 —  [!DNL Marketo Measure]  — 產品檔案
title: Google Analytics轉換與購買者接觸點之間的差異
exl-id: d09d963c-3207-467c-852a-d1edd49511fa
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---

# Google Analytics轉換與購買者接觸點之間的差異 {#difference-between-a-google-analytics-conversion-and-a-buyer-touchpoint}

了解 [!DNL Google Analytics (GA)] 目標是，以及它如何區分購買者接觸點。

**什麼是Google Analytics轉換？**

[!UICONTROL Google Analytics] 轉換完全取決於行銷人員或網頁開發人員對特定網站上「目標」完成的編碼方式。 根據Google的說法，目標可以被視為「進行購買（針對電子商務網站）、完成遊戲級別（針對移動遊戲應用）或提交聯繫資訊表單（針對營銷或潛在客戶生成網站）」。 大部分時候，行銷人員會將目標/轉換視為填寫資訊性表單的人。

但是，無法對目標進行編碼以管理非常具體的行為。 而是有Web開發人員可設定的目標類型。 以下是其中一些範例：

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td><strong>目標類型</strong></td> 
   <td><p><strong>說明</strong></p></td> 
   <td><strong>範例</strong></td> 
  </tr> 
  <tr> 
   <td><p>目的地</p></td> 
   <td>特定位置載入</td> 
   <td><em>感謝您註冊！</em> 網頁或應用程式畫面</td> 
  </tr> 
  <tr> 
   <td>持續時間</td> 
   <td>持續特定時間或更長的工作階段</td> 
   <td>在支援網站上逗留10分鐘或更久</td> 
  </tr> 
  <tr> 
   <td>每個工作階段的頁面/畫面</td> 
   <td>使用者檢視特定數量的頁面或畫面</td> 
   <td>已載入5頁或螢幕</td> 
  </tr> 
  <tr> 
   <td>Event</td> 
   <td>定義為「事件」的動作會觸發</td> 
   <td>社交建議、視訊播放、廣告點按</td> 
  </tr> 
 </tbody> 
</table>

大部分的行銷人員會將其轉換設為「目標」，這表示他們通常會在表單後建立感謝頁面，將其視為正式的轉換。

這表示，Google會將感謝頁面檢視視為轉換。 從Google Analytics的角度來看，這是大多數行銷人員都不介意的認識。

不過，「購買者接觸點」的運作方式非常不同。

**購買者接觸點有何不同？**

[!DNL Marketo Measure] JavaScript會追蹤工作階段資料，以及特定網站上所有表單的提交。 不需要從 [!DNL Marketo Measure] 立場。 此程式是自動的。 對於表單提交， [!DNL Marketo Measure] 每次匿名用戶填寫特定表單的資訊欄位，並按一下表單提交按鈕時，都會報告表單完成情況。 [!DNL Marketo Measure] 不需要感謝頁面即可記錄表單提交。

[!DNL Marketo Measure] 會在下列情況下建立表單接觸點：

* 與這些轉換相關聯的銷售機會/聯絡人會出現在您的CRM中。
* 此 [!DNL Marketo Measure] JS存在於包含表單的網頁上。
* 在30分鐘內提交表單。

[!DNL Marketo Measure] 會忽略目標Google Analytics轉換，但發生下列情況時：

* 機器人會在網站上提交表單（這些機器人通常無法放入用戶端的CRM）。
* 使用者在首次提交表單後提交更多表單。 [!DNL Marketo Measure] 只會推送該工作階段的第一個轉換。
* 使用者點按表單提交多次。 [!DNL Marketo Measure] 只會考慮第一次提交表單。
* 使用者重新載入感謝頁面多次。
* 使用者使用任何廣告封鎖工具。

如您所見，GA和 [!DNL Marketo Measure] 將轉換視為。 因此，轉換次數和表單接觸點數目很可能會有所不同。
