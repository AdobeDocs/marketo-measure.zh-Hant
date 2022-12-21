---
unique-page-id: 18874767
description: 設定Boomerang階段 —  [!DNL Marketo Measure]  — 產品檔案
title: 設定Boomerang階段
exl-id: 00dd2826-27a3-462e-a70e-4cec90d07f92
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 0%

---

# 設定Boomerang階段 {#setting-up-boomerang-stages}

啟用 [!UICONTROL Boomerang] 帳戶的階段，您必須是帳戶管理員。 或者，您可以透過 [Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;}。 啟用功能後，請依照下列指示進行設定。

## 波美朗階段設定 {#boomerang-stage-setup}

1. 前往 [!UICONTROL Stage Mapping]. 在標題為「[!UICONTROL Boomerang],&quot;選擇要跟蹤的階段旁邊的框。

   ![](assets/1-2.png)

1. 前往 [!UICONTROL Attribution Settings] 標籤，並輸入您要檢視之每個階段的接觸點數量。 我們最多允許10個。 預設值設為1。

   ![](assets/2-2.png)

1. 按一下 **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >請允許24到48小時，根據這些變更重新處理您的資料。

## 具有自訂模型歸因的Boomerang階段設定 {#boomerang-stage-setup-with-custom-model-attribution}

1. 前往 [!UICONTROL Stage Mapping]. 在標題為「[!UICONTROL Boomerang],&quot;選擇要跟蹤的階段旁邊的框。

   ![](assets/3-1.png)

1. 如果您也希望這些Boomerang階段包含在您的自訂模型中並獲得歸因評分，請務必也選取「[!UICONTROL Custom Model]」欄。

   ![](assets/4-1.png)

1. 前往 [!UICONTROL Attribution Settings] 標籤。 決定您要如何加權自食果階段的歸因。 選項是對第一次出現、最後一次出現的歸因進行加權，或將歸因平均分割到所有發生次數。

   ![](assets/5-1.png)

1. 輸入每個階段要查看的發生次數。 我們最多可以允許10個。 預設值設為1。

   ![](assets/6-1.png)

1. 設定要分配給自訂模型中已包括的Boomerang階段的歸因百分比。 請確保所有階段的歸因總計為100%。 按一下 **[!UICONTROL Save and Process]**.

   ![](assets/7-1.png)

   >[!NOTE]
   >
   >請允許24到48小時，根據這些變更重新處理您的資料。
