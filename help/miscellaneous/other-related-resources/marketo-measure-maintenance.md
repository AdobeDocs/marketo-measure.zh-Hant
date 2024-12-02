---
unique-page-id: 18874556
description: '[!DNL Marketo Measure]維護 —  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure]維護'
exl-id: 4e1d53bb-0af8-4774-9f69-6a95516b3d11
feature: Tracking
source-git-commit: fca2db86611d16f4e74467405521a89dd5d825ab
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# [!DNL Marketo Measure]維護 {#marketo-measure-maintenance}

[!DNL Marketo Measure]幾乎每天都會從您的CRM提取所需的一切，但您應定期排程一些維護任務，以使[!DNL Marketo Measure]保持運轉並輸出儘可能準確的資訊。

**同步處理新離線行銷活動的購買者接觸點（2x/月）**

如您在上線期間所瞭解，[!DNL Marketo Measure]會透過與您的CRM行銷活動同步來取得您的離線行銷工作的相關資訊。 當您的組織開始新的行銷活動時，請務必適當地為每個行銷活動啟用購買者接觸點。

**上傳所有頻道的支出（1x/月）**

若要充分利用[!DNL Marketo Measure]的完整收入和ROI報告功能，您必須告訴[!DNL Marketo Measure]您在每個行銷管道和子管道上的花費金額。 指定每個管道/子管道的擁有者，並讓這些人員向每月負責上傳新成本資訊的單一方報告支出。

閱讀[本文章](/help/marketing-spend/spend-management/marketing-channel-costs.md)，重新整理您關於如何上傳成本資訊的記憶體。

**更新要追蹤的網域清單（1x/月）**

Marketo Measure會追蹤我們的Javascript作用中的所有頁面和子網域，但僅限於我們知道的網域。 如果您最近剛推出新網域、進行國際擴充，或變更主要網域，請連絡[Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}，確保我們相應地更新您的帳戶。

**檢閱自訂管道對應是否準確（1x/月）**

在上線期間，您可以為線上和離線行銷工作設定自訂管道對應。 隨著您的行銷策略和Marketo Measure使用方式的演變，您想要留意該對應邏輯，以確保所有接觸點都經過適當分類。

請記住，當您編輯對應邏輯時，[!DNL Marketo Measure]會重新處理您的資料，因此您將無法每七天多次變更這些規則。

請參考[這篇文章](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)以進行線上設定，[這篇文章](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)以進行離線設定，以及這份由我們的客戶所組織的最佳實務清單：

* 檢閱目前落入您可能已設定的任何「其他」或「NULL」管道的接觸點。 如果適用，請更新您的對應邏輯，將這些接觸點重新分類為更精確的管道。
* 檢閱目前屬於您的「直接」管道的接觸點。 如果您的部分電子郵件行銷活動或其他工作遺失UTM引數，流量很可能會不適當地分組到直接頻道中。 請考慮更新UTM引數以擷取反向連結來源。

**評估接觸點隱藏設定（1x/季）**

如果您在歸因故事中看到許多您不想要的接觸點（例如[!DNL Login]或[!DNL Unsubscribe forms]、Careers頁面或內部應用程式中的接觸點），建議您評估現有的接觸點隱藏設定。 每季會找出任何產生不必要雜訊的接觸點群組，並適當地更新您的抑制邏輯。 [以下是實用的文章](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)及操作說明。

**檢閱自訂階段對應是否準確（1x/季） （如果適用）**

如果您使用任何自訂[!UICONTROL Lead]、[!UICONTROL Contact]或[!UICONTROL Opportunities]階段，您可能也已自訂這些階段對應的管道部分，以及這些階段是否包含在自訂歸因模型中。 每季一次，請造訪[本文章](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md)以重新整理自訂階段對應的記憶體，並確保您準確追蹤自訂階段。

**比較機器學習模型與自訂模型加權（1x/季） （若適用）**

如果您已獲得[!DNL Marketo Measure]自訂模型的授權，您也會在[!UICONTROL Settings] > [!UICONTROL Attribution Settings]中取得我們的機器學習模型(MLM)所提供的資料。 MLM會使用您帳戶的接觸點資料來計算每個階段的重要性，並可協助您決定如何在自訂模型中分配歸因權重。 我們建議每季將MLM與您的自訂模型比較一次，並與您的SM討論對您的自訂模型可能進行變更的影響。

如需[!DNL Marketo Measure]機器學習模型的詳細資訊，請參閱[本文章](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md)。
