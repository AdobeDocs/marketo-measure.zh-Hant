---
description: '[!DNL Marketo Measure] Salesforce封裝安裝及設定 —  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] [!DNL Salesforce] 封裝安裝及設定'
exl-id: ed58bc1e-cfb0-48db-aa53-96204e12de2e
feature: Installation, Salesforce
source-git-commit: 05ba9e487d492ba4352a7f0577c7221f6ec9567e
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 0%

---

# [!DNL Marketo Measure] Salesforce套件安裝與設定 {#marketo-measure-salesforce-package-installation-and-set-up}

在安裝[!DNL Marketo Measure] [!DNL Salesforce]基本套件之前，您必須先判斷您是否先在[!DNL Salesforce]沙箱中安裝它，然後再移至您的Salesforce生產執行個體。

>[!NOTE]
>
>一旦您的[!DNL Marketo Measure]帳戶連線至[!DNL Salesforce]生產執行個體後，您就無法回溯並連線至沙箱。 此外，[!DNL Marketo Measure]帳戶只能連線至一個[!DNL Salesforce]生產執行個體。

[!DNL Marketo Measure]基底封裝包含：

* 7個自訂[!DNL Marketo Measure]物件
* 自訂[!DNL Marketo Measure]欄位
* 25個[!DNL Stock]報告

[!DNL Marketo Measure]能夠讀取標準[!DNL Salesforce]物件、欄位和記錄，但[!DNL Marketo Measure]永遠不會更新或推送資料給它們。 [!DNL Marketo Measure] JavaScript所收集的所有資料都會顯示在[!DNL Marketo Measure]自訂物件與欄位中。

請依照下列步驟安裝[!DNL Marketo Measure Salesforce]基礎套件。

1. 使用無痕瀏覽器，前往[SalesforceAppExchange](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target="_blank"}並登入。

1. 在沙箱或生產環境的[!DNL Marketo Measure]套件中安裝。

1. 以管理員身分登入[!DNL Salesforce]。

1. 為所有使用者選取&#x200B;**[!UICONTROL Install]**。

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-1.png)

1. 安裝完成後，即可檢視。

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-2.png)

完成安裝之後，您可以視需要使用[!DNL Marketo Measure]欄位更新您的[[!DNL Salesforce] 頁面配置](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md){target="_blank"}。

>[!NOTE]
>
>瞭解已建立的[!DNL Marketo Measure]許可權集及[其使用方式](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md){target="_blank"}。

## 建立[!DNL Marketo Measure]設定檔和使用者 {#creating-a-marketo-measure-profile-and-user}

[!DNL Marketo Measure]會透過[!DNL Marketo Measure]應用程式中連線的[!DNL Salesforce]使用者傳送及接收資料。

若要將接觸點資料推送至您的[!DNL Salesforce]執行個體，連線的使用者必須能存取[!DNL Marketo Measure]個自訂物件(例如Buyer Touchpoint和Buyer Attribution Touchpoint)以及銷售機會和聯絡人等標準[!DNL Salesforce]物件。

建立[!DNL Marketo Measure]設定檔，以確保您在推送資料至Salesforce時不會發生驗證錯誤。

步驟1：建立特定的[!DNL Marketo Measure]設定檔

1. 指派下列許可權：

* [!DNL Marketo Measure]管理員許可權集
   * Managed許可權集可讓SFDC管理員從[!DNL Marketo Measure]物件建立、讀取、寫入和刪除記錄。
* 「檢視和編輯轉換的潛在客戶許可權集」
   * 這可讓[!DNL Marketo Measure]在銷售機會轉換為聯絡人後裝飾銷售機會。 如果未啟用此許可權集，可能會出現嚴重的資料追蹤差距。

>[!NOTE]
>
>此設定檔可以是系統管理員設定檔的複製品。

步驟2：建立專屬的[!DNL Marketo Measure]使用者，以便追蹤[!DNL Marketo Measure]對您的[!DNL Salesforce]執行個體的影響

1. 將新的[!DNL Marketo Measure]設定檔指派給該使用者。

1. 啟用「行銷使用者」作為使用者層級的許可權。

* [!UICONTROL Marketing User]核取方塊可讓使用者建立行銷活動並使用行銷活動匯入精靈。 如果未選取此選項，使用者只能檢視行銷活動和進階行銷活動設定、編輯單一潛在客戶或聯絡人的行銷活動歷史記錄，以及執行行銷活動報告。 [!DNL Marketo Measure]必須能夠讀取和寫入行銷活動物件。

步驟3：從所有觸發器、工作流程和流程中排除此設定檔

步驟4：登入您的[!DNL Marketo Measure]帳戶並重新授權與新使用者的[!DNL Salesforce]連線

1. 前往apps.bizible.com並使用新的使用者產品[!DNL Salesforce]認證登入。

1. 在&#x200B;**[!UICONTROL My Account]**&#x200B;下拉式清單中選取&#x200B;**[!UICONTROL Settings]**。

1. 在&#x200B;**[!UICONTROL Integrations]**&#x200B;群組中選取&#x200B;**[!UICONTROL Connections]**。

1. 按一下目前連線的[!DNL Salesforce]連線右側的鍵圖示，並選取&#x200B;**使用生產重新授權**。 使用新的使用者憑證再次登入（如果出現提示）。

>[!MORELIKETHIS]
>
>* [整合許可權總覽](/help/api-connections/utilizing-marketo-measures-api-connections/integration-permissions-overview.md){target="_blank"}
>
>* [Adobe Admin Console安裝程式](/help/configuration-and-setup/getting-started-with-marketo-measure/adobe-admin-console-setup.md){target="_blank"}
