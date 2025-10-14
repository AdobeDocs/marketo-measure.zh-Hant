---
unique-page-id: 18874789
description: '[!DNL Marketo Measure]許可權集 —  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure]許可權集'
exl-id: 84b7aa24-3934-4584-af05-02e804d00a98
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

---

# [!DNL Marketo Measure]許可權集 {#marketo-measure-permission-sets}

瞭解如何在Salesforce中存取及指派[!DNL Marketo Measure]許可權集。

## [!DNL Marketo Measure]許可權集 {#marketo-measure-permission-sets-1}

[!DNL Marketo Measure] Salesforce套件包含三個許可權集。 這些許可權集可讓管理員、行銷人員和標準使用者存取[!DNL Marketo Measure]。

若要在Salesforce中存取及指派許可權集：

1. 按一下「**[!UICONTROL Setup]**」。
1. 在左邊界中，按一下&#x200B;**[!UICONTROL Users]**，然後按&#x200B;**[!UICONTROL Permission Sets]**。
1. 選取您要指派的[!DNL Marketo Measure]許可權集。
1. 按一下&#x200B;**[!UICONTROL Manage Assignments]**，然後按&#x200B;**[!UICONTROL Add Assignments]**。
1. 選取許可權集的使用者並按一下&#x200B;**[!UICONTROL Assign]**。

   ![](assets/1-5.png)

## 說明[!DNL Marketo Measure]許可權集 {#marketo-measure-permission-sets-explained}

<table> 
 <tbody> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] 管理員</strong></span></td> 
   <td><span>讓SFDC管理員能從[!DNL Marketo Measure]物件建立、讀取、寫入及刪除記錄。 [!DNL Marketo Measure]將資料推送至SFDC的授權應啟用此許可權集。 此外，建議此授權能夠編輯轉換的銷售機會，在[!DNL Marketo Measure]將資料套用至記錄之前轉換的銷售機會。 這可確保Salesforce與[!DNL Marketo Measure]之間報表的正確性。 <a href="https://help.salesforce.com/articleView?id=release-notes.rn_sales_leads_view_converted.htm&type=5&release=206&language=en_us">在此閱讀更多資訊</a>。</span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] 行銷使用者</strong></span></td> 
   <td><span>讓行銷使用者能夠讀取和寫入[!DNL Marketo Measure]物件的記錄。 行銷團隊的所有成員都應該啟用[!DNL Marketo Measure]行銷使用者許可權集。 <br></span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] 標準使用者</strong></span></td> 
   <td><span>讓使用者能夠讀取[!DNL Marketo Measure]物件的記錄。</span></td> 
  </tr> 
 </tbody> 
</table>

傳入的銷售開發團隊和客戶高階主管可能會受益於[!DNL Marketo Measure]資料。 如果這些角色想要在報告中使用[!DNL Marketo Measure]資料，請啟用[!DNL Marketo Measure]標準使用者許可權集。

>[!NOTE]
>
>此外，我們透過連線的使用者必須在使用者層級啟用「行銷使用者」[!DNL Salesforce]設定檔，我們才能存取Campaign物件。 若要檢查此專案，請按一下&#x200B;**[!UICONTROL Setup]** > **[!UICONTROL Manage Users]** > **[!UICONTROL Profiles]** > **[!UICONTROL Marketing User]** > **指派的使用者**。
