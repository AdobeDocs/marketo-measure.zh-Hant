---
unique-page-id: 18874704
description: 活動歸因常見問題集 —  [!DNL Marketo Measure]
title: 活動歸因常見問題集
exl-id: 6272024f-b6ae-4aa7-ba92-c9f183549614
feature: Attribution
source-git-commit: e5931d783d8aad9ab0b32b4e30bbbfdfd46230dd
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 0%

---

# 活動歸因常見問題集 {#activities-attribution-faq}

[!DNL Marketo Measure]活動會匯入您的所有活動記錄並為其產生接觸點，以允許這些活動接收歸因評分。 最常見的使用案例是追蹤銷售團隊的活動，因為這些活動通常會建立傳送給潛在客戶的電話或電子郵件記錄。 其他可以追蹤的獨特專案包括內容互動，例如資產下載或視訊檢視。

>[!AVAILABILITY]
>
>此功能僅對第2層客戶啟用。 若要要求更高的客戶層級，請聯絡Adobe客戶團隊（您的客戶經理）。

**這跟離線行銷活動有何不同？**

最大的差異在於「行銷活動」只能提供一個接觸點，因為「行銷活動」只允許每個潛在客戶或聯絡人擁有一個行銷活動成員。 這表示除非您為每個群組建立個別行銷活動，否則您無法追蹤週期性事件，例如傳出電話或示範或網路研討會出席者。 活動可讓您測量每個事件。

**任務、事件和活動之間是否有差異？**

Activities物件可作為Task和Event物件的傘狀物件或父件。 活動基本上同時涵蓋任務和事件。 任務通常用於記錄快速的一次性專案，例如電話或電子郵件。 事件通常用於可能有開始或結束日期的事情，例如會議或會議。

**如果我有具有相同遞回任務的Lead或Contact，我是否會看到所有這些專案的購買者接觸點？**

可以。您的同步活動與建立的接觸點之間會維持1:1關係。

**我如何知道哪些記錄會導致建立接觸點？**

建議先在CRM中使用Activity物件設定您的篩選器。 根據篩選規則，您會很好瞭解有多少記錄符合該條件，然後您可以視需要加以調整。 這並不需要，但這是讓使用者瞭解在設定活動規則後將會建立多少活動接觸點的有用方法。

**什麼是[!DNL Marketo Measure]行銷活動名稱？**

由於這些活動會產生接觸點，[!DNL Marketo Measure]必須知道他們屬於哪個管道和子管道。 您必須為每個規則提供[!DNL Marketo Measure]行銷活動名稱。 建立之後，請使用線上頻道CSV將該[!DNL Marketo Measure]行銷活動名稱對應到其適當的頻道。 [!DNL Marketo Measure]行銷活動名稱也會出現在接觸點本身的[!UICONTROL Ad Campaign Name]欄位中。

**已填入哪些其他接觸點欄位？**

| **接觸點欄位** | **值** |
|---|---|
| 銷售機會/聯絡人 | 所有活動都與潛在客戶或聯絡人有關 |
| Campaign | Channel.Subchannel [[!DNL Marketo Measure]] |
| 接觸點Source | CRM活動 |
| 媒體 | Activity.Type |
| 接觸點型別 | Activity.Type |
| 廣告行銷活動名稱 | [!DNL Marketo Measure]行銷活動名稱 |
| 廣告內容 | 活動主題 |
| 廣告ID | 活動外部Id |
| 接觸點日期 | [自訂 — 設定於應用程式] |

**如果我必須為每位銷售代表建立不同的規則，該怎麼辦？ 我是否需要為每個建立不同的[!DNL Marketo Measure]行銷活動？**

不可以。 「動態行銷活動名稱」可讓您使用參考活動物件欄位的「取代引數」，填入[!DNL Marketo Measure]行銷活動名稱的一部分（或全部）。 例如，如果您有[!DNL Marketo Measure]促銷活動名稱標題為&quot;Outbound Call&quot;，但您想要讓銷售代表在結尾處，請接受CRM欄位名稱並呼叫[!DNL Marketo Measure]促銷活動名稱&quot;Outbound Call {AssignedTo}&quot;或&quot;Outbound Call {CreatedBy}&quot;。

**如何在[!DNL Marketo Measure]應用程式中設定活動？**

您可在[!DNL Marketo Measure]活動支援文章中找到如何設定[!UICONTROL Marketo]量值應用程式內活動的指示。

**不同的運運算元代表什麼意思？**

* 等於：與值完全相符（亦稱為： social）
* 包含：文字位於中間（亦即： &#42;social&#42;）
* 開頭為：值開頭為文字（亦即： social&#42;）
* 結尾為：值結尾為文字（亦即： &#42;social）
* 符合任何：可新增多個以逗號分隔的值。 如果必須套用[!UICONTROL starts with]、[!UICONTROL ends with]或包含運運算元，請使用萬用字元(&#42;)
* 大於：用於數值欄位或日期/時間欄位
* 小於：用於數值欄位或日期/時間欄位

**這些活動是根據哪個管道？**

建立活動規則及其對應的[!DNL Marketo Measure]行銷活動名稱時，請使用線上管道定義，將這些行銷活動放置在正確的行銷管道下。 [!DNL Marketo Measure]不僅可以使用媒體和來源，而且可以使用行銷活動來定義管道。

在上述範例中，若要將「傳出呼叫{指派給}」行銷活動指派給BDR頻道，請在您的線上頻道CSV中為BDR頻道插入一列，其行銷活動定義為「傳出呼叫&#42;」（星號代表萬用字元值），因此所有以「傳出呼叫」開頭的行銷活動都將落在BDR頻道之下，而不必為每個行銷活動名稱建立個別的列。
