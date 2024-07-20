---
description: 活動歸因的最佳實務 —  [!DNL Marketo Measure]
title: 活動歸因的最佳實務
exl-id: 66fb9f47-3912-40a6-b112-3efca789f321
feature: Attribution
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 0%

---

# 活動歸因的最佳實務 {#best-practices-for-activities-attribution}

## 概觀 {#overview}

[!DNL Marketo Measure]活動歸因功能可讓客戶從您CRM中的活動記錄建立接觸點。 這種建立接觸點的方法是有彈性的。 它可讓您根據「任務」或「事件」欄位建立規則，以通知[!DNL Marketo Measure]它應該從哪些活動記錄產生接觸點，從而接收歸因評分。

此功能最常見的使用案例是製作規則，將銷售互動整合到您的購買者接觸點資料中。 活動歸因可讓您將銷售和行銷資料整合到一個歷程中。

對於許多[!DNL Salesforce]執行個體，活動物件可以存放各種記錄型別，因此重要的是，您的活動規則要針對您嘗試轉譯為接觸點的記錄進行特定和客製化。 以下最佳實務可協助您透過活動歸因建立有意義且有價值的接觸點。

## 最佳實務 {#best-practice}

無論是第一次定義活動規則，還是檢閱先前已設定的活動規則，請記住以下最佳實務。

* 開始簡單
   * 識別您想要整合至[!DNL Marketo Measure]資料中的幾項關鍵活動型別，然後在您瞭解這些接觸點的歸因方式後新增更多型別
   * 如前所述，此功能的主要使用案例是建立追蹤銷售開發團隊功效的接觸點，尤其是「傳出電話」和「傳出電子郵件」

>[!NOTE]
>
>**不**&#x200B;建議追蹤在建立Opportunity之後發生的銷售活動，因為追蹤銷售主管程式不會提供太多深入分析。 目標為追蹤銷售影響與行銷影響，主要是開發新的商機/管道開發

* 請勿使用公式欄位來定義規則
* 建立明確且精確的規則
   * 建立活動接觸點的臨界值應與表單填寫或行銷活動成員資格相同（或類似）：回覆傳出電子郵件或完成的電話交談
* 儲存與處理前，一律驗證[!DNL Salesforce]中的新規則
   * 在「任務與事件」報表型別中複製活動規則，可讓您清楚瞭解該規則中有多少接觸點
* 與您的Sales Opp團隊合作
   * 引進與您的活動記錄或銷售啟用工具最接近的團隊，將確保您使用正確的欄位來定義規則

## 維護最佳實務 {#best-practice-for-maintenance}

每年至少檢閱兩次活動歸因規則，以確保您的活動接觸點準確且為最新狀態。 您想要確保這些規則不會建立稀釋購買者歸因資料的不需要的接觸點。 檢閱規則的定義方式將有助於您和您的團隊對您的活動歸因及其在您[!DNL Marketo Measure]資料中的角色充滿信心。

其他可能觸發檢閱活動規則的原因包括……

* 您行銷團隊中的營業額
* 用於定義活動記錄的欄位變更
* 銷售啟用工具的變更或更新

>[!MORELIKETHIS]
>
>* [活動歸因](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [銷售活動歸因常見問題集](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)
