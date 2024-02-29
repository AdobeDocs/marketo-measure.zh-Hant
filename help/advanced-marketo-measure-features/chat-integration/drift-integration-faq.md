---
unique-page-id: 27656441
description: 漂移整合常見問題集 —  [!DNL Marketo Measure]
title: 漂移整合常見問題集
exl-id: ae5706b1-1f6c-4201-8585-0d7c587746e1
feature: Integration
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 0%

---

# 漂移整合常見問題集 {#drift-integration-faq}

作為 [!DNL Marketo Measure] 與Drift整合，以下是一些最常見的問題。 如果有任何未概述的問題，請聯絡Adobe客戶團隊（您的客戶經理）或 [Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

**如何啟用整合？**

漂移聊天追蹤 [!DNL Marketo Measure] 預設為啟用。 如果您要將其停用（預設不會從「漂移聊天」建立接觸點），請新增其他屬性至您的 [!DNL Marketo Measure] Javascript實施，粗體顯示如下：

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" id="bizible-settings" data-chatEnabled="false"></script>`

適用於使用 [!DNL Google Tag Manager] 載入 [!DNL Marketo Measure] 指令碼，如果要排除「漂移聊天」符合接觸點資格，請將新增至下列專案 `<span>` 緊接在您的 [!DNL Marketo Measure] 指令碼：

`<span id="bizible-settings" data-chatEnabled="false"></span>`

**整合有什麼作用？**

整合現在允許 [!DNL Marketo Measure] 追蹤一般使用者在漂移聊天中提供其電子郵件地址的時間。 從那裡，我們會使用「網頁聊天」型別的接觸點從這些互動建立接觸點。 此整合可讓行銷人員瞭解其聊天互動的效能，以及推動人們與這些聊天互動的管道/子管道/行銷活動。

**如果我透過行銷活動同步規則追蹤漂移，該怎麼辦？**

如果有任何Campaign同步規則可建立Drift聊天互動的接觸點，請務必停止將這些特定使用者新增至對應的CRM Campaign。 否則，在啟用功能位元後，請建立CRM Campaign接觸點和數位接觸點，以便進行Drift聊天互動。

**如果我透過CRM Campaigns追蹤漂移，該怎麼辦？**

如果有CRM行銷活動來建立Drift聊天互動的接觸點，則在這些特定行銷活動上必須設定接觸點結束日期（接觸點結束日期應為啟用網頁聊天整合功能位元的日期）。

**如果我透過活動追蹤漂移，該怎麼辦？**

如果已有活動規則可建立「漂流」聊天互動的接觸點，則必須將額外的邏輯新增至規則。 使用「任務建立日期」欄位新增邏輯，以防止建立重複的接觸點（IE CrmTask.CreatedDate小於啟用功能位元的日期）。 如需範例，請參閱下方的熒幕擷圖。

![](assets/activity-rule-drift.png)
