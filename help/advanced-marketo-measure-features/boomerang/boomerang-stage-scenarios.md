---
unique-page-id: 18874692
description: 自美朗階段情景 —  [!DNL Marketo Measure]  — 產品檔案
title: 波梅朗階段情景
exl-id: 150db070-eef5-4741-845c-775ab4034ead
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 0%

---

# 波梅朗階段情景 {#boomerang-stage-scenarios}

以下是Boomerang Stage案例的一些範例，以了解如何 [!DNL Marketo Measure] 會在每種情況下建立接觸點。

## 單一銷售機會方案 {#single-lead-scenarios}

**方案1:銷售機會的標準回歸接觸點**

這是最簡單的「自食其果」情景。 頂線（標示為Lead 1）代表個別Lead的歷程，以及其接觸點在Lead記錄中的顯示方式。 底線（標籤為Opportunity）顯示Lead的接觸點如何轉化到Opportunity。 接觸點的進展將以時間順序的發生方式（從左到右）進行說明。

在此案例中，客戶已選擇 **MQL** 和 **SQL** 用波美蘭號追蹤的階段。 每個Boomerang接觸點位置都將標籤有其發生的階段和編號(MQL-01、SQL-01、MQL-02)。 等)。 該階段的最後一個回飛接觸點在接觸點位置也會有「（最後）」。

然後，Lead 1將轉換為具有Opportunity的Contact，該Opportunity被視為OC接觸。

![](assets/1-1.png)

**方案2:Boomerang銷售機會接觸點和自訂階段**

在此案例中，客戶選擇只追蹤 **SQL階段** 自食其果接觸點。 仍在跟蹤MQL和SAL階段，但使用 [!DNL Marketo Measure] 自訂舞台功能。

![](assets/2-1.png)

請注意，MQL接觸點位置未標示數字。 這是因為未選擇使用Boomerang接觸點來追蹤。 為包含在自訂模型中的階段建立接觸點時，但不會使用Boomerang追蹤， [!DNL Marketo Measure] 會從那個階段開始。

在SAL階段， [!DNL Marketo Measure] 會忽略此階段的前兩次出現。 [!DNL Marketo Measure] 僅建立 _最近_ 值。 在上例中，這會在OC接觸點之前發生。

SQL階段正在使用Boomerang接觸點進行跟蹤，並且已建立三個接觸點並相應地標籤。

然後，Lead 1將轉換為具有Opportunity的Contact，該Opportunity被視為OC接觸。

**方案3:當Lead未到達/跳過階段**

此方案使用與方案2相同的條件。 客戶僅選擇使用自動調整接觸點跟蹤SQL階段。 仍在跟蹤MQL和SAL，但使用 [!DNL Marketo Measure] 自訂舞台功能。

![](assets/3.png)

在此情況下，銷售機會從不實際轉變為SAL階段。 它在到達SAL階段之前轉換為Contact，實際上是「跳過」SAL階段。 在這種情況下， [!DNL Marketo Measure] 將假定SAL與OC接觸點一起發生，並且SAL和OC位置將出現在同一接觸點上。

然後，Lead 1將轉換為具有Opportunity的Contact，該Opportunity被視為OC接觸。

## 具有多個銷售機會的方案 {#scenarios-with-multiple-leads}

以下情形是Boomerang Stages可能變得更複雜的情形，因為我們正在研究多個Lead如何影響Opportunity歷程。

頂線（標示為Lead 1，藍色）代表個別Lead的歷程，以及其接觸點在Lead記錄上的顯示方式。 Lead 2（粉紅色）和Lead 3（橙色）也是如此。 底線（標籤為Opportunity）顯示了這兩個Lead的接觸點如何轉化到Opportunity。 接觸點的進展將以時間順序的發生方式（從左到右）進行說明。

**方案1:[!UICONTROL Three Leads with Opportunity]**

在此案例中，客戶已選擇追蹤 **MQL** 和 **SAL階段** 自食其果接觸點。 SQL階段正由標準自定義階段跟蹤。

![](assets/4.png)

「機會」上的FT和LC接觸點將來自Lead 1（藍色），因為它們發生在Lead 2的FT和LC之前（粉紅色）。 Lead 2的LC接觸點將顯示為Opportunity上的「表單」接觸點。

Lead 2的MQL-01（最後一個）將成為Opportunity的第一個MQL。 Lead 1的MQL-01不會作為Opportunity上的接觸點顯示，因為Lead 2的MQL是先發生的。 但是，銷售機會上將出現Lead 1的MQL-02和MQL-03。

請注意，SQL階段是使用自訂階段來追蹤，而非回歸階段。 儘管Lead 1和Lead 2之間有三次出現SQL階段，但只有最後一次SQL出現將作為Opportunity上的接觸點。

來自Lead 1的SAL-01（最後一個）接觸點作為Opportunity的接觸點被傳遞。 然後，Lead 1將轉換為具有Opportunity的Contact，該Opportunity被視為OC接觸。 將建立Lead 2的SAL-01（最後一個）接觸點作為接觸點，因為此階段轉變已發生 _after_ OC接觸。

Lead 3的FT、LC和MQL、SQL、SAL接觸點（橙色）均發生在Opportunity上的OC接觸點之後。 這些接觸點將包含在「機會」中，但被視為「中間接觸」。

當Lead 2和3轉換為Contacts時， [!DNL Marketo Measure] 不會建立另一個OC接觸點，因為只能有一個機會建立階段。

**方案2 -[!UICONTROL Three Leads with Opportunity]**

在此案例中，客戶已選擇追蹤 **MQL**, **SQL**，和 **薩爾** 與自飛鏢接觸點分階段。

