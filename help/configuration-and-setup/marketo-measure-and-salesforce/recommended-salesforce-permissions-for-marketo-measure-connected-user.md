---
unique-page-id: 18874696
description: 為 [!DNL Marketo Measure] 連線的使用者 —  [!DNL Marketo Measure]建議的 [!DNL Salesforce] 許可權
title: 為 [!DNL Marketo Measure] 連線使用者建議的 [!DNL Salesforce] 許可權
exl-id: b74aa28b-4a7b-42d1-8df0-d1ae0ff1f338
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 0%

---

# 為[!DNL Marketo Measure]個連線使用者建議的[!DNL Salesforce]許可權 {#recommended-salesforce-permissions-for-marketo-measure-connected-user}

[!DNL Marketo Measure]會透過[!DNL Marketo Measure]應用程式中連線的[!DNL Salesforce]使用者傳送及接收資料。

若要將接觸點資料推送至您的[!DNL Salesforce]執行個體，連線的使用者必須能存取[!DNL Marketo Measure]個自訂物件(即Buyer Touchpoint和Buyer Attribution Touchpoint)以及銷售機會和聯絡人等標準[!DNL Salesforce]物件。 請參閱Salesforce[&#128279;](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md)中的[!DNL Marketo Measure] 。

[!DNL Salesforce]管理員使用者授權可作為已連線的使用者，因為他們通常預設擁有必要的資料許可權。 不過，您的團隊可能偏好使用整合使用者或專用的[!DNL Salesforce]使用者授權，以追蹤[!DNL Marketo Measure]對您執行個體的影響。

我們建議下列許可權，以確保[!DNL Marketo Measure]資料正確流動：

* 已針對專用使用者設定[!DNL Marketo Measure]管理員許可權

Managed許可權集可讓SFDC管理員從[!DNL Marketo Measure]物件建立、讀取、寫入、刪除記錄。

* 檢視和編輯轉換的潛在客戶許可權集

這可讓[!DNL Marketo Measure]在銷售機會轉換為聯絡人後裝飾銷售機會。 如果未啟用此許可權集，可能會出現嚴重的資料追蹤差距。 您可以在[[!DNL Salesforce Trailblazer] 社群](https://help.salesforce.com/s/articleView?language=en_US&id=leads_view_edit_converted.htm&type=5)中找到更多資訊。

* [!DNL Salesforce]行銷使用者核取方塊

[!UICONTROL Marketing User]核取方塊可讓使用者建立行銷活動並使用行銷活動匯入精靈。 如果未選取此選項，使用者只能檢視行銷活動和進階行銷活動設定、編輯單一潛在客戶或聯絡人的行銷活動歷史記錄，以及執行行銷活動報告。 [!DNL Marketo Measure]必須能夠讀取和寫入行銷活動物件。

**其他疑難排解**

如果[!DNL Marketo Measure]在讀取或寫入資料時仍然遇到問題，則調查以下內容可能會有所幫助：

* [!DNL Salesforce]佇列的存取權

如果專用使用者無權存取佇列中的潛在客戶，則無法修改具有[!DNL Marketo Measure]資料的潛在客戶。 您可以在階層中擁有角色，允許存取佇列或個別授與使用者存取權，以達成此目的。

* 欄位層級安全性和協助工具

欄位層級安全性和欄位可存取性相關，但有一些主要差異。 欄位層級安全性會定義指定設定檔的欄位可見性，而欄位協助工具會根據欄位層級安全性和頁面配置設定來決定是否可編輯欄位。 使用[!DNL Marketo Measure]封裝的許可權集，您會收到必要的欄位物件安全性設定。 有時候，為了有正確的欄位協助工具，連線的使用者需要在頁面配置中有[!DNL Marketo Measure]個欄位。 配置上的[!DNL Marketo Measure]欄位允許[!DNL Marketo Measure]資料對應到[!DNL Salesforce]。 這取決於您特定的[!DNL Salesforce]環境。

每個組織的[!DNL Salesforce]都有個別的需求，但我們會提供您平衡存取需求[!DNL Marketo Measure]與安全性通訊協定的需求。 請隨時聯絡[[!DNL Marketo Support]](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}。
