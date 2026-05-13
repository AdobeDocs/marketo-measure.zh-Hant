---
unique-page-id: 18874736
description: 從Google Analytics中的登陸頁面URL移除 [!DNL Marketo Measure] 追蹤引數 —  [!DNL Marketo Measure]
title: 從Google Analytics中的登陸頁面URL移除 [!DNL Marketo Measure] 追蹤引數
exl-id: ec81ba4a-bb10-49fd-b62e-5a1bc9e1a023
feature: Tracking
TQID: https://experienceleague.adobe.com/vKhwWUT0VQ1Kr-3-dWVWt08S4848Q0Bn4HYrGgHawb8
product_v2: id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
topic_v2: id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 9ceb54139bfa9b6ce7c2c5fbb4e25e649f5708a3
workflow-type: tm+mt
source-wordcount: 109
ht-degree: 0%

---

# 從Google Analytics中的登陸頁面URL移除[!DNL Marketo Measure]追蹤引數 {#remove-marketo-measure-tracking-parameters-from-the-landing-page-url-in-google-analytics}

有時在[!DNL Google Analytics]中檢視登入頁面時，您會想要從URL中移除追蹤引數。 否則，它們將會分割成個別列。

幸運的是，這是一個簡單的修正。

1. 在[!DNL Google Analytics]中，移至[!UICONTROL Admin] >[!UICONTROL View Settings] >[!UICONTROL Exclude URL Query Parameters]。
1. 在方塊中輸入「_bt，_bk，_bm，_bn，_bg」（減去引號）。
1. 向下捲動並按一下&#x200B;**[!UICONTROL Save]**。

   請記住，[!DNL Google Analytics]不會重新處理資料。 因此，此變更只會反映到以後，而您的過去資料仍會以bt、bk和bm引數顯示。
