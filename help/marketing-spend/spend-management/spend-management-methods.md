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

支出資料是投資報酬率報告成功的關鍵 [!DNL Marketo Measure]. 若要針對所有管道和子管道製作準確且全面的ROI報表，您必須確定您有適當的支出資料可提取至其中 [!DNL Marketo Measure].

有三種方式可將支出資料匯入 [!DNL Marketo Measure]. 每種方法的設計都是為了從特定資料輸入中提取支出資料。

**1個API連線帳戶**

您已連線的任何廣告帳戶 [!DNL Marketo Measure] 透過API，其支出會自動提取到 [!DNL Marketo Measure] ROI報表。 若要檢查您已連線哪些帳戶，進而提取支出，請前往您的 [!DNL Marketo Measure] 應用程式並選取 [!UICONTROL Connections] 標籤下的 [!UICONTROL Integrations] 區段。 如需有關設定API連線的詳細資訊，請檢閱 [整合式廣告平台](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms).

**2 CRM Campaign成本同步**

每 [!DNL Marketo Measure] 帳戶可存取名為的功能 [同步CRM Campaign成本](/help/marketing-spend/spend-management/crm-campaign-costs.md#availability). 依預設，此功能位元設為「否」，但可隨時開啟。

![](assets/spend-management-methods-1.png)

啟用後，此功能會自動從符合以下條件的任何CRM行銷活動/方案中提取費用：

i. [!DNL Marketo Measure] 首先檢視行銷活動/方案是否正在建立接觸點（從相符專案） [Campaign同步規則](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md) 已建立的，或相符的 [程式同步規則](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md) 已建立的，或 [啟用購買者接觸點值](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md#how-to-create-a-campaign-and-sync-buyer-touchpoints) 是「包含所有行銷活動成員」或「包含「已回應」行銷活動成員。」

二、 行銷活動/方案必須填入開始日期

三、 必須在行銷活動/方案上填入結束日期

iv. 必須指定實際成本（適用於SFDC中的行銷活動）或期間成本(適用於Marketo中的方案)。

**3手動成本上傳**

此方法可讓您 [手動上傳支出資料](/help/marketing-spend/spend-management/marketing-channel-costs.md#uploading-marketing-costs) API連線帳戶或CRM Campaign Cost Sync未涵蓋的管道和子管道。 導覽至「 」中的「行銷支出」區段 [!DNL Marketo Measure] 設定，您可以透過任何管道的CSV檔案上傳支出資料。

客戶可使用這三種方法的組合，根據的具體設定，管理其支出 [!DNL Marketo Measure]. 因為有三種方式可將支出匯入 [!DNL Marketo Measure]，我們強烈建議您使用位於Discover中的行銷支出展示板，以全面檢視所有支出資料。 此展示板是唯一可讓您檢視所有管道及其相關支出的地方。 行銷支出委員會可幫助您快速找出支出資料中可能存在差距的位置，以及如何提高投資報酬率報告。
