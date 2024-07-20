---
unique-page-id: 18874648
description: Google Analytics轉換與Buyer Touchpoint之間的差異 —  [!DNL Marketo Measure]
title: Google Analytics轉換與Buyer Touchpoint之間的差異
exl-id: d09d963c-3207-467c-852a-d1edd49511fa
feature: Touchpoints
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 1%

---

# Google Analytics轉換與Buyer Touchpoint之間的差異 {#difference-between-a-google-analytics-conversion-and-a-buyer-touchpoint}

瞭解[!DNL Google Analytics (GA)]目標是什麼，以及它與Buyer Touchpoint有何不同。

**Google Analytics的轉換次數是多少？**

[!UICONTROL Google Analytics]轉換是由行銷人員或Web開發人員在特定網站上編碼「目標」完成的方式所決定。 根據Google的說法，目標可視為「進行購買（針對電子商務網站）、完成遊戲層級（針對行動遊戲應用程式）或提交聯絡資訊表單（針對行銷或潛在客戶產生網站）」。 大多數時候，行銷人員會將目標/轉換視為填寫資訊表單的人。

但是，無法以編碼方式管理特定行為。 而是有網頁開發人員可以設定的目標型別。 以下是其中一些範例：

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td><strong>目標型別</strong></td> 
   <td><p><strong>說明</strong></p></td> 
   <td><strong>範例</strong></td> 
  </tr> 
  <tr> 
   <td><p>目的地</p></td> 
   <td>特定位置載入</td> 
   <td><em>感謝您註冊！</em>網頁或應用程式畫面</td> 
  </tr> 
  <tr> 
   <td>持續時間</td> 
   <td>持續特定時間或更長的工作階段</td> 
   <td>在支援網站上逗留10分鐘或更長時間</td> 
  </tr> 
  <tr> 
   <td>每個工作階段的頁面/Screens</td> 
   <td>使用者檢視特定數量的頁面或畫面</td> 
   <td>已載入5個頁面或熒幕</td> 
  </tr> 
  <tr> 
   <td>事件</td> 
   <td>定義為事件的動作會觸發</td> 
   <td>社交推薦、視訊播放、廣告點選</td> 
  </tr> 
 </tbody> 
</table>

大部分行銷人員將其轉換設定為「目的地目標」，這表示他們通常會在表單後面建立感謝頁面，以視為正式轉換。

這表示Google將「感謝您」頁面檢視視為轉換。 從Google Analytics的觀點來看，這是大部分行銷人員都接受的實現。

不過，購買者接觸點的作用不同。

**購買者接觸點有何不同？**

[!DNL Marketo Measure] JavaScript會追蹤特定網站所有形式的工作階段資料與表單提交。 不需要從[!DNL Marketo Measure]觀點來編寫目標的程式碼。 此程式是自動的。 針對表單提交，每次匿名使用者填寫特定表單的資訊欄位並按一下表單提交按鈕時，[!DNL Marketo Measure]都會報告表單完成。 [!DNL Marketo Measure]不需要感謝頁面來記錄表單提交。

[!DNL Marketo Measure]會在下列情況建立表單接觸點：

* 與這些轉換相關聯的銷售機會/聯絡人會出現在您的CRM中。
* [!DNL Marketo Measure] JS出現在包含表單的網頁上。
* 表單會在30分鐘工作階段中提交。

在下列情況下，[!DNL Marketo Measure]會忽略目的地Google Analytics轉換：

* 機器人在網站上提交表單（這些機器人通常無法將其變成客戶的CRM）。
* 使用者在首次提交表單後提交更多表單。 [!DNL Marketo Measure]只會推送該工作階段的第一次轉換。
* 使用者按多次表單提交。 [!DNL Marketo Measure]將只考慮第一個表單提交。
* 使用者多次重新載入感謝頁面。
* 使用者正在使用任何廣告封鎖工具。

如您所見，GA和[!DNL Marketo Measure]認為的轉換之間有根本的差異。 因此，轉換次數與形式接觸點數量可能會有所不同。
