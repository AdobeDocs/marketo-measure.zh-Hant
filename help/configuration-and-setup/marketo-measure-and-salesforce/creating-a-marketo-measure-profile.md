---
unique-page-id: 18874698
description: 建立 [!DNL Marketo Measure] 設定檔 —  [!DNL Marketo Measure]  — 產品檔案
title: 建立 [!DNL Marketo Measure] 個人資料
exl-id: dab2e2cb-fbd3-464a-9bd7-e9bf153d9848
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# 建立 [!DNL Marketo Measure] 個人資料 {#creating-a-marketo-measure-profile}

瞭解如何建立 [!DNL Marketo Measure] 設定檔。 建立 [!DNL Marketo Measure] 設定檔可確保在推送資料至您的CRM時不會發生驗證錯誤。

1. 建立特定 [!DNL Marketo Measure] 設定檔：

   * 指派 [!DNL Marketo Measure] 管理員許可權集
   * 啟用檢視和編輯已轉換潛在客戶的許可權

   >[!NOTE]
   >
   >此設定檔可以是 [!DNL System Admin] 設定檔

1. 已建立專用的 [!DNL Marketo Measure] 使用者：

   * 指派新的 [!DNL Marketo Measure] 該使用者的設定檔
   * 啟用「行銷使用者」作為使用者層級的許可權

1. 從所有觸發器、工作流程和流程中排除此設定檔。
1. 登入您的 [!DNL Marketo Measure] 帳戶並重新授權 [!DNL Salesforce] 與新使用者的連線：

   * 前往 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} 並使用新的使用者生產Salesforce憑證登入
   * 選取「[!UICONTROL Settings]「 （在「」中）[!UICONTROL My Account]「下拉式清單
   * 選取「[!UICONTROL Connections]「 （在「」中）[!UICONTROL Integrations]&quot;分組
   * 按一下目前連線右側的按鍵圖示 [!DNL Salesforce] 連線並選取「 」以使用生產環境重新授權。 然後在出現提示時，使用新的使用者認證再次登入

   完成!

   如果您對建立專屬檔案有任何疑問， [!DNL Marketo Measure] 設定檔，請聯絡Adobe客戶團隊（您的客戶經理）或 [Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
