---
unique-page-id: 18874716
description: 歸因對應方法 —  [!DNL Marketo Measure]
title: 歸因對應方法
exl-id: 4d54dd20-9a82-4b87-8908-ced2bd9c0f2f
feature: Attribution
source-git-commit: cd5597a681f388a5b5c743dadd38bf3127811bff
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 0%

---

# 歸因對應方法 {#attribution-mapping-methodology}

歸因對應方法是指在CRM中查詢特定物件（聯絡人、商機、帳戶）的程式，以便在關聯的商機中建立歸因接觸點。 換言之，這是 [!DNL Marketo Measure] 根據您目前的CRM流程，瞭解歸因模型中要包含哪些接觸點的方式。

## 帳戶ID對應 {#account-id-mapping}

立即可用， [!DNL Marketo Measure] 提供帳戶ID對應。 這表示 [!DNL Marketo Measure] 檢視Account及其Contacts行銷資訊，以建立與商機相關聯的歸因接觸點。 以下是此程式的簡單表示。

![](assets/1-1.png)

請記住 **並非全部** 來自您連絡人的接觸點會作為Attribution接觸點推送到Opportunity中。 Opportunity的時間表（其首次接觸日期 — 關閉日期）會決定接觸點是否計為Opportunity的影響者。 因此，如果聯絡人A上的接觸點在商機關閉後發生成功/失敗， [!DNL Marketo Measure] 不會將該接觸點推送至商機。 所有其他歸因物件對應都會遵循此時間表程式。

優點：這種歸因方法對大多數公司都非常有效。 行銷團隊不需要依賴銷售團隊將所有連絡人與特定機會建立關聯（這通常是問題）。 此外，即使銷售團隊與聯絡人角色建立關聯，也可能會遺漏許多其他聯絡人與行銷資料的互動。 最後，此方法可協助ABM策略，該策略會努力影響帳戶的整體性，而非特定影響者。

缺點：如果有強大的行銷和銷售SLA定義誰應該獲得功勞，則此方法可能會產生問題。 此外，如果人們不使用帳戶階層來定義較大帳戶內的特定業務單位(例如：IBM)，則特定於一個業務單位的行銷互動可能會散佈到其他業務單位機會。

## 機會聯絡人角色對應 {#opportunity-contact-role-mapping}

雖然大多數使用者端使用帳戶ID對應， [!DNL Marketo Measure] 可以在機會中查詢聯絡人角色（與機會相關聯的聯絡人），以劃分歸因流程。 這表示 [!DNL Marketo Measure] 僅會以購買者歸因接觸點的形式推播與機會上聯絡人角色相關聯的行銷互動。 以下是此程式的表示方式。

![](assets/2-1.png)

優點：如果您的團隊具有定義良好的聯絡人角色程式，這種型別的歸因對應可能非常適合您。 它有助於讓銷售和行銷更加一致，因為每個人都能完全瞭解歸因的劃分方式。 如果組織要鎖定一家大型公司內的多個業務單位，同時銷售不同的產品，此程式也會很有幫助。

缺點：不過，如果沒有連絡人角色處理，行銷會遺失大量行銷資料，而團隊在影響機會的行銷活動中，最終會獲得較少的評分。

## 機會主要連絡人角色對應 {#opportunity-primary-contact-role-mapping}

除了單純檢視商機的聯絡人角色以外， [!DNL Marketo Measure] 可以更集中地只檢視商機上的主要聯絡人。 有了這項設定， [!DNL Marketo Measure] 僅會擷取與機會上主要聯絡人相關聯的行銷接觸點，並將該資訊推送至該特定機會的歸因故事。 請參閱下圖。

![](assets/3.png)

優點：如果您的團隊只想瞭解對設定為商機上「主要」之聯絡人的行銷影響，這種型別的對應最適合團隊。

缺點：這肯定是最不常使用的對應程式，而且可能會嚴重削弱行銷影響力，導致機會上的其他聯絡人移動針腳。
