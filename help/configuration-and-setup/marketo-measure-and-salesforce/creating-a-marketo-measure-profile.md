---
unique-page-id: 18874698
description: 正在建立 [!DNL Marketo Measure] 設定檔 —  [!DNL Marketo Measure]
title: 建立 [!DNL Marketo Measure] 設定檔
exl-id: dab2e2cb-fbd3-464a-9bd7-e9bf153d9848
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 0%

---

# 建立[!DNL Marketo Measure]設定檔 {#creating-a-marketo-measure-profile}

瞭解如何建立[!DNL Marketo Measure]設定檔。 建立[!DNL Marketo Measure]設定檔可確保推送資料至您的CRM時，不會發生驗證錯誤。

1. 建立特定的[!DNL Marketo Measure]設定檔：

   * 指派[!DNL Marketo Measure]系統管理員許可權集
   * 啟用檢視和編輯已轉換潛在客戶的許可權

   >[!NOTE]
   >
   >此設定檔可以是[!DNL System Admin]設定檔的複製

1. 已建立專用的[!DNL Marketo Measure]使用者：

   * 將新的[!DNL Marketo Measure]設定檔指派給該使用者
   * 啟用「行銷使用者」作為使用者層級的許可權

1. 從所有觸發器、工作流程和流程中排除此設定檔。
1. 登入您的[!DNL Marketo Measure]帳戶並重新授權與新使用者的[!DNL Salesforce]連線：

   * 移至[experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}並使用新的使用者生產Salesforce認證登入
   * 在「[!UICONTROL My Account]」下拉式清單中選取「[!UICONTROL Settings]」
   * 在「[!UICONTROL Integrations]」群組中選取「[!UICONTROL Connections]」
   * 按一下目前連線的[!DNL Salesforce]連線右側的按鍵圖示，然後選取「使用生產重新授權」。 然後在出現提示時，使用新的使用者認證再次登入

   完成！

   如果您對建立專用的[!DNL Marketo Measure]設定檔有任何疑問，請聯絡Adobe帳戶團隊（您的帳戶經理）或[Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}。
