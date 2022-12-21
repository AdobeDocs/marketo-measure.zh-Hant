---
unique-page-id: 18874783
description: 排除 [!DNL Marketo Measure] 從特定Forms - [!DNL Marketo Measure]  — 產品檔案
title: 排除 [!DNL Marketo Measure] 從特定Forms
exl-id: ce39a3b2-2ac6-4385-b6d1-3c36b51c03fa
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 0%

---

# 排除 [!DNL Marketo Measure] 從特定Forms {#excluding-marketo-measure-from-specific-forms}

依預設， [!DNL Marketo Measure] 會附加至您網站上的所有表單。 不過，並非所有表單提交都應受到追蹤，或納入歸因模型中。 這是因為並非所有表單填寫都被視為「好」。 例如，取消訂閱頁面/表單。 此外，系統通常不會追蹤登入表單，因為這會稀釋歸因模型。

## 如何新增 [!DNL Marketo Measure] — 排除代碼：  {#how-to-add-marketo-measure-exclude-code}

防止 [!DNL Marketo Measure] 從追蹤特定表單，只需新增「[!DNL Bizible-Exclude]」作為表單上的「類」。 代碼如下：

`<form id="myForm" action="/Home/TestPage" method="POST" class="Bizible-Exclude">`
