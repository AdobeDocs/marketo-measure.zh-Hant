---
unique-page-id: 27656735
description: 總覽 —  [!DNL Marketo Measure]
title: 概觀
exl-id: 2076521c-b579-457c-ab1c-263b1da4dd89
feature: Multi-Currency
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 1%

---

# 概觀 {#overview}

目前，[!DNL Marketo Measure]應用程式僅支援單一貨幣（假設為美元），但我們知道並知道全球有客戶需要報告自己的公司和使用者貨幣。 此功能可讓使用者在檢視[!DNL Marketo Measure]中報告的支出或銷售收入時，於其CRM中使用的相同貨幣之間切換。

## 可用性 {#availability}

第2層及以上。

## 需求 {#requirements}

[!DNL Marketo Measure]將自動從客戶的CRM提取貨幣設定。 不再需要[!DNL Marketo Measure]中的手動設定以符合CRM。 您可以在「CRM」底下的「一般」頁面中找到貨幣設定。

在[!DNL Salesforce]中，客戶必須啟用「啟用多種貨幣」。 或者，客戶也可以選取「是，我要啟用「進階幣別管理」。

在Dynamics中，客戶可以在其「設定」中為多種貨幣設定靜態匯率。 Dynamics中沒有「進階貨幣管理」的概念。

## 條款 {#terms}

| **字詞** | 說明 |
|---|---|
| **進階貨幣** | 客戶已啟用「進階幣別管理」與「多重幣別」，這表示他們可以在不同的期間有不同的兌換率。 |
| **公司貨幣** | 這些是組織在CRM中列出並宣告的各種貨幣，全都採用轉換率。 [!DNL Marketo Measure]將匯入這些值，並讓我們的產品內的使用者可以使用這些貨幣。 |
| **貨幣地區設定** | 組織所用的單一貨幣，在公司資訊頁面上設定。 |
| **當地貨幣（或使用者貨幣）** | 在使用者設定檔中為單一使用者設定的貨幣，以便他們能夠檢視任何金額的當地貨幣。 組織必須先宣告並設定貨幣，使用者才能選取其當地貨幣。 |
| **單一貨幣** | 用於未在CRM中使用多種貨幣，但其組織以不同貨幣執行的客戶，因此他們具有「貨幣地區設定」。 這仍然是組織的單一貨幣，但沒有任何轉換。 |
| **簡單貨幣** | 客戶已啟用「多幣別」，但各幣別的靜態轉換率相同。 |
