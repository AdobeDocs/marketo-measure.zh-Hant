---
unique-page-id: 18874763
description: '"[!DNL Microsoft Dynamics] CRM安裝指南 — Marketo Measure — 產品檔案」'
title: '"[!DNL Microsoft Dynamics] CRM安裝指南」'
exl-id: bc422c98-60bb-49ea-9bd1-c4149ae628b1
source-git-commit: 9de82556ca543aa8e6c53242eacae5c87019886c
workflow-type: tm+mt
source-wordcount: '1305'
ht-degree: 0%

---

# [!DNL Microsoft Dynamics] CRM安裝指南 {#microsoft-dynamics-crm-installation-guide}

>[!NOTE]
>
>您可能會看到指定「[!DNL Marketo Measure]「 」，但仍可在CRM中看到「Bizible」。 我們正致力更新該更新，品牌重塑將很快反映在您的CRM中。

## 支援的版本 {#supported-versions}

[!DNL Marketo Measure] 支援下列 [!DNL Microsoft Dynamics CRM] 版本：

* [!DNL Microsoft Dynamics 2016] （線上和內部部署）
* [!DNL Microsoft Dynamics 365] （線上和內部部署）

對於連接和驗證， [!DNL Marketo Measure] 支援以下Active Directory Federated Services(ADFS)版本：

* ADFS 4.0 - [!DNL Windows Server 2016]
* ADFS 5.0 - [!DNL Windows Server 2019]

## 安裝托管解決方案 {#install-the-managed-solution}

[下載並安裝](assets/marketo-measure-dynamics-extension.zip) Dynamics CRM中的zip檔案。

**[!UICONTROL Settings]** > **[!UICONTROL Customizations]** > **[!UICONTROL Solutions]** > **[!UICONTROL Import]** （按鈕）> **[!UICONTROL Choose File]**.

![](assets/1.png)

>[!NOTE]
>
>以下兩個螢幕擷取畫面可能與您的略有不同，因為這兩個螢幕擷取畫面是在解決方案升級期間擷取的。

![](assets/2.png)

![](assets/3.png)

## [!DNL Marketo Measure] 使用者權限 {#marketo-measure-user-permissions}

建議您建立專屬 [!DNL Marketo Measure] Dynamics中的使用者可讓我們透過匯出和匯入資料，以避免與您CRM中的其他使用者發生任何問題。 請注意使用者名稱、密碼以及端點URL，這將在建立 [!DNL Marketo Measure] 帳戶。

## 安全形色 {#security-roles}

如果貴組織使用Dynamics安全形色，請確保已連接的用戶或專用用戶 [!DNL Marketo Measure] 用戶對所需實體具有足夠的讀/寫權限。

安全形色位於以下位置： **[!UICONTROL Settings]** > **[!UICONTROL Security]** > **[!UICONTROL Security Roles]**.

針對 [!DNL Marketo Measure] 自訂實體時，我們需要所有實體的完整權限。

>[!NOTE]
>
>將關閉銷售機會的用戶也需要完全權限。

![](assets/4.png)

有關Dynamics標準實體，請參閱 [!DNL Marketo Measure] 動態架構文檔。 從高層面講， [!DNL Marketo Measure] 只需讀取特定實體，即可收集適當資料並寫入將隨托管解決方案安裝的自訂欄位。 我們不會建立新的標準記錄，也不會更新任何標準欄位。

## 在頁面配置上包含接觸點： {#include-touchpoints-on-page-layouts}

1. 對於每個實體，導覽至「表單編輯器」。 您可以在下方找到此項目 **[!UICONTROL Settings]** > **[!UICONTROL Customizations]** > **[!UICONTROL Customize the System]** > `[Entity]` > **[!UICONTROL Forms]**. 或者，您可以在檢視記錄時的設定中找到。

   * 要配置的實體：帳戶、機會、聯繫人、銷售機會和促銷活動。

   * 若要設定促銷活動，您必須在 **[!UICONTROL CRM]** > **[!UICONTROL Campaigns]**.

   ![](assets/5.png)

1. 頁面配置：首先新增「[!UICONTROL One Column]「 」區段中的圖磚，以讓接觸點上線。 在該新列中，我們需要將子網格添加到您的Account、Opportunity、Contact和Lead實體中的每個表單中。

   ![](assets/6.png)

   ![](assets/7.png)

