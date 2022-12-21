---
unique-page-id: 18874753
description: 新增 [!DNL Marketo Measure] Forms。 [!DNL Marketo Measure]  — 產品檔案
title: 新增 [!DNL Marketo Measure] 到Forms
exl-id: 3d246e6a-ad3b-4683-b2b7-ab3f0f4c5ab2
source-git-commit: b910e5aedb9e178058f7af9a6907a1039458ce7a
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 0%

---

# 新增 [!DNL Marketo Measure] 到Forms {#adding-marketo-measure-to-act-on-forms}

## 方向 {#directions}

1. 在您編輯的表單中，選取 **[!UICONTROL Settings]** 選項。
1. 查找標籤為 [!UICONTROL "External Web Analytics."] 這是您放置 [!DNL Marketo Measure] 追蹤程式碼片段。

## [!DNL Marketo Measure] JavaScript {#marketo-measure-javascript}

`script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

>[!NOTE]
>
>此區域中可能已有其他追蹤程式碼片段，例如 [!DNL Google Analytics] 程式碼。 請務必使用分號加以分隔 `;` 一個空間，就這樣：
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>**; **<script async="true" type="someothercode" src="someotherfile.js" ></script>`
