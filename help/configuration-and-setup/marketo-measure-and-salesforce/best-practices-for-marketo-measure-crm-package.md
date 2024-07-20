---
description: ' [!DNL Marketo Measure] CRM封裝的最佳實務 —  [!DNL Marketo Measure]'
title: ' [!DNL Marketo Measure] CRM封裝的最佳作法'
exl-id: 97ce0ff3-8aa5-4789-9ee0-25d68c001def
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 0%

---

# [!DNL Marketo Measure] CRM封裝的最佳實務 {#best-practices-for-marketo-measure-crm-package}

>[!NOTE]
>
>您可能會在檔案中看到指定&quot;[!DNL Marketo Measure]&quot;的說明，但在您的CRM中仍會看到&quot;Bizible&quot;。 此專案已更新，品牌重塑將很快反映在您的CRM中。

## 概觀 {#overview}

[!DNL Marketo Measure]與[!DNL Salesforce]和[!DNL Microsoft Dynamics]整合，本檔案著重於針對[!DNL Salesforce]設計的CRM套件的[!DNL Marketo Measure]最佳做法。

實施期間，下列兩個套件會安裝在您的[!DNL Salesforce]執行個體中。

基礎封裝：這是基礎封裝，包含自訂物件和欄位。 建議所有使用者在生產環境中安裝。
控制面板擴充功能套件：這是我們的控制面板擴充功能套件，包含三個預先建立的控制面板。 我們建議您在生產環境中為所有使用者安裝。 這是選擇性的，但我們鼓勵客戶安裝。

這些套件可讓您的[!DNL Marketo Measure]使用者在整個[!DNL Salesforce]執行個體中輕鬆存取接觸點資料。 確認您已正確設定這些套件，是驗證頁面配置、許可權集、報告和儀表板是否如預期般向您的[!DNL Marketo Measure]使用者呈現的關鍵。

## 最佳實務 {#best-practice}

在實作及管理您的[!DNL Marketo Measure] [!DNL Salesforce]封裝時，請記住下列最佳實務。

* 確認每個必要的團隊成員都可以存取[!DNL Marketo Measure]報告資料夾。 應該有1到3個[!DNL Marketo Measure]資料夾（下面將加以說明）。 若要開啟存取權，安裝套件的人員必須與適當的使用者或角色共用報表資料夾。
   * **Buyer Touchpoint報告** — 可供所有人使用
   * **[!DNL Marketo Measure]帳戶型行銷報告** — 報告僅會填入至第2層及以上的客戶
   * **Buyer Touchpoint儀表板** — 可供所有人使用，不過此套件為選購專案。

## 維護最佳實務 {#best-practice-for-maintenance}

雖然CRM套件的設定會在初始實作期間涵蓋，但建議您每年審視一次CRM套件的設定。 此檢閱確認所有版面配置均已正確設定，且所有適當的團隊成員都可存取[!DNL Marketo Measure]報告和儀表板。

其他可能觸發評論的原因……

* 新增團隊成員
* 更新您的[!DNL Salesforce]頁面配置
* 將[!DNL Salesforce] Classic移轉至Lightning
* 升級至您的[!DNL Marketo Measure]合約
* 檢查您是否已在[!DNL Salesforce]中安裝最新版本的購買者接觸點套件

>[!NOTE]
>
>當您停用Marketo Measure將資料匯出至Salesforce時，並不會刪除任何現有的資料。 若要移除它，請依照[此Salesforce說明文章](https://help.salesforce.com/s/articleView?language=en_US&amp;id=sf.c360_a_delete_data_stream_records.htm&amp;type=5){target="_blank"}中的步驟操作。

>[!MORELIKETHIS]
>
>* [更新Buyer Touchpoint封裝](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md)
>* [[!DNL Marketo Measure] 許可權集](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)
>* [共用報告和儀表板資料夾](https://help.salesforce.com/s/articleView?language=en_US&amp;id=analytics_share_folder.htm&amp;type=0)
>* [將Marketo Measure連線至Salesforce](/help/configuration-and-setup/marketo-measure-and-salesforce/connect-marketo-measure-to-salesforce.md)
