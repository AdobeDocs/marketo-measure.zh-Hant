---
unique-page-id: 18874554
description: 接觸點產生與對應 —  [!DNL Marketo Measure]
title: 接觸點產生與對應
exl-id: bb4988f5-4fbc-43b7-9544-da541b8e1d32
feature: Touchpoints
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 0%

---

# 接觸點產生與對應 {#touchpoint-generation-and-mapping}

[!DNL Marketo Measure]歸因故事取決於兩個程式：

* 產生接觸點，這會建立代表個人與行銷和銷售工作互動的接觸點
* 接觸點對應，將接觸點歸因到適當的管道和子管道

若要充分利用[!DNL Marketo Measure]，您應該與您的[!DNL Marketo Measure]代表合作，以自訂兩個程式來滿足您組織的需求。

接觸點產生方法

接觸點產生程式會回答以下問題：「如何讓[!DNL Marketo Measure]知道這已發生？」 根據您的功能集和潛在客戶可進行的互動型別，[!DNL Marketo Measure]最多有三種方式可選取互動並建立代表該互動的接觸點。

>[!IMPORTANT]
>
>[!DNL Marketo Measure]在每個工作階段僅產生一個接觸點。 如果填寫了多個表單，則只會擷取第一個表單填寫。

| **互動型別** | **範例** | **接觸點產生方法** |
|---|---|---|
| 線上，在您的網站上 | 表單填寫 | [!DNL Marketo Measure] JavaScript |
| 離線；不在您的網站上線上 | 商展；內容整合合作夥伴會提供參與您內容的潛在客戶清單 | CRM Campaign會籍已同步至[!DNL Marketo Measure]，方法是直接在行銷活動中設定Campaign同步型別，或在[!DNL Marketo Measure]的「行銷活動」頁面上設定規則 |
| 銷售活動 | 依SDR的傳出呼叫 | CRM活動（工作或事件）記錄已透過[!DNL Marketo Measure]中[!UICONTROL Activities]頁面上的邏輯同步至[!DNL Marketo Measure] |

接觸點對應方法

接觸點對應程式回答以下問題：「一旦建立此接觸點，[!DNL Marketo Measure]如何知道其屬於哪個管道和子管道？」 每個產生接觸點的方法都有各自的接觸點對應方法。

| **互動型別** | **產生方法** | **對應方法** |
|---|---|---|
| 線上，在您的網站上 | [!DNL Marketo Measure] JavaScript | 透過[!DNL Marketo Measure]中的[!DNL Online Channels]頁面，參考UTM值、登陸頁面和引用頁面資訊 |
| 離線；線上，不在您的網站上 | CRM Campaign成員資格同步 | 透過[!DNL Marketo Measure]中的[!UICONTROL Offline Channels]頁面，透過參考促銷活動型別 |
| 銷售活動 | CRM活動同步 | 透過[!DNL Marketo Measure]中的[!UICONTROL Online Channels]頁面，參考[!UICONTROL Activities]頁面上指派的行銷活動名稱 |

>[!MORELIKETHIS]
>
>* [將線上接觸點對應至 [!DNL Marketo Measure] 管道/子管道](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [正在從SFDC](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md)內同步CRM行銷活動
>* [正在從 [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)內同步CRM行銷活動
>* [將CRM行銷活動對應至 [!DNL Marketo Measure] 管道/子管道](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [從銷售活動建立接觸點](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [活動常見問題集以及將活動接觸點對應到管道/子管道](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)

