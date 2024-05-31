---
description: 最新發行說明 —  [!DNL Marketo Measure]
title: 最新發行說明
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: 69b937f53f8ba3e449f7b13fb92d169dadc14c17
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 0%

---

# 發行說明：2024年 {#release-notes-2024}

請參閱下文，瞭解2024年發行版本的所有新功能和更新功能。

## 第3季發行 {#q3-release}

<p>

**提醒： Salesforce欄位淘汰 — 6月14日**

如去年所宣佈，我們將逐步淘汰對Lead/Contact物件的匯出工作，以簡化整合，並免除匯出至Salesforce標準物件的需要。 您可以依照下列步驟，從接觸點物件取得相同的資料 [在此處記錄](/help/release-notes/previous-releases/2023.md#deprecations). 我們也會分享有關建立工作流程的檔案，以將此資料新增至銷售機會/聯絡人物件。 淘汰將於2024年6月14日生效。

此變更將帶來兩個主要優點：

* **降低Salesforce API成本**：客戶可望將Salesforce API成本降低約10%。
* **簡化的整合**：匯出作業中與這些流程相關的錯誤數量最高。 移除這些元素將大幅簡化我們的整合。

**已歸因的機會儀表板**

我們很高興為您介紹新的 [已歸因的機會儀表板](/help/marketo-measure-discover-ui/dashboards/attributed-opportunity-dashboard.md)，可讓您全面瞭解行銷工作如何對新興和成熟的管道商機有所貢獻。 此儀表板可讓您深入瞭解歸因於您策略的每個開啟和關閉商機的詳細資訊，並靈活地按商機階段篩選。 它提供哪些管道、子管道或行銷活動在歸因商機金額方面排名最高的深入分析，並顯示歸因商機金額總計以及歸因的未完成與已結束商機計數。

**適用於Marketo Measure Ultimate的Marketo EngageCookie同步**

Marketo Measure Ultimate現在提供Marketo EngageCookie同步功能。 若要使用此功能：

1. 在「AEP綱要」頁面上，編輯「B2B人員」綱要，並新增欄位群組「Marketo Engage人員詳細資訊」。
1. 將資料內嵌至MMU時，請將欄位群組中的Cookie ID欄位對應至Marketo Engage中的Cookie欄位。

<p>

## 第2季發行 {#q2-release}

<p>

**第三方Cookie淘汰後淘汰Marketo Measure功能**

為回應日益增加的隱私權顧慮，第三方Cookie正在逐步淘汰，Google Chrome將於2024年第三季度截止日期發出終止訊號。 Marketo Measure將淘汰依賴第三方Cookie的某些功能，尤其是跨網域追蹤和瀏覽歸因，這些依賴於Google/DoubleClick曝光數Cookie。 此變更不會影響其他Marketo Measure功能或第一方Cookie的使用。 根據Google的時間表，這些功能預計在6月1日前淘汰，不過客戶仍然可以存取在此日期之前收集的資料。

* [在Marketo Measure中適應第三方Cookie淘汰](https://nation.marketo.com/t5/employee-blogs/adapting-to-third-party-cookie-deprecation-in-marketo-measure/ba-p/345110){target="_blank"}
* [Marketo Measure Cookie](/help/marketo-measure-tracking/setting-up-tracking/marketo-measure-cookies.md){target="_blank"}

**分階段推出我們的增強錯誤處理**

我們將分階段推出匯出工作的增強錯誤處理功能，從許可權錯誤的立即應用程式內脈衝通知開始，並轉換到匯出工作將在錯誤點暫停的新方式。 這項變更旨在改善資料完整性和可見度，確保使用者有更流暢、更可靠的資料管理流程。 為確保順利轉換並將營運中斷降至最低，我們分兩個階段實作這些變更：

* Pulse通知的立即可用性：在匯出作業期間，您將收到有關許可權錯誤的應用程式內脈衝通知。 這不會中斷您的匯出，但可協助您瞭解錯誤，而不會影響您目前的工作。
* 於4月25日實施工作暫停： **已延遲**  — 考慮Marketo Measure使用者的意見回饋後，我們決定延遲實施在錯誤點暫停匯出工作（原定於4月25日）。 我們瞭解暫停工作可能不是最有效率的方法。 我們致力於尋找更好的解決方案，以維持資料完整性並儘量減少中斷。 在可確保解決方案更符合使用者的需求之前，我們不會對目前的系統進行任何變更。

_這很重要的原因_

增強資料完整性和前瞻性您的整合：我們會在第一次出現問題跡象時停止工作，以防止資料遺失並確保準確性。 這有助於快速解決問題，改善資料匯出品質和系統可靠性。

立即可見：引入脈衝通知可讓您對許可權錯誤做出即時回應，避免對作業造成潛在影響。

_支援您的轉變_

為協助您適應這項變更， [我們已建立檔案](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"} 提供清晰的錯誤說明和完整的疑難排解步驟。

<br>

**linkedIn整合所需動作**

linkedIn最近發佈了其Lead Sync API的更新版本。 請在5月20日前重新驗證Marketo Measure執行個體中的LinkedIn連線，以避免任何服務中斷。

