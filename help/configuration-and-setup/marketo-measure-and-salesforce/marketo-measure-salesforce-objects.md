---
unique-page-id: 18874582
description: '"[!DNL Marketo Measure] Salesforce物件 —  [!DNL Marketo Measure]  — 產品檔案」'
title: '"[!DNL Marketo Measure] Salesforce物件」'
exl-id: d5d6f334-6531-40fa-b043-75b49d8f43d5
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '935'
ht-degree: 0%

---

# [!DNL Marketo Measure] Salesforce物件 {#marketo-measure-salesforce-objects}

>[!NOTE]
>
>您可能會看到指定&#39;&#39;的說明[!DNL Marketo Measure]&quot;，但仍在您的CRM中看到「Bizible」。 我們正致力於更新此專案，品牌重塑將很快反映在您的CRM中。

時間 [!DNL Marketo Measure] 安裝於 [!DNL Salesforce] (SFDC)，數個自訂 [!DNL Marketo Measure] 新增物件。 本文提供其中幾個自訂專案的說明 [!DNL Marketo Measure] 物件。 某些物件 [!DNL Marketo Measure] 新增至 [!DNL Salesforce] 為：

* [購買者接觸點](#touchpoint)
* [購買者歸因接觸點](#attribution)
* [[!DNL Marketo Measure] 個人](#person)
* [[!DNL Marketo Measure] A/B測試](#ab)
* [[!DNL Marketo Measure] 事件](#events)

由您要追蹤的專案所擷取的接觸點會寫入由安裝所建立的自訂物件 [!DNL Bizible Salesforce] 封裝。

[!DNL Marketo Measure] 物件與特定標準相關 [!DNL Salesforce] 物件。 這可讓您報告 [!DNL Marketo Measure] 和 [!DNL Salesforce] 物件在一起。 下表顯示了 [!DNL Salesforce] 物件 [!DNL Marketo Measure] 物件與相關。

![](assets/1-1.png)

## 購買者接觸點 {#buyer-touchpoint}

此 [!UICONTROL Buyer Touchpoint] (BT) Object訴說個人的行銷故事。 其中儲存與銷售機會和聯絡人產生的行銷接觸點相關的所有資料。 BT會顯示資訊，例如接觸點來自的行銷管道，或廣告促銷活動將特定銷售機會/聯絡人帶到您的網站。

BT物件會顯示在潛在客戶與聯絡人頁面上，做為 **相關清單** （請參閱下圖）。

![](assets/2-1.png)

BT相關清單會顯示屬於「銷售機會」或「連絡人」的所有接觸點。 在清單中為自訂 [!DNL Marketo Measure] 提供有關每個接觸點的進一步詳細資訊的欄位。 按一下「購買者接觸點ID」編號，您就會進入「購買者接觸點詳細資訊」頁面，該頁面會提供更多有關接觸點的詳細資訊，例如銷售機會/聯絡人在該Web工作階段造訪的第一個網頁(**登陸頁面**)。

## 購買者歸因接觸點 {#buyer-attribution-touchpoint}

此 [!UICONTROL Buyer Attribution Touchpoint] Object會訴說與機會相關之聯絡人的行銷互動故事。 它顯示 *歸因* 和行銷接觸點相關的資料。 此物件可讓您檢視將多少收入點數歸因於每個行銷接觸點。 您使用的歸因模型型別將決定歸因於接觸點的收入百分比。

採購員歸因接觸點(BAT)只有在建立「商機」後，才會建立，該商機與具有「採購員接觸點(BT)」資料的聯絡人有關。 BAT若沒有Opportunity將無法建立。 建立Opportunity後，BAT物件將使用 [!DNL Salesforce] *數量* 「機會」上的欄位，以瞭解歸因於接觸點的收入。

A **工作流程** 如果您使用 [自訂金額欄位](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md) 以顯示Opportunity物件的收入。 [!DNL Marketo Measure] 無法讀取自訂「金額」欄位中顯示的資訊，因此無法填入接觸點上的收入歸因資料。 此工作流程將使用 **[!DNL Marketo Measure]機會金額** 欄位，其中一項 [!DNL Marketo Measure] 自訂欄位，以將自訂金額欄位的收入值對應至機會金額欄位。

![](assets/3-1.png)

BAT物件會顯示在 [!UICONTROL Opportunity]， [!UICONTROL Contact]、和 [!UICONTROL Account] 物件做為相關清單。 此清單會顯示所有具有屬於某個機會的歸因資料的接觸點。 按一下「購買者歸因接觸點ID」 ，您會直接前往「購買者歸因接觸點詳細資訊」頁面。 在這裡，您可以看到更具體的歸因資料，以及有關接觸點來源資訊（類似於購買者接觸點物件所提供的資訊）。

## [!DNL Marketo Measure] 個人 {#marketo-measure-person}

此 [!DNL Marketo Measure] Person Object將Lead和Contact物件關聯在一起。 Salesforce不會提供立即可用選項，讓您使用相同報表中的Lead和Contact物件來建立報表。 透過關聯潛在客戶與連絡人物件， [!DNL Marketo Measure] 「人員」可讓您在同一份報表中同時報告兩個物件。 當Lead已轉換為Contact時，這會特別有用。 在 [!DNL Marketo Measure] 個人記錄：您會看到對應Lead和/或Contact記錄的查閱、與個人相連結的Touchpoints相關清單，以及個人ID （一律為Lead/Contact的電子郵件地址）。 由於 [!DNL Marketo Measure] 與銷售機會和聯絡人物件相關的個人，將永遠不會 [!DNL Marketo Measure] 繫結至購買者歸因接觸點的個人記錄。 以下是 [!DNL Marketo Measure] Salesforce中的個人記錄：

![](assets/4.png)

## [!DNL Marketo Measure] A/B 測試 {#marketo-measure-a-b-test}

如果您要透過執行A/B測試 [!DNL Optimizely] 或VWO (Visual Web Optimizer)，您可以將這些帳戶連線至您的 [!DNL Marketo Measure] 在Salesforce中檢視A/B測試資料的帳戶。 此 [!DNL Marketo Measure] A/B測試物件基本上可讓您從Optimizy/VWO取得A/B測試資料，並將資料連結至銷售機會和聯絡人。

![](assets/5.png)

此 [!DNL Marketo Measure] A/B測試物件會顯示為 [!UICONTROL Leads]， [!UICONTROL Contacts] 和 [!UICONTROL Opportunity] 頁面。 清單會顯示您正在最佳化或VWO中執行的所有實驗和變數，並可讓您檢視與特定潛在客戶或聯絡人相關的實驗/變數。

## [!DNL Marketo Measure] 事件 {#marketo-measure-events}

此 [!DNL Marketo Measure] 事件物件可讓您追蹤網站上發生的特定事件。 若要追蹤網站上發生的特定事件，除了新增自訂程式碼至您的頁面外， [!DNL Marketo Measure] Javascript。 擷取的資訊將顯示在 [!DNL Marketo Measure] 物件相關清單，可在以下網址找到： [!UICONTROL Leads]， [!UICONTROL Contacts] 和 [!UICONTROL Opportunity] 頁面。 此 [!DNL Marketo Measure] 事件物件 *不會* 繫結至歸因資料。 此物件的目的是檢視使用者是否在您的網站上執行特定動作。

## [!DNL Marketo Measure] 欄位 {#marketo-measure-fields}

由擷取的資料 [!DNL Marketo Measure] Javascript將會推送至自訂 [!DNL Marketo Measure] 內的欄位 [!DNL Marketo Measure] 物件。 特定欄位將只會出現在特定物件上。 取得所有 [!DNL Marketo Measure] 欄位，請 [按一下這裡](/help/introduction-to-marketo-measure/overview-resources/glossary-of-marketo-measure-fields.md). 針對下列專案的視覺效果： [!DNL Marketo Measure] 物件間隔 [!DNL Marketo Measure] 與相關的欄位，請 [按一下這裡](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md).

## [!DNL Marketo Measure] 報告和儀表板 {#marketo-measure-reports-and-dashboards}

此 [!DNL Marketo Measure] 新增至您的的報告和控制面板 [!DNL Salesforce] 提供立即可用的報表和資料視覺化功能。 這些是基本功能 [!DNL Marketo Measure] 報表，可讓您快速組織、分析和瞭解接觸點資料。
