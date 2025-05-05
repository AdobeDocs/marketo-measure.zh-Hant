---
unique-page-id: 18874582
description: '[!DNL Marketo Measure]個Salesforce物件 —  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure]個Salesforce物件'
exl-id: d5d6f334-6531-40fa-b043-75b49d8f43d5
feature: Salesforce
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 0%

---

# [!DNL Marketo Measure]個Salesforce物件 {#marketo-measure-salesforce-objects}

>[!NOTE]
>
>您可能會在檔案中看到指定&quot;[!DNL Marketo Measure]&quot;的說明，但在您的CRM中仍會看到&quot;Bizible&quot;。 我們正致力於更新此專案，品牌重塑將很快反映在您的CRM中。

當[!DNL Marketo Measure]安裝在[!DNL Salesforce] (SFDC)中時，幾個自訂[!DNL Marketo Measure]物件已新增。 本文說明其中幾個自訂[!DNL Marketo Measure]物件。 [!DNL Marketo Measure]新增至[!DNL Salesforce]的部分物件包括：

* [Buyer Touchpoint](#touchpoint)
* [Buyer Attribution Touchpoint](#attribution)
* [[!DNL Marketo Measure]人](#person)
* [[!DNL Marketo Measure] A/B測試](#ab)
* [[!DNL Marketo Measure] 活動](#events)

由您要追蹤的專案所擷取的接觸點，會寫入到安裝[!DNL Bizible Salesforce]套件所建立的自訂物件。

[!DNL Marketo Measure]物件與特定標準[!DNL Salesforce]物件相關。 這可讓您一起報告[!DNL Marketo Measure]和[!DNL Salesforce]物件。 下表顯示[!DNL Marketo Measure]物件與哪個[!DNL Salesforce]物件相關。

![](assets/1-1.png)

## Buyer Touchpoint {#buyer-touchpoint}

[!UICONTROL Buyer Touchpoint] (BT)物件會講述個人的行銷故事。 其中儲存與銷售機會和聯絡人產生的行銷接觸點相關的所有資料。 BT會顯示資訊，例如接觸點來自的行銷管道，或廣告促銷活動將特定銷售機會/聯絡人帶到您的網站。

BT物件會以&#x200B;**相關清單**&#x200B;的形式顯示在潛在客戶與聯絡人頁面上（請參閱下圖）。

![](assets/2-1.png)

「BT相關清單」會顯示屬於「銷售機會」或「聯絡人」的所有接觸點。 清單中有自訂[!DNL Marketo Measure]欄位，提供有關每個接觸點的進一步詳細資訊。 按一下Buyer Touchpoint ID號碼，您就會前往Buyer Touchpoint「詳細資料」頁面，該頁面提供更多有關接觸點的詳細資訊，例如潛在客戶/聯絡人在該Web工作階段期間造訪的第一個網頁（**登陸頁面**）。

## Buyer Attribution Touchpoint {#buyer-attribution-touchpoint}

[!UICONTROL Buyer Attribution Touchpoint]物件說明與機會相關之聯絡人的行銷互動故事。 它會顯示與行銷接觸點相關的&#x200B;*歸因*&#x200B;資料。 此物件可讓您檢視將多少收入點數歸因於每個行銷接觸點。 您使用的歸因模型型別將決定歸因於接觸點的收入百分比。

「購買者歸因接觸點(BAT)」只有在建立「商機」後，才會建立「商機」，此商機與具有Buyer Touchpoint (BT)資料的聯絡人有關。 如果沒有商機，將不會建立BAT。 一旦建立機會後，BAT物件就會使用機會上的[!DNL Salesforce] *金額*&#x200B;欄位，來瞭解歸因於接觸點的收入有多少。

如果您使用[自訂金額欄位](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)在機會物件上顯示收入，則必須建立&#x200B;**工作流程**。 [!DNL Marketo Measure]無法讀取自訂「金額」欄位中顯示的資訊，因此無法填入接觸點上的收入歸因資料。 此工作流程將使用&#x200B;**[!DNL Marketo Measure]機會金額**&#x200B;欄位（其中[!DNL Marketo Measure]個自訂欄位之一）將自訂金額欄位的收入值對應至機會金額欄位。

![](assets/3-1.png)

BAT物件在[!UICONTROL Opportunity]、[!UICONTROL Contact]和[!UICONTROL Account]物件上顯示為相關清單。 此清單會顯示所有具有屬於某個機會的歸因資料的接觸點。 按一下Buyer Attribution Touchpoint ID可將您導向Buyer Attribution Touchpoint詳細資料頁面。 在這裡，您可以看到更具體的歸因資料，以及有關接觸點來源資訊(類似於Buyer Touchpoint物件所提供的資訊)。

## [!DNL Marketo Measure]人 {#marketo-measure-person}

[!DNL Marketo Measure]個人物件將潛在客戶與連絡人物件關聯在一起。 現成可用的Salesforce不會提供選項，讓您使用相同報表中的Lead和Contact物件來建立報表。 透過關聯潛在客戶與連絡人物件，[!DNL Marketo Measure]人員可讓您在同一份報表中報告兩個物件。 當Lead已轉換為Contact時，這會特別有用。 在[!DNL Marketo Measure]個人記錄中，您將會看到對應銷售機會和/或聯絡人記錄的查閱、與個人相連結的接觸點相關清單，以及個人ID （永遠是銷售機會/聯絡人的電子郵件地址）。 由於[!DNL Marketo Measure]個人與銷售機會和聯絡人物件有關，因此將永遠沒有與Buyer Attribution Touchpoint繫結的[!DNL Marketo Measure]個人記錄。 以下是Salesforce中[!DNL Marketo Measure]個人記錄的範例：

![](assets/4.png)

## [!DNL Marketo Measure] A/B測試 {#marketo-measure-a-b-test}

如果您透過[!DNL Optimizely]或VWO (Visual Web Optimizer)執行A/B測試，您可以將這些帳戶連線至您的[!DNL Marketo Measure]帳戶，以在Salesforce中檢視A/B測試資料。 [!DNL Marketo Measure] A/B測試物件基本上可讓您從Optimizy/VWO取得A/B測試資料，並將資料連結至銷售機會和聯絡人。

![](assets/5.png)

[!DNL Marketo Measure] A/B測試物件在[!UICONTROL Leads]、[!UICONTROL Contacts]和[!UICONTROL Opportunity]頁面上顯示為相關清單。 清單會顯示您透過Optimizly或VWO執行的所有實驗與變化，並可讓您檢視與特定潛在客戶及聯絡人相關的實驗/變化。

## [!DNL Marketo Measure] 活動 {#marketo-measure-events}

[!DNL Marketo Measure]事件物件可讓您追蹤網站上發生的特定事件。 若要追蹤您網站上發生的特定事件，除了[!DNL Marketo Measure] Javascript之外，您還必須將自訂程式碼新增至您的頁面。 擷取的資訊將顯示在[!DNL Marketo Measure]物件相關清單中，可在[!UICONTROL Leads]、[!UICONTROL Contacts]和[!UICONTROL Opportunity]頁面上找到。 [!DNL Marketo Measure]事件物件&#x200B;*未*&#x200B;繫結至歸因資料。 此物件的目的是檢視使用者是否在您的網站上執行特定動作。

## [!DNL Marketo Measure]欄位 {#marketo-measure-fields}

由[!DNL Marketo Measure] JavaScript擷取的資料已推送到[!DNL Marketo Measure]物件內的自訂[!DNL Marketo Measure]欄位。 某些欄位僅存在於某些物件上。 您可以檢閱[[!DNL Marketo Measure]欄位][&#128279;](/help/introduction-to-marketo-measure/overview-resources/glossary-of-marketo-measure-fields.md)的[字彙表，以及相關 [!DNL Marketo Measure] 物件](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md)的視覺效果。

## [!DNL Marketo Measure]個報告和儀表板 {#marketo-measure-reports-and-dashboards}

新增至您[!DNL Salesforce]的[!DNL Marketo Measure]報告和儀表板提供立即可用的報告和資料視覺化功能。 這些是基本的[!DNL Marketo Measure]報告，可讓您快速組織、分析和瞭解接觸點資料。
