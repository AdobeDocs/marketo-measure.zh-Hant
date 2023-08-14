---
unique-page-id: 18874694
description: Salesforce沙箱至生產環境移轉 —  [!DNL Marketo Measure]  — 產品檔案
title: Salesforce沙箱移轉至生產環境
exl-id: b2b71c4a-f192-43ce-a27e-cbd0ec3cf008
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 0%

---

# Salesforce沙箱移轉至生產環境 {#salesforce-sandbox-to-production-migration}

如果您選擇測試 [!DNL Marketo Measure] 在 [!DNL Salesforce] 沙箱環境，請在您準備就緒後，按照這些指示移轉至生產。 下列指示假設您已下載 [!DNL Marketo Measure] 封裝到您的沙箱組織，執行了必要的測試並準備好推送 [!DNL Marketo Measure] 至生產環境。

## 步驟1：安裝 [!DNL Marketo Measure] 將套件放入生產環境 [!DNL Salesforce] 例項 {#install-marketo-measure-packages-into-your-production-salesforce-instance}

* 安裝兩項 [!DNL Marketo Measure] 使用&quot;[!UICONTROL All Users]」設定

   * [基礎封裝](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target="_blank"}
   * [控制面板擴充功能套件](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t610000001jI6){target="_blank"}

* 如需關於的詳細資訊 [!DNL Marketo Measure] 關聯性 [!DNL Salesforce]，檢視一下 [本文](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md)
* 一點 [!DNL Salesforce] 設定是必要的。 以下概述特定動作專案 [下面的步驟4](#salesforce-configuration)

## 步驟2：刪除中目前的沙箱CRM連線 [!DNL Marketo Measure] 應用程式 {#delete-the-current-sandbox-crm-connection-in-marketo-measure-app}

* 登入 [!DNL Marketo Measure] 應用程式，網址為experience.adobe.com/marketo-measure
* 導覽至「我的帳戶」 >[!UICONTROL Settings] >[!UICONTROL Connections]
* 按一下SFDC連線旁的垃圾桶圖示以刪除
* 系統會提示您確認刪除。 請務必仔細閱讀提示並瞭解刪除的後果

  ![](assets/salesforce-sandbox-to-production-migration-1.png)

   * 按照確認模式中的提示輸入企業的名稱，然後按一下「我瞭解後果，刪除此連線」
* 這將會觸發刪除程式，並需要一些時間才能完成

## 步驟3：連線中的生產CRM執行個體 [!DNL Marketo Measure] 應用程式 {#connect-the-production-crm-instance-in-marketo-measure-app}

* 登入 [!DNL Marketo Measure] 應用程式，網址為experience.adobe.com/marketo-measure
* 瀏覽至 [!UICONTROL My Account] >[!UICONTROL Settings] > [!UICONTROL Connections]
* 一旦成功刪除沙箱連線後，連線將從頁面中消失，否則連線仍會以「刪除進行中」的狀態出現
* 按一下 &quot;[!UICONTROL Set up New CRM connection]&quot;
* 在&quot;[!UICONTROL Select CRM Connection]「強制回應對話方塊，按一下「[!UICONTROL Connect]「動作」旁邊 [!DNL Salesforce] 平台，選取&quot;[!UICONTROL Production]「選項
* 系統會提示您輸入憑證，請務必輸入生產登入詳細資訊

## 步驟4： Salesforce設定 {#salesforce-configuration}

[頁面配置](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md)

[許可權集](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)

[共用報告](https://help.salesforce.com/articleView?id=analytics_share_folder.htm&amp;type=0){target="_blank"}

[隱藏不必要的報表型別](/help/configuration-and-setup/marketo-measure-and-salesforce/hiding-unnecessary-report-types.md)

[自訂工作流程（如適用）](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
