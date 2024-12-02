---
unique-page-id: 18874763
description: '[!DNL Microsoft Dynamics] CRM安裝指南 — Marketo Measure — 產品檔案'
title: '[!DNL Microsoft Dynamics] CRM安裝指南'
exl-id: bc422c98-60bb-49ea-9bd1-c4149ae628b1
feature: Installation, Microsoft Dynamics
source-git-commit: 706f60a3b35e524da816b1d70abd363f0f02a1ba
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 0%

---

# [!DNL Microsoft Dynamics] CRM安裝指南 {#microsoft-dynamics-crm-installation-guide}

>[!NOTE]
>
>您可能會在檔案中看到指定&quot;[!DNL Marketo Measure]&quot;的說明，但在您的CRM中仍會看到&quot;Bizible&quot;。 我們正致力於更新此專案，品牌重塑將很快反映在您的CRM中。

## 支援的版本 {#supported-versions}

[!DNL Marketo Measure]支援下列[!DNL Microsoft Dynamics CRM]版本：

* [!DNL Microsoft Dynamics 2016] （線上和內部部署）
* [!DNL Microsoft Dynamics 365] （線上和內部部署）

對於連線和驗證，[!DNL Marketo Measure]支援下列Active Directory Federated Services (ADFS)版本：

* ADFS 4.0 - [!DNL Windows Server 2016]
* ADFS 5.0 - [!DNL Windows Server 2019]

## 安裝受管理的解決方案 {#install-the-managed-solution}

[下載並安裝](assets/marketo-measure-dynamics-extension.zip) Dynamics CRM中的zip檔案。

**[!UICONTROL Settings]** > **[!UICONTROL Customizations]** > **[!UICONTROL Solutions]** > **[!UICONTROL Import]** （按鈕） > **[!UICONTROL Choose File]**。

![](assets/1.png)

>[!NOTE]
>
>以下兩個熒幕擷取畫面可能會與您的熒幕擷取畫面稍有不同，因為在解決方案升級時擷取了這些畫面。

![](assets/2.png)

![](assets/3.png)

## 建立[!DNL Marketo Measure]使用者 {#creating-a-marketo-measure-user}

建議您在Dynamics中建立專用的Marketo Measure使用者作為「應用程式使用者」，透過匯出和匯入資料，以避免與您CRM中的其他使用者發生任何問題。 記下建立[!DNL Marketo Measure]帳戶時使用的使用者名稱和密碼，以及端點URL。

## 安全性角色 {#security-roles}

如果您的組織使用Dynamics安全性角色，請確定已連線的使用者或專用的[!DNL Marketo Measure]使用者具有所需實體的足夠讀取/寫入許可權。

安全性角色位於此處： **[!UICONTROL Settings]** > **[!UICONTROL Security]** > **[!UICONTROL Security Roles]**。

對於[!DNL Marketo Measure]個自訂實體，我們需要所有實體的完整許可權。

除了標準實體的讀取/寫入許可權外，還需要行銷活動「建立」許可權。

>[!NOTE]
>
>關閉商機的使用者也需要完整許可權。

![](assets/4.png)

若為Dynamics標準實體，請參閱[!DNL Marketo Measure] Dynamics結構描述檔案。 從高層面來看，[!DNL Marketo Measure]會讀取特定實體以收集適當的資料，並寫入與受管理解決方案一起安裝的自訂欄位。 不會建立標準記錄，也不會更新標準欄位。

## 在頁面配置中加入接觸點： {#include-touchpoints-on-page-layouts}

1. 對於每個實體，導覽至表單編輯器。 您可以在&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Customizations]** > **[!UICONTROL Customize the System]** > `[Entity]` > **[!UICONTROL Forms]**&#x200B;下找到此專案。 或者，您可以在檢視記錄時透過設定找到它。

   * 要設定的實體：客戶、商機、聯絡人、銷售線索和促銷活動。

   * 若要設定Campaigns，您必須在&#x200B;**[!UICONTROL CRM]** > **[!UICONTROL Campaigns]**&#x200B;中開啟[Campaign同步]選項。

   ![](assets/5.png)

1. 頁面配置：首先，在您想要接觸點存在的區段中新增&quot;[!UICONTROL One Column]&quot;圖磚。 在該新欄中，我們需要在您的Account、Opportunity、Contact和Lead實體內的每個表單中新增一個子格線。

   ![](assets/6.png)

   ![](assets/7.png)

1. 選取應在子格線中呈現的物件（「購買者歸因接觸點」或「購買者接觸點」），這取決於物件關係。 或者，按一下編輯按鈕來變更顯示的欄。 預設版面配置是由受管理的解決方案所設定。

   Buyer Attribution Touchpoint子格線 — 帳戶、機會和連絡人\
   Buyer Touchpoint子網路 — 銷售機會與聯絡人

   ![](assets/8.png)

1. 更新完表單後，請發佈並儲存變更。

## 結構描述相關的考量事項 {#schema-related-considerations}

**收入**

根據預設，[!DNL Marketo Measure]指向標準的實際收入欄位。 如果您未使用此專案，請說明您需要如何向解決方案工程師或成功經理報告收入，以作為自訂工作流程。

