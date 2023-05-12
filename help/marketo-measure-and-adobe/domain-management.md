---
description: 網域管理 —  [!DNL Marketo Measure]  — 產品檔案
title: 網域管理
exl-id: 4db287a0-0267-463c-a359-266b41f15c59
source-git-commit: 148cc203f1fd2a3b90771f2223bbacacdcfad7b0
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 0%

---

# 網域管理 {#domain-management}

針對啟用IMS的租戶執行 [!DNL Marketo Measure] 在Experience Cloud介面中， [!DNL Marketo Measure] 提供一個介面，讓使用者可管理自己的網域清單。 [!DNL Marketo Measure] 使用者必須先驗證想要追蹤的任何網域 [Adobe Admin Console](https://adminconsole.adobe.com/). 在Admin Console中驗證網域後，使用者可以管理 [!DNL Marketo Measure] 使用這些網域來追蹤網站流量。

## 在Admin Console中新增網域 {#adding-domains-in-admin-console}

具有Adobe Admin Console存取權的IMS使用者可以新增及驗證自己擁有的網域。 域驗證包括為每個域添加DNS記錄，然後允許Admin Console驗證該記錄。

![](assets/domain-management-1.png)

如需新增網域的指示，請參閱 [Admin Console檔案](https://helpx.adobe.com/enterprise/using/set-up-identity.html#setup-domains). 新增網域後，必須 [連結到目錄](https://helpx.adobe.com/enterprise/using/set-up-identity.html#link-domains-to-directories).

## 管理中的網域 [!DNL Marketo Measure] {#managing-domains-in-marketo-measure}

在Admin Console中新增網域後， [!DNL Marketo Measure] 會定期將此記錄同步到資料庫中。 此同步會在每晚，也會在使用者每次造訪 **[!UICONTROL Domains]** 頁面 [!DNL Marketo Measure] UI。 預設情況下， [!DNL Marketo Measure] 將禁用導入，租戶必須手動啟用每個域。

![](assets/domain-management-2.png)

在 **[!UICONTROL Integration]** > **[!UICONTROL Domains]** 頁面，則使用者會看到他們在Admin Console中註冊的所有網域及其狀態。 每個網域均可啟用或停用。 如果已啟用網域， [!DNL Marketo Measure] 追蹤會收集該網域上顯示的任何流量。 如果域被禁用， [!DNL Marketo Measure] 會忽略從該網域看到的任何流量，且不會建立接觸點或其他資料。 [!DNL Marketo Measure] 也會確認網域的停用並警告後果：

![](assets/domain-management-3.png)

切換網域會立即產生影響，且變更不可回溯。 未來， [!DNL Marketo Measure] 會在設定的時段後清除已停用網域的資料。

## 狀態 {#statuses}

Admin Console狀態分類如下：

* **已驗證**:此域已在Admin Console中驗證
* **未驗證**:此網域未在Admin Console中完全驗證，且不符合在 [!DNL Marketo Measure]
* **無效**:此域可能已過期或已從Admin Console中刪除。 在中追蹤資料 [!DNL Marketo Measure] 已標籤為刪除
* **舊版**:此域建立於 [!DNL Marketo Measure] 和不存在於Admin Console中

追蹤狀態如下：

* **活動**: [!DNL Marketo Measure] 正在接收來自此域的資料
* **已停用**:此網域可供追蹤，但目前已停用
* **不可用**:此域無法進行跟蹤，因為未驗證

將滑鼠暫留在任何個別狀態項目上，會觸發工具提示，進一步說明該狀態。

## 常見問題集 {#faq}

**移除Admin Console中的網域時會發生什麼事？**

移除Admin Console中的網域時， [!DNL Marketo Measure] 會將網域標示為已刪除。 [!DNL Marketo Measure] 會立即停止此網域的追蹤流量，但不會移除先前收集的任何資料。

**為何無法啟用網域？**

此頁面上不允許選取網域的數個原因如下。 如果未在Admin Console中驗證網域，則無法在 [!DNL Marketo Measure]. 同樣地，如果網域擁有者是與目前不同的Adobe組織 [!DNL Marketo Measure] 租用戶，則可能無法進行選擇。

**如何從此清單中刪除域？**

如果域已關閉「已啟用」開關， [!DNL Marketo Measure] 會忽略它，並有效地從 [!DNL Marketo Measure]. 從中永久刪除域 [!DNL Marketo Measure]，您必須在中停用 [!DNL Marketo Measure]，並隨後將其從Admin Console中移除。
