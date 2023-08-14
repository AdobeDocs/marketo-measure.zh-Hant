---
unique-page-id: 18874773
description: A/B測試設定與報告 —  [!DNL Marketo Measure]  — 產品檔案
title: A/B測試設定與報告
exl-id: 9a3f0731-5909-4fbf-a35a-9608ff561061
feature: A/B Testing
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 0%

---

# A/B測試設定與報告 {#a-b-testing-set-up-and-reporting}

此 [!DNL Marketo Measure] A/B測試整合可讓您追蹤 [最佳化](https://optimizely.com/){target="_blank"} 和VWO網站實驗。 本文指南提供如何新增的指示 [!DNL Marketo Measure] 潛在客戶的A/B測試區段， [!UICONTROL Contact]、大小寫和 [!UICONTROL Opportunity] 頁面配置。 我們也會介紹一般報告實務和執行的建議 [!DNL Marketo Measure] A/B報表型別。

## 設定 {#set-up}

新增 [!DNL Marketo Measure] 有關銷售機會、聯絡人、案例和機會的A/B測試區段。 [!DNL Marketo Measure] A/B測試整合可讓您追蹤 [最佳化](https://optimizely.com/){target="_blank"} and [VWO](https://vwo.com/){target="_blank"} 網站實驗。

1. 確認您正在使用封裝 [!DNL Marketo Measure] v3.9或更新版本。 若要這麼做，請前往 [!UICONTROL Salesforce] >[!UICONTROL Set Up] > [!UICONTROL Installed packages].
1. 編輯銷售機會頁面版面配置並新增 **[!DNL Marketo Measure]A/B測試** 頁面的相關清單。

   ![](assets/1.png)

1. 按一下 [!UICONTROL Wrench] 按鈕。 從所選欄位清單中移除庫存「Id」欄位。 新增 **[!UICONTROL Experiment]**， **[!UICONTROL Variation]**、和 **[!UICONTROL DateReported]** 欄位。 變更&quot;[!UICONTROL Sort by]「至 **[!UICONTROL Date Reported]**，並選取 **[!UICONTROL Descending]** 位於下拉式清單中。

   ![](assets/2.png)

1. 在 [!UICONTROL Buttons]，取消勾選 **[!UICONTROL New]**.

   ![](assets/3.png)

1. 連絡您的 [!DNL Marketo Measure] 代表或 [Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} 以啟用此功能。

## 報告 {#reporting}

客戶可存取多個 [!DNL Marketo Measure] 可讓您報告A/B測試（與銷售機會、聯絡人及商機相關）的A/B報告型別：

* [!DNL Marketo Measure] A/B測試集
* [!DNL Marketo Measure] A/BTests連絡人
* [!DNL Marketo Measure] 含潛在客戶的A/B測試
* [!DNL Marketo Measure] A/BTests與商機

![](assets/4.png)

A/B報告型別用於報告哪些Lead或Contact或Opportunity已接受A/B測試。 此外，這些報表可顯示和已遭受A/B測試的Opportunity相關聯的收入金額。

請務必注意，「最佳化/VWO」是內容變異平台，而非行銷管道。 因此，這些 [!DNL Marketo Measure] A/B報表型別的使用方式與「購買者接觸點」報表不同。 購買者接觸點報表型別可用來瞭解哪些行銷管道（例如，付費廣告、網路直接、社交）將銷售機會或聯絡人導向至特定頁面。 不過， [!DNL Marketo Measure] A/B報表型別無法用於報告變異如何影響Lead或Opportunity。 此外，由於A/B測試變數不是管道，因此變數的詳細資訊將不會顯示在購買者接觸點上。

以下是一些建議在A/B測試報告中使用的常見欄位，以協助提高清晰度和深入分析：

* 潛在客戶已轉換
* 實驗
* 實驗ID
* 變異
* 變數ID
* 報告日期

## [!DNL Salesforce] 範例報表 {#salesforce-example-reports}

**[!DNL Marketo Measure]使用潛在客戶的A/B測試**

![](assets/5.png)

**[!DNL Marketo Measure]A/B測試與商機**

![](assets/6.png)
