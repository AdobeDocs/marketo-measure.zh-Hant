---
unique-page-id: 18874783
description: 正在從特定Forms排除 [!DNL Marketo Measure]  - [!DNL Marketo Measure]
title: 正在從特定Forms中排除 [!DNL Marketo Measure]
exl-id: ce39a3b2-2ac6-4385-b6d1-3c36b51c03fa
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 0%

---

# 正在從特定Forms排除[!DNL Marketo Measure] {#excluding-marketo-measure-from-specific-forms}

根據預設，[!DNL Marketo Measure]會附加至您網站上的所有表單。 不過，並非所有表單提交都必然會進行追蹤或納入歸因模型。 這是因為並非所有表單填寫都視為「良好」。 例如，取消訂閱頁面/表單。 此外，系統通常不會追蹤登入表單，因為這會稀釋歸因模型。

## 如何新增[!DNL Marketo Measure] — 排除程式碼：  {#how-to-add-marketo-measure-exclude-code}

若要防止[!DNL Marketo Measure]追蹤特定表單，只需在您的表單上新增&quot;[!DNL Bizible-Exclude]&quot;為「類別」即可。 程式碼如下：

`<form id="myForm" action="/Home/TestPage" method="POST" class="Bizible-Exclude">`
