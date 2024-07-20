---
unique-page-id: 18874753
description: 正在新增 [!DNL Marketo Measure] 至實際執行Forms - [!DNL Marketo Measure]
title: 正在新增 [!DNL Marketo Measure] 至實際執行Forms
exl-id: 3d246e6a-ad3b-4683-b2b7-ab3f0f4c5ab2
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '72'
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
