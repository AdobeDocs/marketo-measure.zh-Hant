---
unique-page-id: 18874759
description: 新增 [!DNL Marketo Measure] 至 [!DNL Hubspot] - [!DNL Marketo Measure]  — 產品檔案
title: 新增 [!DNL Marketo Measure] 至 [!DNL Hubspot]
exl-id: 633e7ef7-7959-461e-881f-dcc543595b66
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%

---

# 新增 [!DNL Marketo Measure] 至 [!DNL Hubspot] {#adding-marketo-measure-to-hubspot}

瞭解如何新增 [!DNL Marketo Measure] JavaScript，追蹤您的 [!DNL Hubspot] 登陸頁面和表單提交。

Hubspot與其他行銷自動化系統有些不同，因為它可以託管您的登入頁面/表單以及您的網站。 請務必注意，以下指示適用於擁有 [!DNL Marketo Measure] 追蹤活動 [!DNL Hubspot] — 託管頁面。 如果您使用以外的CMS支援網站 [!DNL Hubspot] （例如Wordpress），您需要新增 [!DNL Marketo Measure] 將JavaScript新增至該CMS。

>[!NOTE]
>
>如果您要透過標籤管理提供者(例如 [!DNL Google Tag Manager]，您不需要手動硬式編碼 [!DNL Marketo Measure] JavaScript至您的網站。

## 快速入門 {#getting-started}

登入後 [!DNL Hubspot] 帳戶，請遵循這些步驟。

1. 導覽至「內容」。

1. 按一下 **[!UICONTROL Content Settings]**.

1. 範圍 [!UICONTROL Content Settings]，按一下「網站標題」HTML（請參閱下圖）。

1. 在您的中新增以下指令碼 `<header>`：

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

   它應如下所示：

```text
<!-- Marketo Measure Javascript -->
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="">
```

>[!TIP]
>
>此區域可能已有其他追蹤程式碼片段，例如Google Analytics程式碼。 請務必以分號分隔 `;` 和單一空間，如下所示：
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`
