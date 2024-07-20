---
unique-page-id: 18874570
description: Marketo Measure架構 — Marketo Measure — 產品檔案
title: Marketo Measure框架
exl-id: fa6de27c-cdd2-4fd9-ac35-7286fe2752d8
feature: Fundamentals
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 0%

---

# Marketo Measure框架 {#marketo-measure-framework}

深入瞭解構成Marketo Measure架構的四個主要元件。 Marketo Measure仰賴這些應用程式來追蹤、整理及存放資料，並提供報表功能。 構成Marketo Measure架構的四個元件包括：

* Marketo Measure的JavaScript
* CRM整合
* 協力廠商應用程式/系統
* Marketo Measure應用程式

## Marketo Measure JavaScript {#marketo-measure-javascript}

Marketo Measure JavaScript會追蹤潛在客戶/潛在客戶與您組織的所有線上行銷互動（也稱為接觸點）。 這是自訂指令碼，會在您網站每個頁面的結束`</head>`標籤之前新增。

`<script type="text/javascript" src="//[cdn.bizible.com/scripts/bizible.js](http://cdn.bizible.com/scripts/bizible.js)" async=""></script>`

>[!NOTE]
>
>如需如何新增Marketo Measure JS的說明，[請按一下這裡](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md)。

Marketo Measure的JS會擷取網站造訪（包括匿名網站造訪）、一般流量/頁面導覽、內容下載和表單提交中的資料。 此資料會推送至您的CRM，而每次行銷互動都會顯示為接觸點。

## CRM整合 {#crm-integrations}

Marketo Measure會與CRM整合，以存放及組織Marketo Measure JS擷取的所有資料。 目前，Marketo Measure已將API與兩個CRM整合：

![](assets/1-2.png)

透過在CRM中呈現Marketo Measure資料，您可以檢視與每個接觸點相關的精細資訊，並產生報表以瞭解管道的表現。

## 協力廠商應用程式 {#third-party-applications}

大部分行銷人員會依賴一些不同的應用程式來執行其行銷工作。 除了Salesforce和MS Dynamics，Marketo Measure還與13個協力廠商應用程式（如下所列）整合。

![](assets/2-1.png)

如果您使用上述應用程式執行任何行銷工作，可以將這些帳戶連結至您的Marketo Measure帳戶。 這可讓您輕鬆追蹤資料，並將資料傳輸至您的Marketo Measure帳戶。

## Marketo Measure應用程式 {#marketo-measure-application}

Marketo Measure應用程式可用來檢視和報告您的歸因資料、設定帳戶設定以及更新帳戶資訊。 Marketo Measure應用程式中的主要功能表專案包括：

**帳戶組態**

您可以在此處更新公司的一般資訊並存取Marketo Measure Javascript。

**設定**

此功能表專案可讓您設定歸因和管道對應設定、管理與CRM和協力廠商應用程式的整合、檢視/新增Marketo Measure帳戶使用者，以及更新計費資訊。

**行銷ROI儀表板**

「行銷ROI控制面板」功能表專案可讓您根據管道績效、活動和成本將資料視覺化。
