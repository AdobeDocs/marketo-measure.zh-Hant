---
unique-page-id: 18874761
description: 單一登入 —  [!DNL Marketo Measure]  — 產品檔案
title: 單一登入
exl-id: a328e9cb-8352-4693-8a44-533e08f1a29c
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '1310'
ht-degree: 0%

---

# 單一登入 {#single-sign-on}

SSO（單一登入）適用的SAML（安全斷言標籤語言）讓使用者登入時，可透過公司的身分提供者進行驗證 [!DNL Marketo Measure] 應用程式。 SSO允許用戶僅進行一次身份驗證，而無需對不同的應用進行身份驗證。 SAML是企業客戶的必要條件，因為並非所有使用者都會 [!DNL Salesforce] 或 [!DNL Google] 帳戶。 為了擴大規模， [!DNL Marketo Measure] 已開發出可支援公司身分提供者的SAML解決方案。

>[!CAUTION]
>
>本文概述單一登入(SSO)和進階CRM使用者管理。 如果已布建您的帳戶 **之後9/10/2020**，請忽略本條，因為SSO和Identity Management將在 [Adobe Admin Console [!DNL Marketo Measure] 整合](/help/configuration-and-setup/getting-started-with-marketo-measure/marketo-measure-quick-start.md).

>[!NOTE]
>
>公司可能會使用不同的身分提供者（例如Ping Identity、Okta）。 下列設定指示和UI中使用的辭彙可能不會直接與您的身分提供者所使用的辭彙相符。

## 需求 {#requirements}

* 在 [!DNL Marketo Measure] 應用程式
* 具有客戶身分提供者管理存取權的使用者

## 快速入門 {#getting-started}

若要開始使用，請導覽至 [!DNL Marketo Measure] 應用程式。 然後將「登入類型」切換為「自訂SSO」，以查看設定選項。 在您測試驗證並按一下 **[!UICONTROL Save]** 按鈕。

![](assets/single-sign-on-1.png)

## 程式 {#process}

[!DNL Marketo Measure] 單一登入需要執行一系列重要步驟來設定驗證設定，這樣您就不會有被鎖出您的 [!DNL Marketo Measure] 帳戶。

