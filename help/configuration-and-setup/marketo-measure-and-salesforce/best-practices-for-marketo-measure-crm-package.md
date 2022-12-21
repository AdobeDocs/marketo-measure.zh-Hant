---
description: 最佳實務 [!DNL Marketo Measure] CRM套件 —  [!DNL Marketo Measure]  — 產品檔案
title: 最佳實務 [!DNL Marketo Measure] CRM套件
exl-id: 97ce0ff3-8aa5-4789-9ee0-25d68c001def
source-git-commit: 00268f49ff6e5dfc105fa7ea21837375eae49647
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 0%

---

# 最佳實務 [!DNL Marketo Measure] CRM套件 {#best-practices-for-marketo-measure-crm-package}

>[!NOTE]
>
>您可能會看到指定「[!DNL Marketo Measure]「 」，但仍可在CRM中看到「Bizible」。 我們正致力更新該更新，品牌重塑將很快反映在您的CRM中。

## 總覽 {#overview}

[!DNL Marketo Measure] 與兩者整合 [!DNL Salesforce] 和 [!DNL Microsoft Dynamics]，本檔案將著重於 [!DNL Marketo Measure] 專為 [!DNL Salesforce].

實施期間，您的 [!DNL Salesforce] 例項。

基本包：這是我們的基本套件，包含自訂物件和欄位。 建議所有使用者在生產環境中安裝。
控制面板擴充功能套件：這是我們的控制面板擴充功能套件，包含3個預先建立的控制面板。 建議所有使用者在生產環境中安裝。 這是選用項目，但我們鼓勵客戶安裝。

這些套件可讓您 [!DNL Marketo Measure] 使用者可在其 [!DNL Salesforce] 例項。 確認您已正確設定這些套件是驗證頁面配置、權限集、報表和控制面板是否呈現給您的關鍵 [!DNL Marketo Measure] 使用者。

## 最佳實務 {#best-practice}

關於實作和管理 [!DNL Marketo Measure] [!DNL Salesforce] 套件，請牢記下列最佳實務。

* 確認每個必要的團隊成員都能存取 [!DNL Marketo Measure] 報告資料夾。 1-3 [!DNL Marketo Measure] 資料夾（以下說明）。 若要開啟存取權，安裝套件的人員必須與適當的使用者或角色共用報表資料夾。
   * **購買者接觸點報表**  — 適用於所有人
   * **[!DNL Marketo Measure]帳戶型行銷報告**  — 報表只會填入至第2層及以上的客戶
   * **購買者接觸點控制面板**  — 可供所有人使用，不過此套件為選用。

## 維護最佳實務 {#best-practice-for-maintenance}

雖然初始實作期間涵蓋CRM套件的設定，但建議您每年檢閱一次CRM套件的設定。 此檢閱將確認所有頁面配置皆已正確設定，且所有適當的團隊成員皆有權存取 [!DNL Marketo Measure] 報表和控制面板。

其他原因可能會觸發審核……

* 新增團隊成員
* 更新至您 [!DNL Salesforce] 頁面配置
* 移轉 [!DNL Salesforce] Classic到Leading
* 升級至您的 [!DNL Marketo Measure] 合同
* 確認您已在 [!DNL Salesforce]

>[!NOTE]
>
>當您停用將資料匯出至Salesforce的Marketo測量時，不會移除任何現有資料。 若要移除，請依照 [本Salesforce說明文章](https://help.salesforce.com/s/articleView?id=sf.c360_a_delete_data_stream_records.htm&amp;type=5){target=&quot;_blank&quot;}。

>[!MORELIKETHIS]
>
>* [更新購買者接觸點套件](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md)
>* [[!DNL Marketo Measure] 權限集](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)
>* [共用報表和控制面板資料夾](https://help.salesforce.com/articleView?id=analytics_share_folder.htm&amp;type=0)
>* [將Marketo測量連接到Salesforce](/help/configuration-and-setup/marketo-measure-and-salesforce/connect-marketo-measure-to-salesforce.md)

