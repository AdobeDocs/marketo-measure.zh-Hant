---
unique-page-id: 18874698
description: 建立 [!DNL Marketo Measure] 設定檔 —  [!DNL Marketo Measure]  — 產品檔案
title: 建立 [!DNL Marketo Measure] 設定檔
exl-id: dab2e2cb-fbd3-464a-9bd7-e9bf153d9848
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 0%

---

# 建立 [!DNL Marketo Measure] 設定檔 {#creating-a-marketo-measure-profile}

了解如何建立 [!DNL Marketo Measure] 設定檔。 建立 [!DNL Marketo Measure] 設定檔可確保在將資料推送至您的CRM時，不會發生驗證錯誤。

1. 建立特定 [!DNL Marketo Measure] 設定檔：

   * 指派 [!DNL Marketo Measure] 管理員權限集
   * 啟用查看和編輯轉換的銷售線索的權限

   >[!NOTE]
   >
   >此設定檔可以是 [!DNL System Admin] 設定檔

1. 建立專用 [!DNL Marketo Measure] 使用者：

   * 指派新 [!DNL Marketo Measure] 向該使用者設定檔
   * 啟用「行銷使用者」作為使用者層級權限

1. 從所有觸發器、工作流程和程式中排除此設定檔。
1. 登入 [!DNL Marketo Measure] 帳戶並重新授權 [!DNL Salesforce] 與新用戶的連接：

   * 前往 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target=&quot;_blank&quot;}並使用新的用戶生產Salesforce憑據登錄
   * 選擇「[!UICONTROL Settings]&quot;[!UICONTROL My Account]&quot;下拉式清單
   * 選擇「[!UICONTROL Connections]&quot;[!UICONTROL Integrations]&quot;分組&quot;
   * 按一下當前已連接的右側的鍵表徵圖 [!DNL Salesforce] 連線，然後選取「透過生產重新授權」 。 如果出現提示，則使用新用戶憑據重新登錄

   完成!

   如果您對建立專用 [!DNL Marketo Measure] 設定檔請洽詢您的客戶成功經理，或 [Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;}。