設定 [!DNL Marketo Measure] 身份提供程式中的應用程式。 請參閱下方列出的外部檔案以了解逐步說明。

    a.當系統提示輸入URL、收件者URL或目的地URL、SAML斷言客戶服務(ACS)URL時，請使用[https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest](https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest)
    
    b.提示輸入對象限制URL或應用程式定義的唯一識別碼時，請使用[https://BizibleLPM](https://biziblelpm/)

切換至 [!DNL Marketo Measure] 應用程式

    a.為您的帳戶啟用「帳單群組」後，您現在可以導覽至 [!UICONTROL Settings] >>[!UICONTROL Security] >> [!UICONTROL Authentication]
    
    b.您的登入類型預設會設為「CRM使用者」。
    
    c.將「登入類型」切換為「自訂SSO」，以開始設定程式。

填寫Identity Provider配置的連接設定

    a.您的身分提供者可能會提供IdP中繼資料.xml檔案，以提取必要的設定欄位。 在.xml文檔的內容中載入，或從在身份提供程式配置過程中獲得的輸出中填寫以下三個欄位。 **您不需要同時完成兩者。**
    
    我。IdP URL:URL [!DNL Marketo Measure] 需要指向，才能驗證使用者 [!DNL Marketo Measure] 應用程式。 有時稱為「重新導向URL」。
    ii. IdP頒發者：身份提供程式的唯一標識符。 有時稱為「外部金鑰」。
    三。 IdP憑證：允許 [!DNL Marketo Measure] 驗證和驗證所有身份提供程式響應的簽名。

設定使用者的代號過期時間（以分鐘為單位）。

    a. [!DNL Marketo Measure] 允許1到1440分鐘的整數。 超過使用者的工作階段時間後，使用者導覽至新頁面後即會被登出。

設定您的「使用者屬性」設定並對應至相應的名字、姓氏和電子郵件地址。

    a.輸入SAML屬性後， [!DNL Marketo Measure] 就能透過傳遞的資訊識別使用者。
    
    我。電子郵件屬性：提供您的身分提供者用於使用者電子郵件地址的屬性名稱。
    ii. 名字屬性：提供您的身分提供者用於使用者名字的屬性名稱。
    三。 姓氏屬性：提供您的身分提供者用於使用者姓氏的屬性名稱。
    
    b.提示：如果您現在測試SAML設定，我們會剖析您可用於此區段的電子郵件、名字和姓氏屬性。

![](assets/single-sign-on-2.png)

設定使用者角色設定，並將其對應至從您的IdP分類的個別角色或群組。

    a.客戶可以選擇指派 [!DNL Marketo Measure] 根據其身分提供者中定義的群組，提供使用者角色。 輸入SAML屬性後， [!DNL Marketo Measure] 能將使用者的角色和群組對應至 [!DNL Marketo Measure] 使用者權限。 我們強烈建議您設定這些角色，以便 [!DNL Marketo Measure] 管理員有足夠的權限來更新您的帳戶。
    
    b.如果未映射任何角色或組，預設設定是標識提供程式中的所有員工都將具有標準用戶訪問權限。
    
    我。 [!DNL Marketo Measure] 標準用戶：為應具有唯讀存取權的使用者提供角色或群組值（來自您的SSO提供者） [!DNL Marketo Measure] 應用程式。
    ii. [!DNL Marketo Measure] 帳戶管理員使用者：為應具有管理存取權的使用者提供角色或群組值（來自您的SSO提供者） [!DNL Marketo Measure] 應用程式。 這表示角色有權變更與您的帳戶相關的設定和設定。
    三。 您的IdP中必須有一個屬性，其確切名稱為「groups」，會容納您放入「Bizible Standard User」或「Bizible Account Admin User」屬性的值。
    
    c.如果應將多個角色或組映射到某個角色，請輸入以逗號分隔的每個值。

![](assets/single-sign-on-3.png)

測試單一登入組態

    a.點擊「儲存」之前，您必須按一下 [!UICONTROL Test SAML Authentication] 按鈕，確認設定已正確設定。
    
    b.如果您看到「失敗」錯誤，請依照訊息進行，然後再次嘗試。

![](assets/single-sign-on-4.png)

保存設定並指示同事使用 [!UICONTROL Single Sign On] 使用您的新自訂登入URL。

    a.重要：儲存新的驗證設定後，由於您已停用CRM使用者登入並啟用自訂SSO，因此導覽至新頁面後，您的工作階段可能會結束。

![](assets/single-sign-on-5.png)

試試看！

    a.使用您新的自訂登入URL並嘗試重新登入 [!DNL Marketo Measure] 具有您的身份提供程式憑據的應用程式。
    
    b.格式將如「https://apps.adobe.com/business/[accountName]」
    
    c.祝賀！ 您已成功將單一登入設定為 [!DNL Marketo Measure] 您的帳戶申請！

![](assets/single-sign-on-6.png)

>[!NOTE]
>
>設定SSO後，您不再需要在 [!DNL Marketo Measure] 應用程式。 應直接在您的身分提供者中處理使用者布建。

## CRM用戶（高級設定） {#crm-users-advanced-setup}

依預設，所有帳戶都可以存取 [!DNL Marketo Measure] 應用程式。 有時，帳戶擁有者需要限制特定角色的存取權，而不是將其開啟給具有作用中CRM授權的所有使用者。 進階設定可讓您將CRM角色和群組對應至 [!DNL Marketo Measure] 使用者權限。

如果未映射任何角色或組，預設設定是CRM中所有活動許可證都將具有標準用戶訪問權限。

* [!DNL Marketo Measure] 標準用戶：為應具有唯讀存取權的使用者提供角色或群組值 [!DNL Marketo Measure] 應用程式。
* [!DNL Marketo Measure] 帳戶管理員使用者：為應具有管理存取權的使用者提供角色或群組值 [!DNL Marketo Measure] 應用程式。 這表示角色有權變更與您的帳戶相關的設定和設定。

如果應將多個角色或組映射到某個角色，請輸入以逗號分隔的每個值。

**Salesforce角色**

針對 [!DNL Salesforce] 角色，使用每個角色的名稱。 您可以在 [!UICONTROL Setup] >[!UICONTROL Manage Users] >[!UICONTROL Roles] 功能表。

![](assets/6.png)

**動態角色**

針對 [!DNL Dynamics] 角色，使用每個安全形色的名稱。 您可以在 [!UICONTROL Settings] >[!UICONTROL Security] >[!UICONTROL Security Roles] 功能表。

![](assets/7.png)

![](assets/8.png)

**Google使用者**

設定自訂SSO後， [!UICONTROL Users] 頁面將會更新，僅顯示已隨Google登入新增的外部使用者。 因為所有具有存取權的使用者都是透過SSO設定來定義，此處會列出其他外部使用者。

![](assets/9.png)

僅有效 [!DNL Google] 可以添加帳戶，並且必須定義用戶角色。

## 外部連結 {#external-links}

* [奧克塔](http://developer.okta.com/standards/SAML/setting_up_a_saml_application_in_okta)
* [Ping身份](http://docs.pingidentity.com/bundle/p1_enterpriseConfigSsoSaml_cas/page/enableAppWithoutURL.html)
* [OneLogin](http://onelogin.service-now.com/support?id=kb_article&amp;sys_id=b2c91143db109700d5505eea4b9619d5)
* [Active Directory](http://docs.microsoft.com/en-us/azure/active-directory/active-directory-saas-custom-apps)
