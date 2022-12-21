---
unique-page-id: 27656441
description: Drift整合常見問題 —  [!DNL Marketo Measure]  — 產品檔案
title: Drift整合常見問題集
exl-id: ae5706b1-1f6c-4201-8585-0d7c587746e1
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 0%

---

# Drift整合常見問題集 {#drift-integration-faq}

作為 [!DNL Marketo Measure] 與Drift的整合，我們列出了一些最常見的問題。 若有任何問題未概述於下方，請洽詢您的客戶成功經理，或 [Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;}。

**如何啟用整合？**

漂移聊天跟蹤 [!DNL Marketo Measure] 預設為啟用。 如果您出於任何原因想要禁用它（預設情況下，不是從「漂移聊天」建立接觸點），我們需要在您的 [!DNL Marketo Measure] Javascript實施，粗體如下：

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" id="bizible-settings" data-chatEnabled="false"></script>`

針對使用 [!DNL Google Tag Manager] 載入 [!DNL Marketo Measure] 指令碼，如果您希望將「漂移聊天」排除在符合接觸點條件之外，則需要添加到以下內容 `<span>` 在 [!DNL Marketo Measure] 指令碼：

`<span id="bizible-settings" data-chatEnabled="false"></span>`

**整合有何功能？**

整合現在允許 [!DNL Marketo Measure] 追蹤使用者在「漂移」聊天中提供其電子郵件地址的時間。 從那裡，我們會以「網路聊天」的接觸點類型，從這些互動中建立接觸點。 此整合可讓行銷人員了解其聊天互動的效能，以及可促進人們與這些聊天互動的管道/子管道/行銷活動。

**如果我透過促銷活動同步規則追蹤「漂移」，該怎麼辦？**

如果有任何促銷活動同步規則可建立「隨動聊天」互動的接觸點，您將需要確保停止將這些特定使用者新增至對應的CRM促銷活動。 否則，一旦啟用功能位，我們會為一個「漂移聊天」互動建立CRM Campaign接觸點和數位接觸點。

**如果我透過CRM行銷活動追蹤流向，該怎麼辦？**

如果有CRM促銷活動可建立「隨動聊天」互動的接觸點，則需要在這些特定促銷活動上設定「接觸點結束日期」（「接觸點結束日期」應為啟用「網站聊天整合」功能位元的日期）。

**如果我透過活動追蹤流向，該怎麼辦？**

如果有活動規則可建立「漂移」聊天互動的接觸點，則需要在規則中新增額外的邏輯片段。 您將需要使用「任務建立日期」欄位來新增邏輯，以防止建立接觸點的重複（IE CrmTask.CreatedDate小於啟用功能位的日期）。 如需範例，請參閱下方的螢幕擷圖。

![](assets/activity-rule-drift.png)
