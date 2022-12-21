---
unique-page-id: 18874777
description: 自訂模型設定 — 啟用欄位歷史記錄追蹤 —  [!DNL Marketo Measure]  — 產品檔案
title: 自訂模型設定 — 啟用欄位歷史記錄追蹤
exl-id: 70328e67-051b-4864-891b-b251e49859c2
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 0%

---

# 自訂模型設定：啟用欄位歷史記錄追蹤 {#custom-model-setup-enable-field-history-tracking}

## 啟用欄位歷史記錄追蹤的原因和時機 {#why-and-when-to-enable-field-history-tracking}

如果您決定將自訂欄位納入自訂歸因模型中，作為階段，欄位歷史記錄追蹤 **必須啟用** 欄位。 啟用欄位歷史記錄追蹤將允許 [!DNL Salesforce] 若要在「歷史記錄追蹤」表格中建立記錄，以追蹤任何編輯自訂欄位的時間。 [!DNL Marketo Measure] 可以下載該表格，並使用此資訊來測量發生「轉變」的時間和日期。 沒有欄位歷史記錄追蹤， [!DNL Marketo Measure] 無法追蹤與此欄位相關的變更。

如果 [!UICONTROL Lead Status] 或者，在自定義模型中使用了機會階段，無需開啟欄位歷史記錄跟蹤，因為它將作為階段轉變自動跟蹤。

若要啟用欄位歷史記錄追蹤，請遵循下列指示。

## 啟用欄位歷史記錄追蹤 {#enable-field-history-tracking}

>[!NOTE]
>
>您需要是系統管理員，才能對Lead/Contact/Opportunity對象上的欄位進行這些更改。

1. 前往自訂欄位所在的物件，然後按一下 **[!UICONTROL Set History Tracking]** 按鈕。

   ![](assets/1.png)

1. 選取您要追蹤變更的欄位。

   ![](assets/2.png)

[!DNL Marketo Measure] 只有在發現記錄最近已被修改時，才能重新導入記錄。 公式欄位在技術上不會修改記錄，因為它會在背景進行計算。 我們已看到規則被略過的問題，因為 [!DNL Marketo Measure] 未看到記錄更改，因此建議 **未在規則定義中使用公式欄位**. 解決方案是建立文字欄位，並使用工作流程來在每次編輯記錄或符合條件時，為該欄位填入適當的值或計算。 這要求編輯所有記錄，以便工作流程可以對舊記錄進行回溯運作。
