---
unique-page-id: 18874684
description: 促銷活動同步日期 —  [!DNL Marketo Measure]  — 產品檔案
title: 促銷活動同步日期
exl-id: 66ce9948-9297-47ef-8b16-0ac45c5664fc
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 0%

---

# 促銷活動同步日期 {#campaign-sync-dates}

了解「促銷活動同步日期」功能有何功能，並針對此功能提供一些使用案例。

**[!DNL Marketo Measure]需要包：6.9或更高版本**

此功能包含 [!DNL Salesforce] 促銷活動物件：

* 接觸點開始日期
* 接觸點結束日期

在特定促銷活動上啟用購買者接觸點後，促銷活動同步日期可讓您在個別促銷活動上設定接觸點日期參數。 因此，如果您要新增接觸點結束日期（2017年3月1日） [!DNL Marketo Measure] 只會在該日期前新增至促銷活動之促銷活動成員上建立接觸點。 [!DNL Marketo Measure] 不會為2017年3月1日之後新增的促銷活動成員建立接觸點。

![](assets/1.gif)

同樣地，如果您要在促銷活動上新增接觸點開始日期（例如2017年1月1日），則 [!DNL Marketo Measure] 不會在2017年1月1日之前新增至促銷活動的促銷活動成員上建立接觸點。 如果您新增接觸點結束日期，則不需要新增接觸點開始日期，反之亦然。

## 使用案例 {#use-cases}

**回填接觸點**

有時候，行銷團隊可能會遺漏將utm參數新增至特定行銷工作。 促銷活動同步日期可讓您（如果您使用SFDC促銷活動進行線上工作）回填部分遺漏的資料。 假設您正在執行從5月1日開始的電子郵件促銷活動，但您的團隊直到5月15日才在該電子郵件促銷活動上新增utm參數。 如果您要透過SFDC促銷活動追蹤電子郵件轉換，則可以在該促銷活動上設定5月15日的接觸點結束日期，並為促銷活動的「已回應」成員啟用接觸點。 此動作將說明 [!DNL Marketo Measure] 直到5月15日為止，為所有回應建立接觸點。

**追溯促銷活動成員資格接觸點**

如果你是新來的 [!DNL Marketo Measure] 客戶，您可能有興趣將您通過SFDC促銷活動追蹤的一些行銷資料帶入。 不過，如果您要為線上SFDC促銷活動啟用接觸點，則可能會遇到重複計算歸因的問題，因為 [!DNL Marketo Measure] 自動建立線上行銷工作的接觸點。 為避免重複計算資料，您可以使用「促銷活動接觸點結束日期」來設定所建立之接觸點日期的限制 [!DNL Marketo Measure] 在SFDC促銷活動上。 例如，如果您想要為已在SFDC中追蹤的Social促銷活動新增追溯轉換，但您了解您已新增 [!DNL Marketo Measure] JavaScript（即於7月1日建立線上接觸點），然後您可以編輯Social SFDC促銷活動，將接觸點結束日期等於7月1日，並啟用該促銷活動的購買者接觸點。

接觸點結束日期可能有許多其他使用案例。 如果你需要幫助，找出具體情況，請立即聯繫 [Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] 大學：促銷活動和促銷活動成員欄位](https://learn.bizible.com/2-bizible-customization/137720https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63007334d9f0367662b758)
