---
unique-page-id: 18874767
description: 設定Boomerang階段 —  [!DNL Marketo Measure]  — 產品檔案
title: 設定Boomerang階段
exl-id: 00dd2826-27a3-462e-a70e-4cec90d07f92
source-git-commit: 01be819ccee1b3079b15a748480e9dacf6adb488
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 0%

---

# 設定Boomerang階段 {#setting-up-boomerang-stages}

>[!AVAILABILITY]
>
>Boomerang功能僅對第3級客戶啟用。 若要要求更高的帳戶層級，請聯絡Adobe帳戶團隊（您的帳戶經理）。

若要啟用 [!UICONTROL Boomerang] 您的帳戶階段，您必須是帳戶管理員。 或者，您也可以透過以下方式啟用： [Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}. 啟用功能後，請依照下列指示進行設定。

## 迴音廊階段設定 {#boomerang-stage-setup}

1. 前往 [!UICONTROL Stage Mapping]. 在標題為「」的欄下[!UICONTROL Boomerang]，」選取您要追蹤的階段旁的方塊。

   ![](assets/1-2.png)

1. 前往 [!UICONTROL Attribution Settings] 定位並輸入您要檢視之每個階段的接觸點數目。 我們最多允許10個。 預設值設為1。

   ![](assets/2-2.png)

1. 按一下 **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >請允許24到48小時根據這些變更重新處理您的資料。

## 自訂模型歸因的Boomerang階段設定 {#boomerang-stage-setup-with-custom-model-attribution}

1. 前往 [!UICONTROL Stage Mapping]. 在標題為「」的欄下[!UICONTROL Boomerang]，」選取您要追蹤的階段旁的方塊。

   ![](assets/3-1.png)

1. 如果您也希望將這些Boomerang階段包含在自訂模型中並接收歸因評分，請務必也選取「[!UICONTROL Custom Model]「 」欄。

   ![](assets/4-1.png)

1. 前往 [!UICONTROL Attribution Settings] 標籤。 決定您要如何為回溯期階段加權歸因。 選項包括在第一次發生、最後一次發生時加權歸因，或將其平均分割到所有發生次數。

   ![](assets/5-1.png)

1. 輸入您要檢視之每個階段的發生次數。 最多允許10個。 預設值設為1。

   ![](assets/6-1.png)

1. 設定您要配置給已納入自訂模型中的Boomerang階段的歸因百分比。 請確定所有階段的歸因總數加起來為100%。 按一下 **[!UICONTROL Save and Process]**.

   ![](assets/7-1.png)

   >[!NOTE]
   >
   >請允許24到48小時根據這些變更重新處理您的資料。
