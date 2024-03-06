---
unique-page-id: 18874757
description: 新增 [!DNL Marketo Measure] JavaScript至 [!DNL Pardot] - [!DNL Marketo Measure]
title: 新增 [!DNL Marketo Measure] JavaScript至 [!DNL Pardot]
exl-id: e49190ad-aa86-4f8f-a9ed-48de9e937a7e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%

---

# 新增 [!DNL Marketo Measure] JavaScript至 [!DNL Pardot] {#adding-marketo-measure-javascript-to-pardot}

[!DNL Pardot] 除了在網站上放置指令碼外，表單還需要在表單範本中進行其他處理 [!DNL Marketo Measure] 以辨識表單提交。 程式很簡單，只需要將 [!DNL Marketo Measure] 將指令碼追蹤至 [!DNL Pardot] 表單範本。

## 逐步指示 {#step-by-step-instructions}

登入後 [!DNL Pardot] 帳戶，請遵循下列步驟。

1. 瀏覽至 **[!UICONTROL Marketing]**.

1. 按一下 **[!UICONTROL Landing Pages]**.

1. 選取 **[!UICONTROL Layout Template]**.

   ![](assets/1-3.png)

1. 決定適當的版面範本，然後按一下 **[!UICONTROL Edit]** 右邊。

   ![](assets/2-1.png)

1. 複製並貼上 [!DNL Marketo Measure] JavaScript程式碼位於HTML頁面上的關閉頁首標籤之前。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 請依照這些步驟操作所有適用的登陸頁面配置範本。

1. 確定 [!DNL Marketo Measure] JavaScript也位於一般網站頁面。

   在 [!DNL Pardot] 配置範本，程式碼看起來像這樣：

```text
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>
   </head>
   <body>
```

## 其他附註 {#additional-notes}

如果 [!DNL Pardot] IFrame具有下列HTML標籤：

`<base href="http://go.pardot.com">`

_與_ 在中載入指令碼時，IFrame本身實際上是安全頁面(HTTPS)而不是不安全(HTTP) [!DNL Pardot] IFrame，瀏覽器會嘗試在HTTPS頁面上載入指令碼的HTTP版本而失敗，並中斷追蹤。 解決方案是更新上的指令碼 [!DNL Pardot] 要載入指令碼的安全版本的IFrame：

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

此區域可能已有其他追蹤程式碼片段，例如 [!DNL Google Analytics] 程式碼。 請務必以分號分隔 `;` 和單一空格，如以下範例所示：

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="othercode_example" src="otherfile_example.js" ></script>`
