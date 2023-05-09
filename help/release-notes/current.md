---
description: 最新發行說明 —  [!DNL Marketo Measure]  — 產品檔案
title: 最新發行說明
source-git-commit: 8e8ddd80d69102455fa678a32f31a9fe8319822c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# 發行說明：2023年 {#release-notes-2023}

以下是我們2023版本的所有新功能和更新功能。

## 第2季發行 {#q2-release}

<p>

**Salesforce套件整合**

* 我們將所有Salesforce套件合併為單一、全面的套件，以改善使用者體驗並簡化使用。 V1、V2_EXT和報表套件將於下季度淘汰。 新套件結合了先前的所有功能，可提供更有效的追蹤功能和更深入的客戶見解。
* 已安裝V2軟體包的客戶必須將其更新到新的整合版本。
* 我們已新增兩個欄位來增強您的報表功能：
   * form_name:現在可在BT/BAT物件中使用，此欄位可讓使用者根據表單名稱建立報表。
   * user_touchpoint_id:此欄位可讓使用者建立具有不重複使用者接觸點計數的報表。
* [本文](/help/configuration-and-setup/marketo-measure-and-salesforce/salesforce-package-consolidation.md){target="_blank"} 包括從舊版報表套件重新建立報表和控制面板的指南。

**Salesforce API版本更新**

* 所有Apex類的Salesforce API版本（包括UserActivityContext類）均更新為支援的版本。 (31.0 - 57.0)

**新軟體包安裝**

* 新的整合包安裝連結 [可在此處找到](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t1P000000VY6Z){target="_blank"}

### 接下來呢？ {#whats-coming}

<p>

**IP位址儲存的變更**

* 根據隱私權考量，我們將不再將IP位址儲存在系統中。 我們將繼續識別和儲存IP位址的地理位置，但格式將會變更（例如「美國」變更為「美國」）。
