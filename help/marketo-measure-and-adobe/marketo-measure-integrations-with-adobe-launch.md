---
description: '[!DNL Marketo Measure]與Adobe啟動整合 —  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure]與Adobe啟動整合'
exl-id: 316ee8a8-b2d3-42e9-9ee5-c9b1d91c2769
feature: Integration
source-git-commit: 6aaf6fd26f19e9382cc559e54558e1c5d84cfd6d
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 1%

---

# [!DNL Marketo Measure]與Adobe啟動整合 {#marketo-measure-integrations-with-adobe-launch}

Adobe Launch擴充功能是專為已在網站上使用Adobe Launch的現有[!DNL Marketo Measure]使用者所設計。 擴充功能可作為標籤管理解決方案，用於根據特定事件和條件設定及動態載入頁面上的指令碼。

在Adobe Launch中安裝並設定後，[!DNL Marketo Measure]擴充功能會在有Adobe Launch指令碼的頁面上載入bizible.js指令碼。 這可讓行銷人員透過Adobe Launch設定新增bizible.js，而非明確修改網頁以新增bizible.js指令碼標籤。

## 設定Adobe Launch擴充功能 {#configure-the-adobe-launch-extension}

>[!PREREQUISITES]
>
>請參閱下列連結，深入瞭解AdobeLaunch及其擴充功能：
>
>* [[!DNL Marketo Measure] 延伸模組](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email/bizible.html#catalog){target="_blank"}
>* [Adobe啟動概述](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/overview.html){target="_blank"}
>* [Adobe啟動擴充功能概觀](https://experienceleague.adobe.com/docs/experience-platform/tags/extension-dev/overview.html){target="_blank"}

1. 依照本文[&#128279;](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/configure-tags/create-a-property.html#go-to-the-data-collection-interface){target="_blank"}中的步驟建立屬性。

1. 按一下您建立的屬性。

   ![](assets/marketo-measure-integrations-with-adobe-launch-1.png)

1. 按一下「**[!UICONTROL Extensions]**」。

   ![](assets/marketo-measure-integrations-with-adobe-launch-2.png)

1. 按一下&#x200B;**[!UICONTROL Catalog]**&#x200B;索引標籤並搜尋&quot;[!UICONTROL Bizible]&quot;。

   ![](assets/marketo-measure-integrations-with-adobe-launch-3.png)

1. 在[!UICONTROL Bizible Analytics]圖磚中，按一下&#x200B;**[!UICONTROL Install]**。

   ![](assets/marketo-measure-integrations-with-adobe-launch-4.png)

1. 在Bizible AccountId欄位中，輸入您網站的URL （例如，`adobe.com`）。

   ![](assets/marketo-measure-integrations-with-adobe-launch-5.png)

1. 按一下「**[!UICONTROL Save]**」。

   ![](assets/marketo-measure-integrations-with-adobe-launch-6.png)

1. 按一下&#x200B;**[!UICONTROL Rules]**，然後選取&#x200B;**[!UICONTROL Create New Rule]**。

   ![](assets/marketo-measure-integrations-with-adobe-launch-7.png)

1. 按一下[!UICONTROL Events]下方的&#x200B;**[!UICONTROL Add]**&#x200B;按鈕。

   ![](assets/marketo-measure-integrations-with-adobe-launch-8.png)

1. 在「擴充功能」下拉式清單中，選取&#x200B;**[!UICONTROL Core]**。 然後在「事件型別」下拉式清單中，選取&#x200B;**[!UICONTROL Library Loaded (Page Top)]**。 如果您未提供事件的名稱，系統會套用預設名稱。 完成時，按一下&#x200B;**[!UICONTROL Keep Changes]**。

   ![](assets/marketo-measure-integrations-with-adobe-launch-9.png)

1. 按一下「動作」底下的&#x200B;**[!UICONTROL Add]**&#x200B;按鈕。

   ![](assets/marketo-measure-integrations-with-adobe-launch-10.png)

1. 在「擴充功能」下拉式清單中，選取&#x200B;**[!UICONTROL Bizible Analytics]**。 然後在「動作型別」下拉式清單中，選取&#x200B;**[!UICONTROL Initialize]**。 如果您未提供動作的名稱，則會套用預設名稱。 完成時，按一下&#x200B;**[!UICONTROL Keep Changes]**。

   ![](assets/marketo-measure-integrations-with-adobe-launch-11.png)

1. 按一下「**[!UICONTROL Save]**」。

   ![](assets/marketo-measure-integrations-with-adobe-launch-12.png)

