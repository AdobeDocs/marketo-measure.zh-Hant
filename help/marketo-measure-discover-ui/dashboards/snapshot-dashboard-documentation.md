---
unique-page-id: 42762600
description: 快照儀表板文檔 —  [!DNL Marketo Measure]  — 產品檔案
title: 快照儀表板文檔
exl-id: 4dfc92d2-ccab-4726-a869-3ae32aa89a5f
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---

# 快照儀表板文檔 {#snapshot-dashboard-documentation}

快照儀表板使您能夠查看CRM在任何給定時間點的狀態，並跨銷售機會/聯繫人和銷售機會階段分配記錄。

此控制面板有兩個圖磚：

* **銷售機會/聯繫人快照：** 在所選日期的每個階段中的銷售機會或聯繫人記錄數。

>[!NOTE]
>
>在所有Discover控制面板中，只能報告一個人員物件，即銷售機會或聯絡人。 此設定於 [!UICONTROL Settings] > [!UICONTROL Reporting] > [!UICONTROL Attribution Settings] > [!UICONTROL Default Dashboard Object].

* **機會快照：** 在所選日期的每個階段中的Opportunity記錄數。

此控制面板支援下列篩選器（所有篩選器都會套用至兩個圖磚）:

* 快照日期：選擇快照日期。
* CRM帳戶ID/名稱：按CRM帳戶ID或名稱篩選記錄。

>[!NOTE]
>
>建議僅顯示名稱。

* 管道：依管道篩選記錄。 如果其任何接觸點都與管道相關聯，則記錄會與管道相關聯。
* 子頻道：依子通道篩選記錄。 如果記錄的任何接觸點都與子管道相關聯，則記錄會與子管道相關聯。
* 促銷活動：依促銷活動篩選記錄。 如果促銷活動的任何接觸點都與促銷活動相關聯，則記錄會與促銷活動相關聯。
* 促銷活動來源：依促銷活動來源篩選記錄。 促銷活動來源範例為 [!DNL Adwords], [!DNL BingAds], [!DNL Facebook], [!DNL LinkedIn]、等 如果任何接觸點與促銷活動來源相關聯，則記錄會與促銷活動來源相關聯。
* 廣告帳戶ID/名稱：依「廣告帳戶ID」或「名稱」篩選記錄。 如果記錄的任何接觸點都與來自所選廣告帳戶的促銷活動相關聯，則記錄會與廣告帳戶相關聯。

>[!NOTE]
>
>建議僅顯示名稱。

* 群體篩選：依自訂區段篩選記錄。 如果任何接觸點都與區段相關聯，則記錄會與區段相關聯。

對所有篩選器都使用「AND」邏輯。

>[!NOTE]
>
>如果記錄在所選日期發生變更階段，則記錄將被計為從階段和到階段，以及所有傳遞階段。

## 銷售機會/聯繫人快照 {#lead-contact-snapshot}

![](assets/one.png)

階段包括FT、LC和在開啟的引導/接觸階段([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping])。

您可以從每個條向下鑽取以查看每個階段的銷售機會/聯繫人記錄。

## 機會快照 {#opportunity-snapshot}

![](assets/two.png)

階段包括FT、LC、開啟的引導/接觸階段中選定的漏斗階段([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping])。 在Open Opportunity階段([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping])。

您可以從每個欄深入查看每個階段的Opportunity記錄。
