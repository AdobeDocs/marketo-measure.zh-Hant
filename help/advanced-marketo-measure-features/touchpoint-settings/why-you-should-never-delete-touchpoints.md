---
unique-page-id: 18874560
description: 為何您絕不應該刪除接觸點 —  [!DNL Marketo Measure]
title: 為何您絕不應該刪除接觸點
exl-id: e74c14ff-0399-4ee9-b732-6686823ff5c7
feature: Touchpoints
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# 為何您絕不應該刪除接觸點 {#why-you-should-never-delete-touchpoints}

如果您發現Opportunity上的某個接觸點未正確指派歸因評分，請洽詢您的客戶經理以決定後續步驟。 在這些情況下，我們建議使用購買者的接觸點隱藏功能，將接觸點從SFDC和ROI儀表板移除。 您的客戶經理可協助建立這些規則。 請勿自行手動刪除這些接觸點。

此 [!DNL Marketo Measure] 處理系統不會登入接觸點已手動從SFDC刪除。 截至今日，沒有觸發程式會訊號至我們的系統以調整資料。 [!DNL Marketo Measure] 將不會自動推送另一個接觸點來取代已刪除的接觸點，也不會重新指派該接觸點位置或歸因於後續接觸點。

刪除接觸點時，會在歸因資料中建立一個洞。 通常，這會出現在機會上的歸因接觸點中。 在下圖中，原本會收到Opportunity Creation接觸的接觸點已刪除。 因此，此機會缺少OC接觸點，且此Opp的歸因百分比加總不會達到100%。

![](assets/1.png)

如果接觸點已從SFDC刪除，請聯絡 [Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} 以請求重新匯入您的資料。
