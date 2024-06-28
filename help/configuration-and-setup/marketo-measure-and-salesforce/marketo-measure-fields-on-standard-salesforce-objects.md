---
unique-page-id: 18874574
description: "[!DNL Marketo Measure] 標準欄位 [!DNL Salesforce] 物件 —  [!DNL Marketo Measure]"
title: '"[!DNL Marketo Measure] 標準欄位 [!DNL Salesforce] 物件」'
exl-id: c9d5254f-06bd-4813-bb29-1a4955b37041
feature: Salesforce
source-git-commit: 05ba9e487d492ba4352a7f0577c7221f6ec9567e
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 0%

---

# [!DNL Marketo Measure] 標準欄位 [!DNL Salesforce] 物件 {#marketo-measure-fields-on-standard-salesforce-objects}

>[!NOTE]
>
>您可能會看到指定&#39;&#39;的說明[!DNL Marketo Measure]&quot;，但仍在您的CRM中看到「Bizible」。 我們正致力於更新此專案，品牌重塑將很快反映在您的CRM中。

瞭解各種 [!DNL Marketo Measure] 新增到的欄位 [!DNL Salesforce] 標準物件。

## 帳戶 {#account}

預測性參與分數：此欄位與我們的ABM功能搭配使用，以提供與帳戶參與程度相關的分數，並會考量許多因素，例如頁面檢視的造訪間隔、與帳戶相關聯的聯絡人數量，是否有已關閉的營業等。

## Campaign {#campaign}

僅新增4個欄位、1個按鈕和1個驗證規則。

UniqueID：此欄位供我們內部使用，以追蹤與同步的不同行銷活動 [!DNL Marketo Measure].

啟用購買者接觸點：此欄位是用於離線歸因包含和歷史資料之促銷活動的實際同步。

接觸點開始日期：此欄位是用於設定將接觸點套用至歷史行銷活動的開始日期。

接觸點結束日期：此欄位是用於設定將接觸點套用至歷史行銷活動的結束日期。 常見的範例是包含數位行銷活動之前[!DNL Marketo Measure] 然後設定結束日期為套用指令碼的日期。

大量更新接觸點日期（按鈕）：當行銷活動同步時，此按鈕用於管理行銷活動成員的接觸點日期，因為我們將參考行銷活動會員資格日期或第一個立即可用的回應日期。 如果這些日期欄位無法準確表示實際接觸點日期，我們會使用此按鈕來設定接觸點日期。

更新 [!DNL Marketo Measure] 歸因（驗證規則）：在套件版本6.0之後已棄用此規則。

## 促銷活動會員 {#campaign-member}

套件中已新增5個欄位和1個Apex觸發器。

接觸點狀態（銷售機會）：這是與未開箱即用功能相關的診斷欄位。 我們透過此瞭解是否針對相關Lead記錄建立了接觸點，若否，為什麼。

接觸點狀態（連絡人）：這是與未開箱即用功能相關的診斷欄位。 我們透過此瞭解是否針對相關連絡人記錄建立了接觸點，若否，為什麼。

接觸點狀態（機會）：這是與未開箱即用功能相關的診斷欄位。 我們透過此專案來瞭解是否針對相關Opportunity記錄建立了接觸點，若否，為什麼。

接觸點狀態日期：此為填入診斷欄位的日期。

Buyer Touchpoint日期：此日期與 [!UICONTROL Bulk Update Touchpoint date] 按鈕。 使用時，我們會套用定義的接觸點日期至促銷活動會員。

OnCampaignMemberDelete：立即可用， [!DNL Salesforce] 刪除行銷活動成員時不會顯示，這可能會造成精確歸因報表的問題。 刪除行銷活動會員時，系統會觸發此動作以通知 [!DNL Marketo Measure] 以移除與該不存在的行銷活動成員相關的接觸點。

## 銷售機會 {#lead}

Bizible Account欄位用於ABM功能的Lead to Account對應。 我們會填入此欄位，以建立兩個物件之間的查閱關係。

## 帳戶 {#account-1}

這用於我們的ABM功能的Lead to Account對應。 我們會填入此欄位，以建立兩個物件之間的查閱關係。

## 機會 {#opportunity}

[!DNL Marketo Measure] 商機金額：此欄位用於商機使用自訂金額欄位的案例中。 我們將該自訂欄位值對應至 [!DNL Marketo Measure] 使用工作流程檢視機會金額，然後針對Buyer Attribution Touchpoint物件上的收入歸因欄位讀取此欄位。

## 活動 {#activity}

BizibleID：這是供我們將接觸點關聯到活動歸因和呼叫追蹤量度整合的活動。

Buyer Touchpoint日期：此欄位可透過工作流程填入，以作為活動歸因的日期，並將填入供我們的calltrackingmetrics整合得知互動發生的時間。
