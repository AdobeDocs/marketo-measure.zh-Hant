---
description: API連線的最佳作法 —  [!DNL Marketo Measure]
title: API連線的最佳作法
exl-id: b8550e4e-a567-427f-b5d3-50232553a066
feature: APIs, Integration
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 0%

---

# API連線的最佳作法 {#best-practices-for-api-connections}

## 概觀 {#overview}

[!DNL Marketo Measure] 提供的API連線與 [!DNL Google AdWords]， [!DNL Microsoft Bing Ads]， [!DNL Facebook Ads]和LinkedIn。 這些API連線會啟用 [!DNL Marketo Measure] 從廣告平台提取各種資料，然後可以在購買者接觸點資料中回報。 這些API連線的一項重要功能是能夠自動提取支出資料，為您和您的團隊節省手動上傳資料以進行ROI報告所需的時間和精力。 設定這些API連線並非強制性 [!DNL Marketo Measure] 以追蹤這些管道，但它們的確可提供可增強報表的重要精細細節。

此 [!DNL Marketo Measure] API連線對您的帳戶是非常寶貴的方面，我們的最佳實務建議將幫助您和您的團隊最大程度地利用我們的連線。

## 最佳實務 {#best-practice}

無論您連線的廣告平台為何，請務必牢記以下准則！

* 使用管理員進行連線
* 您可以為一個平台連線多個廣告帳戶
* 連線所有可能的廣告帳戶，以儘可能自動化您的支出報表
* 如果可用，請一律實作追蹤範本。 此範本可確保即使廣告帳戶中斷連線， [!DNL Marketo Measure] 仍可提取精細的廣告詳細資料

最佳化每個 [!DNL Marketo Measure] API，請遵循以下最佳實務。

**[!DNL Facebook]**：使用自動標籤連線

在啟用自動標籤之前，請將廣告歷史記錄匯出至csv。 啟用自動標籤將會重設以下標籤之所有廣告的轉換歷史記錄和社交證明： [!DNL Marketo Measure].

依照我們的最佳實務建議， [!DNL Marketo Measure] [!DNL Facebook] API將能夠：

* 全部自動標籤 [!DNL Facebook] 具有必要內容的廣告 [!DNL Marketo Measure] 引數 `_bf ={creative}`
* 下載所有作用中的廣告成本資訊 [!DNL Facebook] 廣告

>[!NOTE]
>
>「 」沒有追蹤範本 [!DNL Facebook]，則API需仰賴自動標籤(_bf)引數來收集廣告詳細資料。

**AdWords**：在帳戶層級實作追蹤範本並啟用自動標籤

[!DNL Marketo Measure] 建議使用帳戶層級、行銷活動層級或廣告群組層級追蹤範本，因為它允許針對所有廣告新增及減除引數，而不會產生廣告歷史記錄中斷或刪除的風險。

依照我們的最佳實務建議， [!DNL Marketo Measure] AdWords API將能夠：

* 使用自動標籤所有AdWords廣告 [!DNL Marketo Measure] 引數 `_bk={keyword}, _bt={creative}, _bm={matchtype}, _bn={network}, _bg={adgroupID}`
* 下載所有作用中AdWords廣告的廣告成本資訊

**Bing**：在帳戶層級實作追蹤範本並啟用自動標籤

設定您的時，沒有遺失廣告歷史記錄的風險 [!DNL Bing] API連線，不同於我們其他幾個API連線。

依照我們的最佳實務建議， [!DNL Marketo Measure] Bing API將能夠：
* 使用下列引數自動標籤所有Bing Ads `_bt={adid}, utm_medium=cpc, utm_source=bing, utm_term={keyword}`
* 下載所有作用中Bing廣告的廣告成本資訊

**linkedIn**：使用自動標籤連線

啟用自動標籤功能會重新建立共用，並將其放置在新的創意中，舊創意會封存。

依照我們的最佳實務建議， [!DNL Marketo Measure] linkedIn API將能夠：

* 自動標籤屬於廣告型別「贊助內容」的所有LinkedIn廣告，如有必要 [!DNL Marketo Measure] 引數_bl={creativeId}. 此引數提取創作ID，允許 [!DNL Marketo Measure] 以解決行銷活動和創意資訊。
* 下載所有使用中及支援的廣告成本資訊 [!DNL LinkedIn] 廣告

>[!NOTE]
>
>「 」沒有追蹤範本 [!DNL LinkedIn]，此API仰賴自動標籤(_bl)引數來收集所有可能的廣告詳細資料。

## 維護最佳實務 {#best-practice-for-maintenance}

雖然遵循我們的最佳實務可防止您因中斷連線而遺失資料，但我們仍建議您定期檢查連線，如有可能，請每月檢查。 這是對的簡單視覺檢查 [!UICONTROL Connections] 區段 [!DNL Marketo Measure] 應用程式以確定沒有出現紅色按鍵圖示，表示帳戶已中斷連線。

當API連線的帳戶中斷連線時， [!DNL Marketo Measure] 無法提取支出資料或標籤新廣告。 這就是為什麼我們總是建議儘可能實作追蹤範本的原因。 此範本可確保即使廣告帳戶中斷連線， [!DNL Marketo Measure] 仍可標籤廣告並提取精細的廣告細節。 重新連線後，支出資料將會回填，而您的付費管道報表的中斷將會降至最低。

中斷連線及重新授權的原因包括……

* 變更已連線之個人帳戶的密碼
* 此人已不在公司
* API的更新

如果您的團隊經歷過上述任何情況，請在「 」中檢視您的API連線 [!DNL Marketo Measure] 應用程式以確定他們不需要重新授權。

>[!MORELIKETHIS]
>
>* [整合式廣告平台(API)](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md)
>* [競標管理工具如何影響 [!DNL Marketo Measure]](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md)
>* [[!DNL Marketo Measure] 說明API引數](/help/api-connections/utilizing-marketo-measures-api-connections/marketo-measure-parameters.md)
>* [facebook API概觀](/help/api-connections/utilizing-marketo-measures-api-connections/facebook-api.md)
>* [[!DNL LinkedIn] 整合概述](/help/api-connections/utilizing-marketo-measures-api-connections/linkedin-integration.md)
>* [AdWords整合概述](/help/api-connections/utilizing-marketo-measures-api-connections/understanding-marketo-measure-adwords-tagging.md)
>* [重新授權連線API帳戶](/help/api-connections/utilizing-marketo-measures-api-connections/reauthorizing-connected-accounts.md)
