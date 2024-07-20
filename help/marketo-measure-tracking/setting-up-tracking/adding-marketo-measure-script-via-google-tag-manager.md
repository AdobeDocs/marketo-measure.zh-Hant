---
unique-page-id: 18874797
description: 正在透過 [!DNL Google Tag Manager] - [!DNL Marketo Measure]新增 [!DNL Marketo Measure] 指令碼
title: 正在透過 [!DNL Google Tag Manager]新增 [!DNL Marketo Measure] 指令碼
exl-id: 539efb10-35cb-4146-8eea-728c3948a11e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 0%

---

# 透過[!DNL Google Tag Manager]新增[!DNL Marketo Measure]指令碼 {#adding-marketo-measure-script-via-google-tag-manager}

安裝[!DNL Marketo Measure] JavaScript時，建議您[直接將指令碼](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md){target="_blank"}硬式編碼至網站。 如果無法這樣做，您也可以使用[!DNL Google Tag Manager] (GTM)來載入[!DNL Marketo Measure] JS。 請注意，透過GTM載入的[!DNL Marketo Measure] JS容易發生延遲。 延遲會導致指令碼載入時間延遲，這可能會造成所有表單提交中約3-5%的遺失。

如果您決定透過GTM新增指令碼，請將[!DNL Marketo Measure]指令碼設為觸發順序中的最高優先順序，並確保[!DNL Marketo Measure]標籤前面沒有同步指令碼，以減少GTM延遲的影響。

>[!NOTE]
>
>使用此[Google的支援文章](https://support.google.com/tagmanager/answer/2772421?hl=en){target="_blank"}瞭解更多資訊。

## 如何透過[!DNL Google Tag Manager]新增[!DNL Marketo Measure] JS {#how-to-add-marketo-measure-js-via-google-tag-manager}

1. 開啟GTM並在您的網站容器上新增[!DNL Marketo Measure]指令碼。 請務必選取&#x200B;**[!UICONTROL Custom HTML tag]**。

1. 使用以下的[!DNL Marketo Measure]指令碼，並將其合併到您的容器中。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 按一下「**[!UICONTROL Add a Firing Rule]**」，以便讓Google在&#x200B;*所有頁面*&#x200B;上載入我們的程式碼片段。

1. 前往左側的容器草稿概觀區段。 按一下按鈕以建立容器的版本並發佈變更。
