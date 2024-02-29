---
description: Data Warehouse存取 — 直接共用 — 產品檔案
title: Data Warehouse存取 — 直接共用
exl-id: 940c3316-5f94-4aa2-a656-aec5eb7b7450
feature: Data Warehouse
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%

---

# Data Warehouse存取 — 直接共用 {#data-warehouse-access-direct-share}

## 需求 {#requirements}

為了 [!DNL Marketo Measure] 若要設定直接共用至Data Warehouse，您必須符合下列需求。

* 您有自己的Snowflake例項。
* 您的Snowflake執行個體位於Azure East US 2Snowflake區域。
* 您提供 [!DNL Marketo Measure] 連同您的Snowflake帳戶id。

## 限制 {#limitations}

[!DNL Marketo Measure] 由於目前的Snowflake直接共用限制，將只能以Azure East US 2中的帳戶設定Snowflake直接共用。 如果您要求將您的資料開放在其他Snowflake地區使用，建議您在Azure East US 2的Snowflake帳戶中製作資料副本，並運用 [Snowflake資料庫復寫](https://docs.snowflake.com/en/user-guide/database-replication-intro.html){target="_blank"} 功能，可在您選擇的Snowflake地區/帳戶中複製您的資料。

## 輸入Snowflake帳戶ID {#enter-snowflake-account-id}

開啟 **設定** 區段並導覽至Marketo Measure應用程式中的 **Data Warehouse** 頁面。 在 **直接共用** 區段，輸入您的 [Snowflake帳戶id](https://docs.snowflake.com/en/user-guide/admin-account-identifier.html){target="_blank"} 在提供的方塊中，然後按一下 **連線**.

![](assets/data-warehouse-access-direct-share-1.png)

## 存取共用 {#accessing-the-share}

為提供的帳戶ID建立共用後，您必須完成 [設定步驟](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"} 在您的Snowflake例項中以便存取資料。

>[!NOTE]
>
>您可以選擇任何想要的資料庫名稱。 只要許可權存在於您的Snowflake執行個體中，您就可以將許可權指派給您選擇的任何角色。

* 使用帳戶管理員角色

```
USE ROLE ACCOUNTADMIN
```

* 檢視可用的共用（這會顯示授與的共用名稱）

```
SHOW SHARES
```

* 為共用建立資料庫

```
CREATE DATABASE <database_name> FROM SHARE <provider_account>.<share_name>
```

* 授與共用資料庫的許可權

```
GRANT IMPORTED PRIVILEGES ON DATABASE <database_name> TO ROLE <role_name>
GRANT IMPORTED PRIVILEGES ON ALL SCHEMAS IN DATABASE <database_name> TO ROLE <role_name>
```

如需從SnowflakeUI完成這些步驟的詳細指示和步驟，請參閱 [直接取得Snowflake的檔案](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"}.
