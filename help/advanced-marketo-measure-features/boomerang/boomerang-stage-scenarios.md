---
unique-page-id: 18874692
description: Boomerang階段案例 —  [!DNL Marketo Measure]
title: 迴旋舞步舞台情境
exl-id: 150db070-eef5-4741-845c-775ab4034ead
feature: Boomerang
source-git-commit: 855ae5abe6f8782ed1883f85be545c11bf86e7ce
workflow-type: tm+mt
source-wordcount: '1500'
ht-degree: 0%

---

# 迴旋舞步舞台情境 {#boomerang-stage-scenarios}

>[!AVAILABILITY]
>
>Boomerang功能僅針對2級和3級客戶啟用。 若要請求更高的客戶層級，請聯絡Adobe客戶團隊（您的客戶經理）。

以下是Boomerang Stage案例的幾個範例，可讓您瞭解[!DNL Marketo Measure]如何在每種情況下建立接觸點。

## 單一潛在客戶案例 {#single-lead-scenarios}

**案例1：潛在客戶的標準Boomerang接觸點**

這是最簡單的迴旋鏢案例。 頂線（標示為Lead 1）代表個別Lead的歷程，及其接觸點在Lead記錄上的顯示方式。 底線（標示為Opportunity）顯示Leads的接觸點轉譯為Opportunity的方式。 接觸點的進度會依發生次數從左到右進行說明。

在此案例中，客戶已選擇使用Boomerangs追蹤其&#x200B;**MQL**&#x200B;和&#x200B;**SQL**&#x200B;階段。 每個Boomerang接觸點位置都標有階段和發生階段的數字(MQL-01、SQL-01、MQL-02)。 該階段的最後一個回圈接觸點在接觸點位置有「（最後一個）」。

然後Lead 1會轉換為具有商機的聯絡人，這視為OC接觸。

![](assets/1-1.png)

**案例2：潛在客戶的Boomerang接觸點和自訂階段**

在此案例中，客戶已選擇只追蹤&#x200B;**SQL階段**&#x200B;與迴旋式接觸點。 仍在追蹤MQL和SAL階段，但使用[!DNL Marketo Measure]自訂階段功能。

![](assets/2-1.png)

請注意，MQL接觸點位置未標示為數字。 這是因為未選取要使用迴旋加速器接觸點來追蹤。 為包含在自訂模型中但未使用Boomerang追蹤的階段建立接觸點時，[!DNL Marketo Measure]會取用該階段的最後一次發生。

對於SAL階段，[!DNL Marketo Measure]會忽略此階段的前兩次發生次數。 [!DNL Marketo Measure]只會為&#x200B;_最後_&#x200B;個發生次數建立SAL接觸點。 在上述範例中，這會在OC接觸點之前發生。

正在使用Boomerang接觸點追蹤SQL階段，並且已建立三個接觸點並相應地加上標籤。

然後Lead 1會轉換為具有商機的聯絡人，這視為OC接觸。

**案例3：潛在客戶未達到/略過階段**&#x200B;時

此情境使用與情境2相同的條件。 客戶已選擇只追蹤具有回圈接觸點的SQL階段。 仍在追蹤MQL和SAL，但使用[!DNL Marketo Measure]自訂階段功能。

![](assets/3.png)

在此案例中，銷售機會實際上永遠不會轉換到SAL階段。 它到達SAL階段之前會轉換為Contact，實際上就是「略過」SAL階段。 在此情況下，[!DNL Marketo Measure]會假設SAL與OC接觸點同時發生，且SAL和OC位置會出現在相同的接觸點上。

然後Lead 1會轉換為具有商機的聯絡人，這視為OC接觸。

## 具有多個潛在客戶的案例 {#scenarios-with-multiple-leads}

以下情境中，隨著我們審視多個潛在客戶如何影響機會歷程，回味轉送階段會變得更複雜。

頂線（標示為銷售機會1，藍色的）代表個別銷售機會的歷程，及其接觸點在Lead記錄上的顯示方式。 這同樣適用於Lead 2 （粉紅色）和Lead 3 （橙色）。 底線（標籤為Opportunity）會顯示這兩個Lead的接觸點轉譯為Opportunity的方式。 接觸點的進度會依發生次數從左到右進行說明。

**案例1：[!UICONTROL Three Leads with Opportunity]**

在此案例中，客戶已選擇使用回圈接觸點追蹤&#x200B;**MQL**&#x200B;和&#x200B;**SAL階段**。 標準自訂階段正在追蹤SQL階段。

![](assets/4.png)

Opportunity上的FT和LC接觸點來自Lead 1 （藍色），因為它們發生在Lead 2的FT和LC之前（粉紅色）。 Lead 2的LC接觸點會在Opportunity上顯示為「Form」接觸點。

來自Lead 2的MQL-01 （最後一個）將成為Opportunity上的第一個MQL。 Lead 1的MQL-01不會顯示為Opportunity上的接觸點，因為Lead 2的MQL會先發生。 但是，銷售機會1的MQL-02和MQL-03將會出現在商機中。

正在以自訂階段追蹤SQL階段，而不是以回溯階段追蹤。 雖然Lead 1和Lead 2之間有三次SQL階段，但只有最後一次SQL發生次數會作為接觸點包含在Opportunity中。

