---
unique-page-id: 18874572
description: 複製記錄和 [!DNL Marketo Measure] - [!DNL Marketo Measure]  — 產品檔案
title: 複製記錄和 [!DNL Marketo Measure]
exl-id: e340100c-120a-4771-946d-336a1458da4e
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%

---

# 複製記錄和 [!DNL Marketo Measure] {#duplicate-records-and-marketo-measure}

>[!NOTE]
>
>您可能會看到指定「[!DNL Marketo Measure]「 」，但仍可在CRM中看到「Bizible」。 我們正致力更新該更新，品牌重塑將很快反映在您的CRM中。

[!DNL Marketo Measure] 在將資料與CRM中的相關主管或聯絡人比對時，會利用電子郵件地址作為我們的唯一識別碼。 當 [!DNL Marketo Measure] 找到多個Lead或Contacts具有相同的電子郵件地址，我們會在所有記錄上顯示相同的資料。 當您報告與 [!DNL Marketo Measure] 而且可能會不正確增加具有購買者接觸點的不重複人員數量。

這看起來像什麼 [!DNL Marketo Measure] 報告？

_範例報表： [!DNL Marketo Measure] 具有購買者接觸點的人員。_

![](assets/1-1.png)

您可以在 [!DNL Marketo Measure] kelsey@adobe.com的人員ID是指該電子郵件地址中同時存在潛在客戶和聯繫人。 您會發現，在此報告中報告了2個「首次接觸」報告、2個「銷售機會建立接觸」報告和2個「PostLC交互報告」。 這些重複記錄會共用相同的接觸點日期和接觸點資訊，因此可能得出結論，即使是同一人，他們還是2個不同的人。

**建議**

* 為了在您的報表中獲得最大的回報，我們建議您運用CRM中的去重複化工具，以確保您只建立新的唯一記錄。 您可以使用行銷自動化工具，或在CRM中安裝個別軟體來完成此作業。 [!DNL Marketo Measure] 不會自動刪除重複記錄，也不會通過我們的軟體提供此服務。
* 另一個選項是在您識別重複項目時手動合併記錄。 此過程可能既費時又繁瑣，但準確報告的輸出值得投入時間。
