---
unique-page-id: 18874797
description: 新增 [!DNL Marketo Measure] 指令碼管道 [!DNL Google Tag Manager] - [!DNL Marketo Measure]
title: 新增 [!DNL Marketo Measure] 指令碼管道 [!DNL Google Tag Manager]
exl-id: 539efb10-35cb-4146-8eea-728c3948a11e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 0%

---

# 新增 [!DNL Marketo Measure] 指令碼管道 [!DNL Google Tag Manager] {#adding-marketo-measure-script-via-google-tag-manager}

安裝時 [!DNL Marketo Measure] JavaScript，建議您最好使用 [對指令碼進行硬式編碼](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md){target="_blank"} 直接進入網站。 如果不可能，您也可以使用 [!DNL Google Tag Manager] (GTM)以載入 [!DNL Marketo Measure] JS. 請注意 [!DNL Marketo Measure] 透過GTM載入的JS容易發生延遲。 延遲會導致指令碼載入時間延遲，這可能會造成所有表單提交中約3-5%的遺失。

如果您決定透過GTM新增指令碼，請將 [!DNL Marketo Measure] 指令碼觸發順序的最高優先順序，並確保前面沒有同步指令碼 [!DNL Marketo Measure] 標籤以減少因GTM延遲所造成的影響。

>[!NOTE]
>
>使用此 [Google的支援文章](https://support.google.com/tagmanager/answer/2772421?hl=en){target="_blank"} 以進一步瞭解。

## 如何新增 [!DNL Marketo Measure] JS via [!DNL Google Tag Manager] {#how-to-add-marketo-measure-js-via-google-tag-manager}

1. 開啟GTM並新增 [!DNL Marketo Measure] 網站容器上的指令碼。 請務必選取 **[!UICONTROL Custom HTML tag]**.

1. 使用 [!DNL Marketo Measure] 編寫下方的指令碼，並將其併入您的容器中。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 按一下 **[!UICONTROL Add a Firing Rule]** 以便您指示Google將我們的程式碼片段載入 *所有頁面*.

1. 前往左側的容器草稿概觀區段。 按一下按鈕以建立容器的版本並發佈變更。
