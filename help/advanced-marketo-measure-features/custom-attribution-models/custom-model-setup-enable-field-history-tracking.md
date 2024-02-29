---
unique-page-id: 18874777
description: 自訂模型設定 — 啟用欄位歷史記錄追蹤 —  [!DNL Marketo Measure]
title: 自訂模型設定 — 啟用欄位歷史記錄追蹤
exl-id: 70328e67-051b-4864-891b-b251e49859c2
feature: Custom Models
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 0%

---

# 自訂模型設定：啟用欄位歷史記錄追蹤 {#custom-model-setup-enable-field-history-tracking}

## 啟用欄位記錄追蹤的原因與時機 {#why-and-when-to-enable-field-history-tracking}

如果您決定在自訂歸因模型中納入自訂欄位作為階段，則欄位歷史記錄追蹤 **必須啟用** 用於此欄位。 啟用欄位歷史記錄追蹤將允許 [!DNL Salesforce] 若要追蹤自訂欄位，只要在「歷程記錄追蹤」表格中建立記錄，即可進行編輯。 [!DNL Marketo Measure] 可以下載該表格，並使用此資訊來測量「轉換」發生的時間和日期。 若無欄位歷史記錄追蹤， [!DNL Marketo Measure] 無法追蹤與此欄位相關的變更。

若僅限 [!UICONTROL Lead Status] 或者，自訂模型中會使用「機會階段」，則不需要開啟「欄位歷史記錄」追蹤，因為它會在階段轉換時自動追蹤。

若要啟用欄位歷史記錄追蹤，請遵循下列指示。

## 啟用欄位記錄追蹤 {#enable-field-history-tracking}

>[!NOTE]
>
>您必須是系統管理員才能對Lead/Contact/Opportunity物件上的欄位進行這些變更。

1. 前往自訂欄位所在的物件，然後按一下 **[!UICONTROL Set History Tracking]** 按鈕。

   ![](assets/1.png)

1. 選取您要追蹤變更的欄位。

   ![](assets/2.png)

[!DNL Marketo Measure] 僅當記錄最近被修改時，才能重新匯入記錄。 從技術上講，公式欄位在記錄變更時不會修改記錄，因為它在背景進行計算。 我們曾看到因下列原因而略過規則的問題 [!DNL Marketo Measure] 未看到記錄變更，因此建議 **未在規則定義中使用公式欄位**. 解決方案是建立文字欄位，並使用工作流程在編輯記錄或符合條件時，以適當的值或計算填入該欄位。 這需要編輯所有記錄，以便工作流程可以在舊記錄上追溯工作。
