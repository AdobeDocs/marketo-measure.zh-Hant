---
unique-page-id: 18874556
description: '"[!DNL Marketo Measure] 維護 —  [!DNL Marketo Measure]  — 產品檔案」'
title: '"[!DNL Marketo Measure] 維護」'
exl-id: 4e1d53bb-0af8-4774-9f69-6a95516b3d11
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 0%

---

# [!DNL Marketo Measure] 維護 {#marketo-measure-maintenance}

[!DNL Marketo Measure] 每天從您的CRM提取幾乎所有需要的，但您會想要定期排程一些維護工作，以保留 [!DNL Marketo Measure] 一邊哼唱，一邊輸出最準確的資訊。

**同步新離線促銷活動的購買者接觸點（2x/月）**

正如你在上線時所學到的， [!DNL Marketo Measure] 透過與CRM的行銷活動同步，取得有關離線行銷工作的資訊。 當您的組織開始新的促銷活動時，請務必為每個促銷活動啟用購買者接觸點。 結帳 [這篇文章](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md)以取得更多資訊。

**所有管道的上傳花費（1個月）**

利用全部收入和ROI報告功能，[!DNL Marketo Measure]，您需要告訴 [!DNL Marketo Measure] 每個行銷管道和子管道的花費。 建議您指定每個管道/子管道的擁有者，並讓這些人員向負責每月上傳新成本資訊的單一方報告支出。

通過閱讀，刷新記憶體，了解如何上傳成本資訊 [這篇文章](/help/marketing-spend/spend-management/marketing-channel-costs.md).

**更新要追蹤的網域清單（1x/月）**

Marketo測量會追蹤Javascript作用中的所有頁面和子網域，但僅限我們已知的網域。 如果您最近首次推出新網域、進行國際擴展或變更主要網域，請聯絡 [Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;}，以確保我們會據此更新您的帳戶。

**檢閱自訂通道對應以取得正確性（1x/月）**

在上線期間，您可為線上和離線行銷工作設定自訂管道對應。 隨著您的行銷策略和Marketo測量的使用方式不斷演化，您會想要留意對應邏輯，以確保所有接觸點皆已適當分類。

記住， [!DNL Marketo Measure] 在編輯對應邏輯時重新處理資料，因此您無法每7天變更這些規則一次。

參考 [這篇文章](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md) 線上設定， [這篇文章](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md) 離線設定，而此最佳實務清單是從客戶那裡整理：

* 檢閱目前屬於您可能已設定的任何「其他」或「NULL」管道的接觸點。 若適用，請更新對應邏輯，將這些接觸點重新分類為更精確的管道。
* 檢閱目前屬於您直接管道的接觸點。 如果您的電子郵件行銷活動或其他努力缺少UTM參數，流量很有可能會不適當地分組至直接管道。 請考慮更新UTM參數以擷取反向連結來源。

**評估接觸點隱藏設定（1x/季）**

如果您看到許多不想在歸因故事中加以考慮的接觸點(來自 [!DNL Login] 或 [!DNL Unsubscribe forms]、職業頁面或內部應用程式)，您可能想要評估現有的接觸點隱藏設定。 每季一次，找出產生不必要雜訊的任何接觸點群組，並適當更新隱藏邏輯。 [這是一篇有用的文章](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)  做法。

**檢視自訂階段對應以取得正確性（1x/季）（如果適用）**

如果您使用任何自訂 [!UICONTROL Lead], [!UICONTROL Contact]，或 [!UICONTROL Opportunities] 階段中，您可能也已自訂這些階段對應到的管道部分，以及這些階段是否包含在自訂歸因模型中。 每季一次，造訪 [這篇文章](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md) 在自定義階段映射上刷新記憶體，並確保準確跟蹤自定義階段。

**比較機器學習模型與自訂模型加權（1x/季）（如果適用）**

如果您已獲得 [!DNL Marketo Measure] 自訂模型中，您也可以從以下位置的機器學習模型(MLM)取得資料： [!UICONTROL Settings] > [!UICONTROL Attribution Settings]. MLM會使用您帳戶的接觸點資料來計算每個階段的重要性，並且可協助您決定如何在自訂模型中分配歸因權重。 建議您每季將MLM與自訂模型比較一次，並與SM討論對自訂模型潛在變更的影響。

如需 [!DNL Marketo Measure] 機器學習模型，簽出 [這篇文章](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md).
