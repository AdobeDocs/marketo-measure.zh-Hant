---
unique-page-id: 18874736
description: 移除 [!DNL Marketo Measure] 從Google Analytics的登陸頁面URL追蹤引數 —  [!DNL Marketo Measure]  — 產品檔案
title: 移除 [!DNL Marketo Measure] 從Google Analytics中的登陸頁面URL追蹤引數
exl-id: ec81ba4a-bb10-49fd-b62e-5a1bc9e1a023
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 0%

---

# 移除 [!DNL Marketo Measure] 從Google Analytics中的登陸頁面URL追蹤引數 {#remove-marketo-measure-tracking-parameters-from-the-landing-page-url-in-google-analytics}

有時當在中檢視登入頁面時 [!DNL Google Analytics]，您會想要從URL中移除追蹤引數。 否則，它們將會分割成個別列。

幸運的是，這是一個簡單的修正。

1. 在 [!DNL Google Analytics]，前往 [!UICONTROL Admin] >[!UICONTROL View Settings] >[!UICONTROL Exclude URL Query Parameters].
1. 在方塊中輸入「_bt，_bk，_bm，_bn，_bg」（減去引號）。
1. 向下捲動並按一下 **[!UICONTROL Save]**.

   請記住 [!DNL Google Analytics] 不會重新處理資料。 因此，此變更只會反映到以後，而您的過去資料仍會以bt、bk和bm引數顯示。
