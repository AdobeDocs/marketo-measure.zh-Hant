---
description: '[!DNL Marketo Measure] Cookie - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Cookie'
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
feature: Tracking
hidefromtoc: true
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 10%

---

# Marketo Measure Cookie {#marketo-measure-cookies}

瞭解當您將[!DNL Marketo Measure] JavaScript套用至登陸頁面時，載入至您網站的各種[!DNL Marketo Measure] Cookie。 這些資訊在實作期間可能對Web開發團隊很有用。

>[!IMPORTANT]
>
>基於隱私權疑慮，第三方Cookie即將推出。 Google Chrome於2024年第3季度宣佈淘汰第三方Cookie，實際標誌著此追蹤形式的結束。 因此，Adobe將淘汰依賴第三方Cookie的Marketo Measure功能；特別是跨網域追蹤和瀏覽歸因，後者使用Google/DoubleClick曝光數Cookie。 Marketo Measure的其他功能將不會受到影響。 第一方Cookie使用量也不受影響。 根據Google排程，上述兩個功能的預計淘汰日期為2024年6月1日。 在此日期之前收集的相關資料仍可供Adobe客戶使用。

| Cookie 名稱 | Cookie型別 | 用途 | 到期日 | 是否已設定安全旗標？ | 是否設定僅HTTP旗標？ | Cookie Setter |
| --- | --- | --- | --- | --- | --- | --- |
| `_biz_uid` | 第一方 | 唯一識別目前網域上的使用者。 | 1 年 | 無 | 無 | `bizible.js` |
| `_biz_nA` | 第一方 | Marketo Measure包含用於內部診斷用途之所有請求的序號。 | 1 年 | 無 | 無 | `bizible.js` |
| `_biz_flagsA` | 第一方 | 此Cookie會儲存各種使用者資訊，例如，表單提交、跨網域移轉、閱覽畫素、追蹤選擇退出狀態等。 | 1 年 | 無 | 無 | `bizible.js` |
| `_biz_pendingA` | 第一方 | 暫時儲存分析資料，直到成功傳送至Marketo Measure伺服器為止。 | 1 年 | 無 | 無 | `bizible.js` |
| `_biz_ABTestA` | 第一方 | 來自Optimizely和Visual Web Optimizer ABTests已回報資料的檢查總和清單，導致`bizible.js`無法重新傳送所收集的資料。 | 1 年 | 無 | 無 | `bizible.js` |
| `_biz_EventA` | 第一方 | Bizible事件所報告的檢查總和清單，用於防止`bizible.js`重新傳送所收集的資料。 | 1 年 | 無 | 無 | `bizible.js` |
| `_biz_su` | 第一方 | 跨多個網域識別使用者的通用使用者ID，僅適用於具有略過ITP限制整合的租使用者。 | 1 年 | 是 | 無 | Edgecast |
| `_BUID` | 第三方，網域=.bizible.com | 跨多個網域識別使用者的通用使用者ID。 | 1 年 | 是 | 無 | Edgecast |
| `_BUID` | 第三方，網域=.bizibly.com | 租使用者網域上的Marketo Measure Cookie ID與其Doubleclick曝光度Cookie ID之間的對應。 | 1 年 | 是 | 無 | Edgecast |

如果在JavaScript設定期間觸發Web應用程式防火牆(WAF)警告，使用者可以停用該WAF規則，或允許列出Cookie，如下列範例所示：

![如果在JavaScript期間觸發Web應用程式防火牆(WAF)警告](assets/adding-script-1.png)
