---
description: 階段對應最佳作法 —  [!DNL Marketo Measure]  — 產品檔案
title: 階段對應最佳作法
exl-id: 1ed380a1-4a3a-4761-b70f-cdf2e290329d
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---

# 階段對應最佳作法 {#best-practices-for-stage-mapping}

## 概觀 {#overview}

您的 [!DNL Marketo Measure] 帳戶概述 [!DNL Marketo Measure] 使用自訂歸因模型時，會自動從您的CRM和您定義的任何自訂階段中提取。 您的 [!DNL Marketo Measure] 資料依賴這些階段的正確排序， [!DNL Marketo Measure] 能夠準確了解您的漏斗以及整個漏斗中記錄的進展。

在 [!DNL Marketo Measure] 例項中，您會從CRM中看到作用中和非作用中階段。 將所有階段排序為最佳狀態，以符合漏斗現狀。

本節中管理的其他功能是漏斗階段，可讓您在不套用歸因的情況下，將階段新增至漏斗。 漏斗階段將被追蹤為接觸點，並將填入CRM的「接觸點位置」欄位中。 這些漏斗階段也會顯示在 [!DNL Marketo Measure] 探索。

## 最佳實務 {#best-practices}

無論您是第一次評估階段對應，還是只是檢閱漏斗順序，請務必牢記下列最佳實務。

* 秩序就是一切！
   * 考慮 [!DNL Marketo Measure] 從您的CRM提取活動中和非活動中階段，確認可用於銷售機會/聯繫人或機會的任何階段將分組在一起並據此排序
* 定義自訂階段時，請確定已針對用於定義階段的任何欄位啟用欄位歷史記錄追蹤
* 請勿使用公式欄位來定義自訂階段
   * 布林欄位是最佳實務建議
* 請注意，銷售機會或聯繫階段部分分為「丟失」、「開啟」和「轉換」；驗證各階段是否位於其適當的階段區段
   * 在不正確的階段區段中設定階段可能會導致高度不正確 [!DNL Marketo Measure] 資料
* 請注意， Opportunity階段部分分為Lost 、 Open和Won;驗證各階段是否位於其適當的階段區段
   * 在不正確的階段區段中設定階段可能會導致高度不正確 [!DNL Marketo Measure] 收入或管道收入資料
* 避免使用重複的階段名稱（我們的系統會偵測這些名稱並自動移除）。

## 維護最佳實務 {#best-practices-for-maintenance}

每年審核一次您的階段映射將確保您的Opportunity資料 [!DNL Marketo Measure] 準確且最新。

可能觸發審核您的階段映射的其他原因包括……

* 行銷團隊的營業額
* 對CRM階段的任何變更
* 組織漏斗的更新
* 在您的 [!DNL Marketo Measure] 報告

>[!MORELIKETHIS]
>
>[漏斗階段和自訂模型階段之間的差異](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md#the-difference-between-funnel-stages-and-custom-model-stages)
