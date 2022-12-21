---
unique-page-id: 18874582
description: '"[!DNL Marketo Measure] Salesforce對象 —  [!DNL Marketo Measure]  — 產品檔案」'
title: '"[!DNL Marketo Measure] Salesforce對象」'
exl-id: d5d6f334-6531-40fa-b043-75b49d8f43d5
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '935'
ht-degree: 0%

---

# [!DNL Marketo Measure] Salesforce對象 {#marketo-measure-salesforce-objects}

>[!NOTE]
>
>您可能會看到指定「[!DNL Marketo Measure]「 」，但仍可在CRM中看到「Bizible」。 我們正致力更新該更新，品牌重塑將很快反映在您的CRM中。

當 [!DNL Marketo Measure] 安裝於 [!DNL Salesforce] (SFDC)，數個自訂 [!DNL Marketo Measure] 添加對象。 本文說明其中幾項自訂 [!DNL Marketo Measure] 對象。 某些對象 [!DNL Marketo Measure] 新增至 [!DNL Salesforce] 為：

* [購買者接觸點](#touchpoint)
* [購買者歸因接觸點](#attribution)
* [[!DNL Marketo Measure] 個人](#person)
* [[!DNL Marketo Measure] A/B測試](#ab)
* [[!DNL Marketo Measure] 事件](#events)

由您要追蹤的項目所擷取的接觸點，會寫入安裝所建立的自訂物件 [!DNL Bizible Salesforce] 包。

[!DNL Marketo Measure] 對象與特定標準相關 [!DNL Salesforce] 對象。 這可讓您報告 [!DNL Marketo Measure] 和 [!DNL Salesforce] 物體。 下表顯示 [!DNL Salesforce] 物件 [!DNL Marketo Measure] 物件與相關。

![](assets/1-1.png)

## 購買者接觸點 {#buyer-touchpoint}

此 [!UICONTROL Buyer Touchpoint] (BT)物件可說明個人的行銷故事。 它會儲存與銷售機會和聯絡人產生的行銷接觸點相關的所有資料。 BT會顯示資訊，例如接觸點來自哪個行銷管道，或是哪個廣告促銷活動將該特定銷售機會/連絡人帶往您的網站。

BT對象在Lead和Contacts頁上顯示為 **相關清單** （請參閱下圖）。

![](assets/2-1.png)

「BT相關清單」顯示屬於銷售機會或聯繫人的所有接觸點。 清單內為自訂 [!DNL Marketo Measure] 提供每個接觸點詳細資訊的欄位。 按一下購買者接觸點ID號碼，會將您導向「購買者接觸點詳細資料」頁面，此頁面提供接觸點的更多詳細資料，例如銷售機會/連絡人在該網站工作階段期間造訪的第一個網頁(**登陸頁面**)。

## 購買者歸因接觸點 {#buyer-attribution-touchpoint}

此 [!UICONTROL Buyer Attribution Touchpoint] Object會說明您的聯絡人與商機相關的行銷互動故事。 它會顯示 *歸因* 與行銷接觸點相關的資料。 此物件可讓您查看每個行銷接觸點的收入評分。 您使用的歸因模型類型將決定歸因至接觸點的收入百分比。

只有在建立了與具有Buyer Touchpoint(BT)資料的聯繫人相關的Opportunity後，才會建立Buyer Attribution Touchpoint(BAT)。 沒有Opportunity將無法建立BAT。 一旦建立了Opportunity,BAT對象將使用 [!DNL Salesforce] *金額* 「機會」欄位，以了解要歸因於接觸點的收入。

A **工作流程** 必須建立 [自訂金額欄位](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md) 顯示Opportunity對象上的收入。 [!DNL Marketo Measure] 無法讀取自訂金額欄位中呈現的資訊，因此無法在接觸點上填入收入歸因資料。 此工作流程將使用 **[!DNL Marketo Measure]機會金額** 欄位，其中 [!DNL Marketo Measure] 自定義欄位，將自定義金額欄位中的收入值映射到機會金額欄位。

![](assets/3-1.png)

BAT對象在 [!UICONTROL Opportunity], [!UICONTROL Contact]，和 [!UICONTROL Account] 作為相關清單的對象。 此清單顯示所有具有屬於Opportunity的歸因資料的接觸點。 按一下「購買者歸因接觸點ID」，即可將您導向至「購買者歸因接觸點詳細資料」頁面。 在此，您將能夠查看更具體的歸因資料，以及接觸點來自何處的相關資訊（類似於購買者接觸點物件提供的內容）。

## [!DNL Marketo Measure] 個人 {#marketo-measure-person}

此 [!DNL Marketo Measure] 「人員對象」(Person Object)將Lead和Contact對象關聯在一起。 Salesforce不提供使用相同報表中的Lead和Contact物件建立報表的現成選項。 通過與Lead和Contact對象相關， [!DNL Marketo Measure] 「人員」可讓您在同一個報表中報告兩個物件。 當銷售機會已轉換為聯絡人時，這特別實用。 在a [!DNL Marketo Measure] 您將看到對應的Lead和/或Contact記錄的查找、與該人員關聯的接觸點的相關清單，以及人員ID（始終是Lead/Contact的電子郵件地址）。 由於 [!DNL Marketo Measure] 與銷售機會與聯絡物件相關的人員，將不會 [!DNL Marketo Measure] 系結至購買者歸因接觸點的人員記錄。 以下是 [!DNL Marketo Measure] Salesforce中的人員記錄：

![](assets/4.png)

## [!DNL Marketo Measure] A/B測試 {#marketo-measure-a-b-test}

如果您執行A/B測試，請透過 [!DNL Optimizely] 或VWO(Visual Web Optimizer)，您可以將這些帳戶連接到 [!DNL Marketo Measure] 帳戶來檢視Salesforce中的A/B測試資料。 此 [!DNL Marketo Measure] A/B測試對象基本上允許您從Optimile/VWO中獲取A/B測試資料，並將資料與Lead和Contact關聯。

![](assets/5.png)

此 [!DNL Marketo Measure] A/B測試物件會顯示為 [!UICONTROL Leads], [!UICONTROL Contacts] 和 [!UICONTROL Opportunity] 頁面。 清單會顯示您通過Optimiley或VWO運行的所有實驗和變化，並允許您查看與特定Lead和Contact相關的實驗/變化。

## [!DNL Marketo Measure] 事件 {#marketo-measure-events}

此 [!DNL Marketo Measure] 事件物件可讓您追蹤網站上發生的特定事件。 若要追蹤網站上發生的特定事件，除了 [!DNL Marketo Measure] Javascript。 擷取的資訊會顯示在 [!DNL Marketo Measure] 對象相關清單，可在 [!UICONTROL Leads], [!UICONTROL Contacts] 和 [!UICONTROL Opportunity] 頁面。 此 [!DNL Marketo Measure] 事件物件 *不* 連結至歸因資料。 此物件的用途是查看使用者是否在您的網站上採取特定動作。

## [!DNL Marketo Measure] 欄位 {#marketo-measure-fields}

由 [!DNL Marketo Measure] Javascript將推送至自訂 [!DNL Marketo Measure] 我們 [!DNL Marketo Measure] 對象。 某些欄位只會出現在特定物件上。 關於 [!DNL Marketo Measure] 欄位，請 [按一下這裡](/help/introduction-to-marketo-measure/overview-resources/glossary-of-marketo-measure-fields.md). 以視覺效果顯示 [!DNL Marketo Measure] 對象 [!DNL Marketo Measure] 請 [按一下這裡](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md).

## [!DNL Marketo Measure] 報表和控制面板 {#marketo-measure-reports-and-dashboards}

此 [!DNL Marketo Measure] 新增至 [!DNL Salesforce] 提供立即可用的報表和資料視覺效果功能。 這些是基本的 [!DNL Marketo Measure] 報表，讓您快速組織、分析和了解接觸點資料。
