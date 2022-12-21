---
unique-page-id: 18874722
description: 測試最佳實務 —  [!DNL Marketo Measure]  — 產品檔案
title: 測試最佳實務
exl-id: ff95a1a9-d324-47f5-b47d-39014dff77e4
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 0%

---

# 測試最佳實務 {#best-practices-for-testing}

您應測試所有不同類型的表單，以確保 [!DNL Marketo Measure] JavaScript正常運作。

## 建議的測試程式 {#recommended-test-process}

1. 使用無痕瀏覽器，或在每次表單提交測試之間清除Cookie _和_ 每次都使用不同的電子郵件地址。

   >[!TIP]
   >
   >最佳作法是使用假電子郵件，內含某些資訊來指出這是測試，以及當天的時間。 例如： `testing830am@test.com`.

1. 從搜尋引擎開始搜尋(例如 `google.com`)，或直接導覽至表單。

1. 使用唯一的電子郵件地址在您的網站上提交表單。

1. 記錄您要在上提交表單的頁面URL，以及使用的電子郵件地址。

1. 找出在您的CRM（銷售機會或聯絡人）中針對該表單提交所建立的記錄，並確認已適當建立接觸點。

>[!NOTE]
>
>您可以使用 [!DNL Marketo Measure] 庫存報表，如銷售機會 [!DNL Marketo Measure] 如果您選擇使用更新頁面配置，則接觸點或查看潛在客戶/聯繫人頁面配置 [!DNL Marketo Measure] 詳細資訊。 資料處理可能需要一些時間。
