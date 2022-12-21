---
unique-page-id: 27656737
description: 報表行銷支出 —  [!DNL Marketo Measure]  — 產品檔案
title: 報表行銷支出
exl-id: 46b0f81c-acd1-47a5-bf75-6a943edb9009
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# 報表行銷支出 {#report-marketing-spend}

## 行銷支出表 {#marketing-spend-table}

「行銷支出」表格現在會包含新欄，以顯示每個管道、子管道和促銷活動列的貨幣。 即使客戶未啟用多種貨幣，新欄仍會顯示給所有客戶。

表格現在將包含多種不同貨幣。 如果您需要以單一貨幣取得任何管道、子管道或促銷活動的總和，請參閱行銷支出控制面板。

## 上傳成本 {#upload-costs}

當使用者下載成本檔案時，檔案也會包含每列使用貨幣的新欄。 唯一可接受的貨幣是已設定並儲存在CRM中的貨幣。 您需要知道貨幣的3個字母縮寫代碼（即USD、CAD、JPY、EUR），如果檔案以無法識別的貨幣上傳，檔案上傳將會失敗。

## 廣告整合的成本 {#costs-from-ad-integrations}

當 [!DNL Marketo Measure] 從連線平台(例如AdWords、Bing、Facebook或Doubleclick)匯入成本，我們也會使用報告的貨幣。 當「行銷支出」表格中顯示貨幣時，該貨幣將與「管道」、「子管道」和「促銷活動」一起顯示。

如果來自廣告提供者的貨幣不符合從CRM提取的貨幣，您可能會在 [!DNL Marketo Measure Discover] 因為我們無法對該貨幣進行轉換。 若要修正此問題，您的CRM管理員需要為未知貨幣新增轉換。

## 移轉至轉換的行銷支出 {#migrate-to-converted-marketing-spend}

由於我們的行銷支出過去只使用單一（美元）貨幣，因此需要少量工作將所有報告支出更改為新貨幣。 即使您的帳戶未啟用多種貨幣，如果您使用美元以外的單一公司貨幣，您也需要進行此移轉。

1. 將目前的「支出」檔案下載為CSV
1. 貨幣欄會顯示「[!UICONTROL USD]」作為假定貨幣。 您可以手動取代「[!UICONTROL USD]」或使用「查找+替換」更改所有「[!UICONTROL USD]」例項至您自己的公司貨幣，例如「[!UICONTROL EUR]&quot;或&quot;[!UICONTROL GBP]」。
1. 儲存檔案，然後將其上傳回 [!DNL Marketo Measure].
1. 您報告的所有成本現在都會顯示為新貨幣。
