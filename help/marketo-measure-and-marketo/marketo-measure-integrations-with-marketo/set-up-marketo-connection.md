---
unique-page-id: 42762762
description: 設定Marketo連線 —  [!DNL Marketo Measure]
title: 設定Marketo連線
exl-id: 11660539-1cc5-4768-8f22-d6f7cd0b94f3
feature: Integration
source-git-commit: de366de2d1df3d4dc9fc33e5fd0dab225b6af081
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 1%

---

# 設定Marketo連線 {#set-up-marketo-connection}

以下說明如何設定您與Marketo的連線。

>[!PREREQUISITES]
>
>[為[!DNL Marketo Measure]/Marketo Engage連線建立僅API使用者角色](https://experienceleague.adobe.com/docs/marketo/using/product-docs/administration/users-and-roles/create-an-api-only-user.html?lang=zh-Hant){target="_blank"}。

1. 在[!DNL Marketo Measure]中，按一下&#x200B;**[!UICONTROL My Account]**&#x200B;下拉式清單並選取&#x200B;**[!UICONTROL Settings]**。

   ![](assets/set-up-marketo-connection-1.png)

1. 在[!UICONTROL Integrations]底下，按一下&#x200B;**[!UICONTROL Connections]**。

   ![](assets/set-up-marketo-connection-2.png)

1. 按一下「**[!UICONTROL Set Up New CRM Connection]**」。

   ![](assets/set-up-marketo-connection-3.png)

1. 按一下Marketo旁的&#x200B;**[!UICONTROL Connect]**&#x200B;按鈕。

   ![](assets/set-up-marketo-connection-4.png)

1. 在新標籤中，登入您的Marketo Engage帳戶。 移至&#x200B;**管理員** > **網站服務**。 向下捲動至REST API。 反白顯示並儲存端點與身分識別服務URL。 您需要在下列步驟中使用這些值。

   ![](assets/set-up-marketo-connection-5.png)

1. 仍在Marketo Engage中，請在左側的樹狀結構中選取&#x200B;**LaunchPoint**。 尋找您要連線至Marketo Measure的自訂服務，然後按一下[檢視詳細資料]。**&#x200B;**

   ![](assets/set-up-marketo-connection-6.png)

1. 反白顯示並儲存使用者端ID和使用者端密碼。 按一下 **關閉**。

   ![](assets/set-up-marketo-connection-7.png)

1. 返回[!DNL Marketo Measure]，將您收集的資料填入欄位中。

   ![](assets/set-up-marketo-connection-8.png)

1. 輸入值後，按一下&#x200B;**[!UICONTROL Authenticate]**。 您的Marketo Engage帳戶已連線至[!DNL Marketo Measure]。

   ![](assets/set-up-marketo-connection-9.png)

   >[!NOTE]
   >
   >[!DNL Marketo Measure]會代表您呼叫Marketo API，而不會消耗任何Marketo API限制，因此您不需要擔心與其他整合的次數上限和評分分配。
