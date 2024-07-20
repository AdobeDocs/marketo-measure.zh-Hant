---
unique-page-id: 27656737
description: 報告行銷支出 —  [!DNL Marketo Measure]
title: 報告行銷支出
exl-id: 46b0f81c-acd1-47a5-bf75-6a943edb9009
feature: Reporting, Spend Management
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 0%

---

# 報告行銷支出 {#report-marketing-spend}

## 行銷支出表格 {#marketing-spend-table}

「行銷支出」表格包含新欄，用以顯示每個管道、子管道和促銷活動列的貨幣。 此新欄會為所有客戶顯示，即使他們未啟用「多幣別」。

此表格包含多種不同的貨幣。 請參閱行銷支出控制面板，以單一貨幣取得任何管道、子管道或行銷活動的總和。

## 上傳成本 {#upload-costs}

當使用者下載成本檔案時，該檔案還將包含一個新欄，其中每列都具有貨幣。 唯一可接受的貨幣是已設定並儲存在CRM中的貨幣。 您必須知道您貨幣的3個字母縮寫代碼(USD、CAD、JPY、EUR)，如果檔案是以無法辨識的貨幣上傳，則檔案上傳會失敗。

## 廣告整合成本 {#costs-from-ad-integrations}

當[!DNL Marketo Measure]從AdWords、Bing、Facebook或Doubleclick等連線平台匯入成本時，我們也會使用報告的貨幣。 貨幣在「行銷支出」表格中顯示時，會與「管道」、「子管道」和「促銷活動」一起顯示。

如果廣告提供者的貨幣與從CRM提取的貨幣不符，您可能會在[!DNL Marketo Measure Discover]中看到「混合貨幣」錯誤。 若要解決此問題，CRM管理員必須為未知貨幣新增轉換。

## 移轉至轉換的行銷支出 {#migrate-to-converted-marketing-spend}

由於行銷支出歷來只使用單一（美元）貨幣，因此只需要少量工作即可將所有報告的支出變更為新貨幣。 即使您的帳戶未啟用多種貨幣，但如果您使用美元以外的單一企業貨幣，則應進行此移轉。

1. 將目前的支出檔案下載至CSV
1. 貨幣欄顯示&quot;[!UICONTROL USD]&quot;為假設貨幣。 您可以手動取代所有出現的&quot;[!UICONTROL USD]&quot;，或使用「尋找+取代」將所有&quot;[!UICONTROL USD]&quot;執行個體變更為您自己的公司貨幣，例如&quot;[!UICONTROL EUR]&quot;或&quot;[!UICONTROL GBP]&quot;。
1. 儲存檔案然後將其上傳回[!DNL Marketo Measure]。
1. 您所有報告的成本現在都會顯示為新貨幣。
