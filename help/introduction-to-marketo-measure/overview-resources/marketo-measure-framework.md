---
unique-page-id: 18874570
description: Marketo Measure架構 — Marketo Measure — 產品檔案
title: Marketo Measure架構
exl-id: fa6de27c-cdd2-4fd9-ac35-7286fe2752d8
source-git-commit: 7eb5ef616e3ae77d53056496f9a1b301ce59d6ee
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 0%

---

# Marketo Measure架構 {#marketo-measure-framework}

進一步了解組成Marketo Measure架構的四個主要元件。 Marketo Measure仰賴這些應用程式來追蹤、整理和存放資料，並提供報告功能。 構成Marketo Measure架構的四個元件為：

* Marketo Measure的JavaScript
* CRM整合
* 第三方應用程式/系統
* Marketo Measure應用程式

## Marketo Measure JavaScript {#marketo-measure-javascript}

Marketo Measure JavaScript會追蹤潛在客戶/潛在客戶與貴組織的所有線上行銷互動（也稱為接觸點）。 這是在結尾 `</head>` 標籤。

`<script type="text/javascript" src="//[cdn.bizible.com/scripts/bizible.js](http://cdn.bizible.com/scripts/bizible.js)" async=""></script>`

>[!NOTE]
>
>如需新增Marketo Measure JS的指示，請參閱 [按一下這裡](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md).

Marketo Measure的JS會擷取來自網站造訪（包括匿名網站造訪）、一般流量/頁面導覽、內容下載和表單提交的資料。 此資料會推送至您的CRM，而每次行銷互動都會顯示為接觸點。

## CRM整合 {#crm-integrations}

Marketo Measure與CRM整合，以儲存及組織Marketo Measure JS擷取的所有資料。 目前，Marketo Measure已與兩個CRM整合API:

![](assets/1-2.png)

透過在CRM中呈現Marketo Measure資料，您將能夠查看與每個接觸點相關的詳細資訊，並產生報表以了解管道的執行情形。

## 第三方應用程式 {#third-party-applications}

大部分的行銷人員都仰賴幾個不同的應用程式來執行行銷工作。 除了Salesforce和MS Dynamics外，Marketo Measure還與13個協力廠商應用程式整合（如下所列）。

![](assets/2-1.png)

如果您使用上述應用程式執行任何行銷工作，可將這些帳戶連結至您的Marketo Measure帳戶。 這可讓您輕鬆追蹤資料，並將資料傳輸至您的Marketo Measure帳戶。

## Marketo Measure應用程式 {#marketo-measure-application}

Marketo Measure應用程式可用來檢視和報告您的歸因資料、設定帳戶設定及更新帳戶資訊。 Marketo Measure應用程式中的主功能表項目包括：

**帳戶設定**

您可以在此更新公司的一般資訊並存取Marketo Measure Javascript。

**設定**

此功能表項目可讓您設定歸因和管道對應設定、管理與CRM和協力廠商應用程式的整合、檢視/新增Marketo Measure帳戶使用者，以及更新計費資訊。

**行銷ROI儀表板**

「行銷ROI控制面板」功能表項目可讓您以管道效能、活動和成本的形式來視覺化資料。
