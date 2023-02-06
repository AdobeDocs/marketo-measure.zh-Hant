---
description: 自訂模型最佳作法 —  [!DNL Marketo Measure]  — 產品檔案
title: 自訂模型最佳作法
exl-id: 7c19bb6a-30fc-4cbd-a58e-f20751102afe
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 0%

---

# 自訂模型最佳作法 {#best-practices-for-custom-model}

## 概觀 {#overview}

除了 [!DNL Marketo Measure] 立即可用的歸因模型中，第2層客戶及以上版本都可存取自訂歸因模型。

此 [!DNL Marketo Measure] 自訂歸因模型可讓使用者選擇要納入模型中的里程碑接觸點位置和/或自訂階段。 此外，使用者可以控制模型內每個階段歸因的評分百分比（使用者可以定義最多6個其他自訂階段），或是使用 [!DNL Marketo Measure] 機器學習模型。

自訂歸因模型有兩個主要方面：

**自訂階段** 可讓使用者根據其業務和程式來定義漏斗。 自訂階段應代表購買者歷程中的「里程碑」，與 [!DNL Marketo Measure] 里程碑（首次接觸、銷售機會建立接觸、機會建立接觸和結束的成功接觸）在股票歸因模型中完成。 請務必在帳戶中正確定義並對應自訂階段，以確保 [!DNL Marketo Measure] 正確追蹤階段轉變。 這是為了識別哪些接觸點應與每個階段關聯，並適當歸因評分。 自訂階段對應本質上是標準「階段對應」的擴充功能，應遵循相同的實務。

>[!NOTE]
>
>有關詳細資訊，請參考階段映射最佳實踐資源

**自訂歸因模型** 會在您選取「自訂階段」漏斗後定義。 然後，使用者就可以控制應指派多少歸因評分給每個自訂階段，以及 [!DNL Marketo Measure] 里程碑階段。 使用者可以視需要為每個階段指派評分，或參考 [!DNL Marketo Measure] 機器學習模型是以歷史資料為基礎的「建議性模型」。

必須正確且準確地定義自訂模型的這兩個方面，以確保 [!DNL Marketo Measure] 會建立精確的自訂歸因模型。

## 最佳實務 {#best-practice}

無論您是第一次設定自訂模型，還是檢閱先前已建立的模型，請務必牢記下列最佳實務。

* 開始簡單
   * 識別您要新增至自訂模型的關鍵階段，這些階段對您的 [!DNL Marketo Measure] 報告。 通常，這些階段是您經常測量的階段，或是您想要深入了解的階段
   * 您隨時都可以新增至自訂模型
* 利用 [!DNL Marketo Measure] 機器學習模型
   * 如果您難以決定百分比歸因突破， [!DNL Marketo Measure] 機器學習模型可協助您在設定自訂歸因模型時做出明智的決策。
   * 檢視機器學習模型時，每個階段的歸因百分比會反映行銷工作的潛在影響
      * 較高的百分比表示行銷會直接影響漏斗在該點的移動
      * 歸因百分比較低，表示階段對於您的團隊而言不那麼重要
* 您必鬚根據銷售機會階段或聯絡階段來定義漏斗階段頂端，而不是同時根據銷售機會階段或聯絡階段來定義
   * 這表示您必須確保所有人員都會在相對物件上通過該階段
      * 例如：如果從Lead對象定義MQL階段，則所有人員必須以Lead身份進入您的系統，並在其Lead記錄上標籤為MQL，以便 [!DNL Marketo Measure] 以準確反映哪個接觸與Lead轉換為MQL有關。 如果情況並非如此，在成為MQL作為Lead之前，有些人會前往Contact , [!DNL Marketo Measure] 無法在您的接觸點資料中準確說明此問題，我們必須假設該人員已擁有MQL。 [!DNL Marketo Measure] 不能解釋跳台，因此我們將推斷階段已經過去，即使沒有。
* 確保對用於定義您合併的自訂階段的所有欄位啟用欄位歷史記錄追蹤
* 請勿使用公式欄位來定義自訂階段
   * 布林欄位是最佳實務建議
* 請勿將自訂階段併入您與 [!DNL Marketo Measure] 里程碑接觸點位置（FT、LC、OC、閉合成功/丟失）
   * 若您這麼做，這些頭寸將一律同時發生，且可能造成漏斗部分的歸因評分膨脹。
* 與您的銷售運營團隊合作
   * 請加入具有最接近階段及其意義的團隊，可確保您使用正確的階段，並確保正確定義這些階段

## 維護最佳實務 {#best-practice-for-maintenance}

每年至少檢閱兩次自訂模型，可確保自訂歸因報表準確可靠。

如果您的自訂模型採用機器學習模型，則應每季在自訂模型中檢閱其應用程式，以確保您的自訂模型盡可能為最新狀態。

其他原因可能會觸發對自訂模型的審核，包括……

* 行銷團隊的營業額
* 對CRM階段的任何變更
* 組織漏斗的更新
* 在 [!DNL Marketo Measure] 套用自訂模型時報告
* 查看已填入與您的組織漏斗無關的接觸點位置

>[!MORELIKETHIS]
>
>* [自訂歸因模型與設定](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md)
>* [為自訂模型啟用欄位歷史記錄追蹤](/help/advanced-marketo-measure-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md)
>* [機器學習模型](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md)

