---
unique-page-id: 18874708
description: Salesforce活動屬性 —  [!DNL Marketo Measure]  — 產品檔案
title: Salesforce活動屬性
exl-id: 1dc6f15b-2a45-4ed3-9fa3-5267366d1f45
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 0%

---

# Salesforce活動屬性 {#salesforce-activities-attribution}

此 [!DNL Marketo Measure] Salesforce活動整合會將特定任務和事件記錄帶入您的歸因模型。 開始追蹤未收到到期信用的銷售電子郵件或銷售電話等。 若要設定活動規則，您必須前往 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}. 從那裡，前往 **[!UICONTROL Settings]** ，然後按一下 **[!UICONTROL Activities]** 標籤。

你將讓你的銷售團隊非常開心！ 讓我們帶您進行快速教學課程。

![](assets/1.png)

首先，我們介紹一個新概念，稱為 [!DNL Marketo Measure] 促銷活動。 對於您定義的每個規則，您會將記錄分段至 [!DNL Marketo Measure] 您可以命名的促銷活動。 視需要新增多個行銷活動。 想像一下，如何測量付費媒體行銷活動旁的傳出行銷活動的成效！

你會用這個 [!DNL Marketo Measure] 行銷活動名稱，告訴我們應對應哪個管道。 如果您仍在考慮外站銷售，則可能所有外站銷售活動都應位於BDR渠道中。

熟悉此階層：

* 管道
   * 子頻道
      * 行銷活動
      * 行銷活動
   * 子頻道
      * 行銷活動

>[!TIP]
>
>例如，如果您想為每個銷售代表設定一個唯一的促銷活動，請使用動態替換參數來填入 [!DNL Marketo Measure] 促銷活動名稱。 在同一個範例中，您可以輸入 `"Outbound Sales - {AssignedTo}"` 然後把它變成 `"Outbound Sales - Jill"` 或 `"Outbound Sales - Jack."` 你不知道我們救了你多少時間！

![](assets/2.png)

一旦您 [!DNL Marketo Measure] 已設定促銷活動名稱，該設定活動規則了。

規則可作為篩選器，告訴我們哪些記錄符合歸因資格。 假設您是使用類似邏輯在CRM中建立報表，以產生該報表。 您可以彈性地使用和/或陳述式的組合，以及各種運算子，例如比對any、contains、starts with、ends with、等於等等。 在框外的盒裝規則或層「or」陳述式中定義&quot;and&quot;陳述式。

![](assets/3.png)

>[!NOTE]
>
>公式欄位無法在規則中使用，且不會出現在選取清單中。 因為公式在背景計算，而不修改記錄， [!DNL Marketo Measure] 無法檢測記錄是否符合規則。
>
>請務必為ID欄位（例如CrmEvent.CreatedById）使用正確的值。 [!DNL Salesforce IDs] 長度為18個字元(例如0054H000007WmrfQAC)。

最後，我們將選擇日期或日期/時間欄位之一，作為購買者接觸點日期。 可選取標準和自訂欄位。

>[!TIP]
>
>安裝您的套件後， [!DNL Marketo Measure] 在「活動」記錄中包含自訂「購買者接觸點日期」欄位。 如果您想使用動態日期，例如狀態變更的日期，則可以使用CRM工作流程來設定「購買者接觸點日期」，然後在此步驟選取「購買者接觸點日期」。

![](assets/4.png)

別忘了為任務或事件設定不同的規則。 您將需要知道您的銷售團隊使用哪個對象來記錄其活動。

![](assets/5.png)

您可能會想要將這些新接觸點放入適當的 [行銷管道](https://experience.adobe.com/#/marketo-measure/MyAccount/Business?busView=false&amp;id=10#/!/MyAccount/Business/Account.Settings.SettingsHome?tab=Channels.Online%20Channels){target="_blank"}. 您可以使用您剛建立的新行銷活動對應來定義管道，即可執行此操作。 您可能會為BDR管道建立新的列，其中促銷活動以傳出開始。

>[!TIP]
>
>新增管道定義時，請使用萬用字元值，這是描述運算子的更簡單方式，例如：
>
>開頭為(傳出&#42; )
>
>包含( &#42;傳出&#42; )
>
>結尾為( &#42;傳出)
>
>沒有萬用字元基本上表示「等於」，因此請務必視需要使用。

| **運算子** | **使用案例** |
|---|---|
| 等於 | 單一值 — 完全相符 |
| 包含 | 單一值 — 包含值 |
| 符合任何 | 多個值 — 完全相符 |
| 符合任何（包含） | 多個值 —  &#42;value&#42;, &#42;值， &#42;value&#42; |

![](assets/6.png)

最後，您可以選擇輸入新渠道的成本。 我們的 [行銷支出上傳](https://experience.adobe.com/#/marketo-measure/MyAccount/Business?busView=false&amp;id=10#/!/MyAccount/Business/Account.Settings.SettingsHome?tab=Reporting.Marketing%20Spend){target="_blank"} 可讓您在管道層級、子管道層級或促銷活動層級輸入您的支出。 使用您的新 [!DNL Marketo Measure] 行銷活動，您可以按月新增相關成本，然後查看每個行銷活動的ROI!

![](assets/7.png)

>[!MORELIKETHIS]
>
>[活動歸因常見問題集](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)
