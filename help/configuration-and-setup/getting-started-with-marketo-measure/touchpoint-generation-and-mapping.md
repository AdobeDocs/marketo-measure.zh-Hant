---
unique-page-id: 18874554
description: 接觸點產生與對應 —  [!DNL Marketo Measure]  — 產品檔案
title: 接觸點產生與對應
exl-id: bb4988f5-4fbc-43b7-9544-da541b8e1d32
source-git-commit: 950dbfacf48cbb81acad9c40033c25a765287bee
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 接觸點產生與對應 {#touchpoint-generation-and-mapping}

[!DNL Marketo Measure] 歸因故事取決於兩個程式：

* 接觸點產生，可建立接觸點，以代表人員與您的行銷和銷售工作的互動
* 接觸點對應，將接觸點評分至適當的管道和子管道

為了讓你 [!DNL Marketo Measure]您應該 [!DNL Marketo Measure] 代表根據您的組織需要定制兩個流程。

接觸點產生方法

接觸點產生程式可回答「如何 [!DNL Marketo Measure] 會知道發生了什麼？」 根據您的功能集和潛在客戶的互動類型，最多有三種方式 [!DNL Marketo Measure] 可擷取互動並建立接觸點來加以呈現。

>[!IMPORTANT]
>
>[!DNL Marketo Measure] 每個工作階段只會產生一個接觸點。 如果已填寫多個表單，則只會擷取第一個表單填入。

| **互動類型** | **範例** | **接觸點產生方法** |
|---|---|---|
| 線上，在您的網站上 | 表單填寫 | [!DNL Marketo Measure] JavaScript |
| 離線；不在您的網站上線上 | 展會；內容整合合作夥伴提供與您的內容接洽的銷售機會清單 | 同步至的CRM促銷活動成員資格 [!DNL Marketo Measure]，方法是直接在促銷活動中設定促銷活動同步類型，或在 [!DNL Marketo Measure] |
| 銷售活動 | 按SDR的出站呼叫 | 同步至的CRM活動（任務或事件）記錄 [!DNL Marketo Measure]，透過邏輯 [!UICONTROL Activities] 頁面 [!DNL Marketo Measure] |

接觸點對應方法

接觸點對應程式可回答以下問題：「建立此接觸點後，如何 [!DNL Marketo Measure] 了解它屬於哪個管道和子管道？」 每個接觸點生成方法都有各自的接觸點映射方法。

| **互動類型** | **產生方法** | **映射方法** |
|---|---|---|
| 線上，在您的網站上 | [!DNL Marketo Measure] JavaScript | 透過 [!DNL Online Channels] 頁面 [!DNL Marketo Measure]，方法是參考UTM值、登陸頁面和反向連結頁面資訊 |
| 離線；線上，不在您的網站上 | CRM促銷活動成員資格同步 | 透過 [!UICONTROL Offline Channels] 頁面 [!DNL Marketo Measure]，方法是參考促銷活動類型 |
| 銷售活動 | CRM活動同步 | 透過 [!UICONTROL Online Channels] 頁面 [!DNL Marketo Measure]，方法是參考 [!UICONTROL Activities] 頁面 |

>[!MORELIKETHIS]
>
>* [將線上接觸點對應至 [!DNL Marketo Measure] 通道/子通道](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [從SFDC同步CRM促銷活動](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md)
>* [從內同步CRM促銷活動 [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [將CRM促銷活動對應至 [!DNL Marketo Measure] 通道/子通道](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [從銷售活動建立接觸點](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [活動常見問題集和將活動接觸點對應至管道/子管道](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)


