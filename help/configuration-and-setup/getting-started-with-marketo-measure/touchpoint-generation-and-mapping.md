---
unique-page-id: 18874554
description: 接觸點產生與對應 —  [!DNL Marketo Measure]  — 產品檔案
title: 接觸點產生與對應
exl-id: bb4988f5-4fbc-43b7-9544-da541b8e1d32
feature: Touchpoints
source-git-commit: b8ea008c594ed114323dedd3762d1265287193c7
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 0%

---

# 接觸點產生與對應 {#touchpoint-generation-and-mapping}

[!DNL Marketo Measure] 歸因故事取決於兩個程式：

* 產生接觸點，這會建立代表個人與行銷和銷售工作互動的接觸點
* 接觸點對應，將接觸點歸因到適當的管道和子管道

為了讓您充分利用 [!DNL Marketo Measure]，您應該使用 [!DNL Marketo Measure] 代表可自訂兩個程式以符合您組織的需求。

接觸點產生方法

接觸點產生程式會回答以下問題：「如何 [!DNL Marketo Measure] 要知道這件事發生了嗎？」 根據您的功能集和潛在客戶可以進行的互動型別，最多有三個方法 [!DNL Marketo Measure] 可以察覺互動並建立代表它的接觸點。

>[!IMPORTANT]
>
>[!DNL Marketo Measure] 每個工作階段只會產生一個接觸點。 如果填寫了多個表單，則只會擷取第一個表單填寫。

| **互動型別** | **範例** | **接觸點產生方法** |
|---|---|---|
| 線上，在您的網站上 | 表單填寫 | [!DNL Marketo Measure] JavaScript |
| 離線；不在您的網站上線上 | 商展；內容整合合作夥伴會提供參與您內容的潛在客戶清單 | CRM Campaign會籍已同步至 [!DNL Marketo Measure]，方法是直接在行銷活動中設定「行銷活動同步型別」 ，或在的「行銷活動」頁面上設定規則 [!DNL Marketo Measure] |
| 銷售活動 | 依SDR的傳出呼叫 | CRM活動（任務或事件）記錄已同步至 [!DNL Marketo Measure]，透過上的邏輯 [!UICONTROL Activities] 頁面位置 [!DNL Marketo Measure] |

接觸點對應方法

接觸點對應程式會回答以下問題：「一旦建立了此接觸點，如何 [!DNL Marketo Measure] 知道它屬於哪個頻道和子頻道嗎？」 每個產生接觸點的方法都有各自的接觸點對應方法。

| **互動型別** | **產生方法** | **對應方法** |
|---|---|---|
| 線上，在您的網站上 | [!DNL Marketo Measure] JavaScript | 透過 [!DNL Online Channels] 頁面位置 [!DNL Marketo Measure]，藉由參考UTM值、登陸頁面和引用頁面資訊 |
| 離線；線上，不在您的網站上 | CRM Campaign成員資格同步 | 透過 [!UICONTROL Offline Channels] 頁面位置 [!DNL Marketo Measure]，透過參考促銷活動型別 |
| 銷售活動 | CRM活動同步 | 透過 [!UICONTROL Online Channels] 頁面位置 [!DNL Marketo Measure]，方式為參考上指派的行銷活動名稱 [!UICONTROL Activities] 頁面 |

>[!MORELIKETHIS]
>
>* [將線上接觸點對應至 [!DNL Marketo Measure] 管道/子管道](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [從SFDC內同步CRM行銷活動](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md)
>* [正在從內部同步CRM行銷活動 [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [將CRM行銷活動對應至 [!DNL Marketo Measure] 管道/子管道](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [從銷售活動建立接觸點](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [活動常見問題集並將活動接觸點對應至管道/子管道](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)

