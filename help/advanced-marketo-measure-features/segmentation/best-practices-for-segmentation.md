---
description: 區段最佳實務 —  [!DNL Marketo Measure]  — 產品檔案
title: 區段最佳作法
exl-id: 68281210-383b-4688-86e9-27fbdc1fabbb
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# 區段最佳作法 {#best-practices-for-segmentation}

## 總覽 {#overview}

[!DNL Marketo Measure] 分段可讓您根據您的CRM欄位來定義規則，這些規則實際上是篩選器，以將它們分段至個別區段。 這些區段便可在您的Discover控制面板及 [!DNL Salesforce] 報告。

區段對於您的 [!DNL Marketo Measure] 帳戶，特別是在您的Discover展示板中。 因為 [!DNL Marketo Measure] Discover展示板受限於預先決定的一組篩選器，分段可讓您像在Discover中一樣，在Discover中剖析資料 [!DNL Salesforce] 報告。

推送至時 [!DNL Salesforce]，區段值會寫入「區段」欄位，且屬於任何「購買者」接觸點報表類型。 這可讓兩個平台執行統一報告。 您也可以在任何接觸點的「接觸點詳細資料」上找到區段。

推送至Discover時，所有展示板的篩選下拉式功能表中，區段會顯示為可用的篩選。

## 最佳實務 {#best-practice}

無論您是第一次定義區段，還是只是檢閱先前已建立的區段，請牢記下列最佳實務。

* 保持簡單！
* 將區段名稱與組織的名稱一致，亦即類別=篩選器名稱、區段=篩選值
* 請勿在規則中使用公式欄位
* 盡可能在Lead/Contact和Opportunity上建立細分，以便您可以在整個漏斗中使用它
   * 並非所有區段類別都會在整個漏斗中保持一致
      * 例如，「機會類型」的區段類別與銷售機會不相關，但與「地區」相關的區段可能是可在整個漏斗中定義的類別
* 請思考您目前想要以何種方式分割資料（不論是在CRM或BI工具中），考慮將此建置為 [!DNL Marketo Measure] 讓您在Discover中擁有相同的報表

## 維護最佳實務 {#best-practice-for-maintenance}

每年至少檢閱兩次區段，可確保您的區段為最新狀態。 建議您檢閱「[!UICONTROL Segments]「 」頁簽 [!DNL Marketo Measure] 帳戶設定，以及提取內的報表 [!DNL Salesforce] 檢視「區段」的實際運作方式。 這些步驟可協助您和您的團隊對您的細分以及後續的 [!DNL Marketo Measure] 報告。

其他可能觸發您的「細分」檢閱的原因包括……

* 行銷團隊的營業額
* 用於定義區段的欄位變更
* 新增或變更已建立之區段

>[!MORELIKETHIS]
>
>[如何設定自訂細分](/help/advanced-marketo-measure-features/segmentation/custom-segmentation.md)
