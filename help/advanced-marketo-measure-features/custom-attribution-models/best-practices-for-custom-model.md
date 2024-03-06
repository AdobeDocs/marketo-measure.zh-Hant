---
description: 自訂模型的最佳實務 —  [!DNL Marketo Measure]
title: 自訂模型的最佳實務
exl-id: 7c19bb6a-30fc-4cbd-a58e-f20751102afe
feature: Custom Models
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 0%

---

# 自訂模型的最佳實務 {#best-practices-for-custom-model}

## 概觀 {#overview}

除了 [!DNL Marketo Measure] 現成可用的歸因模型，第2層客戶及更高層級客戶可存取自訂歸因模型。

此 [!DNL Marketo Measure] 自訂歸因模型可讓使用者選擇要納入模型中的里程碑接觸點位置和/或自訂階段。 此外，使用者可以控制模型中每個階段的歸因點數百分比（使用者最多可定義6個其他自訂階段），也可以使用模型建議的歸因百分比值。 [!DNL Marketo Measure] 機器學習模型。

自訂歸因模型有兩個主要方面：

**自訂階段** 允許使用者定義與其業務和流程相關的漏斗。 自訂階段應該代表整個購買者歷程中的「里程碑」，非常類似於 [!DNL Marketo Measure] 里程碑（首次接觸、潛在客戶建立接觸、商機建立接觸和封閉式成功接觸）會在股票歸因模型中進行。 您的自訂階段必須在帳戶內正確定義和對應，以確保 [!DNL Marketo Measure] 會正確追蹤階段轉變。 這是為了識別哪些接觸點應該與每個階段相關聯，並適當地屬性化評分。 自訂階段對應基本上是標準「階段對應」的延伸，應遵循相同實務。

>[!NOTE]
>
>如需詳細資訊，請參閱階段對應最佳實務資源

**自訂歸因模型** 會在您選取「自訂階段」漏斗後定義。 然後，使用者可以控制應該將多少歸因點數指派給每個自訂階段以及 [!DNL Marketo Measure] 里程碑階段。 使用者可依其認為適當的方式為每個階段指派評分，或參考 [!DNL Marketo Measure] 機器學習模型，可作為根據歷史資料的「建議模型」。

請務必正確定義自訂模型的這兩個層面，以確保 [!DNL Marketo Measure] 正在產生精確的自訂歸因模型。

## 最佳實務 {#best-practice}

無論您是第一次設定自訂模型，還是檢閱先前已建立的專案，請務必牢記以下最佳實務。

* 開始簡單
   * 識別您要新增至自訂模型的關鍵階段，這些階段對您的至關重要 [!DNL Marketo Measure] 報告。 通常，這些是您通常會測量或希望深入瞭解的階段
   * 您可以隨時新增至您的自訂模型
* 利用 [!DNL Marketo Measure] 機器學習模型
   * 如果您難以決定歸因劃分的百分比， [!DNL Marketo Measure] 機器學習模型可協助您在設定自訂歸因模型時做出明智的決策。
   * 檢視機器學習模型時，每個階段的歸因百分比會反映行銷工作的潛在影響
      * 較高的百分比表示行銷會直接影響漏斗在該點的移動
      * 歸因百分比越低，表示團隊監視的階段越不重要
* 您必須根據「銷售機會」或「連絡人」階段來定義漏斗階段的頂端，而不是同時定義兩者
   * 這表示您必須確保所有人員都會在相對物件上通過該舞台
      * 例如：如果您從Lead物件定義MQL階段，則所有人員必須以Lead進入您的系統，並在其Lead記錄上標籤為MQL，以便 [!DNL Marketo Measure] 以準確反映哪個接觸點與Lead轉換至MQL有關。 如果不是這種情況，並且有些人會在成為MQL作為潛在客戶之前進展到聯絡， [!DNL Marketo Measure] 您將無法在接觸點資料中準確說明此問題，且必須假設該人員已執行MQL。 [!DNL Marketo Measure] 無法說明階段跳躍原因，因此我們會推斷階段已通過，即使階段未通過。
* 確保為您納入用來定義自訂階段的所有欄位啟用欄位歷史記錄追蹤
* 請勿使用公式欄位來定義自訂階段
   * 布林值欄位是最佳實務建議
* 請勿將自訂階段合併到自訂模型中 [!DNL Marketo Measure] 里程碑接觸點位置（FT、LC、OC、已結束的勝利/失敗）
   * 如果您這麼做，這些位置一律會同時發生，並可能導致漏斗部分獲得膨脹的歸因評分。
* 與您的Sales Opp團隊合作
   * 引進與階段工作最接近的團隊，以及他們的意思可確保您使用正確的階段，且他們已正確定義

## 維護最佳實務 {#best-practice-for-maintenance}

您每年至少審視自訂模型兩次，才能確保自訂歸因報表準確可靠。

如果您的自訂模型使用機器學習模型，則應每季在自訂模型中檢閱其應用程式，以確保您的自訂模型儘可能最新。

其他可能觸發檢閱自訂模型的原因包括……

* 您行銷團隊中的營業額
* 對您的CRM階段所做的任何變更
* 組織漏斗的更新
* 在您的網站中看到不準確的收入資料 [!DNL Marketo Measure] 套用自訂模型時產生報表
* 檢視已填入與您的組織漏斗無關的接觸點位置

>[!MORELIKETHIS]
>
>* [自訂歸因模型與設定](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md)
>* [為自訂模型啟用欄位記錄追蹤](/help/advanced-marketo-measure-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md)
>* [機器學習模型](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md)
