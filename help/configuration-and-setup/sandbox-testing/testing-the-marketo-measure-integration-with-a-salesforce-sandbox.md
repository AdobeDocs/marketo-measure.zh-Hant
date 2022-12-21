---
unique-page-id: 18874765
description: 測試Marketo測量與Salesforce沙箱的整合 —  [!DNL Marketo Measure]  — 產品檔案
title: 測試Marketo測量與Salesforce沙箱的整合
exl-id: df40b000-4572-46df-aef5-8f690ca8ed7a
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 1%

---

# 測試Marketo測量與Salesforce沙箱的整合 {#testing-the-marketo-measure-integration-with-a-salesforce-sandbox}

>[!NOTE]
>
>您可能會看到指定「[!DNL Marketo Measure]「 」，但仍可在CRM中看到「Bizible」。 我們正致力更新該更新，品牌重塑將很快反映在您的CRM中。

其中 [!DNL Marketo Measure] 核心功能是透過網站上的動作追蹤您的數位行銷成果，然後將該資料推送至您的生產環境 [!DNL Salesforce org] 通過銷售機會和聯繫人。 不過，一般而言，在沙箱整合內不會有從您網站建立的傳入銷售機會，因此純粹以離線觀點著重於資料。

以下是兩個測試階段所參考的兩個來源。 [步驟1-4](https://help.salesforce.com/apex/HTViewHelpDoc?id=lead_import_wizard.htm&amp;language=en_US) 和 [步驟5-6](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md). 我們建議審查這些檔案，因為它們在某些方面提供了更詳細的資訊。

1. 您需要以CSV格式建立一些銷售機會，以便將其上傳至促銷活動。 執行此操作的方法是透過生產Salesforce中的報表匯出部分Lead。 否則，您可以在Excel檔案中手動建立銷售機會，然後儲存為CSV以匯入。 你只需要20張唱片。 檔案必須有下列欄：

   1. 電子郵件
   1. 公司
   1. 姓氏
   1. 名字（可選，但建議使用）

1. 登入您的沙箱環境。
1. 您會先建立測試促銷活動。 建議您使用活動類型，例如「事件」或「電子報」。
1. 建立促銷活動後，您將透過選取 **[!UICONTROL Manage Members]** > **[!UICONTROL Add Members]** > **[!UICONTROL Import Files]**.
1. 完成後，返回「促銷活動」頁面配置，您會看到「啟用購買者接觸點」（選取清單欄位）。 選擇值： **[!UICONTROL Include All Campaign Members]**.

完成後，就會啟動 [!DNL Marketo Measure] 和 [!DNL Salesforce] 並將接觸點套用至銷售機會記錄。 建議您透過報表(稱為：在 [!UICONTROL Buyer Touchpoints Reports] 資料夾。 如果報表正在填入每個銷售機會的接觸點，這是成功的跡象。
