---
unique-page-id: 18874519
description: 新增 [!DNL Marketo Measure] 指令碼至Lightbox Forms - [!DNL Marketo Measure]  — 產品檔案
title: 新增 [!DNL Marketo Measure] 指令碼至Lightbox Forms
exl-id: fa9ce480-fc4f-4abd-8555-dbb74849747e
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 0%

---

# 新增 [!DNL Marketo Measure] 指令碼至Lightbox Forms {#adding-marketo-measure-script-to-lightbox-forms}

了解如何正確新增 [!DNL Marketo Measure] JavaScript轉換為燈箱內的表單。

當訪客執行特定動作時（例如按一下頁面的特定部分、在頁面上逗留特定時間等），燈箱會在您的內容前開啟表單。 通常我們只要求 [!DNL Marketo Measure] 將JavaScript放置在登錄頁面的標題中，但若是燈箱內的表單，則需要額外的步驟。

由於燈箱內的表單基本上是iFrame內的表單，因此我們需要將指令碼放在該iFrame內。

首先，找出iFrame [!UICONTROL lightbox] 形體就住在裡面。

![](assets/1.png)

接下來，將 [!DNL Marketo Measure] iFrame內的JavaScript。

![](assets/2.png)

最後，新增JavaScript時，建議您驗證正在依照下列指示追蹤表單提交：

1. 複製包含的登錄頁面的URL [!UICONTROL lightbox] 表單。
1. 開啟Incognito瀏覽器並貼上URL。
1. 使用唯一的電子郵件地址提交表單。
1. 檢查您的CRM中是否使用不重複的電子郵件地址，確認已追蹤測試，確認接觸點資料已填入。
