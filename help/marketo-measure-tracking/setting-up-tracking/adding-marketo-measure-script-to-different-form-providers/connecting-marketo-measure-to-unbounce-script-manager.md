---
unique-page-id: 18874743
description: 正在連線 [!DNL Marketo Measure] 至解除退回指令碼管理員 —  [!DNL Marketo Measure]
title: 正在連線 [!DNL Marketo Measure] 至解除退回指令碼管理員
exl-id: c3212bc3-1d8f-4da5-bb2d-11ffd2fb4e98
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 0%

---

# 正在將[!DNL Marketo Measure]連線到解除指令碼管理員 {#connecting-marketo-measure-to-unbounce-script-manager}

[!DNL Marketo Measure]直接與「取消退回」整合，可讓您直接在[!DNL Salesforce]中追蹤登陸頁面轉換的數位行銷來源。 若要建立連線，只需將[!DNL Marketo Measure]指令碼新增至您的「彈回指令碼管理員」即可。 方法如下。

1. 登入您的[!DNL Unbounce]帳戶。
1. 按一下&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Script Manager]** > **[!UICONTROL Add Script]**。
1. 在快顯視窗中，選取[!UICONTROL Custom Script]並將其命名為&quot;[!DNL Marketo Measure Marketing Analytics]&quot;。 按一下&#x200B;**[!UICONTROL Add Script Details]**。
1. 選取Head中的位置。 在主要登陸頁面和表單確認對話方塊中包含指令碼。 將下方的[!DNL Marketo Measure]指令碼貼到方塊中。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 按一下&#x200B;**[!UICONTROL Save]**。

[!DNL Marketo Measure]整合適用於彈回登陸頁面，前提是這些頁面託管於您的網域(例如landing.mysite.com)上，而非使用unbounce.com網域的網域。
