---
unique-page-id: 42762628
description: Passport儀表板檔案 —  [!DNL Marketo Measure]  — 產品檔案
title: Passport Dashboard檔案
exl-id: 43cb01a8-d02e-4086-af57-d7ec9275f87a
feature: Reporting
source-git-commit: f8a37a996afefe78900e57e1eb166cdd50b5347f
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 0%

---

# Passport Dashboard檔案 {#passport-dashboard-documentation}

Passport儀表板可讓行銷人員檢視在指定時間段內經過每個管道階段的銷售機會/聯絡人以及商機。

此儀表板有兩個圖磚：

* 機會：在指定的時間範圍內，每個階段傳遞的機會記錄數。
* 銷售機會/聯絡人：在指定的時間範圍內，每個階段傳遞的銷售機會或聯絡人記錄數。

>[!NOTE]
>
>在所有Discover儀表板中，只能報告一個人員物件，即潛在客戶或聯絡人。 此設定於 [!UICONTROL Settings] > [!UICONTROL Reporting] > [!UICONTROL Attribution Settings] > [!UICONTROL Default Dashboard Object].

此控制面板支援下列篩選器（所有篩選器皆適用於兩個圖磚）：

* 日期：選取時間範圍。
* 管道：依管道篩選記錄。 如果某個管道具有關聯的接觸點，該管道就會與記錄相關聯。
* 子管道：依子管道篩選記錄。 如果記錄的任何接觸點與子頻道相關聯，則該記錄與子頻道相關聯。
* 促銷活動：依促銷活動篩選記錄。 如果記錄的任何接觸點與行銷活動相關聯，則該記錄會與行銷活動相關聯。
* 促銷活動來源：依促銷活動來源篩選記錄。 促銷活動來源範例包括Adwords、BingAds、Facebook、LinkedIn等。 如果記錄的任何接觸點與行銷活動來源相關聯，則該記錄會與行銷活動來源相關聯。
* CRM帳戶名稱：依CRM帳戶名稱篩選記錄。
* 區段篩選：依自訂區段篩選記錄。 如果記錄的任何接觸點與區段相關聯，則該記錄會與區段相關聯。

在所有篩選器中，都會使用「AND」邏輯。

>[!NOTE]
>
>如果記錄在選取的日期變更階段，則記錄將從起始階段到結束階段以及所有傳遞階段計數。

## 機會 {#opportunities}

![](assets/one-1.png)

階段包括OC，未結機會階段中選取的漏斗階段([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping])和成功的機會階段([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping])。

>[!NOTE]
>
>對於「已成功」階段，記錄計數僅適用於在選取的時間範圍內已轉換為階段的記錄。

您可以從每個長條圖向下展開，以檢視每個階段的Opportunity記錄。

## 潛在客戶/聯絡人 {#leads-contacts}

![](assets/two-1.png)

階段包括FT、LC、在設定上開啟潛在客戶/聯絡人階段的所選漏斗階段 — CRM — 階段對應，以及在設定上轉換潛在客戶/聯絡人階段 — CRM — 階段對應。

>[!NOTE]
>
>對於「已轉換」階段，記錄計數只適用於在選取的時間範圍內轉換至階段的記錄。

您可以從每個列向下展開，以檢視每個階段的Lead/Contact記錄。