從FT到SAL-01（最後）,Lead 1的所有接觸點都將包含在銷售機會中。 Lead 2的LC接觸點將作為Opportunity上LC和MQL-01接觸點之間的表單接觸點。

![](assets/5.png)

Lead 2的MQL-01（最後一個）最終成為Opportunity上的MQL-04（最後一個）接觸點。 因為此情形是在一個Opportunity中查看多個Lead的歷程，因此當Lead的接觸點被翻譯為Opportunity上的接觸點時，其定位和編號可能會改變。 同樣地，Lead 2中的SQL-01(Last)將變成Opp上的SQL-04(Last)。 Lead 2的SAL-01(Last)也成為Opportunity的SAL-02(Last)。

另外，請注意，Opportunity中只包含2個SAL接觸點。 [!DNL Marketo Measure] 不會嘗試強制/建立階段轉變的接觸點（如果尚未實際發生）。

Lead 3的接觸點歷程就在OC接觸發生之前開始，但在Lead 1和Lead 2的FT和LC接觸很久之後。 在這種情況下，Lead 3的FT和LC將作為Opportunity上的Form接觸點顯示。 然後，Lead 1將轉換為具有Opportunity的Contact，該Opportunity被視為OC接觸。

Lead 3的MQL、SQL和SAL接觸在OC接觸後同時發生。 由於這些接觸點是在OC接觸點之後發生的，因此此接觸點將顯示為Opportunity的表單/中間接觸，而不是Boomerang階段轉變。

**案例2a — 在網路造訪Boomerang接觸點**

在此案例中，客戶已選擇追蹤 **MQL**, **SQL**，和 **薩爾** 與自飛鏢接觸點分階段。 此情境幾乎與上述情境相同，但有一些例外。

![](assets/6.png)

從FT到SAL-01（最後）,Lead 1的所有接觸點都將包含在銷售機會中。 Lead 2的LC接觸點將作為Opportunity上LC和MQL-01接觸點之間的表單接觸點。

Lead 2的MQL-01（最後一個）（Web訪問）不會作為Opp上的接觸點建立。 這是因為此接觸點是在SQL階段最後一次出現之後進行的Web訪問，不有助於推動Opportunity前進。

銷售機會1的階段更改為SAL，然後轉換為Contact with a Opportunity;在這種情況下，SAL-01（最後）和OC位置將合併到同一接觸點中。

Lead 3的FT、LC接觸將建立為Opp上的「表單」接觸點。 在OC接觸後，僅會建立表單填入動作作為接觸點。 因此，將不會建立「銷售機會2」的SQL-01（最後）和SAL-01（最後）階段轉變作為接觸點，因為這些接觸點是Web訪問。

Lead 3的MQL、SQL、SAL接觸將作為接觸點包括在內，因為這是表單填充操作。

**案例3 — 回歸歸歸因加權**

在此案例中，客戶已選擇追蹤 **MQL**, **SQL**，和 **薩爾** 與自飛鏢接觸點分階段。

![](assets/7.png)

「機會」上的FT和LC接觸點將來自Lead 1（藍色），因為它們發生在Lead 2的FT和LC之前（粉紅色）。 Lead 2的LC接觸點將顯示為Opportunity上的「表單」接觸點。

Lead 2的MQL-01（最後一個）將成為Opportunity的第一個MQL。 Lead 1的MQL-01不會作為Opportunity上的接觸點顯示，因為Lead 2的MQL是先發生的。

Lead 2中的SQL-01(Last)將在Opportunity上成為SQL-01。 銷售機會1上的SQL-01不會顯示為銷售機會上的接觸點，因為銷售機會2上的SQL-01是先發生的。

請注意，在MQL和SQL之間的Lead 1回歸了幾次，最後到達SAL階段。 SQL-01、MQL-02、SQL-02、MQL-03、SQL-03 _不會_ 可作為機會的接觸點，因為這些階段轉變並不有助於在歷程中推動機會前進。

來自Lead 1的SAL-01（最後一個）接觸點將是Opp上要包含的下一個接觸點。 然後銷售機會1轉換為具有銷售機會的聯繫人，建立OC接觸點。

Lead 3的FT和LC，以及MQL、SQL和SAL接觸點，將以表單形式顯示，接觸Opportunity。

銷售機會2的SQL-01（最後一個）接觸點將不包括在Opp上作為接觸點，因為它發生在OC接觸點之後。 此外，Lead 2的SQL階段轉變已發生 _SAL階段最終轉變後_，並且無助於推動機會歷程向前推進。

## 機會方案 {#opportunity-scenarios}

**情節1 — 與Opportunity和Boomerang跟蹤的聯繫人**

在此案例中，客戶已選擇追蹤 **演示和協商階段轉換** 在 **連絡人**. 每個自飛舞台最多可接收兩個接觸點。 Contact上的階段轉變與Lead上的階段轉變之間的區別在於， Contact的階段轉變可以顯示為Opportunity上的Boomerang接觸點 _after_ OC接觸點。 對於在銷售機會上發生的階段轉變則並非如此，因為這些轉變會顯示為表單接觸點。

![](assets/8.png)

在此示例中， Contact 1的Demo和Negotiation階段轉變包括在Opportunity上的Demo-01和Negotiation-01接觸點中。 聯繫人2的演示階段轉變發生 _after_ 聯繫1，並以Demo-02（最後一個）接觸點的形式顯示在Opportunity上。

請注意，沒有第二個轉變到「洽談」階段；機會立即從Demo-02（最後一個）轉移到Close Won。 在這種情況下， [!DNL Marketo Measure] 將包含與「已結束原因」接觸點的「洽談」轉變。
