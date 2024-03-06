---
description: Adobe Admin Console設定 — Marketo Measure — 產品檔案
title: Adobe Admin Console設定
feature: Installation
exl-id: f9edacae-79e0-408c-ac37-bbe67c185f2d
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---

# Adobe Admin Console設定 {#adobe-admin-console-setup}

使用的第一個步驟 [!DNL Marketo Measure] 是要建立並登入您已布建的Adobe Admin Console。 如果您尚未收到包含登入指示的電子郵件，請聯絡您的 [!DNL Marketo Measure] 客戶代表。

## 設定您的Adobe Admin Console和身分提供者 {#set-up-your-adobe-admin-console-and-identity-provider}

身為Adobe套裝中的產品， [!DNL Marketo Measure] 使用適用於Identity Management的Adobe Admin Console的完整功能。 更多資源可以 [可在此處找到](https://helpx.adobe.com/tw/enterprise/using/admin-console.html).

建議您檢閱以下專案可用的資源、最佳實務和選項： [Identity Management](https://helpx.adobe.com/enterprise/using/set-up-identity.html).

如需在Adobe Admin Console中設定Identity Management的指導方針和檢閱，請聯絡您的 [!DNL Marketo Measure] 客戶代表。

促進使用者驗證和授權您的 [!DNL Marketo Measure] 執行個體中，Adobe Admin Console需要下列步驟：

**設定 [!DNL Marketo Measure] 產品卡**

存取Adobe Admin Console時，您會看到 [!DNL Marketo Measure] 產品執行個體出現在總覽區段。

![](assets/adobe-admin-console-setup-1.png)

按一下 [!DNL Marketo Measure] 產品卡會顯示您所有的 [!DNL Marketo Measure] 執行個體。 依預設，每個 [!DNL Marketo Measure] 執行個體有自己的設定檔，前置詞為「[!DNL Marketo Measure]&#39;. 任何新增至此或此執行個體中任何其他設定檔的管理員或使用者，都可以登入 [!DNL Marketo Measure].

![](assets/adobe-admin-console-setup-2.png)

不需要採取任何動作即可在 [!DNL Marketo Measure] 產品執行個體。

若要開始新增可以存取的使用者 [!DNL Marketo Measure]，請參閱 [新增 [!DNL Marketo Measure] 管理員和 [!DNL Marketo Measure] 使用者](#adding-marketo-measure-admins-and-marketo-measure-users) 一節。

## 新增 [!DNL Marketo Measure] 管理員和 [!DNL Marketo Measure] 使用者 {#adding-marketo-measure-admins-and-marketo-measure-users}

下一步是授予 [!DNL Marketo Measure] 應用程式，透過新增使用者。 您可以在的admins and users目錄中完成此作業。 [!DNL Marketo Measure] 產品卡。

| 使用者型別 | 說明 |
|---|---|
| 管理員 | 這些是管理員和超級使用者 [!DNL Marketo Measure] 具備完整更新和管理能力的應用程式 [!DNL Marketo Measure]特定組態選項 |
| 使用者 | 這些是 [!DNL Marketo Measure] 內具有唯讀許可權的應用程式 [!DNL Marketo Measure] 應用計畫 |

將使用者新增至其個別群組時，您會看到其 [身分型別已列出](https://helpx.adobe.com/enterprise/using/set-up-identity.html).

>[!NOTE]
>
>成為 [!DNL Marketo Measure] 管理員(在 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"})，則必須將使用者新增為使用者 _和_ 管理員至任何 [!DNL Marketo Measure] 內的產品設定檔 [!DNL Marketo Measure] 產品卡。

**登入[!DNL Marketo Measure]**

將使用者新增至產品設定檔後，他們便能存取其 [!DNL Marketo Measure] 執行個體，方法是選擇 **使用Adobe ID登入** 選項於 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}.

![](assets/adobe-admin-console-setup-3.png)
