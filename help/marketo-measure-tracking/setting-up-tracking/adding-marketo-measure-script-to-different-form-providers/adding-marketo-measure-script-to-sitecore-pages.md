---
unique-page-id: 18874747
description: 新增 [!DNL Marketo Measure] Sitecore頁面的指令碼 —  [!DNL Marketo Measure]
title: 新增 [!DNL Marketo Measure] Sitecore頁面的指令碼
exl-id: 87ce1857-7532-45a7-8c39-255c6118b50a
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 0%

---

# 新增 [!DNL Marketo Measure] Sitecore頁面的指令碼 {#adding-marketo-measure-script-to-sitecore-pages}

內容管理系統可能需要在的標準指令碼實施之外進行其他步驟 [!DNL Marketo Measure] 以辨識表單提交。 以下程式概述如何新增 [!DNL Marketo Measure] 您的javascript [!DNL Sitecore] 頁面。

對於具有Sitecore頁面的網站：

1. 登入Sitecore並導覽至您的網站。 找到 [!UICONTROL Configuration] 與位於相同層級的資料夾 [!UICONTROL Home] 專案和 [!UICONTROL Metadata] 資料夾。
1. 按一下 **[!UICONTROL +]** 在 [!UICONTROL Configuration] 資料夾。
1. 按一下 **[!UICONTROL +]** 在 [!UICONTROL Tools] 資料夾。
1. 選取 [!UICONTROL Javascript] 個專案。
1. 在 [!UICONTROL Content] 索引標籤，按一下 **[!UICONTROL Lock and Edit]** 解鎖專案以進行編輯的連結。
1. 尋找 [!UICONTROL 'JavaScript'] 區段。 如果尚未展開，請按一下 **[!UICONTROL +]**.
1. 輸入我們的指令碼： `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js"async=""></script>`
1. 按一下 **[!UICONTROL Save]** 左上角。
