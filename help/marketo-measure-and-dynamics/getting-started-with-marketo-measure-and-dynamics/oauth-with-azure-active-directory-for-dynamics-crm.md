---
unique-page-id: 37357059
description: OAuth與 [!DNL Azure Active Directory] 對於Dynamics CRM - [!DNL Marketo Measure]  — 產品檔案
title: OAuth與 [!DNL Azure Active Directory] （適用於Dynamics CRM）
exl-id: 0a2f6b29-541d-4965-a460-e6f19b934edb
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 0%

---

# OAuth與 [!DNL Azure Active Directory] （適用於Dynamics CRM） {#oauth-with-azure-active-directory-for-dynamics-crm}

## 受影響者 {#who-s-affected}

此設定適用於新 [!DNL Marketo Measure] 客戶使用Dynamics CRM搭配 [!DNL Azure Active Directory] (AAD)帳戶，或想從舊版使用者名稱和密碼登入移轉至的客戶 [!DNL Azure Active Directory] 和OAuth。

>[!NOTE]
>
>對於這兩種情況，AAD都設定在此處，以便於在 [!DNL Marketo Measure] 資料提供者。

## 設定新應用程式 {#set-up-new-application}

1. 登入您的 [Azure門戶](https://portal.azure.com/#home).

1. 按一下頁面右上角的您的帳戶，然後按一下「切換目錄」導覽列，然後選取適當的租用戶，以選擇您的Azure AD租用戶（如果您的帳戶下只有一個Azure AD租用戶，或您已選取適當的Azure AD租用戶，請跳過此步驟）。

   ![](assets/setup-2.png)

1. 搜索「[!DNL Azure Active Directory]」，然後按一下「名稱」以開啟。

   ![](assets/setup-3.png)

1. 按一下 **[!UICONTROL App Registrations]** 的下一頁。

   ![](assets/setup-4.png)

1. 按一下 **[!UICONTROL New Registration]** 頂端。

   ![](assets/setup-5.png)

1. 按照提示建立新應用程式。 無論是Web應用程式還是公共客戶端（移動和案頭）應用程式，但是如果您想要Web應用程式或公共客戶端應用程式的特定示例，請查看我們的 [快速入門](https://docs.microsoft.com/en-us/azure/active-directory/develop/v1-overview).\
   a.名稱是應用程式名稱，向最終用戶說明您的應用程式。\
   b.在「支援的帳戶類型」下，選擇任何組織目錄中的帳戶和個人Microsoft帳戶。\
   c.提供重定向URI。 若為Web應用程式，此為使用者可登入之應用程式的基礎URL。 例如， `http://localhost:12345`. 針對公用用戶端（行動和案頭）,Azure AD會使用它傳回權杖回應。 輸入應用程式的特定值。 例如， `http://MyFirstAADApp`.

1. 完成註冊後，Azure AD將為您的應用程式分配唯一的客戶端標識符（應用程式ID）。 您需要在下一節中使用此值，請從應用程式頁面複製它。

1. 若要在Azure入口網站中尋找您的應用程式，請按一下 **[!UICONTROL App Registrations]**，然後按一下 **[!UICONTROL All Applications]**. 開啟新建立的應用程式

1. 按一下 **[!UICONTROL Authentication]** 的下一頁。

   ![](assets/setup-9.png)

1. 新增 [!DNL Marketo Measure] 重新導向URL: `https://apps.bizible.com/OAuth2` 和 `https://apps.bizible.com/OAuth2?identityOnly=true` 重新導向URL清單。

   ![](assets/setup-10.png)

1. 導覽至「API權限」標籤，並確認已將正確的權限指派給應用程式。

   ![](assets/setup-10a.png)

1. 在此輸入「[!UICONTROL enterprise]」，然後按一下 **[!UICONTROL Enterprise Applications]**.

   ![](assets/setup-11.png)

1. 再次，從應用程式清單中查找並開啟新應用程式。

1. 在權限標籤中，按一下 **[!UICONTROL Grant Admin Consent for (instance name)]**.

   ![](assets/setup-13a.png)

1. 按一下 **[!UICONTROL Accept]**.

   ![](assets/setup-13b.png)

1. 從「[!UICONTROL Users and Groups]「 」頁簽，確保將有效的「用戶和組」分配給應用程式。

   ![](assets/setup-14.png)

## 建立應用程式使用者 {#creating-an-application-user}

完成應用程式註冊後，就可以建立應用程式用戶。

1. 導覽至您的通用資料服務環境(`https://[org].crm.dynamics.com`)。

1. 導覽至 **[!UICONTROL Settings]** > **[!UICONTROL Security]** > **[!UICONTROL Users]**.

1. 選擇 **[!UICONTROL Application Users]** （在檢視篩選器中）。

1. 選取 **[!UICONTROL + New]**.

1. 在「應用程式用戶」表單中，輸入所需資訊。

   >[!NOTE]
   >
   >* 用戶名資訊不得與 [!DNL Azure Active Directory].
   >
   >* 在「應用程式ID」欄位中，輸入您先前在Azure AD中註冊的應用程式的應用程式ID。


1. 如果設定正確，則在選取 **[!UICONTROL Save]**, **[!UICONTROL Application ID URI]** 和 **[!UICONTROL Azure AD Object Id]** 欄位會自動填入正確的值。

1. 退出用戶表單之前，請選擇 **[!UICONTROL Manage Roles]** 並為此應用程式用戶分配安全形色，使應用程式用戶能夠訪問所需的組織資料。

## 透過OAuth連線您的Dynamics例項 {#connecting-your-dynamics-instance-via-oAuth}

1. 首次設定Dynamics連線時，請依照 [這篇文章](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md).

1. 提示輸入OAuth憑證時，請填入上節中設定的用戶端ID、用戶端密碼和應用程式ID URI。

a.用戶端ID是上節中#7步的ID。 如果您未將其記下，應用程式ID會顯示在應用程式註冊的「設定」中。

b.用戶端密碼是在Azure入口網站中，針對您的應用程式，在「憑證與密碼」下建立的應用程式密碼。

![](assets/creating-2e.png)

c.應用程式ID URI是目標Web API（安全資源）的URL。 若要尋找應用程式ID URL，請在Azure入口網站中，按一下 [!DNL Azure Active Directory]，按一下應用程式註冊，開啟應用程式的「設定」頁面，然後按一下「屬性」。 也可能是外部資源，例如 `https://graph.microsoft.com`. 這通常是Dynamics例項的URL。

1. 按一下 **[!UICONTROL Submit]**，系統會提示您使用 [!DNL Azure Active Directory]. 當驗證成功時，您的Dynamics帳戶將會以資料提供者身分在內連線 [!DNL Marketo Measure].

## 重新驗證Dynamics帳戶 {#re-authenticating-your-dynamics-account}

1. 當你在 [!DNL Marketo Measure] 應用程式，轉到 **[!UICONTROL My Settings]** > **[!UICONTROL Settings]** > **[!UICONTROL Connections]**.

1. 按一下Dynamics連線旁CRM區段中的金鑰圖示。

1. 按一下金鑰後，會出現快顯視窗，系統會提示您輸入用戶端ID、用戶端密碼和應用程式ID URI，類似於註冊流程。

   ![](assets/re-authenticating-3.png)

1. 按一下 **[!UICONTROL Submit]**，系統會提示您使用 [!DNL Azure Active Directory]. 驗證成功後，您的Dynamics帳戶將在 [!DNL Marketo Measure].
