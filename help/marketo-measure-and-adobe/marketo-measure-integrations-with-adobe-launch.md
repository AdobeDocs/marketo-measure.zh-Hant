---
description: '''[!DNL Marketo Measure] 整合Adobe啟動 —  [!DNL Marketo Measure]  — 產品檔案`'
title: '''[!DNL Marketo Measure] 與Adobe啟動的整合'
exl-id: 316ee8a8-b2d3-42e9-9ee5-c9b1d91c2769
source-git-commit: 19f670505358b04fb26620574b71c2af8d0d9847
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 0%

---

# [!DNL Marketo Measure] 與Adobe啟動的整合 {#marketo-measure-integrations-with-adobe-launch}

AdobeLaunch擴充功能是針對現有 [!DNL Marketo Measure] 已在其網站上運用AdobeLaunch的使用者。 擴充功能可做為標籤管理解決方案，讓您根據特定事件和條件在頁面上設定及動態載入指令碼。

在AdobeLaunch中安裝並設定後， [!DNL Marketo Measure] 擴充功能會在有AdobeLaunch指令碼的頁面上載入bizible.js指令碼。 這可讓行銷人員透過AdobeLaunch設定新增bizible.js，而非明確修改網頁以新增bizible.js指令碼標籤。

## 設定AdobeLaunch擴充功能 {#configure-the-adobe-launch-extension}

>[!PREREQUISITES]
>
>請查看下列連結，以進一步了解AdobeLaunch及其擴充功能：
>
>* [[!DNL Marketo Measure] 擴充功能](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email/bizible.html?lang=en#catalog){target="_blank"}
>* [Adobe啟動概述](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/index.html?lang=en#prerequisites){target="_blank"}
>* [AdobeLaunch擴充功能概觀](https://experienceleague.adobe.com/docs/launch/using/extension-dev/overview.html?lang=en#extension-configuration){target="_blank"}


1. 依照步驟建立屬性 [本文](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/configure-tags/create-a-property.html?lang=en#go-to-the-data-collection-interface){target="_blank"}.

1. 按一下您剛建立的屬性。

   ![](assets/marketo-measure-integrations-with-adobe-launch-1.png)

1. 按一下 **[!UICONTROL Extensions]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-2.png)

1. 按一下 **[!UICONTROL Catalog]** 標籤和搜索「[!UICONTROL Bizible].&quot;

   ![](assets/marketo-measure-integrations-with-adobe-launch-3.png)

1. 在 [!UICONTROL Bizible Analytics] 拼貼，按一下 **[!UICONTROL Install]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-4.png)

1. 在「Bizible AccountId」欄位中，輸入您網站的URL。

   ![](assets/marketo-measure-integrations-with-adobe-launch-5.png)

   >[!NOTE]
   >
   >此欄位不是Business_Prod.Business表中的「帳戶ID」。 來自指定URL的所有Web活動都會對應至 [!DNL Marketo Measure] 租用戶。

1. 按一下 **[!UICONTROL Save]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-6.png)

1. 按一下 **[!UICONTROL Rules]**，然後選取 **[!UICONTROL Create New Rule]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-7.png)

1. 按一下 **[!UICONTROL Add]** 按鈕 [!UICONTROL Events].

   ![](assets/marketo-measure-integrations-with-adobe-launch-8.png)

1. 在「擴充功能」下拉式清單中，選取 **[!UICONTROL Core]**. 然後，在「事件類型」下拉式清單中，選取 **[!UICONTROL Library Loaded (Page Top)]**. 如果您未為事件命名，則會套用預設名稱。 按一下 **[!UICONTROL Keep Changes]** 時才能使用。

   ![](assets/marketo-measure-integrations-with-adobe-launch-9.png)

1. 按一下 **[!UICONTROL Add]** 按鈕。

   ![](assets/marketo-measure-integrations-with-adobe-launch-10.png)

1. 在「擴充功能」下拉式清單中，選取 **[!UICONTROL Bizible Analytics]**. 然後，在「動作類型」下拉式清單中，選取 **[!UICONTROL Initialize]**. 如果您未為動作命名，則會套用預設名稱。 按一下 **[!UICONTROL Keep Changes]** 時才能使用。

   ![](assets/marketo-measure-integrations-with-adobe-launch-11.png)

1. 按一下 **[!UICONTROL Save]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-12.png)
