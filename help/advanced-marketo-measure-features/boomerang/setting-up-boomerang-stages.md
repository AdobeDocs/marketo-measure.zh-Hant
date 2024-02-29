---
unique-page-id: 18874767
description: 設定回力艙階段 —  [!DNL Marketo Measure]
title: 設定回車族階段
exl-id: 00dd2826-27a3-462e-a70e-4cec90d07f92
feature: Boomerang
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 0%

---

# 設定回車族階段 {#setting-up-boomerang-stages}

>[!AVAILABILITY]
>
>Boomerang功能僅針對第3級客戶啟用。 若要要求更高的客戶層級，請聯絡Adobe客戶團隊（您的客戶經理）。

若要啟用 [!UICONTROL Boomerang] 您的帳戶階段，您必須是帳戶管理員。 或者，您也可以透過連絡以啟用 [Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}. 啟用功能後，請依照這些指示進行設定。

## 迴旋鏢階段設定 {#boomerang-stage-setup}

1. 前往 [!UICONTROL Stage Mapping]. 在標題為「」的欄下[!UICONTROL Boomerang]，」選取您要追蹤的階段旁的方塊。

   ![](assets/1-2.png)

1. 前往 [!UICONTROL Attribution Settings] 定位並輸入您要檢視之每個階段的接觸點數目。 我們最多允許10個。 預設值設為1。

   ![](assets/2-2.png)

1. 按一下 **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >允許24到48小時根據這些變更重新處理您的資料。

## 使用自訂模型歸因的Boomerang階段設定 {#boomerang-stage-setup-with-custom-model-attribution}

1. 前往 [!UICONTROL Stage Mapping]. 在標題為「」的欄下[!UICONTROL Boomerang]，」選取您要追蹤的階段旁的方塊。

   ![](assets/3-1.png)

1. 如果您也希望將這些Boomerang階段包含在自訂模型中並接收歸因評分，請務必選取「[!UICONTROL Custom Model]「欄。

   ![](assets/4-1.png)

1. 前往 [!UICONTROL Attribution Settings] 標籤。 決定您要如何為回溯期階段加權歸因。 選項是在第一次發生、最後一次發生時加權歸因，或將其平均分割為所有發生次數。

   ![](assets/5-1.png)

1. 輸入您要檢視之每個階段的發生次數。 最多允許10個。 預設值設為1。

   ![](assets/6-1.png)

1. 設定歸因百分比，您要將其配置給已納入自訂模型中的「回車族階段」 。 確定所有階段的歸因總數為100%。 按一下 **[!UICONTROL Save and Process]**.

   ![](assets/7-1.png)

   >[!NOTE]
   >
   >允許24到48小時根據這些變更重新處理您的資料。
