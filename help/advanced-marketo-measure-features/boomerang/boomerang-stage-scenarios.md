---
unique-page-id: 18874692
description: 迴音廊階段案例 —  [!DNL Marketo Measure]  — 產品檔案
title: 迴音廊階段情境
exl-id: 150db070-eef5-4741-845c-775ab4034ead
source-git-commit: 01be819ccee1b3079b15a748480e9dacf6adb488
workflow-type: tm+mt
source-wordcount: '1707'
ht-degree: 0%

---

# 迴音廊階段情境 {#boomerang-stage-scenarios}

>[!AVAILABILITY]
>
>Boomerang功能僅對第3級客戶啟用。 若要要求更高的帳戶層級，請聯絡Adobe帳戶團隊（您的帳戶經理）。

以下是「飛毛腿舞台」的一些範例，可讓您瞭解如何進行 [!DNL Marketo Measure] 會在每種情況下建立接觸點。

## 單一潛在客戶案例 {#single-lead-scenarios}

**案例1：潛在客戶的標準Boomerang接觸點**

這是最簡單的「飛人」案例。 頂行（標示為Lead 1）代表個別Lead的歷程，及其接觸點在Lead記錄上的顯示方式。 底線（標示為Opportunity）顯示Leads的接觸點如何翻譯成Opportunity。 接觸點的進度會依出現時間從左到右進行說明。

在此案例中，客戶已選擇讓其 **MQL** 和 **SQL** 使用「回彈」追蹤的階段。 每個Boomerang接觸點位置都會標示階段和發生階段的數字(MQL-01、SQL-01、MQL-02。 等)。 該階段的最後一個迴音廊接觸點也會在接觸點位置中顯示「（最後一個）」。

然後Lead 1會轉換為具有機會的聯絡人，這視為OC接觸。

![](assets/1-1.png)

**案例2：潛在客戶的Boomerang接觸點和自訂階段**

在此案例中，客戶已選擇僅追蹤 **SQL階段** 與迴音廊接觸點。 系統仍在追蹤MQL和SAL階段，但使用 [!DNL Marketo Measure] 自訂舞台功能。

![](assets/2-1.png)

請注意，MQL接觸點位置未標示為數字。 這是因為系統未選取要使用迴音廊接觸點來追蹤。 為包含在自訂模型中、但未使用Boomerang追蹤的階段建立接觸點時， [!DNL Marketo Measure] 將會取用該階段的最後一次發生次數。

在SAL階段中， [!DNL Marketo Measure] 會忽略此階段的前兩次發生次數。 [!DNL Marketo Measure] 僅建立SAL接觸點 _最後_ 發生次數。 在上述範例中，這會直接發生在OC接觸點之前。

正在使用Boomerang接觸點追蹤SQL階段，並且已建立三個接觸點並相應地加上標籤。

然後Lead 1會轉換為具有機會的聯絡人，這視為OC接觸。

**案例3：潛在客戶未達到/略過階段時**

此案例使用與案例2相同的條件。 客戶已選擇只追蹤具有迴音廊接觸點的SQL階段。 MQL和SAL仍在追蹤中，但使用 [!DNL Marketo Measure] 自訂舞台功能。

![](assets/3.png)

在此案例中，銷售機會實際上永遠不會轉換到SAL階段。 在到達SAL階段之前，它會轉換為Contact，實際上就是「略過」SAL階段。 在此情況下， [!DNL Marketo Measure] 會假設SAL與OC接觸點同時發生，且SAL和OC位置會出現在相同的接觸點上。

然後Lead 1會轉換為具有機會的聯絡人，這視為OC接觸。

## 具有多個潛在客戶的案例 {#scenarios-with-multiple-leads}

由於我們正在研究多個潛在客戶如何影響Opportunity歷程，因此以下情境是Boomerang階段可能變得更加複雜的情況。

