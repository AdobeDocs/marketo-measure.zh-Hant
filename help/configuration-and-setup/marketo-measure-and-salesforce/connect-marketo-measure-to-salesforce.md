---
unique-page-id: 18874580
description: 將Marketo Measure連線至Salesforce - [!DNL Marketo Measure]
title: 將Marketo Measure連線至Salesforce
exl-id: 9be8d3fa-1045-4e41-bc2e-5b9d4d3513ae
feature: Salesforce
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 0%

---

# 將Marketo Measure連線至Salesforce {#connect-marketo-measure-to-salesforce}

本文概述如何將[!DNL Salesforce]帳戶連線至您的[!DNL Marketo Measure]帳戶。

## 正在連線[!DNL Marketo Measure]與[!DNL Salesforce] {#connecting-marketo-measure-with-salesforce}

1. 使用無痕瀏覽器登入[!DNL Marketo Measure]。

1. 在熒幕頂端的功能表列中，導覽至&#x200B;**[!UICONTROL My Account]**&#x200B;並按一下&#x200B;**[!UICONTROL Settings]**&#x200B;選項。

1. 在左側的設定選項欄中，按一下[!UICONTROL Integrations]區段下的&#x200B;**[!UICONTROL Connections]**。

   ![](assets/connect-marketo-measure-to-salesforce-1.png)

1. 在[連線]中的CRM區段下，按一下&#x200B;**[!UICONTROL Set Up New CRM Connection]**。

   ![](assets/connect-marketo-measure-to-salesforce-2.png)

1. 系統會顯示一個快顯視窗，要求您選取CRM連線。 按一下[!DNL Salesforce]標誌旁的&#x200B;**[!UICONTROL Connect]**。

   ![](assets/connect-marketo-measure-to-salesforce-3.png)

1. 最後快顯視窗會出現，要求您提供[!DNL Salesforce]認證、沙箱或生產環境。 輸入您的資訊，然後按一下&#x200B;**[!UICONTROL Authorize]**，將帳戶連線到[!DNL Marketo Measure]。

>[!NOTE]
>
>[!DNL Marketo Measure]一次只能連線到一個[!DNL Salesforce]執行個體。
>
>* [!DNL Marketo Measure]執行個體可以連線至SFDC沙箱執行個體，以便在將連線切換至您的SFDC生產執行個體之前測試整合。
>* 如果您先使用SFDC沙箱進行測試，我們強烈建議您使用SFDC生產執行個體的精確復本進行測試，其包含潛在客戶、連絡人、帳戶、商機、促銷活動及Case物件上的欄位。 如果您的生產中有任何作用中的APEX觸發器會觸發Lead、Contact、Account、Opportunity、Campaign和Case物件的更新，您應該嘗試將它們置於沙箱中作用中。
>* 完成測試後，請更新[!DNL Marketo Measure]帳戶以指向生產[!DNL Salesforce] （而不是沙箱[!DNL Salesforce]）。 由於整合的建置方式，一旦[!DNL Marketo Measure]帳戶連線至生產[!DNL Salesforce]，您就無法「往後」連線至沙箱[!DNL Salesforce]組織。

## API積分使用情況 {#api-credits-usage}

Marketo Measure採用CRM整合工作，透過整合使用者與客戶的Salesforce介面。 透過此使用者進行的所有資料交換都使用Salesforce API積分。 您有能力將評分配額分配給整合使用者，這會用來規管過度的API呼叫。 此配額或限制每24小時重設一次。

您可以在Marketo Measure中透過&#x200B;**我的帳戶** > **設定** > **CRM** > **一般** > **每日CRM API限制**&#x200B;存取此限制，也可以為租使用者設定。

![](assets/connect-marketo-measure-to-salesforce-4.png)

### 設定API積分的限制 {#setting-a-limit-for-api-credits}

1. 瀏覽至&#x200B;**我的帳戶** > **設定**。

1. 在CRM底下，按一下&#x200B;**一般**。 您看到&#x200B;**每日CRM API限制**&#x200B;選項。

1. 按一下「鎖定」圖示以進行編輯。

   ![](assets/connect-marketo-measure-to-salesforce-5.png)

1. 輸入等於或大於100,000的所需限制。 完成時，按一下&#x200B;**儲存**。

   ![](assets/connect-marketo-measure-to-salesforce-6.png)

>[!NOTE]
>
>若要為您連線的解決方案增加可用的Salesforce API積分，請連絡您的Salesforce管理員並參考[此Salesforce檔案](https://developer.salesforce.com/docs/atlas.en-us.salesforce_app_limits_cheatsheet.meta/salesforce_app_limits_cheatsheet/salesforce_app_limits_platform_api.htm){target="_blank"}。

>[!MORELIKETHIS]
>
>[錯誤通知](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}
