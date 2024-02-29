---
description: 接觸點設定的最佳實務 —  [!DNL Marketo Measure]
title: 接觸點設定的最佳實務
exl-id: 01e314a6-e33d-45cd-aaa3-c212afec07d1
feature: Touchpoints
source-git-commit: 518a984b0d8d640290bd9b637221fcdc0948e5b9
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 0%

---

# 接觸點設定的最佳實務 {#best-practices-for-touchpoint-settings}

## 概觀 {#overview}

此 [!UICONTROL Touchpoint Settings] 部分 [!DNL Marketo Measure] 應用程式可讓您設定規則，以抑制或移除您的接觸點。 [!DNL Marketo Measure] 資料和相關系統。 這些規則可協助您隔離某些不需要顯示在購買者接觸點資料中的資料集，或是您不想在不干擾追蹤和資料收集的情況下接收歸因點數的資料集。

**接觸點移除** 方法 [!DNL Marketo Measure] 會從您的CRM中清除（即移除）符合規則條件的任何接觸點。 資料可在中回報 [!DNL Marketo Measure] ROI控制面板（探索），但不出現在CRM中。 通常用於減輕CRM內資料儲存空間限制的壓力

**接觸點隱藏** 類似「移除接觸點」，但無法在ROI控制面板中報告資料。 任何被抑制的接觸點將無法在CRM或Discover中存取。 隱藏專案將確保您的CRM資料與您的探索資料相符。 通常用於微調並進一步指定您要接收歸因點數的接觸點資料。

在您的 [!DNL Marketo Measure] 應用程式， [!UICONTROL Touchpoint Settings] 區段將細分為四個主要區段。 每個區段都會隱藏或移除不同的資料集。 使用下列鍵來確保您的規則會隱藏或移除所需的接觸點。

* 從CRM移除購買者接觸點
   * 當您想要建立將移除的規則時，請使用此區段 **購買者接觸點資料** (和個人（而非商機）相關聯的接觸點) **CRM**
* 從CRM隱藏購買者接觸點
   * 當您想要建立將移除的規則時，請使用此區段 **購買者接觸點資料** (和個人（而非商機）相關聯的接觸點) **CRM** 和 **探索**
* 從CRM移除購買者歸因接觸點
   * 當您想要建立將移除的規則時，請使用此區段 **購買者歸因接觸點** 資料（與商機和收入關聯的接觸點），來自 **CRM**
* 從CRM隱藏購買者歸因接觸點
   * 當您想要建立將移除的規則時，請使用此區段 **購買者歸因接觸點** 資料（與商機和收入關聯的接觸點），來自 **CRM** 和 **探索**

## 最佳實務 {#best-practice}

無論是第一次建立接觸點設定規則，還是檢閱規則以檢查準確性，請記住以下最佳作法。

* 建立規則之前，先建立您要隱藏或移除的資料清單
* 準確地識別哪些欄位將清楚表示您正在設定的規則
* 請確定您已為規則指定正確的運運算元
* 利用上述鍵，確定您的規則已在接觸點設定的正確區段中指定
* 在CRM中復寫購買者接觸點報表中的規則邏輯，在實作規則之前先測試規則，以確保該規則會隱藏或移除所需資料

## 維護最佳實務 {#best-practice-for-maintenance}

檢閱您的 [!UICONTROL Touchpoint Settings] 重要是因為定義不正確時，資料可能會大幅變更您的資料。 作為最佳實務，建議您每年至少審視接觸點設定兩次。 這是對您在的接觸點設定區段中設定的規則進行的簡單視覺檢閱。 [!DNL Marketo Measure] 應用程式。 此檢閱可讓您放心，您的接觸點設定是最新狀態，並且可以據此進行任何變更。

審視您的理由 [!UICONTROL Touchpoint] 設定包括……

* 您行銷團隊中的營業額
* 網站結構的重大更新
* 識別不再實用的接觸點資料
   * 每當遇到您認為不應該獲得歸因點數的接觸點資料時， [!DNL touchpoint suppression] 規則是確保資料儘可能乾淨和準確的功能。
* 用於定義隱藏或移除規則的欄位變更

>[!MORELIKETHIS]
>
>* [接觸點移除與隱藏概述](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)
>* [為什麼絕不應該刪除接觸點](/help/advanced-marketo-measure-features/touchpoint-settings/why-you-should-never-delete-touchpoints.md)
>* [購買者接觸點(BT)與購買者歸因接觸點(BAT)](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md)

