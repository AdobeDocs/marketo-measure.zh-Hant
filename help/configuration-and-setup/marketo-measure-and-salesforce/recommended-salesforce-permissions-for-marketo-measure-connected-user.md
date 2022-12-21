---
unique-page-id: 18874696
description: 建議 [!DNL Salesforce] 的權限 [!DNL Marketo Measure] 已連接用戶 —  [!DNL Marketo Measure]  — 產品檔案
title: 建議 [!DNL Salesforce] 的權限 [!DNL Marketo Measure] 已連接用戶
exl-id: b74aa28b-4a7b-42d1-8df0-d1ae0ff1f338
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 0%

---

# 建議 [!DNL Salesforce] 的權限 [!DNL Marketo Measure] 已連接用戶 {#recommended-salesforce-permissions-for-marketo-measure-connected-user}

[!DNL Marketo Measure] 通過連接的 [!DNL Salesforce] 使用者 [!DNL Marketo Measure] 應用程式。

若要推送接觸點資料至您的 [!DNL Salesforce] 例項中，連線的使用者必須擁有 [!DNL Marketo Measure] 自訂物件（即購買者接觸點和購買者歸因接觸點）以及標準 [!DNL Salesforce] 對象，如銷售機會和聯繫人(請參閱 [[!DNL Marketo Measure] 在Salesforce中](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md).

[!DNL Salesforce] 管理員用戶許可證可以作為連接的用戶，因為預設情況下他們通常具有必要的資料權限。 不過，您的團隊可能偏好使用整合使用者或專用 [!DNL Salesforce] 追蹤 [!DNL Marketo Measure] 在您的例項上。

建議您下列權限，以確保 [!DNL Marketo Measure] 資料正確流動：

* [!DNL Marketo Measure] 專用用戶的管理員權限集

托管權限集使SFDC管理員能夠建立、讀取、寫入、刪除記錄 [!DNL Marketo Measure] 對象。

* 查看和編輯轉換的銷售機會權限集

這允許 [!DNL Marketo Measure] 以裝飾銷售線索。 如果未啟用此權限集，可能會存在重大資料追蹤差距。 如需詳細資訊，請參閱 [[!DNL Salesforce Trailblazer] 社群](https://help.salesforce.com/articleView?id=leads_view_edit_converted.htm&amp;type=5).

* [!DNL Salesforce] 行銷使用者核取方塊

此 [!UICONTROL Marketing User] 核取方塊可讓使用者建立促銷活動，並使用促銷活動匯入精靈。 如果未選取此選項，則使用者只能檢視促銷活動和進階促銷活動設定、編輯單一銷售機會或聯絡人的促銷活動歷史記錄，以及執行促銷活動報表。 [!DNL Marketo Measure] 需要讀取和寫入行銷活動物件的功能。

**其他疑難排解**

若 [!DNL Marketo Measure] 仍在讀取或寫入資料時發生問題，調查下列內容可能會有所幫助：

* 存取 [!DNL Salesforce] 隊列

如果專用用戶沒有隊列中銷售機會的訪問權限，則它無法使用 [!DNL Marketo Measure] 資料。 您可以在階層中擁有允許存取佇列或個別授予使用者存取權的角色，來達成此目的。

* 欄位級安全性和可訪問性

欄位層級安全性和欄位協助工具相關，但有一些主要差異。 「欄位級安全性」定義指定設定檔的欄位可見性，而「欄位可及性」則根據欄位級安全性和頁面配置設定來判斷欄位是否可編輯。 使用 [!DNL Marketo Measure] 包的權限集將接收必要的欄位對象安全設定。 在某些情況下，為了擁有正確的欄位協助工具，連線的使用者必須具備 [!DNL Marketo Measure] 欄位。 [!DNL Marketo Measure] 版面上的欄位允許 [!DNL Marketo Measure] 對應至 [!DNL Salesforce]. 這取決於您的特定 [!DNL Salesforce] 環境。

每個組織的 [!DNL Salesforce] 有個人需求，但我們提供您平衡需求的條件 [!DNL Marketo Measure] 存取需要您的安全通訊協定。 不要猶豫地聯繫 [[!DNL Marketo Support]](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;}。
