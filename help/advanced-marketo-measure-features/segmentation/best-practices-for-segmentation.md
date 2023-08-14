---
description: 區段最佳實務 —  [!DNL Marketo Measure]  — 產品檔案
title: 細分的最佳實務
exl-id: 68281210-383b-4688-86e9-27fbdc1fabbb
feature: Segmentation
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# 細分的最佳實務 {#best-practices-for-segmentation}

## 概觀 {#overview}

[!DNL Marketo Measure] 區段可讓您根據您的CRM欄位定義規則（本質上是篩選器），以將它們分段為個別區段。 然後，這些區段將可用於您的Discover儀表板以及您的 [!DNL Salesforce] 報告。

區段是您運用到 [!DNL Marketo Measure] 帳戶，尤其是在您探索展示板內。 因為 [!DNL Marketo Measure] 探索面板僅限於預先決定的篩選器集，分段可讓您在Discover中剖析資料，就像在Discover中一樣 [!DNL Salesforce] 報告。

當推送至 [!DNL Salesforce]，區段值會寫入「區段」欄位，並位於任何購買者接觸點報表型別內。 這允許跨兩個平台進行統一報告。 您也可以在任何接觸點的「接觸點詳細資料」上找到該區段。

推送到「探索」時，區段會在所有展示板上的篩選器下拉式功能表中顯示為可用篩選器。

## 最佳實務 {#best-practice}

無論是第一次定義區段，還是檢閱先前已建立的區段，請記住以下最佳實務。

* 保持簡單！
* 將您的區段名稱與組織的名稱對齊，即類別=篩選器名稱，區段=篩選器值
* 請勿在規則中使用公式欄位
* 儘可能在Lead/Contact和Opportunity上建立細分，以便用於整個漏斗
   * 並非所有「區段」類別都會在整個漏斗中對齊
      * 例如，「機會型別」的區段類別不會與銷售機會相關，但與「地區」相關的區段可能是可在整個漏斗中定義的類別
* 請思考您目前偏好將資料分割的方式，無論資料位於CRM或BI工具中，請考慮將此區段建置為 [!DNL Marketo Measure] 以便在Discover中有相同的報表

## 維護最佳實務 {#best-practice-for-maintenance}

每年至少兩次檢閱您的細分，將確保您的細分是最新的。 建議您最好在「 」中檢閱規則，作為最佳實務[!UICONTROL Segments]的「 」標籤 [!DNL Marketo Measure] 帳戶設定，以及在其中提取報表 [!DNL Salesforce] 以檢閱您的區段運作中。 這些步驟將幫助您和您的團隊對您的細分以及隨後的您的細分充滿信心 [!DNL Marketo Measure] 報告。

可能觸發審查您的區段的其他原因包括……

* 您行銷團隊中的營業額
* 用於定義區段的欄位變更
* 已建立區段的新增或變更

>[!MORELIKETHIS]
>
>[如何設定自訂分段](/help/advanced-marketo-measure-features/segmentation/custom-segmentation.md)
