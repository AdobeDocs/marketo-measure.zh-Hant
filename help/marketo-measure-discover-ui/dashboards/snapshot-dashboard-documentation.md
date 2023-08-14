---
unique-page-id: 42762600
description: 快照儀表板檔案 —  [!DNL Marketo Measure]  — 產品檔案
title: 快照儀表板檔案
exl-id: 4dfc92d2-ccab-4726-a869-3ae32aa89a5f
feature: Reporting
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---

# 快照儀表板檔案 {#snapshot-dashboard-documentation}

快照儀表板可讓您檢視在任何指定時間點的CRM狀態，以及銷售機會/聯絡人和銷售機會階段之間的記錄分佈。

此儀表板有兩個圖磚：

* **銷售機會/聯絡人快照：** 所選日期每個階段中的潛在客戶或聯絡人記錄數。

>[!NOTE]
>
>在所有Discover儀表板中，只能報告一個人員物件，即潛在客戶或聯絡人。 此設定於 [!UICONTROL Settings] > [!UICONTROL Reporting] > [!UICONTROL Attribution Settings] > [!UICONTROL Default Dashboard Object].

* **機會快照：** 所選日期每個階段中的Opportunity記錄數。

此控制面板支援下列篩選器（所有篩選器皆適用於兩個圖磚）：

* 快照日期：選取快照日期。
* CRM帳戶ID/名稱：依CRM帳戶ID或名稱篩選記錄。

>[!NOTE]
>
>建議只會顯示名稱。

* 管道：依管道篩選記錄。 如果某個管道具有關聯的接觸點，該管道就會與記錄相關聯。
* 子管道：依子管道篩選記錄。 如果記錄的任何接觸點與子頻道相關聯，則該記錄與子頻道相關聯。
* 促銷活動：依促銷活動篩選記錄。 如果記錄的任何接觸點與行銷活動相關聯，則該記錄會與行銷活動相關聯。
* 促銷活動來源：依促銷活動來源篩選記錄。 促銷活動來源範例為 [!DNL Adwords]， [!DNL BingAds]， [!DNL Facebook]， [!DNL LinkedIn]等 如果記錄的任何接觸點與行銷活動來源相關聯，則該記錄會與行銷活動來源相關聯。
* 廣告帳戶ID/名稱：依廣告帳戶ID或名稱篩選記錄。 如果記錄的任何接觸點與來自所選廣告帳戶的促銷活動相關聯，則該記錄會與廣告帳戶相關聯。

>[!NOTE]
>
>建議僅顯示名稱。

* 區段篩選：依自訂區段篩選記錄。 如果記錄的任何接觸點與區段相關聯，則該記錄會與區段相關聯。

在所有篩選器中，都會使用「AND」邏輯。

>[!NOTE]
>
>如果記錄在選取的日期變更階段，則記錄將從起始階段到結束階段以及所有傳遞階段計數。

## 銷售機會/聯絡人快照 {#lead-contact-snapshot}

![](assets/one.png)

階段包括FT、LC和選取的「漏斗」階段（在「未結銷售機會/接觸」階段） ([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping])。

您可以從每個列向下展開，以檢視每個階段的Lead/Contact記錄。

## 機會快照 {#opportunity-snapshot}

![](assets/two.png)

階段包括FT、LC、開啟銷售機會/聯絡人階段中選取的漏斗階段([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping])。 以及Open Opportunity階段中的OC和選取的漏斗階段([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping])。

您可以從每個長條圖向下展開，以檢視每個階段的Opportunity記錄。
