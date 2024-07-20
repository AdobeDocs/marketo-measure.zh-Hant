---
unique-page-id: 37357059
description: Dynamics CRM - [!DNL Marketo Measure]的OAuth （含 [!DNL Azure Active Directory] ）
title: OAuth與Dynamics CRM的 [!DNL Azure Active Directory]
exl-id: 0a2f6b29-541d-4965-a460-e6f19b934edb
feature: Microsoft Dynamics
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 0%

---

# Dynamics CRM的OAuth （含[!DNL Azure Active Directory]） {#oauth-with-azure-active-directory-for-dynamics-crm}

## 受影響者 {#who-s-affected}

此設定適用於使用Dynamics CRM搭配[!DNL Azure Active Directory] (AAD)帳戶的新[!DNL Marketo Measure]客戶，或想要從舊版使用者名稱和密碼移轉至[!DNL Azure Active Directory]搭配OAuth的客戶。

>[!NOTE]
>
>針對這兩種情況，此處設定的AAD是為了方便在[!DNL Marketo Measure]中連線您的Dynamics執行個體以作為資料提供者。

## 設定新應用程式 {#set-up-new-application}

1. 登入您的[Azure入口網站](https://portal.azure.com/#home)。

1. 選擇Azure AD租使用者，方法是按一下頁面右上角的帳戶，然後按一下[切換目錄]導覽，然後選取適當的租使用者。 如果您的帳戶下只有一個Azure AD租使用者，或您已選取適當的Azure AD租使用者，請略過此步驟。

   ![](assets/setup-2.png)

1. 在搜尋列中搜尋「[!DNL Azure Active Directory]」，然後按一下名稱以開啟。

   ![](assets/setup-3.png)

1. 按一下左側功能表中的&#x200B;**[!UICONTROL App Registrations]**。

   ![](assets/setup-4.png)

1. 按一下頂端的&#x200B;**[!UICONTROL New Registration]**。

   ![](assets/setup-5.png)

1. 按照提示建立應用程式。 不論是Web應用程式或公用使用者端（行動與案頭）應用程式，但如果您想要Web應用程式或公用使用者端應用程式的特定範例，請檢視[快速入門](https://learn.microsoft.com/en-us/azure/active-directory/develop/v2-overview)。\
   a.名稱是應用程式名稱，向一般使用者說明您的應用程式。\
   b.在「支援的帳戶型別」下，選取任何組織目錄中的帳戶和個人Microsoft帳戶。\
   c.提供重新導向URI。 若為Web應用程式，這是使用者可登入之應用程式的基礎URL。 例如，`http://localhost:12345`。 對於公用使用者端（行動裝置和案頭），Azure AD會使用它來傳回權杖回應。 輸入應用程式的特定值。 例如，`http://MyFirstAADApp`。

1. 註冊完成後，Azure AD會指派唯一的使用者端識別碼（應用程式ID）給應用程式。 您需要在下一節中使用此值，請從應用程式頁面複製此值。

1. 若要在Azure入口網站中尋找您的應用程式，請按一下&#x200B;**[!UICONTROL App Registrations]**，然後按一下&#x200B;**[!UICONTROL All Applications]**。 開啟您新建立的應用程式

1. 按一下左側功能表中的&#x200B;**[!UICONTROL Authentication]**。

   ![](assets/setup-9.png)

1. 將[!DNL Marketo Measure]重新導向URL： `https://apps.bizible.com/OAuth2`與`https://apps.bizible.com/OAuth2?identityOnly=true`新增至重新導向URL清單。

   ![](assets/setup-10.png)

1. 導覽至API許可權索引標籤，並確保為應用程式指派了正確的許可權。

   ![](assets/setup-10a.png)

1. 從這裡，在搜尋方塊中輸入&quot;[!UICONTROL enterprise]&quot;並按一下&#x200B;**[!UICONTROL Enterprise Applications]**。

   ![](assets/setup-11.png)

1. 再次從應用程式清單中尋找並開啟您的新應用程式。

1. 在[許可權]索引標籤中，按一下&#x200B;**[!UICONTROL Grant Admin Consent for (instance name)]**。

   ![](assets/setup-13a.png)

1. 按一下&#x200B;**[!UICONTROL Accept]**。

   ![](assets/setup-13b.png)

1. 從「[!UICONTROL Users and Groups]」索引標籤，確定已將有效的「使用者和群組」指派給應用程式。

   ![](assets/setup-14.png)

## 建立應用程式使用者 {#creating-an-application-user}

應用程式註冊完成後，即可建立應用程式使用者。

1. 導覽至您的Common Data Service環境(`https://[org].crm.dynamics.com`)。

1. 導覽至&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Security]** > **[!UICONTROL Users]**。

1. 在檢視篩選中選擇&#x200B;**[!UICONTROL Application Users]**。

1. 選取&#x200B;**[!UICONTROL + New]**。

1. 在「應用程式使用者」表單中輸入必要資訊。

   >[!NOTE]
   >
   >* 使用者名稱資訊不得符合[!DNL Azure Active Directory]中存在的使用者。
   >
   >* 在「應用程式ID」欄位中，輸入您先前在Azure AD中註冊的應用程式應用程式ID。

1. 如果設定正確，則選取&#x200B;**[!UICONTROL Save]**&#x200B;後，**[!UICONTROL Application ID URI]**&#x200B;和&#x200B;**[!UICONTROL Azure AD Object Id]**&#x200B;欄位將自動填入正確的值。

1. 結束使用者表單之前，請選擇&#x200B;**[!UICONTROL Manage Roles]**&#x200B;並指派安全性角色給此應用程式使用者，讓應用程式使用者可以存取想要的組織資料。

## 透過OAuth連線您的Dynamics執行個體 {#connecting-your-dynamics-instance-via-oAuth}

1. 第一次設定Dynamics連線時，請依照[本文章](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md)中「CRM為資料提供者」章節的步驟1-5操作。

1. 提示輸入OAuth認證時，請填入上節中設定的使用者端ID、使用者端密碼和應用程式ID URI。

a.使用者端ID是上一節中步驟#7的ID。 如果您沒有寫下應用程式ID，應用程式註冊的設定中會顯示應用程式ID 。

b.使用者端密碼是在Azure入口網站中為您在「憑證和密碼」下的應用程式建立的應用程式密碼。

![](assets/creating-2e.png)

c.應用程式ID URI是目標網頁API （安全資源）的URL。 若要尋找應用程式ID URL，請在Azure入口網站中，按一下[!DNL Azure Active Directory]，按一下[應用程式註冊]，開啟應用程式的[設定]頁面，然後按一下[內容]。 它也可以是外部資源，例如`https://graph.microsoft.com`。 這通常是Dynamics執行個體的URL。

1. 按一下&#x200B;**[!UICONTROL Submit]**&#x200B;後，系統會提示您使用[!DNL Azure Active Directory]登入。 驗證成功後，您的Dynamics帳戶會在[!DNL Marketo Measure]內以資料提供者的身分連線。

## 正在重新驗證您的Dynamics帳戶 {#re-authenticating-your-dynamics-account}

1. 當您在[!DNL Marketo Measure]應用程式中時，請移至&#x200B;**[!UICONTROL My Settings]** > **[!UICONTROL Settings]** > **[!UICONTROL Connections]**。

1. 按一下Dynamics連線旁CRM區段中的鍵圖示。

1. 按一下金鑰時，會出現快顯視窗，提示您輸入使用者端ID、使用者端密碼和應用程式ID URI，類似於註冊流程。

   ![](assets/re-authenticating-3.png)

1. 按一下&#x200B;**[!UICONTROL Submit]**&#x200B;後，系統會提示您使用[!DNL Azure Active Directory]登入。 當驗證成功時，您的Dynamics帳戶會在[!DNL Marketo Measure]內重新授權。
