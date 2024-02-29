---
unique-page-id: 18874672
description: 如何 [!DNL Marketo Measure] 和 [!DNL Salesforce] Interact - Marketo Measure — 產品檔案
title: 如何 [!DNL Marketo Measure] 和 [!DNL Salesforce] 互動
exl-id: c2f9d7ce-c5b8-4664-8f92-cb54255190cd
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '1263'
ht-degree: 19%

---

# 如何 [!DNL Marketo Measure] 和 [!DNL Salesforce] 互動 {#how-marketo-measure-and-salesforce-interact}

>[!NOTE]
>
>您可能會看到指定&#39;&#39;的說明[!DNL Marketo Measure]&quot;，但仍在您的CRM中看到「Bizible」。 我們正致力於更新此專案，品牌重塑將很快反映在您的CRM中。

讓我們來深入瞭解一下兩者之間的關係 [!DNL Marketo Measure] 和Salesforce。

## Salesforce和 [!DNL Marketo Measure] {#salesforce-and-marketo-measure}

一旦 [!DNL Marketo Measure] 帳戶已建立且 [!DNL Salesforce] 已連線， [!DNL Marketo Measure] 開始推送行銷資料至CRM執行個體，只要 [!DNL Marketo Measure] 已安裝Managed套件，且 [!DNL Marketo Measure] Salesforce使用者擁有編輯許可權。

如果您未安裝 [!DNL Marketo Measure] Salesforce套件， [!DNL Marketo Measure] 不會將任何資料寫入您的Salesforce執行個體。

![](assets/1-3.png)

根據預設， [!DNL Marketo Measure] 每次工作將資料傳送至您的CRM時，都會匯出每個API評分200筆記錄。 對於大多數客戶而言，這可提供以下專案所耗用的API積分之間的最佳平衡 [!DNL Marketo Measure] 和CRM的CPU資源需求。 不過，對於具有複雜CRM設定（例如工作流程和觸發器）的客戶，較小的批次大小可能有助於改善CRM效能。 為此， [!DNL Marketo Measure] 允許客戶設定CRM匯出批次大小。 此設定可在 [!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL General] 中的頁面 [!DNL Marketo Measure] Web應用程式和客戶可以選擇批次大小200 （預設）、100、50或25。

![](assets/how-bizible-and-salesforce-interact-2.png)

修改此設定時，請記住，較小的批次大小會消耗您CRM的更多API積分。 建議您只有在CRM中遇到CPU逾時或CPU負載過高時，才減少批次大小。

## Salesforce標準物件與存取 {#salesforce-standard-objects-and-access}

這會列出 [!DNL Salesforce] 符合以下條件的標準物件： [!DNL Marketo Measure] 會與互動，在建立連線後，我們將自訂欄位新增到這些物件， [!DNL Marketo Measure] 已安裝套件。 立即可用， [!DNL Marketo Measure] 不會寫入任何標準 [!DNL Salesforce] 物件欄位。

**銷售機會**

<table> 
 <tbody> 
  <tr> 
   <th>欄位</th> 
   <th>標準/自訂</th> 
   <th>讀取</th> 
   <th>寫入</th> 
  </tr> 
  <tr> 
   <td>ID</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>電子郵件</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>狀態</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ConvertedDate</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ConvertedContactId</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ConvertedOpportunityId</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsConverted</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDeleted</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>網站</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>公司</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>bizible2__Account__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Campaign_Name_FT__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Campaign_Name_LC__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Landing_Page_FT__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Landing_Page_LC__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Marketing_Channel_FT__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Marketing_Channel_LC__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Date_FT__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Date_LC__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Source_FT__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Source_LC__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x </td> 
  </tr> 
 </tbody> 
</table>

**連絡人**

