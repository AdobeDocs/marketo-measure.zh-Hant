---
unique-page-id: 18874759
description: 新增 [!DNL Marketo Measure] to [!DNL Hubspot] - [!DNL Marketo Measure]  — 產品檔案
title: 新增 [!DNL Marketo Measure] to [!DNL Hubspot]
exl-id: 633e7ef7-7959-461e-881f-dcc543595b66
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%

---

# 新增 [!DNL Marketo Measure] to [!DNL Hubspot] {#adding-marketo-measure-to-hubspot}

了解如何新增 [!DNL Marketo Measure] JavaScript來追蹤您的 [!DNL Hubspot] 登錄頁面和表單提交。

Hubspot與其他行銷自動化系統略有不同，因為它可以托管您的登錄頁面/表單，以及您的網站。 請務必注意，下列指示是 [!DNL Marketo Measure] 追蹤活動 [!DNL Hubspot] — 托管的頁面。 如果您使用CMS以外的CMS為網站供電， [!DNL Hubspot] （例如Wordpress），您需要將 [!DNL Marketo Measure] JavaScript也支援。

>[!NOTE]
>
>如果您是透過標籤管理提供者(例如 [!DNL Google Tag Manager]，您不需要手動硬式編碼 [!DNL Marketo Measure] JavaScript填入您的網站。

## 快速入門 {#getting-started}

登入後 [!DNL Hubspot] 帳戶，請遵循下列步驟。

1. 導覽至「內容」。

1. 按一下 **[!UICONTROL Content Settings]**.

1. 內 [!UICONTROL Content Settings]，按一下「網站標題」HTML（請參閱下圖）。

1. 在您的 `<header>`:

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

   應該如下所示：

```text
<!-- Marketo Measure Javascript -->
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="">
```

>[!TIP]
>
>此區域中可能已有其他追蹤程式碼片段，例如Google Analytics程式碼。 請務必以分號分隔 `;` 一個空間，就這樣：
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`
