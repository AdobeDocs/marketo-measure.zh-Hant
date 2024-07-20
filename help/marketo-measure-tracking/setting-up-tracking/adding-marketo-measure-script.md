---
unique-page-id: 18874795
description: 正在新增 [!DNL Marketo Measure] 指令碼 —  [!DNL Marketo Measure]
title: 正在新增 [!DNL Marketo Measure] 指令碼
exl-id: f8773037-04d7-4308-ba04-440e9b990d92
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '1282'
ht-degree: 0%

---

# 正在新增[!DNL Marketo Measure]指令碼 {#adding-marketo-measure-script}

您想要由[!DNL Marketo Measure]追蹤的[!DNL Marketo Measure]個JavaScript應儘快新增至所有Web屬性。 部署JavaScript後，[!DNL Marketo Measure]就會開始收集您的數位資料。 本文概述部署[!DNL Marketo Measure] JavaScript的方法以及其他考量事項。

>[!NOTE]
>
>除了部署[!DNL Marketo Measure] JavaScript之外，請確定您已[申請 [!DNL Adobe Admin Console]](/help/marketo-measure-and-adobe/domain-management.md){target="_blank"}中的所有適當網域。

開始使用[!DNL Marketo Measure]時，有兩種方式可將[!DNL Marketo Measure] JavaScript新增至您的網站：

* 硬式編碼
* Tag Management系統

## 硬式編碼 {#hard-coding}

作為最佳作法，我們強烈建議將[!DNL Marketo Measure] JavaScript以硬式編碼方式編碼至您的Web屬性。 若要以硬式編碼撰寫指令碼，您必須將指令碼放置在網站每個頁面的結尾`</head>`之前。

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

將JavaScript以硬式編碼方式編碼至頁面的`<head>`，以確保先載入[!DNL Marketo Measure]指令碼，且不會遺漏轉介資訊。 [!DNL Marketo Measure] JavaScript以非同步方式載入。 如果是硬式編碼，則必須手動將JavaScript新增至行銷自動化。

>[!TIP]
>
>瞭解如何確定您的指令碼符合[GDPR](/help/security-and-compliance/compliance-related-resources/ensuring-consent-for-gdpr-in-marketo-measure-js.md){target="_blank"}。

## Tag Management系統 {#tag-management-systems}

如果無法透過硬式編碼新增[!DNL Marketo Measure]個JavaScript，另一個選項是使用Tag Management系統(例如[!DNL Google Tag Manager] (GTM)或Tealium)新增[!DNL Marketo Measure]指令碼。

使用標籤管理系統來部署[!DNL Marketo Measure] JS可能會因為指令碼載入時間延遲而導致5-10%的資料遺失。 基本上，如果標籤管理工具載入的速度不夠快，[!DNL Marketo Measure] JS也無法載入的速度夠快，可能會遺失第一個反向連結資訊。

常見的作法是透過標籤管理工具部署[!DNL Marketo Measure] JS，直到時間/資源移至硬式編碼較佳為止。

若要透過標籤管理解決方案新增[!DNL Marketo Measure]指令碼，您必須建立標籤並在其中新增我們的JavaScript。 將此標籤套用至網站上您要追蹤的所有頁面。

[!DNL Marketo Measure]建議任何頁面檢視都應該導致引發標籤。 此外，最好在引發順序中為[!DNL Marketo Measure]指定最高優先順序，並確定[!DNL Marketo Measure]標籤前面沒有同步指令碼，以確保最高的資料品質。

更多資訊可在[這裡](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md){target="_blank"}找到。

## 其他考量事項 {#additional-considerations}

[!DNL Marketo Measure] JavaScript是以網域為基礎，因此只要JavaScript位於頁面上，而且根網域與用來建立Marketo Measure帳戶的網域相同，它就能自動處理任何子網域。

不過，如果您使用任何個別或國際網域，請務必通知您的[!DNL Marketo Measure]顧問。 網域必須在[!DNL Marketo Measure]結尾手動新增到您的帳戶，以便[!DNL Marketo Measure]知道將其他網域的資料連結到您的帳戶。 因此，請將任何個別/國際網域傳送給您的[!DNL Marketo Measure]顧問。

如果您使用任何協力廠商頁面，請和您的[!DNL Marketo Measure]顧問討論您的使用案例。 一般而言，您會想要知道您是否可新增自訂版本的[!DNL Marketo Measure] JavaScript來追蹤這些頁面（如適用）。 如果無法執行此操作，我們將與您的[!DNL Marketo Measure]顧問探討透過CRM Campaign接觸點進行追蹤的問題。

您是否有任何[!DNL Marketo Measure]不應追蹤的表單，因為它們對歸因不一定有意義（例如，取消訂閱表單、客戶登入等）？ 若是如此，您會想要將此文章中的排除代碼[新增至每個表單](/help/marketo-measure-tracking/setting-up-tracking/excluding-marketo-measure-from-specific-forms.md){target="_blank"}

您有任何不安全的頁面嗎？ 導覽安全/不安全的頁面時會中斷追蹤工作階段，因此您應該保護這些頁面。

