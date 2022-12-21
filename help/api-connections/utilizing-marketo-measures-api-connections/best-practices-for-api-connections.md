---
description: API連線最佳實務 —  [!DNL Marketo Measure]  — 產品檔案
title: API連線最佳實務
exl-id: b8550e4e-a567-427f-b5d3-50232553a066
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 0%

---

# API連線最佳實務 {#best-practices-for-api-connections}

## 總覽 {#overview}

[!DNL Marketo Measure] 提供API連線，與 [!DNL Google AdWords], [!DNL Microsoft Bing Ads], [!DNL Facebook Ads]和LinkedIn。 這些API連線可啟用 [!DNL Marketo Measure] 從您的廣告平台提取各種資料，然後可在您的購買者接觸點資料中報告。 這些API連線的一個關鍵功能是能夠自動提取支出資料，從而為您和您的團隊節省手動上傳資料以實現ROI報告的時間和精力。 設定這些API連線並非 [!DNL Marketo Measure] 來追蹤這些管道，但這些管道確實提供可增強您報表的寶貴精細詳細資料。

此 [!DNL Marketo Measure] API連線是您帳戶中非常寶貴的一環，而我們的最佳實務建議將可協助您和您的團隊充分利用我們的連線。

## 最佳實務 {#best-practice}

無論您連線的廣告平台為何，請謹記下列重要准則！

* 使用管理員連線
* 您可以為一個平台連接多個廣告帳戶
* 連接所有可能的廣告帳戶，盡可能自動化您的支出報告
* 如果有，請一律實作追蹤範本。 範本可確保即使廣告帳戶中斷連線， [!DNL Marketo Measure] 仍可提取精細的廣告詳細資訊

若要最佳化每個 [!DNL Marketo Measure] API，請遵循下列最佳實務。

**[!DNL Facebook]**:使用自動標籤連接

啟用自動標籤之前，請先將您的廣告歷史記錄匯出為CSV。 啟用自動標籤會重設所有標籤廣告的轉換歷史記錄和社交證明 [!DNL Marketo Measure].

遵循我們的最佳實務建議， [!DNL Marketo Measure] [!DNL Facebook] API將能夠：

* 自動標籤全部 [!DNL Facebook] 具有必要 [!DNL Marketo Measure] 參數 `_bf ={creative}`
* 下載所有活動廣告成本資訊 [!DNL Facebook] 廣告

>[!NOTE]
>
>沒有的追蹤範本 [!DNL Facebook]，則API需仰賴自動標籤(_bf)參數來收集廣告詳細資料。

**AdWords**:在帳戶層級實作追蹤範本並啟用自動標籤

[!DNL Marketo Measure] 建議使用「帳戶層級」、「促銷活動層級」或「廣告群組層級追蹤」範本，因為此範本可為所有廣告新增和減除參數，而不會造成廣告歷史記錄中斷或刪除的風險。

遵循我們的最佳實務建議， [!DNL Marketo Measure] AdWords API將能：

* 使用 [!DNL Marketo Measure] 參數 `_bk={keyword}, _bt={creative}, _bm={matchtype}, _bn={network}, _bg={adgroupID}`
* 下載所有作用中AdWords廣告的廣告成本資訊

**兵**:在帳戶層級實作追蹤範本並啟用自動標籤

設定您的 [!DNL Bing] API連線，不同於其他API連線。

遵循我們的最佳實務建議， [!DNL Marketo Measure] Bing API將能夠：
* 使用下列參數自動標籤所有Bing Ads: `_bt={adid}, utm_medium=cpc, utm_source=bing, utm_term={keyword}`
* 下載所有作用中Bing廣告的廣告成本資訊

**linkedIn**:使用自動標籤連接

啟用自動標籤會重新建立「共用」，並將其置於新的「創作」中，舊的「創作」會封存。

遵循我們的最佳實務建議， [!DNL Marketo Measure] linkedIn API將能：

* 自動標籤所有屬於廣告類型的LinkedIn廣告，必要時需提供贊助內容 [!DNL Marketo Measure] 參數_bl={creativeId}。 此參數會提取創作ID，允許 [!DNL Marketo Measure] 來解析促銷活動和創意資訊。
* 下載所有活動和支援的廣告成本資訊 [!DNL LinkedIn] 廣告

>[!NOTE]
>
>沒有的追蹤範本 [!DNL LinkedIn],API會仰賴自動標籤(_bl)參數來收集所有可能的廣告詳細資訊。

## 維護最佳實務 {#best-practice-for-maintenance}

雖然遵循我們的最佳實務可保護您在中斷連線時不會遺失資料，但我們仍建議您定期檢閱連線，如有可能，每月檢閱一次。 這是對 [!UICONTROL Connections] 區段 [!DNL Marketo Measure] 應用程式，確保沒有紅色金鑰圖示，向中斷的帳戶發出信號。

當API連線的帳戶中斷連線時， [!DNL Marketo Measure] 無法提取支出資料或標籤新廣告。 這就是為什麼我們一律建議盡可能實作追蹤範本。 範本可確保即使廣告帳戶中斷連線， [!DNL Marketo Measure] 仍可標籤廣告，並提取精細的廣告詳細資訊。 重新連線後，支出資料將回填，您的付費管道報表中斷的程度極小。

斷開連接和重新授權的原因包括……

* 更改已連接的人員帳戶的密碼
* 那個人已不在公司
* API更新

如果您的團隊遇到上述任何情況，請在 [!DNL Marketo Measure] 應用程式，確保不需要重新授權。

>[!MORELIKETHIS]
>
>* [整合廣告平台(API)](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md)
>* [競標管理工具的影響 [!DNL Marketo Measure]](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md)
>* [[!DNL Marketo Measure] API參數說明](/help/api-connections/utilizing-marketo-measures-api-connections/marketo-measure-parameters.md)
>* [Facebook API概述](/help/api-connections/utilizing-marketo-measures-api-connections/facebook-api.md)
>* [[!DNL LinkedIn] 整合概述](/help/api-connections/utilizing-marketo-measures-api-connections/linkedin-integration.md)
>* [AdWords整合概述](/help/api-connections/utilizing-marketo-measures-api-connections/understanding-marketo-measure-adwords-tagging.md)
>* [重新授權連線的API帳戶](/help/api-connections/utilizing-marketo-measures-api-connections/reauthorizing-connected-accounts.md)

