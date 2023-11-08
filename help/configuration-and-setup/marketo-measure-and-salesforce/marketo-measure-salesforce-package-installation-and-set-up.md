---
description: '"[!DNL Marketo Measure] Salesforce封裝安裝及設定 —  [!DNL Marketo Measure]  — 產品檔案」'
title: '"[!DNL Marketo Measure] [!DNL Salesforce] 封裝安裝及設定」'
exl-id: ed58bc1e-cfb0-48db-aa53-96204e12de2e
feature: Installation, Salesforce
source-git-commit: 68eb5bf83d589c9161490b1772551ed46a9ce444
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 0%

---

# [!DNL Marketo Measure] Salesforce套件安裝和設定 {#marketo-measure-salesforce-package-installation-and-set-up}

安裝之前 [!DNL Marketo Measure] [!DNL Salesforce] 基礎套件，您必須先判斷是否要在 [!DNL Salesforce] 沙箱，然後再移動至您的Salesforce生產執行個體。

>[!NOTE]
>
>一旦您的 [!DNL Marketo Measure] 帳戶已連線至 [!DNL Salesforce] 生產執行個體時，您無法回溯並連線至沙箱。 此外， [!DNL Marketo Measure] 帳戶只能連線至一個 [!DNL Salesforce] 生產執行個體。

此 [!DNL Marketo Measure] 基礎封裝包含：

* 7個自訂 [!DNL Marketo Measure] 物件
* 自訂 [!DNL Marketo Measure] 欄位
* 25 [!DNL Stock] 報表

[!DNL Marketo Measure] 能夠讀取標準內容 [!DNL Salesforce] 物件、欄位和記錄， [!DNL Marketo Measure] 絕對不會更新或推送資料給他們。 收集的所有資料 [!DNL Marketo Measure] Javascript將顯示在 [!DNL Marketo Measure] 自訂物件和欄位。

請依照下列步驟安裝 [!DNL Marketo Measure Salesforce] 基礎封裝。

1. 使用無痕瀏覽器，前往 [Salesforce Appexchange](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target="_blank"} 並登入。

1. 在中安裝 [!DNL Marketo Measure] 封裝在沙箱或生產環境中。

1. 登入 [!DNL Salesforce] 身為管理員。

1. 選取 **[!UICONTROL Install]適用於所有使用者**.

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-1.png)

1. 安裝完成後，即可檢視。

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-2.png)

完成安裝後，您可以更新 [[!DNL Salesforce] 頁面配置](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md){target="_blank"} 使用 [!DNL Marketo Measure] 欄位（如有需要）。

>[!NOTE]
>
>閱讀關於 [!DNL Marketo Measure] 許可權集已建立和 [如何使用](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md){target="_blank"}.

## 建立 [!DNL Marketo Measure] 設定檔和使用者 {#creating-a-marketo-measure-profile-and-user}

[!DNL Marketo Measure] 透過已連線的傳送和接收資料 [!DNL Salesforce] 使用者在 [!DNL Marketo Measure] 應用程式。

為了將接觸點資料推送至您的 [!DNL Salesforce] 執行個體，則連線的使用者必須有權存取 [!DNL Marketo Measure] 自訂物件（例如購買者接觸點和購買者歸因接觸點）以及標準 [!DNL Salesforce] 物件，例如「銷售機會」和「聯絡人」。

建立 [!DNL Marketo Measure] 設定檔以確保您在推送資料至Salesforce時不會發生驗證錯誤。

步驟1：建立特定的 [!DNL Marketo Measure] 設定檔

1. 指派下列許可權：

* &quot;[!DNL Marketo Measure] 管理員許可權集」
   * Managed許可權集可讓SFDC管理員從建立、讀取、寫入和刪除記錄 [!DNL Marketo Measure] 物件。
* 「檢視和編輯轉換的潛在客戶許可權集」
   * 這允許 [!DNL Marketo Measure] 在銷售機會轉換為聯絡人後進行裝飾。 如果未啟用此許可權集，可能會出現嚴重的資料追蹤差距。

>[!NOTE]
>
>此設定檔可以是系統管理員設定檔的複製品。

步驟2：建立專用的 [!DNL Marketo Measure] 使用者，以便您追蹤 [!DNL Marketo Measure] 在您的 [!DNL Salesforce] 例項

1. 指派新的 [!DNL Marketo Measure] 該使用者的設定檔。

1. 啟用「行銷使用者」作為使用者層級的許可權。

* 此 [!UICONTROL Marketing User] 核取方塊可讓使用者建立行銷活動並使用Campaign匯入精靈。 如果未選取此選項，使用者只能檢視行銷活動和進階行銷活動設定、編輯單一潛在客戶或聯絡人的行銷活動歷史記錄，以及執行行銷活動報告。 [!DNL Marketo Measure] 需要能夠讀取和寫入campaign物件。

步驟3：從所有觸發器、工作流程和流程中排除此設定檔

步驟4：登入 [!DNL Marketo Measure] 帳戶並重新授權 [!DNL Salesforce] 與新使用者的連線

1. 前往apps.bizible.com並使用新使用者產品登入 [!DNL Salesforce] 認證。

1. 選取 **[!UICONTROL Settings]** 在 **[!UICONTROL My Account]** 下拉式清單。

1. 選取 **[!UICONTROL Connections]** 在 **[!UICONTROL Integrations]** 分組。

1. 按一下目前連線右側的按鍵圖示 [!DNL Salesforce] 連線並選取 **透過生產環境重新授權**. 使用新的使用者憑證再次登入（如果出現提示）。

>[!MORELIKETHIS]
>
>[Adobe Admin Console設定](/help/configuration-and-setup/getting-started-with-marketo-measure/adobe-admin-console-setup.md){target="_blank"}
