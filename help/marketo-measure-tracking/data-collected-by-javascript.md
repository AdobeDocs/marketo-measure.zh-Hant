---
description: JavaScript針對Marketo Measure使用者的收集資料指南
title: JavaScript所收集的資料
feature: Tracking
exl-id: 83814168-9d3e-45ac-b514-df58f0b2e90b
hidefromtoc: true
source-git-commit: 7a4661c8d42214d32e5360dc45d6d880b08ef37c
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 13%

---

# JavaScript所收集的資料 {#data-collected-by-javascript}

瞭解Marketo Measure JavaScript在部署時收集的資料。

**範例要求：**

```text
https://cdn.bizible.com/m/ipv?_biz_r=https%3A%2F%2Fwww.google.com%2F&_biz_h=-1801745101&_biz_u=7059e81415f34f7bbaf40fe32fdcba21&_biz_s=8cbeed&_biz_l=https%3A%2F%2Fwww.zendesk.com%2Fservice%2F&_biz_t=1676483822155&_biz_i=Customer%20service%20software%20for%20the%20best%20customer%20experiences%20%7C%20Zendesk&_biz_n=0&rnd=235938&cdn_o=a&_biz_z=1676483822155
```

<br>

Marketo Measure會為所有型別的請求收集以下常用資料：

| 來源 | 名稱 | 資料類型 | 用途 |
| --- | --- | --- | --- |
| 請求標頭 | IP 位址 | 字串 | 使用者的位置可透過GeoIP查詢推斷。 此資料為暫時性，不會永久儲存。 |
| 請求標頭 | 使用者代理字串 | 字串 | 決定使用者使用的裝置。 |
| 查詢參數 | `_biz_u` | 字串 | Bizible Cookie ID。 |
| 查詢參數 | `_biz_l` | 字串 | 目前頁面URL。 |
| 查詢參數 | `_biz_t` | 長整數 | 活動時間戳記。 |
| 查詢參數 | `_biz_i` | 字串 | 目前頁面標題。 |

除了上述的常見資料外，bizible.js也會根據下列指定的請求型別附加其他資料：

| 請求型別 | 請求路徑 | 其他查詢引數 | 資料類型 | 用途 |
| --- | --- | --- | --- | --- |
| Pageview | `/ipv` | `_biz_r` | 字串 | 反向連結頁面URL。 |
|  |  | `_biz_h` | 字串 | 雜湊使用者端的熒幕解析度。 |
|  |  | `_biz_c` | 字串 | 選用引數。 如果此引數存在，表示租使用者將`bizible.js`設定為在追蹤前等待使用者同意，而且`bizible.js`已收到要追蹤的使用者同意。 |
| 表單提交 | `/frm` | `eMail` | 字串 | 純文字電子郵件地址。 |
| 使用者id對應 | `/u` | `mapType` | 列舉 | 偵測到哪種使用者ID對應`bizible.js` (Marketo Munchkin ID和Adobe ECID) |
|  |  | `mapValue` | 字串 | 上述整合的實際第三方Cookie ID值。 |

>[!NOTE]
>
>Bizible是Marketo Measure的前稱。
