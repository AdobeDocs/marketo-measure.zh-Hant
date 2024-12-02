---
unique-page-id: 37356132
description: Dynamics的[!DNL Marketo Measure]收入工作流程 —  [!DNL Marketo Measure]
title: Dynamics的[!DNL Marketo Measure]收入工作流程
exl-id: 0e64201a-bc65-4a6d-9192-09c14c810c4a
feature: Microsoft Dynamics
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 0%

---

# Dynamics的[!DNL Marketo Measure]收入工作流程 {#marketo-measure-revenue-workflows-for-dynamics}

## 第一部分：預估收入vs實際收入 {#part-estimated-revenue-vs-actual-revenue}

[!DNL Marketo Measure]指向一個立即可用的標準收入欄位（實際收入），但Dynamics有兩個標準收入欄位：「實際收入」和「預估收入」。 若要在Discover Dashboard中使用管道收入，需要自訂欄位和工作流程以從「預估收入」或「實際收入」欄位擷取正確的金額(視商機為「開啟」或「關閉（成功）」而定)。

步驟1：在Dynamics中建立自訂機會金額欄位

>[!NOTE]
>
>所有Dynamics收入欄位都有基本欄位和一般欄位。 忽略基本欄位。

步驟2：建立工作流程，以更新在步驟1建立的自訂機會金額欄位和[!DNL Marketo Measure]機會金額欄位。

>[!NOTE]
>
>我們無法指向使用Dynamics帳戶探索中的[!DNL Marketo Measure]機會金額(bizible2_bizible_opportunity_amount)欄位。 Dynamics客戶必須建立自訂機會金額欄位，[!DNL Marketo Measure]才能指向Discover。 完成之後，客戶必須建立工作流程，以更新&#x200B;**兩個** [!DNL Marketo Measure]機會金額(bizible2_bizible_opportunity_amount) **和**&#x200B;自訂機會金額欄位。 [!DNL Marketo Measure]機會金額欄位隨附在套件中，但必須建立自訂欄位。

金額工作流程指示：

**工作流程#1**：商機 — 更新[!DNL Marketo Measure]商機金額欄位和自訂欄位=預估收入

此工作流程會在每次預估收入變更並更新[!DNL Marketo Measure]機會金額欄位和您的自訂欄位以等於預估收入欄位時於未結機會上執行。 工作流程應設為「即時」執行，但也可「隨選」執行，以更新開啟的商機。

提供您[!DNL Marketo Measure]聯絡人自訂機會金額欄位的名稱。 他們更新「[!DNL Marketo Measure]應用程式商機設定」以包含自訂商機金額欄位的名稱。 這會告訴Discover要在報告中使用的欄位。

**工作流程#2**：商機 — 更新[!DNL Marketo Measure]商機金額欄位和自訂欄位=實際收入

此工作流程會在使用者關閉商機並更新[!DNL Marketo Measure]商機金額欄位和您的自訂欄位時起始，該欄位會在商機鎖定為已關閉之前將實際收入新增到商機關閉表單。

## 第2部分：預估關閉日期vs.實際關閉日期 {#part-estimated-close-date-vs-actual-close-date}

管道收入資料是現成可用的儀表板，因為依預設，Dynamics有兩個庫存結案日期欄位：預估結案日期和實際結案日期。 [!DNL Marketo Measure]在儀表板中只能指向一個關閉日期欄位，它指向實際關閉日期。

如果「實際關閉日期」欄位中沒有開啟商機的資料，則控制面板中沒有開啟商機的資料。 也就是說，需要根據機會階段的工作流程來支援這兩個日期欄位。

1. 在機會物件上建立自訂關閉日期欄位（[!DNL Marketo Measure]自訂關閉日期）。
1. 建立工作流程，以使用預估關閉日期或實際關閉日期的日期來更新[!DNL Marketo Measure]自訂關閉日期欄位，視商機是否開啟而定（工作流程應儲存為即時執行，但至少必須「依需求」執行一次，以更新所有目前開啟的商機）。
1. 測試工作流程並確認其運作正常。
1. 客戶向[!DNL Marketo Measure]提供自訂關閉日期API名稱。
1. [!DNL Marketo Measure]更新[!DNL Marketo Measure]應用程式設定，以指向控制面板中的[!DNL Marketo Measure]自訂關閉日期欄位。

   完成上述步驟後，請執行工作流程以更新您歷史機會上的「自訂[!DNL Marketo Measure]營業額」欄位和「[!DNL Marketo Measure]自訂結案日期」欄位，以反映正確的資料。 這可能會導致修改「 on/by」欄位變更，因此您應該與團隊確認，看看這是否會造成任何問題。

若要更新已關閉的商機……

1. 隔離自[!DNL Marketo Measure]開始日期起關閉的機會，直到工作流程作用中為止。 這是您必須透過工作流程更新的歷史機會群組。
1. 將所有記錄匯出至Excel。
1. 開啟Excel檔案，啟用內容。
1. 將實際關閉日期資料複製到[!DNL Marketo Measure]自訂關閉日期。
1. 將實際收入資料複製到[!DNL Marketo Measure]自訂機會金額&#x200B;**和** [!DNL Marketo Measure]機會金額（有兩個欄位）。
1. 儲存檔案。
1. 匯入檔案。 Dynamics會將其識別為具有要更新的現有記錄的檔案。
1. 檢查匯入檔案是否失敗。

>[!NOTE]
>
>本檔案概述的工作流程只是更新欄位的一種方式，這樣[!DNL Marketo Measure]就能在Discover中顯示正確的資料。 如果您有其他方法完成相同的工作，您可以繼續進行。 基本上，我們需要的是某種工作流程，能達成下列目標：
>
> * 如果Opp =開啟，請分別更新自訂結案日期欄位、自訂opp金額欄位和[!DNL Marketo Measure]個opp金額欄位以等於「預估結案日期」和「預估收入」。
> * 如果Opp = Closed Won，請將自訂結案日期欄位、自訂結案金額欄位及[!DNL Marketo Measure] Opp金額欄位分別更新為等於Actual Close Date與Actual Revenue。
