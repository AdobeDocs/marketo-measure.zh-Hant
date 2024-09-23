---
unique-page-id: 18874672
description: ' [!DNL Marketo Measure] 與 [!DNL Salesforce] 如何互動 — Marketo Measure — 產品檔案'
title: ' [!DNL Marketo Measure] 和 [!DNL Salesforce] 如何互動'
exl-id: c2f9d7ce-c5b8-4664-8f92-cb54255190cd
feature: Salesforce
source-git-commit: dec80278958e51c1f0449173d45fe74425fb047e
workflow-type: tm+mt
source-wordcount: '1314'
ht-degree: 18%

---

# [!DNL Marketo Measure]和[!DNL Salesforce]如何互動 {#how-marketo-measure-and-salesforce-interact}

>[!NOTE]
>
>您可能會在檔案中看到指定&quot;[!DNL Marketo Measure]&quot;的說明，但在您的CRM中仍會看到&quot;Bizible&quot;。 我們正致力於更新此專案，品牌重塑將很快反映在您的CRM中。

讓我們來深入瞭解[!DNL Marketo Measure]與Salesforce之間的關係。

## Salesforce和[!DNL Marketo Measure] {#salesforce-and-marketo-measure}

建立[!DNL Marketo Measure]帳戶並連線[!DNL Salesforce]後，只要已安裝[!DNL Marketo Measure]受管理的套件且[!DNL Marketo Measure] Salesforce使用者擁有編輯許可權，[!DNL Marketo Measure]就會開始將行銷資料推送至CRM執行個體。

如果您未安裝[!DNL Marketo Measure] Salesforce套件，[!DNL Marketo Measure]將不會將任何資料寫入您的Salesforce執行個體。

![](assets/1-3.png)

依預設，每次工作將資料傳送至您的CRM時，[!DNL Marketo Measure]會針對每個API點數匯出200筆記錄。 對於大多數客戶而言，這會在[!DNL Marketo Measure]所消耗的API點數與CRM上的CPU資源需求之間提供最佳平衡。 不過，對於具有複雜CRM設定（例如工作流程和觸發器）的客戶，較小的批次大小可能有助於改善CRM效能。 為此，[!DNL Marketo Measure]允許客戶設定CRM匯出批次大小。 此設定可在[!DNL Marketo Measure] Web應用程式的[!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL General]頁面上使用，客戶可以選擇批次大小200 （預設）、100、50或25。

![](assets/how-bizible-and-salesforce-interact-2.png)

修改此設定時，請記住，較小的批次大小會消耗您CRM的更多API積分。 建議您只有在CRM中遇到CPU逾時或CPU負載過高時才減少批次大小。

## Salesforce已連線使用者許可權 {#salesforce-connected-user-permissions}

**專用使用者的Marketo Measure管理員許可權集**：允許SFDC管理員對Marketo Measure物件執行CRUD作業。

**檢視和編輯轉換的潛在客戶許可權集**：這可讓Marketo Measure在潛在客戶轉換為聯絡人後加以裝飾。

**Salesforce行銷使用者核取方塊**：可讓使用者建立行銷活動，並使用行銷活動匯入精靈。

* 我們需要CRM中Campaign的「建立」和「更新」額外許可權。

* 從網路活動建立接觸點時，我們需要將其連結至促銷活動。 由於網站活動沒有對應的CRM行銷活動，因此我們需要建立一個行銷活動以建立此連結。 這同時適用於銷售機會和銷售機會接觸點。 需要更新許可權，因為我們使用的呼叫是「upsert」 — 如果記錄存在，我們會更新記錄；如果沒有，我們會建立記錄。 這僅適用於我們建立的行銷活動。

**Marketo Measure Standard使用者**：讓使用者能夠從Marketo Measure物件讀取記錄。

## Salesforce標準物件與存取 {#salesforce-standard-objects-and-access}

這會列出[!DNL Marketo Measure]互動的[!DNL Salesforce]標準物件，以及在建立連線並安裝[!DNL Marketo Measure]套件後新增到這些物件的自訂欄位。 [!DNL Marketo Measure]不會立即寫入任何標準[!DNL Salesforce]物件欄位。

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
 </tbody> 
</table>

**個案例**

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
   <td>StageName</td> 
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
  <tr> 
   <td>名稱</td> 
   <td>標準</td> 
   <td>x</td> 
   <td>x</td> 
  </tr>
  <tr> 
   <td>bizible2__UniqueId__c</td> 
   <td>自訂</td> 
   <td>x</td> 
   <td>x</td> 
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
>為了確保Marketo Measure擷取您Salesforce帳戶內刪除事件的精確性，以下物件需要可複製的許可權。 可復寫許可權與下列物件一起提供標準許可權：
>
>* 帳戶
>* Campaign
>* 促銷活動會員
>* 連絡人
>* 活動
>* 銷售機會
>* 機會
>* 任務


## [!DNL Salesforce]中的[!DNL Marketo Measure]個自訂物件 {#marketo-measure-custom-objects-in-salesforce}

除了在SFDC的標準物件上建立自訂欄位之外，在安裝[!DNL Marketo Measure]套件之後，它會建立一些自訂物件。 以下是這些「自訂物件」的清單，以及表示[!DNL Marketo Measure]將寫入其中的欄位的表格。

**Buyer Touchpoint**

Buyer Touchpoint是[!DNL Marketo Measure]自訂物件，可封裝聯絡人、銷售機會和案例的行銷互動。

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

**[!DNL Marketo Measure]人員**

[!DNL Marketo Measure]個人是[!DNL Marketo Measure]自訂物件，與銷售機會、連絡人和案例物件都有關。

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

## Buyer Attribution Touchpoint {#buyer-attribution-touchpoint}

Buyer Attribution Touchpoint是[!DNL Marketo Measure]自訂物件，可封裝行銷對機會的影響。

**Buyer Attribution Touchpoint**

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

>[!MORELIKETHIS]
>
>[整合許可權總覽](/help/api-connections/utilizing-marketo-measures-api-connections/integration-permissions-overview.md){target="_blank"}
