---
unique-page-id: 18874684
description: Campaign同步日期 —  [!DNL Marketo Measure]
title: Campaign同步日期
exl-id: 66ce9948-9297-47ef-8b16-0ac45c5664fc
feature: Channels
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 0%

---

# Campaign同步日期 {#campaign-sync-dates}

瞭解Campaign同步日期功能的功能，並提供此功能的一些使用案例。

>[!NOTE]
>
>本文會介紹過時的程式。 我們鼓勵使用者使用 [新的、改良的應用程式內程式](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"}.

**[!DNL Marketo Measure]需要套件： 6.9或更新版本**

此功能包含兩個位於 [!DNL Salesforce] 促銷活動物件：

* 接觸點開始日期
* 接觸點結束日期

在特定行銷活動上啟用購買者接觸點後，Campaign同步日期將允許您在個別行銷活動上設定接觸點日期引數。 因此，如果您要新增接觸點結束日期2017年3月1日，則 [!DNL Marketo Measure] 僅會在該日期之前新增至行銷活動的行銷活動成員上建立接觸點。 [!DNL Marketo Measure] 將不會針對2017年3月1日之後新增的行銷活動成員建立接觸點。

![](assets/1.gif)

同樣地，如果您要在行銷活動上新增接觸點開始日期（假設2017年1月1日），則 [!DNL Marketo Measure] 不會在2017年1月1日之前新增至Campaign的Campaign成員上建立接觸點。 如果您新增接觸點結束日期，則不需要新增接觸點開始日期，反之亦然。

## 使用案例 {#use-cases}

**回填接觸點**

行銷團隊有時可能會遺漏將utm引數新增到特定行銷工作。 行銷活動同步日期可讓您（如果您使用SFDC行銷活動進行線上工作）回填一些遺漏的資料。 假設您正在執行從5月1日開始的電子郵件促銷活動，但您的團隊直到5月15日才在該電子郵件促銷活動上新增utm引數。 如果您透過SFDC促銷活動追蹤電子郵件轉換，您可以將接觸點結束日期設為5月15日（該促銷活動）並啟用促銷活動「已回應」成員的接觸點。 此動作將告知 [!DNL Marketo Measure] 為截至5月15日的所有這些回應建立接觸點。

**回溯性Campaign會籍接觸點**

如果您是新手 [!DNL Marketo Measure] 客戶，您可能有興趣透過SFDC Campaigns帶回部分您一直在追蹤的行銷資料。 不過，如果您要啟用線上SFDC行銷活動的接觸點，則可能會遇到重複計算歸因的問題，因為 [!DNL Marketo Measure] 會自動建立用於線上行銷工作的接觸點。 為避免重複計算資料，您可以使用Campaign接觸點結束日期，對建立的接觸點日期設定限制 [!DNL Marketo Measure] SFDC促銷活動上的資訊。 例如，如果您想要為一直在SFDC中追蹤的Social促銷活動新增追溯轉換，但您瞭解您已新增 [!DNL Marketo Measure] 7月1日的JavaScript （會建立線上接觸點）則可編輯Social SFDC促銷活動，使其包含等於7月1日的接觸點結束日期，並啟用該促銷活動的購買者接觸點。

接觸點結束日期可能有許多其他使用案例。 如果您需要協助瞭解特定情況，請隨時與 [Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] 大學：促銷活動和促銷活動成員欄位](https://learn.bizible.com/2-bizible-customization/137720https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63007334d9f0367662b758)
