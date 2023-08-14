---
unique-page-id: 18874789
description: '"[!DNL Marketo Measure] 許可權集 —  [!DNL Marketo Measure]  — 產品檔案」'
title: '"[!DNL Marketo Measure] 許可權集」'
exl-id: 84b7aa24-3934-4584-af05-02e804d00a98
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# [!DNL Marketo Measure] 許可權集 {#marketo-measure-permission-sets}

瞭解如何存取和指派 [!DNL Marketo Measure] Salesforce中的許可權集。

## [!DNL Marketo Measure] 許可權集 {#marketo-measure-permission-sets-1}

隨附三個許可權集 [!DNL Marketo Measure] Salesforce套件。 這些許可權集提供存取許可權 [!DNL Marketo Measure] 適用於管理員、行銷人員和標準使用者。

若要在Salesforce中存取及指派許可權集：

1. 按一下 **[!UICONTROL Setup]**.
1. 在左邊界中，按一下 **[!UICONTROL Users]**，然後 **[!UICONTROL Permission Sets]**.
1. 選取 [!DNL Marketo Measure] 您要指派的許可權集。
1. 按一下 **[!UICONTROL Manage Assignments]**，然後 **[!UICONTROL Add Assignments]**.
1. 選取許可權集的使用者並按一下 **[!UICONTROL Assign]**.

   ![](assets/1-5.png)

## [!DNL Marketo Measure] 說明許可權集 {#marketo-measure-permission-sets-explained}

<table> 
 <tbody> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] 管理員</strong></span></td> 
   <td><span>讓SFDC管理員能夠建立、讀取、寫入、刪除記錄 [!DNL Marketo Measure] 物件。 使用授權的 [!DNL Marketo Measure] 將資料推送至SFDC時，應啟用此許可權集。 此外，在以下情況下，建議此授權能夠編輯轉換的Lead：之前轉換的Lead [!DNL Marketo Measure] 將資料套用至記錄。 這將確保Salesforce和之間的報告準確性 [!DNL Marketo Measure]. <a href="http://releasenotes.docs.salesforce.com/en-us/spring17/release-notes/rn_sales_leads_view_converted.htm">請在此閱讀詳情</a>.</span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] 行銷使用者</strong></span></td> 
   <td><span>讓行銷使用者能夠讀取和寫入記錄 [!DNL Marketo Measure] 物件。 行銷團隊的所有成員應該 [!DNL Marketo Measure] 已啟用行銷使用者許可權集。 <br></span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] 標準使用者</strong></span></td> 
   <td><span>讓使用者能夠讀取記錄 [!DNL Marketo Measure] 物件。</span></td> 
  </tr> 
 </tbody> 
</table>

傳入的銷售開發團隊和客戶高階主管可能會受益於 [!DNL Marketo Measure] 資料。 如果這些角色想要使用 [!DNL Marketo Measure] 資料在報表中，啟用 [!DNL Marketo Measure] 標準使用者許可權集。

>[!NOTE]
>
>此外，我們連線的使用者必須擁有「行銷使用者」 [!DNL Salesforce] 設定檔已啟用至使用者層級，以便我們存取Campaign物件。 若要檢查此專案，請按一下 **[!UICONTROL Setup]** > **[!UICONTROL Manage Users]** > **[!UICONTROL Profiles]** > **[!UICONTROL Marketing User]** > **已指派的使用者**.
