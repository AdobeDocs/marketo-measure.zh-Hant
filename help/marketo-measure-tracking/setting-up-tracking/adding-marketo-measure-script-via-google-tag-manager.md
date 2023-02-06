---
unique-page-id: 18874797
description: 新增 [!DNL Marketo Measure] 指令碼 [!DNL Google Tag Manager] - [!DNL Marketo Measure]  — 產品檔案
title: 新增 [!DNL Marketo Measure] 指令碼 [!DNL Google Tag Manager]
exl-id: 539efb10-35cb-4146-8eea-728c3948a11e
source-git-commit: 82cc8269bfdb26b6acf039d0ce0e06564f5e2612
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 0%

---

# 新增 [!DNL Marketo Measure] 指令碼 [!DNL Google Tag Manager] {#adding-marketo-measure-script-via-google-tag-manager}

安裝 [!DNL Marketo Measure] javascript，我們強烈建議 [硬編碼指令碼](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md){target="_blank"} 直接進入您的網站。 不過，如果無法這麼做，您也可以使用 [!DNL Google Tag Manager] (GTM)載入 [!DNL Marketo Measure] JS. 請注意 [!DNL Marketo Measure] 透過GTM載入的JS容易發生延遲。 延遲會導致指令碼載入時間延遲，而可能導致所有表單提交數中缺少約3-5%。

若您決定透過GTM新增指令碼，請設定 [!DNL Marketo Measure] 指令碼，以引發順序中的最高優先順序，並確保在 [!DNL Marketo Measure] 標籤，以減少GTM延遲的任何影響。

>[!NOTE]
>
>請使用此 [Google支援文章](https://support.google.com/tagmanager/answer/2772421?hl=en){target="_blank"} 了解更多。

## 如何新增 [!DNL Marketo Measure] JS透過 [!DNL Google Tag Manager] {#how-to-add-marketo-measure-js-via-google-tag-manager}

1. 開啟GTM並新增 [!DNL Marketo Measure] 指令碼。 請務必選取 **[!UICONTROL Custom HTML tag]**.

1. 使用 [!DNL Marketo Measure] 並將其併入容器中。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 按一下 **[!UICONTROL Add a Firing Rule]** 讓Google在 *所有頁面*.

1. 前往左側的「容器草稿概觀」區段。 按一下按鈕以建立新版本的容器並發佈變更。
