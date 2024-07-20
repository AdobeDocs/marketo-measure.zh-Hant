---
unique-page-id: 18874759
description: 正在新增 [!DNL Marketo Measure] 至 [!DNL Hubspot] - [!DNL Marketo Measure]
title: 正在新增 [!DNL Marketo Measure] 至 [!DNL Hubspot]
exl-id: 633e7ef7-7959-461e-881f-dcc543595b66
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 1%

---

# 正在新增[!DNL Marketo Measure]至[!DNL Hubspot] {#adding-marketo-measure-to-hubspot}

瞭解如何新增[!DNL Marketo Measure] JavaScript以追蹤您的[!DNL Hubspot]登陸頁面和表單提交。

Hubspot與其他行銷自動化系統有些不同，因為它可以託管您的登入頁面/表單以及您的網站。 請務必注意，以下指示適用於在[!DNL Hubspot]託管頁面上使用[!DNL Marketo Measure]追蹤活動。 如果您使用[!DNL Hubspot]以外的CMS （例如Wordpress）支援網站，您也需要將[!DNL Marketo Measure] JavaScript新增至該CMS。

>[!NOTE]
>
>如果您是透過[!DNL Google Tag Manager]等標籤管理提供者部署JavaScript，則不需要手動將[!DNL Marketo Measure] JavaScript硬式編碼至您的網站。

## 快速入門 {#getting-started}

登入[!DNL Hubspot]帳戶後，請依照下列步驟操作。

1. 導覽至「內容」。

1. 按一下&#x200B;**[!UICONTROL Content Settings]**。

1. 在[!UICONTROL Content Settings]內，按一下網站標題HTML（請參閱下圖）。

1. 在您的`<header>`中新增下列指令碼：

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

   它應如下所示：

```text
<!-- Marketo Measure Javascript -->
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="">
```

>[!TIP]
>
>此區域可能已有其他追蹤程式碼片段，例如Google Analytics程式碼。 請務必以分號`;`和單一空格來分隔，如下所示：
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`
