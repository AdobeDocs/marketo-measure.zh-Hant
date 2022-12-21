---
unique-page-id: 18874789
description: '"[!DNL Marketo Measure] 權限集 —  [!DNL Marketo Measure]  — 產品檔案」'
title: '"[!DNL Marketo Measure] 權限集」'
exl-id: 84b7aa24-3934-4584-af05-02e804d00a98
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# [!DNL Marketo Measure] 權限集 {#marketo-measure-permission-sets}

了解如何存取及指派 [!DNL Marketo Measure] Salesforce中的權限集。

## [!DNL Marketo Measure] 權限集 {#marketo-measure-permission-sets-1}

包含三個權限集 [!DNL Marketo Measure] Salesforce套件。 這些權限集提供 [!DNL Marketo Measure] 適用於管理員、行銷人員和標準使用者。

要訪問和分配Salesforce中的權限集，請執行以下操作：

1. 按一下 **[!UICONTROL Setup]**.
1. 在左邊距中，按一下 **[!UICONTROL Users]**，然後 **[!UICONTROL Permission Sets]**.
1. 選取 [!DNL Marketo Measure] 您要指派的權限集。
1. 按一下 **[!UICONTROL Manage Assignments]**，然後 **[!UICONTROL Add Assignments]**.
1. 為權限集選擇用戶，然後按一下 **[!UICONTROL Assign]**.

   ![](assets/1-5.png)

## [!DNL Marketo Measure] 權限集說明 {#marketo-measure-permission-sets-explained}

<table> 
 <tbody> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] 管理員</strong></span></td> 
   <td><span>使SFDC管理員能夠從中建立、讀取、寫入、刪除記錄 [!DNL Marketo Measure] 對象。 根據 [!DNL Marketo Measure] 將資料推送至SFDC應啟用此權限集。 此外，建議此許可證能夠在銷售機會在之前轉換的情況下編輯轉換的銷售機會 [!DNL Marketo Measure] 將資料套用至記錄。 這可確保Salesforce與 [!DNL Marketo Measure]. <a href="http://releasenotes.docs.salesforce.com/en-us/spring17/release-notes/rn_sales_leads_view_converted.htm">詳情請見</a>.</span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] 行銷使用者</strong></span></td> 
   <td><span>讓行銷使用者能夠從 [!DNL Marketo Measure] 對象。 行銷團隊的所有成員都應 [!DNL Marketo Measure] 已啟用行銷使用者權限集。 <br></span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] 標準使用者</strong></span></td> 
   <td><span>讓使用者能夠從 [!DNL Marketo Measure] 對象。</span></td> 
  </tr> 
 </tbody> 
</table>

入站銷售開發團隊和客戶主管可能受益於 [!DNL Marketo Measure] 資料。 如果這些角色想要使用 [!DNL Marketo Measure] 資料，請啟用 [!DNL Marketo Measure] 標準用戶權限集。

>[!NOTE]
>
>此外，我們所連線的使用者需要有「行銷使用者」 [!DNL Salesforce] 在使用者層級啟用設定檔，以便我們存取Campaign物件。 若要檢查，請按一下 **[!UICONTROL Setup]** > **[!UICONTROL Manage Users]** > **[!UICONTROL Profiles]** > **[!UICONTROL Marketing User]** > **指派的使用者**.
