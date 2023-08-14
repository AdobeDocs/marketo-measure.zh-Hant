---
description: 活動歸因的最佳實務 —  [!DNL Marketo Measure]  — 產品檔案
title: 活動歸因的最佳實務
exl-id: 66fb9f47-3912-40a6-b112-3efca789f321
feature: Attribution
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# 活動歸因的最佳實務 {#best-practices-for-activities-attribution}

## 概觀 {#overview}

此 [!DNL Marketo Measure] 活動歸因功能可讓客戶從CRM中的活動記錄建立接觸點。 這種建立接觸點的方法是靈活的，因為它允許您根據任務或事件欄位建立規則以通知 [!DNL Marketo Measure] 哪一個活動會記錄它應該從哪個產生接觸點，以及之後應該從哪個活動取得歸因評分。

此功能最常見的使用案例是製作規則，將銷售互動整合到您的購買者接觸點資料中。 活動歸因可讓您將銷售和行銷資料整合到一個歷程中。

針對許多 [!DNL Salesforce] 例項中，活動物件可存放各種記錄型別，因此您的活動規則必須是針對您嘗試轉換為接觸點的記錄而量身打造的特定規則，這點很重要。 下列最佳實務有助於確保您透過活動歸因建立有意義且有價值的接觸點。

## 最佳實務 {#best-practice}

無論是第一次定義活動規則，還是檢閱先前已設定的活動規則，請記住以下最佳實務。

* 開始簡單
   * 找出您想要併入活動中的幾個關鍵型別 [!DNL Marketo Measure] 資料，然後在您熟悉這些接觸點的歸因方式時新增更多型別
   * 如前所述，此功能的主要使用案例是建立追蹤銷售開發團隊功效的接觸點，尤其是「傳出電話」和「傳出電子郵件」

>[!NOTE]
>
>它是 **NOT** 建議追蹤在建立Opportunity之後發生的銷售活動，因為追蹤銷售主管程式不會提供太多深入分析。 目標為追蹤銷售影響與行銷影響，主要是開發新的商機/管道開發

* 請勿使用公式欄位來定義規則
* 建立明確且精確的規則
   * 您希望建立活動接觸點的臨界值與表單填寫或行銷活動成員資格相同（或類似），例如（回覆傳出電子郵件或已完成的電話交談）
* 一律驗證中的新規則 [!DNL Salesforce] 儲存與處理前
   * 在「任務與事件」報告型別中複製活動規則，可讓您清楚瞭解將會根據該規則建立多少接觸點
* 與您的Sales Opp團隊合作
   * 請團隊中最接近您的活動記錄或銷售啟用工具，以確保您使用正確的欄位來定義規則

## 維護最佳實務 {#best-practice-for-maintenance}

每年至少檢閱兩次活動歸因規則，可確保您的活動接觸點準確且為最新狀態。 您想要確定這些規則不會建立稀釋您的購買者歸因資料的不想要的接觸點。 檢閱規則的定義方式，有助於您和團隊對活動歸因及其在中的角色充滿信心 [!DNL Marketo Measure] 資料。

其他可能觸發檢閱活動規則的原因包括……

* 您行銷團隊中的營業額
* 用於定義活動記錄的欄位變更
* 銷售啟用工具的變更或更新

>[!MORELIKETHIS]
>
>* [活動歸因](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [銷售活動歸因常見問題集](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)

