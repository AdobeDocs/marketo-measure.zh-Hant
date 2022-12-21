---
unique-page-id: 18874608
description: '"[!DNL Marketo Measure] 參數 —  [!DNL Marketo Measure]  — 產品檔案」'
title: '"[!DNL Marketo Measure] 參數」'
exl-id: d66b9864-0d7e-455a-ae20-cca555f4d8c8
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 0%

---

# [!DNL Marketo Measure] 參數 {#marketo-measure-parameters}

## [!DNL Marketo Measure] 說明的參數 {#marketo-measure-parameters-explained}

為了進一步了解UTM的使用， [!DNL Marketo Measure] 將自訂參數附加至 [!DNL Google] AdWords、Bing Ads和 [!DNL Facebook] 廣告。 [!DNL Marketo Measure] 與這些平台整合，以自動化大部分的設定程式。 如果您選取使用自動標籤， [!DNL Marketo Measure] 會自動將其參數附加至廣告的URL。 [!DNL Marketo Measure] 也會自動從平台下載行銷成本，並載入到 [!DNL Marketo Measure] 應用程式。

不含參數的URL範例：

`http://adobe.com/landing-page?myParam=foo`

URL的範例，其中 [!DNL Marketo Measure] 參數：

`http://adobe.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## AdWords參數 {#adwords-parameters}

* `_bk={keyword}`
   * 代表搜尋引擎中使用的人員關鍵字。
   * 它類似於UTM術語參數。

* `_bt={creative}`
   * 代表創作ID或名稱。
   * 它類似於UTM內容參數。

* `_bm={matchtype}`
   * 代表關鍵字的匹配程度。
   * 關鍵字比對類型有助於控制哪些搜尋會觸發您的廣告。 例如，您可以使用廣泛比對來向廣泛對象顯示廣告，或使用完全相符來磨練特定的客戶群組。
   * 三種匹配類型為：廣泛、模糊、準確。

>[!NOTE]
>
>如需符合類型的詳細資訊， [這是相關的AdWords文章](https://support.google.com/adwords/answer/2497836?hl=en){target=&quot;_blank&quot;}。

* `_bn={network}`
   * 代表廣告網路類型 —  [顯示或搜尋](https://support.google.com/adwords/answer/1752334?hl=en){target=&quot;_blank&quot;}。
   * 這類似於UTM Source參數。

* `_bg={adgroupID}`
   * 代表廣告所屬的廣告群組ID

## Bing Ads參數 {#bing-ads-parameters}

* `_bt={adid}`
* `utm_medium=cpc`
* `utm_source=bing`
* `utm_term={keyword}`

## Facebook參數 {#facebook-parameters}

* `_bf ={creative}`
   * 這代表創作ID或名稱
