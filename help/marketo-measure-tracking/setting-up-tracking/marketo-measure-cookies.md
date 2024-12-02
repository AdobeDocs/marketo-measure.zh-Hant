---
unique-page-id: 18874590
description: '[!DNL Marketo Measure] Cookie - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Cookie'
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 9%

---

# Marketo Measure Cookie {#marketo-measure-cookies}

瞭解當您將[!DNL Marketo Measure] JavaScript套用至登陸頁面時，載入至您網站的各種[!DNL Marketo Measure] Cookie。 這些資訊在實作期間可能對Web開發團隊很有用。

>[!IMPORTANT]
>
>基於隱私權疑慮，第三方Cookie即將推出。 Google Chrome於2024年第3季度宣佈淘汰第三方Cookie，實際標誌著此追蹤形式的結束。 因此，Adobe淘汰依賴第三方Cookie的Marketo Measure功能；特別是跨網域追蹤和瀏覽歸因，後者使用Google/DoubleClick曝光數Cookie。 Marketo Measure的其他功能將不會受到影響。 第一方Cookie使用量也不受影響。 根據Google排程，上述兩個功能的預計淘汰日期為2024年6月1日。 在此日期之前收集的相關資料仍可供Adobe客戶使用。

<table>
<thead>
  <tr>
    <th>Cookie 名稱</th>
    <th>Cookie型別</th>
    <th>用途</th>
    <th>到期日</th>
    <th>是否已設定安全旗標？<br></th>
    <th>是否設定僅HTTP旗標？</th>
    <th>Cookie Setter</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>_biz_uid</td>
    <td>第一方</td>
    <td>唯一識別目前網域上的使用者。</td>
    <td>1 年</td>
    <td>無</td>
    <td>無</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_nA</td>
    <td>第一方</td>
    <td>Marketo Measure包含用於內部診斷用途之所有請求的序號。</td>
    <td>1 年</td>
    <td>無</td>
    <td>無</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_flagsA</td>
    <td>第一方</td>
    <td>此Cookie會儲存各種使用者資訊，例如，表單提交、跨網域移轉、閱覽畫素、追蹤選擇退出狀態等。</td>
    <td>1 年</td>
    <td>無</td>
    <td>無</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_pendingA</td>
    <td>第一方</td>
    <td>暫時儲存分析資料，直到成功傳送至Marketo Measure伺服器為止。</td>
    <td>1 年</td>
    <td>無</td>
    <td>無</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_ABTestA</td>
    <td>第一方</td>
    <td>來自Optimizely和Visual Web Optimizer ABTests已報告資料的檢查加總清單，可防止bizible.js重新傳送所收集的資料。</td>
    <td>1 年</td>
    <td>無</td>
    <td>無</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_EventA</td>
    <td>第一方</td>
    <td>Bizible Events為了防止bizible.js重新傳送所收集的資料而報告的總和檢查碼清單。</td>
    <td>1 年</td>
    <td>無</td>
    <td>無</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_su</td>
    <td>第一方</td>
    <td>跨多個網域識別使用者的通用使用者ID，僅適用於具有略過ITP限制整合的租使用者。</td>
    <td>1 年</td>
    <td>是</td>
    <td>無</td>
    <td>Edgecast</td>
  </tr>
  <tr>
    <td>_BUID</td>
    <td>協力廠商，網域=。<a href="https://business.adobe.com/products/marketo/bizible.html">bizible.com</a></td>
    <td>跨多個網域識別使用者的通用使用者ID。</td>
    <td>1 年</td>
    <td>是</td>
    <td>無</td>
    <td>Edgecast</td>
  </tr>
  <tr>
    <td>_BUID</td>
    <td>協力廠商，網域=。<a href="http://bizibly.com/">bizibly.com</a></td>
    <td>租使用者網域上的Marketo Measure Cookie ID與其Doubleclick曝光度Cookie ID之間的對應。</td>
    <td>1 年</td>
    <td>是</td>
    <td>無</td>
    <td>Edgecast</td>
  </tr>
</tbody>
</table>

如果在JavaScript設定期間觸發Web應用程式防火牆(WAF)警告，使用者可以停用該WAF規則，或允許列出Cookie，如下列範例所示：

![](assets/marketo-measure-cookies-1.png)