<table> 
 <tbody> 
  <tr> 
   <th>欄位</th> 
   <th>標準/自訂</th> 
   <th>讀取</th> 
   <th>寫入</th> 
  </tr> 
  <tr> 
   <td>帳戶</td> 
   <td>標準</td> 
   <td><span>x</span></td> 
   <td><br></td> 
  </tr> 
  <tr> 
   <td>ID</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>電子郵件</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>建立日期</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDeleted</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Campaign_Name_FT__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Campaign_Name_LC__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Landing_Page_FT__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Landing_Page_LC__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Marketing_Channel_FT__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Marketing_Channel_LC__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Date_FT__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Date_LC__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Source_FT__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Source_LC__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x </td> 
  </tr> 
 </tbody> 
</table>

**案例**

<table> 
 <tbody> 
  <tr> 
   <th>欄位</th> 
   <th>標準/自訂</th> 
   <th>讀取</th> 
   <th>寫入</th> 
  </tr> 
  <tr> 
   <td>ID</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>提供的電子郵件</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDeleted</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Campaign_Name_FT__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Campaign_Name_LC__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Landing_Page_FT__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Landing_Page_LC__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Marketing_Channel_FT__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Marketing_Channel_LC__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Date_FT__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Date_LC__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Source_FT__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Source_LC__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x </td> 
  </tr> 
 </tbody> 
</table>

**帳戶**

<table> 
 <tbody> 
  <tr> 
   <th>欄位</th> 
   <th>標準/自訂</th> 
   <th>讀取</th> 
   <th>寫入</th> 
  </tr> 
  <tr> 
   <td>ID</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>網站</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDeleted</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>bizible2__Engagement_Score__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x </td> 
  </tr> 
 </tbody> 
</table>

**商機**

<table> 
 <tbody> 
  <tr> 
   <th>欄位</th> 
   <th>標準/自訂</th> 
   <th>讀取</th> 
   <th>寫入</th> 
  </tr> 
  <tr> 
   <td>名稱</td> 
   <td>標準</td> 
   <td>x</td> 
   <td><br></td> 
  </tr>
  <tr> 
   <td>帳戶</td> 
   <td>標準</td> 
   <td>x</td> 
   <td><br></td> 
  </tr>
  <tr> 
   <td>ID</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsWon</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsClosed</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDeleted</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>關閉日期</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>階段名稱</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>數量</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>bizible2__Bizible_Opportunity_Amount__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x </td> 
  </tr> 
 </tbody> 
</table>

**機會聯絡人角色**

<table> 
 <tbody> 
  <tr> 
   <th>欄位</th> 
   <th>標準/自訂</th> 
   <th>讀取</th> 
   <th>寫入</th> 
  </tr> 
  <tr> 
   <td>ID</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDeleted</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr>
  <tr> 
   <td>LastModifiedDate</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>商機ID</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>連絡人ID</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr>

<tr> 
   <td>主要的</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>角色</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

**Campaign**

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th>欄位</th> 
   <th>標準/自訂</th> 
   <th>讀取</th> 
   <th>寫入</th> 
  </tr> 
  <tr> 
   <td>ID</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>電子郵件</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>狀態</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ConvertedDate</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ConvertedContactId</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ConvertedOpportunityId</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsConverted</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDeleted</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>網站</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>公司</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>類型</td> 
   <td>標準</td> 
   <td>x</td> 
   <td><br></td> 
  </tr> 
 </tbody> 
</table>

**促銷活動會員**

<table> 
 <tbody> 
  <tr> 
   <th>欄位</th> 
   <th>標準/自訂</th> 
   <th>讀取</th> 
   <th>寫入</th> 
  </tr> 
  <tr> 
   <td>ID</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDeleted</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>FirstRespondedDate</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>HasResponsed</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>連絡人ID</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>銷售機會ID</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsConverted</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CampaignId</td> 
   <td>標準</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>bizible2__Bizible_Touchpoint_Date__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Status_Date__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Status_Contact__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Status_Leade__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Status_Opportunity__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>為了確保Marketo Measure擷取Salesforce帳戶內刪除事件的精確性，以下物件需要可複製的許可權。 可復寫許可權與下列物件一起提供標準許可權：
>
>* 帳戶
>* Campaign
>* 促銷活動會員
>* 連絡人
>* 事件
>* 銷售機會
>* 機會
>* 任務


