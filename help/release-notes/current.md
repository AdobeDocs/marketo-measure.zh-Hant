---
description: 最新發行說明 -  [!DNL Marketo Measure]  - 產品文件
title: 最新發行說明
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: dc4fda07004398207fb5067eb42ecd9e8ffe8624
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 0%

---

# 發行說明：2023年 {#release-notes-2023}

以下是2023年發行版本的所有新功能和更新功能。

## 第4季發行 {#q4-release}

<p>

**探索儀表板重新設計**

所有Marketo Measure使用者都會體驗我們重新設計的應用程式內儀表板，不但可用性增強，價值也大幅提升。 我們也引進了新的量度，例如「實現的投資報酬率」，此量度會考量到行銷投資與B2B進入市場購買之間的典型延遲。

新的預先建立控制面板集合已排定分階段推出，於10月的第一週開始，並在年底前結束。 這些新控制面板連同產品內資訊和檔案連結會自動顯示在您的執行個體中。

* [新增Discover儀表板指南](/help/marketo-measure-discover-ui/dashboards/new-discover-dashboard-guide.md){target="_blank"}
* [探索儀表板基本知識](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
* [收入總覽儀表板](/help/marketo-measure-discover-ui/dashboards/revenue-overview-dashboard.md){target="_blank"}
* [已歸因的收入儀表板](/help/marketo-measure-discover-ui/dashboards/attributed-revenue-dashboard.md){target="_blank"}
* [ROI控制面板](/help/marketo-measure-discover-ui/dashboards/roi-dashboard.md){target="_blank"}
* [Passport儀表板](/help/marketo-measure-discover-ui/dashboards/passport-dashboard.md){target="_blank"}

>[!NOTE]
>
>目前的控制面板將於2024年1月中旬淘汰，在此之前，您可以利用兩個版本，以確保順利轉換。

### 淘汰 {#deprecations}

<p>

* **「custom_properties」欄位**

在我們Data Warehouse中，「custom_properties」欄位一直是固定結構描述未涵蓋之其他資料點的儲存空間。 此欄位以JSON格式儲存，其使用方式有限，而且與SQL查詢的整合可能會很複雜，從而影響效能。 基於這些因素，我們決定棄用此欄位。 此變更主要影響Azure表格儲存空間中的資料處理層，以及匯出至資料倉儲的資料。

* **Dynamics套件相關**

   * 若要保持與Dynamics的連線，請安裝最新套件版本v6.12。舊版 `(<v6.12)` 將不再受支援。 此更新會最佳化歷史記錄的建立，以減少儲存空間使用量。

   * 將棄用具有RefreshToken的過時方法OAuth。 請參閱 [本指南](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/oauth-with-azure-active-directory-for-dynamics-crm.md){target="_blank"} 更新您的認證，以遵守Microsoft使用ClientSecret的最佳做法。

### 即將推出的功能 {#q4-whats-coming}

<p>

**應用程式內自訂報告**

Marketo Measure客戶第一次能夠直接在應用程式中建立和儲存自己的報表。 我們於2024年初發行預先建立的儀表板後開始進行這項作業。

<br>

## 第2季發行 {#q2-release}

<p>

* **Salesforce封裝合併**

我們將所有Salesforce套件合併為單一、完整的套件，以提升使用者體驗並簡化使用程式。 V1、V2_EXT及Reporting套裝軟體將於下季淘汰。 新的套件結合了所有先前的功能，允許更高效的追蹤和更深入的客戶分析。

已安裝V2套件的客戶必須將其更新至新的整合版本。

我們已新增兩個新欄位來增強您的報告功能：

* form_name：此欄位現在可在BT/BAT物件中使用，可讓使用者根據表單名稱建立報表。
* user_touchpoint_id：此欄位可讓使用者建立具有不重複使用者接觸點計數的報告。

[本文](/help/configuration-and-setup/marketo-measure-and-salesforce/salesforce-package-consolidation.md){target="_blank"} 包含從舊版報告套件重新建立報告和儀表板的指南。

* **Salesforce API版本更新**

所有Apex類別的Salesforce API版本（包括UserActivityContext類別）都會更新至支援的版本。 （31.0至57.0）

* **新封裝安裝**

新的整合套件安裝連結 [可在此處找到](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t1P000000VY6Z){target="_blank"}

### 即將推出的功能 {#q2-whats-coming}

<p>

**IP位址儲存的變更**

我們將不再根據隱私權考量將IP位址儲存在系統中。 我們將繼續識別及儲存IP位址的地理位置，但格式將會變更（例如「美國」變更為「美國」）。
