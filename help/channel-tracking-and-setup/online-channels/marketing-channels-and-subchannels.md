---
unique-page-id: 18874682
description: 行銷管道和子管道 —  [!DNL Marketo Measure]  — 產品檔案
title: 行銷管道和子管道
exl-id: fbe2a994-cf6d-439c-af96-a562216434cc
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 0%

---

# 行銷管道和子管道 {#marketing-channels-and-subchannels}

## 用途 {#purpose}

定義管道和子管道的位置 [!DNL Marketo Measure]，它們與您內容的關聯、兩個分類之間的差異，以及在 [!DNL Marketo Measure] 應用程式。

## 總覽 {#overview}

「行銷管道」可協助您將行銷活動分類（或「分段」），以方便報告，兩者皆位於 [!DNL Marketo Measure] ROI破折號以及您的CRM中。 [!DNL Marketo Measure] 隨附12個現成可用的管道（您可以自訂/重新命名以符合組織的慣例），以及進一步建立自訂管道以進行更精細的篩選的能力。

每當您收到網站上您其中一個內容頁面（無論該內容是網頁、白皮書下載、頁面URL等）的訪客時，該銷售機會就會根據URL中找到的數個UTM參數「分段」至管道/子管道：

* 中
* 來源
* 行銷活動
* 登陸頁面
* 反向連結網站

若要根據銷售機會的UTM參數自訂銷售機會將落入的「貯體」，您可以使用管道規則。 如需設定及維護管道規則的詳細資訊， [按一下這裡](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

了解如何設定 [線上頻道](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md) 和 [離線頻道](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)，以及兩者的差異。

**行銷管道**

行銷管道是最廣泛的分類層級，可涵蓋多種子管道。 您可以將這些視為您的銷售機會來源的子管道「類型」。 行銷管道範例包括 **付費搜尋、有機搜尋、顯示、** 和 **付費社交**. 行銷管道通常對應至URL中的utm_medium參數值。

**子頻道**

子通道是拼湊傳入Lead時的第二個拼圖。 子頻道講的 _wh_ 的迭代次數。 例如，在「付費社交行銷管道」中，您可能有 **AdWords**, **BingAds**, **Facebook**、等 子管道通常對應至URL中找到的utm_source參數值。

## 使用案例範例 {#use-case-example}

下圖說明行銷管道、子管道和內容的範例，其基於具有下列URL的網頁：

* [http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=paidsocial](http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=paidsocial)*

在此案例中，使用者嘗試存取的內容是B2B行銷歸因的簡介指南。 [!DNL Marketo Measure] 會使用此組織中設定的「管道規則」來分析導向此內容的URL，並使用它們來「分段」此銷售機會至行銷管道「付費社交」和子管道「LinkedIn」。

![](assets/1.jpg)

其他範例……

**行銷管道（中）**

* PPC
* 付費社交
* 有機社交
* 電子郵件
* 活動和會議
* 自然搜尋/SEO
* PR
* 轉介方案

**子管道（接觸點來源）**

* Google AdWords
* BingAds
* Facebook Ads
* Adroll
* 按兩下
* 卡佩拉
* 滴漏行銷活動
* linkedIn Ads

**內容（白皮書、頁面URL、部落格文章）**

* www.adobe.com/blog1
* www.adobe.com/whitepaper
* www.adobe.com/sign-up-now
