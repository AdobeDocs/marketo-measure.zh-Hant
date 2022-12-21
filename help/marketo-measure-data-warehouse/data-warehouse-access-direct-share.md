---
description: Data Warehouse存取 — 直接共用 — 產品檔案
title: Data Warehouse存取 — 直接共用
exl-id: 940c3316-5f94-4aa2-a656-aec5eb7b7450
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 0%

---

# Data Warehouse存取 — 直接共用 {#data-warehouse-access-direct-share}

**需求**

為了 [!DNL Marketo Measure] 若要設定與資料倉庫的直接共用，您必須符合下列需求。

* 您有自己的Snowflake例項。
* 您的Snowflake實例位於Azure East US 2Snowflake區域。
* 您提供 [!DNL Marketo Measure] 使用您的Snowflake帳戶id。

**限制**

[!DNL Marketo Measure] 因為目前的Snowflake直接共用限制，只能與位於Azure East US 2的帳戶設定Snowflake直接共用。 如果您需要讓您的資料在其他Snowflake地區可用，建議您在位於Azure East US 2的Snowflake帳戶中複製資料，並運用 [Snowflake資料庫複製](https://docs.snowflake.com/en/user-guide/database-replication-intro.html){target=&quot;_blank&quot;}功能，以複製您所選Snowflake地區/帳戶中的資料。

**存取共用**

為提供的帳戶id建立共用後，您必須完成 [設定步驟](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target=&quot;_blank&quot;})，以存取Snowflake例項中的資料。

>[!NOTE]
>
>您可以選擇想要的任何資料庫名稱。 您可以將權限指派給您選擇的任何規則，只要該規則存在於您的Snowflake例項中。

* 使用帳戶管理員角色

```
USE ROLE ACCOUNTADMIN
```

* 檢視可用股份（這會顯示已授出股份的名稱）

```
SHOW SHARES
```

* 為共用建立資料庫

```
CREATE DATABASE <database_name> FROM SHARE <provider_account>.<share_name>
```

* 授予共用資料庫的權限

```
GRANT IMPORTED PRIVILEGES ON DATABASE <database_name> TO ROLE <role_name>
GRANT IMPORTED PRIVILEGES ON ALL SCHEMAS IN DATABASE <database_name> TO ROLE <role_name>
```

如需從SnowflakeUI完成這些步驟的詳細指示和步驟，請參閱 [Snowflake檔案直接](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target=&quot;_blank&quot;}。
