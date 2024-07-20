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

除了現成的[!DNL Marketo Measure]歸因模型之外，第2層以上的客戶也可以存取自訂歸因模型。

[!DNL Marketo Measure]自訂歸因模型可讓使用者選擇要納入模型中的里程碑接觸點位置及/或自訂階段。 此外，使用者可以控制模型中每個階段的歸因點數百分比（使用者最多可定義6個額外的自訂階段），也可以使用[!DNL Marketo Measure]機器學習模型建議的歸因百分比值。

自訂歸因模型有兩個主要方面：

**自訂階段**&#x200B;可讓使用者定義與其業務及程式相關的漏斗。 自訂階段應該在整個購買者的歷程中代表「里程碑」，非常類似於Stock歸因模型中的[!DNL Marketo Measure]里程碑（首次接觸、潛在客戶建立接觸、機會建立接觸和已關閉的已成交接觸）。 您的自訂階段必須正確定義並在帳戶內對應，以確保[!DNL Marketo Measure]可正確追蹤階段轉換。 這是為了識別哪些接觸點應該與每個階段相關聯，並適當地屬性化評分。 自訂階段對應基本上是標準「階段對應」的延伸，應遵循相同實務。

>[!NOTE]
>
>如需詳細資訊，請參閱階段對應最佳實務資源

**自訂歸因模型**&#x200B;定義於您選取「自訂階段」漏斗之後。 然後，使用者就可以控制每個自訂階段以及[!DNL Marketo Measure]里程碑階段應該指派多少歸因評分。 使用者可以依其認為適當的方式指派評分給每個階段，或參考[!DNL Marketo Measure]機器學習模型（根據歷史資料當作「建議模型」）。

請務必正確定義自訂模型的這兩個層面，以確保[!DNL Marketo Measure]產生正確的自訂歸因模型。

## 最佳實務 {#best-practice}

無論您是第一次設定自訂模型，還是檢閱先前已建立的專案，請務必牢記以下最佳實務。

* 開始簡單
   * 識別您要新增至自訂模型的關鍵階段，這些階段對[!DNL Marketo Measure]報表至關重要。 通常，這些是您通常會測量或希望深入瞭解的階段
   * 您可以隨時新增至您的自訂模型
* 利用[!DNL Marketo Measure]機器學習模型
   * 如果您難以決定歸因劃分的百分比，[!DNL Marketo Measure]機器學習模型可協助您在設定自訂歸因模型時做出明智的決策。
   * 檢視機器學習模型時，每個階段的歸因百分比會反映行銷工作的潛在影響
      * 較高的百分比表示行銷會直接影響漏斗在該點的移動
      * 歸因百分比越低，表示團隊監視的階段越不重要
* 您必須根據「銷售機會」或「連絡人」階段來定義漏斗階段的頂端，而不是同時定義兩者
   * 這表示您必須確保所有人員都會在相對物件上通過該舞台
      * 例如：如果您從Lead物件定義MQL階段，則所有人員必須以Lead進入您的系統，並在其Lead記錄上標籤為MQL，以便[!DNL Marketo Measure]能夠準確反映哪個接觸與Lead轉換至MQL有關。 如果不是這種情況，並且某些人在成為MQL作為潛在客戶之前進度到聯絡，則[!DNL Marketo Measure]將無法準確地在您的接觸點資料中說明此問題，並且我們將必須假設該人員已經擁有MQL。[!DNL Marketo Measure]無法說明階段跳躍機制，因此我們將推斷階段已通過，即使階段尚未通過。
* 確保為您納入用來定義自訂階段的所有欄位啟用欄位歷史記錄追蹤
* 請勿使用公式欄位來定義自訂階段
   * 布林值欄位是最佳實務建議
* 請勿將自訂階段合併到自訂模型中，因為自訂模型與[!DNL Marketo Measure]里程碑接觸點位置（FT、LC、OC、已關閉的贏家/輸家）一致
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
* 套用自訂模型時，在[!DNL Marketo Measure]報表中看到不準確的收入資料
* 檢視已填入與您的組織漏斗無關的接觸點位置

>[!MORELIKETHIS]
>
>* [自訂歸因模型與設定](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md)
>* [啟用自訂模型的欄位歷程記錄追蹤](/help/advanced-marketo-measure-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md)
>* [機器學習模型](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md)
