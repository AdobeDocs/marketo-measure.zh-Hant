---
unique-page-id: 18874757
description: 正在新增 [!DNL Marketo Measure] JavaScript至 [!DNL Pardot] - [!DNL Marketo Measure]
title: 正在新增 [!DNL Marketo Measure] JavaScript至 [!DNL Pardot]
exl-id: e49190ad-aa86-4f8f-a9ed-48de9e937a7e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%

---

# 正在新增[!DNL Marketo Measure] JavaScript至[!DNL Pardot] {#adding-marketo-measure-javascript-to-pardot}

[!DNL Pardot]個表單需要在表單範本中進行額外處理，而不只是讓指令碼放到網站上以讓[!DNL Marketo Measure]識別表單提交。 程式很簡單；它只需要將[!DNL Marketo Measure]追蹤指令碼放入[!DNL Pardot]表單範本中。

## 逐步指示 {#step-by-step-instructions}

登入[!DNL Pardot]帳戶後，請遵循下列步驟。

1. 瀏覽至&#x200B;**[!UICONTROL Marketing]**。

1. 按一下&#x200B;**[!UICONTROL Landing Pages]**。

1. 選取&#x200B;**[!UICONTROL Layout Template]**。

   ![](assets/1-3.png)

1. 決定適當的配置範本，然後按一下右側的&#x200B;**[!UICONTROL Edit]**。

   ![](assets/2-1.png)

1. 將[!DNL Marketo Measure] JavaScript程式碼複製並貼到HTML頁面中結尾標頭標籤的前面。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 請依照這些步驟操作所有適用的登陸頁面配置範本。

1. 確定[!DNL Marketo Measure] JavaScript也在一般網站頁面上。

   在[!DNL Pardot]配置範本中，程式碼看起來像這樣：

```text
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>
   </head>
   <body>
```

## 其他附註 {#additional-notes}

如果[!DNL Pardot] IFrame具有下列HTML標籤：

`<base href="http://go.pardot.com">`

_而且_ IFrame本身實際上是一個安全頁面(HTTPS)而不是不安全(HTTP)，當在[!DNL Pardot] IFrame中載入指令碼時，瀏覽器會嘗試在HTTPS頁面上載入指令碼的HTTP版本，這會失敗，並中斷追蹤。 解決方案是更新[!DNL Pardot] IFrame上的指令碼，以載入指令碼的安全版本：

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

此區域可能已有其他追蹤程式碼片段，例如[!DNL Google Analytics]程式碼。 請務必使用分號`;`和單一空格來分隔，如下列範例所示：

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="othercode_example" src="otherfile_example.js" ></script>`
