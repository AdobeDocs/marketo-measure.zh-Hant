---
unique-page-id: 18874614
description: 含採購員接觸點的潛在客戶報表 —  [!DNL Marketo Measure]
title: 具有採購員接觸點的潛在客戶報表
exl-id: 0376abb0-5eed-41bb-ab4f-3c204ab437df
feature: Touchpoints, Reporting
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 0%

---

# 具有採購員接觸點的潛在客戶報表 {#leads-with-buyer-touchpoints-report}

>[!NOTE]
>
>您可能會看到指定&#39;&#39;的說明[!DNL Marketo Measure]&quot;，但仍請參閱&quot;[!DNL Bizible]」（在您的CRM中）。 我們正致力於更新此專案，品牌重塑將很快反映在您的CRM中。

開箱即用地提供多種報告功能，觸手可及 [!DNL Marketo Measure]，但建議您建立其他報表型別。 瞭解如何在下方使用購買者接觸點報告型別建立內含式銷售機會。

1. 瀏覽至以下專案中的設定選項： [!DNL Salesforce]. 從那裡，展開「建立」分組並選取「 」 **[!UICONTROL Report Types]**.

   ![](assets/1.jpg)

1. 選取 **[!UICONTROL New Custom Report Type]**.

   ![](assets/2.jpg)

1. 將主要物件設為「銷售機會」，並在「報表型別標籤」輸入「具有購買者接觸點的銷售機會 — 包含」中設定。 將報告儲存在「銷售機會」類別中，並將部署狀態變更為 **[!UICONTROL Deployed]**. 然後選取 **[!UICONTROL Next]**.

   ![](assets/3.jpg)

1. 針對物件關係，選取 **[!DNL Marketo Measure]人員** 物件做為次要物件。 選取A到B的關係，因為「每個&#39;A&#39;記錄必須至少有一個相關的&#39;B&#39;記錄」。 從那裡，您將會建立「購買者接觸點」物件的關係，並在B和C物件之間選取相同的關係。

   ![](assets/4.jpg)

1. 儲存並開始建立一些報告！