1. 選取應在子格線中呈現的物件（購買者歸因接觸點或購買者接觸點），這取決於物件關係。 （可選）按一下「編輯」按鈕，更改將顯示的列。 受管解決方案已設定預設配置。

   購買者歸因接觸點子格線 — 帳戶、商機和連絡人\
   採購員接觸點子網格 — 銷售機會和聯繫人

   ![](assets/8.png)

1. 更新完表單後，請發佈並儲存變更。

## 架構相關考量事項 {#schema-related-considerations}

**收入**

[!DNL Marketo Measure] 依預設會指向標準「實際收入」欄位。 如果您未使用，請說明您需要以自訂工作流程的形式，向解決方案工程師或成功經理報告收入。

**關閉日期**

[!DNL Marketo Measure] 指向「實際關閉日期」欄位，該欄位已開啟。 如果您沒有使用此功能或也使用「估計關閉日期」欄位，請向解決方案工程師或成功經理解釋您的流程。 自訂工作流程可能需要考慮這兩個欄位。

## 設定您的Adobe Admin Console和身分提供者 {#set-up-your-adobe-admin-console-and-identity-provider}

使用 [!DNL Marketo Measure] 是要建立並登入您布建的Adobe Admin Console。 如果您尚未收到包含登入指示的電子郵件，請連絡您的 [!DNL Marketo Measure] 客戶代表。

作為Adobe套裝中的產品， [!DNL Marketo Measure] 運用Adobe Admin Console for Identity Management的完整功能。 更多資源可以是 [此處找到](https://helpx.adobe.com/tw/enterprise/using/admin-console.html).

建議您檢閱所有可用的資源、最佳實務和選項 [Identity Management](https://helpx.adobe.com/enterprise/using/set-up-identity.html).

如需在Adobe Admin Console中設定Identity Management的指引和檢閱，請洽詢您的 [!DNL Marketo Measure] 客戶代表。

為了方便使用者驗證和授權 [!DNL Marketo Measure] 例項，Adobe Admin Console中需要下列步驟：

**設定 [!DNL Marketo Measure] 產品卡**

存取Adobe Admin Console時，您會看到 [!DNL Marketo Measure] 概述區段中顯示的產品例項。

![](assets/microsoft-dynamics-crm-installation-guide-8a.png)

按一下 [!DNL Marketo Measure] 產品卡會顯示 [!DNL Marketo Measure] 例項。 依預設，每個 [!DNL Marketo Measure] 執行個體的設定檔首碼為「[!DNL Marketo Measure]&#39;。 新增至此執行個體或任何其他設定檔的管理員或使用者都能登入 [!DNL Marketo Measure].

![](assets/microsoft-dynamics-crm-installation-guide-8b.png)

在 [!DNL Marketo Measure] 產品例項。

若要開始新增可存取的使用者 [!DNL Marketo Measure]，請參閱 [新增 [!DNL Marketo Measure] 管理員和 [!DNL Marketo Measure] 使用者](#adding-marketo-measure-admins-and-marketo-measure-users) 一節。

## 新增 [!DNL Marketo Measure] 管理員和 [!DNL Marketo Measure] 使用者 {#adding-marketo-measure-admins-and-marketo-measure-users}

下一步是授予 [!DNL Marketo Measure] 應用程式。 您可以在的管理員和使用者目錄中完成此作業 [!DNL Marketo Measure] 產品卡。

| 使用者類型 | 說明 |
|---|---|
| 管理員 | 這些是管理員和高級用戶 [!DNL Marketo Measure] 具有完全更新和管理能力的應用程式 [!DNL Marketo Measure] — 特定配置選項 |
| 使用者 | 這些是 [!DNL Marketo Measure] 在中具有唯讀權限的應用程式 [!DNL Marketo Measure] 應用程式 |

將使用者新增至其個別群組時，您會看到 [已列出身分類型](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/set-up-identity.ug.html).

>[!NOTE]
>
>為了成為 [!DNL Marketo Measure] 管理員 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"})，則使用者必須新增為使用者 _和_ 管理員 [!DNL Marketo Measure] 中的產品設定檔 [!DNL Marketo Measure] 產品卡。

**登入[!DNL Marketo Measure]**

將使用者新增至產品設定檔後，他們就能存取 [!DNL Marketo Measure] 例項 **使用Adobe ID登入** 選項 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}.

![](assets/microsoft-dynamics-crm-installation-guide-15.png)

## 設定連線和資料提供者 {#configuring-your-connections-and-data-providers}

登入後 [!DNL Marketo Measure] 應用程式，並已在Adobe Admin Console中設定為使用者，下一步是設定您的各種資料連線。

**CRM作為資料提供者**

1. 在 [!DNL Marketo Measure] 帳戶，按一下 **[!UICONTROL My Account]** 下拉式清單並選取 **[!UICONTROL Settings]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-16.png)

1. 在 [!UICONTROL Integrations] 在左側導覽列中，按一下 **[!UICONTROL Connections]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-17.png)