## [!DNL Marketo Measure] 中的自訂物件 [!DNL Salesforce] {#marketo-measure-custom-objects-in-salesforce}

除了在SFDC的標準物件上建立自訂欄位之外， [!DNL Marketo Measure] 安裝套裝軟體，會建立一些自訂物件。 以下是這些「自訂物件」的清單，以及代表以下欄位的表格： [!DNL Marketo Measure] 將寫入。

**購買者接觸點**

購買者接觸點是 [!DNL Marketo Measure] 自訂物件，封裝聯絡人、銷售機會和案例的行銷互動。

<table> 
 <tbody> 
  <tr> 
   <th>欄位</th> 
   <th>標準/自訂</th> 
   <th>讀取</th> 
   <th>寫入</th> 
  </tr> 
  <tr> 
   <td>bizible2__Bizible_Person__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__SF_Campaign__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__UniqueId__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Marketing_Channel__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Marketing_Channel_Path__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Type__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Id__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Content__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Group_Id__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Group_Name__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Campaign_Id__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Campaign_Name__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Placement_Id__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Placement_Name__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Site_Id__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Site_Name__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Form_URL__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Form_URL_Raw__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Platform__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Browser__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Geo_City__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Geo_Country__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Geo_Region__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Keyword_Id__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Keyword_MatchType__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Position__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Keyword_Text__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Landing_Page__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Landing_Page_Raw__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Medium__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Referrer_Page__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Referrer_Page_Raw__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Search_Phrase__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Date__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Source__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Segment__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Count_First_Touch__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Count_Lead_Creation_Touch__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Count_U_Form__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Destination_URL__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Case__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Contact__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
 </tbody> 
</table>

**[!DNL Marketo Measure]個人**

此 [!DNL Marketo Measure] 個人是 [!DNL Marketo Measure] 與Lead、Contact和Case物件都相關的自訂物件。

<table> 
 <tbody> 
  <tr> 
   <th>欄位</th> 
   <th>標準/自訂</th> 
   <th>讀取</th> 
   <th>寫入</th> 
  </tr> 
  <tr> 
   <td>bizible2__UniqueId__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Lead__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Case__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Contact__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x </td> 
  </tr> 
 </tbody> 
</table>

## 購買者歸因接觸點 {#buyer-attribution-touchpoint}

購買者歸因接觸點為 [!DNL Marketo Measure] 自訂物件，可封裝行銷對機會的影響。

**購買者歸因接觸點**

<table> 
 <tbody> 
  <tr> 
   <th>欄位</th> 
   <th>標準/自訂</th> 
   <th>讀取</th> 
   <th>寫入</th> 
  </tr> 
  <tr> 
   <td>bizible2__Account__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__SF_Campaign__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Contact__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Opportunity__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__UniqueId__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Marketing_Channel__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Marketing_Channel_Path__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Type__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Id__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Content__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Group_Id__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Group_Name__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Campaign_Id__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Campaign_Name__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Placement_Id__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Placement_Name__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Site_Id__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Site_Name__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Form_URL__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Form_URL_Raw__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Platform__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Browser__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Geo_City__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Geo_Country__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Geo_Region__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Keyword_Id__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Keyword_MatchType__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Position__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Keyword_Text__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Landing_Page__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Landing_Page_Raw__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Medium__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Referrer_Page__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Referrer_Page_Raw__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Search_Phrase__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Date__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Source__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Segment__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Attribution_First_Touch__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Attribution_Lead_Conversion_Touch__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Attribution_U_Form__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Attribution_W_Form__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Attribution_Custom_Model__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Attribution_Custom_Model_2__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Count_First_Touch__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Count_Lead_Creation_Touch__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Count_U_Form__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Count_W_Form__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Count_Custom_Model__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Count_Custom_Model_2__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Destination_URL__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Revenue_First_Touch__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Revenue_Lead_Creation_Touch__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Revenue_U_Form__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Revenue_W_Form__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Revenue_Custom_Model__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Revenue_Custom_Model_2__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
 </tbody> 
</table>
