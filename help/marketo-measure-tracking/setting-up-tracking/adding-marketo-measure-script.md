---
unique-page-id: 18874795
description: 新增 [!DNL Marketo Measure] 指令碼 —  [!DNL Marketo Measure]  — 產品檔案
title: 新增 [!DNL Marketo Measure] 指令碼
exl-id: f8773037-04d7-4308-ba04-440e9b990d92
source-git-commit: 82cc8269bfdb26b6acf039d0ce0e06564f5e2612
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 0%

---

# 新增 [!DNL Marketo Measure] 指令碼 {#adding-marketo-measure-script}

[!DNL Marketo Measure] 您想要由 [!DNL Marketo Measure] 應盡快新增至所有Web屬性。 部署JavaScript後， [!DNL Marketo Measure] 會開始收集數位資料。 本文概述部署方法 [!DNL Marketo Measure] JavaScript和其他考量事項。

>[!NOTE]
>
>確保 [在 [!DNL Adobe Admin Console]](/help/marketo-measure-and-adobe/domain-management.md){target="_blank"} 除了部署 [!DNL Marketo Measure] JavaScript。

開始使用時 [!DNL Marketo Measure]，有兩種方式可新增 [!DNL Marketo Measure] JavaScript至您的網站：

* 硬編碼
* Tag Management系統

## 硬編碼 {#hard-coding}

我們強烈建議您以硬式編碼撰寫 [!DNL Marketo Measure] JavaScript至您的Web屬性。 若要以硬式編碼撰寫指令碼，您必須將指令碼放在結尾 `</head>` 在您網站的每個頁面上。

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

將JavaScript硬式編碼至 `<head>` 頁面的 [!DNL Marketo Measure] 指令碼會先載入，且不會遺漏反向連結資訊。 此 [!DNL Marketo Measure] JavaScript以非同步方式載入。 如果以硬式編碼，則必須手動將JavaScript新增至行銷自動化。

>[!TIP]
>
>了解如何確認指令碼為 [符合GDPR規範](/help/security-and-compliance/compliance-related-resources/ensuring-consent-for-gdpr-in-marketo-measure-js.md){target="_blank"}.

## Tag Management系統 {#tag-management-systems}

若新增 [!DNL Marketo Measure] 無法透過硬式編碼使用JavaScript，另一個選項是新增 [!DNL Marketo Measure] 使用Tag Management系統的指令碼，例如 [!DNL Google Tag Manager] (GTM)或Tealium。

請注意，使用標籤管理系統來部署 [!DNL Marketo Measure] JS可能會因指令碼載入時間延遲而造成5-10%的資料遺失。 基本上，如果標籤管理工具載入速度不夠快， [!DNL Marketo Measure] JS也無法載入得足夠快，且可能會遺失第一個反向連結資訊。

常見做法是部署 [!DNL Marketo Measure] 透過標籤管理工具的JS，直到計時/資源更適合改為硬式編碼。

若要新增 [!DNL Marketo Measure] 指令碼，您將需要建立新標籤並在其中新增JavaScript。 將此標籤套用至您網站上要追蹤的所有頁面。

[!DNL Marketo Measure] 建議任何頁面檢視都應觸發標籤。 此外，最好 [!DNL Marketo Measure] 引發順序中的最高優先順序，並確保前面沒有同步指令碼 [!DNL Marketo Measure] 標籤，以確保最高的資料品質。

更多資訊可以是 [此處找到](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md){target="_blank"}.

## 其他考量事項 {#additional-considerations}

[!DNL Marketo Measure] JavaScript是以網域為基礎，因此只要JavaScript位於頁面上，且根網域與用來建立Marketo Measure帳戶的網域相同，它就能自動處理任何子網域。

不過，如果您使用任何個別或國際網域，請務必讓 [!DNL Marketo Measure] 顧問知道。 網域需要手動新增至您帳戶的 [!DNL Marketo Measure] 結束 [!DNL Marketo Measure] 知道將其他網域的資料連結至您的帳戶。 因此，請將任何個別/國際網域傳送至您的 [!DNL Marketo Measure] 顧問。

如果您使用任何第三方頁面，請與您的 [!DNL Marketo Measure] 顧問。 一般而言，您會想知道是否可以新增 [!DNL Marketo Measure] JavaScript來追蹤這些頁面（若適用）。 如果無法，將會使用您的 [!DNL Marketo Measure] 顧問。

您有任何「不應」由 [!DNL Marketo Measure] 因為歸因（例如取消訂閱表單、客戶登入等）不一定有意義嗎？ 若是，您將想要新增排除程式碼 [本文](/help/marketo-measure-tracking/setting-up-tracking/excluding-marketo-measure-from-specific-forms.md){target="_blank"} 每個表單

您有任何不安全的頁面嗎？ 若是如此，當您在安全/非安全頁面之間導覽時，會想要保護他們的安全，以中斷追蹤工作階段。

請務必與您的網路團隊對話，讓他們知道 [!DNL Marketo Measure] JavaScript應一律位於適當的Web屬性上。 若推出新頁面/表單/網站，請務必部署 [!DNL Marketo Measure] JavaScript是通訊協定的一部分。

