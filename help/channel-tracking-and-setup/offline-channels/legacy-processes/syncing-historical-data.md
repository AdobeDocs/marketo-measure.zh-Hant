---
unique-page-id: 42762310
description: 同步處理歷史資料 —  [!DNL Marketo Measure]
title: 同步歷史資料
exl-id: 5a3c1a71-463a-4d75-98b9-fc225839512a
feature: Channels
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '1502'
ht-degree: 0%

---

# 同步歷史資料 {#syncing-historical-data}

[!DNL Marketo Measure]是提供最精細、可操作資料的解決方案。 不過，我們瞭解您可能有想要歸因的現有資料。 您可以產生歷史資料的接觸點，但在進行此程式前務必要考量數個因素。

>[!NOTE]
>
>本文會介紹過時的程式。 我們鼓勵使用者使用[新的、改良的應用程式內程式](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"}。

## 要考量的因素 {#factors-to-consider}

**資料是否已組織到行銷活動中？**

a.資料必須整理到Campaigns以同步至[!DNL Marketo Measure]，才能產生接觸點。 如果目前未組織至「行銷活動」，則您會想要評估，是否值得將資料區隔至適當行銷活動所需的時間和資源。

b.將成員新增至促銷活動或標示為已回應的日期將用於接觸點日期，因此這也需要準確。 [!DNL Marketo Measure]在SFDC和MSD中同時提供更新日期的因應措施，但視磁碟區而定，這可能相當耗時。

**您是否針對所有管道（付費搜尋、活動、有機等）將相當相等的資料量組織到行銷活動中？**

為了提供準確且「公正」的報告，擁有平衡的歸因圖景非常重要。 例如，如果您只有歷史離線管道作業（如事件）的資料，則資料本身會有所偏差，沒有歷史線上資料作為補充。

**您期望的詳細程度為何？**

您基本上只會知道頻道、子頻道和促銷活動名稱。

**您未來的報告目標為何？**

此資料將受到限制，因此請務必考慮您計畫如何使用此資料。 將歷史資料與未來資料進行比較可能沒有意義。

**您要回到多久之前？**

[!DNL Marketo Measure]強烈建議不要超過上一年。

我們強烈建議您先與您的[!DNL Marketo Measure]連絡人討論此主題。 如果您已考慮上述事項且想要繼續，一般指示（[!DNL Salesforce]與[!DNL Microsoft Dynamics]分開）如下。

## 正在同步[!DNL Salesforce]中的歷史行銷活動 {#syncing-historic-campaigns-in-salesforce}

**線上：**

若要同步處理線上歷史資料，您必須將資料整理到Salesforce Campaigns中，然後透過[!DNL Marketo Measure]應用程式中的[!DNL Salesforce] Campaign同步處理規則同步處理到[!DNL Marketo Measure]。 請務必確認，在您的JavaScript上線日期後，接觸點不會從這些行銷活動產生。 這是為了避免重複的接觸點。 JavaScript上線後，系統會自動追蹤線上工作，所以我們不想透過SFDC促銷活動追蹤他們。 若要避免此問題，請務必在規則中新增時間感。 「行銷活動會員建立日期小於[JavaScript上線日期]」之類的訊息。

![](assets/syncing-historical-data-1.png)

線上歷史資料的管道對應元件可能會有點棘手。 我們希望它儘可能符合您目前的線上管道規則（來自線上規則表），以實現乾淨的報告。 以下是理想管道對應的範例。

>[!NOTE]
>
>此管道對應是在[!DNL Marketo Measure]應用程式的[!UICONTROL Offline Channels]區段中完成的，因為我們使用SFDC行銷活動。

| Salesforce促銷活動型別 | 管道 | 子管道 |
|---|---|---|
| 付費搜尋 — AdWords | 付費搜尋 | AdWords |
| 付費搜尋 — Bing | 付費搜尋 | Bing |
| 付費搜尋 — Yahoo | 付費搜尋 | Yahoo |

以這種方式新增的線上資料，其精細度原本會比透過JavaScript新增的線上資料[!DNL Marketo Measure]磁軌來得低。 例如，將不會填入表單URL、登陸頁面、反向連結頁面等欄位。 因此，建議儘可能將行銷活動拆分成每個來源。 如上述範例所示，您需針對每個來源設定多個促銷活動型別，才能在報表中有詳細程度。

SFDC行銷活動型別的數量可能無法支援精細的管道對應，這是不合理的，因此您可能會求助於僅對應至管道層級，而忽略子管道。 如果管道層級也不清楚，您可以設定Proxy管道，例如「Historic Digital」，這樣您就至少知道是線上接觸。

如果您需要大量編輯將針對這些歷史線上努力推送的接觸點日期，請使用[!DNL Marketo Measure]自訂&quot;[!UICONTROL Bulk Update Touchpoint Date]&quot;按鈕（這在SFDC中的Campaign物件上當作自訂欄位提供）。 如果行銷活動具有較短的時間範圍，或許值得依逐日間隔大量編輯接觸點日期，但如果行銷活動具有較長的時間範圍，則可能適合每週大量更新。 如果您確實使用「大量更新接觸點日期」功能，請務必更新「Campaign同步規則」，以使用「日期」欄位上的「Buyer Touchpoint日期」 。 請注意，這可能要求您的Campaign同步規則具有創造性，如果這僅適用一或兩個行銷活動，而非全部。

**離線：**

離線行銷工作的歷史資料(無法透過JavaScript追蹤的資料)也需要組織到SFDC行銷活動中。 SFDC行銷活動是[!DNL Marketo Measure]追蹤離線工作的方式，無論活動是「歷史」還是「目前/後[!DNL Marketo Measure]實施」，因此請遵循原始離線管道設定訓練中決定的相同管道對應。

如有必要，請使用「大量更新接觸點日期」按鈕以大量編輯行銷活動成員的接觸點日期。 例如，如果您在事件發生後建立SFDC行銷活動，您想要大量編輯正確的日期。 如果您確實使用「大量更新接觸點日期」功能，請務必更新「Campaign同步規則」，以使用「日期」欄位上的「Buyer Touchpoint日期」 。 請注意，這可能要求您的Campaign同步規則具有創造性，如果這僅適用一或兩個行銷活動，而非全部。

## 正在同步[!DNL Dynamics]中的歷史行銷活動 {#syncing-historic-campaigns-in-dynamics}

只要在過去發生的互動已在[!DNL Dynamics]內整理為行銷活動，[!DNL Marketo Measure]便能回溯產生這些互動的接觸點。

這通常涉及在CRM中說明歷史日期的工作。 線上作業（由JS追蹤）和離線作業（無法由JS追蹤）的處理方式也會不同。

請依照下列指示，以可以同步至[!DNL Marketo Measure]的格式組織[!DNL Dynamics]的歷史資料。

**線上：**

歷史數位資料需要整理為[!DNL Dynamics]個行銷活動才能進行回填。 理想情況下，此結構已經就位。

如果資料存放於其他地方（例如仍留在Marketing Automation中），則需要將其推送至[!DNL Dynamics]，並組織至適當的行銷活動中。 之後，您需要說明接觸點日期，因為您想要它反映的是過去的日期，而不是您推送到[!DNL Dynamics]的日期。 若要覆寫此日期，您可以使用自訂「Buyer Touchpoint日期」欄位來變更日期。 您需要將此專案新增至行銷清單表單。

![](assets/syncing-historical-data-2.png)

因此，您可以為該行銷清單中的所有人整批設定用於接觸點日期的日期。 若要取得更準確的歷史日期，請為相同行銷活動建立多個行銷清單，每個清單都具有自己的接觸點日期。 如果行銷活動具有較短的時間範圍，或許每天建立行銷清單是值得的。 如果行銷活動具有較長的時間範圍，則每週建立行銷清單可能會有意義。

如需同步行銷清單的詳細資訊，請前往： [[!DNL Dynamics] 行銷活動和行銷清單](/help/channel-tracking-and-setup/offline-channels/legacy-processes/dynamics-campaigns-and-marketing-lists.md)

>[!NOTE]
>
>如果您有任何原因導致行銷活動追蹤的線上活動在JavaScript上線日期之後啟用，請務必將&quot;[!UICONTROL Touchpoint End Date]&quot;欄位設定為JS上線的日期。 這是為了避免相同互動出現重複的接觸點。

考量事項：以這種方式新增的線上資料，其精細度原本會低於透過JavaScript進行的線上資料[!DNL Marketo Measure]追蹤。 例如，將不會填入表單URL、登陸頁面、反向連結頁面等欄位。 因此，建議儘可能將行銷活動拆分成每個來源。 以下是理想對應的範例。

| 動態行銷活動型別 | 管道 | 子管道 |
|---|---|---|
| 付費搜尋 — AdWords | 付費搜尋 | AdWords |
| 付費搜尋 — Bing | 付費搜尋 | Bing |
| 付費搜尋 — Yahoo | 付費搜尋 | Yahoo |

如果您無法識別來源，或費時費力無法識別來源，則可以使用對應至「舊式數位」或「歷史網站」之類頻道的促銷活動型別。

**離線：**

若要取得過去離線行銷工作的接觸點，資料必須整理為[!DNL Dynamics]個行銷活動並同步至[!DNL Marketo Measure]。 此程式與目前離線管道相同（透過行銷清單或行銷活動回應同步行銷活動）。 以下是管道對應的範例。

| 動態行銷活動型別 | 管道 | 子管道 |
|---|---|---|
| 活動 — 贊助的會議 | 事件 | 贊助的會議 |
| 活動 — 合作夥伴活動 | 事件 | 合作夥伴活動 |
| 事件 — 託管事件 | 事件 | 託管事件 |
| 網路研討會 — 合作夥伴網路研討會 | 網路研討會 | 合作夥伴網路研討會 |

如果此資料尚未整理到具有正確日期集的行銷活動中，您可以使用「Buyer Touchpoint日期」欄位來反映過去離線活動的正確日期。

