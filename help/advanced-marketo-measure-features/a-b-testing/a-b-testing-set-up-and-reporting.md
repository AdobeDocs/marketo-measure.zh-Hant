---
unique-page-id: 18874773
description: A/B測試設定和報告 —  [!DNL Marketo Measure]  — 產品檔案
title: A/B測試設定和報告
exl-id: 9a3f0731-5909-4fbf-a35a-9608ff561061
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---

# A/B測試設定和報告 {#a-b-testing-set-up-and-reporting}

此 [!DNL Marketo Measure] A/B測試整合可讓您追蹤 [最佳化](https://optimizely.com/){target=&quot;_blank&quot;}和VWO網站實驗。 本文章指南提供如何新增 [!DNL Marketo Measure] A/B測試區段至銷售機會， [!UICONTROL Contact]、案例和 [!UICONTROL Opportunity] 頁面配置。 我們還將介紹一般報告做法和運行建議 [!DNL Marketo Measure] A/B報表類型。

## 設定 {#set-up}

新增 [!DNL Marketo Measure] A/B測試區段，包括銷售機會、連絡人、案例和機會。 [!DNL Marketo Measure] A/B測試整合可讓您追蹤 [最佳化](https://optimizely.com/){target=&quot;_blank&quot;}和 [VWO](https://vwo.com/){target=&quot;_blank&quot;}網站實驗。

1. 確認您使用套件 [!DNL Marketo Measure] v3.9或更新版本。 您可以前往 [!UICONTROL Salesforce] >[!UICONTROL Set Up] > [!UICONTROL Installed packages].
1. 編輯銷售機會頁面版面並新增 **[!DNL Marketo Measure]A/B測試** 頁面的相關清單。

   ![](assets/1.png)

1. 按一下 [!UICONTROL Wrench] 按鈕。 從「選定」欄位清單中刪除「Id」欄位。 新增 **[!UICONTROL Experiment]**, **[!UICONTROL Variation]**，和 **[!UICONTROL DateReported]** 欄位。 更改&quot;[!UICONTROL Sort by]&quot; **[!UICONTROL Date Reported]**，然後選取 **[!UICONTROL Descending]** 中。

   ![](assets/2.png)

1. 在 [!UICONTROL Buttons]，取消勾選 **[!UICONTROL New]**.

   ![](assets/3.png)

1. 請連絡您的 [!DNL Marketo Measure] 代表或 [Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;}啟用此功能。

## 報表 {#reporting}

客戶可以存取 [!DNL Marketo Measure] A/B報表類型，允許您報告與銷售機會、聯繫人和業務機會相關的A/B測試：

* [!DNL Marketo Measure] A/BTest
* [!DNL Marketo Measure] 具有聯繫人的A/BTest
* [!DNL Marketo Measure] A/BTests與Lead
* [!DNL Marketo Measure] A/BTests帶機會

![](assets/4.png)

A/B報表類型用於報告哪些Lead或Contact或Opportunity已暴露在A/B測試中。 此外，這些報告還可以顯示與A/B測試公開的Opportunity相關的收入金額。

請務必注意， Optimizely/VWO是內容變異平台，而非行銷管道。 因此， [!DNL Marketo Measure] A/B報表類型的使用方式與購買者接觸點報表不同。 購買者接觸點報表類型可用來了解哪些行銷管道（例如付費廣告、網路直接、社交）將銷售機會或連絡帶往特定頁面。 不過， [!DNL Marketo Measure] A/B報表類型無法用於報告變異對Lead或Opportunity的影響。 此外，由於A/B測試變異不是管道，有關變異的詳細資訊將不會顯示在購買者接觸點上。

以下是我們建議在報告A/B測試時使用的一些常見欄位，以協助提高清晰度和洞察力：

* 銷售機會轉換
* 實驗
* 實驗ID
* 變異
* 變數ID
* 報告日期

## [!DNL Salesforce] 報表範例 {#salesforce-example-reports}

**[!DNL Marketo Measure]A/B測試與銷售機會**

![](assets/5.png)

**[!DNL Marketo Measure]A/B測試與機會**

![](assets/6.png)
