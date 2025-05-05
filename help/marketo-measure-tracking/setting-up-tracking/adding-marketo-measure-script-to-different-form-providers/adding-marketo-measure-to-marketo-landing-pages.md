---
unique-page-id: 18874755
description: 正在新增 [!DNL Marketo Measure] 至 [!DNL Marketo] 登陸頁面 —  [!DNL Marketo Measure]
title: 正在新增 [!DNL Marketo Measure] 至Marketo登陸頁面
exl-id: 3771d4d2-8723-452a-b23d-cea3b11ab9ee
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# 正在新增[!DNL Marketo Measure]至Marketo登陸頁面 {#adding-marketo-measure-to-marketo-landing-pages}

瞭解如何在[!DNL Marketo Engage]登陸頁面需要其他處理時新增追蹤。 登陸頁面和[!DNL Marketo Engage]表單本身都必須有[!DNL Marketo Measure] JavaScript。 若要這麼做，您必須依照下列指示，將[!DNL Marketo Measure] JavaScript載入[!DNL Marketo Engage]。

>[!NOTE]
>
>如果您是透過[!DNL Google Tag Manager]等標籤管理提供者部署JavaScript，則不需要手動新增[!DNL Marketo Measure] JS至[!DNL Marketo Engage]。

## 如何將[!DNL Marketo Measure]指令碼新增至[!DNL Marketo Engage]登陸頁面 {#how-to-add-marketo-measure-script-to-marketo-engage-landing-pages}

1. 登入您的[!DNL Marketo Engage]帳戶。
1. 選取您的登入頁面並按一下&#x200B;**[!UICONTROL Edit Draft]**。
1. 在HTML元素中拖曳。
1. 在[!UICONTROL head]區段中輸入[!DNL Marketo Measure] JavaScript：

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

以下熒幕擷圖中的範例

1. 按一下&#x200B;**[!UICONTROL Save]**。

   ![](assets/adding-bizible-to-marketo-landing-pages-1.png)

## 其他附註 {#additional-notes}

* 您可能已有其他追蹤程式碼片段，例如[!DNL Google Analytics]程式碼。 這沒有任何問題，請務必以分號`;`和單一空格分隔。 以下是這看起來像的範例：

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`

* 您可能有多個登陸頁面範本正在使用中，請務必新增程式碼至所有包含表單的範本。

* 有時當您編輯登入頁面的範本時，必須重新核准登入頁面所使用的頁面。 本文說明[如何大量核准](https://experienceleague.adobe.com/docs/marketo/using/product-docs/demand-generation/landing-pages/landing-page-actions/approve-multiple-landing-pages-at-once.html?lang=zh-Hant){target="_blank"}。
