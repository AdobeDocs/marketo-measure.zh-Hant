---
description: 最新發行說明 —  [!DNL Marketo Measure]  — 產品檔案
title: 最新發行說明
exl-id: 64b8fce8-af7d-4991-b01e-3fcf375d14e7
feature: Release Notes
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# 發行說明：2023年 {#release-notes-2023}

以下是2023年發行版本的所有新功能和更新功能。

## 第2季發行 {#q2-release}

<p>

**Salesforce封裝合併**

* 我們將所有Salesforce套件合併為單一、完整的套件，以提升使用者體驗並簡化使用程式。 V1、V2_EXT及Reporting套裝軟體將於下季淘汰。 新的套件結合了所有先前的功能，允許更高效的追蹤和更深入的客戶分析。
* 已安裝V2套件的客戶必須將其更新至新的整合版本。
* 我們已新增兩個新欄位來增強您的報告功能：
   * form_name：此欄位現在可在BT/BAT物件中使用，可讓使用者根據表單名稱建立報表。
   * user_touchpoint_id：此欄位可讓使用者建立具有不重複使用者接觸點計數的報告。
* [本文](/help/configuration-and-setup/marketo-measure-and-salesforce/salesforce-package-consolidation.md){target="_blank"} 包含從舊版報告套件重新建立報告和儀表板的指南。

**Salesforce API版本更新**

* 所有Apex類別的Salesforce API版本（包括UserActivityContext類別）都會更新至支援的版本。 （31.0至57.0）

**新封裝安裝**

* 新的整合套件安裝連結 [可在此處找到](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t1P000000VY6Z){target="_blank"}

### 即將推出的功能 {#whats-coming}

<p>

**IP位址儲存的變更**

* 我們將不再根據隱私權考量將IP位址儲存在系統中。 我們將繼續識別及儲存IP位址的地理位置，但格式將會變更（例如「美國」變更為「美國」）。
