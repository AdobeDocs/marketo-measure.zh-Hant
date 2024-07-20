---
unique-page-id: 18874779
description: 自訂歸因模型與設定 —  [!DNL Marketo Measure]
title: 自訂歸因模型與設定
exl-id: 7b156db2-9ac6-4d32-ac67-06c0aa15d651
feature: Attribution, Custom Models
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '822'
ht-degree: 0%

---

# 自訂歸因模型與設定 {#custom-attribution-model-and-setup}

請參閱下方的[!DNL Marketo Measure]自訂歸因模型概觀以及如何設定。

## 自訂歸因模型 {#custom-attribution-model}

[!DNL Marketo Measure]自訂歸因模型可讓使用者選擇要納入模型中的接觸點或自訂階段。 使用者可以控制歸因到這些接觸點和階段的收入點數百分比，或者使用[!DNL Marketo Measure]機器學習模型建議的歸因百分比值。

## 如何設定自訂歸因模型 {#how-to-set-up-your-custom-attribution-model}

1. 決定您要在自訂模型中包含哪些階段。

   若要開始建立自訂歸因模型，您必須選取對行銷團隊重要的階段。 除了[!DNL Marketo Measure]個里程碑階段（FT、LC、OC、已關閉）之外，您最多可以在自訂模型中新增六個額外的銷售機會/聯絡人狀態或銷售機會階段。 例如，MQL階段通常包含在自訂模型中。 行銷團隊經常想知道哪些努力或管道正在推動轉換至MQL階段。

   登入[experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}。 前往「[!UICONTROL My Account] > [!UICONTROL Settings]」，並在CRM區段下選取「**[!UICONTROL Stage Mapping]**」。

   接著，選取&#x200B;**[!UICONTROL Include in Model]**&#x200B;方塊，選擇要包含的Lead/Contacts和Opportunity階段。

   >[!NOTE]
   >
   >您最多允許六個自訂階段（不包括預設值：FT、LC、OC、已關閉）。

   ![](assets/1-1.png)

   >[!NOTE]
   >
   >_所有_&#x200B;銷售機會/聯絡人及商機階段將會顯示在這裡，即使該階段已停用或不再用於[!DNL Salesforce]。 若要移除這些階段，您需要在[!DNL Salesforce]中將其硬刪除。

   當您選取階段時，請務必按一下頁面底部的&#x200B;**[!UICONTROL Save & Process]**&#x200B;按鈕。 這些階段現在會顯示在&#x200B;**[!UICONTROL Attribution Settings]**&#x200B;標籤中，而您將能夠指派歸因百分比給每個階段。 自訂階段也會在「行銷績效套裝」中顯示為「需求瀑布」中的「銷售機會」或「銷售機會」階段。

   如果還有其他階段要納入模型中，但它們不在[!UICONTROL Lead/Contact Status]或[!UICONTROL Opportunity Stage]清單中，您可以根據CRM中的欄位定義自己的自訂階段。

   在以下範例中，使用日期欄位定義自訂「MQL」階段。 此規則只會指出，如果「MQL日期」欄位不是空白，則應將其視為MQL並應包含在自訂模型中。 自訂階段建立後，對自訂階段進行排序也很重要，以便追蹤銷售週期的進度。

   ![](assets/2-1.png)

   >[!CAUTION]
   >
   >別忘了啟用自訂欄位的歷程記錄追蹤。

如果您的自訂模型中使用了自訂欄位，則必須在CRM中啟用欄位歷史記錄追蹤。 如需啟用欄位記錄追蹤的指示，請參閱[自訂模型設定：啟用欄位記錄追蹤](/help/advanced-marketo-measure-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md)。

1. 決定自訂模型的歸因百分比。

   移至[!DNL Marketo Measure]應用程式中的&#x200B;**[!UICONTROL Attribution Settings]**；自訂階段會出現在歸因表格中。 歸因表格會顯示所有[!DNL Marketo Measure]個歸因模型，以及每個模型的歸因加權。 前五個模型的歸因百分比是固定的，無法變更。

   在標示為「**[!UICONTROL Custom]**」的最右欄中，您可以為自訂歸因模型中的各個階段設定百分比加權。 在自訂欄下輸入每個階段的值，完成時按一下&#x200B;**[!UICONTROL Save and Reprocess]**。

   _自訂_&#x200B;欄的左側是&#x200B;**[!DNL Marketo Measure]機器學習模型**。 「機器學習」模型會根據贏得交易的相對重要性（取決於每個自訂階段所發生的情況），計算歸因加權。 如需機器學習模型的詳細資訊，請參閱[機器學習模型常見問題集](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md)。

   ![](assets/3.png)

## 接觸點位置 {#touchpoint-positions}

在儲存及處理歸因百分比後，接觸點將會更新並接收其新階段和位置。 階段轉換之前最近發生的接觸點將獲得該階段的評分（如下所示）。 自訂權重和收入也會重新分配。

![](assets/4.png)

## 漏斗階段和自訂模型階段之間的差異 {#the-difference-between-funnel-stages-and-custom-model-stages}

現在，即使您未啟用自訂模型，仍可在行銷漏斗中看到自訂階段。 這將透過使用我們的「漏斗階段」功能來實現。 漏斗階段現在可讓您將階段新增至漏斗，但看不到其歸因。

漏斗階段仍會以接觸點形式受到追蹤，且仍會顯示為您CRM中的接觸點位置。 如果沒有自訂模型，只要有表單填滿（10%為中間接觸），這些接觸點仍可能獲得中間接觸歸因，但若只是網頁造訪，則歸因點數為零。

如以下所示，我們將「盡職調查」階段列為漏斗階段的一部分。 這表示我們有此位置包含「盡職調查」的接觸點，但若未啟用「自訂模型」（最多10%），這些接觸點將只會獲得中間接觸歸因評分。

![](assets/5.png)

>[!NOTE]
>
>BAT自訂模型的行為是將自訂模型的中間接觸百分比平均分配給其他階段，前提是沒有中間接觸。
