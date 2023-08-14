---
unique-page-id: 18874696
description: 建議 [!DNL Salesforce] 許可權： [!DNL Marketo Measure] 已連線的使用者 —  [!DNL Marketo Measure]  — 產品檔案
title: 建議 [!DNL Salesforce] 許可權： [!DNL Marketo Measure] 已連線的使用者
exl-id: b74aa28b-4a7b-42d1-8df0-d1ae0ff1f338
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 0%

---

# 建議 [!DNL Salesforce] 許可權： [!DNL Marketo Measure] 已連線的使用者 {#recommended-salesforce-permissions-for-marketo-measure-connected-user}

[!DNL Marketo Measure] 透過已連線的傳送和接收資料 [!DNL Salesforce] 使用者在 [!DNL Marketo Measure] 應用程式。

為了將接觸點資料推送至您的 [!DNL Salesforce] 執行個體，則連線的使用者必須有權存取 [!DNL Marketo Measure] 自訂物件（即購買者接觸點和購買者歸因接觸點）和標準 [!DNL Salesforce] 潛在客戶與聯絡人等物件(請參閱 [[!DNL Marketo Measure] 在Salesforce中](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md).

[!DNL Salesforce] 管理員使用者授權可作為已連線的使用者，因為他們通常預設擁有必要的資料許可權。 不過，您的團隊可能偏好使用整合使用者或專用的 [!DNL Salesforce] 追蹤對下列專案影響的使用者授權： [!DNL Marketo Measure] 在您的執行個體上。

我們建議使用下列許可權，以確保 [!DNL Marketo Measure] 資料正精準流動：

* [!DNL Marketo Measure] 為專用使用者設定的管理員許可權

Managed許可權集可讓SFDC管理員從建立、讀取、寫入和刪除記錄 [!DNL Marketo Measure] 物件。

* 檢視和編輯轉換的潛在客戶許可權集

這允許 [!DNL Marketo Measure] 在銷售機會轉換為聯絡人後進行裝飾。 如果未啟用此許可權集，可能會出現嚴重的資料追蹤差距。 如需詳細資訊，請參閱 [[!DNL Salesforce Trailblazer] 社群](https://help.salesforce.com/articleView?id=leads_view_edit_converted.htm&amp;type=5).

* [!DNL Salesforce] 行銷使用者核取方塊

此 [!UICONTROL Marketing User] 核取方塊可讓使用者建立行銷活動並使用Campaign匯入精靈。 如果未選取此選項，使用者只能檢視行銷活動和進階行銷活動設定、編輯單一潛在客戶或聯絡人的行銷活動歷史記錄，以及執行行銷活動報告。 [!DNL Marketo Measure] 需要能夠讀取和寫入campaign物件。

**其他疑難排解**

如果 [!DNL Marketo Measure] 仍在讀取或寫入資料時發生問題。調查以下內容可能會有所助益：

* 存取目標 [!DNL Salesforce] 佇列

如果專用使用者無權存取佇列中的潛在客戶，則無法透過修改潛在客戶 [!DNL Marketo Measure] 資料。 您可以在階層中擁有角色，允許存取佇列或個別授與使用者存取權，以達成此目的。

* 欄位層級安全性和協助工具

欄位層級安全性和欄位可存取性相關，但有一些主要差異。 欄位層級安全性會定義指定設定檔的欄位可見性，而欄位協助工具會根據欄位層級安全性和頁面配置設定來決定是否可編輯欄位。 使用 [!DNL Marketo Measure] 封裝的許可權集，您將收到必要的欄位物件安全性設定。 在某些情況下，為了擁有正確的欄位協助工具，連線使用者需要擁有 [!DNL Marketo Measure] 欄位。 [!DNL Marketo Measure] 版面配置上的欄位允許 [!DNL Marketo Measure] 要對應的資料 [!DNL Salesforce]. 這將取決於您的特定許可權 [!DNL Salesforce] 環境。

每個組織的 [!DNL Salesforce] 有不同的需求，但我們會提供您平衡需求的需求， [!DNL Marketo Measure] 您的安全性通訊協定需要存取。 請隨時聯絡 [[!DNL Marketo Support]](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
