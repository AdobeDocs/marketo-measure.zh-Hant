---
unique-page-id: 18874580
description: 將Marketo Measure連接到Salesforce - [!DNL Marketo Measure]  — 產品檔案
title: 將Marketo Measure連接到Salesforce
exl-id: 9be8d3fa-1045-4e41-bc2e-5b9d4d3513ae
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# 將Marketo Measure連接到Salesforce {#connect-marketo-measure-to-salesforce}

本文概述如何連接您的 [!DNL Salesforce] 帳戶 [!DNL Marketo Measure] 帳戶。

## 連接 [!DNL Marketo Measure] with [!DNL Salesforce] {#connecting-marketo-measure-with-salesforce}

1. 使用無痕瀏覽器登錄到 [!DNL Marketo Measure].

1. 在畫面頂端的功能表列中，導覽至 **[!UICONTROL My Account]** 並按一下 [!UICONTROL Settings] 選項。

1. 在左側的設定選項欄中，按一下 [!UICONTROL Connections] 位於 [!UICONTROL Integrations] 區段。

   ![](assets/1.png)

1. 在「連線」的CRM區段下，按一下 **[!UICONTROL Set Up New CRM Connection]**.

   ![](assets/2.png)

1. 將出現一個彈出窗口，要求您選擇CRM連接。 按一下 [!UICONTROL Connect] 按鈕 [!DNL Salesforce] 標誌。

   ![](assets/3.png)

1. 最後的快顯視窗會出現，詢問您 [!DNL Salesforce] 認證、沙箱或生產。 輸入您的資訊，然後按一下 **[!UICONTROL Authorize]** 將帳戶連接到 [!DNL Marketo Measure].

>[!NOTE]
>
>[!DNL Marketo Measure] 只能連接到一個 [!DNL Salesforce] 例項。
>
>* A [!DNL Marketo Measure] 實例可以連接到SFDC沙箱實例，以在切換到SFDC生產實例的連接之前測試整合。
>* 如果您首先使用SFDC沙箱進行測試，我們強烈建議您使用一個測試，該測試是SFDC生產實例的完全副本，位於銷售機會、聯繫人、帳戶、機會、促銷活動和案例對象上的欄位。 如果您在生產中有任何作用中的APEX觸發器，會在Lead、Contact、Account、Opportunity、Campaign和Case物件的更新時引發，則應嘗試讓它們在您的沙箱中處於作用中狀態。
>* 完成測試後，您將更新 [!DNL Marketo Measure] 帳戶指向生產環境 [!DNL Salesforce] (而非沙箱 [!DNL Salesforce])。 由於整合的建立方式， [!DNL Marketo Measure] 帳戶已連線至生產環境 [!DNL Salesforce]，您無法「回溯」並連線至沙箱 [!DNL Salesforce] 組織。


