---
unique-page-id: 18874755
description: 新增 [!DNL Marketo Measure] 至 [!DNL Marketo] 登陸頁面 —  [!DNL Marketo Measure]
title: 新增 [!DNL Marketo Measure] 前往Marketo登陸頁面
exl-id: 3771d4d2-8723-452a-b23d-cea3b11ab9ee
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 0%

---

# 新增 [!DNL Marketo Measure] 前往Marketo登陸頁面 {#adding-marketo-measure-to-marketo-landing-pages}

瞭解如何新增追蹤至 [!DNL Marketo Engage] 登陸頁面，因為它們需要額外的處理。 [!DNL Marketo Measure] JavaScript需要在登陸頁面和 [!DNL Marketo Engage] 表單本身。 若要這麼做，您必須載入 [!DNL Marketo Measure] JavaScript至 [!DNL Marketo Engage] 如下列方向所述。

>[!NOTE]
>
>如果您要透過標籤管理提供者(例如 [!DNL Google Tag Manager]，您不需要手動新增 [!DNL Marketo Measure] JS至 [!DNL Marketo Engage].

## 如何新增 [!DNL Marketo Measure] 編寫指令碼至 [!DNL Marketo Engage] 登陸頁面 {#how-to-add-marketo-measure-script-to-marketo-engage-landing-pages}

1. 登入您的 [!DNL Marketo Engage] 帳戶。
1. 選取您的登入頁面並按一下 **[!UICONTROL Edit Draft]**.
1. 在HTML元素中拖曳。
1. 輸入 [!DNL Marketo Measure] 將JavaScript移入 [!UICONTROL head] 區段：

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

以下熒幕擷圖中的範例

1. 按一下 **[!UICONTROL Save]**.

   ![](assets/adding-bizible-to-marketo-landing-pages-1.png)

## 其他附註 {#additional-notes}

* 您可能已具備其他追蹤程式碼片段，例如 [!DNL Google Analytics] 程式碼。 這沒有任何問題，請務必以分號加以分隔 `;` 和單一空間。 以下是這看起來像的範例：

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`

* 您可能有多個登陸頁面範本正在使用中，請務必新增程式碼至所有包含表單的範本。

* 有時在編輯登入頁面的範本時，您需要重新核准登入頁面所使用的頁面。 本文會說明 [如何大量核准](https://experienceleague.adobe.com/docs/marketo/using/product-docs/demand-generation/landing-pages/landing-page-actions/approve-multiple-landing-pages-at-once.html){target="_blank"}.
