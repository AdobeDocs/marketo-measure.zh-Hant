---
description: '''[!DNL Marketo Measure] 最終概述 —  [!DNL Marketo Measure]  — 產品檔案`'
title: '''[!DNL Marketo Measure] Ultimate Overview的'
exl-id: fada9479-0671-4698-8043-c67d7977577b
source-git-commit: 59d42e5065ec0db7143208743fd053f5e6c1af7b
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 0%

---

# [!DNL Marketo Measure] 最終概述 {#marketo-measure-ultimate-overview}

[!DNL Marketo Measure] （前身為Bizible）可讓行銷人員深入了解哪些行銷工作最能有效促進收入，並為公司創造最大的投資報酬率。 [!DNL Marketo Measure] 是行銷歸因解決方案，可自動追蹤並報告管道效能，提供哪些管道最能吸引客戶參與，並讓您據此最佳化行銷支出。

[!DNL Marketo Measure Ultimate] 包含其他功能：

* 從幾乎任何資料來源以及多個相同類型的資料來源擷取，匯入所有資料以供歸因之用。
   * 與幾乎任何CRM搭配使用，而不只是Salesforce和Dynamics。
   * 將多個CRM例項和/或MAP例項連結至一個 [!DNL Marketo Measure] 例項。
   * 帶入第三方網路研討會的註冊和參與率資料。

* 透過欄位對應和轉換功能，以極大的彈性轉換資料，以確保正確的資料形狀。

* 透過隨附的資料倉儲，讓外部應用程式可以取得歸因分析，將分析整合到您的工作流程中。 更詳細的結果資料和基於BI的報表，包括SnowflakeData Warehouse，它提供對精細結果資料的存取，以及使用任何BI工具進行分析和報告的功能。

* 與RTCDP（B2B或B2P Edition）整合，為RTCDP客戶提供整合的B2B歸因解決方案，如RTCDP和 [!DNL Marketo Measure] 兩者皆可透過集中式Adobe Experience Platform(AEP)資料運作。

**[!DNL Marketo Measure]第1-3層**

![](assets/marketo-measure-ultimate-overview-1.png)

**[!DNL Marketo Measure Ultimate]**

![](assets/marketo-measure-ultimate-overview-2.png)

## 新增功能 [!DNL Marketo Measure Ultimate] {#whats-new-in-marketo-measure-ultimate}

**透過AEP匯入B2B資料**

行銷人員需透過AEP帶入其B2B資料（例如帳戶、機會、連絡人、銷售機會、行銷活動、行銷活動成員、活動）。 Ultimate不再提供直接CRM和Marketo Engage連線。 行銷人員將持續透過直接連線和追蹤Web活動，提供Ad Platform資料 [!DNL Marketo Measure] javascript。

![](assets/marketo-measure-ultimate-overview-3.png)

**預設貨幣設定**

[!DNL Marketo Measure Ultimate] 會將預設貨幣設為USD，直到使用者變更為止。 設定新的預設貨幣將更新資料，而不會重新處理。 只要所選貨幣顯示為目標ISO代碼，就無需提交轉換率。

![](assets/marketo-measure-ultimate-overview-4.png)

**[!DNL Marketo Measure Ultimate]沙箱**

[!DNL Marketo Measure Ultimate] 執行個體必須先對應至AEP沙箱，才能建立 [!DNL Marketo Measure] AEP中的目的地資料流。

>[!NOTE]
>
>A [!DNL Marketo Measure Ultimate] 生產執行個體必須對應至AEP生產沙箱， [!DNL Marketo Measure Ultimate] 開發人員例項必須對應至AEP開發人員沙箱。

儲存沙箱對應選項後，您目前無法在應用程式中加以變更。 若要變更，請聯絡 [Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

來自指定資料來源的指定實體（例如帳戶）資料只能放入一個資料集。 每個資料集只能包含在一個資料流中。 違反規則會在執行時停止資料流。

![](assets/marketo-measure-ultimate-overview-5.png)

**階段對應**

全部 [!DNL Marketo Measure Ultimate] 規則是資料集專屬的。 必須為所有資料集和所有選定階段建立階段映射規則。

有6個內建階段：

* 銷售線索
* 銷售機會開啟
* 銷售機會轉換
* 機會丟失
* 機會開放
* 機會贏

「遺失」、「贏取」和「已轉換」區段不允許自訂階段。 但是，源資料可以通過更新映射規則來映射到內置的「丟失/原有/已轉換」階段。

只能為「開啟」區段定義自訂階段。
我們不再自動在階段對應中加入CRM階段。

必須用規則映射四個內置階段（其他兩個階段的映射規則為「銷售機會丟失」和「銷售機會轉換」，是可選的）:

* 銷售機會開啟
* 機會丟失
* 機會開放
* 機會贏

規則條件是資料集專屬的。 必須為所有資料集和所有階段建立階段映射規則，但「銷售機會丟失」和「銷售機會轉換」除外。

無法選取漏斗、回歸與自訂模型。 為漏斗、回歸和自訂模型選取所有階段。 我們支援的階段數有限：15個自訂階段，加上6個內建階段。

![](assets/marketo-measure-ultimate-overview-6.png)

促銷活動成員接觸點規則和活動接觸點規則是資料集專屬的。

![](assets/marketo-measure-ultimate-overview-7.png)

![](assets/marketo-measure-ultimate-overview-8.png)

歸因接觸點不會寫入至CRM，因為Ultimate沒有直接CRM連線。

[!DNL Marketo Measure] ABM ML服務（銷售機會帳戶比對和預測性參與分數）不適用於 [!DNL Marketo Measure Ultimate]. 您可以找到RT-CDP B2B版本中免費提供的這類服務。

## 限制 {#limitations}

* 目前，資料轉換規則可使用有限的欄位。
* 現有第1/2/3層用戶沒有遷移路徑。 需要新實作，但我們將協助從現有例項移轉追蹤的Web活動資料。

>[!MORELIKETHIS]
>
>[目標連接](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/set-up-marketo-connection.md){target="_blank"}
