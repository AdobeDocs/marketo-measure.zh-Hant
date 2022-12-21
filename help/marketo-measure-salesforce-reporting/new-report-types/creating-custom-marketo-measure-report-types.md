---
unique-page-id: 18874539
description: 建立自訂 [!DNL Marketo Measure] 報表類型 —  [!DNL Marketo Measure]  — 產品檔案
title: 建立自訂 [!DNL Marketo Measure] 報表類型
exl-id: 1d72a04f-6a2d-4607-ad09-3b025125156a
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 0%

---

# 建立自訂 [!DNL Marketo Measure] 報表類型 {#creating-custom-marketo-measure-report-types}

>[!NOTE]
>
>您可能會看到指定「[!DNL Marketo Measure]」，但仍請參閱「[!DNL Bizible]」。 我們正致力更新該更新，品牌重塑將很快反映在您的CRM中。

了解如何建立自訂 [!DNL Marketo Measure] [!DNL Salesforce] 報表類型。 建議您建立三種不同的報表類型：具有購買者接觸點（自訂）的銷售機會 [!DNL Marketo Measure] 具有購買者接觸點的人員（自訂）、具有購買者歸因接觸點的商機（自訂）。

## 具有購買者接觸點的銷售機會（自訂） {#leads-with-buyer-touchpoints-custom}

1. 前往 **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]**.

   ![](assets/1.png)

1. 定義自訂報表類型。

   * [!UICONTROL Report Type Focus] > [!UICONTROL [!UICONTROL Primary Object]]:銷售機會
   * 身分識別> [!UICONTROL Report Type Label]:具有購買者接觸點的銷售機會（自訂）
   * [!UICONTROL Store in Category]:其他報表
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]:已部署

   ![](assets/2.png)

1. 定義對象關係。

   * 將銷售線對象(A)與 [!DNL Marketo Measure] 人員對象(B)，然後到採購員接觸點對象(C)
   * 確保「[!UICONTROL Each A/B record must have at least one B/C]&quot;記錄已選擇
   * [!UICONTROL Save]

   ![](assets/3.png)

## [!DNL Marketo Measure] 具有購買者接觸點的人員（自訂） {#marketo-measure-person-with-buyer-touchpoints-custom}

1. 前往 **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]**.

   ![](assets/4.png)

1. 定義自訂報表類型。

   * [!UICONTROL Report Type Focus] > [!UICONTROL Primary Object]: [!DNL Marketo Measure] 人員
   * [!UICONTROL Identification] > [!UICONTROL Report Type Label]: [!DNL Marketo Measure] 具有購買者接觸點的人員（自訂）
   * [!UICONTROL Store in Category]:其他報表
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]:已部署

   ![](assets/5.png)

1. 定義對象關係。

   * 關聯 [!DNL Marketo Measure] 人員對象(A)到購買者接觸點對象(B)
   * 確保「[!UICONTROL Each A record must have at least one B]&quot;記錄已選擇
   * [!UICONTROL Save]

   ![](assets/6.png)

## 購買者歸因接觸點商機（自訂） {#opportunities-with-buyer-attribution-touchpoint-custom}

1. 前往 **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]**.

   ![](assets/7.png)

1. 定義自訂報表類型。

   * [!UICONTROL Report Type Focus] > [!UICONTROL Primary Object]: 機會
   * [!UICONTROL Identification] > [!UICONTROL Report Type Label]:購買者歸因接觸點商機（自訂）
   * [!UICONTROL Store in Category]:其他報表
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]:已部署

   ![](assets/8.png)

1. 定義對象關係。

   * 將Opportunity對象(A)與Buyer Attribution接觸點對象(B)相關聯
   * 確保「[!UICONTROL Each A record must have at least one B]&quot;記錄已選擇
   * [!UICONTROL Save]

   ![](assets/9.png)

## 新增自訂欄位至自訂報表類型 {#adding-custom-fields-to-custom-report-types}

1. 建立報表後，系統會將您重新導向至報表類型的概觀。 按一下 **[!UICONTROL Edit Layout]**.

   ![](assets/10.png)

1. 請確定您要新增至報表的自訂欄位出現在「欄位配置屬性」區段中。 如果您想要新增任何其他欄位，請使用「[!UICONTROL Add fields related via lookup]」。

   ![](assets/11.png)
