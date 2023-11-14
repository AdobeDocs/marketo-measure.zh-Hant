---
unique-page-id: 18874763
description: '"[!DNL Microsoft Dynamics] CRM安裝指南 — Marketo Measure — 產品檔案」'
title: '"[!DNL Microsoft Dynamics] CRM安裝指南」'
exl-id: bc422c98-60bb-49ea-9bd1-c4149ae628b1
feature: Installation, Microsoft Dynamics
source-git-commit: 86d610d07ab699266ba68a6f2eaf7c7981e62019
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 0%

---

# [!DNL Microsoft Dynamics] CRM安裝指南 {#microsoft-dynamics-crm-installation-guide}

>[!NOTE]
>
>您可能會看到指定&#39;&#39;的說明[!DNL Marketo Measure]&quot;，但仍在您的CRM中看到「Bizible」。 我們正致力於更新此專案，品牌重塑將很快反映在您的CRM中。

## 支援的版本 {#supported-versions}

[!DNL Marketo Measure] 支援下列專案 [!DNL Microsoft Dynamics CRM] 版本：

* [!DNL Microsoft Dynamics 2016] （線上和內部部署）
* [!DNL Microsoft Dynamics 365] （線上和內部部署）

對於連線和驗證， [!DNL Marketo Measure] 支援下列Active Directory Federated Services (ADFS)版本：

* ADFS 4.0 - [!DNL Windows Server 2016]
* ADFS 5.0 - [!DNL Windows Server 2019]

## 安裝受管理的解決方案 {#install-the-managed-solution}

[下載並安裝](assets/marketo-measure-dynamics-extension.zip) Dynamics CRM內的zip檔案。

**[!UICONTROL Settings]** > **[!UICONTROL Customizations]** > **[!UICONTROL Solutions]** > **[!UICONTROL Import]** （按鈕） > **[!UICONTROL Choose File]**.

![](assets/1.png)

>[!NOTE]
>
>以下兩個熒幕擷取畫面可能會與您的熒幕擷取畫面稍有不同，因為在解決方案升級時擷取了這些畫面。

![](assets/2.png)

![](assets/3.png)

## 建立 [!DNL Marketo Measure] 使用者 {#creating-a-marketo-measure-user}

建議您在Dynamics中建立專屬的Marketo Measure使用者作為「應用程式使用者」，以便我們透過匯出和匯入資料，進而避免您的CRM中其他使用者發生任何問題。 記下使用者名稱和密碼，以及端點URL，以便在建立 [!DNL Marketo Measure] 帳戶。

## 安全性角色 {#security-roles}

如果您的組織使用Dynamics安全性角色，請確定已連線的使用者或專用的 [!DNL Marketo Measure] 使用者具有所需實體的足夠讀取/寫入許可權。

安全性角色位於此處： **[!UICONTROL Settings]** > **[!UICONTROL Security]** > **[!UICONTROL Security Roles]**.

的 [!DNL Marketo Measure] 自訂實體，我們需要所有實體的完整許可權。

>[!NOTE]
>
>即將關閉商機的使用者也需要完整許可權。

![](assets/4.png)

若為Dynamics標準實體，請參閱 [!DNL Marketo Measure] 動態結構描述檔案。 在高層面上， [!DNL Marketo Measure] 只需讀取特定實體，即可收集適當的資料，並寫入自訂欄位，以隨受管理的解決方案一併安裝。 我們不會建立新的標準記錄，也不會更新任何標準欄位。

## 在頁面配置中加入接觸點： {#include-touchpoints-on-page-layouts}

1. 對於每個實體，導覽至表單編輯器。 您可以在下方找到此專案 **[!UICONTROL Settings]** > **[!UICONTROL Customizations]** > **[!UICONTROL Customize the System]** > `[Entity]` > **[!UICONTROL Forms]**. 或者，您可以在檢視記錄時透過設定找到它。

   * 要設定的實體：客戶、商機、聯絡人、銷售線索和促銷活動。

   * 若要設定Campaigns，您必須開啟中的「Campaign同步」選項 **[!UICONTROL CRM]** > **[!UICONTROL Campaigns]**.

   ![](assets/5.png)

1. 版面配置：請先新增&quot;[!UICONTROL One Column]「在您想要接觸點存在的區段拼貼。 在該新欄中，我們需要在您的Account、Opportunity、Contact和Lead實體內的每個表單中新增一個子網格。

   ![](assets/6.png)

   ![](assets/7.png)

1. 選取應在子格線中呈現的物件（「購買者歸因接觸點」或「購買者接觸點」），這取決於物件關係。 或者，按一下「編輯」按鈕來變更顯示的欄。 受管理的解決方案已設定預設版面。

   購買者歸因接觸點子格線 — 帳戶、商機和連絡人\
   購買者接觸點子格線 — 銷售機會與聯絡人

   ![](assets/8.png)

1. 更新完表單後，請發佈並儲存變更。

