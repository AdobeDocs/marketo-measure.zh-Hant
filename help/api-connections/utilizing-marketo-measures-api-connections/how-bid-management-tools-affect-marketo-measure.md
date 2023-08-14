---
unique-page-id: 18874720
description: 競標管理工具如何影響 [!DNL Marketo Measure] - [!DNL Marketo Measure]  — 產品檔案
title: 競標管理工具如何影響 [!DNL Marketo Measure]
exl-id: 67c00ad9-8b12-4238-8a1f-2d2f5ed04423
feature: APIs, Integration, UTM Parameters
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# 競標管理工具如何影響 [!DNL Marketo Measure] {#how-bid-management-tools-affect-marketo-measure}

瞭解競標管理平台如何影響 [!DNL Marketo Measure] 能夠追蹤AdWords和BingAds，以及如何使用我們的引數設定追蹤範本，以確保所有專案都正確追蹤。

Kenshoo和Marin是絕佳的工具，行銷人員可以透過不同的搜尋引擎追蹤、管理和最佳化其廣告促銷活動。 為了 [!DNL Marketo Measure] 要附加至這些廣告URL的引數，您需要使用我們的 [!DNL Marketo Measure] 引數。 您的廣告平台無法連線至 [!DNL Marketo Measure] 帳戶並啟用自動標籤，因為它會導致 [!DNL Marketo Measure] 標籤系統，與Kenshoo/Marin的標籤系統競爭。 這會導致我們的引數遭到更改和錯誤附加。 若要避免此情況，請使用追蹤範本 [!DNL Marketo Measure] 引數需要在Kenshoo和Marin中設定。

## 的 [!DNL Adwords] 帳戶 {#for-adwords-accounts}

設定追蹤範本，如下所示：

* 按一下 **[!UICONTROL Campaigns]** 標籤。
* 按一下 **[!UICONTROL Shared library]** 側面導覽列中的連結。
* 按一下 **URL選項**.
* 在「追蹤範本」旁邊，按一下 **編輯**.
* 填入URL：

   * 如果您的所有廣告URL都有「？」 在其中，使用此URL：
      * `{lpurl}&_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`
   * 如果您的任何廣告URL都沒有「？」 在其中，使用此URL：
      * `{lpurl}?_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`


## 的 [!DNL Bing Ads] 帳戶 {#for-bing-ads-accounts}

設定追蹤範本，如下所示：

* 按一下 **[!UICONTROL Campaigns]** 標籤。
* 按一下 **[!UICONTROL Shared library]** 側面導覽列中的連結。
* 按一下 **URL選項**.
* 在「追蹤範本」旁邊，按一下 **編輯**.
* 填入URL：

   * 如果您的所有廣告URL都有「？」 在其中，使用此URL：
      * `{lpurl}&_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
   * 如果您的任何廣告URL都沒有「？」 在其中，使用此URL：
      * `{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
