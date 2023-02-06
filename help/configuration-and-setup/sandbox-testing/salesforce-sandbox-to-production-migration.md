---
unique-page-id: 18874694
description: Salesforce沙箱移轉至生產環境 —  [!DNL Marketo Measure]  — 產品檔案
title: Salesforce沙箱移轉至生產環境
exl-id: b2b71c4a-f192-43ce-a27e-cbd0ec3cf008
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 0%

---

# Salesforce沙箱移轉至生產環境 {#salesforce-sandbox-to-production-migration}

如果您選擇測試 [!DNL Marketo Measure] 在 [!DNL Salesforce] 沙箱環境，請在您準備就緒後，依照這些指示移轉至生產環境。 下列指示假設您已下載 [!DNL Marketo Measure] 封裝至您的沙箱組織，執行必要的測試並準備好推送 [!DNL Marketo Measure] 生產。

## 步驟1:安裝 [!DNL Marketo Measure] 封裝至生產環境 [!DNL Salesforce] 例項 {#install-marketo-measure-packages-into-your-production-salesforce-instance}

* 安裝兩個 [!DNL Marketo Measure] 封裝至生產環境，並搭配「[!UICONTROL All Users]&quot;設定

   * [基本包](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target="_blank"}
   * [控制面板擴充功能套件](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t610000001jI6){target="_blank"}

* 如需 [!DNL Marketo Measure] 關係 [!DNL Salesforce]，請查看 [這篇文章](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md)
* 有點 [!DNL Salesforce] 需要設定。 具體的動作項目概述於 [下面的步驟4](#salesforce-configuration)

## 步驟2:刪除中目前的沙箱CRM連線 [!DNL Marketo Measure] 應用程式 {#delete-the-current-sandbox-crm-connection-in-marketo-measure-app}

* 登入 [!DNL Marketo Measure] experience.adobe.com/marketo-measure上的應用程式
* 導覽至「我的帳戶>」[!UICONTROL Settings] >[!UICONTROL Connections]
* 按一下SFDC連線旁的垃圾桶圖示以刪除
* 系統會提示您確認刪除。 請務必仔細閱讀提示，並了解刪除的後果

   ![](assets/salesforce-sandbox-to-production-migration-1.png)

   * 鍵入確認模型中提示的業務名稱，然後按一下「了解後果，刪除此連接」
* 這會觸發刪除程式，且需要一些時間才能完成

## 步驟3:在中連接生產CRM執行個體 [!DNL Marketo Measure] 應用程式 {#connect-the-production-crm-instance-in-marketo-measure-app}

* 登入 [!DNL Marketo Measure] experience.adobe.com/marketo-measure上的應用程式
* 導覽至 [!UICONTROL My Account] >[!UICONTROL Settings] > [!UICONTROL Connections]
* 成功刪除沙箱連線後，連線會從頁面中消失，否則連線仍會顯示為「正在刪除」狀態
* 按一下 &quot;[!UICONTROL Set up New CRM connection]&quot;
* 在「[!UICONTROL Select CRM Connection]按一下「強制回應」對話方塊中的「[!UICONTROL Connect]&quot;操作 [!DNL Salesforce] 平台，選取「[!UICONTROL Production]&quot;選項
* 系統會提示您輸入憑證，請務必輸入生產登入詳細資訊

## 步驟4:Salesforce配置 {#salesforce-configuration}

[頁面配置](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md)

[權限集](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)

[共用報表](https://help.salesforce.com/articleView?id=analytics_share_folder.htm&amp;type=0){target="_blank"}

[隱藏不必要的報表類型](/help/configuration-and-setup/marketo-measure-and-salesforce/hiding-unnecessary-report-types.md)

[自訂工作流程（如果適用）](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