來自Lead 1的SAL-01 （最後一個）接觸點會移轉為Opportunity上的接觸點。 然後Lead 1會轉換為具有商機的聯絡人，這視為OC接觸。 潛在客戶2的SAL-01 （上一個）接觸點將不會建立為接觸點，因為此階段轉換發生在&#x200B;_OC接觸_&#x200B;之後。

Lead 3的FT、LC和MQL、SQL、SAL接觸點（橙色）都發生在Opportunity上的OC接觸點之後。 這些接觸點包含在Opportunity中，但視為「中間接觸」。

當Lead 2和3轉換為Contacts時，[!DNL Marketo Measure]將不會建立另一個OC接觸點，因為只能有一個機會建立階段。

**案例2 - Web造訪迴旋接觸點**

在此案例中，客戶已選擇追蹤具有回圈接觸點的&#x200B;**MQL**、**SQL**&#x200B;和&#x200B;**SAL**&#x200B;階段。 除了少數例外情況，此案例與上述案例幾乎相同。

![](assets/6.png)

從FT到SAL-01 （最後一個），Lead 1的所有接觸點都將包含在商機中。 Lead 2的LC接觸點將作為Form接觸點包含在Opportunity上的LC和MQL-01接觸點之間。

潛在客戶2的MQL-01 （上次） （網頁造訪）將不會建立為Opp上的接觸點。 這是因為此接觸點是發生在SQL階段最後一次發生後的Web造訪，無助於推動機會前進。

Lead 1的階段會變更為SAL，然後轉換為具有Opportunity的Contact；在這種情況下，SAL-01 （上一個）和OC位置會在相同的接觸點中合併。

Lead 3的FT，LC觸控是建立為Opp上的表單接觸點。 只有表單填寫動作會在OC接觸後建立為接觸點。 因此，不會將Lead 2的SQL-01 （上一個）和SAL-01 （上一個）階段轉換建立為接觸點，因為這些接觸點是網頁造訪。

潛在客戶3的MQL、SQL、SAL接觸會作為接觸點納入，因為這是表單填寫動作。

**案例3 - Boomerang歸因加權**

在此案例中，客戶已選擇追蹤具有回圈接觸點的&#x200B;**MQL**、**SQL**&#x200B;和&#x200B;**SAL**&#x200B;階段。

![](assets/7.png)

Opportunity上的FT和LC接觸點來自Lead 1 （藍色），因為它們發生在Lead 2的FT和LC之前（粉紅色）。 Lead 2的LC接觸點在Opportunity上會顯示為「Form」接觸點。

來自Lead 2的MQL-01 （最後一個）成為機會上的第一個MQL。 Lead 1的MQL-01不會顯示為Opportunity上的接觸點，因為Lead 2的MQL會先發生。

來自Lead 2的SQL-01 （最後一個）成為Opportunity上的SQL-01。 潛在客戶1上的SQL-01不會顯示為商機的接觸點，因為潛在客戶2上的SQL-01是先發生的。

請注意，Lead 1在最終到達SAL階段之前，會在MQL和SQL之間移動幾次。 SQL-01、MQL-02、SQL-02、MQL-03、SQL-03 _將不會_&#x200B;作為機會上的接觸點納入，因為這些階段轉換無助於推動機會在歷程中前進。

Lead 1的SAL-01 （上一個）接觸點是要包含在Opp上的下一個接觸點。 潛在客戶1接著會轉換為與商機的聯絡人，以建立OC接觸點。

Lead 3的FT和LC以及MQL、SQL和SAL接觸點在Opportunity上顯示為表單接觸。

Lead 2的SQL-01 （上一個）接觸點不會包含在Opp上，因為它發生在OC接觸點之後。 此外，潛在客戶2的SQL階段轉換在最後的SAL階段轉換&#x200B;_之後發生_，無助於推動機會歷程前進。

## 機會案例 {#opportunity-scenarios}

**案例1 — 具有商機和回圈追蹤的聯絡人**

在此案例中，客戶已選擇追蹤&#x200B;**連絡人**&#x200B;上的&#x200B;**示範和交涉階段轉換**。 每個迴旋舞蹈舞台最多可接收兩個接觸點。 Contact上的階段轉換與Lead上的階段轉換之間的差異在於，Contact階段轉換可以在OC接觸點之後&#x200B;_的Opportunity_&#x200B;上顯示為回溯型接觸點。 對於在Lead上發生的階段轉變而言，情況並非如此，因為這些轉變會顯示為「表單」接觸點。

![](assets/8.png)

在此範例中，Contact 1的Demo和Negotiation Stage轉換會包含在Opportunity上的Demo-01和Negotiation-01接觸點中。 Contact 2的Demo階段轉換發生在&#x200B;_Contact 1的_&#x200B;之後，並出現在Opportunity上的Demo-02 （上一個）接觸點。

請注意，沒有第二個轉換到「交涉」階段；Opportunity會從Demo-02 （上一個）移動到Close Won。 在此案例中，[!DNL Marketo Measure]將包含具有「已結束的勝利」接觸點的「交涉」轉變。
