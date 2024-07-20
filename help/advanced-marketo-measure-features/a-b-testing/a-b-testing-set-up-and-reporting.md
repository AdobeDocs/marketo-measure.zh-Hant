---
unique-page-id: 18874773
description: A/B測試設定與報告 —  [!DNL Marketo Measure]
title: A/B測試設定與報告
exl-id: 9a3f0731-5909-4fbf-a35a-9608ff561061
feature: A/B Testing
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 0%

---

# A/B測試設定與報告 {#a-b-testing-set-up-and-reporting}

[!DNL Marketo Measure] A/B測試整合可讓您以最佳化方式[追蹤](https://www.optimizely.com/){target="_blank"}和VWO網站實驗的收入影響。 本文提供如何將[!DNL Marketo Measure]個A/B測試區段新增至銷售機會、[!UICONTROL Contact]、大小寫和[!UICONTROL Opportunity]頁面配置的指示。 也涵蓋一般報告實務和執行[!DNL Marketo Measure] A/B報告型別的建議。

## 設定 {#set-up}

新增潛在客戶、連絡人、案例和機會的[!DNL Marketo Measure]個A/B測試區段。 [!DNL Marketo Measure] A/B測試整合可讓您以最佳化方式追蹤[VWO](https://vwo.com/){target="_blank"}和[VWO{target="_blank"}網站實驗的收入影響。](https://www.optimizely.com/)

1. 請確認您正在使用封裝[!DNL Marketo Measure] v3.9或更新版本。 您可以前往「[!UICONTROL Salesforce] >[!UICONTROL Set Up] > [!UICONTROL Installed packages]」進行此作業。
1. 編輯銷售機會頁面配置，並將&#x200B;**[!DNL Marketo Measure]A/B測試**&#x200B;相關清單新增至頁面。

   ![](assets/1.png)

1. 按一下[!UICONTROL Wrench]按鈕。 從所選欄位清單中移除庫存「Id」欄位。 新增&#x200B;**[!UICONTROL Experiment]**、**[!UICONTROL Variation]**&#x200B;和&#x200B;**[!UICONTROL DateReported]**&#x200B;欄位。 將「[!UICONTROL Sort by]」變更為&#x200B;**[!UICONTROL Date Reported]**，然後在下拉式清單中選取&#x200B;**[!UICONTROL Descending]**。

   ![](assets/2.png)

1. 在[!UICONTROL Buttons]底下，取消核取&#x200B;**[!UICONTROL New]**。

   ![](assets/3.png)

1. 請連絡您的[!DNL Marketo Measure]代表或[Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}以啟用此功能。

## 報告 {#reporting}

客戶可以存取一些[!DNL Marketo Measure]個A/B報告型別，這些報告型別允許您報告與銷售機會、聯絡人和機會有關的A/B測試：

* [!DNL Marketo Measure]個A/B測試集
* 與連絡人進行[!DNL Marketo Measure]個A/B測試
* 有潛在客戶的[!DNL Marketo Measure]個A/B測試集
* [!DNL Marketo Measure]個具有商機的A/B測試集

![](assets/4.png)

A/B報告型別用於報告哪些Lead或Contact或Opportunity已接受A/B測試。 這些報表也會顯示和遭受A/B測試的Opportunity相關聯的收入金額。

請務必注意，「最佳化/VWO」是內容變異平台，而非行銷管道。 因此，這[!DNL Marketo Measure] A/B報告型別與Buyer Touchpoint報告使用方式不同。 購買者接觸點報表型別是用來瞭解哪些行銷管道（付費廣告、網路直接、社交）將「銷售機會」或「連絡人」帶往特定頁面。 但是，[!DNL Marketo Measure] A/B報告型別無法用於報告變異如何影響Lead或Opportunity。 由於A/B測試變數不是管道，因此變數的詳細資訊不會顯示在購買者接觸點上。

以下是報告A/B測試時建議使用的一些欄位，有助於提高清晰度和深入分析：

* 潛在客戶已轉換
* 實驗
* 實驗ID
* 變數
* 變數ID
* 報告日期

## [!DNL Salesforce]範例報告 {#salesforce-example-reports}

**[!DNL Marketo Measure]個A/B測試與潛在客戶**

![](assets/5.png)

**[!DNL Marketo Measure]個A/B測試與機會**

![](assets/6.png)
