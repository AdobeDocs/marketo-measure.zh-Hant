---
unique-page-id: 18874779
description: 自訂歸因模型與設定 —  [!DNL Marketo Measure]  — 產品檔案
title: 自訂歸因模型與設定
exl-id: 7b156db2-9ac6-4d32-ac67-06c0aa15d651
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 0%

---

# 自訂歸因模型與設定 {#custom-attribution-model-and-setup}

請參閱下方的概觀 [!DNL Marketo Measure] 自訂歸因模型及其設定方法。

## 自訂歸因模型 {#custom-attribution-model}

此 [!DNL Marketo Measure] 自訂歸因模型可讓使用者選擇要納入模型中的接觸點或自訂階段。 使用者可以控制歸因於這些接觸點和階段的收入評分百分比，或者可以使用 [!DNL Marketo Measure] 機器學習模型。

## 如何設定自訂歸因模型 {#how-to-set-up-your-custom-attribution-model}

1. 決定要包含在自訂模型中的階段。

   若要開始建立自訂歸因模型，您需要選取哪些階段對您的行銷團隊來說很重要。 除了 [!DNL Marketo Measure] 里程碑階段(FT、LC、OC、Closed)您可以在自定義模型中添加多達六個附加的Lead/Contact狀態或Opportunity階段。 例如，MQL階段通常包含在自訂模型中。 行銷團隊通常想知道哪些工作或管道正在推動MQL階段的轉變。

   登入 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}. 前往 [!UICONTROL My Account] > [!UICONTROL Settings] >和「CRM」區段下，選取 **[!UICONTROL Stage Mapping]**.

   在此處，您需要通過選擇 **[!UICONTROL Include in Model]** 框。

   >[!NOTE]
   >
   >最多可允許6個自訂階段(不包括預設值：FT、LC、OC、閉門)。

   ![](assets/1-1.png)

   >[!NOTE]
   >
   >_全部_ 此處將顯示銷售機會/聯繫人和銷售機會階段，即使該階段處於非活動狀態或不再用於 [!DNL Salesforce]. 如果要刪除這些階段，則需要在 [!DNL Salesforce].

   選取階段後，請務必按一下 **[!UICONTROL Save & Process]** 按鈕。 階段現在會顯示在 **[!UICONTROL Attribution Settings]** 標籤，您將能為每個階段指派歸因百分比。 自訂階段也會顯示在行銷績效套裝中，作為需求瀑布圖中的銷售機會或商機階段。

   如果模型中有其它要包括的階段，但它們不在 [!UICONTROL Lead/Contact Status] 或 [!UICONTROL Opportunity Stage] 清單，您可以根據CRM中的欄位來定義自己的自訂階段。

   在以下範例中，使用日期欄位定義自訂的「MQL」階段。 此規則只說明，如果「MQL日期」欄位不為空，則應將其視為MQL，並應包含在自訂模型中。 請注意，建立自訂階段後，也必須對這些階段進行排序，以便它能跟隨銷售週期的發展。

   ![](assets/2-1.png)

   >[!CAUTION]
   >
   >別忘了啟用自訂欄位的歷史記錄追蹤。

如果您的自訂模型中使用自訂欄位，則必須在CRM中啟用欄位歷史記錄追蹤。 有關如何啟用欄位歷史記錄跟蹤的說明， [請按一下這裡](/help/advanced-marketo-measure-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md).

1. 決定自訂模型的歸因百分比。

   前往 **[!UICONTROL Attribution Settings]** in [!DNL Marketo Measure] 應用；自訂階段會顯示在歸因表格的這裡。 歸因表格會顯示 [!DNL Marketo Measure] 歸因模型，以及每個模型的歸因加權。 前五個模型的歸因百分比是固定的，無法變更。

   在最右側的欄中，標示為「**[!UICONTROL Custom]**，」您可以在自訂歸因模型中，為每個階段設定百分比加權。 只需在「自定義」列下輸入每個階段的值。 然後 **[!UICONTROL Save and Reprocess]** 完成後。

   「自訂」欄的左側是 **[!DNL Marketo Measure]機器學習模型**. 機器學習模型會根據贏取交易的相對重要性，根據每個自訂階段發生的情況，計算歸因加權。 有關機器學習模型的詳細資訊， [請按一下這裡](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md).

   ![](assets/3.png)

## 接觸點位置 {#touchpoint-positions}

儲存並處理歸因百分比後，接觸點將會更新並接收其新階段和位置。 最近發生的接觸點在階段轉變之前，會獲得該階段的評分（如下所示）。 自訂加權和收入也會重新分配。

![](assets/4.png)

## 漏斗階段和自訂模型階段之間的差異 {#the-difference-between-funnel-stages-and-custom-model-stages}

即使您未啟用自訂模型，您現在仍可在行銷漏斗中看到自訂階段。 這需透過使用漏斗階段功能。 漏斗階段現在可讓您將階段新增至漏斗，但無法查看其歸因。

漏斗階段仍會以接觸點的形式受到追蹤，且在CRM中仍會以接觸點的位置顯示。 若沒有自訂模型，如果有表單填入（中間接觸為10%），這些接觸點仍可能會收到中間接觸歸因，但如果只是網路造訪，則歸因評分為零。

如下所示，除了漏斗階段之外，我們還包括了盡職調查階段。 這表示我們會有位置包含「盡職」的接觸點，但只有在未啟用「自訂模型」（最多10%）時，這些接觸點才會獲得「中繼接觸」歸因評分。

![](assets/5.png)

>[!NOTE]
>
>BAT自訂模型的行為是，如果沒有中間接觸，則將自訂模型的中間接觸百分比平均分配給其他階段。
