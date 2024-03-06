---
unique-page-id: 18874519
description: 新增 [!DNL Marketo Measure] Lightbox Forms的指令碼 —  [!DNL Marketo Measure]
title: 新增 [!DNL Marketo Measure] Script to Lightbox Forms
exl-id: fa9ce480-fc4f-4abd-8555-dbb74849747e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---

# 新增 [!DNL Marketo Measure] Script to Lightbox Forms {#adding-marketo-measure-script-to-lightbox-forms}

瞭解如何正確新增 [!DNL Marketo Measure] JavaScript至燈箱中的表單。

當訪客執行特定動作（即按一下頁面的特定部分、在頁面上花費特定時間等）時，燈箱會在您的內容前面開啟表單。 通常我們會要求 [!DNL Marketo Measure] JavaScript放置在登入頁面的開頭，但若是燈箱中的表單，則需要額外的一個步驟。

由於Lightbox中的表單基本上是iFrame中的表單，因此指令碼會放置在該iFrame中。

首先，找出iFrame [!UICONTROL lightbox] 形式存在於中。

![](assets/1.png)

接下來，放置 [!DNL Marketo Measure] iFrame中的JavaScript。

![](assets/2.png)

最後，新增JavaScript時，會依照下列指示追蹤驗證表單提交：

1. 複製包含登入頁面的URL [!UICONTROL lightbox] 表單。
1. 開啟無痕瀏覽器並貼上URL。
1. 使用唯一的電子郵件地址提交表單。
1. 檢查您的CRM是否有使用的唯一電子郵件地址，以確認是否已追蹤測試，並確定已填入接觸點資料。
