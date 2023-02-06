---
description: '"[!DNL Marketo Measure] 安裝和設定Salesforce包 —  [!DNL Marketo Measure]  — 產品檔案」'
title: '"[!DNL Marketo Measure] [!DNL Salesforce] 軟體包安裝和設定」'
exl-id: ed58bc1e-cfb0-48db-aa53-96204e12de2e
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 0%

---

# [!DNL Marketo Measure] 安裝和設定Salesforce包 {#marketo-measure-salesforce-package-installation-and-set-up}

安裝之前 [!DNL Marketo Measure] [!DNL Salesforce] 基本套件時，您需要判斷是否要先在 [!DNL Salesforce] 沙箱，再移至您的Salesforce生產執行個體。

>[!NOTE]
>
>一旦您 [!DNL Marketo Measure] 帳戶已連線至 [!DNL Salesforce] 生產執行個體時，您無法向後移動並連線至沙箱。 此外， [!DNL Marketo Measure] 帳戶只能連接到一個 [!DNL Salesforce] 生產例項。

此 [!DNL Marketo Measure] 基本包包含：

* 7自訂 [!DNL Marketo Measure] 物件
* 自訂 [!DNL Marketo Measure] 欄位
* 25 [!DNL Stock] 報表

[!DNL Marketo Measure] 能讀取標準 [!DNL Salesforce] 但是，對象、欄位和記錄 [!DNL Marketo Measure] 不會更新或推送資料給他們。 由 [!DNL Marketo Measure] Javascript會在 [!DNL Marketo Measure] 自訂物件和欄位。

請依照下列步驟安裝 [!DNL Marketo Measure Salesforce] 基本包。

1. 使用無痕瀏覽器，前往 [Salesforce Appexchange](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target="_blank"} 並登入。

1. 在 [!DNL Marketo Measure] 在沙箱或生產環境中套件。

1. 登入 [!DNL Salesforce] 身為管理員。

1. 選擇 **[!UICONTROL Install]所有用戶**.

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-1.png)

1. 安裝完成後，您即可檢視。

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-2.png)

完成安裝後，您可以更新 [[!DNL Salesforce] 頁面配置](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md){target="_blank"} 和 [!DNL Marketo Measure] 欄位。

>[!NOTE]
>
>閱讀 [!DNL Marketo Measure] 已建立和 [如何使用](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md){target="_blank"}.

## 安裝 [!DNL Marketo Measure] 控制面板套件 {#install-marketo-measure-dashboard-package}

此 [!UICONTROL Dashboard] 擴充功能套件包含三個預先建立的控制面板。 建議您安裝 [!UICONTROL within] 適用於所有使用者的生產環境。

1. 從安裝套件 [[!DNL Salesforce] Appexchange](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t610000001jI6){target="_blank"}.

1. 選取 **[!UICONTROL Install for All Users]**.

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-3.png)

## 建立 [!DNL Marketo Measure] 設定檔與使用者 {#creating-a-marketo-measure-profile-and-user}

[!DNL Marketo Measure] 通過連接的 [!DNL Salesforce] 使用者 [!DNL Marketo Measure] 應用程式。

若要推送接觸點資料至您的 [!DNL Salesforce] 例項中，連線的使用者必須擁有 [!DNL Marketo Measure] 自訂物件（例如購買者接觸點和購買者歸因接觸點）以及標準 [!DNL Salesforce] 對象，如Lead和Contact。

建立 [!DNL Marketo Measure] 設定檔，以確保將資料推送至Salesforce時不會遇到驗證錯誤。

步驟1:建立特定 [!DNL Marketo Measure] 設定檔

1. 指派下列權限：

* &quot;[!DNL Marketo Measure] 管理員權限集」
   * 托管權限集使SFDC管理員能夠建立、讀取、寫入、刪除記錄 [!DNL Marketo Measure] 對象。
* &quot;查看和編輯轉換的銷售機會權限集&quot;
   * 這允許 [!DNL Marketo Measure] 以裝飾銷售線索。 如果未啟用此權限集，可能會存在重大資料追蹤差距。

>[!NOTE]
>
>此設定檔可以是原地複製的系統管理員設定檔。

步驟2:建立專用 [!DNL Marketo Measure] 使用者，以便追蹤 [!DNL Marketo Measure] 在 [!DNL Salesforce] 執行個體

1. 指派新 [!DNL Marketo Measure] 向該使用者設定檔。

1. 啟用「行銷使用者」作為使用者層級的權限。

* 此 [!UICONTROL Marketing User] 核取方塊可讓使用者建立促銷活動，並使用促銷活動匯入精靈。 如果未選取此選項，則使用者只能檢視促銷活動和進階促銷活動設定、編輯單一銷售機會或聯絡人的促銷活動歷史記錄，以及執行促銷活動報表。 [!DNL Marketo Measure] 需要讀取和寫入行銷活動物件的功能。

步驟3:從所有觸發器、工作流程和程式中排除此設定檔

步驟4:登入您的 [!DNL Marketo Measure] 帳戶並重新授權 [!DNL Salesforce] 與新用戶的連接

1. 前往apps.bizible.com ，並使用新的使用者生產環境登入 [!DNL Salesforce] 憑證。

1. 選擇 **[!UICONTROL Settings]** 在 **[!UICONTROL My Account]** 下拉式清單。

1. 選擇 **[!UICONTROL Connections]** 在 **[!UICONTROL Integrations]** 分組。

1. 按一下當前已連接的右側的鍵表徵圖 [!DNL Salesforce] 連接和選擇 **使用生產環境重新授權**. 再次使用新的用戶憑據登錄（如果出現提示）。
