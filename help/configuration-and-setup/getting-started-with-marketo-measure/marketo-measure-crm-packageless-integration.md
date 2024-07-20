---
unique-page-id: 37356027
description: '[!DNL Marketo Measure] CRM無封裝整合 —  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] CRM無封裝整合'
exl-id: a4f31d82-63ec-4bb2-bc8b-d3495e61af4f
feature: Integration
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 0%

---

# [!DNL Marketo Measure] CRM無封裝整合 {#marketo-measure-crm-packageless-integration}

並非所有行銷團隊都希望（或有權存取）從CRM執行行銷報告，無論是因為存取權受限、CRM所有權、實現價值的時間較長或法律影響。 沿著[!DNL Marketo Measure]快速入門的路徑進行，可讓您儘可能減少對CRM的依賴，而有效地實作及執行[!DNL Marketo Measure]。

## 標準[!DNL Marketo Measure]安裝 {#standard-marketo-measure-installation}

透過標準[!DNL Marketo Measure]安裝，您必須安裝[!DNL Salesforce]封裝或[!DNL Microsoft Dynamics]受管理解決方案。 安裝包括新增到CRM的自訂物件/實體和自訂欄位，然後[!DNL Marketo Measure]可以將資料寫入其中。

與[!DNL Marketo Measure]的無封裝整合適用於不想在CRM中建立自訂物件/實體或自訂欄位的客戶。 對於使用外部Data Warehouse的客戶來說，這也是個不錯的選擇。

## 權限 {#permissions}

[!DNL Marketo Measure] CRM無封裝整合仍需要存取標準CRM物件，例如銷售機會和聯絡人。 建議將專用使用者作為已連線的使用者，因為他們擁有適當的資料存取許可權。

為確保所有資料都能從您的CRM正確提取，我們要求下列安全性和協助工具設定：檢視專用使用者設定檔的所有資料。 此許可權集可授予[!DNL Marketo Measure]從標準物件下載資料所需的存取權。 此許可權集位於設定檔層級。

## 設定您的身分提供者和資料連線 {#setup-your-identity-provider-and-data-connections}

在以下指南中，請略過安裝[!DNL Salesforce]套件或[!DNL Microsoft Dynamics]受管理解決方案的步驟，並僅遵循許可權和整合指示。

[!DNL Salesforce]客戶按一下[這裡](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md)。

[!DNL Microsoft Dynamics]客戶按一下[這裡](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md)。

完成這些步驟後，整合應該可正常運作。 如果您遇到任何問題，請聯絡您的[!DNL Marketo Measure]代表或[Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}。

>[!NOTE]
>
>如果您從[!DNL Marketo Measure] CRM無封裝整合開始，您稍後可以安裝Salesforce套件或Microsoft Dynamics管理的解決方案。
