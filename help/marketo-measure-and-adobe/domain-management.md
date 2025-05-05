---
description: 網域管理 —  [!DNL Marketo Measure]
title: 網域管理
exl-id: 4db287a0-0267-463c-a359-266b41f15c59
feature: Integration, Tracking
source-git-commit: 4c68fa08797c252a89ba097c723fb8afee82451f
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%

---

# 網域管理 {#domain-management}

對於在Experience Cloud介面中執行[!DNL Marketo Measure]且已啟用IMS的租使用者，[!DNL Marketo Measure]提供可讓使用者管理自己網域清單的介面。 [!DNL Marketo Measure]使用者必須先確認他們要在[Adobe Admin Console](https://adminconsole.adobe.com/)中追蹤的任何網域。 在Admin Console中驗證網域後，使用者可以管理[!DNL Marketo Measure]是否使用這些網域來追蹤網站流量。

## 在Admin Console中新增網域 {#adding-domains-in-admin-console}

有權存取Adobe Admin Console的IMS使用者可以新增及驗證他們擁有的網域。 網域驗證涉及為每個網域新增DNS記錄，然後允許Admin Console驗證該記錄。

![](assets/domain-management-1.png)

您可以在[Admin Console檔案](https://helpx.adobe.com/tw/enterprise/using/add-domains-directories.html)中找到新增網域的指示。 新增網域後，它必須是[連結到目錄](https://helpx.adobe.com/tw/enterprise/using/add-domains-directories.html#link-domains-to-directoies)。

## 在[!DNL Marketo Measure]中管理網域 {#managing-domains-in-marketo-measure}

在Admin Console中新增網域後，[!DNL Marketo Measure]會定期將此記錄同步到資料庫中。 此同步會在夜間進行，也可在使用者每次在[!DNL Marketo Measure] UI中造訪&#x200B;**[!UICONTROL Domains]**&#x200B;頁面時進行。 依預設，[!DNL Marketo Measure]匯入的任何記錄都會停用，租使用者必須手動啟用每個網域。

![](assets/domain-management-2.png)

在&#x200B;**[!UICONTROL Integration]** > **[!UICONTROL Domains]**&#x200B;頁面上，使用者會看見已在Admin Console中註冊的所有網域，以及其狀態。 每個網域都可以啟用或停用。 如果已啟用網域，[!DNL Marketo Measure]追蹤會收集在該網域上看到的任何流量。 如果網域已停用，[!DNL Marketo Measure]會忽略來自該網域的任何流量，而不會建立接觸點或其他資料。 [!DNL Marketo Measure]會確認網域已停用，並警告任何後果：

![](assets/domain-management-3.png)

切換網域的影響是立即的，而且變更不會回溯。 將來，[!DNL Marketo Measure]會在設定的期間之後，從停用的網域中清除資料。

## 狀態 {#statuses}

Admin Console狀態會依下列方式分類：

* **已驗證**：此網域已在Admin Console中驗證
* **未驗證**：此網域未在Admin Console中完全驗證，因此不符合[!DNL Marketo Measure]中的追蹤資格
* **無效**：此網域可能已過期或已從Admin Console中移除。 [!DNL Marketo Measure]中的追蹤資料已標籤為刪除
* **LEGACY**：此網域是在[!DNL Marketo Measure]中建立且不存在於Admin Console中

追蹤狀態如下所示：

* **作用中**： [!DNL Marketo Measure]正在接收來自此網域的資料
* **已停用**：此網域可用於追蹤，但已停用
* **無法使用**：此網域無法用於追蹤，因為它未驗證

將滑鼠懸停在任何個別狀態專案上會觸發工具提示，進一步說明該狀態。

## 常見問題集 {#faq}

**移除Admin Console中的網域後會發生什麼事？**

在Admin Console中移除網域時，[!DNL Marketo Measure]會將網域標籤為已刪除。 [!DNL Marketo Measure]會立即停止追蹤此網域上的流量，但不會移除任何先前收集的資料。

**為什麼我無法啟用網域？**

有幾個原因可能會禁止在此頁面上選取網域。 如果未在Admin Console中驗證網域，則它在[!DNL Marketo Measure]中無法使用。 同樣地，如果網域屬於與目前[!DNL Marketo Measure]租使用者不同的Adobe組織，則可能無法選取網域。

**如何從此清單移除網域？**

如果網域已關閉「已啟用」開關，[!DNL Marketo Measure]會忽略該開關並將其從[!DNL Marketo Measure]中有效移除。 若要從[!DNL Marketo Measure]永久移除網域，您必須在[!DNL Marketo Measure]中停用該網域，然後從Admin Console中移除它。
