---
unique-page-id: 18874590
description: '"[!DNL Marketo Measure] Cookie - [!DNL Marketo Measure]  — 產品檔案」'
title: "[!DNL Marketo Measure] Cookie"
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---

# Marketo Measure Cookie {#marketo-measure-cookies}

瞭解各種 [!DNL Marketo Measure] 在您套用時載入至您網站的Cookie [!DNL Marketo Measure] JavaScript至您的登陸頁面。 這些資訊在實作期間可能對Web開發團隊很有用。

| **Cookie名稱** | **Cookie型別** | **用途** |
|---|---|---|
| _BUID | 協力廠商，儲存在.bizible.com網域上 | 跨多個使用者端網域識別相同使用者的通用使用者ID。 |
| _biz_uid | 第一方 | 目前網域上的使用者ID。 |
| _biz_sid | 第一方 | 使用者的工作階段ID。 |
| _biz_flagsA | 第一方 | 儲存多個資訊的單一Cookie，例如使用者是否已提交表單、執行跨網域移轉、傳送檢視畫素、選擇退出追蹤等。 |
| _biz_nA | 第一方 | 序號，該序號 [!DNL Marketo Measure] 包含所有要求，以供內部診斷之用 |
| _biz_dfsA | 第一方 | 暫時儲存先前發生的表單提交資料 [!DNL bizible.js] 會接收設定JS，以判斷是否已啟用HTTPS上的追蹤表單。 |
| _biz_pendingA | 第一方 | 暫時儲存尚未成功傳送到的分析資料 [!DNL Marketo Measure] 伺服器尚未安裝。 |

如果在JavaScript設定期間觸發Web應用程式防火牆(WAF)警告，使用者可以停用該WAF規則或允許列出Cookie，如下列範例所示：

![](assets/marketo-measure-cookies-1.png)
