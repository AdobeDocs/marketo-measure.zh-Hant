---
unique-page-id: 37357059
description: OAuth與 [!DNL Azure Active Directory] 適用於Dynamics CRM - [!DNL Marketo Measure]
title: OAuth與 [!DNL Azure Active Directory] 適用於Dynamics CRM
exl-id: 0a2f6b29-541d-4965-a460-e6f19b934edb
feature: Microsoft Dynamics
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 0%

---

# OAuth與 [!DNL Azure Active Directory] 適用於Dynamics CRM {#oauth-with-azure-active-directory-for-dynamics-crm}

## 受影響者 {#who-s-affected}

此設定供新使用者使用 [!DNL Marketo Measure] 客戶透過 [!DNL Azure Active Directory] (AAD)帳戶，或適用於想從舊版使用者名稱和密碼登入移轉至的客戶 [!DNL Azure Active Directory] 使用OAuth。

>[!NOTE]
>
>對於這兩種情況，AAD在此設定為便於在中連線您的Dynamics執行個體 [!DNL Marketo Measure] 作為資料提供者。

## 設定新應用程式 {#set-up-new-application}

1. 登入您的 [Azure入口網站](https://portal.azure.com/#home).

1. 若要選擇您的Azure AD租使用者，請按一下頁面右上角的帳戶，然後按一下[切換目錄]導覽，然後選取適當的租使用者（如果您的帳戶下只有一個Azure AD租使用者，或您已選取適當的Azure AD租使用者，請略過此步驟）。

   ![](assets/setup-2.png)

1. 搜尋&quot;[!DNL Azure Active Directory]&quot;，然後按一下名稱以開啟。

   ![](assets/setup-3.png)

1. 按一下 **[!UICONTROL App Registrations]** 在左側功能表中。

   ![](assets/setup-4.png)

1. 按一下 **[!UICONTROL New Registration]** 在頂端。

   ![](assets/setup-5.png)

1. 按照提示建立新的應用程式。 無論是Web應用程式還是公用使用者端（行動與案頭）應用程式，如果您想要Web應用程式或公用使用者端應用程式的特定範例，請參閱我們的 [快速入門](https://docs.microsoft.com/en-us/azure/active-directory/develop/v1-overview).\
   a.名稱是應用程式名稱，向一般使用者說明您的應用程式。\
   b.在「支援的帳戶型別」下，選取任何組織目錄中的帳戶和個人Microsoft帳戶。\
   c.提供重新導向URI。 若為Web應用程式，這是使用者可登入之應用程式的基礎URL。 例如， `http://localhost:12345`. 對於公用使用者端（行動裝置和案頭），Azure AD會使用它來傳回權杖回應。 輸入應用程式的特定值。 例如， `http://MyFirstAADApp`.

1. 註冊完成後，Azure AD將為您的應用程式指派唯一的使用者端識別碼（應用程式ID）。 您需要在下一節中使用此值，請從應用程式頁面複製此值。

1. 若要在Azure入口網站中尋找您的應用程式，請按一下 **[!UICONTROL App Registrations]**，然後按一下 **[!UICONTROL All Applications]**. 開啟您新建立的應用程式

1. 按一下 **[!UICONTROL Authentication]** 在左側功能表中。

   ![](assets/setup-9.png)

1. 新增 [!DNL Marketo Measure] 重新導向URL： `https://apps.bizible.com/OAuth2` 和 `https://apps.bizible.com/OAuth2?identityOnly=true` 重新導向URL清單。

   ![](assets/setup-10.png)

1. 瀏覽至API許可權索引標籤，並確認為應用程式指派了正確的許可權。

   ![](assets/setup-10a.png)

1. 從這裡，輸入&quot;[!UICONTROL enterprise]」並按一下 **[!UICONTROL Enterprise Applications]**.

   ![](assets/setup-11.png)

1. 再次從應用程式清單中尋找並開啟您的新應用程式。

1. 在許可權索引標籤中，按一下 **[!UICONTROL Grant Admin Consent for (instance name)]**.

   ![](assets/setup-13a.png)

1. 按一下 **[!UICONTROL Accept]**.

   ![](assets/setup-13b.png)

1. 從&quot;[!UICONTROL Users and Groups]」索引標籤中，確定已將有效的「使用者和群組」指派給應用程式。

   ![](assets/setup-14.png)

## 建立應用程式使用者 {#creating-an-application-user}

應用程式註冊完成後，即可建立應用程式使用者。

1. 導覽至您的Common Data Service環境(`https://[org].crm.dynamics.com`)。

1. 瀏覽至 **[!UICONTROL Settings]** > **[!UICONTROL Security]** > **[!UICONTROL Users]**.

1. 選擇 **[!UICONTROL Application Users]** 在檢視篩選中。

1. 選取 **[!UICONTROL + New]**.

1. 在「應用程式使用者」表單中輸入必要資訊。

   >[!NOTE]
   >
   >* 使用者名稱資訊不得符合中存在的使用者 [!DNL Azure Active Directory].
   >
   >* 在「應用程式ID」欄位中，輸入您先前在Azure AD中註冊的應用程式應用程式ID。

1. 如果設定正確，則在選取 **[!UICONTROL Save]**，則 **[!UICONTROL Application ID URI]** 和 **[!UICONTROL Azure AD Object Id]** 欄位會自動填入正確的值。

1. 結束使用者表單前，請選擇 **[!UICONTROL Manage Roles]** 並指派安全性角色給此應用程式使用者，讓應用程式使用者可以存取所需的組織資料。

## 透過OAuth連線您的Dynamics執行個體 {#connecting-your-dynamics-instance-via-oAuth}

1. 第一次設定Dynamics連線時，請遵循中「CRM為資料提供者」一節的步驟1-5 [本文](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md).

1. 提示輸入OAuth認證時，請填入上節中設定的使用者端ID、使用者端密碼和應用程式ID URI。

a.使用者端ID是上一節中步驟#7的ID。 如果您沒有寫下應用程式ID，應用程式註冊的設定中會顯示應用程式ID 。

b.使用者端密碼是在Azure入口網站中為您在「憑證和密碼」下的應用程式建立的應用程式密碼。

![](assets/creating-2e.png)

c.應用程式ID URI是目標網頁API （安全資源）的URL。 若要尋找應用程式ID URL，請在Azure入口網站中，按一下 [!DNL Azure Active Directory]，按一下「應用程式註冊」 ，開啟應用程式的「設定」頁面，然後按一下「屬性」 。 也可能是外部資源，例如 `https://graph.microsoft.com`. 這通常是Dynamics執行個體的URL。

1. 在您按一下 **[!UICONTROL Submit]**，系統會提示您使用 [!DNL Azure Active Directory]. 驗證成功後，您的Dynamics帳戶將會在中以資料提供者的身分連線 [!DNL Marketo Measure].

## 重新驗證您的Dynamics帳戶 {#re-authenticating-your-dynamics-account}

1. 當您在 [!DNL Marketo Measure] 應用程式，前往 **[!UICONTROL My Settings]** > **[!UICONTROL Settings]** > **[!UICONTROL Connections]**.

1. 按一下Dynamics連線旁CRM區段中的鍵圖示。

1. 按一下金鑰後，畫面會顯示快顯視窗，提示您輸入使用者端ID、使用者端密碼和應用程式ID URI，類似於註冊流程。

   ![](assets/re-authenticating-3.png)

1. 在您按一下 **[!UICONTROL Submit]**，系統會提示您使用 [!DNL Azure Active Directory]. 驗證成功後，您的Dynamics帳戶將會在中重新授權 [!DNL Marketo Measure].
