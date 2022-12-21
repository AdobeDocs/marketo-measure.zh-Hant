---
unique-page-id: 18874736
description: 移除 [!DNL Marketo Measure] 從Google Analytics中的登陸頁面URL追蹤參數 —  [!DNL Marketo Measure]  — 產品檔案
title: 移除 [!DNL Marketo Measure] 從Google Analytics中的登陸頁面URL追蹤參數
exl-id: ec81ba4a-bb10-49fd-b62e-5a1bc9e1a023
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 0%

---

# 移除 [!DNL Marketo Measure] 從Google Analytics中的登陸頁面URL追蹤參數 {#remove-marketo-measure-tracking-parameters-from-the-landing-page-url-in-google-analytics}

在中檢視登錄頁面時，有時 [!DNL Google Analytics]，您會想要從URL中移除追蹤參數。 否則，它們會分割為個別列。

幸運的是，這是個簡單的解決辦法。

1. 在 [!DNL Google Analytics]，前往 [!UICONTROL Admin] >[!UICONTROL View Settings] >[!UICONTROL Exclude URL Query Parameters].
1. 在框中鍵入「_bt,_bk,_bm,_bn,_bg」（減去引號）。
1. 向下捲動並按一下 **[!UICONTROL Save]**.

   請記住 [!DNL Google Analytics] 不會重新處理資料。 因此，此變更只會反映在未來，而您過去的資料仍會以bt、bk和bm參數顯示。
