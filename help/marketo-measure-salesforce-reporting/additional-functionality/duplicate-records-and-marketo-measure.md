---
unique-page-id: 18874572
description: 重複的記錄和 [!DNL Marketo Measure] - [!DNL Marketo Measure]
title: 重複的記錄和 [!DNL Marketo Measure]
exl-id: e340100c-120a-4771-946d-336a1458da4e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 0%

---

# 重複的記錄和[!DNL Marketo Measure] {#duplicate-records-and-marketo-measure}

>[!NOTE]
>
>您可能會在檔案中看到指定&quot;[!DNL Marketo Measure]&quot;的說明，但在您的CRM中仍會看到&quot;Bizible&quot;。 我們正致力於更新此專案，品牌重塑將很快反映在您的CRM中。

將資料與CRM中的相關銷售機會或連絡人比對時，[!DNL Marketo Measure]會使用電子郵件地址做為唯一識別碼。 當[!DNL Marketo Measure]找到多個具有相同電子郵件地址的銷售機會或聯絡人時，我們會在所有記錄上呈現相同的資料。 當您報告具有[!DNL Marketo Measure]的銷售機會或聯絡人時，這會造成影響，而且可能會錯誤地誇大具有購買者接觸點的獨特人數。

這在[!DNL Marketo Measure]報表中看起來像什麼？

_範例報告： [!DNL Marketo Measure]具有購買者接觸點的人員。_

![](assets/1-1.png)

您可以在kelsey@adobe.com的[!DNL Marketo Measure]人員ID中看到該電子郵件地址同時存在潛在客戶和聯絡人。 在此報表中，已報告2個首次接觸、2個銷售機會建立接觸，以及兩個PostLC互動。 這些重複的記錄會共用接觸點日期和接觸點資訊，因此可以得出結論：儘管是同一個人，但他們是兩個不同的人。

**建議**

* 為了最大化報表回報，我們建議您在CRM中使用重複資料刪除工具，以確保您只會建立全新不重複記錄。 您可以使用行銷自動化工具或安裝在CRM中的個別軟體來完成這項作業。 [!DNL Marketo Measure]不會自動刪除重複資料記錄，且不會透過我們的軟體提供此服務。
* 另一種選擇是在您識別重複專案時手動合併記錄。 此程式可能曠日持久且乏味，但準確報告的輸出值得投入時間。
