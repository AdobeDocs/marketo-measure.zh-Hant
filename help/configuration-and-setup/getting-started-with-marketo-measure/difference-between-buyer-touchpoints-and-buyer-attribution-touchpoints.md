---
unique-page-id: 18874646
description: 購買者接觸點與購買者歸因接觸點之間的差異 —  [!DNL Marketo Measure]  — 產品檔案
title: 購買者接觸點與購買者歸因接觸點之間的差異
exl-id: 19109271-7b59-44c0-b1ff-e3b0bba9f5ce
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 0%

---

# 購買者接觸點與購買者歸因接觸點之間的差異 {#difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints}

了解如何定義購買者接觸點(BT)和購買者歸因接觸點(BAT)、兩者之間的差異，並回答常見問題。

「購買者接觸點」和「購買者歸因接觸點」之間的主要區別，是它們與 [!DNL Salesforce] 對象。 BT與Lead 、 Contact和Case對象相關，但與Opportunity對象無關。 這表示不會有與購買者接觸點相關的收入。

而購買者歸因接觸點對象與聯繫人、帳戶和機會對象相關，而不是銷售機會對象。 這表示永遠不會有與銷售機會系結的購買者歸因接觸點。 BAT物件可讓您看到與特定行銷互動相關的收入。

BT與BAT的差異：

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td>購買者接觸點(BT)</td> 
   <td>購買者歸因接觸點(BAT)</td> 
  </tr> 
  <tr> 
   <td> 
    <ul> 
     <li>與銷售機會、聯繫人和案例對象相關</li> 
     <li>與Opportunity對象不相關</li> 
     <li>收入未與購買者接觸點相關聯</li> 
    </ul></td> 
   <td> 
    <ul> 
     <li>與聯繫人、帳戶和機會對象相關</li> 
     <li>與銷售機會對象不相關</li> 
     <li>由於買方歸因接觸點與機會相關聯，因此所有BAT都有與它們相關聯的收入</li> 
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## 常見問題集 {#faq}

**購買者接觸點何時會變成購買者歸因接觸點？**

一旦此BT與具有關聯機會的聯繫人關聯，BT就會成為BAT。 需要了解的一件非常重要的事情是，某個特定的行銷互動可以是BT和BAT。

**購買者接觸點是否可以具有建立機會(OC)的接觸點位置？**

購買者接觸點的接觸點位置僅為「首次接觸」(FT)、「銷售機會建立」(LC)或「表單提交」（中間接觸點）。 由於BT與Opportunity無關，因此BT不可能具有Opportunity Creation或Colled的Touchpoint Position。

**如何運用購買者接觸點資料？**

通常客戶會利用購買者接觸點資料來了解漏斗頂端和漏斗中間參與。 意義 [!DNL Marketo Measure] 使用者知道誰提交表單、誰正在檢視其網站、哪些部落格貼文表現良好、AdWords廣告帶來哪些轉換等。 購買者接觸點資料非常有助於了解您的銷售機會和聯絡人的參與度。

**購買者接觸點在Salesforce中看起來是什麼樣子？**

這是BT的螢幕截圖 [!DNL Salesforce]:

![](assets/1.png)

**購買者歸因接觸點在Salesforce中會是什麼樣子？**

這是BAT的螢幕截圖 [!DNL Salesforce]:

![](assets/2.png)
