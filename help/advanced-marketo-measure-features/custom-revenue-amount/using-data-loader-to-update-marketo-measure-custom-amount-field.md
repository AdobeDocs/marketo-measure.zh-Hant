---
unique-page-id: 18874771
description: 使用資料載入器來更新 [!DNL Marketo Measure] 自訂金額欄位 —  [!DNL Marketo Measure]
title: 使用資料載入器更新Marketo Measure自訂金額欄位
exl-id: 55e91ac4-a835-48e0-a6ce-1d85b32aeac0
feature: Custom Revenue Amount
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 0%

---

# 使用資料載入器更新[!DNL Marketo Measure]自訂金額欄位 {#using-data-loader-to-update-marketo-measure-custom-amount-field}

[!DNL Marketo Measure]建議使用資料載入器，作為在[!DNL Marketo Measure]中使用自訂收入欄位時更新機會值的便利選項（我們使用立即可用的金額欄位）。 較偏好使用資料載入器而非使用[!DNL Marketo Measure]更新指令碼，因為指令碼要求使用者在[!DNL Marketo Measure]指令碼執行時停用所有Salesforce驗證規則。

## 使用資料載入器更新[!DNL Marketo Measure]自訂金額欄位{#using-data-loader-to-update-marketo-measure-custom-amount-field-1}

1. 建立Excel工作表，包含：

   * 機會ID
   * 自訂機會金額欄位（您偏好的收入欄位）
   * [!DNL Marketo Measure]機會金額欄位

1. 將您偏好收入欄位的值複製並貼到[!UICONTROL [!DNL Marketo Measure] Opportunity Amount]欄位。 然後，使用.csv檔案更新這些Opp。

**_或者，您可以進入Salesforce並使用自訂清單檢視來大量編輯所有機會……_**

1. 為所有商機建立自訂清單檢視。
1. 為偏好的收入欄位新增篩選器並非空白&#x200B;_且_ [!UICONTROL Marketo]量值機會金額欄位為空白。
1. 按一下&#x200B;**[!UICONTROL Mass Edit]**，但實際上並不會變更任何專案。
1. 按一下&#x200B;**[!UICONTROL Save]**。 這將觸發工作流程，以使用「軟體收入」欄位填入[!DNL Marketo Measure]機會金額欄位。
