---
unique-page-id: 18874678
description: 瞭解 [!DNL Marketo Measure] AdWords標籤 —  [!DNL Marketo Measure]  — 產品檔案
title: 瞭解 [!DNL Marketo Measure] AdWords標籤
exl-id: c6658766-d3a8-46ed-b2d2-826eb61ce269
source-git-commit: 7ee55e3493558880408e76a4572667348ffedd8e
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---

# 瞭解 [!DNL Marketo Measure] AdWords標籤 {#understanding-marketo-measure-adwords-tagging}

為了在非常精細的層級追蹤您的廣告，廣告目的地URL必須是唯一的。 若要完成此作業， [!DNL Marketo Measure] 自動標籤會自動將追蹤引數新增至的廣告目的地URL [!DNL AdWords] 廣告。 讓我們來看看以下範例。

下列URL不會提供任何精細的資料：

* `http://example.com/landing-page?myParam=foo`

不過，相同的URL將提供細微資料，原因在於 [!DNL Marketo Measure] 引數：

* `http://example.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## 如何 [!DNL Marketo Measure] 自動標籤功能 {#how-marketo-measure-auto-tagging-works}

**若 [!DNL Marketo Measure] 尋找追蹤範本：**

* [!DNL Marketo Measure] 會將其引數新增至追蹤範本。
* 如果在追蹤範本中找到協力廠商重新導向，例如Kenshoo或Marin， [!DNL Marketo Measure] 不會採取任何動作。 您必須 [新增 [!DNL Marketo Measure] 至您帳戶中第三方工具的引數](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md){target="_blank"}.

不過，如果找不到追蹤範本， [!DNL Marketo Measure] 將：

* 掃描我們的所有廣告目的地URL [!DNL Marketo Measure] 引數。
* 如果找到，則表示您已準備就緒。
* 如果找不到， [!DNL Marketo Measure] 會將其引數附加至廣告目的地URL的結尾。 對於新廣告， [!DNL Marketo Measure] 會在建立後的兩小時內，將其引數附加至廣告目的地URL。
* 啟用自動標籤之前，請務必先建立追蹤範本，以便 [!DNL Marketo Measure] 可以附加至該檔案並防止廣告記錄重設。

[!DNL Marketo Measure] 建議使用帳戶層級、行銷活動層級或廣告群組層級追蹤範本，因為它允許為所有廣告新增和減除引數，而無廣告歷史記錄中斷或刪除的風險。

## 追蹤範本 {#tracking-templates}

如以下內容所述： [!DNL Google AdWords]，追蹤範本是用於存取登入頁面的URL。 收集到的追蹤資訊會用於瞭解您的廣告流量。 [按一下這裡](https://support.google.com/adwords/answer/7197008?hl=en){target="_blank"} 以取得Google的詳細資訊。

[!DNL Marketo Measure] 建議使用帳戶層級、行銷活動層級或廣告群組層級追蹤範本，因為它允許為所有廣告新增和減除引數，而無廣告歷史記錄中斷或刪除的風險。

有兩種追蹤範本 [!DNL Marketo Measure] 建議使用。 請使用下列專案來判斷適合您的版本：

* 如果您的所有廣告URL都有「？」 在其中，使用此URL：

`{lpurl}&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

* 如果您的廣告URL均未包含「？」 在其中，使用此URL：

`{lpurl}?_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## 在帳戶層級設定追蹤範本 {#setting-up-a-tracking-template-at-the-account-level}

1. 登入您的 [!DNL Google AdWords] 帳戶。

1. 按一下 **[!UICONTROL All campaigns]** 然後 **[!UICONTROL Settings]** 在展開視窗中。

   ![](assets/1.png)

1. 按一下 **[!UICONTROL Account Settings]** 在上方，然後 **[!UICONTROL Tracking Template]**. 輸入 [!DNL Marketo Measure] 追蹤範本。

   ![](assets/2-1.png)

1. 按一下 **[!UICONTROL Save]**.

## 在行銷活動層級設定追蹤範本 {#setting-up-a-tracking-template-at-the-campaign-level}

1. 按一下 **[!UICONTROL All campaigns]** 然後 **[!UICONTROL Campaigns]** 在展開視窗中。

   ![](assets/3.png)

1. 選取所有適用的行銷活動或 **[!UICONTROL Select All]**，按一下 **[!UICONTROL Edit]**，然後按一下 **[!UICONTROL Change Tracking Templates]**.

   ![](assets/4-1.png)

1. 輸入 [!DNL Marketo Measure] 追蹤範本和點按 **[!UICONTROL Apply]**.

## 在廣告群組層級設定追蹤範本： {#setting-up-a-tracking-template-at-the-ad-group-level}

1. 按一下 **[!UICONTROL All campaigns]** 然後 **[!UICONTROL Ad Groups]** 在展開視窗中。

   ![](assets/5-1.png)

1. 選取所有適用的廣告群組或全選，按一下 **[!UICONTROL Edit]** 然後按一下 **[!UICONTROL Change Tracking Templates]**.

1. 輸入 [!DNL Marketo Measure] 追蹤範本和點按 **[!UICONTROL Apply]**.

   ![](assets/6-1.png)

## 常見問題集 {#faq}

**問：連線使用者需要哪些許可權？**

答：userinfo.email

**問：匯入支出資料需要多久的時間？**

答：6小時

**問：匯入廣告資料需要多久的時間？**

答：4小時

**問：若使用動態搜尋廣告，我們可以在提供的創意內容中追蹤標題、說明等專案的組合嗎？**

答：我們無法擷取動態搜尋廣告的個別創意細節，但如果啟用自動標籤，我們仍可取得創意ID和屬性收入。

>[!NOTE]
>
>完成變更後，您就完成了。 歡迎您隨時聯絡 [Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} 如果在設定期間有任何問題。

[按一下這裡](https://support.google.com/adwords/answer/6076199?hl=en#tracking){target="_blank"} 以取得Google建立帳戶層級追蹤範本的說明。
