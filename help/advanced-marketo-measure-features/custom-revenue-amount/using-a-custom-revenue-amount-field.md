---
unique-page-id: 18874793
description: 使用自訂收入金額欄位 —  [!DNL Marketo Measure]  — 產品檔案
title: 使用自訂收入金額欄位
exl-id: 517ea4f9-aa83-48d0-8ce7-003f4a907430
source-git-commit: 51397a02872035fef41d308c1f855bcaecc29c4e
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---

# 使用自訂收入金額欄位 {#using-a-custom-revenue-amount-field}

預設情況下，「購買者歸因接觸點」將從以下兩個欄位之一提取「機會金額」：

* 金額（SFDC預設值）
* [!DNL Marketo Measure] 機會金額（自定義）

如果您在Opportunity上使用自訂金額欄位，我們需要設定工作流程，以計算購買者接觸點收入。 這需要一些更進階的 [!DNL Salesforce]，因此可能需要您的SFDC管理員的協助。

從頭開始，我們需要以下資訊：

* 「金額」欄位的API名稱

從這裡開始，我們將開始建立工作流程。

1. 導覽至 **[!UICONTROL Setup]** > **[!UICONTROL Create]** > **[!UICONTROL Workflow & Approvals]** > **[!UICONTROL Workflow Rules]**.

   ![](assets/1.jpg)

1. 選擇 **[!UICONTROL New Rule]**，將對象設定為「Opportunity」，然後按一下 **[!UICONTROL Next]**.

   ![](assets/2.jpg)

   ![](assets/3.jpg)

1. 設定工作流程。 將規則名稱設定為「更新」 [!DNL Marketo Measure] 機會金額。」 將評估標準設定為「已建立，且每次編輯。」 對於「規則條件」，選取您的自訂金額欄位並選取運算子 [!UICONTROL as "Not Equal To"] 並將「值」欄位留空。

   ![](assets/4.jpg)

1. 新增工作流程動作。 將此選擇清單設定為「[!UICONTROL New Field Update].&quot;

   ![](assets/5.jpg)

1. 在這裡，你將填寫欄位資訊。 在「名稱」欄位中，建議使用此命名：&quot;[!DNL Marketo Measure] Opp金額。」 「唯一名稱」將根據「名稱」欄位自動填入。 在「要更新的欄位」選擇清單中，選擇「[!DNL Marketo Measure] 機會金額。」 選取欄位後，選取「欄位變更後重新評估工作流程規則」方塊。 在「指定新欄位值」中，選擇「使用公式來設定新值」。 在空白方塊中，拖放自訂「金額」欄位的API名稱。 按一下 **[!UICONTROL Save]**.

   ![](assets/6.png)

1. 系統會將您帶回工作流程的統計頁面，請務必「啟用」，您就可以開始使用。 若要啟用，請按一下 **編輯** 在新工作流程旁邊，然後按一下 **啟動**.

   完成這些步驟後，需要更新機會，以觸發工作流程，從 [!UICONTROL custom opportunity] 欄位。

   通過SFDC內的Data Loader運行您的機會可以實現這一點。 有關使用資料載入器的詳細資訊，請參閱 [這篇文章](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md).

若途中有任何疑問，請立即聯絡Adobe客戶團隊（您的客戶經理）或 [[!DNL Marketo] 支援](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
