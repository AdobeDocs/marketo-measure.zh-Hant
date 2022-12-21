---
unique-page-id: 18874720
description: 競標管理工具的影響 [!DNL Marketo Measure] - [!DNL Marketo Measure]  — 產品檔案
title: 競標管理工具的影響 [!DNL Marketo Measure]
exl-id: 67c00ad9-8b12-4238-8a1f-2d2f5ed04423
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# 競標管理工具的影響 [!DNL Marketo Measure] {#how-bid-management-tools-affect-marketo-measure}

了解競標管理平台如何影響 [!DNL Marketo Measure] 追蹤AdWords和BingAds的功能，以及如何使用參數設定追蹤範本，以確保所有項目皆可正確追蹤。

Kenshoo和Marin是絕佳的工具，可讓行銷人員使用不同的搜尋引擎來追蹤、管理和最佳化其廣告促銷活動。 為了 [!DNL Marketo Measure] 要附加至這些廣告URL的參數時，您需要使用 [!DNL Marketo Measure] 參數。 無法將您的廣告平台連結至 [!DNL Marketo Measure] 帳戶和啟用自動標籤，因為這會導致 [!DNL Marketo Measure] 標籤系統與Kenshoo/Marin的標籤系統相競爭。 這會導致參數發生變更及錯誤附加。 若要避免此情況，請使用 [!DNL Marketo Measure] 參數需要在Kenshoo和Marin中設定。

## 針對 [!DNL Adwords] 帳戶 {#for-adwords-accounts}

設定追蹤範本，如下所示：

* 按一下 **[!UICONTROL Campaigns]** 標籤。
* 按一下 **[!UICONTROL Shared library]** 連結。
* 按一下 **URL選項**.
* 在「追蹤範本」旁，按一下 **編輯**.
* 填入URL:

   * 如果您的所有廣告URL都有「？」 在它們中，使用此URL:
      * `{lpurl}&_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`
   * 如果您的廣告URL中沒有「？」 在它們中，使用此URL:
      * `{lpurl}?_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`


## 針對 [!DNL Bing Ads] 帳戶 {#for-bing-ads-accounts}

設定追蹤範本，如下所示：

* 按一下 **[!UICONTROL Campaigns]** 標籤。
* 按一下 **[!UICONTROL Shared library]** 連結。
* 按一下 **URL選項**.
* 在「追蹤範本」旁，按一下 **編輯**.
* 填入URL:

   * 如果您的所有廣告URL都有「？」 在它們中，使用此URL:
      * `{lpurl}&_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
   * 如果您的廣告URL中沒有「？」 在它們中，使用此URL:
      * `{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
