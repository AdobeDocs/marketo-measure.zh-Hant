---
unique-page-id: 18874747
description: 正在新增 [!DNL Marketo Measure] 指令碼至Sitecore頁面 —  [!DNL Marketo Measure]
title: 正在新增 [!DNL Marketo Measure] 指令碼至Sitecore頁面
exl-id: 87ce1857-7532-45a7-8c39-255c6118b50a
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 0%

---

# 正在新增[!DNL Marketo Measure]指令碼至Sitecore頁面 {#adding-marketo-measure-script-to-sitecore-pages}

除了標準指令碼實作之外，內容管理系統可能還需要其他步驟，以讓[!DNL Marketo Measure]識別表單提交。 以下程式概述如何將[!DNL Marketo Measure] JavaScript新增至您的[!DNL Sitecore]頁面。

對於具有Sitecore頁面的網站：

1. 登入Sitecore並導覽至您的網站。 找出與[!UICONTROL Home]專案和[!UICONTROL Metadata]資料夾位於相同層級的[!UICONTROL Configuration]資料夾。
1. 按一下[!UICONTROL Configuration]資料夾旁的&#x200B;**[!UICONTROL +]**。
1. 按一下[!UICONTROL Tools]資料夾旁的&#x200B;**[!UICONTROL +]**。
1. 選取[!UICONTROL Javascript]專案。
1. 在[!UICONTROL Content]索引標籤中，按一下&#x200B;**[!UICONTROL Lock and Edit]**&#x200B;連結以解除鎖定要編輯的專案。
1. 尋找[!UICONTROL 'JavaScript']區段。 如果尚未展開，請按一下&#x200B;**[!UICONTROL +]**。
1. 輸入我們的指令碼： `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js"async=""></script>`
1. 按一下左上角的&#x200B;**[!UICONTROL Save]**。