## 結構描述相關的考量事項 {#schema-related-considerations}

**收入**

[!DNL Marketo Measure] 依預設，指向標準的實際收入欄位。 如果您沒有使用此功能，請說明您將需要如何向解決方案工程師或成功經理報告收入作為自訂工作流程。

**關閉日期**

[!DNL Marketo Measure] 指向立即可用的實際關閉日期欄位。 如果您未使用此欄位或同時使用預估關閉日期欄位，請向您的解決方案工程師或成功經理說明您的流程。 可能需要使用自訂工作流程來說明這兩個欄位。

## 設定連線和資料提供者 {#configuring-your-connections-and-data-providers}

在您登入 [!DNL Marketo Measure] 應用程式並且已在Adobe Admin Console中設定為使用者，下一步是設定各種資料連線。

**CRM作為資料提供者**

1. 在您的 [!DNL Marketo Measure] 帳戶，按一下 **[!UICONTROL My Account]** 下拉式清單並選取 **[!UICONTROL Settings]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-16.png)

1. 在 [!UICONTROL Integrations] 在左側導覽中，按一下 **[!UICONTROL Connections]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-17.png)

1. 按一下 **[!UICONTROL Set Up New CRM Connection]** 按鈕。

   ![](assets/microsoft-dynamics-crm-installation-guide-18.png)

1. 旁邊 [!UICONTROL Microsoft Dynamics CRM]，按一下 **[!UICONTROL Connect]** 按鈕。

   ![](assets/microsoft-dynamics-crm-installation-guide-19.png)

1. 選取 [!UICONTROL Credentials] 或 [!UICONTROL OAuth].

   ![](assets/microsoft-dynamics-crm-installation-guide-20.png)

   >[!NOTE]
   >
   >如需OAuth的詳細資訊，請造訪 [本文](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/oauth-with-azure-active-directory-for-dynamics-crm.md). 如果您對程式有任何疑問，請聯絡您的 [!DNL Marketo Measure] 客戶代表。

1. 在此範例中，我們已選取「認證」。 輸入您的認證，然後按一下 **[!UICONTROL Next]**.

連線後，您會在CRM/MAP連線清單中看到Dynamics連線的詳細資料。

**廣告帳戶連線**

若要將您的Ad帳戶與連結 [!DNL Marketo Measure]，首先請造訪 [!UICONTROL Connections] 標籤內的欄位 [!DNL Marketo Measure] 應用程式。

1. 請依照上述步驟1和2操作 _CRM作為資料提供者_ 區段。

1. 按一下 **[!UICONTROL Set up New CRM Connection]** 按鈕。

   ![](assets/microsoft-dynamics-crm-installation-guide-21.png)

1. 選取您想要的平台。

   ![](assets/microsoft-dynamics-crm-installation-guide-22.png)

**[!DNL Marketo Measure]Javascript**

為了 [!DNL Marketo Measure] 若要追蹤您的網路活動，設定需執行多個步驟。

1. 按一下 **[!UICONTROL My Account]** 下拉式清單並選取 **[!UICONTROL Account Configuration]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-23.png)

1. 輸入您的電話號碼。 針對網站，輸入您的主要根網域，此網域將用於 [!DNL Marketo Measure] 在您的網站上進行追蹤。 按一下 **[!UICONTROL Save]** 完成時。

   ![](assets/microsoft-dynamics-crm-installation-guide-24.png)

   >[!NOTE]
   >
   >若要新增多個根網域，請聯絡您的 [!DNL Marketo Measure] 客戶代表。

1. 此 [[!DNL Marketo Measure] JavaScript](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md) 然後需要跨整個網站和登入頁面放置。 我們建議您在登入頁面標題中以硬式編碼撰寫指令碼，或透過Tag Management系統新增，例如 [Google Tag Manager](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md).

   >[!NOTE]
   >
   >根據預設， [!DNL Marketo Measure] 每次工作將資料傳送至您的CRM時，都會匯出每個API評分200筆記錄。 對於大多數客戶而言，這可提供以下專案所耗用的API積分之間的最佳平衡 [!DNL Marketo Measure] 和CRM的CPU資源需求。 不過，對於具有複雜CRM設定（例如工作流程和觸發器）的客戶，較小的批次大小可能有助於改善CRM效能。 為此， [!DNL Marketo Measure] 允許客戶設定CRM匯出批次大小。 此設定位於「 」中的「設定> CRM >一般」頁面 [!DNL Marketo Measure] Web應用程式和客戶可以選擇批次大小200 （預設）、100、50或25。
   >
   >修改此設定時，請牢記，較小的批次大小將使用來自CRM的更多API積分。 建議您只有在CRM中遇到CPU逾時或CPU負載過高時，才減少批次大小。

   >[!NOTE]
   >
   >當您停用Marketo Measure將資料匯出至Dynamics時，並不會移除任何現有的資料。 如需移除現有資料的協助，請連絡Dynamics支援。
