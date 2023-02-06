---
unique-page-id: 18874678
description: 了解 [!DNL Marketo Measure] AdWords標籤 —  [!DNL Marketo Measure]  — 產品檔案
title: 了解 [!DNL Marketo Measure] AdWords標籤
exl-id: c6658766-d3a8-46ed-b2d2-826eb61ce269
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 0%

---

# 了解 [!DNL Marketo Measure] AdWords標籤 {#understanding-marketo-measure-adwords-tagging}

若要在非常精細的層級追蹤廣告，廣告目標URL必須是唯一的。 要完成此操作， [!DNL Marketo Measure] 自動標籤會自動將追蹤參數新增至您的廣告目標URL [!DNL AdWords] 廣告。 讓我們看下面的一個例子。

下列URL不會提供任何精細資料：

* `http://example.com/landing-page?myParam=foo`

不過，相同的URL將提供精細資料，因為 [!DNL Marketo Measure] 參數：

* `http://example.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## 如何 [!DNL Marketo Measure] 自動標籤有效 {#how-marketo-measure-auto-tagging-works}

**若 [!DNL Marketo Measure] 尋找追蹤範本：**

* [!DNL Marketo Measure] 會將其參數新增至追蹤範本。
* 如果在追蹤範本（例如Kenshoo或Marin）中找到第三方重新導向， [!DNL Marketo Measure] 不會採取任何行動。 相反，您必須 [新增 [!DNL Marketo Measure] 參數至帳戶中的協力廠商工具](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md){target="_blank"}.

不過，如果找不到追蹤範本， [!DNL Marketo Measure] 會：

* 掃描我們的所有廣告目標URL [!DNL Marketo Measure] 參數。
* 如果找到，你就可以走了。
* 如果找不到， [!DNL Marketo Measure] 會將其參數附加至廣告目的地URL的結尾。 對於新廣告， [!DNL Marketo Measure] 會在建立後的兩小時內，將其參數附加至廣告目的地URL。
* 啟用自動標籤之前，請務必先建立追蹤範本，這樣才能 [!DNL Marketo Measure] 可附加至廣告記錄，並防止廣告歷史記錄重設。

[!DNL Marketo Measure] 建議使用「帳戶層級」、「促銷活動層級」或「廣告群組層級追蹤」範本，因為此範本可為所有廣告新增和減除參數，而不會造成廣告歷史記錄中斷或刪除的風險。

## 追蹤範本 {#tracking-templates}

如 [!DNL Google AdWords]，追蹤範本是用來存取登錄頁面的URL。 收集的追蹤資訊用於了解您的廣告流量。 [按一下這裡](https://support.google.com/adwords/answer/7197008?hl=en){target="_blank"} 以取得Google的詳細資訊。

[!DNL Marketo Measure] 建議使用「帳戶層級」、「促銷活動層級」或「廣告群組層級追蹤」範本，因為此範本可為所有廣告新增和減除參數，而不會造成廣告歷史記錄中斷或刪除的風險。

有兩個追蹤範本 [!DNL Marketo Measure] 建議使用。 請使用下列程式碼來判斷哪個版本適合您：

* 如果您的所有廣告URL都有「？」 在它們中，使用此URL:

`{lpurl}&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

* 如果您的廣告URL中沒有「？」 在它們中，使用此URL:

`{lpurl}?_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## 在帳戶層級設定追蹤範本 {#setting-up-a-tracking-template-at-the-account-level}

1. 登入 [!DNL Google AdWords] 帳戶。

1. 按一下 **[!UICONTROL All campaigns]** 然後 **[!UICONTROL Settings]** 在展開的視窗中。

   ![](assets/1.png)

1. 按一下 **[!UICONTROL Account Settings]** 在頂端，然後 **[!UICONTROL Tracking Template]**. 輸入 [!DNL Marketo Measure] 追蹤範本。

   ![](assets/2-1.png)

1. 按一下 **[!UICONTROL Save]**.

## 在促銷活動層級設定追蹤範本 {#setting-up-a-tracking-template-at-the-campaign-level}

1. 按一下 **[!UICONTROL All campaigns]** 然後 **[!UICONTROL Campaigns]** 在展開的視窗中。

   ![](assets/3.png)

1. 選取所有適用的促銷活動或 **[!UICONTROL Select All]**，按一下 **[!UICONTROL Edit]**，然後按一下 **[!UICONTROL Change Tracking Templates]**.

   ![](assets/4-1.png)

1. 輸入 [!DNL Marketo Measure] 追蹤範本，然後按一下 **[!UICONTROL Apply]**.

## 在廣告群組層級設定追蹤範本： {#setting-up-a-tracking-template-at-the-ad-group-level}

1. 按一下 **[!UICONTROL All campaigns]** 然後 **[!UICONTROL Ad Groups]** 在展開的視窗中。

   ![](assets/5-1.png)

1. 選擇所有適用的廣告群組或選擇全部，按一下 **[!UICONTROL Edit]** 然後按一下 **[!UICONTROL Change Tracking Templates]**.

1. 輸入 [!DNL Marketo Measure] 追蹤範本，然後按一下 **[!UICONTROL Apply]**.

   ![](assets/6-1.png)

## 常見問題集 {#faq}

**問：連線的使用者需要什麼權限？**

答：userinfo.email

**問：匯入支出資料需要多久的時間？**

答：6小時

**問：匯入廣告資料需要多久時間？**

答：4小時

>[!NOTE]
>
>進行變更後，即完成。 隨時可以聯繫 [Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} 設定期間是否有任何問題。

[按一下這裡](https://support.google.com/adwords/answer/6076199?hl=en#tracking){target="_blank"} Google建立帳戶層級追蹤範本的相關指示。
