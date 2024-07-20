---
unique-page-id: 18874736
description: 從Google Analytics- [!DNL Marketo Measure]中的登陸頁面URL移除 [!DNL Marketo Measure] 追蹤引數
title: 從Google Analytics中的登陸頁面URL移除 [!DNL Marketo Measure] 追蹤引數
exl-id: ec81ba4a-bb10-49fd-b62e-5a1bc9e1a023
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 0%

---

# 從Google Analytics中的登陸頁面URL移除[!DNL Marketo Measure]個追蹤引數 {#remove-marketo-measure-tracking-parameters-from-the-landing-page-url-in-google-analytics}

有時在[!DNL Google Analytics]中檢視登入頁面時，您會想要從URL中移除追蹤引數。 否則，它們將會分割成個別列。

幸運的是，這是一個簡單的修正。

1. 在[!DNL Google Analytics]中，移至[!UICONTROL Admin] >[!UICONTROL View Settings] >[!UICONTROL Exclude URL Query Parameters]。
1. 在方塊中輸入「_bt，_bk，_bm，_bn，_bg」（減去引號）。
1. 向下捲動並按一下&#x200B;**[!UICONTROL Save]**。

   請記住，[!DNL Google Analytics]不會重新處理資料。 因此，此變更只會反映到以後，而您的過去資料仍會以bt、bk和bm引數顯示。
