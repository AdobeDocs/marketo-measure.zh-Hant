---
description: 『[!DNL Marketo Measure] 與Adobe Launch整合 —  [!DNL Marketo Measure]『
title: 『[!DNL Marketo Measure] 與Adobe Launch的整合
exl-id: 316ee8a8-b2d3-42e9-9ee5-c9b1d91c2769
feature: Integration
source-git-commit: 6aaf6fd26f19e9382cc559e54558e1c5d84cfd6d
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 0%

---

# [!DNL Marketo Measure] 整合Adobe Launch {#marketo-measure-integrations-with-adobe-launch}

Adobe Launch擴充功能是專為現有的 [!DNL Marketo Measure] 已在網站上使用AdobeLaunch的使用者。 擴充功能可作為標籤管理解決方案，用於根據特定事件和條件設定及動態載入頁面上的指令碼。

在Adobe Launch中完成安裝和設定後， [!DNL Marketo Measure] 擴充功能會將bizible.js指令碼載入出現AdobeLaunch指令碼的頁面上。 這可讓行銷人員透過Adobe Launch設定新增bizible.js，而非明確修改網頁以新增bizible.js指令碼標籤。

## 設定Adobe Launch擴充功能 {#configure-the-adobe-launch-extension}

>[!PREREQUISITES]
>
>請參閱下列連結，深入瞭解AdobeLaunch及其擴充功能：
>
>* [[!DNL Marketo Measure] 副檔名](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email/bizible.html#catalog){target="_blank"}
>* [AdobeLaunch概述](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/overview.html){target="_blank"}
>* [Adobe Launch擴充功能概觀](https://experienceleague.adobe.com/docs/experience-platform/tags/extension-dev/overview.html){target="_blank"}

1. 依照下列步驟建立屬性 [本文章](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/configure-tags/create-a-property.html#go-to-the-data-collection-interface){target="_blank"}.

1. 按一下您建立的屬性。

   ![](assets/marketo-measure-integrations-with-adobe-launch-1.png)

1. 按一下 **[!UICONTROL Extensions]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-2.png)

1. 按一下 **[!UICONTROL Catalog]** 索引標籤並搜尋&quot;[!UICONTROL Bizible].」

   ![](assets/marketo-measure-integrations-with-adobe-launch-3.png)

1. 在 [!UICONTROL Bizible Analytics] 圖磚，按一下 **[!UICONTROL Install]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-4.png)

1. 在Bizible AccountId欄位中，輸入您網站的URL (例如 `adobe.com`)。

   ![](assets/marketo-measure-integrations-with-adobe-launch-5.png)

1. 按一下 **[!UICONTROL Save]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-6.png)

1. 按一下 **[!UICONTROL Rules]**，然後選取 **[!UICONTROL Create New Rule]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-7.png)

1. 按一下 **[!UICONTROL Add]** 按鈕在 [!UICONTROL Events].

   ![](assets/marketo-measure-integrations-with-adobe-launch-8.png)

1. 在「擴充功能」下拉式清單中，選取 **[!UICONTROL Core]**. 然後在「事件型別」下拉式清單中，選取 **[!UICONTROL Library Loaded (Page Top)]**. 如果您未提供事件的名稱，系統會套用預設名稱。 按一下 **[!UICONTROL Keep Changes]** 完成時。

   ![](assets/marketo-measure-integrations-with-adobe-launch-9.png)

1. 按一下 **[!UICONTROL Add]** 按鈕。

   ![](assets/marketo-measure-integrations-with-adobe-launch-10.png)

1. 在「擴充功能」下拉式清單中，選取 **[!UICONTROL Bizible Analytics]**. 然後在「動作型別」下拉式清單中，選取 **[!UICONTROL Initialize]**. 如果您未提供動作的名稱，則會套用預設名稱。 按一下 **[!UICONTROL Keep Changes]** 完成時。

   ![](assets/marketo-measure-integrations-with-adobe-launch-11.png)

1. 按一下 **[!UICONTROL Save]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-12.png)

