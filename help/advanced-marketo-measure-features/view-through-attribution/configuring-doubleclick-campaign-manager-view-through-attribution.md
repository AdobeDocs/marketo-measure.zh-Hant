---
unique-page-id: 18874781
description: 透過歸因設定Doubleclick Campaign Manager檢視 —  [!DNL Marketo Measure]  — 產品檔案
title: 透過歸因設定Doubleclick Campaign Manager檢視
exl-id: 2cc6c2cd-afb7-4052-b18b-9ad0bf16a9fa
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---

# 透過歸因設定Doubleclick Campaign Manager檢視 {#configuring-doubleclick-campaign-manager-view-through-attribution}

## 透過歸因測量檢視 {#measuring-view-through-attribution}

>[!NOTE]
>
>如果您使用 [!DNL Marketo Measure] 和DoubleClick Campaign Manager整合，我們需要 [API連線](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms) 因此，我們可以下載促銷活動和創意的詳細資訊來解析廣告。

若要開始透過Doubleclick Campaign Manager追蹤，從檢視獲得更精細的深入分析，必須設定我們的追蹤像素。

請 [按一下這裡](/help/advanced-marketo-measure-features/view-through-attribution/marketo-measure-view-through-attribution-faq.md) ，了解 [!DNL Marketo Measure] 透過歸因功能檢視。

[!DNL Marketo Measure] 會視為「搭便車」標籤，因為這是透過DCM廣告標籤進行的協力廠商呼叫。 背標標籤無法與影像標籤搭配使用，只能與iframe或javascript標籤搭配使用。 根據DCM支援，最近並未改變，而且一直如此。 標準標籤已於2017年10月2日淘汰，但不會影響 [!DNL Marketo Measure] 以追蹤曝光次數。

如果您在DCM中運用父層級和子層級，則需要將標籤套用至所有層級，以便進行曝光追蹤。

## 如何新增影像標籤 {#how-to-add-the-image-tag}

您會在「廣告商」設定下方將標籤新增至Doubleclick中，且您會想要建立「曝光事件標籤」。

1. 將下列程式碼新增為1x1影像像素。

`https://cdn.bizibly.com/i?v=%eadv!&a=%eaid!&c=%ecid!&s=%esid!&p=%epid!&m=%m&n=%n`

1. 新增分隔字元後，請確認分隔字元已對應如下。 在套用標籤後，這應該會自動執行：

   v = %eadv! 展開廣告商Id\
   a = %eaid! 展開廣告Id\
   c = %ecid! 展開創作Id\
   s = %esid! 展開網站Id\
   p = %epid! 展開位置Id\
   m = %m匹配代碼宏\
   n = %n隨機數宏

   ![](assets/1.png)

## 常見問題集 {#faq}

**問：影像標籤是否安全？**

答：是。 它不是JavaScript標籤，而是影像標籤。

**問：連線的使用者需要什麼權限？**

答：dfatfrafficing, dfarporting, userinfo.email

**問：匯入支出資料需要多久的時間？**

答：最多6小時

**問：匯入廣告資料需要多久時間？**

答：最多6小時
