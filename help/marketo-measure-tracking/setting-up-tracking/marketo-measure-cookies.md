---
unique-page-id: 18874590
description: '"[!DNL Marketo Measure] Cookie - [!DNL Marketo Measure]  — 產品檔案」'
title: '"[!DNL Marketo Measure] Cookie」'
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
source-git-commit: 3a13ab3e497652d1975e69280a3d224ac95504aa
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---

# Marketo測量Cookie {#marketo-measure-cookies}

了解各種 [!DNL Marketo Measure] 套用 [!DNL Marketo Measure] JavaScript至您的登錄頁面。 這些資訊在實作期間可能對Web開發團隊有用。

| **Cookie名稱** | **Cookie類型** | **用途** |
|---|---|---|
| _BUID | 第三方，儲存在.bizible.com網域上 | 通用使用者ID，可跨多個用戶端的網域識別相同的使用者。 |
| _biz_uid | 第一方 | 目前網域上的使用者ID。 |
| _biz_sid | 第一方 | 使用者的工作階段ID。 |
| _biz_flagsA | 第一方 | 儲存多項資訊的單一Cookie，例如使用者是否已提交表單、執行跨網域移轉、傳送檢視像素、選擇退出追蹤等。 |
| _biz_nA | 第一方 | 序號 [!DNL Marketo Measure] 包括所有請求，用於內部診斷 |
| _biz_dfsA | 第一方 | 暫時儲存之前發生的表單提交資料 [!DNL bizible.js] 接收設定JS以判斷是否啟用HTTPS上的追蹤表單。 |
| _biz_pendingA | 第一方 | 暫時儲存尚未成功傳送至的分析資料 [!DNL Marketo Measure] 伺服器。 |

如果JavaScript設定期間觸發Web應用程式防火牆(WAF)警告，則使用者可以停用該WAF規則或允許列出Cookie，如下列範例所示：

![](assets/marketo-measure-cookies-1.png)
