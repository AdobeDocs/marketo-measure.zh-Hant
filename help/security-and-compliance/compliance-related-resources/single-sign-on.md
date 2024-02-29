---
unique-page-id: 18874761
description: 單一登入 —  [!DNL Marketo Measure]
title: 單一登入
exl-id: a328e9cb-8352-4693-8a44-533e08f1a29c
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '1267'
ht-degree: 0%

---

# 單一登入 {#single-sign-on}

SSO （單一登入）的SAML （安全性宣告標籤語言）讓使用者可以在登入時透過公司的身分提供者進行驗證 [!DNL Marketo Measure] 應用程式。 SSO僅允許使用者驗證一次，無需驗證個別應用程式。 企業客戶必須使用SAML，因為並非所有使用者都會 [!DNL Salesforce] 或 [!DNL Google] 組織內的帳戶。 若要進行縮放， [!DNL Marketo Measure] 已開發可支援公司身分提供者的SAML解決方案。

>[!CAUTION]
>
>本文概述單一登入(SSO)和進階CRM使用者管理。 如果您的帳戶已布建 **2020年9月10日之後**，請忽略本文，因為SSO和Identity Management將在中設定 [適用於您的Adobe Admin Console [!DNL Marketo Measure] 整合](/help/configuration-and-setup/getting-started-with-marketo-measure/marketo-measure-quick-start.md).

>[!NOTE]
>
>公司可能會使用不同的身分提供者（例如Ping Identity、Okta）。 下列設定指示和UI中使用的字詞，可能和您的身分提供者使用的字詞不直接相符。

## 需求 {#requirements}

* 中具有帳戶管理員許可權的使用者 [!DNL Marketo Measure] 應用程式
* 具有客戶身分提供者管理存取許可權的使用者

## 快速入門 {#getting-started}

