---
description: 支出管理方法 —  [!DNL Marketo Measure]  — 產品檔案
title: 支出管理方法
exl-id: 36478d8d-986c-4d4f-8854-3287d6c57a9d
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 0%

---

# 支出管理方法 {#spend-management-methods}

使用支出資料是成功實現ROI報告的關鍵 [!DNL Marketo Measure]. 為了在所有管道和子管道中獲得準確且全面的ROI報告，您需要確保將適當的支出資料提取到 [!DNL Marketo Measure].

有三種方式可將支出資料帶入 [!DNL Marketo Measure]. 每種方法都設計為從特定資料輸入中提取支出資料。

**1)API連接帳戶**

您已連線的任何廣告帳戶 [!DNL Marketo Measure] 透過API，會自動將其支出提取至 [!DNL Marketo Measure] 用於ROI報告。 要檢查哪些帳戶已連接並因此吸引支出，請轉到 [!DNL Marketo Measure] 應用程式並選取 [!UICONTROL Connections] 標籤 [!UICONTROL Integrations] 區段。 如需如何設定API連線的詳細資訊，請檢閱我們的 [整合廣告平台](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms) 文章。

**2)CRM促銷活動成本同步**

每個 [!DNL Marketo Measure] 帳戶可存取 [同步CRM促銷活動成本](/help/marketing-spend/spend-management/crm-campaign-costs.md#availability). 此功能位預設會設為「否」，但可隨時開啟。

![](assets/spend-management-methods-1.png)

啟用後，此功能會自動從符合下列條件的任何CRM促銷活動/方案提取支出

我。 [!DNL Marketo Measure] 首先會查看促銷活動/方案是否正在建立接觸點，或是從相符的 [促銷活動同步規則](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md) 已建立，或相符 [程式同步規則](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md) 建立的，或 [啟用購買者接觸點值](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md#how-to-create-a-campaign-and-sync-buyer-touchpoints) 是「包含所有促銷活動成員」或「包含&#39;已回應&#39;促銷活動成員」。

ii. 必須在促銷活動/方案上填入「開始日期」

三。 也必須在促銷活動/方案上填入結束日期

四。 最後，必須指定「實際成本」（適用於SFDC中的促銷活動）或「期間成本」(適用於Marketo中的計畫)。

**3)手動成本上傳**

此方法可讓您 [手動上傳支出資料](/help/marketing-spend/spend-management/marketing-channel-costs.md#uploading-marketing-costs) API連線帳戶或CRM促銷活動成本同步未涵蓋的管道和子管道。 導覽至 [!DNL Marketo Measure] 設定時，您可以透過任何管道的CSV檔案上傳支出資料。

客戶可使用這三種方法的組合來管理其支出，且取決於 [!DNL Marketo Measure]. 因為有三種方法可將支出匯入 [!DNL Marketo Measure]，強烈建議您利用位於Discover的行銷支出展示板，以取得所有支出資料的完整檢視。 此展示板是您唯一能夠查看所有管道及其相關支出的地方。 「行銷支出」展示板可協助您快速找出支出資料中可能存在的差距，以及如何改善ROI報表。
