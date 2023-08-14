---
unique-page-id: 27656737
description: 報告行銷支出 —  [!DNL Marketo Measure]  — 產品檔案
title: 報告行銷支出
exl-id: 46b0f81c-acd1-47a5-bf75-6a943edb9009
feature: Reporting, Spend Management
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# 報告行銷支出 {#report-marketing-spend}

## 行銷支出表格 {#marketing-spend-table}

「行銷支出」表格現在會包含新欄，以顯示每個管道、子管道和促銷活動列的貨幣。 此新欄會為所有客戶顯示，即使他們未啟用多重幣別。

表格現在將包含多種不同的貨幣。 如果您需要以單一貨幣取得任何管道、子管道或行銷活動的總和，請參閱行銷支出儀表板。

## 上傳成本 {#upload-costs}

當使用者下載成本檔案時，該檔案還將包含一個新欄，其中每列都具有貨幣。 唯一可接受的貨幣是已設定並儲存在CRM中的貨幣。 您必須知道您貨幣的3個字母縮寫代碼（即USD、CAD、JPY、EUR），如果檔案是以無法辨識的貨幣上傳，檔案上傳將會失敗。

## 廣告整合成本 {#costs-from-ad-integrations}

時間 [!DNL Marketo Measure] 從連線平台匯入成本，例如AdWords、Bing、Facebook或Doubleclick，我們也會使用報告的貨幣。 當顯示在「行銷支出」表格中時，貨幣會與「管道」、「子管道」和「促銷活動」一起顯示。

如果廣告提供者的貨幣與從CRM提取的貨幣不符，您可能會在中看到「混合貨幣」錯誤 [!DNL Marketo Measure Discover] 因為無法轉換該貨幣。 若要解決此問題，您的CRM管理員需要新增未知貨幣的轉換。

## 移轉至轉換的行銷支出 {#migrate-to-converted-marketing-spend}

由於我們的行銷支出歷來僅以單一（美元）貨幣計算，因此需要執行少量工作才能將所有報告支出變更為新貨幣。 即使您的帳戶未啟用多種貨幣，但如果您使用美元以外的單一企業貨幣，您也會想要進行此移轉。

1. 將目前的支出檔案下載至CSV
1. 貨幣欄將顯示&quot;[!UICONTROL USD]「」作為假設貨幣。 您可以手動取代所有出現的&quot;[!UICONTROL USD]&quot;或使用「尋找+取代」變更所有&quot;[!UICONTROL USD]&quot;執行個體變更為您自己的公司貨幣，例如&quot;[!UICONTROL EUR]「或」[!UICONTROL GBP]」為例。
1. 儲存檔案然後將其上傳回 [!DNL Marketo Measure].
1. 您所有報告的成本現在都會顯示為新貨幣。