頂行（標示為Lead 1，藍色的）代表個別Lead的歷程，及其接觸點在Lead記錄上的顯示方式。 這同樣適用於Lead 2 （粉紅色）和Lead 3 （橙色）。 底線（標示為Opportunity）會顯示這兩個Lead的接觸點如何翻譯成Opportunity。 接觸點的進度會依出現時間從左到右進行說明。

**案例1：[!UICONTROL Three Leads with Opportunity]**

在此案例中，客戶已選擇追蹤 **MQL** 和 **SAL階段** 與迴音廊接觸點。 標準自訂階段正在追蹤SQL階段。

![](assets/4.png)

Opportunity上的FT和LC接觸點將來自Lead 1 （藍色），因為它們發生在Lead 2 （粉紅色）的FT和LC之前。 Lead 2的LC接觸點將作為Opportunity上的「Form」接觸點出現。

來自Lead 2的MQL-01 （最後一個）將成為Opportunity上的第一個MQL。 Lead 1的MQL-01不會顯示為Opportunity上的接觸點，因為Lead 2的MQL會先發生。 但是，Lead 1的MQL-02和MQL-03將會出現在Opportunity上。

請注意，正在以自訂階段追蹤SQL階段，而不是以自訂階段追蹤Boomerang。 即使Lead 1和Lead 2之間有三次SQL階段，只有最後一次SQL發生次數會作為接觸點包含在Opportunity中。

來自Lead 1的SAL-01 （上一個）接觸點會移轉作為Opportunity上的接觸點。 然後Lead 1會轉換為具有機會的聯絡人，這視為OC接觸。 潛在客戶2的SAL-01 （上一個）接觸點將建立為接觸點，因為此階段轉換已發生 _晚於_ OC觸控。

Lead 3的FT、LC和MQL、SQL、SAL接觸點（橙色）都發生在Opportunity上的OC接觸點之後。 這些接觸點將包含在Opportunity中，但視為「中間接觸」。

當潛在客戶2和3轉換為聯絡人時， [!DNL Marketo Measure] 將不會建立另一個OC接觸點，因為只能有一個機會建立階段。

**案例2 -[!UICONTROL Three Leads with Opportunity]**

在此案例中，客戶已選擇追蹤 **MQL**， **SQL**、和 **SAL** 與迴音廊接觸點一起暫存。

從FT到SAL-01 （上一個），Lead 1的所有接觸點都將包含在商機中。 Lead 2的LC接觸點將作為Form接觸點包含在Opportunity上的LC和MQL-01接觸點之間。

![](assets/5.png)

來自Lead 2的MQL-01 （上一個）最終成為Opportunity上的MQL-04 （上一個）接觸點。 由於此情境是檢視一個Opportunity中多個Lead的歷程，因此Lead的接觸點的定位和編號在轉換為Opportunity上的接觸點時可能會變更。 同樣地，來自Lead 2的SQL-01 (Last)會變成Opp上的SQL-04 (Last)。 Lead 2的SAL-01 （上一個）也會變成Opportunity的SAL-02 （上一個）。

此外，請注意Opportunity上僅包含2個SAL接觸點。 [!DNL Marketo Measure] 不會嘗試強制/建立階段轉變的接觸點（如果實際上並未發生）。

Lead 3的接觸點歷程在OC接觸發生之前開始，但在Lead 1和Lead 2進行FT和LC接觸之後很久。 在此案例中，Lead 3的FT和LC將作為Opportunity上的Form接觸點出現。 然後Lead 1會轉換為具有機會的聯絡人，這視為OC接觸。

Lead 3的MQL、SQL和SAL接觸都會在OC接觸後同時發生。 由於它們發生在OC接觸點之後，此接觸點將在Opportunity上顯示為Form/Middle Touch，而不是Boomerang階段轉換。

**案例2a — 網頁瀏覽反彈式接觸點**

在此案例中，客戶已選擇追蹤 **MQL**， **SQL**、和 **SAL** 與迴音廊接觸點一起暫存。 除了少數例外情況外，此案例幾乎與上述案例相同。

