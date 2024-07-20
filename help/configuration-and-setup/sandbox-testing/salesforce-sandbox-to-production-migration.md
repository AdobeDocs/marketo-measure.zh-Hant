---
unique-page-id: 18874694
description: Salesforce沙箱移轉至生產環境 —  [!DNL Marketo Measure]
title: Salesforce沙箱移轉至生產環境
exl-id: b2b71c4a-f192-43ce-a27e-cbd0ec3cf008
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 0%

---

# Salesforce沙箱移轉至生產環境 {#salesforce-sandbox-to-production-migration}

如果您選擇在[!DNL Salesforce]沙箱環境中測試[!DNL Marketo Measure]，請依照這些指示，在您準備好後移轉至生產。 下列指示假設您已將[!DNL Marketo Measure]套件下載至您的沙箱組織、執行了必要的測試並準備將[!DNL Marketo Measure]推送至生產環境。

## 步驟1：將[!DNL Marketo Measure]套件安裝到您的生產[!DNL Salesforce]執行個體

* 使用&quot;[!UICONTROL All Users]&quot;設定將[!DNL Marketo Measure]套件安裝至生產環境

   * [基底封裝](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target="_blank"}

* 有關與[!DNL Salesforce]的[!DNL Marketo Measure]關係的詳細資訊，請參閱[本文章](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md)
* 需要[!DNL Salesforce]位元組態。 下面的[步驟4](#salesforce-configuration)概述了特定動作專案

## 步驟2：刪除[!DNL Marketo Measure]應用程式中目前的沙箱CRM連線 {#delete-the-current-sandbox-crm-connection-in-marketo-measure-app}

* 在experience.adobe.com/marketo-measure登入[!DNL Marketo Measure]應用程式
* 導覽至「我的帳戶>[!UICONTROL Settings] >[!UICONTROL Connections]」
* 按一下SFDC連線旁的垃圾桶圖示以刪除
* 系統會提示您確認刪除。 請務必仔細閱讀提示，並瞭解刪除的後果

  ![](assets/salesforce-sandbox-to-production-migration-1.png)

   * 按照確認模式中的提示輸入企業的名稱，然後按一下「我瞭解後果，刪除此連線」
* 這會觸發刪除程式，並需要一些時間才能完成

## 步驟3：在[!DNL Marketo Measure]應用程式中連線生產CRM執行個體 {#connect-the-production-crm-instance-in-marketo-measure-app}

* 在experience.adobe.com/marketo-measure登入[!DNL Marketo Measure]應用程式
* 導覽至[!UICONTROL My Account] >[!UICONTROL Settings] > [!UICONTROL Connections]
* 成功刪除沙箱連線後，連線會從頁面消失，否則連線仍會以「刪除進行中」的狀態出現
* 按一下&quot;[!UICONTROL Set up New CRM connection]&quot;
* 在「[!UICONTROL Select CRM Connection]」強制回應對話方塊中，按一下[!DNL Salesforce]平台旁的「[!UICONTROL Connect]」動作，選取「[!UICONTROL Production]」選項
* 系統會提示您輸入憑證，請務必輸入生產登入詳細資訊

## 步驟4： Salesforce設定 {#salesforce-configuration}

[頁面配置](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md)

[許可權集](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)

[共用報告](https://help.salesforce.com/s/articleView?language=en_US&amp;id=analytics_share_folder.htm&amp;type=0){target="_blank"}

[隱藏不必要的報表型別](/help/configuration-and-setup/marketo-measure-and-salesforce/hiding-unnecessary-report-types.md)

[自訂工作流程（如適用）](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
