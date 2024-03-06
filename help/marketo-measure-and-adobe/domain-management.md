---
description: 網域管理 —  [!DNL Marketo Measure]
title: 網域管理
exl-id: 4db287a0-0267-463c-a359-266b41f15c59
feature: Integration, Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%

---

# 網域管理 {#domain-management}

針對正在執行的IMS啟用租使用者 [!DNL Marketo Measure] 在Experience Cloud介面中， [!DNL Marketo Measure] 提供可讓使用者管理自己網域清單的介面。 [!DNL Marketo Measure] 使用者必須先確認要在「 」中追蹤的任何網域 [Adobe Admin Console](https://adminconsole.adobe.com/). 在Admin Console中驗證網域後，使用者可以管理 [!DNL Marketo Measure] 會使用這些網域來追蹤網站流量。

## 在Admin Console中新增網域 {#adding-domains-in-admin-console}

有權存取Adobe Admin Console的IMS使用者可以新增及驗證他們擁有的網域。 網域驗證涉及為每個網域新增DNS記錄，然後允許Admin Console驗證該記錄。

![](assets/domain-management-1.png)

新增網域的指示可在以下網址找到： [Admin Console檔案](https://helpx.adobe.com/enterprise/using/set-up-identity.html#setup-domains). 新增網域後，它必須 [連結至目錄](https://helpx.adobe.com/enterprise/using/set-up-identity.html#link-domains-to-directories).

## 在中管理網域 [!DNL Marketo Measure] {#managing-domains-in-marketo-measure}

在Admin Console中新增網域後， [!DNL Marketo Measure] 會定期將此記錄同步至資料庫。 此同步會在夜間進行，也可在使用者每次造訪網站時進行 **[!UICONTROL Domains]** 中的頁面 [!DNL Marketo Measure] UI。 根據預設，任何 [!DNL Marketo Measure] 匯入已停用，租使用者必須手動啟用每個網域。

![](assets/domain-management-2.png)

在 **[!UICONTROL Integration]** > **[!UICONTROL Domains]** 頁面中，使用者會看見已在Admin Console中註冊的所有網域，以及其狀態。 每個網域都可以啟用或停用。 如果已啟用網域， [!DNL Marketo Measure] 追蹤會收集在該網域上看到的任何流量。 如果網域已停用， [!DNL Marketo Measure] 會忽略來自該網域的任何流量，且不會建立接觸點或其他資料。 [!DNL Marketo Measure] 確認網域停用，並警告任何後果：

![](assets/domain-management-3.png)

切換網域的影響是立即的，而且變更不會回溯。 未來， [!DNL Marketo Measure] 將會在設定的時段後從停用的網域中清除資料。

## 狀態 {#statuses}

Admin Console狀態會依下列方式分類：

* **已驗證**：此網域已在Admin Console中驗證
* **未驗證**：此網域在Admin Console中未完全驗證，因此不符合在中追蹤的資格 [!DNL Marketo Measure]
* **無效**：此網域可能已過期或已從Admin Console中移除。 在中追蹤資料 [!DNL Marketo Measure] 已標籤為刪除
* **舊版**：此網域建立於 [!DNL Marketo Measure] 而且不存在於Admin Console中

追蹤狀態如下所示：

* **作用中**： [!DNL Marketo Measure] 正在接收來自此網域的資料
* **已停用**：此網域可用於追蹤，但已停用
* **無法使用**：此網域無法用於追蹤，因為它未驗證

將滑鼠懸停在任何個別狀態專案上會觸發工具提示，進一步說明該狀態。

## 常見問題集 {#faq}

**移除Admin Console中的網域時會發生什麼事？**

在Admin Console中移除網域時， [!DNL Marketo Measure] 將網域標籤為已刪除。 [!DNL Marketo Measure] 會立即停止追蹤此網域上的流量，但不會移除任何先前收集的資料。

**為什麼我無法啟用網域？**

有幾個原因可能會禁止在此頁面上選取網域。 如果未在Admin Console中驗證網域，則在 [!DNL Marketo Measure]. 同樣地，如果網域屬於與目前不同的Adobe組織 [!DNL Marketo Measure] 租使用者，可能無法選取。

**如何從此清單移除網域？**

如果網域已關閉「已啟用」開關， [!DNL Marketo Measure] 會忽略該檔案，並會將其從有效地移除 [!DNL Marketo Measure]. 若要從下列位置永久移除網域： [!DNL Marketo Measure]，您必須在中停用 [!DNL Marketo Measure]，然後將其從Admin Console中移除。
