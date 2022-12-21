---
unique-page-id: 18874757
description: 新增 [!DNL Marketo Measure] JavaScript轉換為 [!DNL Pardot] - [!DNL Marketo Measure]  — 產品檔案
title: 新增 [!DNL Marketo Measure] JavaScript轉換為 [!DNL Pardot]
exl-id: e49190ad-aa86-4f8f-a9ed-48de9e937a7e
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---

# 新增 [!DNL Marketo Measure] JavaScript轉換為 [!DNL Pardot] {#adding-marketo-measure-javascript-to-pardot}

[!DNL Pardot] 表單範本中除了需要將指令碼放在網站上外，還需要進行其他處理，才能 [!DNL Marketo Measure] 識別表單提交。 過程簡單；它只需要將 [!DNL Marketo Measure] 追蹤指令碼 [!DNL Pardot] 表單範本。

## 逐步指示 {#step-by-step-instructions}

登入您的 [!DNL Pardot] 帳戶，請遵循下列步驟。

1. 導覽至 **[!UICONTROL Marketing]**.

1. 按一下 **[!UICONTROL Landing Pages]**.

1. 選取 **[!UICONTROL Layout Template]**.

   ![](assets/1-3.png)

1. 確定適當的「佈局模板」，然後按一下 **[!UICONTROL Edit]** 右邊。

   ![](assets/2-1.png)

1. 複製並貼上 [!DNL Marketo Measure] JavaScript程式碼，緊接在您的HTML頁面上的關閉標題標籤之前。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 請依照下列步驟操作所有適用的登陸頁面配置範本。

1. 請確定 [!DNL Marketo Measure] JavaScript也位於一般網站頁面上。

   在 [!DNL Pardot] 版面範本中，程式碼看起來會像這樣：

```text
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>
   </head>
   <body>
```

## 其他附註 {#additional-notes}

若 [!DNL Pardot] IFrame具有下列HTML標籤：

`<base href="http://go.pardot.com">`

_和_ 當我們嘗試在 [!DNL Pardot] 若為IFrame，瀏覽器會嘗試在HTTPS頁面上載入我們指令碼的HTTP版本，但該版本會失敗，且會阻止我們追蹤。 解決方案是更新 [!DNL Pardot] IFrame來載入指令碼的安全版本：

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

此外，此區域中可能已有其他追蹤程式碼片段，例如 [!DNL Google Analytics] 程式碼。 請務必以分號分隔 `;` 和單一空間，如此範例所示：

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="othercode_example" src="otherfile_example.js" ></script>`
