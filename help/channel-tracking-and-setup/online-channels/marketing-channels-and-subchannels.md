---
unique-page-id: 18874682
description: 行銷管道和子管道 —  [!DNL Marketo Measure]  — 產品檔案
title: 行銷管道和子管道
exl-id: fbe2a994-cf6d-439c-af96-a562216434cc
feature: Channels
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 1%

---

# 行銷管道和子管道 {#marketing-channels-and-subchannels}

## 用途 {#purpose}

定義管道和子管道的用途 [!DNL Marketo Measure]，它們與您的內容有何關係、兩個分類之間的差異，以及它們在 [!DNL Marketo Measure] 應用程式。

## 概觀 {#overview}

行銷管道是用來協助將您的行銷活動分類（或「貯體」），以方便報告，兩者皆適用於 [!DNL Marketo Measure] ROI短劃線以及您的CRM。 [!DNL Marketo Measure] 隨附立即可用的12個管道（您可自訂/重新命名以符合貴組織的慣例），並可進一步建立自訂管道以進行更精細的篩選。

每當您收到網站其中一個內容頁面（無論是網頁、白皮書下載、頁面URL等）的訪客時，該Lead會根據URL中的數個UTM引數，分組到頻道/子頻道中：

* 中
* 來源
* Campaign
* 登陸頁面
* 引用網站

若要根據潛在客戶的UTM引數自訂其所屬的「貯體」，您可以使用管道規則。 如需設定和維護您的管道規則的詳細資訊， [按一下這裡](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

瞭解如何設定您的 [線上頻道](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md) 和 [離線頻道](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)以及兩者之間的差異。

**行銷管道**

行銷管道是最廣泛的分類等級，可涵蓋各種子管道。 您可以考慮這些是潛在客戶來源的子管道「型別」。 行銷管道的範例包括 **付費搜尋、有機搜尋、顯示、** 和 **付費社交**. 行銷管道通常對應於在URL中找到的utm_medium引數值。

**子管道**

子管道是劃分傳入的潛在客戶時的第二個拼圖。 子管道準確地訴說以下故事 _哪個_ 已使用您行銷管道的版序。 例如，在付費社交行銷管道中，您可能有子管道 **AdWords**， **BingAds**， **facebook**&#x200B;等 子管道通常對應於在您的URL中找到的utm_source引數值。

## 使用案例範例 {#use-case-example}

下圖舉例說明根據具有下列URL之網頁的行銷管道、子管道和內容：

* [http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=paidsocial](http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=paidsocial)*

在此情況下，使用者嘗試存取的內容是B2B行銷歸因簡介指南。 [!DNL Marketo Measure] 將使用此組織中設定的管道規則來分析導向此內容的URL，並使用它們「貯體」此銷售機會至行銷管道「付費社交」和子管道「LinkedIn」。

![](assets/1.jpg)

更多範例……

**行銷管道（媒體）**

* PPC
* 付費社交
* 自然社交
* 電子郵件
* 活動與會議
* 有機搜尋/SEO
* PR
* 轉介計畫

**子管道（接觸點來源）**

* Google AdWords
* BingAds
* facebook Ads
* Adroll
* 按兩下
* Capterra
* 滴答式行銷活動
* LinkedIn 廣告

**內容（白皮書、頁面URL、部落格）**

* www.adobe.com/blog1
* www.adobe.com/whitepaper
* www.adobe.com/sign-up-now
