---
unique-page-id: 18874720
description: 競標管理工具如何影響 [!DNL Marketo Measure] - [!DNL Marketo Measure]
title: 競標管理工具如何影響 [!DNL Marketo Measure]
exl-id: 67c00ad9-8b12-4238-8a1f-2d2f5ed04423
feature: APIs, Integration, UTM Parameters
TQID: https://experienceleague.adobe.com/gcugeRrHUi4qetrYBpUavRyrBHVpB0qCzPo4OYMI4hw
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
feature_v2:
  - id: fb43f4c1-87d9-4081-8df1-6fe7e6e5cdc8
source-git-commit: 9ceb54139bfa9b6ce7c2c5fbb4e25e649f5708a3
workflow-type: tm+mt
source-wordcount: 259
ht-degree: 2%

---

# 競標管理工具如何影響[!DNL Marketo Measure] {#how-bid-management-tools-affect-marketo-measure}

瞭解競標管理平台如何影響[!DNL Marketo Measure]追蹤AdWords和BingAds的能力，以及如何使用我們的引數設定追蹤範本以確保所有專案都正確追蹤。

Kenshoo和Marin是絕佳的工具，行銷人員可以透過不同的搜尋引擎追蹤、管理和最佳化其廣告促銷活動。 為了將[!DNL Marketo Measure]引數附加至這些廣告URL，您需要使用我們的[!DNL Marketo Measure]引數設定追蹤範本。 無法將您的廣告平台連線至您的[!DNL Marketo Measure]帳戶並啟用自動標籤，因為這會導致[!DNL Marketo Measure]標籤系統與Kenshoo/Marin的標籤系統競爭。 這會導致我們的引數遭到更改和錯誤附加。 若要避免此問題，必須在Kenshoo和Marin中設定包含[!DNL Marketo Measure]引數的追蹤範本。

## 針對[!DNL Adwords]個帳戶 {#for-adwords-accounts}

設定追蹤範本，如下所示：

* 按一下「**[!UICONTROL Campaigns]**」索引標籤。
* 按一下側面導覽列中的&#x200B;**[!UICONTROL Shared library]**&#x200B;連結。
* 按一下&#x200B;**URL選項**。
* 在「追蹤範本」旁邊，按一下&#x200B;**編輯**。
* 填入URL：

   * 如果您的所有廣告URL都有「？」 在其中，使用此URL：
      * `{lpurl}&_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`
   * 如果您的任何廣告URL都沒有「？」 在其中，使用此URL：
      * `{lpurl}?_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`


## 針對[!DNL Bing Ads]個帳戶 {#for-bing-ads-accounts}

設定追蹤範本，如下所示：

* 按一下「**[!UICONTROL Campaigns]**」索引標籤。
* 按一下側面導覽列中的&#x200B;**[!UICONTROL Shared library]**&#x200B;連結。
* 按一下&#x200B;**URL選項**。
* 在「追蹤範本」旁邊，按一下&#x200B;**編輯**。
* 填入URL：

   * 如果您的所有廣告URL都有「？」 在其中，使用此URL：
      * `{lpurl}&_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
   * 如果您的任何廣告URL都沒有「？」 在其中，使用此URL：
      * `{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
