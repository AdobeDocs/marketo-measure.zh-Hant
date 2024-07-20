---
unique-page-id: 18874678
description: 瞭解 [!DNL Marketo Measure] AdWords標籤 —  [!DNL Marketo Measure]
title: 瞭解 [!DNL Marketo Measure] AdWords標籤
exl-id: c6658766-d3a8-46ed-b2d2-826eb61ce269
feature: APIs, Integration, UTM Parameters
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 0%

---

# 瞭解[!DNL Marketo Measure]個AdWords標籤 {#understanding-marketo-measure-adwords-tagging}

為了在非常精細的層級追蹤您的廣告，廣告目的地URL必須是唯一的。 若要完成此操作，[!DNL Marketo Measure]自動標籤會自動將追蹤引數新增到[!DNL AdWords]個廣告的廣告目的地URL。 讓我們來看一個範例。

下列URL不會提供任何精細資料：

* `http://example.com/landing-page?myParam=foo`

不過，由於[!DNL Marketo Measure]引數，相同的URL將提供精細資料：

* `http://example.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## [!DNL Marketo Measure]自動標籤的運作方式 {#how-marketo-measure-auto-tagging-works}

**如果[!DNL Marketo Measure]找到追蹤範本：**

* [!DNL Marketo Measure]會將其引數新增至追蹤範本。
* 如果在追蹤範本中找到協力廠商重新導向，例如Kenshoo或Marin，[!DNL Marketo Measure]將不會採取任何動作。 您必須[新增 [!DNL Marketo Measure] 引數至您帳戶](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md){target="_blank"}中的協力廠商工具。

不過，如果找不到追蹤範本，[!DNL Marketo Measure]會：

* 掃描所有[!DNL Marketo Measure]引數的廣告目的地URL。
* 如果找到，則表示一切準備就緒。
* 如果找不到，[!DNL Marketo Measure]會將其引數附加至廣告目的地URL的結尾。 針對新廣告，[!DNL Marketo Measure]將在建立後的兩小時內將其引數附加至廣告目的地URL。
* 啟用自動標籤之前，請務必先設定追蹤範本，以便[!DNL Marketo Measure]可以附加至該範本，並防止重設廣告歷程記錄。

[!DNL Marketo Measure]建議使用帳戶層級、行銷活動層級或廣告群組層級追蹤範本，因為它允許針對所有廣告新增及減除引數，而不會造成廣告歷史記錄中斷或刪除的風險。

## 追蹤範本 {#tracking-templates}

如[!DNL Google AdWords]所說明，追蹤範本是用來存取登入頁面的URL。 收集到的追蹤資訊會用於瞭解您的廣告流量。 [按一下這裡](https://support.google.com/adwords/answer/7197008?hl=en){target="_blank"}以取得來自Google的詳細資訊。

[!DNL Marketo Measure]建議使用帳戶層級、行銷活動層級或廣告群組層級追蹤範本，因為它允許針對所有廣告新增及減除引數，而不會造成廣告歷史記錄中斷或刪除的風險。

有兩個追蹤範本[!DNL Marketo Measure]建議使用。 請使用下列專案來決定適合您的版本：

* 如果您的所有廣告URL都有「？」 在其中，使用此URL：

`{lpurl}&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

* 如果您的廣告URL皆不包含「？」 在其中，使用此URL：

`{lpurl}?_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## 在帳戶層級設定追蹤範本 {#setting-up-a-tracking-template-at-the-account-level}

1. 登入您的[!DNL Google AdWords]帳戶。

1. 按一下&#x200B;**[!UICONTROL All campaigns]**，然後在展開視窗中按一下&#x200B;**[!UICONTROL Settings]**。

   ![](assets/1.png)

1. 按一下頂端的&#x200B;**[!UICONTROL Account Settings]**，然後按&#x200B;**[!UICONTROL Tracking Template]**。 輸入[!DNL Marketo Measure]追蹤範本。

   ![](assets/2-1.png)

1. 按一下&#x200B;**[!UICONTROL Save]**。

## 在行銷活動層級設定追蹤範本 {#setting-up-a-tracking-template-at-the-campaign-level}

1. 按一下&#x200B;**[!UICONTROL All campaigns]**，然後在展開視窗中按一下&#x200B;**[!UICONTROL Campaigns]**。

   ![](assets/3.png)

1. 選取所有適用的行銷活動或&#x200B;**[!UICONTROL Select All]**，按一下&#x200B;**[!UICONTROL Edit]**，然後按一下&#x200B;**[!UICONTROL Change Tracking Templates]**。

   ![](assets/4-1.png)

1. 輸入[!DNL Marketo Measure]追蹤範本並按一下&#x200B;**[!UICONTROL Apply]**。

## 在廣告群組層級設定追蹤範本： {#setting-up-a-tracking-template-at-the-ad-group-level}

1. 按一下&#x200B;**[!UICONTROL All campaigns]**，然後在展開視窗中按一下&#x200B;**[!UICONTROL Ad Groups]**。

   ![](assets/5-1.png)

1. 選取所有適用的廣告群組或選取全部，按一下&#x200B;**[!UICONTROL Edit]**，然後按一下&#x200B;**[!UICONTROL Change Tracking Templates]**。

1. 輸入[!DNL Marketo Measure]追蹤範本並按一下&#x200B;**[!UICONTROL Apply]**。

   ![](assets/6-1.png)

## 常見問題集 {#faq}

**問：連線的使用者需要哪些許可權？**

答：userinfo.email

**問：匯入支出資料需要多久的時間？**

答：6小時

**問：匯入廣告資料需要多久的時間？**

答：4小時

**問：如果是動態搜尋廣告，我們可以在提供的創意中追蹤標題、說明等組合嗎？**

答：我們無法擷取動態搜尋廣告的個別創意細節，但如果已啟用自動標籤，我們仍可取得創意ID和屬性收入。

>[!NOTE]
>
>完成變更後，就表示您已完成。 如果在安裝期間有任何問題，請隨時聯絡[Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}。

[按一下這裡](https://support.google.com/adwords/answer/6076199?hl=en#tracking){target="_blank"}，取得Google關於建立帳戶層級追蹤範本的指示。
