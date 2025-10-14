---
unique-page-id: 18874761
description: 單一登入 —  [!DNL Marketo Measure]
title: 單一登入
exl-id: a328e9cb-8352-4693-8a44-533e08f1a29c
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '1257'
ht-degree: 0%

---

# 單一登入 {#single-sign-on}

SSO （單一登入）的SAML （安全性宣告標籤語言）可讓使用者在登入[!DNL Marketo Measure]應用程式時，透過公司的身分提供者進行驗證。 SSO可讓使用者驗證一次，而不需要驗證個別應用程式。 企業客戶必須使用SAML，因為並非所有使用者在其組織內都有[!DNL Salesforce]或[!DNL Google]帳戶。 為了擴充，[!DNL Marketo Measure]已開發可支援公司身分提供者的SAML解決方案。

>[!CAUTION]
>
>本文概述單一登入(SSO)和進階CRM使用者管理。 如果您的帳戶是在2020年9月10日&#x200B;**之後布建**，請忽略本文，因為SSO和Identity Management將會在[Adobe Admin Console中設定為您的 [!DNL Marketo Measure] 整合](/help/configuration-and-setup/getting-started-with-marketo-measure/marketo-measure-quick-start.md)。

>[!NOTE]
>
>公司可能會使用不同的身分提供者（例如Ping Identity、Okta）。 下列設定指示和UI中使用的字詞，可能和您的身分提供者使用的字詞不直接相符。

## 需求 {#requirements}

* 在[!DNL Marketo Measure]應用程式中具有AccountAdmin許可權的使用者
* 具有客戶身分提供者管理存取許可權的使用者

## 快速入門 {#getting-started}

若要開始使用，請瀏覽至[!DNL Marketo Measure]應用程式中的[設定] > [安全性] > [驗證]頁面。 然後將「登入型別」切換為「自訂SSO」以檢視配置選項。 在您測試驗證並按一下頁面底部的&#x200B;**[!UICONTROL Save]**&#x200B;按鈕之前，變更將不會生效。

![](assets/single-sign-on-1.png)

## 程式 {#process}

[!DNL Marketo Measure]單一登入需要透過一系列步驟來設定您的驗證設定，以免您遭到[!DNL Marketo Measure]帳戶的鎖定。

