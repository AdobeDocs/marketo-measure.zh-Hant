---
description: 細分的最佳實務 —  [!DNL Marketo Measure]
title: 細分的最佳實務
exl-id: 68281210-383b-4688-86e9-27fbdc1fabbb
feature: Segmentation
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%

---

# 細分的最佳實務 {#best-practices-for-segmentation}

## 概觀 {#overview}

[!DNL Marketo Measure]區段可讓您根據您的CRM欄位定義規則（基本上是篩選器），以將其儲存為個別區段。 然後，這些區段將可用於您的Discover儀表板以及[!DNL Salesforce]報表。

細分對於使用您的[!DNL Marketo Measure]帳戶至關重要，尤其是在您Discover展示板中。 由於[!DNL Marketo Measure] Discover面板僅限於預先決定的篩選器集，因此分段可讓您在Discover中剖析資料，就像在[!DNL Salesforce]報表中一樣。

推送至[!DNL Salesforce]時，區段值會寫入「區段」欄位，且位於任何購買者接觸點報表型別中。 這允許跨兩個平台進行統一報告。 您也可以在任何接觸點的「接觸點詳細資料」上找到該區段。

推送至[!UICONTROL Discover]時，區段會在所有展示板上的篩選器下拉式功能表中顯示為可用篩選器。

## 最佳實務 {#best-practice}

無論是第一次定義區段，還是檢閱先前已建立的區段，請記住以下最佳實務。

* 保持簡單！
* 將您的區段名稱與組織的名稱對齊，即類別=篩選器名稱，區段=篩選器值
* 請勿在規則中使用公式欄位
* 儘可能在Lead/Contact和Opportunity上建立細分，以便用於整個漏斗
   * 如果您是Marketo Measure Ultimate客戶，並將您的預設儀表板物件設定為連絡人，請勿使用下列兩個專屬於潛在客戶的欄位（[在這裡瞭解更多](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}）。
      * b2b.personStatus
      * b2b.isConverted
   * 並非所有「區段」類別都會在整個漏斗中對齊
      * 例如，「機會型別」的區段類別不會與銷售機會相關，但與「地區」相關的區段可能是可在整個漏斗中定義的類別
* 請思考您目前想要切割資料的方式，不論資料位於CRM或BI工具中，請考慮將此區段建置為[!DNL Marketo Measure]中的區段，以便您在Discover中擁有相同的報表

## 維護最佳實務 {#best-practice-for-maintenance}

每年至少兩次檢閱您的細分，將確保您的細分是最新的。 根據最佳實務，建議您在[!DNL Marketo Measure]帳戶設定的&#39;[!UICONTROL Segments]&#39;標籤中檢閱規則，並在[!DNL Salesforce]中提取報表，以檢閱運作中的區段。 這些步驟可協助您和您的團隊對細分以及隨後的[!DNL Marketo Measure]報告充滿信心。

可能觸發審查您的區段的其他原因包括……

* 您行銷團隊中的營業額
* 用於定義區段的欄位變更
* 已建立區段的新增或變更

>[!MORELIKETHIS]
>
>[如何設定自訂分段](/help/advanced-marketo-measure-features/segmentation/custom-segmentation.md)
