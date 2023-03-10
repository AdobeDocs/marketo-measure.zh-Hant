---
unique-page-id: 18874574
description: '"[!DNL Marketo Measure] 標準欄位 [!DNL Salesforce] 對象 —  [!DNL Marketo Measure]  — 產品檔案」'
title: '"[!DNL Marketo Measure] 標準欄位 [!DNL Salesforce] 對象」'
exl-id: c9d5254f-06bd-4813-bb29-1a4955b37041
source-git-commit: b910e5aedb9e178058f7af9a6907a1039458ce7a
workflow-type: tm+mt
source-wordcount: '1273'
ht-degree: 0%

---

# [!DNL Marketo Measure] 標準欄位 [!DNL Salesforce] 物件 {#marketo-measure-fields-on-standard-salesforce-objects}

>[!NOTE]
>
>您可能會看到指定「[!DNL Marketo Measure]「 」，但仍可在CRM中看到「Bizible」。 我們正致力更新該更新，品牌重塑將很快反映在您的CRM中。

了解各種 [!DNL Marketo Measure] 新增至的欄位 [!DNL Salesforce] 標準物件。

## 帳戶 {#account}

預測性參與分數：此欄位與我們的ABM功能搭配使用，以提供與帳戶參與程度相關的分數，並考量許多因素，例如頁面檢視的間隔、有多少個連絡人與帳戶相關聯、是否有關閉的選項等。

## 案例 {#case}

我們將欄位新增至與首次接觸和銷售機會建立接觸里程碑相關的Case物件。 這適用於使用Case對象來代替Lead或Contact的客戶，並且還用於另一種查看資料的方式，以防客戶不希望我們建立Touchpoint記錄。

接觸點源(FT):這是首次接觸互動的來源。

接觸點源(LC):這是銷售機會建立接觸互動的來源。

行銷渠道(FT):這是首次接觸互動的行銷管道。

行銷管道(LC):這是銷售機會建立接觸互動的行銷管道。

廣告促銷活動名稱(FT):這是來自廣告網路的UTM促銷活動、廣告促銷活動，或 [!DNL Salesforce] 首次接觸互動的促銷活動。

廣告促銷活動名稱(LC):這是來自廣告網路的UTM促銷活動、廣告促銷活動，或 [!DNL Salesforce] 促銷活動 [!UICONTROL lead creation] 觸控互動。

登陸頁面(FT):這是首次接觸互動的登陸頁面。

登錄頁(LC):這是 [!UICONTROL lead creation] 觸控互動。

接觸點日期(FT):這是首次接觸互動的日期。

接觸點日期(LC):這是銷售機會建立接觸互動的日期。

## 行銷活動 {#campaign}

僅新增4個欄位、1個按鈕和1個驗證規則。

UniqueID:此欄位供我們內部使用，以追蹤與同步的不同促銷活動 [!DNL Marketo Measure].

啟用購買者接觸點：此欄位用於實際同步促銷活動，以便離線歸因包含和歷史資料。

接觸點開始日期：此欄位可用來設定將接觸點套用至歷史促銷活動的開始日期。

接觸點結束日期：此欄位可用來設定將接觸點套用至歷史促銷活動的結束日期。 將數位行銷活動納入前述範例[!DNL Marketo Measure] 然後將結束日期設定為套用指令碼的當天。

大量更新接觸點日期（按鈕）:此按鈕可用於在同步促銷活動時管理促銷活動成員的接觸點日期，因為我們會參考促銷活動成員資格日期或第一個回應日期，且會立即生效。 如果這些日期欄位未精確表示實際接觸點日期，我們會使用此按鈕來設定接觸點日期。

更新 [!DNL Marketo Measure] 歸因（驗證規則）:套件6.0版後，將不再使用此規則。

## 促銷活動成員 {#campaign-member}

套件中已新增5個欄位和1個Apex觸發程式。

接觸點狀態（銷售機會）:這是與未開啟的功能相關的診斷欄位。 我們會利用此資訊來了解是否已根據相關的銷售機會記錄建立接觸點，若未建立，則為何建立接觸點。

接觸點狀態（聯繫人）:這是與未開啟的功能相關的診斷欄位。 我們會利用此資訊來了解是否已根據相關的「連絡人」記錄建立接觸點，若未建立，則了解原因。

