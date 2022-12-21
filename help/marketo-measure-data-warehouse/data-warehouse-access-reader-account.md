---
description: Data Warehouse存取 — Reader帳戶 — 產品檔案
title: Data Warehouse存取 — Reader帳戶
exl-id: 2aa73c41-47ab-4f11-96d8-dafb642308fc
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 0%

---

# Data Warehouse存取 — Reader帳戶 {#data-warehouse-access-reader-account}

## Snowflake存取連結 {#snowflake-access-link}

若要存取Snowflake資料倉庫，您必須導覽至Snowflake帳戶的特定URL。 您可以登入以找到此存取連結 [!DNL Marketo Measure] 並依照下列步驟導覽至「Data Warehouse資訊」頁面。

1. 在 [!DNL Marketo Measure]，在頁面頂端按一下 **[!UICONTROL My Account]** > **[!UICONTROL Settings]**.

   ![](assets/data-warehouse-access-reader-account-1.png)

1. 在左側功能表的「安全」下，按一下 **[!UICONTROL Data Warehouse]**.

   ![](assets/data-warehouse-access-reader-account-2.png)

1. 在此頁面上，您會找到Snowflake資料倉庫和使用者名稱的連結。

   ![](assets/data-warehouse-access-reader-account-3.png)

   >[!NOTE]
   >
   >這是唯讀帳戶，可供您的組織使用，而不只是個別使用者使用。 您組織內可存取 [!DNL Marketo Measure] 可以使用此帳戶登入SnowflakeData Warehouse讀取器帳戶。

1. 按一下SnowflakeURL中提供的連結，這會帶您前往Snowflake登入頁面，在該頁面中輸入您的使用者名稱和密碼。 _如果您沒有密碼，請參閱下列步驟以重設密碼_.

   ![](assets/data-warehouse-access-reader-account-4.png)

1. 登入後，按一下 **[!UICONTROL Worksheets]** 頁面頂端。

   ![](assets/data-warehouse-access-reader-account-5.png)

1. BIZIBLE_ROI_V3資料庫對象位於螢幕左側。 在查詢窗口頂部的下拉清單選項中輸入倉庫、資料庫和架構。 每個應該只有一個選項。 現在，您可以在Snowflake查詢編輯器內執行查詢。

   ![](assets/data-warehouse-access-reader-account-6.png)

## 重設密碼 {#reset-your-password}

[!DNL Marketo Measure] 無權訪問您的Snowflake登錄密碼。 如果您需要重設密碼，請按一下 [!UICONTROL Reset Password] 按鈕，並按照說明操作。 UI中會立即顯示暫時密碼。 系統會提示您在下次資料倉庫登錄時建立自己的密碼。

>[!NOTE]
>
>* 重設密碼會重設所有密碼 [!DNL Marketo Measure] 您組織中的使用者，而不只是目前登入的使用者。
>* 我們只會在UI中顯示暫時密碼。 不會傳送電子郵件。


![](assets/data-warehouse-access-reader-account-7.png)

![](assets/data-warehouse-access-reader-account-8.png)

## 透過協力廠商工具連線至Snowflake {#connecting-to-snowflake-via-third-party-tools}

您需要輸入一些資訊，以將您的Snowflake資料倉庫連結至協力廠商工具。

>[!NOTE]
>
>每個工具的連接要求不同；建議您參閱本檔案，以取得您嘗試連線的特定工具。

* **URI** （一律為必要）
   * 這是Snowflake帳戶的網域名稱。  它包含在Snowflake登入連結的一部分中。
* **使用者名稱** （一律為必要）
   * 使用者名稱會列在的Data Warehouse資訊頁面上 [!DNL Marketo Measure].
* **密碼** （一律為必要）
   * 這是您第一次登入Snowflake帳戶時設定的密碼。  若要重設密碼，請參閱上述步驟。
* **資料庫名稱** （不一律為必要）
   * 資料庫是將資料儲存在Snowflake中的。 這是儲存資源。 資料庫名稱列在的「Data Warehouse資訊」頁面上。 [!DNL Marketo Measure].
* **倉庫名稱** （不一律為必要）
   * 倉庫是在Snowflake中執行查詢的原因。 它是計算資源。  倉庫名稱列在以下位置的Data Warehouse資訊頁面上： [!DNL Marketo Measure].
   ![](assets/data-warehouse-access-reader-account-9.png)
