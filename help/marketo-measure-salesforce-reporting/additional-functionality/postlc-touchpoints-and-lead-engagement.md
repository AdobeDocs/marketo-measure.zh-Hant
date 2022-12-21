---
unique-page-id: 18874562
description: PostLC接觸點和潛在客戶參與 — Marketo測量 — 產品檔案
title: PostLC接觸點和銷售機會參與
exl-id: 3ee5c571-195e-46c7-b150-fedcbc3614cb
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 0%

---

# PostLC接觸點和銷售機會參與 {#postlc-touchpoints-and-lead-engagement}

[!DNL Marketo Measure] 使用多點接觸歸因模型（W型及以上）的客戶，可使用建立銷售機會後(PostLC)接觸點。 當銷售機會或連絡人返回您的網站並繼續填寫表單時，這些表單提交作業將註冊為PostLC接觸點。 這些接觸點可讓您查看哪些內容促使銷售機會在首次轉換後很久，繼續與您的網站互動。 PostLC接觸點與Opportunity內的所有中介接觸點共用歸因評分；10%的歸因評分會分配給中介接觸點，並在所有接觸之間平均分配。

![](assets/1.png)

您可以調整顯示在 [!DNL SFDC]. 通常，我們建議最多推送5個PostLC接觸點；每個接觸點佔用1KB的 [!DNL SFDC].

>[!NOTE]
>
>如需如何調整PostLC接觸點設定的說明，請參閱本文結尾。

PostLC接觸點為動態。 由於銷售機會或聯繫人繼續提交PostLC表單， [!DNL Marketo Measure] 會更新您CRM中的PostLC接觸點，以顯示其最新提交的表單。 具體來說，如果您已設定5個PostLC接觸點的限制， [!DNL Marketo Measure] 總是按5 _最近_ CRM的接觸點。  在此範例中，此帳戶已將其PostLC限制設為四個接觸點。 此銷售機會已達到可在CRM中擁有的PostLC接觸點數目上限。 上次PostLC接觸是在2/6/2018。 如果這人第二天要填另一張表格， [!DNL Marketo Measure] 將從11/9/2017中移除第一個PostLC接觸點，以便從2/7/2018中新增最新接觸點。

![](assets/2.png)

>[!NOTE]
>
>[!DNL Marketo Measure] 只會更新銷售機會或連絡人上的PostLC接觸點，不會更新Opportunity上的PostLC歸因接觸點。 Opportunity中將包括Contact上所有相關的PostLC接觸點。

## 如何更改PostLC接觸點設定 {#how-to-change-postlc-touchpoint-settings}

要調整Lead或Contact的PostLC接觸點設定，請按照以下說明操作。

**銷售機會**

1. 登入 [!DNL Marketo Measure] 帳戶 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target=&quot;_blank&quot;}，轉到 [!UICONTROL Settings].

1. 在CRM下，選擇 **[!UICONTROL Leads]**.

1. 輸入您要推送至銷售機會的postLC接觸點數目，然後按一下 **[!UICONTROL Save]**.

   ![](assets/3.png)

**聯繫人**

1. 登入 [!DNL Marketo Measure] 帳戶 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target=&quot;_blank&quot;}，轉到 [!UICONTROL Settings].

1. 在CRM下，選擇 **[!UICONTROL Contacts]**.

1. 輸入要推送到聯繫人的postLC接觸點數，然後按一下 **[!UICONTROL Save]**.

   ![](assets/4.png)