若 [!DNL Web Application Firewall (WAF)] 警告會在JavaScript設定期間觸發，使用者可以停用該WAF規則或允許列出cookie，如下列範例所示：

![](assets/adding-marketo-measure-script-1.png)

## Forms將特別關注 {#forms-to-pay-extra-attention-to}

**多表單提交**

* 問題：如果您在提交單一表單時有多個已連結的表單，即使未提交完整的表單，第一個表單仍可能產生接觸點。
* 解決方案：您需要強制其中一個表單向 [!DNL Marketo Measure] 會根據快取的資料，並討論放棄實務。 一般來說， [報告使用者代碼](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target="_blank"} 能解決這個問題。

**帳戶登入（非建立）**

* 問題： [!DNL Marketo Measure] 建議不要為後續帳戶登入建立接觸點，因為這些往往會稀釋歸因歷程。
* 解決方案：將「排除代碼」新增至帳戶/客戶/合作夥伴登入表單。

>[!NOTE]
>
>我們建議您建立帳戶或試用的接觸點。

**下載資產**

* 問題：如果你的資產被關閉， [!DNL Marketo Measure] 會以表單填入的形式追蹤下載內容。 如果資產未受限制，我們可針對哪些資產不需自訂即可回報，會有所限制。
* 解決方案：如果您想要透過 [!DNL Marketo Measure] JavaScript。 如果此選項不適用，而您仍想要它的接觸點，請考慮改為同步CRM促銷活動。

**iFrames**

* 問題：iFrame基本上可作為頁面內的頁面。
* 解決方案：此 [!DNL Marketo Measure] JS必須直接部署在iFrame標題中，才能正確附加至表單。

**燈箱**

* 燈箱通常是包含iFrame的快顯視窗
* 解決方案：the [!DNL Marketo Measure] JS必須部署在該托管iFrame的標題內。

**頁面上的多個表單**

* 問題：如果頁面上托管有多個表單，您可能無法分辨填入的特定表單 [!DNL Marketo Measure] 表單URL欄位。
* 解決方案：如果您需要知道已填寫的表單，請探索如何與網站團隊設定動態URL雜湊。

**Forms組織 `<div>` 格式**

* 問題： [!DNL Marketo Measure] JS很難辨識組織於 `<div>` 格式，因此可能需要自訂程式碼。
* 解決方案：這些 [報表使用者範本](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target="_blank"} 可供網頁開發團隊用來新增所需的程式碼。

**聊天**

* 問題：如果您使用聊天提供程式，則可能需要特殊處理。
* 解決方案： [!DNL Marketo Measure] 與Drift、Olark、Livechat、LivePerson和SnapEngage整合。 所有其他平台皆需透過CRM促銷活動成員資格來追蹤。

**第二網域**

* 問題： [!DNL Marketo Measure] JavaScript是網域專用的，因此需要對任何個別或國際網域執行額外步驟。 請注意 [!DNL Marketo Measure] JS可以處理相同根網域上的子網域。
* 解決方案：如果您擁有多個根網域，則想要由 [!DNL Marketo Measure] 請務必將JS新增至網域，並讓您的 [!DNL Marketo Measure] 顧問知道哪些網域應手動關聯至您的 [!DNL Marketo Measure] 帳戶。

## 測試 [!DNL Marketo Measure] JavaScript {#testing-marketo-measure-javascript}

您的 [!DNL Marketo Measure] 顧問會協助您找出測試網站，以確保 [!DNL Marketo Measure] JavaScript存在於所有頁面中。 此測試的一部分是提交一些填滿明確指示的測試詳細資訊的表單，以確保追蹤正確傳回。

不過，您的 [!DNL Marketo Measure] 顧問可能不像您的網站團隊那樣熟悉您的網站。 因此，您的網站團隊或其他適當團隊務必仔細檢查網站，尤其是當使用中有如上所述之複雜表單時。 您的團隊最終將負責確保所有必要的Web屬性皆正確追蹤，但如果您知道任何複雜的表單或情況，歡迎詢問您的 [!DNL Marketo Measure] 協助測試顧問。

若要自行測試表單，請依照下列步驟操作：

1. 請始終使用無痕瀏覽器，或在每次表單提交測試之間清除快取，並且每次都使用不同的電子郵件地址。

   a.最佳作法是使用假電子郵件，內含某些資訊，指出其為測試，以及當天的時間。 例如：testing830am@test.com。

1. 記錄您要提交表單的頁面URL，以及使用的電子郵件。

1. 找出在您的CRM（銷售機會或聯絡人）中針對該表單提交所建立的記錄，並確認已適當建立接觸點。

   a.您可以使用 [!DNL Marketo Measure] 庫存報表，例如具有購買者接觸點的銷售機會，或查看銷售機會/聯繫人頁面配置（如果您選擇使用更新頁面配置） [!DNL Marketo Measure] 詳細資訊。

   b.請注意，資料處理可能需要一些時間。
