---
unique-page-id: 18874765
description: 正在測試Marketo Measure與Salesforce沙箱的整合 —  [!DNL Marketo Measure]
title: 使用Salesforce沙箱測試Marketo Measure整合
exl-id: df40b000-4572-46df-aef5-8f690ca8ed7a
feature: Salesforce
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 1%

---

# 使用Salesforce沙箱測試Marketo Measure整合 {#testing-the-marketo-measure-integration-with-a-salesforce-sandbox}

>[!NOTE]
>
>您可能會在檔案中看到指定&quot;[!DNL Marketo Measure]&quot;的說明，但在您的CRM中仍會看到&quot;Bizible&quot;。 我們正致力於更新此專案，品牌重塑將很快反映在您的CRM中。

[!DNL Marketo Measure]核心功能之一，是能夠透過網站上的動作追蹤您的數位行銷工作，然後透過Leads和Contacts將該資料推送至您的產品[!DNL Salesforce org]。 不過，在沙箱整合中，通常不會從您的網站建立傳入銷售機會，因此對資料的關注將從純粹離線角度進行。

以下是測試兩個階段參考的兩個來源。 [步驟1-4](https://help.salesforce.com/s/articleView?id=lead_import_wizard.htm&amp;language=en_US&amp;type=5)和[步驟5-6](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md)。 建議您檢閱這些檔案，因為它們在某些方面提供了更多詳細資訊。

1. 您需要在CSV中建立一些銷售機會，以便將其上傳至促銷活動。 方法是透過生產Salesforce中的報告匯出一些銷售機會。 否則，您可以在Excel檔案中手動建立銷售機會，然後將其儲存為CSV以供匯入。 您只需要大約20筆記錄。 檔案必須包含下列欄：

   1. 電子郵件
   1. 公司
   1. 姓氏
   1. 名字（可選用，但建議使用）

1. 登入您的沙箱環境。
1. 建立測試行銷活動。 使用行銷活動型別，例如事件或電子報。
1. 建立行銷活動後，選取&#x200B;**[!UICONTROL Manage Members]** > **[!UICONTROL Add Members]** > **[!UICONTROL Import Files]**，將銷售機會上傳為行銷活動成員。
1. 完成之後，返回「促銷活動」頁面配置，您會看到「啟用購買者接觸點」，這是挑選清單欄位。 選擇值： **[!UICONTROL Include All Campaign Members]**。

完成之後，它會在[!DNL Marketo Measure]和[!DNL Salesforce]之間啟動同步，並將接觸點套用至Lead記錄。 建議隔天透過名為「潛在客戶上的Buyer Touchpoint」的報表檢視，該報表可在「報表」標籤內的「[!UICONTROL Buyer Touchpoints Reports]」資料夾中找到。 如果報告填入每個Lead的接觸點，就表示成功。
