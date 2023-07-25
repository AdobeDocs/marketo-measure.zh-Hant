---
unique-page-id: 18874608
description: '"[!DNL Marketo Measure] 引數 —  [!DNL Marketo Measure]  — 產品檔案」'
title: '"[!DNL Marketo Measure] 引數」'
exl-id: d66b9864-0d7e-455a-ae20-cca555f4d8c8
source-git-commit: 7ee55e3493558880408e76a4572667348ffedd8e
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 0%

---

# [!DNL Marketo Measure] 引數 {#marketo-measure-parameters}

## [!DNL Marketo Measure] 引數說明 {#marketo-measure-parameters-explained}

若要進一步瞭解如何使用UTM， [!DNL Marketo Measure] 將自訂引數附加至中的廣告 [!DNL Google] AdWords、Bing Ads和 [!DNL Facebook] 廣告。 [!DNL Marketo Measure] 與這些平台整合，以自動化大部分的設定程式。 如果您選取使用自動標籤， [!DNL Marketo Measure] 會自動將其引數附加至廣告的URL。 [!DNL Marketo Measure] 也會自動從平台下載行銷成本，並將其載入至 [!DNL Marketo Measure] 應用程式。

沒有引數的URL範例：

`http://adobe.com/landing-page?myParam=foo`

具有的URL範例 [!DNL Marketo Measure] 引數：

`http://adobe.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## AdWords引數 {#adwords-parameters}

* `_bk={keyword}`
   * 代表人員在搜尋引擎中使用的關鍵字。
   * 它類似於UTM字詞引數。

* `_bt={creative}`
   * 代表創作ID或名稱。
   * 它類似於UTM內容引數。

* `_bm={matchtype}`
   * 表示關鍵字的符合程度。
   * 關鍵字比對型別有助於控制哪些搜尋會觸發您的廣告。 例如，您可以使用廣泛比對來向廣泛的對象顯示您的廣告，或使用完全比對來深入檢視特定客戶群組。
   * 三種相符型別為：廣泛、模糊和精確。

>[!TIP]
>
>如需比對型別的詳細資訊， [以下是相關的AdWords文章](https://support.google.com/adwords/answer/2497836?hl=en){target="_blank"}.

* `_bn={network}`
   * 代表廣告網路型別 —  [顯示或搜尋](https://support.google.com/adwords/answer/1752334?hl=en){target="_blank"}.
   * 這類似於UTM來源引數。

* `_bg={adgroupID}`
   * 代表廣告所屬的廣告群組ID

>[!NOTE]
>
>我們不支援重新導向URL引數。

## Bing Ads引數 {#bing-ads-parameters}

* `_bt={adid}`
* `utm_medium=cpc`
* `utm_source=bing`
* `utm_term={keyword}`

## facebook引數 {#facebook-parameters}

* `_bf ={creative}`
   * 這代表創作ID或名稱
