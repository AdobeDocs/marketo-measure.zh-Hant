---
unique-page-id: 18874580
description: 將Marketo Measure連線至Salesforce - [!DNL Marketo Measure]  — 產品檔案
title: 將Marketo Measure連線至Salesforce
exl-id: 9be8d3fa-1045-4e41-bc2e-5b9d4d3513ae
feature: Salesforce
source-git-commit: 5b1511395aff958f20f74c8a52c2701c4a64329d
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---

# 將Marketo Measure連線至Salesforce {#connect-marketo-measure-to-salesforce}

本文概述如何連結 [!DNL Salesforce] 帳戶至您的 [!DNL Marketo Measure] 帳戶。

## 正在連線 [!DNL Marketo Measure] 替換為 [!DNL Salesforce] {#connecting-marketo-measure-with-salesforce}

1. 使用無痕瀏覽器登入 [!DNL Marketo Measure].

1. 在熒幕頂端的功能表列中，導覽至 **[!UICONTROL My Account]** 並按一下 **[!UICONTROL Settings]** 選項。

1. 在左側的設定選項欄中，按一下 **[!UICONTROL Connections]** 位於 [!UICONTROL Integrations] 區段。

   ![](assets/connect-marketo-measure-to-salesforce-1.png)

1. 在「連線」的CRM區段下，按一下 **[!UICONTROL Set Up New CRM Connection]**.

   ![](assets/connect-marketo-measure-to-salesforce-2.png)

1. 系統會顯示快顯視窗，要求您選取CRM連線。 按一下 **[!UICONTROL Connect]** 按鈕旁的 [!DNL Salesforce] 標誌。

   ![](assets/connect-marketo-measure-to-salesforce-3.png)

1. 最後快顯視窗隨即出現，詢問您的 [!DNL Salesforce] 認證、沙箱或生產。 輸入您的資訊，然後按一下 **[!UICONTROL Authorize]** 將帳戶連線至 [!DNL Marketo Measure].

>[!NOTE]
>
>[!DNL Marketo Measure] 只能連線至一個 [!DNL Salesforce] 一次執行個體。
>
>* A [!DNL Marketo Measure] 執行個體可以連線至SFDC沙箱執行個體，以便在將連線切換至您的SFDC生產執行個體之前測試整合。
>* 如果您先使用SFDC沙箱進行測試，我們強烈建議您使用SFDC生產執行個體的精確復本進行測試，其包含潛在客戶、連絡人、帳戶、商機、促銷活動及Case物件上的欄位。 如果您的生產中有任何作用中的APEX觸發器會觸發Lead、Contact、Account、Opportunity、Campaign和Case物件的更新，您應該嘗試將它們置於沙箱中作用中。
>* 完成測試後，您將會更新 [!DNL Marketo Measure] 指向生產環境的帳戶 [!DNL Salesforce] （而非沙箱） [!DNL Salesforce])。 由於整合的建置方式，只要一次 [!DNL Marketo Measure] 帳戶已連線至生產環境 [!DNL Salesforce]，您不能「後退」並連線至沙箱 [!DNL Salesforce] 組織

## API積分使用情況 {#api-credits-usage}

Marketo Measure採用CRM整合工作，透過整合使用者與客戶的Salesforce介面。 透過此使用者進行的所有資料交換都會利用Salesforce API積分。 您有能力將評分配額分配給整合使用者，這會用來規管過度的API呼叫。 此配額或限制每24小時重設一次。

您可以在Marketo Measure中透過以下方式存取此限制： **我的帳戶** > **設定** > **CRM** > **一般** > **每日CRM API限制**，並可為租使用者設定。

![](assets/connect-marketo-measure-to-salesforce-4.png)

### 設定API積分的限制 {#setting-a-limit-for-api-credits}

1. 瀏覽至 **我的帳戶** > **設定**.

1. 在CRM底下，按一下 **一般**. 您將會看到 **每日CRM API限制** 選項。

1. 按一下「鎖定」圖示以進行編輯。

   ![](assets/connect-marketo-measure-to-salesforce-5.png)

1. 輸入等於或大於100,000的所需限制。 按一下 **儲存** 完成時。

   ![](assets/connect-marketo-measure-to-salesforce-6.png)

>[!NOTE]
>
>若要為您連線的解決方案增加可用的Salesforce API積分，請連絡您的Salesforce管理員和參考 [此Salesforce檔案](https://developer.salesforce.com/docs/atlas.en-us.salesforce_app_limits_cheatsheet.meta/salesforce_app_limits_cheatsheet/salesforce_app_limits_platform_api.htm){target="_blank"}.
