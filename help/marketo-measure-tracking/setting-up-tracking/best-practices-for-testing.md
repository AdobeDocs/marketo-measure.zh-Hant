---
unique-page-id: 18874722
description: 測試的最佳作法 —  [!DNL Marketo Measure]
title: 測試的最佳作法
exl-id: ff95a1a9-d324-47f5-b47d-39014dff77e4
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 0%

---

# 測試的最佳作法 {#best-practices-for-testing}

您應測試所有不同型別的表格，以確保 [!DNL Marketo Measure] JavaScript正常運作。

## 建議的測試程式 {#recommended-test-process}

1. 使用無痕瀏覽器或在每個表單提交測試之間清除您的Cookie _和_ 每次使用不同的電子郵件地址。

   >[!TIP]
   >
   >最佳做法是使用包含表示這是測試的內容以及時間的假電子郵件。 例如： `testing830am@test.com`.

1. 在搜尋引擎開始您的搜尋(例如 `google.com`)，或直接導覽至表單。

1. 使用唯一的電子郵件地址在您的網站上提交表單。

1. 紀錄您在上提交表單的頁面的URL及使用的電子郵件地址。

1. 找出在您的CRM （潛在客戶或連絡人）中針對該表單提交所建立的記錄，並確認已正確建立接觸點。

>[!NOTE]
>
>您可以使用 [!DNL Marketo Measure] 庫存報表，例如，銷售機會 [!DNL Marketo Measure] 接觸點或檢視銷售機會/聯絡人頁面配置（如果您選擇更新您的頁面配置） [!DNL Marketo Measure] 詳細資料。 這可能需要一些時間來處理資料。
