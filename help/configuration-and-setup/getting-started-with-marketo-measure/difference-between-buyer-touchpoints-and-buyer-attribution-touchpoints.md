---
unique-page-id: 18874646
description: 購買者接觸點和購買者歸因接觸點之間的差異 —  [!DNL Marketo Measure]
title: 購買者接觸點和購買者歸因接觸點之間的差異
exl-id: 19109271-7b59-44c0-b1ff-e3b0bba9f5ce
feature: Touchpoints
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 0%

---

# 購買者接觸點和購買者歸因接觸點之間的差異 {#difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints}

瞭解定義購買者接觸點(BT)和購買者歸因接觸點(BAT)的定義，以及兩者之間的差異，並回答常見問題。

「購買者接觸點」和「購買者歸因接觸點」的主要區別在於它們之間的關係 [!DNL Salesforce] 物件。 BT與Lead、Contact和Case物件有關，但與Opportunity物件無關。 這表示永遠沒有與購買者接觸點相關的收入。

雖然購買者歸因接觸點物件與聯絡人、帳戶和商機物件相關，但與Lead物件無關；購買者歸因接觸點不會與銷售機會繫結。 BAT物件是您看到與特定行銷互動相關聯之收入的位置。

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
     <li>與Lead、Contact和Case物件相關</li> 
     <li>與機會物件無關</li> 
     <li>收入未與購買者接觸點建立關聯</li> 
    </ul></td> 
   <td> 
    <ul> 
     <li>與連絡人、帳戶和機會物件相關</li> 
     <li>與Lead物件無關</li> 
     <li>由於「購買者歸因」接觸點與「商機」相關聯，因此所有BAT都有與其相關聯的收入</li> 
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## 常見問題集 {#faq}

**購買者接觸點何時會成為購買者歸因接觸點？**

一旦此BT與具有相關Opportunity的Contact關聯，BT就會變成BAT。 要瞭解的一件重要事情是，特定行銷互動可以是BT和BAT。

**採購員接觸點是否有「機會建立」(OC)的接觸點位置？**

購買者接觸點的接觸點位置只有首次接觸(FT)、銷售機會建立(LC)或表單提交（中介接觸點）。 由於BT與商機無關，因此BT不可能擁有建立或關閉商機的接觸點位置。

**如何使用購買者接觸點資料？**

客戶通常會使用購買者接觸點資料來瞭解漏斗頂端和漏斗中間參與度。 含義 [!DNL Marketo Measure] 使用者可知道哪些人正在提交表單、哪些人正在檢視其網站、哪些部落格成效良好、哪些AdWords廣告在推動哪些人可轉化，等等。 購買者接觸點資料對於瞭解潛在客戶與聯絡人的參與度非常有幫助。

**Salesforce中的購買者接觸點看起來像什麼？**

以下是BT的熒幕擷圖 [!DNL Salesforce]：

![](assets/1.png)

**Salesforce中的購買者歸因接觸點看起來像什麼？**

以下是中的BAT熒幕擷圖 [!DNL Salesforce]：

![](assets/2.png)
