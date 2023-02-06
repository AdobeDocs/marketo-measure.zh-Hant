---
unique-page-id: 18874560
description: 為何您絕不應刪除接觸點 —  [!DNL Marketo Measure]  — 產品檔案
title: 為何您絕不應刪除接觸點
exl-id: e74c14ff-0399-4ee9-b732-6686823ff5c7
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 0%

---

# 為何您絕不應刪除接觸點 {#why-you-should-never-delete-touchpoints}

如果您發現Opportunity上的接觸點被錯誤地分配歸因評分，請聯繫您的客戶經理以確定後續步驟。 在這些情況下，我們建議使用購買者的接觸點抑制功能，從SFDC和ROI儀表板中移除接觸點。 您的帳戶管理員可協助建立這些規則。 請勿自行手動刪除這些接觸點。

此 [!DNL Marketo Measure] 處理系統不會註冊已從SFDC手動刪除接觸點。 到今天為止，我們的系統還沒有觸發任何信號來調整資料。 [!DNL Marketo Measure] 不會自動推送另一個接觸點來取代已刪除的接觸點，也不會將接觸點位置或歸因重新指派至後續的接觸點。

刪除接觸點時，會在歸因資料中建立一個孔。 通常，這會顯示在Opportunity的歸因接觸點中。 在下圖中，本應接收機會建立接觸的接觸點已被刪除。 因此，此機會缺少OC接觸點，此Opp的歸因百分比加起來不會達到100%。

![](assets/1.png)

如果從您的SFDC中刪除了接觸點，請聯繫 [Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} 請求重新匯入資料。