1. 按一下 **[!UICONTROL Set Up New CRM Connection]** 按鈕。

   ![](assets/microsoft-dynamics-crm-installation-guide-18.png)

1. 旁邊 [!UICONTROL Microsoft Dynamics CRM]，按一下 **[!UICONTROL Connect]** 按鈕。

   ![](assets/microsoft-dynamics-crm-installation-guide-19.png)

1. 選擇 [!UICONTROL Credentials] 或 [!UICONTROL OAuth].

   ![](assets/microsoft-dynamics-crm-installation-guide-20.png)

   >[!NOTE]
   >
   >如需OAuth的詳細資訊，請造訪 [這篇文章](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/oauth-with-azure-active-directory-for-dynamics-crm.md). 若您對此程式有任何疑問，請聯絡您的 [!DNL Marketo Measure] 客戶代表。

1. 在此示例中，我們選擇了憑據。 輸入您的憑證，然後按一下 **[!UICONTROL Next]**.

連線之後，您會在CRM/MAP連線清單中看到Dynamics連線的詳細資訊。

**廣告帳戶連線**

連結廣告帳戶的方式 [!DNL Marketo Measure]，首先請造訪 [!UICONTROL Connections] 標籤 [!DNL Marketo Measure] 應用程式。

1. 請依照上述步驟1和2操作 _CRM作為資料提供者_ 區段。

1. 按一下 **[!UICONTROL Set up New CRM Connection]** 按鈕。

   ![](assets/microsoft-dynamics-crm-installation-guide-21.png)

1. 選取所需的平台。

   ![](assets/microsoft-dynamics-crm-installation-guide-22.png)

**[!DNL Marketo Measure]Javascript**

為了 [!DNL Marketo Measure] 若要追蹤您的Web活動，請執行多個步驟進行設定。

1. 按一下 **[!UICONTROL My Account]** 下拉式清單並選取 **[!UICONTROL Account Configuration]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-23.png)

1. 輸入您的電話號碼。 在「網站」中，輸入要用於的主根域 [!DNL Marketo Measure] 追蹤。 按一下 **[!UICONTROL Save]** 時才能使用。

   ![](assets/microsoft-dynamics-crm-installation-guide-24.png)

   >[!NOTE]
   >
   >若要新增多個根網域，請連絡您的 [!DNL Marketo Measure] 客戶代表。

1. 此 [[!DNL Marketo Measure] JavaScript](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md) 之後，才需要將其放置在整個網站和登陸頁面。 建議您在登錄頁面標題內以硬式編碼撰寫指令碼，或透過Tag Management系統新增，例如 [Google Tag Manager](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md).

   >[!NOTE]
   >
   >依預設， [!DNL Marketo Measure] 每次工作將資料傳送至您的CRM時，會根據每個API評分匯出200筆記錄。 對於大部分的客戶，這可提供所使用API評分之間的最佳平衡 [!DNL Marketo Measure] 和CRM的CPU資源需求。 不過，對於具有複雜CRM設定（例如工作流程和觸發器）的客戶，較小的批次大小可能有助於改善CRM效能。 為此， [!DNL Marketo Measure] 允許客戶配置CRM導出批大小。 此設定位於 [!DNL Marketo Measure] Web應用程式和客戶可以選擇200（預設）、100、50或25的批量大小。
   >
   >修改此設定時，請記住，較小的批次大小將會佔用您CRM的更多API評分。 建議您只有在CRM中遇到CPU逾時或CPU負載高時，才減少批次大小。

   >[!NOTE]
   >
   >當您停用將資料匯出至Dynamics的Marketo Measure時，它不會移除任何現有資料。 如需移除現有資料的協助，請聯絡Dynamics支援。
