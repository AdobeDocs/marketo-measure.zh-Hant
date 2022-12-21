---
description: 活動歸因最佳實務 —  [!DNL Marketo Measure]  — 產品檔案
title: 活動歸因最佳實務
exl-id: 66fb9f47-3912-40a6-b112-3efca789f321
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# 活動歸因最佳實務 {#best-practices-for-activities-attribution}

## 總覽 {#overview}

此 [!DNL Marketo Measure] 活動歸因功能可讓客戶從CRM中的活動記錄建立接觸點。 此建立接觸點的方法具有彈性，可讓您根據「任務」或「事件」欄位建立規則，以通知 [!DNL Marketo Measure] 哪些活動會記錄其應從產生接觸點，並隨後獲得歸因評分。

此功能最常見的使用案例是建立規則，將銷售互動整合至您的購買者接觸點資料中。 活動歸因可讓您將銷售和行銷資料統一至一個歷程。

對許多人 [!DNL Salesforce] 例項中，活動物件可容納多種記錄類型，因此，請務必針對您嘗試轉譯為接觸點的記錄，量身打造您的活動規則。 下列最佳實務有助於確保您透過活動歸因建立有意義且有價值的接觸點。

## 最佳實務 {#best-practice}

無論您是第一次定義活動規則，還是只是檢閱先前已設定的活動規則，請牢記下列最佳實務。

* 開始簡單
   * 識別您要併入您的 [!DNL Marketo Measure] 接著，當您熟悉這些接觸點的歸因方式時，請新增更多類型
   * 如前所述，此功能的主要使用案例是建立接觸點，以追蹤您的銷售開發團隊的成效，尤其是傳出電話和傳出電子郵件

>[!NOTE]
>
>是 **NOT** 建議跟蹤在建立Opportunity後發生的銷售活動，因為跟蹤銷售執行官流程將不提供太多深入分析。 目標是跟蹤銷售影響和營銷影響，主要是在開發新的機會/管道生成

* 請勿使用公式欄位來定義規則
* 建立特定且精確的規則
   * 您希望建立活動接觸點的臨界值與表單填入或促銷活動成員資格相同（或類似），即（回復傳出電子郵件或完成的電話對話）
* 一律驗證 [!DNL Salesforce] 儲存和處理之前
   * 在「工作與事件」報表類型中複製您的活動規則，可讓您清楚了解將從該規則建立的接觸點確切數量
* 與您的銷售運營團隊合作
   * 請加入與活動記錄或銷售啟用工具最接近的團隊，可確保您使用正確的欄位來定義規則

## 維護最佳實務 {#best-practice-for-maintenance}

每年至少檢閱兩次活動歸因規則，可確保活動接觸點準確且為最新狀態。 您想要確定這些規則不會建立會稀釋「購買者歸因」資料的不想要的接觸點。 檢閱規則的定義方式，可協助您和您的團隊對活動歸因及其在 [!DNL Marketo Measure] 資料。

其他可能觸發審核的原因包括……

* 行銷團隊的營業額
* 用於定義活動記錄的欄位變更
* 變更或更新您的銷售輔助工具

>[!MORELIKETHIS]
>
>* [活動歸因](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [銷售活動歸因常見問題集](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)


