---
unique-page-id: 18874743
description: 正在連線 [!DNL Marketo Measure] 若要取消退回指令碼管理員 —  [!DNL Marketo Measure]  — 產品檔案
title: 正在連線 [!DNL Marketo Measure] 至彈回指令碼管理員
exl-id: c3212bc3-1d8f-4da5-bb2d-11ffd2fb4e98
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 1%

---

# 正在連線 [!DNL Marketo Measure] 至彈回指令碼管理員 {#connecting-marketo-measure-to-unbounce-script-manager}

[!DNL Marketo Measure] 直接與「反彈」整合，好讓您直接在中追蹤登陸頁面轉換的數位行銷來源 [!DNL Salesforce]. 若要建立連線，只需新增 [!DNL Marketo Measure] 編寫指令碼至您的退信指令碼管理員。 方法如下。

1. 登入您的 [!DNL Unbounce] 帳戶。
1. 按一下 **[!UICONTROL Settings]** > **[!UICONTROL Script Manager]** > **[!UICONTROL Add Script]**.
1. 在快顯視窗中選取 [!UICONTROL Custom Script] 並將其命名為&quot;[!DNL Marketo Measure Marketing Analytics].」 按一下 **[!UICONTROL Add Script Details]**.
1. 選取Head中的位置。 在主要登陸頁面和表單確認對話方塊中包含指令碼。 貼上 [!DNL Marketo Measure] 下方指令碼放入方塊中。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 按一下 **[!UICONTROL Save]**.

此 [!DNL Marketo Measure] 整合適用於反彈登陸頁面，前提是這些登陸頁面託管於您的網域(例如landing.mysite.com)，而非使用unbounce.com網域的網域。
