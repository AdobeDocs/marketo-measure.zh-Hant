---
unique-page-id: 18874743
description: 連接 [!DNL Marketo Measure] 取消退回指令碼管理器 —  [!DNL Marketo Measure]  — 產品檔案
title: 連接 [!DNL Marketo Measure] 取消退信指令碼管理器
exl-id: c3212bc3-1d8f-4da5-bb2d-11ffd2fb4e98
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 1%

---

# 連接 [!DNL Marketo Measure] 取消退信指令碼管理器 {#connecting-marketo-measure-to-unbounce-script-manager}

[!DNL Marketo Measure] 與Unbounce直接整合，可讓您直接在 [!DNL Salesforce]. 若要建立連線，只需新增 [!DNL Marketo Measure] 指令碼至Unbounce Script Manager。 這是方法。

1. 登入 [!DNL Unbounce] 帳戶。
1. 按一下 **[!UICONTROL Settings]** > **[!UICONTROL Script Manager]** > **[!UICONTROL Add Script]**.
1. 在快顯視窗中，選取 [!UICONTROL Custom Script] 將其命名為「[!DNL Marketo Measure Marketing Analytics].&quot; 按一下 **[!UICONTROL Add Script Details]**.
1. 在頭中選取放置。 在主要登陸頁面和表單確認對話方塊中加入指令碼。 貼上 [!DNL Marketo Measure] 指令碼。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 按一下 **[!UICONTROL Save]**.

此 [!DNL Marketo Measure] 只要整合托管於您的網域（例如landing.mysite.com），而非使用unbounce.com網域的登錄頁面，則整合就能在「取消退回」登陸頁面上運作。
