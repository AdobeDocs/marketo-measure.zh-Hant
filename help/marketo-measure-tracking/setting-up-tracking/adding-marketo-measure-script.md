---
unique-page-id: 18874795
description: 新增 [!DNL Marketo Measure] 指令碼 —  [!DNL Marketo Measure]  — 產品檔案
title: 新增 [!DNL Marketo Measure] 指令碼
exl-id: f8773037-04d7-4308-ba04-440e9b990d92
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 0%

---

# 新增 [!DNL Marketo Measure] 指令碼 {#adding-marketo-measure-script}

[!DNL Marketo Measure] 您想要透過追蹤的JavaScript [!DNL Marketo Measure] 應該會儘快新增到所有Web屬性。 部署JavaScript後， [!DNL Marketo Measure] 將會開始收集您的數位資料。 本文概述部署方法 [!DNL Marketo Measure] 要考慮的JavaScript和其他考量事項。

>[!NOTE]
>
>確定您已 [已在「 」中申請所有適當的網域 [!DNL Adobe Admin Console]](/help/marketo-measure-and-adobe/domain-management.md){target="_blank"} 除了部署 [!DNL Marketo Measure] JavaScript。

開始使用時 [!DNL Marketo Measure]，您可透過兩種方式新增 [!DNL Marketo Measure] JavaScript至您的網站：

* 硬式編碼
* Tag Management系統

## 硬式編碼 {#hard-coding}

作為最佳作法，我們強烈建議使用硬式編碼 [!DNL Marketo Measure] JavaScript至您的Web屬性。 若要以硬式編碼撰寫指令碼，您必須將指令碼放置在結尾的之前 `</head>` 在您網站的每個頁面上。

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

將JavaScript硬式編碼至 `<head>` ，可確保 [!DNL Marketo Measure] 指令碼將會先載入，而且不會遺漏轉介資訊。 此 [!DNL Marketo Measure] JavaScript會以非同步方式載入。 如果是硬式編碼，則必須手動將JavaScript新增至「行銷自動化」。

>[!TIP]
>
>瞭解如何確認您的指令碼為 [符合GDPR規範](/help/security-and-compliance/compliance-related-resources/ensuring-consent-for-gdpr-in-marketo-measure-js.md){target="_blank"}.

## Tag Management系統 {#tag-management-systems}

如果新增 [!DNL Marketo Measure] 無法透過硬式編碼使用JavaScript，另一個選項是新增 [!DNL Marketo Measure] 使用Tag Management系統編寫指令碼，例如 [!DNL Google Tag Manager] (GTM)或Tealium。

請注意，使用標籤管理系統進行部署 [!DNL Marketo Measure] JS可能會因為指令碼載入時間延遲而導致5-10%的資料遺失。 基本上，如果標籤管理工具載入不夠快， [!DNL Marketo Measure] JS也無法以足夠快的速度載入，而且可能會遺失第一個反向連結資訊。

常見的作法是部署 [!DNL Marketo Measure] JS透過標籤管理工具，直到時間/資源改用硬式編碼為佳。

新增 [!DNL Marketo Measure] 透過標籤管理解決方案編寫指令碼，您需要建立新標籤並在其中新增JavaScript。 將此標籤套用至網站上您要追蹤的所有頁面。

[!DNL Marketo Measure] 建議任何頁面檢視都應該觸發標籤。 此外，最好提供 [!DNL Marketo Measure] 引發順序中的最高優先順序，並確定前面沒有同步指令碼 [!DNL Marketo Measure] 標籤來確保最高資料品質。

更多資訊可以是 [可在此處找到](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md){target="_blank"}.

## 其他考量事項 {#additional-considerations}

[!DNL Marketo Measure] JavaScript是以網域為基礎，因此只要頁面上有JavaScript，而且根網域與用來建立Marketo Measure帳戶的網域相同，它就能自動處理任何子網域。

不過，如果您使用任何個別或國際網域，請務必讓您的 [!DNL Marketo Measure] 諮詢顧問知道。 網域需要手動新增到您在上的帳戶 [!DNL Marketo Measure] 結束 [!DNL Marketo Measure] 會知道將其他網域的資料連結至您的帳戶。 因此，請將任何個別/國際網域傳送至您的 [!DNL Marketo Measure] 顧問。

如果您使用任何協力廠商頁面，請與您的討論有關您的使用案例 [!DNL Marketo Measure] 顧問。 一般來說，您會想要知道您是否可新增自訂版本的 [!DNL Marketo Measure] JavaScript可適當追蹤這些頁面。 如果無法這麼做，我們將探索透過CRM Campaign接觸點進行追蹤，並與 [!DNL Marketo Measure] 顧問。

您是否有任何不應由追蹤的表單 [!DNL Marketo Measure] 因為它們對歸因不一定有意義（例如，取消訂閱表單、客戶登入等）？ 若是如此，您會想要新增排除程式碼 [本文章](/help/marketo-measure-tracking/setting-up-tracking/excluding-marketo-measure-from-specific-forms.md){target="_blank"} 至每個表單

您有任何不安全的頁面嗎？ 若是如此，您會想要保護這些使用者，因為導覽安全/不安全頁面將會中斷追蹤工作階段。

