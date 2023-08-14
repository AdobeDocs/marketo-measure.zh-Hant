---
description: 以下專案的最佳實務 [!DNL Marketo Measure] CRM套件 —  [!DNL Marketo Measure]  — 產品檔案
title: 以下專案的最佳實務 [!DNL Marketo Measure] CRM套件
exl-id: 97ce0ff3-8aa5-4789-9ee0-25d68c001def
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# 以下專案的最佳實務 [!DNL Marketo Measure] CRM套件 {#best-practices-for-marketo-measure-crm-package}

>[!NOTE]
>
>您可能會看到指定&#39;&#39;的說明[!DNL Marketo Measure]&quot;，但仍在您的CRM中看到「Bizible」。 我們正致力於更新此專案，品牌重塑將很快反映在您的CRM中。

## 概觀 {#overview}

[!DNL Marketo Measure] 與兩者整合 [!DNL Salesforce] 和 [!DNL Microsoft Dynamics]，本檔案將會聚焦在 [!DNL Marketo Measure] 專為CRM套件設計的最佳實務 [!DNL Salesforce].

實施期間，下列兩個套件將安裝在您的 [!DNL Salesforce] 執行個體。

基礎套件：這是我們的基礎套件，包含我們的自訂物件和欄位。 我們建議您在生產環境中為所有使用者安裝。
儀表板擴充功能套件：這是我們的儀表板擴充功能套件，其中包含3個預先建立的控制面板。 我們建議您在生產環境中為所有使用者安裝。 這是選擇性的，但我們鼓勵客戶安裝。

這些套件可讓您的 [!DNL Marketo Measure] 使用者可輕鬆存取其所有接觸點資料 [!DNL Salesforce] 執行個體。 確認您已正確設定這些套件，將是驗證頁面配置、許可權集以及報告和儀表板是否向您的展示的關鍵 [!DNL Marketo Measure] 使用者如預期。

## 最佳實務 {#best-practice}

實作及管理您的 [!DNL Marketo Measure] [!DNL Salesforce] 套裝軟體，請牢記以下最佳實務。

* 確認每個必要的團隊成員都可以存取 [!DNL Marketo Measure] 報告資料夾。 應該有1-3個 [!DNL Marketo Measure] 資料夾（請見下文說明）。 若要開啟存取權，安裝套件的人員需要與適當的使用者或角色共用報表資料夾。
   * **購買者接觸點報告**  — 可供所有人使用
   * **[!DNL Marketo Measure]以帳戶為基礎的行銷報表**  — 報表只會填入至第2級及以上的客戶
   * **購買者接觸點控制面板**  — 所有人都能使用，不過此套件為選填。

## 維護最佳實務 {#best-practice-for-maintenance}

雖然CRM套件的設定會在初始實作期間涵蓋，但建議您每年審視一次CRM套件的設定。 此檢閱將確認所有頁面配置已正確設定，且所有適當的團隊成員都有權存取 [!DNL Marketo Measure] 報告和儀表板。

其他可能觸發評論的原因……

* 新增團隊成員
* 您的更新 [!DNL Salesforce] 頁面配置
* 移轉 [!DNL Salesforce] 從傳統轉換為輕盈
* 升級至 [!DNL Marketo Measure] 合約
* 檢查您是否已在中安裝最新版的購買者接觸點套件 [!DNL Salesforce]

>[!NOTE]
>
>當您停用Marketo Measure將資料匯出至Salesforce時，並不會移除任何現有的資料。 若要移除它，請依照中的步驟操作 [此Salesforce說明文章](https://help.salesforce.com/s/articleView?id=sf.c360_a_delete_data_stream_records.htm&amp;type=5){target="_blank"}.

>[!MORELIKETHIS]
>
>* [更新購買者接觸點套件](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md)
>* [[!DNL Marketo Measure] 許可權集](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)
>* [共用報表和控制面板資料夾](https://help.salesforce.com/articleView?id=analytics_share_folder.htm&amp;type=0)
>* [將Marketo Measure連線至Salesforce](/help/configuration-and-setup/marketo-measure-and-salesforce/connect-marketo-measure-to-salesforce.md)
