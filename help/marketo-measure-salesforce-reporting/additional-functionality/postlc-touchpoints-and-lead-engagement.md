---
unique-page-id: 18874562
description: PostLC接觸點和Lead Engagement - Marketo Measure — 產品檔案
title: PostLC接觸點與潛在客戶參與
exl-id: 3ee5c571-195e-46c7-b150-fedcbc3614cb
feature: Touchpoints
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# PostLC接觸點與潛在客戶參與 {#postlc-touchpoints-and-lead-engagement}

[!DNL Marketo Measure]潛在客戶建立後(PostLC)接觸點可供使用多重接觸歸因模型（W-Shape和以上版本）的客戶使用。 當銷售機會或聯絡人返回您的網站並繼續填寫表單時，這些表單提交將註冊為PostLC接觸點。 這些接觸點可讓您檢視哪些內容推動Lead在首次轉換很久之後繼續參與您的網站。 PostLC接觸點與Opportunity內的所有中介接觸點分享歸因評分；10%的歸因評分會分配給中介接觸點，並在所有接觸之間平均分配。

![](assets/1.png)

您可以調整[!DNL SFDC]中顯示的PostLC接觸點數目。 通常我們建議最多推送五個PostLC接觸點；每個接觸點在[!DNL SFDC]中會佔用1 KB。

>[!NOTE]
>
>本文結尾提供了如何調整PostLC接觸點設定的說明。

PostLC接觸點是動態的。 當銷售機會或連絡人繼續提交PostLC表單時，[!DNL Marketo Measure]會更新您CRM中的PostLC接觸點，以顯示他們最近提交的表單。 具體來說，如果您已設定5個PostLC接觸點的限制，[!DNL Marketo Measure]一律會將五個&#x200B;_最近_&#x200B;個接觸點推送至您的CRM。  在此範例中，此帳戶已將其PostLC限制設為四個接觸點。 此銷售機會已達到其CRM中可以擁有的最大PostLC接觸點數量。 最後一次PostLC觸控時間為2018年2月6日。 如果此人於隔天填寫其他表格，[!DNL Marketo Measure]將會從2017年9月11日移除第一個PostLC接觸點，以從2018年7月2日新增最新的接觸點。

![](assets/2.png)

>[!NOTE]
>
>[!DNL Marketo Measure]只會更新Lead或Contact上的PostLC接觸點，不會更新Opportunity上的PostLC歸因接觸點。 Contact的所有相關PostLC接觸點都包含在Opportunity中。

## 如何變更PostLC接觸點設定 {#how-to-change-postlc-touchpoint-settings}

若要調整潛在客戶或連絡人的PostLC接觸點設定，請遵循下列指示。

**個銷售機會**

1. 在[experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}登入您的[!DNL Marketo Measure]帳戶並移至[!UICONTROL Settings]。

1. 在CRM底下，選取&#x200B;**[!UICONTROL Leads]**。

1. 輸入您要推送至銷售機會的postLC接觸點數目，然後按一下&#x200B;**[!UICONTROL Save]**。

   ![](assets/3.png)

**連絡人**

1. 在[experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}登入您的[!DNL Marketo Measure]帳戶並移至[!UICONTROL Settings]。

1. 在CRM底下，選取&#x200B;**[!UICONTROL Contacts]**。

1. 輸入您要推送至連絡人的postLC接觸點數目，然後按一下&#x200B;**[!UICONTROL Save]**。

   ![](assets/4.png)
