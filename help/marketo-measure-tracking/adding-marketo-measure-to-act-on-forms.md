---
description: 新增[!DNL Marketo Measure]至Marketo Measure使用者的實際Forms指引
title: 正在新增[!DNL Marketo Measure]至Act-On Forms
exl-id: 3d246e6a-ad3b-4683-b2b7-ab3f0f4c5ab2
feature: Tracking
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
    internal-label: Marketo Measure
feature_v2:
  - id: dcbeff6e-0253-5a4b-9ac2-1b67cc4a6286
    internal-label: Tracking
source-git-commit: 940fee4abd0e09b6bf513b5e7526d3c242bd31c7
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 0%
---
# 正在新增[!DNL Marketo Measure]至Act-On Forms {#adding-marketo-measure-to-act-on-forms}

## 方向 {#directions}

1. 在您編輯的表單中，選取右上角的&#x200B;**[!UICONTROL Settings]**&#x200B;選項。
1. 尋找標示為[!UICONTROL "External Web Analytics."]的區域。您會在此處放置[!DNL Marketo Measure]追蹤程式碼片段。

## [!DNL Marketo Measure] JavaScript {#marketo-measure-javascript}

`script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

>[!NOTE]
>
>此區域可能已有其他追蹤程式碼片段，例如[!DNL Google Analytics]程式碼。 請務必使用分號`;`和單一空格來分隔，如下所示：
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>**; **<script async="true" type="someothercode" src="someotherfile.js" ></script>`