在您的身分提供者中設定[!DNL Marketo Measure]應用程式。 如需逐步說明，請參閱下列外部檔案。

    a。當系統提示您輸入單一登入URL或收件者URL或目的地URL、SAML Assertion Customer Service (ACS) URL時，請使用[https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest](https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest)
    
    b。當系統提示您輸入對象限制URL或應用程式定義的唯一識別碼時，請使用[https://BizibleLPM](https://biziblelpm/)

在[!DNL Marketo Measure]應用程式中切換至自訂SSO

    a。為您的帳戶啟用帳單群組後，您現在可以導覽至[!UICONTROL Settings] >>[!UICONTROL Security] >> [!UICONTROL Authentication]
    
    b。依預設，您的登入型別將設為「CRM使用者」。
    
    c。將登入型別切換為「自訂SSO」以開始設定程式。

填寫身分提供者設定的連線設定

    a。您的身分提供者可能會提供IdP中繼資料.xml檔案，以提取必要的設定欄位。 請載入.xml檔案的內容，或從身份提供者組態程式期間取得的輸出填寫以下三個欄位。 **您不需要同時完成兩者。**
    
    i.IdP URL：  [!DNL Marketo Measure] 需要指向的URL才能驗證您的使用者是否進入 [!DNL Marketo Measure] 應用程式。 有時稱為「重新導向URL」。
    ii。 IdP簽發者：身分提供者的唯一識別碼。 有時稱為「外部金鑰」。
    iii. IdP憑證：可讓 [!DNL Marketo Measure] 驗證及驗證所有識別提供者回應的簽章的公開金鑰。

設定使用者的權杖有效期（分鐘）。

    a. [!DNL Marketo Measure] 允許從1到1440分鐘的整數。 超過使用者的工作階段時間後，使用者在導覽至新頁面時會登出。

設定您的使用者屬性設定，並將其對應至個別的名字、姓氏和電子郵件地址。

    a。輸入SAML屬性後， [!DNL Marketo Measure] 將能夠透過傳遞的資訊識別您的使用者。
    
    i。電子郵件屬性：提供您的身分提供者用於使用者電子郵件地址的屬性名稱。
    ii。 名字屬性：提供您的識別提供者用於使用者名字的屬性名稱。
    iii. 姓氏屬性：提供您的識別提供者用於使用者姓氏的屬性名稱。
    
    b。提示：如果您現在測試您的SAML設定，我們會剖析您可用於此節的電子郵件、名字和姓氏屬性。

![](assets/single-sign-on-2.png)

設定您的使用者角色設定，並將其對應至分類自IdP的個別角色或群組。

    a。客戶可以選擇根據在其身分提供者中定義的群組來指派 [!DNL Marketo Measure] 使用者角色。 透過輸入SAML屬性， [!DNL Marketo Measure] 將能夠將您的使用者角色和群組對應到 [!DNL Marketo Measure] 使用者許可權。 強烈建議您設定這些角色，以便 [!DNL Marketo Measure] 管理員有足夠的許可權更新您的帳戶。
    
    b。如果未對應任何角色或群組，則預設設定為「身分提供者」中的所有員工將具有「標準」使用者存取權。
    
    i. [!DNL Marketo Measure] 標準使用者：提供角色或群組值（來自您的SSO提供者），給應該擁有 [!DNL Marketo Measure] 應用程式的唯讀存取權的使用者。
    ii。 [!DNL Marketo Measure] 帳戶管理員使用者：為應該擁有 [!DNL Marketo Measure] 應用程式管理存取權的使用者提供角色或群組值（來自您的SSO提供者）。 這表示該角色有權變更與您的帳戶相關的組態和設定。
    iii. 您必須在IdP中擁有屬性，且此IdP必須包含「群組」的確切名稱，這些群組可容納您放入「Bizible Standard User」或「Bizible Account Admin User」屬性的值。
    
    c。如果多個角色或群組應該對應至一個角色，請輸入每個值（以逗號分隔）。

![](assets/single-sign-on-3.png)

測試單一登入設定

    a。點選「儲存」之前，您必須先按一下「[!UICONTROL Test SAML Authentication]」按鈕，確認您的設定已正確設定。
    
    b。如果您看到「失敗」錯誤，請依照訊息操作，然後再試一次。

![](assets/single-sign-on-4.png)

儲存您的設定，並指示您的同事搭配您新的自訂登入URL使用[!UICONTROL Single Sign On]。

    a。重要：儲存新的驗證設定後，工作階段可能會在您導覽至新頁面後結束，因為您已停用CRM使用者的登入功能並啟用自訂SSO。

![](assets/single-sign-on-5.png)

試試看！

    a。使用您新的自訂登入URL，並嘗試使用您的身分提供者憑證重新登入 [!DNL Marketo Measure] 應用程式。
    
    b。格式看起來會像&#39;https://apps.adobe.com/business/[accountName]&#39;
    
    c。恭喜！ 您已成功為您的帳戶設定 [!DNL Marketo Measure] 應用程式的單一登入！

![](assets/single-sign-on-6.png)

>[!NOTE]
>
>設定SSO後，您將不再需要在[!DNL Marketo Measure]應用程式中新增使用者。 使用者布建應直接在您的身分提供者內處理。

## CRM使用者（進階設定） {#crm-users-advanced-setup}

依預設，所有帳戶都可以使用其CRM認證存取[!DNL Marketo Measure]應用程式。 有時候，帳戶擁有者需要限制特定角色的存取權，而不是將其開放給具有有效CRM授權的所有使用者。 進階設定可讓您將您的CRM角色和群組對應到[!DNL Marketo Measure]使用者許可權。

如果未對應任何角色或群組，預設設定為您CRM中的所有使用中授權都具有標準使用者存取權。

* [!DNL Marketo Measure]標準使用者：為應該擁有[!DNL Marketo Measure]應用程式唯讀存取權的使用者提供角色或群組值。
* [!DNL Marketo Measure]帳戶管理員使用者：為應該擁有[!DNL Marketo Measure]應用程式管理存取權的使用者提供角色或群組值。 這表示該角色有權變更與您的帳戶相關的組態和設定。

如果多個角色或群組應該對應至一個角色，請輸入每個值，值之間以逗號分隔。

**Salesforce角色**

對於[!DNL Salesforce]角色，請使用每個角色的名稱。 您可以在[!UICONTROL Setup] >[!UICONTROL Manage Users] >[!UICONTROL Roles]功能表找到所有角色。

![](assets/6.png)

**動態角色**

對於[!DNL Dynamics]角色，請使用每個安全性角色的名稱。 您可以在[!UICONTROL Settings] >[!UICONTROL Security] >[!UICONTROL Security Roles]功能表找到所有安全性角色。

![](assets/7.png)

![](assets/8.png)

**Google使用者**

設定自訂SSO後，[!UICONTROL Users]頁面會更新，以僅顯示已新增Google登入的外部使用者。 由於所有具有存取權的使用者都是透過SSO設定來定義，因此此處列出其他外部使用者。

![](assets/9.png)

只能新增有效的[!DNL Google]帳戶，而且必須定義使用者角色。

## 外部連結 {#external-links}

* [Okta](https://developer.okta.com/standards/SAML/setting_up_a_saml_application_in_okta)
* [Ping身分](https://docs.pingidentity.com:443/bundle/p1_enterpriseConfigSsoSaml_cas/page/enableAppWithoutURL.html)
* [OneLogin](https://onelogin.service-now.com/support?id=kb_article&sys_id=b2c91143db109700d5505eea4b9619d5)
* [Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-saas-custom-apps)