請務必與您的網路團隊溝通，讓他們知道 [!DNL Marketo Measure] JavaScript應一律位於適當的Web屬性上。 如果引進了新頁面/表單/網站，請務必部署 [!DNL Marketo Measure] JavaScript是通訊協定的一部分。

如果 [!DNL Web Application Firewall (WAF)] 在JavaScript設定期間會觸發警告，使用者可以停用該WAF規則或允許列出Cookie，如下例所示：

![](assets/adding-marketo-measure-script-1.png)

## Forms要特別注意 {#forms-to-pay-extra-attention-to}

**多表單提交**

* 問題：如果您在提交單一表單時有多個連結的表單，即使未提交完整表單，第一個表單也可能會產生接觸點。
* 解決方案：您需要強制其中一個表單向報告使用者 [!DNL Marketo Measure] 根據快取資料並討論放棄作法。 一般而言， [報表使用者代碼](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target="_blank"} 可以解決這個問題。

**帳戶登入（非建立）**

* 問題： [!DNL Marketo Measure] 建議您不要為後續的帳戶登入建立接觸點，因為這樣會稀釋歸因故事的份量。
* 解決方案：將排除程式碼新增至帳戶/客戶/合作夥伴登入表單。

>[!NOTE]
>
>我們建議您建立建立帳戶或試用版的接觸點。

**下載資產**

* 問題：若您的資產被封存， [!DNL Marketo Measure] 會在表單填寫時追蹤下載。 如果您的資產沒有閘道，我們報告的內容會有一些限制，無需自訂。
* 解決方案：若要由追蹤資產，請啟動資產 [!DNL Marketo Measure] JavaScript。 如果這不是選項且您仍想要使用接觸點，請考慮改為同步CRM行銷活動。

**iFrames**

* 問題： iFrame基本上可作為頁面內的頁面。
* 解決方案： [!DNL Marketo Measure] JS必須直接部署在iFrame標題中，我們才能正確地附加至表單。

**燈箱**

* 燈箱通常是包含iFrame的快顯視窗
* 解決方案： [!DNL Marketo Measure] JS必須部署在該託管iFrame的標頭中。

**一個頁面上的多個表單**

* 問題：如果頁面上有多個託管表單，您可能無法分辨哪個特定表單已填入 [!DNL Marketo Measure] 表單URL欄位。
* 解決方案：如果您需要知道已填寫哪個表單，請探索與您的網路團隊設定動態URL雜湊處理。

**Forms組織於 `<div>` 格式**

* 問題： [!DNL Marketo Measure] JS難以辨識在中組織的表單 `<div>` 格式，以便需要自訂程式碼。
* 解決方案：這些 [報表使用者範本](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target="_blank"} 可供您的網頁開發團隊用來新增所需的程式碼。

**聊天**

* 問題：如果您使用聊天提供者，則可能需要特殊處理。
* 解決方案： [!DNL Marketo Measure] 與Drift、Olark、Livechat、LivePerson和SnapEngage整合。 所有其他平台則需要透過CRM行銷活動會員資格進行追蹤。

**第二個網域**

* 問題： [!DNL Marketo Measure] JavaScript是網域所專屬的，因此您需要針對任何個別或國際網域採取額外步驟。 請注意 [!DNL Marketo Measure] JS可以處理相同根網域上的子網域。
* 解決方案：如果您擁有多個根網域，且希望由追蹤 [!DNL Marketo Measure] 請務必將JS新增至網域，並讓 [!DNL Marketo Measure] 顧問知道哪些網域應該手動關聯至您的 [!DNL Marketo Measure] 帳戶。

## 測試 [!DNL Marketo Measure] JavaScript {#testing-marketo-measure-javascript}

您的 [!DNL Marketo Measure] 顧問會協助您找出網站的測試，以確保 [!DNL Marketo Measure] JavaScript會出現在所有頁面上。 這項測試的部分內容是提交一些填入明確指定測試詳細資訊的表單，以確保正確傳回追蹤結果。

不過，您的 [!DNL Marketo Measure] 顧問可能不會像您的網路團隊那樣熟悉您的網站。 因此，您的網站團隊或其他適當的團隊務必徹底檢查網站，尤其是如果有與上述相同且複雜的表單在使用中。 您的團隊最終將負責確保所有必要的Web屬性皆正確追蹤，但如果您知道任何複雜的表單或情況，歡迎您詢問 [!DNL Marketo Measure] 提供測試協助的顧問。

若要自行測試表單，請遵循下列步驟：

1. 請一律使用無痕瀏覽器，或清除每個表單提交測試之間的快取，並且每次都使用不同的電子郵件地址。

   a.最佳做法是使用包含表示這是測試及當天時間的內容的假電子郵件。 例如： testing830am@test.com。

1. 記錄您要提交表單的頁面URL及使用的電子郵件。

1. 找出在您的CRM （潛在客戶或連絡人）中針對該表單提交所建立的記錄，並確認已正確建立接觸點。

   a.您可以使用 [!DNL Marketo Measure] 庫存報表，例如「具有採購員接觸點的銷售機會」，或如果您選擇更新頁面配置，請檢視「銷售機會/聯絡人」頁面配置 [!DNL Marketo Measure] 詳細資料。

   b.請注意，這可能需要一些時間來處理資料。
