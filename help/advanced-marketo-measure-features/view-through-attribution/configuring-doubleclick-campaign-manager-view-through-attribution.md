---
unique-page-id: 18874781
description: 透過歸因設定Doubleclick Campaign Manager檢視 —  [!DNL Marketo Measure]
title: 透過歸因設定Doubleclick Campaign Manager檢視
exl-id: 2cc6c2cd-afb7-4052-b18b-9ad0bf16a9fa
feature: Attribution
source-git-commit: 48962b999fdd16fe96d18708ec301e64a39bc76e
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 0%

---

# 透過歸因設定Doubleclick Campaign Manager檢視 {#configuring-doubleclick-campaign-manager-view-through-attribution}

## 透過歸因測量檢視 {#measuring-view-through-attribution}

>[!IMPORTANT]
>
>基於隱私權疑慮，第三方Cookie即將推出。 Google Chrome於2024年第3季度宣佈淘汰第三方Cookie，實際標誌著此追蹤形式的結束。 因此，Adobe淘汰依賴第三方Cookie的Marketo Measure功能；特別是跨網域追蹤和瀏覽歸因，後者使用Google/DoubleClick曝光數Cookie。 Marketo Measure的其他功能將不會受到影響。 第一方Cookie使用量也不受影響。 根據Google排程，上述兩個功能的預計淘汰日期為2024年6月1日。 在此日期之前收集的相關資料仍可供Adobe客戶使用。

>[!NOTE]
>
>如果您使用[!DNL Marketo Measure]和[!DNL DoubleClick Campaign Manager]整合，我們需要[API連線](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms)，這樣我們才能下載行銷活動的詳細資訊和創意來解析廣告。

若要透過[!DNL Doubleclick Campaign Manager]的追蹤開始從檢視中獲得更細微的深入分析，需要設定我們的追蹤畫素。

如需有關透過歸因功能檢視[!DNL Marketo Measure]的詳細資訊，請參閱[透過歸因常見問答集](/help/advanced-marketo-measure-features/view-through-attribution/marketo-measure-view-through-attribution-faq.md)Marketo Measure檢視。

[!DNL Marketo Measure]被視為隨附標籤，因為它是透過DCM廣告標籤的第三方呼叫。 揹帶標籤不適用於影像標籤，只有iframe或javascript標籤。 根據DCM支援，這種情況最近並沒有改變，而且一直都是如此。 標準標籤已於2017年10月2日淘汰，但不會影響[!DNL Marketo Measure]追蹤曝光的能力。

若您在DCM中使用父項和子項階層，我們需要將標籤套用至曝光追蹤的所有層級。

## 如何新增影像標籤 {#how-to-add-the-image-tag}

將標籤新增至「廣告商」設定下的Doubleclick中，並建立曝光事件標籤。

1. 將下列程式碼新增為1x1影像畫素。

`https://cdn.bizibly.com/i?v=%eadv!&a=%eaid!&c=%ecid!&s=%esid!&p=%epid!&m=%m&n=%n`

1. 新增分隔符號後，請確認分隔符號已如下對應。 套用標籤後，這應為自動的：

   v = %eadv！ [!DNL Expand]廣告商ID\
   a = %eaid！ 展開廣告Id\
   c = %ecid！ 展開創作Id\
   s = %esid！ 展開網站ID\
   p = %epid！ 展開位置Id\
   m = %m符合程式碼巨集\
   n = %n隨機數字巨集

   ![](assets/1.png)

## 常見問題集 {#faq}

**問：影像標籤是否安全？**

答：是。 它不是JavaScript標籤，而是影像標籤。

**問：連線的使用者需要哪些許可權？**

答：dfatrafficking、dfareporting、userinfo.email

**問：匯入支出資料需要多久的時間？**

答：最多6小時

**問：匯入廣告資料需要多久的時間？**

答：最多6小時
