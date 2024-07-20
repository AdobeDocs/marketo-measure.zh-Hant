---
unique-page-id: 18874722
description: 測試的最佳實務 —  [!DNL Marketo Measure]
title: 測試的最佳作法
exl-id: ff95a1a9-d324-47f5-b47d-39014dff77e4
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---

# 測試的最佳作法 {#best-practices-for-testing}

您應該測試所有您需要的不同表格型別，以確保[!DNL Marketo Measure] JavaScript正常運作。

## 建議的測試程式 {#recommended-test-process}

1. 使用無痕瀏覽器或清除每個表單提交測試&#x200B;_和_&#x200B;之間的Cookie，每次都使用不同的電子郵件地址。

   >[!TIP]
   >
   >最佳做法是使用包含表示這是測試的內容以及時間的假電子郵件。 例如： `testing830am@test.com`。

1. 在搜尋引擎（例如`google.com`）開始搜尋，或直接導覽至表單。

1. 使用唯一的電子郵件地址在您的網站上提交表單。

1. 紀錄您在上提交表單的頁面的URL及使用的電子郵件地址。

1. 找出在您的CRM （潛在客戶或連絡人）中針對該表單提交所建立的記錄，並確認已正確建立接觸點。

>[!NOTE]
>
>您可以使用[!DNL Marketo Measure]庫存報告，例如具有[!DNL Marketo Measure]接觸點的銷售機會，或者如果您選擇使用[!DNL Marketo Measure]詳細資料更新您的頁面配置，則可以檢視銷售機會/聯絡人頁面配置。 這可能需要一些時間來處理資料。
