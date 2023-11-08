---
unique-page-id: 18874765
description: 使用Salesforce沙箱測試Marketo Measure整合 —  [!DNL Marketo Measure]  — 產品檔案
title: 使用Salesforce沙箱測試Marketo Measure整合
exl-id: df40b000-4572-46df-aef5-8f690ca8ed7a
feature: Salesforce
source-git-commit: b8ea008c594ed114323dedd3762d1265287193c7
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 1%

---

# 使用Salesforce沙箱測試Marketo Measure整合 {#testing-the-marketo-measure-integration-with-a-salesforce-sandbox}

>[!NOTE]
>
>您可能會看到指定&#39;&#39;的說明[!DNL Marketo Measure]&quot;，但仍在您的CRM中看到「Bizible」。 我們正致力於更新此專案，品牌重塑將很快反映在您的CRM中。

其中一項 [!DNL Marketo Measure] 核心功能是能透過網站上的動作追蹤您的數位行銷工作，然後將資料推送至生產環境 [!DNL Salesforce org] 透過Leads和Contact。 不過，在沙箱整合中，通常不會從您的網站建立傳入銷售機會，因此對資料的關注將從純粹離線角度進行。

以下是測試兩個階段參考的兩個來源。 [步驟1-4](https://help.salesforce.com/apex/HTViewHelpDoc?id=lead_import_wizard.htm&amp;language=en_US) 和 [步驟5-6](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md). 我們建議您檢閱這些檔案，因為這些檔案在某些方面可提供更多詳細資訊。

1. 您需要在CSV中建立一些銷售機會，以便將其上傳至行銷活動。 方法是透過生產Salesforce中的報告匯出一些銷售機會。 否則，您可以在Excel檔案中手動建立銷售機會，然後將其儲存為CSV以供匯入。 您只需要大約20筆記錄。 檔案必須包含下列欄：

   1. 電子郵件
   1. 公司
   1. 姓氏
   1. 名字（可選用，但建議使用）

1. 登入您的沙箱環境。
1. 您將先建立測試行銷活動。 我們建議使用行銷活動型別，例如事件或電子報。
1. 建立行銷活動後，您將透過選取以下專案將潛在客戶上傳為行銷活動成員 **[!UICONTROL Manage Members]** > **[!UICONTROL Add Members]** > **[!UICONTROL Import Files]**.
1. 完成之後，返回「促銷活動」頁面配置，您會看到「啟用購買者接觸點」，這是挑選清單欄位。 選擇值： **[!UICONTROL Include All Campaign Members]**.

完成此操作後，將啟動以下專案之間的同步： [!DNL Marketo Measure] 和 [!DNL Salesforce] 並將接觸點套用至Lead記錄。 建議隔天透過以下報告返回檢視：「潛在客戶上的購買者接觸點」，可在 [!UICONTROL Buyer Touchpoints Reports] 資料夾（在「報表」標籤中）。 如果報告填入每個Lead的接觸點，就表示成功。
