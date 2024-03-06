---
unique-page-id: 18874634
description: 我的報告中的重複記錄 —  [!DNL Marketo Measure]
title: 我的報告中的重複記錄
exl-id: 4ee42371-5b67-4c69-9b49-3249f33614d0
feature: Reporting
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# 我的報告中的重複記錄 {#duplicate-records-in-my-report}

>[!NOTE]
>
>您可能會看到指定&#39;&#39;的說明[!DNL Marketo Measure]&quot;，但仍請參閱&quot;[!DNL Bizible]」（在您的CRM中）。 我們正致力於更新此專案，品牌重塑將很快反映在您的CRM中。

當您深入瞭解 [!DNL Marketo Measure] 中的報表 [!DNL Salesforce]，您可能會開始在報表中找到「重複」記錄。 您可能在檢閱時體驗到這種感覺 [!DNL Marketo Measure] 現成可用的報表。

使用「採購員接觸點」物件或「採購員歸因接觸點」物件進行報告時，請務必瞭解您不再報告銷售機會、聯絡人或商機的數量，而是報告與這些標準物件（銷售機會、聯絡人、商機）相關的「採購員接觸點」或「採購員歸因接觸點」的數量。

以下列報表為例：

這是 **與購買者接觸點的連絡人** 報告。 同樣地，這表示我們檢視的是與個別聯絡人相關聯的接觸點計數。

![](assets/1.gif)

如您所見，報表中似乎有三個James Williams聯絡人，因此您可能會想「重複！」

不過，此報表會顯示與James相關的接觸點數量。 在報表中，您可以看到James有個別的FT （首次接觸）、個別的LC、Form （潛在客戶建立接觸）和PostLC接觸點（在LC接觸點之後發生的表單提交）。

如果您想要瞭解「聯絡人計數」，則可以使用「計數 — 首次接觸」、「計數 — 銷售機會建立接觸」或「計數 — U形」欄位，瞭解有多少聯絡人曾經進行行銷互動。

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] 大學：庫存SFDC報表](https://universityonline.marketo.com/courses/bizible-fundamentals-bizible-102/#/page/5c5cb68dfb384d0c9fb96cc4)
