---
description: 為Marketo Measure使用者設定Marketo連線指南
title: 設定Marketo連線
exl-id: 11660539-1cc5-4768-8f22-d6f7cd0b94f3
feature: Integration
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 4%

---

# 設定Marketo連線 {#set-up-marketo-connection}

以下說明如何設定您與Marketo的連線。

>[!PREREQUISITES]
>
>[為](https://experienceleague.adobe.com/docs/marketo/using/product-docs/administration/users-and-roles/create-an-api-only-user.html)/Marketo Engage連線建立僅API使用者角色[!DNL Marketo Measure]。

1. 在[!DNL Marketo Measure]中，按一下&#x200B;**[!UICONTROL My Account]**&#x200B;下拉式清單並選取&#x200B;**[!UICONTROL Settings]**。

   ![1. 在Marketo Measure中，按一下「我的帳戶」下拉式清單及](assets/set-connection-7.png)

1. 在[!UICONTROL Integrations]底下，按一下&#x200B;**[!UICONTROL Connections]**。

   ![1. 在「整合」底下，按一下「連線」。](assets/set-connection-8.png)

1. 按一下「**[!UICONTROL Set Up New CRM Connection]**」。

   ![1. 按一下[設定新的CRM連線]。](assets/set-connection-9.png)

1. 按一下Marketo旁的&#x200B;**[!UICONTROL Connect]**&#x200B;按鈕。

   ![1. 按一下Marketo旁的[連線]按鈕。](assets/set-connection-5.png)

1. 在新標籤中，登入您的Marketo Engage帳戶。 移至&#x200B;**管理員** > **網站服務**。 向下捲動至REST API。 反白顯示並儲存端點與身分識別服務URL。 您需要在下列步驟中使用這些值。

   ![1. 在新標籤中，登入您的Marketo Engage帳戶。](assets/set-connection-6.png)

1. 仍然在Marketo Engage中，在左側的樹狀結構中選取&#x200B;**LaunchPoint**。 尋找您要連線至Marketo Measure的自訂服務，然後按一下[檢視詳細資料]。****

   ![1. 仍然在Marketo Engage中，選取](assets/set-connection-4.png)樹狀結構中的LaunchPoint

1. 反白顯示並儲存使用者端ID和使用者端密碼。 按一下 **關閉**。

   ![1. 反白顯示並儲存使用者端ID和使用者端密碼。 按一下[關閉]。](assets/set-connection-3.png)

1. 返回[!DNL Marketo Measure]，將您收集的資料填入欄位中。

   ![1. 返回Marketo Measure，將資料填入欄位中](assets/set-connection-1.png)

1. 輸入值後，按一下&#x200B;**[!UICONTROL Authenticate]**。 您的Marketo Engage帳戶已連線至[!DNL Marketo Measure]。

   ![1. 輸入值後，按一下「驗證」。 您的Marketo Engage](assets/set-connection-2.png)

   >[!NOTE]
   >
   >[!DNL Marketo Measure]會代表您呼叫Marketo API，而不會消耗任何Marketo API限制，因此您不需要擔心與其他整合的次數上限和評分分配。
