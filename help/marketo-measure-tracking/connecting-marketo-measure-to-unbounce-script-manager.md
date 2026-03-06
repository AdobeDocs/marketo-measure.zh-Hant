---
description: 正在連線至Marketo Measure使用者的 [!DNL Marketo Measure] 取消退回指令碼管理員指南
title: 正在連線 [!DNL Marketo Measure] 至解除退回指令碼管理員
exl-id: c3212bc3-1d8f-4da5-bb2d-11ffd2fb4e98
feature: Tracking
source-git-commit: 7a4661c8d42214d32e5360dc45d6d880b08ef37c
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 3%

---


# 正在將[!DNL Marketo Measure]連線到解除指令碼管理員 {#connecting-marketo-measure-to-unbounce-script-manager}

[!DNL Marketo Measure]直接與「取消退回」整合，可讓您直接在[!DNL Salesforce]中追蹤登陸頁面轉換的數位行銷來源。 若要建立連線，只需將[!DNL Marketo Measure]指令碼新增至您的「彈回指令碼管理員」即可。 方法如下。

1. 登入您的[!DNL Unbounce]帳戶。
1. 按一下&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Script Manager]** > **[!UICONTROL Add Script]**。
1. 在快顯視窗中，選取[!UICONTROL Custom Script]並將其命名為&quot;[!DNL Marketo Measure Marketing Analytics]&quot;。 按一下「**[!UICONTROL Add Script Details]**」。
1. 選取Head中的位置。 在主要登陸頁面和表單確認對話方塊中包含指令碼。 將下方的[!DNL Marketo Measure]指令碼貼到方塊中。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 按一下「**[!UICONTROL Save]**」。

[!DNL Marketo Measure]整合適用於彈回登陸頁面，前提是這些頁面託管於您的網域(例如landing.mysite.com)上，而非使用unbounce.com網域的網域。
