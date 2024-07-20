---
description: 支出管理方法 —  [!DNL Marketo Measure]
title: 支出管理方法
exl-id: 36478d8d-986c-4d4f-8854-3287d6c57a9d
feature: Spend Management
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 0%

---

# 支出管理方法 {#spend-management-methods}

支出資料是成功使用[!DNL Marketo Measure]進行ROI報告的關鍵。 若要針對所有管道和子管道製作準確且全面的ROI報表，您必須確定已將適當的支出資料提取至「[!DNL Marketo Measure]」。

有三種方式可將支出資料匯入[!DNL Marketo Measure]。 每種方法的設計都是為了從特定資料輸入中提取支出資料。

**1個API連線帳戶**

您透過API連線至[!DNL Marketo Measure]的任何廣告帳戶其支出會自動提取至[!DNL Marketo Measure]，以產生ROI報表。 若要檢查您已連線哪些帳戶，進而提取支出，請移至您的[!DNL Marketo Measure]應用程式，並選取「[!UICONTROL Integrations]」區段下的「[!UICONTROL Connections]」標籤。 如需有關設定API連線的詳細資訊，請檢閱[整合式廣告平台](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms)。

**2 CRM Campaign成本同步**

每個[!DNL Marketo Measure]帳戶都可以存取名為[同步CRM行銷活動成本](/help/marketing-spend/spend-management/crm-campaign-costs.md#availability)的功能。 依預設，此功能位元設為「否」，但可隨時開啟。

![](assets/spend-management-methods-1.png)

啟用後，此功能會自動從符合以下條件的任何CRM行銷活動/方案中提取費用：

i. [!DNL Marketo Measure]會先檢視行銷活動/方案是否正在建立接觸點，其來源是已建立的相符的[行銷活動同步規則](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)、或已建立的相符的[方案同步規則](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md)，或[啟用購買者接觸點值](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md#how-to-create-a-campaign-and-sync-buyer-touchpoints)是「包含所有行銷活動成員」或「包含『已回應』行銷活動成員」。

二、 行銷活動/方案必須填入開始日期

三、 必須在行銷活動/方案上填入結束日期

iv. 必須指定實際成本（適用於SFDC中的行銷活動）或期間成本(適用於Marketo中的方案)。

**3手動成本上傳**

此方法可讓您[手動上傳API連線帳戶或CRM Campaign成本同步處理未涵蓋之管道和子管道的支出資料](/help/marketing-spend/spend-management/marketing-channel-costs.md#uploading-marketing-costs)。 瀏覽至[!DNL Marketo Measure]設定中的「行銷支出」區段，即可透過任何管道的CSV檔案上傳支出資料。

客戶可使用這三種方法的組合，根據[!DNL Marketo Measure]的特定設定，管理其支出。 因為有三種方式可將支出匯入[!DNL Marketo Measure]，我們強烈建議您使用位於Discover的行銷支出展示板，以取得所有支出資料的完整檢視。 此展示板是唯一可讓您檢視所有管道及其相關支出的地方。 行銷支出委員會可幫助您快速找出支出資料中可能存在差距的位置，以及如何提高投資報酬率報告。
