---
description: 階段對應的最佳實務 —  [!DNL Marketo Measure]  — 產品檔案
title: 中繼對應的最佳實務
exl-id: 1ed380a1-4a3a-4761-b70f-cdf2e290329d
source-git-commit: b8388c4f89734f55ec779ef23b75b34b07da6f58
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# 中繼對應的最佳實務 {#best-practices-for-stage-mapping}

## 概觀 {#overview}

的「階段對應」區段 [!DNL Marketo Measure] 帳戶概述以下階段 [!DNL Marketo Measure] 如果使用自訂歸因模型，則會自動從您的CRM和您已定義的任何自訂階段提取。 您的的有效性 [!DNL Marketo Measure] 資料需要這些階段正確排序，以便 [!DNL Marketo Measure] 可以準確地瞭解您的漏斗以及記錄在整個漏斗中的進度。

在「 」的「階段對應」區段中 [!DNL Marketo Measure] 執行個體時，您會從CRM中看到作用中和非作用中階段。 依據您目前的漏斗狀況，盡全力排序所有階段。

本節所管理的額外功能是「漏斗階段」，可讓您新增階段至漏斗，而不需套用歸因。 漏斗階段將作為接觸點進行追蹤，並將填入您CRM的接觸點位置欄位中。 這些「漏斗階段」也會出現在各種歷程展示板中： [!DNL Marketo Measure] 探索。

## 最佳實務 {#best-practices}

無論您是第一次評估階段對應，還是隻檢閱漏斗順序，請務必牢記以下最佳實務。

* 訂單就是一切！
   * 考慮 [!DNL Marketo Measure] 從您的CRM中同時提取使用中和非使用中階段，確認任何可用於潛在客戶/聯絡人或機會的階段都會分組在一起並據此排序
* 定義自訂階段時，請確定已針對用於定義階段的任何欄位啟用欄位歷史記錄追蹤
* 不要使用公式欄位來定義自訂階段
   * 布林值欄位是最佳實務建議
* 請注意，「銷售機會」或「連絡人」階段區段分為「遺失」、「開啟」和「已轉換」；驗證階段是否在其適當的階段區段中
   * 在不正確的階段區段中擁有階段可能會導致高度不正確 [!DNL Marketo Measure] 資料
* 請注意， Opportunity階段區段分為Lost 、 Open和Won ；驗證階段是否在其適當的階段區段中
   * 在不正確的階段區段中擁有階段可能會導致高度不正確 [!DNL Marketo Measure] 收入或管道收入資料
* 避免使用重複的階段名稱（我們的系統將偵測到它們並自動移除一個）。
* 若要設定檢查NULL值的規則，請將值文字方塊留空。

## 維護最佳實務 {#best-practices-for-maintenance}

每年審視一次階段對應，即可確保您的Opportunity資料位於 [!DNL Marketo Measure] 正確且為最新狀態。

可能觸發階段對應稽核的其他原因包括……

* 您行銷團隊中的營業額
* 對您的CRM階段所做的任何變更
* 貴組織漏斗的更新
* 檢視中的不正確收入資料 [!DNL Marketo Measure] 報告

>[!MORELIKETHIS]
>
>[漏斗階段和自訂模型階段之間的差異](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md#the-difference-between-funnel-stages-and-custom-model-stages)
