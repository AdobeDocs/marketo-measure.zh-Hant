---
unique-page-id: 18874716
description: 歸因對應方法 —  [!DNL Marketo Measure]  — 產品檔案
title: 歸因對應方法
exl-id: 4d54dd20-9a82-4b87-8908-ced2bd9c0f2f
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 0%

---

# 歸因對應方法 {#attribution-mapping-methodology}

歸因對應方法是在CRM（聯繫人、機會、帳戶）中查找特定對象的過程，以在關聯的機會中建立歸因接觸點。 換句話說， [!DNL Marketo Measure] 了解根據您目前CRM的流程，要納入歸因模型的接觸點。

## 帳戶ID對應 {#account-id-mapping}

現成可用， [!DNL Marketo Measure] 提供帳戶ID對應。 這表示 [!DNL Marketo Measure] 查看帳戶及其聯繫人營銷資訊，以建立與商機關聯的歸因接觸點。 以下是該程式的簡單表示。

![](assets/1-1.png)

請記住 **不是全部** 來自您連絡人的接觸點會作為歸因接觸點推送至Opportunity 。 Opportunity的時間表（首次接觸日期 — 結束日期）將確定某個接觸點是否將算作對Opportunity的影響者。 因此，如果在Opportunity關閉後/丟失後發生了聯繫A上的接觸點， [!DNL Marketo Measure] 不會將該接觸點推送至Opportunity。 在所有其他歸因物件對應中，會依照此時間軸程式操作。

優點：此歸因方法對大多數公司都非常有效。 行銷團隊不需要依賴銷售團隊將所有聯繫人關聯到特定機會（這通常是個問題）。 此外，即使銷售團隊與聯繫人角色建立關聯，也可能遺漏了許多其他聯繫人與營銷資料的互動。 最後，這一方法有助於旨在影響賬戶總量而不是具體影響者的ABM戰略。

缺點：如果有強大的行銷和銷售SLA來定義誰應該獲得什麼的評分，則此方法可能會有問題。 此外，如果人員不使用帳戶層次結構來定義較大帳戶內的特定業務單位(例如：IBM)，則特定於一個業務部門的行銷互動可能會分散到其他業務部門的機會。

## 機會聯繫人角色映射 {#opportunity-contact-role-mapping}

雖然大部分用戶端都採用帳戶ID對應， [!DNL Marketo Measure] 能夠查找Opportunity中的聯繫人角色（與Opportunity關聯的聯繫人），以劃分歸因流程。 這表示 [!DNL Marketo Measure] 只會推送與Opportunity上的聯絡人角色相關聯的行銷互動，做為購買者歸因接觸點。 以下是此程式的表示。

![](assets/2-1.png)

優點：如果您的團隊有定義非常明確的聯絡人角色程式，這種歸因對應方式可能非常適合您。 這有助於讓銷售和行銷更加協調，因為每個人都會完全了解歸因的劃分方式。 當組織鎖定大公司內的多個業務單位，以及同時銷售不同產品時，此程式也非常實用。

缺點：但是，如果沒有建立聯繫角色流程，行銷將會失去大量行銷資料，而團隊在影響商機的行銷工作中獲得的評分會少很多。

## 機會主要聯繫人角色映射 {#opportunity-primary-contact-role-mapping}

除了簡單地看看機會上的聯繫人角色， [!DNL Marketo Measure] 可以更集中地查看Opportunity上的主聯繫人。 考慮到這個設定， [!DNL Marketo Measure] 只會抓取與某個機會的主要聯絡人相關聯的行銷接觸點，並將該資訊推送至該特定機會的歸因故事中。 請參閱下圖。

![](assets/3.png)

優點：如果您的團隊只想了解對商機上設定為「主要」的聯繫人的市場影響，則此類型的映射將最適合團隊。

缺點：這無疑是最少使用的測繪流程，而且會嚴重削弱營銷影響力，而這種影響力正在讓其他人有機會接觸。