若要開始使用，請瀏覽至「設定>安全性>驗證」頁面(位於 [!DNL Marketo Measure] 應用程式。 然後將「登入型別」切換為「自訂SSO」以檢視配置選項。 在您測試驗證並按一下 **[!UICONTROL Save]** 按鈕來切換頁面。

![](assets/single-sign-on-1.png)

## 程式 {#process}

[!DNL Marketo Measure] 單一登入需要依照一系列重要的步驟來設定您的驗證設定，以免您遭鎖定在外 [!DNL Marketo Measure] 帳戶。

設定 [!DNL Marketo Measure] 您的身分提供者中的應用程式。 如需逐步說明，請參閱下列外部檔案。

    a.出現單一登入URL或收件者URL或目的地URL、SAML Assertion Customer Service (ACS) URL的提示時，請使用[https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest](https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest)
    
    b.當系統提示您輸入對象限制URL或應用程式定義的唯一識別碼時，請使用[https://BizibleLPM](https://biziblelpm/)

在中切換至自訂SSO [!DNL Marketo Measure] 應用

    a.為您的帳戶啟用「帳單群組」後，您現在可以瀏覽至 [!UICONTROL Settings] >>[!UICONTROL Security] >> [!UICONTROL Authentication]
    
    b.依預設，您的登入型別將設為&quot;CRM使用者&quot;。
    
    c.將登入型別切換為「自訂SSO」以開始設定程式。

填寫身分提供者設定的連線設定

    a.您的身分提供者可能會提供IdP中繼資料.xml檔案，以提取必要的設定欄位。 請載入.xml檔案的內容，或從身份提供者組態程式期間取得的輸出填寫以下三個欄位。 **您不需要同時完成兩者。**
    
    i. IdP URL：符合以下條件的URL： [!DNL Marketo Measure] 需要指向，才能在中驗證您的使用者 [!DNL Marketo Measure] 應用程式。 有時稱為「重新導向URL」。
    二、 IdP簽發者：身分提供者的唯一識別碼。 有時稱為「外部金鑰」。
    三、 IdP憑證：公開金鑰，可允許 [!DNL Marketo Measure] 驗證及驗證所有識別提供者回應的簽章。

設定使用者的權杖有效期（分鐘）。

    答： [!DNL Marketo Measure] 允許從1到1440分鐘的整數。 超過使用者的工作階段時間後，使用者在導覽至新頁面時會登出。

設定您的使用者屬性設定，並將其對應至個別的名字、姓氏和電子郵件地址。

    a.輸入SAML屬性， [!DNL Marketo Measure] 將能夠透過傳遞的資訊識別您的使用者。
    
    i.電子郵件屬性：提供您的「識別提供者」用於使用者電子郵件地址的屬性名稱。
    二、 名字屬性：提供您的識別提供者用於使用者名字的屬性名稱。
    三、 姓氏屬性：提供您的識別提供者用於使用者姓氏的屬性名稱。
    
    b.提示：如果您現在測試您的SAML組態，我們會剖析您可以用於此節的電子郵件、名字和姓氏屬性。

![](assets/single-sign-on-2.png)

設定您的使用者角色設定，並將其對應至分類自IdP的個別角色或群組。

    a.客戶可選擇指派 [!DNL Marketo Measure] 使用者角色是根據在其身分提供者中定義的群組。 輸入SAML屬性， [!DNL Marketo Measure] 將能夠將您的使用者角色和群組對應至 [!DNL Marketo Measure] 使用者許可權。 強烈建議您設定這些角色，以便 [!DNL Marketo Measure] 管理員有足夠的許可權更新您的帳戶。
    
    b.如果未對應任何角色或群組，則預設設定為「識別提供者」中的所有員工將具有「標準」使用者存取權。
    
    i. [!DNL Marketo Measure] 標準使用者：為應該對以下專案擁有唯讀存取許可權的使用者提供角色或群組值（來自您的SSO提供者）： [!DNL Marketo Measure] 應用程式。
    二、 [!DNL Marketo Measure] 帳戶管理員使用者：提供角色或群組值（來自您的SSO提供者），給應該擁有 [!DNL Marketo Measure] 應用程式。 這表示該角色有權變更與您的帳戶相關的組態和設定。
    三、 您必須在IdP中擁有屬性，且此IdP必須包含「群組」的確切名稱，這些群組可容納您放入「Bizible Standard User」或「Bizible Account Admin User」屬性的值。
    
    c.若有多個角色或群組應對應至一個角色，請輸入每個值，值之間以逗號分隔。

![](assets/single-sign-on-3.png)

測試單一登入設定

    a.按一下「儲存」之前，您必須先按一下 [!UICONTROL Test SAML Authentication] 按鈕，驗證您的設定是否已正確設定。
    
    b.如果您看到「失敗」錯誤，請追蹤訊息並再試一次。

![](assets/single-sign-on-4.png)

儲存您的設定並指示您的同事使用 [!UICONTROL Single Sign On] 使用您新的自訂登入URL。

    a.重要：儲存新的「驗證」設定後，由於您已停用CRM使用者的登入功能並啟用「自訂SSO」，因此一旦您導覽至新頁面，工作階段可能會結束。

![](assets/single-sign-on-5.png)

試試看！

    a.使用新的自訂登入URL並嘗試重新登入 [!DNL Marketo Measure] 具有您的身分提供者憑證的應用程式。
    
    b.格式類似於&#39;https://apps.adobe.com/business/[accountName]&#39;
    
    c.恭喜！ 您已成功設定單一登入 [!DNL Marketo Measure] 您的帳戶申請！

![](assets/single-sign-on-6.png)

>[!NOTE]
>
>設定SSO後，您將不再需要在 [!DNL Marketo Measure] 應用程式。 使用者布建應直接在您的身分提供者內處理。

## CRM使用者（進階設定） {#crm-users-advanced-setup}

依預設，所有帳戶都可以存取 [!DNL Marketo Measure] 使用其CRM憑證的應用程式。 有時候，帳戶擁有者需要限制特定角色的存取權，而不是將其開放給具有有效CRM授權的所有使用者。 進階設定可讓您將您的CRM角色和群組對應至 [!DNL Marketo Measure] 使用者許可權。

如果未對應任何角色或群組，預設設定為您CRM中的所有使用中授權都將具有標準使用者存取權。

* [!DNL Marketo Measure] 標準使用者：為應具備唯讀存取許可權的使用者提供角色或群組值。 [!DNL Marketo Measure] 應用程式。
* [!DNL Marketo Measure] 帳戶管理員使用者：為應具有管理員存取許可權的使用者提供角色或群組值。 [!DNL Marketo Measure] 應用程式。 這表示該角色有權變更與您的帳戶相關的組態和設定。

如果多個角色或群組應該對應至一個角色，請輸入每個值，值之間以逗號分隔。

**Salesforce角色**

的 [!DNL Salesforce] 角色，使用每個角色的名稱。 所有角色都可在下找到 [!UICONTROL Setup] >[!UICONTROL Manage Users] >[!UICONTROL Roles] 功能表。

![](assets/6.png)

**動態角色**

的 [!DNL Dynamics] 角色，使用每個安全性角色的名稱。 所有安全性角色都可在 [!UICONTROL Settings] >[!UICONTROL Security] >[!UICONTROL Security Roles] 功能表。

![](assets/7.png)

![](assets/8.png)

**Google使用者**

設定自訂SSO後， [!UICONTROL Users] 頁面將更新為僅顯示已新增Google登入的外部使用者。 由於所有具有存取權的使用者都是透過SSO設定來定義，因此此處列出其他外部使用者。

![](assets/9.png)

僅有效 [!DNL Google] 可新增帳戶，且必須定義使用者角色。

## 外部連結 {#external-links}

* [Okta](http://developer.okta.com/standards/SAML/setting_up_a_saml_application_in_okta)
* [Ping身分](http://docs.pingidentity.com/bundle/p1_enterpriseConfigSsoSaml_cas/page/enableAppWithoutURL.html)
* [OneLogin](http://onelogin.service-now.com/support?id=kb_article&amp;sys_id=b2c91143db109700d5505eea4b9619d5)
* [主動式目錄](http://docs.microsoft.com/en-us/azure/active-directory/active-directory-saas-custom-apps)
