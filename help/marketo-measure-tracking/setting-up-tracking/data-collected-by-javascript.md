---
description: JavaScript收集的資料 —  [!DNL Marketo Measure]  — 產品檔案
title: JavaScript收集的資料
feature: Tracking
source-git-commit: 2be08b96fb9f6d027e80751db64f16a7f2893764
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 6%

---

# JavaScript收集的資料 {#data-collected-by-javascript}

瞭解Marketo Measure JavaScript在部署時收集的資料。

**範例要求：**

```
https://cdn.bizible.com/m/ipv?_biz_r=https%3A%2F%2Fwww.google.com%2F&_biz_h=-1801745101&_biz_u=7059e81415f34f7bbaf40fe32fdcba21&_biz_s=8cbeed&_biz_l=https%3A%2F%2Fwww.zendesk.com%2Fservice%2F&_biz_t=1676483822155&_biz_i=Customer%20service%20software%20for%20the%20best%20customer%20experiences%20%7C%20Zendesk&_biz_n=0&rnd=235938&cdn_o=a&_biz_z=1676483822155
```

<br>

Marketo Measure會為所有型別的請求收集以下常用資料：

<table>
<thead>
  <tr>
    <th>來源</th>
    <th>名稱</th>
    <th>資料類型</th>
    <th>用途</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>請求標頭</td>
    <td>IP位址</td>
    <td>字串</td>
    <td>使用者的位置可透過GeoIP查詢推斷。 此資料為暫時性，不會永久儲存。</td>
  </tr>
  <tr>
    <td>請求標頭</td>
    <td>使用者代理字串</td>
    <td>字串</td>
    <td>決定使用者使用的裝置。</td>
  </tr>
  <tr>
    <td>查詢引數</td>
    <td>_biz_u</td>
    <td>字串</td>
    <td>Bizible Cookie ID</td>
  </tr>
  <tr>
    <td>查詢引數</td>
    <td>_biz_l</td>
    <td>字串</td>
    <td>目前頁面URL</td>
  </tr>
  <tr>
    <td>查詢引數</td>
    <td>_biz_t</td>
    <td>長</td>
    <td>活動時間戳記</td>
  </tr>
  <tr>
    <td>查詢引數</td>
    <td>_biz_i</td>
    <td>字串</td>
    <td>目前頁面標題</td>
  </tr>
</tbody>
</table>

除了上述的常見資料外，bizible.js也會根據下列指定的請求型別附加其他資料：

<table>
<thead>
  <tr>
    <th>請求型別</th>
    <th>請求路徑</th>
    <th>其他查詢引數</th>
    <th>資料類型</th>
    <th>用途</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>頁面檢視</td>
    <td>/ipv</td>
    <td>_biz_r</td>
    <td>字串</td>
    <td>反向連結頁面URL。</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>_biz_h</td>
    <td>字串</td>
    <td>雜湊使用者端的熒幕解析度。</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>_biz_c</td>
    <td>字串</td>
    <td>選用引數。 如果此引數存在，表示租使用者將bizible.js設定為在追蹤前等待使用者同意，而bizible.js已收到要追蹤的使用者同意。</td>
  </tr>
  <tr>
    <td>表單提交</td>
    <td>/frm</td>
    <td>電子郵件</td>
    <td>字串</td>
    <td>純文字電子郵件地址。</td>
  </tr>
  <tr>
    <td>使用者id對應</td>
    <td>/u</td>
    <td>mapType</td>
    <td>列舉</td>
    <td>偵測到對應bizible.js的使用者ID種類(Marketo munchkin ID和AdobeECID)</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>地圖值</td>
    <td>字串</td>
    <td>上述整合的實際第三方Cookie ID值。</td>
  </tr>
</tbody>
</table>

>[!NOTE]
>
>Bizible是Marketo Measure的前稱。