請務必與您的網站團隊溝通，讓他們知道[!DNL Marketo Measure] JavaScript應一律使用適當的Web屬性。 如果引進了新頁面/表單/網站，請確定部署[!DNL Marketo Measure] JavaScript是通訊協定的一部分。

如果在JavaScript設定期間觸發[!DNL Web Application Firewall (WAF)]警告，使用者可以停用該WAF規則或允許列出Cookie，如下列範例所示：

![](assets/adding-marketo-measure-script-1.png)

## Forms要特別注意 {#forms-to-pay-extra-attention-to}

**多重表單提交**

* 問題：如果您在提交單一表單時有多個連結的表單，即使未提交完整表單，第一個表單也可能會產生接觸點。
* 解決方案：您必須強制其中一個表單根據快取資料向[!DNL Marketo Measure]報告使用者並討論放棄作法。 一般來說，[報告使用者代碼](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target="_blank"}可以解決這個問題。

**帳戶登入（非建立）**

* 問題： [!DNL Marketo Measure]建議不要為後續的帳戶登入建立接觸點，因為這些可能會稀釋歸因故事。
* 解決方案：將排除程式碼新增至帳戶/客戶/合作夥伴登入表單。

>[!NOTE]
>
>我們建議您建立建立帳戶或試用版的接觸點。

**下載資產**

* 問題：如果您的資產被封存，[!DNL Marketo Measure]會以表單填寫形式追蹤下載。 如果您的資產沒有閘道，我們報告的內容會有一些限制，無需自訂。
* 解決方案：若您希望[!DNL Marketo Measure] JavaScript追蹤資產，請將該資產閘門。 如果這不是選項且您仍想要使用接觸點，請考慮改為同步CRM行銷活動。

**iFrames**

* 問題： iFrame基本上可作為頁面內的頁面。
* 解決方案： [!DNL Marketo Measure] JS必須直接部署在iFrame標頭中，我們才能正確地附加至表單。

**燈箱**

* 燈箱通常是包含iFrame的快顯視窗
* 解決方案： [!DNL Marketo Measure] JS必須部署在該代管iFrame的標頭中。

**一個頁面上有多個表單**

* 問題：如果頁面上託管多個表單，您可能無法分辨哪個特定表單已填入[!DNL Marketo Measure]表單URL欄位。
* 解決方案：如果您必須知道已填寫哪個表單，請探索與您的網路團隊設定動態URL雜湊處理。

以`<div>`格式組織的&#x200B;**Forms**

* 問題： [!DNL Marketo Measure] JS難以辨識以`<div>`格式組織的表單，因此可能需要自訂程式碼。
* 解決方案：您的網頁開發團隊可以使用這些[報表使用者範本](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target="_blank"}來新增所需的程式碼。

**聊天**

* 問題：如果您使用聊天提供者，則可能需要特殊處理。
* 解決方案： [!DNL Marketo Measure]與Drift、Olark、Livechat、LivePerson和SnapEngage整合。 所有其他平台則需要透過CRM行銷活動會員資格進行追蹤。

**第二個網域**

* 問題： [!DNL Marketo Measure] JavaScript是網域所專屬的，因此對任何個別或國際網域必須採取額外步驟。 [!DNL Marketo Measure] JS可以在相同的根網域上處理子網域。
* 解決方案：如果您擁有多個根網域，且您想要由[!DNL Marketo Measure]追蹤，請務必將JS新增至網域，並告知[!DNL Marketo Measure]顧問應將哪些網域手動關聯至您的[!DNL Marketo Measure]帳戶。

## 測試[!DNL Marketo Measure] JavaScript {#testing-marketo-measure-javascript}

您的[!DNL Marketo Measure]顧問將協助您測試網站，以確保[!DNL Marketo Measure] JavaScript出現在所有頁面上。 這項測試的部分工作是將一些填入明確說明的測試詳細資料的表單提交，以確保正確傳回追蹤資料。

不過，您的[!DNL Marketo Measure]顧問可能不像您的網路團隊那樣熟悉您的網站。 因此，您的網站團隊或其他適當的團隊務必徹底檢查網站，尤其是如果有與上述表格類似的複雜表單在使用中。 您的團隊最終將負責確保所有必要的Web屬性皆正確追蹤，但如果您知道任何複雜的表單或情況，歡迎您向[!DNL Marketo Measure]顧問請求測試協助。

若要自行測試表單，請遵循下列步驟：

1. 請一律使用無痕瀏覽器，或清除每個表單提交測試之間的快取，並且每次都使用不同的電子郵件地址。

   a.最佳做法是使用包含表示這是測試及當天時間的內容的假電子郵件。 例如： testing830am@test.com。

1. 紀錄您要提交表單的頁面URL及使用的電子郵件。

1. 找出在您的CRM （潛在客戶或連絡人）中針對該表單提交所建立的記錄，並確認已正確建立接觸點。

   a.您可以使用[!DNL Marketo Measure]庫存報告，例如「具有採購員接觸點的銷售機會」，或如果您選擇以[!DNL Marketo Measure]詳細資料更新您的版面配置，請檢視「銷售機會/聯絡人」頁面配置。

   b.可能需要一些時間來處理資料。
