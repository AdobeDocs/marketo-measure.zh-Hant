---
unique-page-id: 37356132
description: "[!DNL Marketo Measure] Dynamics的收入工作流程 —  [!DNL Marketo Measure]"
title: '"[!DNL Marketo Measure] Dynamics的收入工作流程」'
exl-id: 0e64201a-bc65-4a6d-9192-09c14c810c4a
feature: Microsoft Dynamics
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 0%

---

# [!DNL Marketo Measure] Dynamics的收入工作流程 {#marketo-measure-revenue-workflows-for-dynamics}

## 第一部分：預估收入vs實際收入 {#part-estimated-revenue-vs-actual-revenue}

[!DNL Marketo Measure] 指向一個立即可用的標準收入欄位（實際收入），但Dynamics有兩個標準收入欄位：「實際收入」和「預估收入」。 若要在Discover Dashboard中使用管道收入，需要自訂欄位和工作流程以從「預估收入」或「實際收入」欄位擷取正確的金額(視商機為「開啟」或「關閉（成功）」而定)。

步驟1：在Dynamics中建立自訂機會金額欄位

>[!NOTE]
>
>所有Dynamics收入欄位都有基本欄位和一般欄位。 忽略基本欄位。

步驟2：建立工作流程，以更新在步驟1建立的自訂機會金額欄位和 [!DNL Marketo Measure] 商機金額欄位。

>[!NOTE]
>
>我們無法指向 [!DNL Marketo Measure] Discover with Dynamics帳戶中的「機會金額」 (bizible2_bizible_opportunity_amount)欄位。 Dynamics客戶必須建立自訂機會金額欄位，用於 [!DNL Marketo Measure] 指向Discover。 完成後，客戶必須建立可更新的工作流程 **兩者** 此 [!DNL Marketo Measure] 機會金額(bizible2_bizible_opportunity_amount) **和** 自訂機會金額欄位。 此 [!DNL Marketo Measure] 套件隨附機會金額欄位，但必須建立自訂欄位。

金額工作流程指示：

**工作流程#1**：機會 — 更新 [!DNL Marketo Measure] 機會金額欄位與自訂欄位=預估收入

此工作流程會在每次「預估收入」變更並更新 [!DNL Marketo Measure] 機會金額欄位和您的自訂欄位等於「預估收入」欄位。 工作流程應設為「即時」執行，但也可「隨選」執行，以更新開啟的商機。

提供您的 [!DNL Marketo Measure] 具有自訂機會數量欄位名稱的聯絡點。 他們更新 [!DNL Marketo Measure] 應用程式機會設定以包含自訂機會數量欄位的名稱。 這會告訴Discover要在報告中使用的欄位。

**工作流程#2**：機會 — 更新 [!DNL Marketo Measure] 機會金額欄位與自訂欄位=實際收入

此工作流程會在使用者關閉機會並更新 [!DNL Marketo Measure] 商機金額欄位和您的自訂欄位，其中實際收入已新增到商機關閉表單，然後商機將鎖定為已關閉。

## 第2部分：預估關閉日期vs.實際關閉日期 {#part-estimated-close-date-vs-actual-close-date}

管道收入資料是現成可用的儀表板，因為依預設，Dynamics有兩個庫存結案日期欄位：預估結案日期和實際結案日期。 [!DNL Marketo Measure] 只能指向控制面板中的一個關閉日期欄位，且它指向實際關閉日期。

如果「實際關閉日期」欄位中沒有開啟商機的資料，則控制面板中沒有開啟商機的資料。 也就是說，需要根據機會階段的工作流程來支援這兩個日期欄位。

1. 在機會物件上建立自訂關閉日期欄位([!DNL Marketo Measure] 自訂關閉日期)。
1. 建立工作流程以更新 [!DNL Marketo Measure] 「自訂關閉日期」欄位，其日期為「預估關閉日期」或「實際關閉日期」，視商機是否開啟而定（工作流程應儲存為即時執行，但至少必須「依需求」執行一次，以更新所有目前開啟的商機）。
1. 測試工作流程並確認其運作正常。
1. 要提供自訂關閉日期API名稱的客戶 [!DNL Marketo Measure].
1. [!DNL Marketo Measure] 更新 [!DNL Marketo Measure] 指向的應用程式設定 [!DNL Marketo Measure] 儀表板中的自訂關閉日期欄位。

   完成上述步驟後，執行工作流程以更新兩個自訂 [!DNL Marketo Measure] 「應付金額」欄位與 [!DNL Marketo Measure] 自訂關閉日期您歷史機會上的欄位以反映正確的資料。 這可能會導致修改「 on/by」欄位變更，因此您應該與團隊確認，看看這是否會造成任何問題。

若要更新已關閉的商機……

1. 隔離自「 」之後關閉的機會 [!DNL Marketo Measure] 開始日期直到工作流程作用中為止。 這是您必須透過工作流程更新的歷史機會群組。
1. 將所有記錄匯出至Excel。
1. 開啟Excel檔案，啟用內容。
1. 複製實際關閉日期資料至 [!DNL Marketo Measure] 自訂關閉日期。
1. 將實際收入資料複製到 [!DNL Marketo Measure] 自訂機會金額 **和** [!DNL Marketo Measure] 機會金額（有兩個欄位）。
1. 儲存檔案。
1. 匯入檔案。 Dynamics會將其識別為具有要更新的現有記錄的檔案。
1. 檢查匯入檔案是否失敗。

>[!NOTE]
>
>本檔案中概述的工作流程只是更新欄位的一種方法，因此 [!DNL Marketo Measure] 可以在探索中顯示正確的資料。 如果您有其他方法完成相同的工作，您可以繼續進行。 基本上，我們需要的是某種工作流程，能達成下列目標：
>
> * 如果Opp =開啟，請更新自訂結案日期欄位、自訂交易金額欄位，以及 [!DNL Marketo Measure] 「營業額」欄位分別等於「預估關閉日期」和「預估收入」。
> * 如果Opp = Closed Won，請更新自訂結案日期欄位、自訂Opp金額欄位，以及 [!DNL Marketo Measure] 「營業額」欄位分別等於「實際結束日期」與「實際收入」。
