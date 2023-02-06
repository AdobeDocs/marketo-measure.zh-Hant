---
unique-page-id: 18874771
description: 使用資料載入器更新 [!DNL Marketo Measure] 自訂金額欄位 —  [!DNL Marketo Measure]  — 產品檔案
title: 使用資料載入器更新Marketo Measure自訂量欄位
exl-id: 55e91ac4-a835-48e0-a6ce-1d85b32aeac0
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 0%

---

# 使用資料載入器更新 [!DNL Marketo Measure] 自訂金額欄位 {#using-data-loader-to-update-marketo-measure-custom-amount-field}

[!DNL Marketo Measure] 建議在使用自訂收入欄位（我們使用現成的「金額」欄位）時，使用資料載入器作為更新機會值的便利選項 [!DNL Marketo Measure]. 偏好使用資料載入器，而非使用 [!DNL Marketo Measure] 更新指令碼，因為指令碼要求使用者在 [!DNL Marketo Measure] 指令碼執行。

## 使用資料載入器更新 [!DNL Marketo Measure] 自訂金額欄位{#using-data-loader-to-update-marketo-measure-custom-amount-field-1}

1. 使用建立Excel工作表：

   * 機會ID
   * Custom Opportunity Amount欄位（首選收入欄位）
   * [!DNL Marketo Measure] 機會金額欄位

1. 將您偏好收入欄位的值複製並貼到 [!UICONTROL [!DNL Marketo Measure] Opportunity Amount] 欄位。 然後，使用.csv檔案更新這些Opp。

**_或者，您也可以進入Salesforce並使用自定義清單視圖成批編輯所有業務機會……_**

1. 為所有Opportunity建立自定義清單視圖。
1. 為偏好收入欄位新增篩選條件不得空白 _和_ [!UICONTROL Marketo] Measure Opportunity Amount欄位為空。
1. 按一下 **[!UICONTROL Mass Edit]**，但別改變任何東西。
1. 按一下 **[!UICONTROL Save]**. 這會觸發工作流程以填入 [!DNL Marketo Measure] Opportunity Amount欄位和Software Revenue欄位。
