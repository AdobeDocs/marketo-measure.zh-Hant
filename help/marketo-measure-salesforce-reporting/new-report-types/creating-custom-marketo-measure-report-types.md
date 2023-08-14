---
unique-page-id: 18874539
description: 建立自訂 [!DNL Marketo Measure] 報表型別 —  [!DNL Marketo Measure]  — 產品檔案
title: 建立自訂 [!DNL Marketo Measure] 報表型別
exl-id: 1d72a04f-6a2d-4607-ad09-3b025125156a
feature: Reporting
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 0%

---

# 建立自訂 [!DNL Marketo Measure] 報表型別 {#creating-custom-marketo-measure-report-types}

>[!NOTE]
>
>您可能會看到指定&#39;&#39;的說明[!DNL Marketo Measure]&quot;，但仍請參閱&quot;[!DNL Bizible]」（在您的CRM中）。 我們正致力於更新此專案，品牌重塑將很快反映在您的CRM中。

瞭解如何建立自訂 [!DNL Marketo Measure] [!DNL Salesforce] 報表型別。 我們建議您建立三種不同的報表型別：具有購買者接觸點的銷售機會（自訂）、 [!DNL Marketo Measure] 具有購買者接觸點（自訂）的人員，具有購買者歸因接觸點（自訂）的機會。

## 具有購買者接觸點的銷售機會（自訂） {#leads-with-buyer-touchpoints-custom}

1. 前往 **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]**.

   ![](assets/1.png)

1. 定義自訂報表型別。

   * [!UICONTROL Report Type Focus] > [!UICONTROL [!UICONTROL Primary Object]]：銷售機會
   * 識別> [!UICONTROL Report Type Label]：具有購買者接觸點的銷售機會（自訂）
   * [!UICONTROL Store in Category]：其他報表
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]：已部署

   ![](assets/2.png)

1. 定義物件關係。

   * 將Lead物件(A)與 [!DNL Marketo Measure] 人員物件(B)，然後移至購買者接觸點物件(C)
   * 請確定&quot;[!UICONTROL Each A/B record must have at least one B/C]已選取「記錄」
   * [!UICONTROL Save]

   ![](assets/3.png)

## [!DNL Marketo Measure] 有購買者接觸點的人員（自訂） {#marketo-measure-person-with-buyer-touchpoints-custom}

1. 前往 **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]**.

   ![](assets/4.png)

1. 定義自訂報表型別。

   * [!UICONTROL Report Type Focus] > [!UICONTROL Primary Object]： [!DNL Marketo Measure] 人員
   * [!UICONTROL Identification] > [!UICONTROL Report Type Label]： [!DNL Marketo Measure] 有購買者接觸點的人員（自訂）
   * [!UICONTROL Store in Category]：其他報表
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]：已部署

   ![](assets/5.png)

1. 定義物件關係。

   * 建立關聯 [!DNL Marketo Measure] 個人物件(A)和購買者接觸點物件(B)
   * 請確定&quot;[!UICONTROL Each A record must have at least one B]已選取「記錄」
   * [!UICONTROL Save]

   ![](assets/6.png)

## 有購買者歸因接觸點的商機（自訂） {#opportunities-with-buyer-attribution-touchpoint-custom}

1. 前往 **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]**.

   ![](assets/7.png)

1. 定義自訂報表型別。

   * [!UICONTROL Report Type Focus] > [!UICONTROL Primary Object]: 機會
   * [!UICONTROL Identification] > [!UICONTROL Report Type Label]：有購買者歸因接觸點的機會（自訂）
   * [!UICONTROL Store in Category]：其他報表
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]：已部署

   ![](assets/8.png)

1. 定義物件關係。

   * 將商機物件(A)與購買者歸因接觸點物件(B)建立關聯
   * 請確定&quot;[!UICONTROL Each A record must have at least one B]已選取「記錄」
   * [!UICONTROL Save]

   ![](assets/9.png)

## 新增自訂欄位至自訂報表型別 {#adding-custom-fields-to-custom-report-types}

1. 建立報告後，您將被重新導向至報告型別的概觀。 按一下 **[!UICONTROL Edit Layout]**.

   ![](assets/10.png)

1. 確認您要新增至報表的自訂欄位會出現在欄位配置屬性區段中。 如果您想要新增任何其他欄位，請使用&quot;[!UICONTROL Add fields related via lookup]」選項。

   ![](assets/11.png)
