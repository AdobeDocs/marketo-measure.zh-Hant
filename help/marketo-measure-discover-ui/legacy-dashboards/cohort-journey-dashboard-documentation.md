---
unique-page-id: 42762648
description: 同類群組歷程儀表板檔案 —  [!DNL Marketo Measure]
title: 同類群組歷程儀表板檔案
exl-id: b139f720-86ae-4f6d-9dfc-cc67b4186f88
feature: Reporting
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 0%

---

# 同類群組歷程儀表板檔案 {#cohort-journey-dashboard-documentation}

同類群組影響和漏斗儀表板可讓行銷人員檢視選定時間範圍內的開始同類群組階段的進度，並測量轉換率。

主要差異在於我們計算同類群組階段中每個實體的方式。

* 同類群組漏斗：每個階段的結果會直接衍生自上一個階段。

   * 只有在已設定的同類群組開始時間後，才會計入漏斗中經過每個階段的記錄。

![](assets/cohort-journey-dashboard-documentation-1.png)

* 同類群組影響：每個階段的結果會衍生自同類群組階段，而非前一個階段。

   * 每個階段中的所有記錄，只要它們發生在設定的同類群組開始時間之後，就會計算在內。 此儀表板自然會有比漏斗儀表板更多的記錄，因為我們檢視的是實體如何受到同類群組階段的影響，而不僅僅是漏斗中的移動。

![](assets/cohort-journey-dashboard-documentation-2.png)

每個儀表板有兩個圖磚：

* 同類群組收入： 「同類群組歷程」圖磚之「交易」階段中所有商機的機會總量。
* 同類群組歷程：從所選時間範圍的開始同類群組階段推進至每個歷程階段。

>[!NOTE]
>
>在所有Discover儀表板中，只能報告一個人員物件，即潛在客戶或聯絡人。 此設定於 [!UICONTROL Settings] > [!UICONTROL Reporting] > [!UICONTROL Attribution Settings] > [!UICONTROL Default Dashboard Object].

控制面板支援下列篩選器：

* 同類群組階段：選取開始同類群組階段。 以下所有階段的記錄都是從同類群組階段的記錄演變而來。
* 同類群組日期範圍：選取所選同類群組階段的時間範圍。 它與「同類群組階段」一起定義開始資料集。
* 截止日期：選取下列所有階段中必須發生記錄順行處理的日期。 預設為今天。 請注意，這適用於同類群組階段以外的所有階段。
* 管道：依管道篩選記錄。 如果某個管道具有關聯的接觸點，該管道就會與記錄相關聯。
* 子管道：依子管道篩選記錄。 如果記錄的任何接觸點與子頻道相關聯，則該記錄與子頻道相關聯。
* 促銷活動：依促銷活動篩選記錄。 如果記錄的任何接觸點與行銷活動相關聯，則該記錄會與行銷活動相關聯。
* 促銷活動來源：依促銷活動來源篩選記錄。 促銷活動來源範例為 [!DNL Adwords]， [!DNL BingAds]， [!DNL Facebook]， [!DNL LinkedIn]等 如果記錄的任何接觸點與行銷活動來源相關聯，則該記錄會與行銷活動來源相關聯。
* 區段篩選：依自訂區段篩選記錄。 如果記錄的任何接觸點與區段相關聯，則該記錄會與區段相關聯。

在所有篩選器中，都會使用「AND」邏輯。

>[!NOTE]
>
>區段篩選器僅適用於LC階段及之後。 如果「同類群組階段」為「未知」或「已知」，且其中一個區段篩選器有值，控制面板將不會傳回任何結果。

階段包括未知、已知、LC、開啟潛在客戶/聯絡人階段中選取的漏斗階段（設定> CRM >階段對應）、OC、開啟機會階段中選取的漏斗階段（設定> CRM >階段對應）和交易（已結束的成功機會）。

>[!NOTE]
>
>歷程階段的記錄計數（定義為同類群組階段以外的任何階段）包含與同類群組記錄相關的所有新記錄，這些記錄是在所選時間範圍的開始日期之後和截止日期之前建立的。 這是推斷的因果關係。

您可以從每個列向下展開，以檢視每個階段的記錄。

* 若為「未知」，它會顯示匿名訪客的詳細資料。
* 「已知」會顯示已知的訪客詳細資料。
* 對於LC和Open Lead/Contact階段，它會顯示Lead/Contact詳細資料。
* 對於OC、開放機會階段和交易，它會顯示機會詳細資訊。
