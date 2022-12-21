---
unique-page-id: 18874747
description: 新增 [!DNL Marketo Measure] 指令碼至網站核心頁面 —  [!DNL Marketo Measure]  — 產品檔案
title: 新增 [!DNL Marketo Measure] 指令碼至網站核心頁面
exl-id: 87ce1857-7532-45a7-8c39-255c6118b50a
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 0%

---

# 新增 [!DNL Marketo Measure] 指令碼至網站核心頁面 {#adding-marketo-measure-script-to-sitecore-pages}

內容管理系統可能需要執行標準指令碼實施以外的其他步驟， [!DNL Marketo Measure] 識別表單提交。 以下程式概述如何新增 [!DNL Marketo Measure] javascript至 [!DNL Sitecore] 頁面。

若是具有Sitecore頁面的網站：

1. 登入Sitecore並導覽至您的網站。 找出 [!UICONTROL Configuration] 與 [!UICONTROL Home] 項目和 [!UICONTROL Metadata] 檔案夾。
1. 按一下 **[!UICONTROL +]** 旁邊 [!UICONTROL Configuration] 檔案夾。
1. 按一下 **[!UICONTROL +]** 旁邊 [!UICONTROL Tools] 檔案夾。
1. 選取 [!UICONTROL Javascript] 項目。
1. 在 [!UICONTROL Content] ，按一下 **[!UICONTROL Lock and Edit]** 連結以解除鎖定項目以進行編輯。
1. 尋找 [!UICONTROL 'JavaScript'] 區段。 如果尚未展開，請按一下 **[!UICONTROL +]**.
1. 輸入指令碼： `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js"async=""></script>`
1. 按一下 **[!UICONTROL Save]** 在左上角。
