---
description: 最新發行說明 —  [!DNL Marketo Measure]
title: 最新發行說明
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: db71cbfaf7deb5b724ac4babc38e835c04fadac7
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 0%

---

# 發行說明：2024年 {#release-notes-2024}

請參閱下文，瞭解2024年發行版本的所有新功能和更新功能。

## 第2季發行 {#q2-release}

<p>

**第三方Cookie淘汰後淘汰Marketo Measure功能**

為回應日益增加的隱私權顧慮，第三方Cookie正在逐步淘汰，Google Chrome將於2024年第三季度截止日期發出終止訊號。 Marketo Measure將淘汰依賴第三方Cookie的某些功能，尤其是跨網域追蹤和瀏覽歸因，這些依賴於Google/DoubleClick曝光數Cookie。 此變更不會影響其他Marketo Measure功能或第一方Cookie的使用。 根據Google的時間表，這些功能預計在6月1日前淘汰，不過客戶仍然可以存取在此日期之前收集的資料。

* [在Marketo Measure中適應第三方Cookie淘汰](https://nation.marketo.com/t5/employee-blogs/adapting-to-third-party-cookie-deprecation-in-marketo-measure/ba-p/345110){target="_blank"}
* [Marketo Measure Cookie](/help/marketo-measure-tracking/setting-up-tracking/marketo-measure-cookies.md){target="_blank"}

**分階段推出我們的增強錯誤處理**

我們將分階段推出匯出作業的增強錯誤處理功能，從許可權錯誤的立即應用程式內脈衝通知開始，並在4月25日轉換為新的方法，讓匯出作業在錯誤點暫停。 這項變更旨在改善資料完整性和可見度，確保使用者有更流暢、更可靠的資料管理流程。 為確保順利轉換並將營運中斷降至最低，我們分兩個階段實作這些變更：

* Pulse通知的立即可用性：在匯出作業期間，您將收到有關許可權錯誤的應用程式內脈衝通知。 這不會中斷您的匯出，但可協助您瞭解錯誤，而不會影響您目前的工作。
* 於4月25日實施作業暫停：從4月25日開始，如果我們的系統在匯出作業期間遇到許可權錯誤，則會暫停作業以確保不會略過任何資料。 您會收到任何問題的通知，許可權修正後，匯出作業將可從中斷處順利恢復。

_這很重要的原因_

增強資料完整性和前瞻性您的整合：我們會在第一次出現問題跡象時停止工作，以防止資料遺失並確保準確性。 這有助於快速解決問題，改善資料匯出品質和系統可靠性。

立即可見：引入脈衝通知可讓您對許可權錯誤做出即時回應，避免對作業造成潛在影響。

_支援您的轉變_

為協助您適應這項變更， [我們已建立檔案](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"} 提供清晰的錯誤說明和完整的疑難排解步驟。

<br>
**LinkedIn整合所需動作**

linkedIn最近發佈了其Lead Sync API的更新版本。 請在5月20日前重新驗證Marketo Measure執行個體中的LinkedIn連線，以避免任何服務中斷。

