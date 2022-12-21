---
unique-page-id: 18874755
description: 新增 [!DNL Marketo Measure] to [!DNL Marketo] 登陸頁面 —  [!DNL Marketo Measure]  — 產品檔案
title: 新增 [!DNL Marketo Measure] 至Marketo登陸頁面
exl-id: 3771d4d2-8723-452a-b23d-cea3b11ab9ee
source-git-commit: 82cc8269bfdb26b6acf039d0ce0e06564f5e2612
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---

# 新增 [!DNL Marketo Measure] 至Marketo登陸頁面 {#adding-marketo-measure-to-marketo-landing-pages}

了解如何將追蹤新增至 [!DNL Marketo Engage] 登錄頁面，因為這些頁面需要其他處理。 [!DNL Marketo Measure] JavaScript必須同時位於登陸頁面和 [!DNL Marketo Engage] 形成。 若要這麼做，您必須載入 [!DNL Marketo Measure] JavaScript整合至 [!DNL Marketo Engage] 如下列指示所述。

>[!NOTE]
>
>如果您是透過標籤管理提供者(例如 [!DNL Google Tag Manager]，您不需要手動新增 [!DNL Marketo Measure] JS至 [!DNL Marketo Engage].

## 如何新增 [!DNL Marketo Measure] 指令碼至 [!DNL Marketo Engage] 登錄頁面 {#how-to-add-marketo-measure-script-to-marketo-engage-landing-pages}

1. 登入 [!DNL Marketo Engage] 帳戶。
1. 選取您的登錄頁面，然後按一下 **[!UICONTROL Edit Draft]**.
1. 拖曳至HTML元素。
1. 輸入 [!DNL Marketo Measure] JavaScript匯入 [!UICONTROL head] 小節：

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

下方螢幕擷取範例

1. 按一下 **[!UICONTROL Save]**.

   ![](assets/adding-bizible-to-marketo-landing-pages-1.png)

## 其他附註 {#additional-notes}

* 您可能已有其他追蹤程式碼片段，例如 [!DNL Google Analytics] 程式碼。 這沒問題，只要以分號分隔即可 `;` 和一個空間。 以下是其外觀的範例：

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`

* 您可能有多個使用中的登錄頁面範本，請務必將程式碼新增至所有有表單的範本。

* 有時候，當您編輯登錄頁面的範本時，您需要重新核准登錄頁面所使用的頁面。 本文說明 [如何成批批准](https://experienceleague.adobe.com/docs/marketo/using/product-docs/demand-generation/landing-pages/landing-page-actions/approve-multiple-landing-pages-at-once.html){target=&quot;_blank&quot;}。