接觸點狀態（機會）:這是與未開啟的功能相關的診斷欄位。 我們使用此資訊來了解是否根據相關Opportunity記錄建立了接觸點，或者，如果沒有，原因。

接觸點狀態日期：這是診斷欄位的填入日期。

購買者接觸點日期：這與 [!UICONTROL Bulk Update Touchpoint date] 按鈕。 使用時，我們會將定義的接觸點日期套用至促銷活動成員。

OnCampaignMemberDelete:現成可用， [!DNL Salesforce] 刪除促銷活動成員時無法顯示，而這可能會造成正確歸因報表的問題。 刪除促銷活動成員時，會觸發此動作以通知 [!DNL Marketo Measure] 移除與該不存在的促銷活動成員相關的接觸點。

## 連絡人 {#contact}

我們將與首次接觸和銷售機會建立接觸里程碑相關的欄位新增至Contact物件。 這適用於希望將歸因直接報告至欄位，而非建立接觸點記錄的客戶。 我們的大部分客戶都選擇接觸點記錄路線，但也會在其自動化平台中使用這些欄位。

接觸點源(FT):這是首次接觸互動的來源。

接觸點源(LC):這是銷售機會建立接觸互動的來源。

行銷渠道(FT):這是首次接觸互動的行銷管道。

行銷管道(LC):這是銷售機會建立接觸互動的行銷管道。

廣告促銷活動名稱(FT):這是來自廣告網路的UTM促銷活動、廣告促銷活動，或 [!DNL Salesforce] 首次接觸互動的促銷活動。

廣告促銷活動名稱(LC):這是來自廣告網路的UTM促銷活動、廣告促銷活動，或 [!DNL Salesforce] 促銷活動 [!UICONTROL lead creation] 觸控互動。

登陸頁面(FT):這是首次接觸互動的登陸頁面。

登錄頁(LC):這是 [!UICONTROL lead creation] 觸控互動。

接觸點日期(FT):這是首次接觸互動的日期。

接觸點日期(LC):這是銷售機會建立接觸互動的日期。

BizibleID:這用於與活動歸因和呼叫追蹤量度整合相關，以便讓連絡人關聯至接觸點。

## 銷售機會 {#lead}

我們將與首次接觸和銷售機會建立接觸里程碑相關的欄位新增至銷售機會物件。 這適用於希望將歸因直接報告至欄位，而非建立接觸點記錄的客戶。 我們的大部分客戶都選擇接觸點記錄路線，但也會在其自動化平台中使用這些欄位。

接觸點源(FT):這是首次接觸互動的來源。

接觸點源(LC):這是銷售機會建立接觸互動的來源。

行銷渠道(FT):這是首次接觸互動的行銷管道。

行銷管道(LC):這是銷售機會建立接觸互動的行銷管道。

廣告促銷活動名稱(FT):這是來自廣告網路的UTM促銷活動、廣告促銷活動，或 [!DNL Salesforce] 首次接觸互動的促銷活動。

廣告促銷活動名稱(LC):這是來自廣告網路的UTM促銷活動、廣告促銷活動，或 [!DNL Salesforce] 銷售機會建立的促銷活動接觸互動。

登陸頁面(FT):這是首次接觸互動的登陸頁面。

登錄頁(LC):這是銷售機會建立接觸互動的登陸頁面。

接觸點日期(FT):這是首次接觸互動的日期。

接觸點日期(LC):這是銷售機會建立接觸互動的日期。

BizibleID:這與我們的活動歸因和呼叫追蹤量度整合，以讓銷售機會關聯至接觸點有關。

## 帳戶 {#account-1}

這用於ABM功能的「銷售機會帳戶」對應。 我們會填入此欄位，以建立兩個物件之間的查詢關係。

## 機會 {#opportunity}

[!DNL Marketo Measure] 機會金額：此欄位用於Opportunity上利用自定義金額欄位的情況。 我們將自訂欄位值對應至 [!DNL Marketo Measure] Opportunity Amount（使用工作流），然後閱讀此欄位以獲取「購買者歸因接觸點」對象上的「收入」歸因欄位。

## 活動 {#activity}

BizibleID:這可讓我們將接觸點與活動歸因和呼叫追蹤量度整合的活動產生關聯。

購買者接觸點日期：此欄位可透過工作流程填入，作為活動歸因的日期，且將會填入供我們的calltrackingmetrics整合使用，以知道互動發生的時間。
