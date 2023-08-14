---
unique-page-id: 18874793
description: 使用自訂收入金額欄位 —  [!DNL Marketo Measure]  — 產品檔案
title: 使用自訂收入金額欄位
exl-id: 517ea4f9-aa83-48d0-8ce7-003f4a907430
feature: Custom Revenue Amount
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---

# 使用自訂收入金額欄位 {#using-a-custom-revenue-amount-field}

依預設，「購買者歸因接觸點」會從下列兩個欄位之一提取「商機金額」：

* 金額（SFDC預設值）
* [!DNL Marketo Measure] 機會金額（自訂）

如果您在您的「商機」上使用自訂「金額」欄位，我們將需要設定工作流程以計算「購買者接觸點收入」。 這需要一些更進階的知識 [!DNL Salesforce]，因此可能需要SFDC管理員的協助。

開始之前，我們需要以下資訊：

* 金額欄位的API名稱

從這裡，我們將開始建立工作流程。

1. 瀏覽至 **[!UICONTROL Setup]** > **[!UICONTROL Create]** > **[!UICONTROL Workflow & Approvals]** > **[!UICONTROL Workflow Rules]**.

   ![](assets/1.jpg)

1. 選取 **[!UICONTROL New Rule]**，將物件設為「Opportunity」並按一下 **[!UICONTROL Next]**.

   ![](assets/2.jpg)

   ![](assets/3.jpg)

1. 設定工作流程。 將規則名稱設為「更新」 [!DNL Marketo Measure] 機會金額。」 將評估條件設為「已建立，且每次都進行編輯」。 在「規則條件」中，選取自訂「金額」欄位並選取「運運算元」 [!UICONTROL as "Not Equal To"] 並保留「值」欄位空白。

   ![](assets/4.jpg)

1. 新增工作流程動作。 將此挑選清單設為&quot;[!UICONTROL New Field Update].」

   ![](assets/5.jpg)

1. 您將在這裡填寫欄位資訊。 在「名稱」欄位中，我們建議使用此命名： &quot;[!DNL Marketo Measure] Opp金額。」 「唯一名稱」將會根據「名稱」欄位自動填入。 在「要更新的欄位」選擇清單中，選擇「[!DNL Marketo Measure] 機會金額。」 選取欄位後，選取「欄位變更後重新評估工作流程規則」方塊。 在「指定新欄位值」中，選取「使用公式來設定新值」。 在空白方塊中，拖放自訂金額欄位的API名稱。 按一下 **[!UICONTROL Save]**.

   ![](assets/6.png)

1. 系統會將您帶回工作流程的彙總頁面，請確定「啟動」，然後您就可以開始使用了。 若要啟動，請按一下 **編輯** ，然後按一下 **啟動**.

   完成這些步驟後，將必須更新機會，才能觸發工作流程以從取得新值 [!UICONTROL custom opportunity] 欄位。

   您可以透過SFDC內的Data Loader執行您的機會，來達成此目標。 請尋找在中使用資料載入器的詳細資訊 [本文](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md).

如果過程中有任何問題，請隨時聯絡Adobe客戶團隊（您的客戶經理）或 [[!DNL Marketo] 支援](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
