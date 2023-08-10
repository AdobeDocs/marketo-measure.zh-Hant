---
unique-page-id: 18874556
description: '"[!DNL Marketo Measure] 維護 —  [!DNL Marketo Measure]  — 產品檔案」'
title: '"[!DNL Marketo Measure] 維護」'
exl-id: 4e1d53bb-0af8-4774-9f69-6a95516b3d11
feature: Tracking
source-git-commit: 3df1bd288ebd65f75a2ed52d7c8a6faf50c7ff1f
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 0%

---

# [!DNL Marketo Measure] 維護 {#marketo-measure-maintenance}

[!DNL Marketo Measure] 幾乎每天都會從您的CRM提取所需的一切，但您會想要定期排程保留一些維護任務 [!DNL Marketo Measure] 哼著唱並輸出最精確的資訊。

**同步處理新離線行銷活動的購買者接觸點（2x/月）**

正如您在入門期間所學的， [!DNL Marketo Measure] 與您的CRM行銷活動同步，以取得離線行銷工作的相關資訊。 當您的組織開始新的行銷活動時，請務必適當地為每個行銷活動啟用購買者接觸點。 簽出 [本文](/help/channel-tracking-and-setup/offline-channels/deprecated-processes/syncing-offline-campaigns.md)以取得詳細資訊。

**上傳所有管道的支出（1x/月）**

若要充分利用以下專案的完整收入和ROI報告功能[!DNL Marketo Measure]，您必須告訴 [!DNL Marketo Measure] 您在每個行銷管道和子管道的花費金額。 我們建議您指定每個管道/子管道的擁有者，並讓這些人員向每月負責上傳新成本資訊的單一方報告支出。

閱讀以下內容，重新整理記憶體以掌握如何上傳成本資訊 [本文](/help/marketing-spend/spend-management/marketing-channel-costs.md).

**更新要追蹤的網域清單（1x/月）**

Marketo Measure會追蹤我們的Javascript作用中的所有頁面和子網域，但僅限於我們知道的網域。 如果您最近推出新網域、在國際上擴充或變更主要網域，請聯絡 [Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} 以確保我們更新您的帳戶。

**檢閱自訂管道對應的準確性（1x/月）**

在上線期間，您可以為線上和離線行銷工作設定自訂管道對應。 隨著您的行銷策略和Marketo Measure的使用演變，您將需要注意該對應邏輯，以確保所有接觸點都經過適當分類。

請記住， [!DNL Marketo Measure] 編輯對應邏輯時會重新處理資料，因此您無法每7天變更這些規則一次。

參考 [本文](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md) 進行線上設定時， [本文](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md) 離線設定方面，以及這份由客戶所組織的最佳實務清單：

* 檢閱目前落入您可能已設定的任何「其他」或「NULL」管道的接觸點。 如果適用，請更新您的對應邏輯，將這些接觸點重新分類為更精確的管道。
* 檢閱目前屬於您的「直接」管道的接觸點。 如果您的部分電子郵件行銷活動或其他工作遺失UTM引數，流量很可能會不適當地分組到直接頻道中。 請考慮更新UTM引數以擷取反向連結來源。

**評估接觸點隱藏設定（1x/季）**

如果您看到許多您不希望在歸因故事中考慮的接觸點(來自 [!DNL Login] 或 [!DNL Unsubscribe forms]、工作機會頁面或內部應用程式等)，您可能會想要評估現有的接觸點隱藏設定。 每季會找出任何產生不必要雜訊的接觸點群組，並適當地更新您的抑制邏輯。 [以下是一篇實用的文章](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)  和操作說明。

**檢閱自訂階段對應的準確性（1x/季） （如果適用）**

如果您使用任何自訂 [!UICONTROL Lead]， [!UICONTROL Contact]，或 [!UICONTROL Opportunities] 階段，您也可能已自訂這些階段對應的管道部分，以及這些階段是否包含在自訂歸因模型中。 每季一次，造訪 [本文](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md) 重新整理自訂階段對應上的記憶體，並確保您準確追蹤自訂階段。

**比較機器學習模型與自訂模型加權（1x/季） （若適用）**

如果您已獲得授權 [!DNL Marketo Measure] 自訂模型，您也有來自機器學習模型(MLM)的可用資料，位於 [!UICONTROL Settings] > [!UICONTROL Attribution Settings]. MLM會使用您帳戶的接觸點資料來計算每個階段的重要性，並可協助您決定如何在自訂模型中分配歸因權重。 我們建議每季將MLM與您的自訂模型比較一次，並與您的SM討論對您的自訂模型可能進行變更的影響。

如需關於的詳細資訊 [!DNL Marketo Measure] 機器學習模型，簽出 [本文](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md).
