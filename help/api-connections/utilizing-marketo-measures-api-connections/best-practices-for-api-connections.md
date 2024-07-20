---
description: API連線的最佳實務 —  [!DNL Marketo Measure]
title: API連線的最佳作法
exl-id: b8550e4e-a567-427f-b5d3-50232553a066
feature: APIs, Integration
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 0%

---

# API連線的最佳作法 {#best-practices-for-api-connections}

## 概觀 {#overview}

[!DNL Marketo Measure]提供與[!DNL Google AdWords]、[!DNL Microsoft Bing Ads]、[!DNL Facebook Ads]和LinkedIn的API連線。 這些API連線可讓[!DNL Marketo Measure]從您的廣告平台提取各種資料，然後可以在您的Buyer Touchpoint資料中回報。 這些API連線的一項重要功能是能夠自動提取支出資料，為您和您的團隊節省手動上傳資料以進行ROI報告所需的時間和精力。 [!DNL Marketo Measure]不必設定這些API連線來追蹤這些管道，但是它們可提供寶貴的精細細節，可增強您的報告。

[!DNL Marketo Measure] API連線是您帳戶的寶貴方面，我們的最佳實務建議將協助您和您的團隊最大程度地利用我們的連線。

## 最佳實務 {#best-practice}

無論您連線的廣告平台為何，請務必牢記以下准則！

* 使用管理員進行連線
* 您可以為一個平台連線多個廣告帳戶
* 連線所有可能的廣告帳戶，以儘可能自動化您的支出報表
* 如果可用，請一律實作追蹤範本。 範本可確保即使廣告帳戶中斷連線，[!DNL Marketo Measure]仍可提取精細的廣告詳細資料

若要最佳化每個[!DNL Marketo Measure] API，請遵循下列最佳實務。

**[!DNL Facebook]**：使用自動標籤連線

在啟用自動標籤之前，請將廣告歷史記錄匯出至csv。 啟用自動標籤將重設[!DNL Marketo Measure]標籤之所有廣告的轉換歷史記錄和社交證明。

依照我們的最佳實務建議，[!DNL Marketo Measure] [!DNL Facebook] API將能夠：

* 使用必要的[!DNL Marketo Measure]引數`_bf ={creative}`自動標籤所有[!DNL Facebook]廣告
* 下載所有作用中[!DNL Facebook]廣告的廣告成本資訊

>[!NOTE]
>
>[!DNL Facebook]沒有追蹤範本，API依賴自動標籤(_bf)引數來收集廣告詳細資料。

**AdWords**：在帳戶層級實作追蹤範本並啟用自動標籤

[!DNL Marketo Measure]建議使用帳戶層級、行銷活動層級或廣告群組層級追蹤範本，因為它允許針對所有廣告新增及減除引數，而不會造成廣告歷史記錄中斷或刪除的風險。

依照我們的最佳實務建議，[!DNL Marketo Measure] AdWords API將能夠：

* 使用`_bk={keyword}, _bt={creative}, _bm={matchtype}, _bn={network}, _bg={adgroupID}`的[!DNL Marketo Measure]引數自動標籤所有AdWords廣告
* 下載所有作用中AdWords廣告的廣告成本資訊

**Bing**：在帳戶層級實作追蹤範本並啟用自動標籤

與某些其他API連線不同，在設定您的[!DNL Bing] API連線時，不會遺失廣告歷程記錄的風險。

依照我們的最佳實務建議，[!DNL Marketo Measure] Bing API將能夠：
* 使用下列引數`_bt={adid}, utm_medium=cpc, utm_source=bing, utm_term={keyword}`自動標籤所有Bing Ads
* 下載所有作用中Bing廣告的廣告成本資訊

**LinkedIn**：連線到自動標籤

啟用自動標籤功能會重新建立共用，並將其放置在新的創意中，舊創意會封存。

依照我們的最佳實務建議，[!DNL Marketo Measure] LinkedIn API將能夠：

* 使用必要的[!DNL Marketo Measure]引數_bl={creativeId}，自動標籤屬於廣告型別「贊助內容」的所有LinkedIn廣告。 此引數提取創意ID，允許[!DNL Marketo Measure]解析行銷活動和創意資訊。
* 下載所有使用中及支援的[!DNL LinkedIn]個廣告的廣告成本資訊

>[!NOTE]
>
>[!DNL LinkedIn]沒有追蹤範本，API依賴自動標籤(_bl)引數來收集所有可能的廣告詳細資料。

## 維護最佳實務 {#best-practice-for-maintenance}

雖然遵循我們的最佳實務可防止您因中斷連線而遺失資料，但我們仍建議您定期檢查連線，如有可能，請每月檢查。 這是對您[!DNL Marketo Measure]應用程式中[!UICONTROL Connections]區段的簡單視覺檢查，以確定沒有紅色按鍵圖示出現，表示帳戶已中斷連線。

當API連線帳戶中斷連線時，[!DNL Marketo Measure]無法提取支出資料或標籤新廣告。 這就是為什麼我們總是建議儘可能實作追蹤範本的原因。 範本可確保即使廣告帳戶中斷連線，[!DNL Marketo Measure]仍可標籤廣告並提取精細的廣告詳細資料。 重新連線後，支出資料將會回填，而您的付費管道報表的中斷將會降至最低。

中斷連線及重新授權的原因包括……

* 變更已連線之個人帳戶的密碼
* 此人已不在公司
* API的更新

如果您的團隊經歷過上述任何情況，請檢查您在[!DNL Marketo Measure]應用程式中的API連線，以確保他們不需要重新授權。

>[!MORELIKETHIS]
>
>* [整合式廣告平台(API)](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md)
>* [競標管理工具如何影響 [!DNL Marketo Measure]](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md)
>* [[!DNL Marketo Measure] API引數說明](/help/api-connections/utilizing-marketo-measures-api-connections/marketo-measure-parameters.md)
>* [Facebook API總覽](/help/api-connections/utilizing-marketo-measures-api-connections/facebook-api.md)
>* [[!DNL LinkedIn] 整合概述](/help/api-connections/utilizing-marketo-measures-api-connections/linkedin-integration.md)
>* [AdWords整合總覽](/help/api-connections/utilizing-marketo-measures-api-connections/understanding-marketo-measure-adwords-tagging.md)
>* [重新授權連線的API帳戶](/help/api-connections/utilizing-marketo-measures-api-connections/reauthorizing-connected-accounts.md)
