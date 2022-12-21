---
unique-page-id: 42762628
description: 護照儀表板文檔 —  [!DNL Marketo Measure]  — 產品檔案
title: 護照儀表板文檔
exl-id: 43cb01a8-d02e-4086-af57-d7ec9275f87a
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 0%

---

# 護照儀表板文檔 {#passport-dashboard-documentation}

Passport儀表板使行銷人員能夠查看在指定時間範圍內通過每個管道階段的銷售機會/聯繫人和銷售機會。

此控制面板有兩個圖磚：

* 機會：在指定時間範圍內通過每個階段的Opportunity記錄數。
* 銷售機會/聯繫人：在指定時間範圍內通過每個階段的銷售機會或聯繫人記錄數。

>[!NOTE]
>
>在所有Discover控制面板中，只能報告一個人員物件，即銷售機會或聯絡人。 此設定於 [!UICONTROL Settings] > [!UICONTROL Reporting] > [!UICONTROL Attribution Settings] > [!UICONTROL Default Dashboard Object].

此控制面板支援下列篩選器（所有篩選器都會套用至兩個圖磚）:

* 日期：選取時間範圍。
* 管道：依管道篩選記錄。 如果其任何接觸點都與管道相關聯，則記錄會與管道相關聯。
* 子頻道：依子通道篩選記錄。 如果記錄的任何接觸點都與子管道相關聯，則記錄會與子管道相關聯。
* 促銷活動：依促銷活動篩選記錄。 如果促銷活動的任何接觸點都與促銷活動相關聯，則記錄會與促銷活動相關聯。
* 促銷活動來源：依促銷活動來源篩選記錄。 範例促銷活動來源包括Adwords、BingAds、Facebook、LinkedIn等。 如果任何接觸點與促銷活動來源相關聯，則記錄會與促銷活動來源相關聯。
* CRM帳戶名稱：按CRM帳戶名稱篩選記錄。
* 群體篩選：依自訂區段篩選記錄。 如果任何接觸點都與區段相關聯，則記錄會與區段相關聯。

對所有篩選器都使用「AND」邏輯。

>[!NOTE]
>
>如果記錄在所選日期發生變更階段，則記錄將被計為從階段和到階段，以及所有傳遞階段。

## 機會 {#opportunities}

![](assets/one-1.png)

階段包括OC、Open Opportunity階段中選定的漏斗階段([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping])和贏得機會階段([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping])。

>[!NOTE]
>
>對於Won階段，記錄計數只適用於在所選時間範圍內轉換為階段的記錄。

您可以從每個欄深入查看每個階段的Opportunity記錄。

## 銷售機會/聯繫人 {#leads-contacts}

![](assets/two-1.png)

階段包括FT、LC、在「設定」的「開啟銷售機會/聯繫人」階段中選定的漏斗階段 — CRM — 階段映射，以及在「設定」的「轉換銷售機會/聯繫人」階段 — CRM — 階段映射。

>[!NOTE]
>
>對於「已轉換」階段，記錄計數只適用於在所選時間範圍內轉換為階段的記錄。

您可以從每個條向下鑽取以查看每個階段的銷售機會/聯繫人記錄。