**關閉日期**

[!DNL Marketo Measure]指向立即可用的實際關閉日期欄位。 如果您未使用此欄位或同時使用預估關閉日期欄位，請向您的解決方案工程師或成功經理說明您的流程。 可能需要自訂工作流程來說明這兩個欄位。

## 設定連線和資料提供者 {#configuring-your-connections-and-data-providers}

在您登入[!DNL Marketo Measure]應用程式並在Adobe Admin Console中設定為使用者後，下一步就是設定您的各種資料連線。

**CRM做為資料提供者**

1. 在您的[!DNL Marketo Measure]帳戶中，按一下&#x200B;**[!UICONTROL My Account]**&#x200B;下拉式清單並選取&#x200B;**[!UICONTROL Settings]**。

   ![](assets/microsoft-dynamics-crm-installation-guide-16.png)

1. 在左側導覽的[!UICONTROL Integrations]下，按一下&#x200B;**[!UICONTROL Connections]**。

   ![](assets/microsoft-dynamics-crm-installation-guide-17.png)

1. 按一下&#x200B;**[!UICONTROL Set Up New CRM Connection]**&#x200B;按鈕。

   ![](assets/microsoft-dynamics-crm-installation-guide-18.png)

1. 在[!UICONTROL Microsoft Dynamics CRM]旁邊，按一下&#x200B;**[!UICONTROL Connect]**&#x200B;按鈕。

   ![](assets/microsoft-dynamics-crm-installation-guide-19.png)

1. 選取「[!UICONTROL Credentials]」或「[!UICONTROL OAuth]」。

   ![](assets/microsoft-dynamics-crm-installation-guide-20.png)

   >[!NOTE]
   >
   >如需有關OAuth的詳細資訊，請瀏覽[本文章](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/oauth-with-azure-active-directory-for-dynamics-crm.md)。 如果您對程式有任何疑問，請聯絡您的[!DNL Marketo Measure]客戶代表。

1. 在此範例中，我們已選取「認證」。 輸入您的認證並按一下&#x200B;**[!UICONTROL Next]**。

連線之後，您會在CRM/MAP連線清單中看到您的Dynamics連線的詳細資料。

**廣告帳戶連線**

若要將您的廣告帳戶與[!DNL Marketo Measure]連線，請先造訪[!DNL Marketo Measure]應用程式中的[!UICONTROL Connections]索引標籤。

1. 請依照上述&#x200B;_CRM as a Data Provider_&#x200B;區段中的步驟1和2操作。

1. 按一下&#x200B;**[!UICONTROL Set up New CRM Connection]**&#x200B;按鈕。

   ![](assets/microsoft-dynamics-crm-installation-guide-21.png)

1. 選取您想要的平台。

   ![](assets/microsoft-dynamics-crm-installation-guide-22.png)

**[!DNL Marketo Measure]Javascript**

若要讓[!DNL Marketo Measure]追蹤您的網路活動，設定需要執行多個步驟。

1. 按一下&#x200B;**[!UICONTROL My Account]**&#x200B;下拉式清單，然後選取&#x200B;**[!UICONTROL Account Configuration]**。

   ![](assets/microsoft-dynamics-crm-installation-guide-23.png)

1. 輸入您的電話號碼。 針對網站，輸入您的網站上用於[!DNL Marketo Measure]追蹤的主要根網域。 完成時，按一下&#x200B;**[!UICONTROL Save]**。

   ![](assets/microsoft-dynamics-crm-installation-guide-24.png)

   >[!NOTE]
   >
   >若要新增多個根網域，請聯絡您的[!DNL Marketo Measure]客戶代表。

1. 然後必須將[[!DNL Marketo Measure] JavaScript](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md)放置在整個網站和登入頁面上。 建議將指令碼硬式編碼於登入頁面的標題內，或透過Tag Management系統(例如[Google Tag Manager](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md))新增。

   >[!NOTE]
   >
   >依預設，每次工作將資料傳送至您的CRM時，[!DNL Marketo Measure]會針對每個API點數匯出200筆記錄。 對於大多數客戶而言，這會在[!DNL Marketo Measure]所消耗的API點數與CRM上的CPU資源需求之間提供最佳平衡。 不過，對於具有複雜CRM設定（例如工作流程和觸發器）的客戶，較小的批次大小可能有助於改善CRM效能。 為此，[!DNL Marketo Measure]允許客戶設定CRM匯出批次大小。 此設定可在[!DNL Marketo Measure] Web應用程式的「設定> CRM >一般」頁面上取得，客戶可以選擇批次大小200 （預設）、100、50或25。
   >
   >修改此設定時，請記住，較小的批次大小會消耗您CRM的更多API積分。 建議您只有在CRM中遇到CPU逾時或CPU負載過高時才減少批次大小。

   >[!NOTE]
   >
   >當您停用Marketo Measure將資料匯出至Dynamics時，並不會移除任何現有的資料。 如需移除現有資料的協助，請連絡Dynamics支援。

   >[!MORELIKETHIS]
   >
   >[錯誤通知](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}
