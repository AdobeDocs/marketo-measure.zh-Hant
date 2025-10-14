---
unique-page-id: 18874708
description: Salesforce活動歸因 —  [!DNL Marketo Measure]
title: Salesforce活動歸因
exl-id: 1dc6f15b-2a45-4ed3-9fa3-5267366d1f45
feature: Attribution, Salesforce
source-git-commit: e5931d783d8aad9ab0b32b4e30bbbfdfd46230dd
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 1%

---

# Salesforce活動歸因 {#salesforce-activities-attribution}

[!DNL Marketo Measure] Salesforce活動整合會將特定的任務和事件記錄帶入您的歸因模型。 開始追蹤未收到到期點數的銷售電子郵件或銷售電話等內容。 若要設定活動規則，請移至[experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}。 從那裡，移至&#x200B;**[!UICONTROL Settings]**&#x200B;標籤，然後按一下&#x200B;**[!UICONTROL Activities]**&#x200B;標籤。

![](assets/1.png)

>[!AVAILABILITY]
>
>此功能僅對第2層客戶啟用。 若要要求更高的客戶層級，請聯絡Adobe客戶團隊（您的客戶經理）。

首先，我們推出名為「[!DNL Marketo Measure]」行銷活動的新概念。 對於您定義的每個規則，您會將記錄儲存至您可命名的[!DNL Marketo Measure]行銷活動中。 視需要新增多個行銷活動。 想像一下在付費媒體行銷活動旁邊測量對外銷售行銷活動的成效！

您即將使用此[!DNL Marketo Measure]行銷活動名稱，告訴我們應將其對應至哪個管道。 如果您仍在考慮「傳出銷售」，或許所有「傳出銷售」行銷活動都應該位於BDR管道中。

熟悉此階層：

* Channel
   * 子管道
      * Campaign
      * Campaign
   * 子管道
      * Campaign

>[!TIP]
>
>舉例來說，如果您想要為每個銷售代表設定唯一的促銷活動，請使用動態取代引數來填入[!DNL Marketo Measure]促銷活動名稱。 在相同的範例中，您可以輸入`"Outbound Sales - {AssignedTo}"`，然後它會將其變更為`"Outbound Sales - Jill"`或`"Outbound Sales - Jack."`之類的專案

![](assets/2.png)

設定[!DNL Marketo Measure]行銷活動名稱后，就可以設定活動規則了。

規則可當作篩選條件，告訴我們哪些記錄符合歸因資格。 想像您正使用類似的邏輯在CRM中建立報告，以產生該報告。 您可以靈活地結合使用and/or陳述式以及各種運運算元，例如`matches any`、`contains`、`starts with`、`ends with`、`is equal to`。 定義盒裝規則內的`and`陳述式或方塊外的圖層`or`陳述式。

![](assets/3.png)

>[!NOTE]
>
>公式欄位無法在規則中使用，也不會出現在選擇清單中。 因為公式會在背景計算且不會修改記錄，[!DNL Marketo Measure]無法偵測記錄是否符合規則。
>
>請務必對ID欄位使用正確的值，例如CrmEvent.CreatedById。 [!DNL Salesforce IDs]長度為18個字元( 0054H000007WmrfQAC)。

最後，選擇一個日期或日期/時間欄位來用作Buyer Touchpoint日期。 標準和自訂欄位都是可選取的。

>[!TIP]
>
>安裝套件時，[!DNL Marketo Measure]在活動記錄中包含自訂Buyer Touchpoint日期欄位。 如果您想要使用動態日期，例如狀態變更的日期，則可以使用CRM工作流程來設定「Buyer Touchpoint日期」，然後在此步驟中選取Buyer Touchpoint日期。

![](assets/4.png)

別忘了為任務或事件設定不同的規則。 您必須知道您的銷售團隊使用哪個物件來記錄其活動。

![](assets/5.png)

您可能會想要將這些新的接觸點放入其適當的[行銷管道](https://experience.adobe.com/#/marketo-measure/MyAccount/Business?busView=false&id=10#/!/MyAccount/Business/Account.Settings.SettingsHome？tab=Channels.Online%20Channels){target="_blank"}。 使用剛建立的新行銷活動對應來定義頻道，以執行此操作。

>[!TIP]
>
>新增管道定義時，請使用萬用字元值，這是陳述運運算元如下的更簡單方式：
>
>開頭為（傳出&#42; ）
>
>包含（ &#42;傳出&#42; ）
>
>結尾為（ &#42;傳出）
>
>無萬用字元基本上表示「等於」，因此請務必視需要使用它們。

| **運運算元** | **使用案例** |
|---|---|
| 等於 | 單一值 — 完全相符 |
| 包含 | 單一值 — 包含值 |
| 符合任一 | 多個值 — 完全相符 |
| 符合任何（包含） | 多個值 — &#42;值&#42;、&#42;值、&#42;值&#42; |

![](assets/6.png)

最後，您可以選擇輸入新管道的成本。 [行銷支出上傳](https://experience.adobe.com/#/marketo-measure/MyAccount/Business?busView=false&id=10#/!/MyAccount/Business/Account.Settings.SettingsHome？tab=Reporting.Marketing%20Spent){target="_blank"}可讓您在頻道層級、子頻道層級或行銷活動層級輸入支出。 使用新的[!DNL Marketo Measure]行銷活動，您可以按月新增這些相關成本，然後檢視每個行銷活動的ROI！

![](assets/7.png)

>[!MORELIKETHIS]
>
>[活動歸因常見問題集](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)
