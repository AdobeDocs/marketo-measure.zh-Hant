---
description: 接觸點設定的最佳實務 —  [!DNL Marketo Measure]
title: 接觸點設定的最佳實務
exl-id: 01e314a6-e33d-45cd-aaa3-c212afec07d1
feature: Touchpoints
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 0%

---

# 接觸點設定的最佳實務 {#best-practices-for-touchpoint-settings}

## 概觀 {#overview}

[!DNL Marketo Measure]應用程式的[!UICONTROL Touchpoint Settings]區段可讓您設定規則，以抑制或移除[!DNL Marketo Measure]資料和相關系統中的接觸點。 這些規則可協助您隔離某些不需要顯示在購買者接觸點資料中的資料集，或是您不想在不干擾追蹤和資料收集的情況下接收歸因點數的資料集。

**接觸點移除**&#x200B;表示[!DNL Marketo Measure]將從您的CRM中清除（亦即移除）符合規則條件的任何接觸點。 資料可以在[!DNL Marketo Measure] ROI控制面板（探索）中回報，但不會顯示在CRM中。 通常用於減輕CRM內資料儲存空間限制的壓力

**接觸點隱藏**&#x200B;類似於接觸點移除，但無法在ROI儀表板中報告資料。 任何被抑制的接觸點將無法在CRM或Discover中存取。 隱藏專案將確保您的CRM資料與您的探索資料相符。 通常用於微調並進一步指定您要接收歸因點數的接觸點資料。

在您的[!DNL Marketo Measure]應用程式中，[!UICONTROL Touchpoint Settings]區段將分成四個主要區段。 每個區段都會隱藏或移除不同的資料集。 使用下列鍵來確保您的規則會隱藏或移除所需的接觸點。

* 從CRM移除購買者接觸點
   * 當您想要建立將從&#x200B;**CRM**&#x200B;移除&#x200B;**Buyer Touchpoint資料** （與個人而非機會相關聯的接觸點）的規則時，請使用此區段
* 從CRM隱藏購買者接觸點
   * 當您想要建立將將&#x200B;**Buyer Touchpoint資料** （與個人關聯的接觸點，而非商機）從您的&#x200B;**CRM**&#x200B;和&#x200B;**Discover**&#x200B;移除的規則時，請使用此區段
* 從CRM移除購買者歸因接觸點
   * 當您想要建立將從&#x200B;**CRM**&#x200B;移除&#x200B;**Buyer Attribution Touchpoint**&#x200B;資料（與商機和收入關聯的接觸點）的規則時，請使用此區段
* 從CRM隱藏購買者歸因接觸點
   * 當您想要建立將從&#x200B;**CRM**&#x200B;和&#x200B;**Discover**&#x200B;中移除&#x200B;**Buyer Attribution Touchpoint**&#x200B;資料（與商機和收入相關聯的接觸點）的規則時，請使用此區段

## 最佳實務 {#best-practice}

無論是第一次建立接觸點設定規則，還是檢閱規則以檢查準確性，請記住以下最佳作法。

* 建立規則之前，先建立您要隱藏或移除的資料清單
* 準確地識別哪些欄位將清楚表示您正在設定的規則
* 請確定您已為規則指定正確的運運算元
* 利用上述鍵，確定您的規則已在接觸點設定的正確區段中指定
* 在CRM中復寫購買者接觸點報表中的規則邏輯，在實作規則之前先測試規則，以確保該規則會隱藏或移除所需資料

## 維護最佳實務 {#best-practice-for-maintenance}

檢閱您的[!UICONTROL Touchpoint Settings]很重要，因為若未適當定義，他們可能會大幅變更您的資料。 作為最佳實務，建議您每年至少審視接觸點設定兩次。 這是在[!DNL Marketo Measure]應用程式「接觸點設定」區段中設定的規則之簡單視覺化檢閱。 此檢閱可讓您放心，您的接觸點設定是最新狀態，並且可以據此進行任何變更。

檢閱[!UICONTROL Touchpoint]設定的理由包括……

* 您行銷團隊中的營業額
* 網站結構的重大更新
* 識別不再實用的接觸點資料
   * 每當您遇到不應該獲得歸因評分的接觸點資料時，[!DNL touchpoint suppression]規則都是功能，可確保您的資料儘可能乾淨和準確。
* 用於定義隱藏或移除規則的欄位變更

>[!MORELIKETHIS]
>
>* [接觸點移除與隱藏概述](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)
>* [絕不應該刪除接觸點的原因](/help/advanced-marketo-measure-features/touchpoint-settings/why-you-should-never-delete-touchpoints.md)
>* [購買者接觸點(BT)與購買者歸因接觸點(BAT)](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md)

