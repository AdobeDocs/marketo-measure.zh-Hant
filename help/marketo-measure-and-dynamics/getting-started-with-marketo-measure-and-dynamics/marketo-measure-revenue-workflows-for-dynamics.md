---
unique-page-id: 37356132
description: '"[!DNL Marketo Measure] Dynamics的收入工作流程 —  [!DNL Marketo Measure]  — 產品檔案」'
title: '"[!DNL Marketo Measure] Dynamics的收入工作流程」'
exl-id: 0e64201a-bc65-4a6d-9192-09c14c810c4a
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 0%

---

# [!DNL Marketo Measure] Dynamics的收入工作流程 {#marketo-measure-revenue-workflows-for-dynamics}

## 第1部分：預估收入與實際收入 {#part-estimated-revenue-vs-actual-revenue}

[!DNL Marketo Measure] 指向一個現成的標準收入欄位（實際收入），但Dynamics有兩個標準收入欄位：實際收入和估計收入。 要在Discover Dashboard中提供管道收入，需要一個自定義欄位和一個工作流，以根據Opportunity是Open還是Closed(Won)從Estimated Revenue或Actual Revenue欄位中獲取正確的金額。

步驟1:在Dynamics中建立自定義業務機會金額欄位

>[!NOTE]
>
>所有Dynamics收入欄位都有一個基本欄位和一個常規欄位。 忽略基欄位。

步驟2:建立一個工作流，該工作流更新了在步驟1中建立的自定義業務機會金額欄位和 [!DNL Marketo Measure] 機會金額欄位。

>[!NOTE]
>
>我們不能指向 [!DNL Marketo Measure] Discover中的Opportunity Amount(bizible2_bizible_opportunity_amount)欄位（具有Dynamics帳戶）。 Dynamics客戶必須為 [!DNL Marketo Measure] 指向Discover。 完成後，客戶需要建立更新的工作流程 **both** the [!DNL Marketo Measure] Opportunity Amount(bizible2_bizible_opportunity_amount) **和** 「自定義機會金額」欄位。 此 [!DNL Marketo Measure] Opportunity Amount欄位隨包一起提供，但必須建立自定義欄位。

金額工作流說明：

**工作流程#1**:機會 — 更新 [!DNL Marketo Measure] 業務機會金額欄位和自定義欄位=估計收入

此工作流在每次「估計收入」更改時開啟的業務機會上運行，並將更新 [!DNL Marketo Measure] Opportunity Amount欄位和自定義欄位等於Estimated Revenue欄位。 工作流應設定為運行「即時」，但也可以按需運行，以更新未結的Opportunity。

提供您的 [!DNL Marketo Measure] 聯繫點，其名稱為自定義機會金額欄位。 他們會更新 [!DNL Marketo Measure] App Opportunity設定，以包括自定義機會金額欄位的名稱。 這會告訴Discover報表中要使用的欄位。

**工作流程#2**:機會 — 更新 [!DNL Marketo Measure] 業務機會金額欄位和自定義欄位=實際收入

此工作流程會即時執行。 當用戶關閉Opportunity時啟動，並將更新 [!DNL Marketo Measure] Opportunity Amount欄位和您的自定義欄位，在Opportunity鎖定為已關閉之前， Actual Revenue添加到Opportunity Close表單中。

## 第2部分：預計關閉日期與實際關閉日期的比較 {#part-estimated-close-date-vs-actual-close-date}

現成可用的管道收入資料將無法在控制面板中使用，因為依預設，Dynamics有兩個庫存關閉日期欄位：預計關閉日期和實際關閉日期。 [!DNL Marketo Measure] 只能指向儀表板中的一個關閉日期欄位，而且我們當前指向的是實際關閉日期。

如果「實際關閉日期」欄位中沒有資料，則在控制面板中不會看到任何資料顯示未結業務機會。 也就是說，需要基於機會階段的工作流來支援兩個日期欄位。

1. 在Opportunity對象上建立自定義關閉日期欄位(即 [!DNL Marketo Measure] 自訂關閉日期)。
1. 建立工作流程以更新 [!DNL Marketo Measure] 根據業務機會是開啟還是關閉（應保存工作流以即時運行，但至少需要運行一次「按需」以更新所有當前開啟的Op），使用「估計關閉日期」或「實際關閉日期」的日期的自定義關閉日期欄位。
1. 測試工作流程並確認其運作。
1. 客戶：提供自訂關閉日期API名稱給 [!DNL Marketo Measure].
1. [!DNL Marketo Measure] 更新 [!DNL Marketo Measure] 指向的應用程式設定 [!DNL Marketo Measure] 控制面板中的「自訂關閉日期」欄位。

   完成上述步驟後，我們需要執行工作流程來更新兩個自訂 [!DNL Marketo Measure] Opp Amount欄位和 [!DNL Marketo Measure] 關於您的歷史機會的「自定義關閉日期」欄位，以反映正確的資料。 這可能會變更修改的「開啟/按」欄位，因此您會想要洽詢您的團隊，以查看這是否會出現任何問題。

要更新已關閉的業務機會……

1. 隔離自您 [!DNL Marketo Measure] 啟動日期，直到工作流處於活動狀態。 這是您需要通過工作流更新的一組歷史業務機會。
1. 將所有記錄匯出至Excel。
1. 開啟Excel檔案，啟用內容。
1. 將實際關閉日期資料複製到 [!DNL Marketo Measure] 自訂關閉日期。
1. 將實際收入資料複製到 [!DNL Marketo Measure] 自定義機會量 **和** [!DNL Marketo Measure] 機會金額（有兩個欄位。）
1. 儲存檔案。
1. 匯入檔案。 Dynamics會將此檔案識別為具有現有記錄的檔案，以便更新。
1. 檢查導入檔案的失敗。

>[!NOTE]
>
>本檔案中概述的工作流程只是更新欄位的其中一種方式 [!DNL Marketo Measure] 可在Discover中顯示正確的資料。 如果您有其他方法來完成相同的任務，則可以執行該任務。 基本上，我們需要從這些工作流程中完成以下工作：
>
> * 如果Opp =開啟，請更新自訂關閉日期欄位、自訂op量欄位，以及 [!DNL Marketo Measure] opp金額欄位分別等於「估計關閉日期」和「估計收入」。
> * 如果Opp =關閉Won，請更新自訂關閉日期欄位、自訂Opp金額欄位，以及 [!DNL Marketo Measure] opp金額欄位分別等於實際關閉日期和實際收入。

