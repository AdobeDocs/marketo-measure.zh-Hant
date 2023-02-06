---
description: 接觸點設定最佳實務 —  [!DNL Marketo Measure]  — 產品檔案
title: 接觸點設定最佳實務
exl-id: 01e314a6-e33d-45cd-aaa3-c212afec07d1
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 0%

---

# 接觸點設定最佳實務 {#best-practices-for-touchpoint-settings}

## 概觀 {#overview}

您 [!DNL Marketo Measure] 應用程式可讓您設定規則，以從您的 [!DNL Marketo Measure] 資料及相關系統。 這些規則可協助您隔離出不需要在購買者接觸點資料中呈現，或您不想在不干擾追蹤和資料收集的情況下接收歸因評分的特定資料集。

**移除接觸點** 裝置 [!DNL Marketo Measure] 會清除（亦即移除）符合規則條件之CRM中的任何接觸點。 資料可在 [!DNL Marketo Measure] ROI控制面板(Discover)，但不會顯示在CRM中。 通常用於緩解CRM中資料儲存限制的壓力

**觸控點隱藏** 類似於「接觸點移除」，但無法在ROI控制面板中報告資料。 CRM或Discover中將無法存取任何受抑制的接觸點。 隱藏功能可確保您的CRM資料和Discover資料相符。 通常用於微調並進一步指定您要接收歸因評分的接觸點資料。

在 [!DNL Marketo Measure] 應用程式中，「接觸點設定」區段會劃分為四個關鍵區段。 每個區段會隱藏或移除不同的資料集。 使用下方的鍵，確保規則會隱藏或移除所需的接觸點。

* 從CRM中移除購買者接觸點
   * 當您想要建立要移除的規則時，請使用此區段 **購買者接觸點資料** （與個人相關聯的接觸點，而非商機） **CRM**
* 從CRM中隱藏採購員接觸點
   * 當您想要建立要移除的規則時，請使用此區段 **購買者接觸點資料** （與個人相關聯的接觸點，而非商機） **CRM** 和 **Discover**
* 從CRM中移除購買者歸因接觸點
   * 當您想要建立要移除的規則時，請使用此區段 **購買者歸因接觸點** 來自您 **CRM**
* 從CRM中隱藏購買者歸因接觸點
   * 當您想要建立要移除的規則時，請使用此區段 **購買者歸因接觸點** 來自您 **CRM** 和 **Discover**

## 最佳實務 {#best-practice}

無論您是首次建立接觸點設定規則，還是只是檢閱規則以檢查正確性，請牢記下列最佳實務。

* 建立規則之前，建立要隱藏或移除的資料清單
* 確切識別哪些欄位將清楚表示您正在設定的規則
* 請務必為規則指定正確的運算子
* 請利用上述金鑰，在「接觸點設定」的正確區段中確定已指定您的規則
* 在實作規則之前先測試規則，方法是複製CRM中「購買者」接觸點報表中的規則邏輯，以確保能抑制或移除所需資料

## 維護最佳實務 {#best-practice-for-maintenance}

檢閱接觸點設定很重要，因為若未定義，這些設定可大幅變更您的資料。 建議您每年至少檢閱兩次「接觸點設定」，這是最佳作法。 這是您在 [!DNL Marketo Measure] 應用程式。 此檢閱可讓您確信您的接觸點設定是最新的，且可以據此進行任何變更。

檢閱接觸點設定的原因包括……

* 行銷團隊的營業額
* 網站結構重大更新
* 識別不再有用的接觸點資料
   * 每當您遇到您認為不應接收歸因評分的接觸點資料時，接觸點隱藏規則就能提供功能，確保您的資料盡可能幹淨準確。
* 用於定義隱藏或移除規則的欄位的更改

>[!MORELIKETHIS]
>
>* [觸控點移除和隱藏概述](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)
>* [為何不應刪除接觸點](/help/advanced-marketo-measure-features/touchpoint-settings/why-you-should-never-delete-touchpoints.md)
>* [購買者接觸點(BT)與購買者歸因接觸點(BAT)](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md)

