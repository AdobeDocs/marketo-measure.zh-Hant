---
unique-page-id: 18874646
description: 購買者接觸點和購買者歸因接觸點之間的差異 —  [!DNL Marketo Measure]
title: 購買者接觸點和購買者歸因接觸點之間的差異
exl-id: 19109271-7b59-44c0-b1ff-e3b0bba9f5ce
feature: Touchpoints
source-git-commit: bdc32fdfe24d57fd7770654f1238896c7b59acf6
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 0%

---

# 購買者接觸點和購買者歸因接觸點之間的差異 {#difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints}

瞭解什麼會定義Buyer Touchpoint (BT)和Buyer Attribution Touchpoint (BAT)，以及兩者之間的差異，並回答常見問題。

「購買者接觸點」和「購買者歸因接觸點」的主要區別在於它們與[!DNL Salesforce]物件的關係。 BT與Lead、Contact和Case物件有關，但與Opportunity物件無關。 這表示永遠沒有與購買者接觸點相關的收入。

雖然Buyer Attribution Touchpoint物件與聯絡人、帳戶和機會物件相關，但與Lead物件無關；購買者歸因接觸點不會與銷售機會繫結。 BAT物件是您看到與特定行銷互動相關聯之收入的位置。

BT和BAT之間的差異：

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td>Buyer Touchpoint (BT)</td> 
   <td>Buyer Attribution Touchpoint (BAT)</td> 
  </tr> 
  <tr> 
   <td> 
    <ul> 
     <li>與Lead、Contact和Case物件相關</li> 
     <li>與機會物件無關</li> 
     <li>收入與Buyer Touchpoint沒有關聯</li> 
    </ul></td> 
   <td> 
    <ul> 
     <li>與連絡人、帳戶和機會物件相關</li> 
     <li>與Lead物件無關</li> 
     <li>由於Buyer Attribution Touchpoint與某個商機相關聯，因此所有BAT都有與其關聯的收入</li> 
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## 常見問題集 {#faq}

**Buyer Touchpoint何時會成為Buyer Attribution Touchpoint？**

一旦此BT與具有相關商機的連絡人建立關聯，該BT就會變成BAT。 請務必瞭解一件事，一件特定的行銷互動可以是BT和BAT。

**Buyer Touchpoint是否可擁有機會建立(OC)的接觸點位置？**

Buyer Touchpoint的接觸點位置只有首次接觸(FT)、銷售機會建立(LC)或表單提交（中介接觸點）。 由於BT與商機無關，因此BT不可能有建立或關閉商機的接觸點位置。

**如何使用Buyer Touchpoint資料？**

客戶通常使用Buyer Touchpoint資料來瞭解漏斗頂端和漏斗中間參與度。 這表示[!DNL Marketo Measure]使用者知道哪些人正在提交表單、哪些人正在檢視其網站、哪些部落格成效良好、哪些AdWords廣告在推動哪些人能夠轉換等等。 Buyer Touchpoint資料對於瞭解潛在客戶與聯絡人的參與度非常有幫助。

**Buyer Touchpoint在Salesforce中看起來像什麼？**

以下是[!DNL Salesforce]中BT的熒幕擷圖：

![](assets/buyer-touchpoints-and-buyer-attribution-touchpoints-1.png){width="600" zoomable="yes"}

**Buyer Attribution Touchpoint在Salesforce中看起來像什麼？**

以下是[!DNL Salesforce]中BAT的熒幕擷圖：

![](assets/buyer-touchpoints-and-buyer-attribution-touchpoints-2.png){width="600" zoomable="yes"}