![](assets/6.png)

從FT到SAL-01 （上一個），Lead 1的所有接觸點都將包含在商機中。 Lead 2的LC接觸點將作為Form接觸點包含在Opportunity上的LC和MQL-01接觸點之間。

潛在客戶2的MQL-01 （上次） （網頁造訪）將不會建立為Opp上的接觸點。 這是因為此接觸點是發生在SQL階段最後一次發生之後的Web造訪，無助於推動機會前進。

Lead 1的階段變更為SAL，然後轉換為具有機會的聯絡人；在這種情況下，SAL-01 （上一個）和OC位置將在相同的接觸點中合併。

Lead 3的FT、LC觸控功能將建立為Opp上的表單接觸點。 只有表單填入動作才會建立為OC接觸後的接觸點。 因此，「銷售機會2」的SQL-01 （上一個）和SAL-01 （上一個）階段轉換將不會建立為接觸點，因為這些接觸點是網頁造訪。

潛在客戶3的MQL、SQL、SAL接觸將會納入為接觸點，因為這是表單填寫動作。

**案例3 - Boomerang歸因加權**

在此案例中，客戶已選擇追蹤 **MQL**， **SQL**、和 **SAL** 與迴音廊接觸點一起暫存。

![](assets/7.png)

Opportunity上的FT和LC接觸點將來自Lead 1 （藍色），因為它們發生在Lead 2 （粉紅色）的FT和LC之前。 Lead 2的LC接觸點將作為Opportunity上的「Form」接觸點出現。

來自Lead 2的MQL-01 （最後一個）將成為Opportunity上的第一個MQL。 Lead 1的MQL-01不會顯示為Opportunity上的接觸點，因為Lead 2的MQL會先發生。

來自Lead 2的SQL-01 （上一個）將成為Opportunity上的SQL-01。 潛在客戶1上的SQL-01不會顯示為商機的接觸點，因為潛在客戶2上的SQL-01是先發生的。

請注意，Lead 1在最終到達SAL階段之前，會在MQL和SQL之間移動幾次。 SQL-01、MQL-02、SQL-02、MQL-03、SQL-03 _不會_ 被列為機會的接觸點，因為這些階段轉換無助於推動機會在歷程中前進。

來自Lead 1的SAL-01 （上一個）接觸點是要包含在Opp上的下一個接觸點。 潛在客戶1接著會轉換為與商機的聯絡人，建立OC接觸點。

Lead 3的FT和LC，以及MQL、SQL和SAL接觸點，將以表單式接觸形式出現在Opportunity上。

Lead 2的SQL-01 （上一個）接觸點不會作為Opp上的接觸點納入，因為它發生在OC接觸點之後。 此外，已發生Lead 2的SQL階段轉換 _在最後的SAL階段轉換之後_，無助於推動機會之旅。

## 機會案例 {#opportunity-scenarios}

**案例1 — 具有商機與回圈追蹤的聯絡人**

在此案例中，客戶已選擇追蹤 **示範和交涉階段轉換** 於 **連絡人**. 每個迴音廊階段最多可接收兩個接觸點。 Contact上的階段轉變與Lead上的階段轉變之間的差異在於Contact階段轉變可以顯示為Opportunity上的Boomerang接觸點 _晚於_ oc接觸點。 這不適用於在Lead上發生的階段轉變，因為這些轉變會顯示為Form接觸點。

![](assets/8.png)

在此範例中，Contact 1的Demo和Negotiation Stage轉換會作為Demo-01和Negotiation-01接觸點包含在Opportunity中。 連絡人2的示範階段轉換發生 _晚於_ 連絡人1的，並出現在Opportunity上當作Demo-02 （上一個）接觸點。

請注意，沒有第二個轉變到「交涉」階段；Opportunity會立即從Demo-02 （上一個）移動到Close Won。 在這種情況下， [!DNL Marketo Measure] 將包括「交涉」轉變與「成功關閉」接觸點。
