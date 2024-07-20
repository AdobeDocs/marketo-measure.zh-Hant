---
description: 階段對應的最佳實務 —  [!DNL Marketo Measure]
title: 階段對應的最佳實務
exl-id: 1ed380a1-4a3a-4761-b70f-cdf2e290329d
feature: Tracking, Custom Models
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---

# 階段對應的最佳實務 {#best-practices-for-stage-mapping}

## 概觀 {#overview}

[!DNL Marketo Measure]帳戶的階段對應區段概述了[!DNL Marketo Measure]自動從您的CRM中提取的階段，以及您在使用自訂歸因模型時定義的任何自訂階段。 您的[!DNL Marketo Measure]資料是否有效取決於這些階段的順序是否正確，以便[!DNL Marketo Measure]能夠準確地瞭解您的漏斗以及記錄在整個漏斗中的進度。

在[!DNL Marketo Measure]執行個體的「階段對應」區段中，您會看到CRM中的作用中和非作用中階段。 根據您目前的漏斗狀況，以最好的方式排序所有階段。

本節所管理的額外功能是「漏斗階段」，可讓您新增階段至漏斗，而不需套用歸因。 漏斗階段將作為接觸點進行追蹤，並將填入您CRM中的接觸點位置欄位中。 這些漏斗階段也會顯示在[!DNL Marketo Measure] Discover的各種歷程展示板中。

## 最佳實務 {#best-practices}

無論您是第一次評估階段對應，還是檢閱漏斗順序，請務必牢記以下最佳實務。

* 順序就是一切！
   * 考慮到CRM中同時處於使用中和非使用中階段的[!DNL Marketo Measure]個提取，請確認任何可用於銷售機會/聯絡人或機會的階段都會分組在一起，並據此排序
* 定義自訂階段時，請確定已針對用來定義階段的任何欄位啟用欄位歷史記錄追蹤
* 請勿使用公式欄位來定義自訂階段
   * 布林值欄位是最佳實務建議
* 請注意，「銷售機會」或「聯絡人」階段區段分為「遺失」、「開啟」和「已轉換」；驗證階段是否在其適當的階段區段中
   * 在不正確的階段區段中有階段，可能會導致[!DNL Marketo Measure]資料高度不正確
   * 如果您是Marketo Measure Ultimate客戶，並將您的預設控制面板物件設定為連絡人，請勿使用下列兩個專屬於潛在客戶的欄位（[深入瞭解](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}）。
      * b2b.personStatus
      * b2b.isConverted
* 請注意，「機會」階段區段分為「已失敗」、「未完成」和「已獲勝」；驗證階段是否在其適當的階段區段中
   * 在不正確的階段區段中有某個階段，可能會導致[!DNL Marketo Measure]收入或管道收入資料高度不正確
* 避免使用重複的階段名稱（我們的系統將偵測這些名稱並自動移除一個）。
* 若要設定檢查NULL值的規則，請將值文字方塊留空。

## 維護作業的最佳作法 {#best-practices-for-maintenance}

每年檢閱一次階段對應，即可確保您在[!DNL Marketo Measure]中的機會資料正確且為最新狀態。

可能觸發階段對應稽核的其他原因包括……

* 您行銷團隊中的營業額
* 對您的CRM階段所做的任何變更
* 貴組織漏斗的更新
* 在您的[!DNL Marketo Measure]報表中看到不正確的收入資料

>[!MORELIKETHIS]
>
>[漏斗階段和自訂模型階段之間的差異](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md#the-difference-between-funnel-stages-and-custom-model-stages)
