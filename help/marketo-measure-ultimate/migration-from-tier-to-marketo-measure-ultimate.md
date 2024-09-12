---
description: 瞭解從 [!DNL Marketo Measure] 階層訂閱移轉至 [!DNL Marketo Measure] Ultimate時的移轉程式。
title: 從階層移轉至 [!DNL Marketo Measure] Ultimate
feature: Integration, Tracking, Attribution
source-git-commit: 9c3c3c75a9a505bb078da18e13f210add8699c24
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 1%

---

# 從第1-2層移轉至[!DNL Marketo Measure]旗艦版 {#migration-from-tier-to-marketo-measure-ultimate}

本文概述從第1或第2層訂閱移轉至[!DNL Marketo Measure] Ultimate的使用者移轉程式。

>[!IMPORTANT]
>
>請記得保留現有的Tier執行個體，直到移轉完成。

## 資料彙集 {#data-collection}

### 網站流量資料 {#web-traffic-data}

* JavaScript部署不需要任何變更。

* 在新的Ultimate執行個體中啟用網域。

* 如有需要，請提交票證以移轉並重新處理歷史Web資料。

* 廣告整合保持不變，但請記得在Ultimate中重新連線它們。 在執行此操作之前，請確定您中斷與Tier租使用者中Ad帳戶的連線。

>[!NOTE]
>
>將不會匯入歷史廣告成本資料。 我們只會在廣告帳戶重新連線後，匯入往後推的廣告成本資料。

### 企業資料連線 {#enterprise-data-connection}

在AEP中重新實作所有來源資料連線，包括CRM和Marketo Engage連線。

## 資料轉換 {#data-transformation}

* Ultimate中不提供Account-Based Marketing功能，包括銷售線索對帳戶的比對和預測性參與分數。

   * 不過，您可以透過AEP匯入銷售線索與帳戶的比對結果，並在平台內使用這些結果。

* 在Ultimate中，會推斷CRM歷史階段轉變，而非直接讀取，因為沒有直接CRM連線。

   * 我們會讀取機會記錄和時間戳記，檢視目前階段，然後推斷歷史階段。

## 報告 {#reporting}

* Ultimate不會將資料推送回CRM。

   * 如果需要將資料推送回CRM，則需要自訂ETL管道，才能從Marketo MeasureSnowflake將資料擷取到CRM。 您必須在CRM中設定自訂資料模型。

* 所有Discover儀表板除了新增Attribution AI儀表板外，與階層式解決方案中的相同。
