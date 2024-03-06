---
unique-page-id: 18874572
description: 複製記錄和 [!DNL Marketo Measure] - [!DNL Marketo Measure]
title: 複製記錄和 [!DNL Marketo Measure]
exl-id: e340100c-120a-4771-946d-336a1458da4e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 0%

---

# 複製記錄和 [!DNL Marketo Measure] {#duplicate-records-and-marketo-measure}

>[!NOTE]
>
>您可能會看到指定&#39;&#39;的說明[!DNL Marketo Measure]&quot;，但仍在您的CRM中看到「Bizible」。 我們正致力於更新此專案，品牌重塑將很快反映在您的CRM中。

[!DNL Marketo Measure] 比對資料與CRM中相關銷售機會或聯絡人時，會使用電子郵件地址作為唯一識別碼。 時間 [!DNL Marketo Measure] 找到多個電子郵件地址相同的潛在客戶或聯絡人，我們會在所有記錄上顯示相同的資料。 當您報告的潛在客戶或聯絡人時，這會造成影響 [!DNL Marketo Measure] 而且可能會不正確地誇大具有購買者接觸點的不重複使用者人數。

這看起來像什麼 [!DNL Marketo Measure] 報表？

_報表範例： [!DNL Marketo Measure] 具有購買者接觸點的人員。_

![](assets/1-1.png)

您可以看到的 [!DNL Marketo Measure] kelsey@adobe.com的人員ID，表示該電子郵件地址同時存在銷售機會與聯絡人。 在此報表中，已報告2個首次接觸、2個銷售機會建立接觸，以及兩個PostLC互動。 這些重複的記錄會共用接觸點日期和接觸點資訊，因此可以得出結論：儘管是同一個人，但他們是兩個不同的人。

**建議**

* 為了最大化報表回報，我們建議您在CRM中使用重複資料刪除工具，以確保您只會建立全新不重複記錄。 您可以使用行銷自動化工具或安裝在CRM中的個別軟體來完成這項作業。 [!DNL Marketo Measure] 不會自動刪除重複資料記錄，也不會透過我們的軟體提供此服務。
* 另一種選擇是在您識別重複專案時手動合併記錄。 此程式可能曠日持久且乏味，但準確報告的輸出值得投入時間。
