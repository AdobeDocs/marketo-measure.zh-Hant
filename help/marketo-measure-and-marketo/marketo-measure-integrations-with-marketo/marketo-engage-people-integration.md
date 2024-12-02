---
unique-page-id: 37356395
description: '[!DNL Marketo Engage]人員整合 —  [!DNL Marketo Measure]'
title: '[!DNL Marketo Engage]人員整合'
exl-id: 51930e84-4ff8-4e35-9d44-ea017c24b051
feature: Integration
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 1%

---

# [!DNL Marketo Engage]人員整合 {#marketo-engage-people-integration}

Marketo人員整合可讓[!DNL Marketo Measure]開始從Marketo下載人員，並開始將其追蹤的工作階段連結至個人，並將接觸點對應至其參與。 在過去，[!DNL Marketo Measure]只能將接觸點對應至CRM中的人員，因此這有助於行銷人員更早衡量其行銷成效，而非等待階段或觸發器將其同步至CRM。

## 需求 {#requirements}

* 生產Marketo執行個體
* 生產[!DNL Salesforce]或[!DNL Microsoft Dynamics]執行個體
* 任何付費的[!DNL Marketo Measure]訂閱
* SOLR已啟用(請聯絡[Marketo支援](https://nation.marketo.com/t5/Support/ct-p/Support)以啟用此功能)

## 運作方式 {#how-it-works}

[!DNL Marketo Measure]目前已經從您的CRM下載人員。 標準程式是[!DNL Marketo Measure]下載人員，並將電子郵件地址對應到我們透過bizible.js追蹤的網頁工作階段。

由於開始下載Marketo人員，[!DNL Marketo Measure]現在可以將網頁工作階段對應到更大的個人集區，也就是尚未與CRM同步處理的個人集區。 我們之所以會看到此問題，是因為內部程式會等到使用者達到特定狀態後，才會推送至CRM。

當[!DNL Marketo Measure]成功將Marketo人員對應到網頁工作階段時，我們的處理將會為其產生任何相關的接觸點，這些最終可在[!DNL Marketo Measure Discover]中報告。 如果該Marketo人員被推送到CRM，[!DNL Marketo Measure]將處理重複案例，我們將會為CRM人員重新建立接觸點，並將初始設定標籤為「重複」。

為了讓我們偵測這些重複專案，請確定您的[!DNL Marketo-Salesforce]或[!DNL Marketo-Dynamics]同步處理正在填入Marketo人員上的銷售機會和連絡人ID。 如果ID正確同步，您應該可以在人員記錄上看到CRM ID，如下所示：

![](assets/5a.png)

![](assets/5b.png)

客戶可選擇報告[!DNL Marketo Measure] Discover中的整組Marketo人員和CRM人員。 如果您只想針對CRM人員製作報表，建議您建立區段來篩選他們。

## [!DNL Marketo Measure Discover] {#marketo-measure-discover}

在[!DNL Marketo Measure Discover]中報告銷售機會（人員）時，您將會看到Marketo和CRM銷售機會的總數。 為了僅報告Marketo人員或CRM銷售機會，您將想要為來源建立區段類別，然後使用「Source系統」欄位來定義規則，以建立Marketo和CRM的區段規則。 建立區段後，您會看到Source類別可用於篩選[!DNL Marketo Measure Discover]儀表板。

![](assets/bizible-discover-1.png)

![](assets/bizible-discover-2.png)

## 欄位對應 {#field-mappings}

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><p><strong>biz_leads</strong></p></th> 
   <th><p><strong>Marketo</strong></p></th> 
  </tr> 
  <tr> 
   <td><p>ID</p></td> 
   <td><p>ID</p></td> 
  </tr> 
  <tr> 
   <td><p>MODIFIED_DATE</p></td> 
   <td><p>更新於<strong>*</strong></p></td> 
  </tr> 
  <tr> 
   <td><p>CREATED_DATE</p></td> 
   <td><p>createdAt</p></td> 
  </tr> 
  <tr> 
   <td><p>電子郵件</p></td> 
   <td><p>電子郵件</p></td> 
  </tr> 
  <tr> 
   <td><p>WEBSITE</p></td> 
   <td><p>網站</p></td> 
  </tr> 
  <tr> 
   <td><p>公司</p></td> 
   <td><p>公司</p></td> 
  </tr> 
  <tr> 
   <td><p>IS_CONVERTED</p></td> 
   <td><p>不適用</p></td> 
  </tr> 
  <tr> 
   <td><p>ACCOUNT_ID</p></td> 
   <td><p>帳戶Id (L2A)</p></td> 
  </tr> 
  <tr> 
   <td><p>BIZIBLE_STAGE</p></td> 
   <td><p>狀態</p></td> 
  </tr> 
  <tr> 
   <td><p>IS_DELETED</p></td> 
   <td><p>true/false</p></td> 
  </tr> 
 </tbody> 
</table>

*在已知行為問題中，Marketo公司實體的欄位不會影響人員的updatedAt值，因此，如果更新網站或公司等相關欄位，[!DNL Marketo Measure]將無法得知這些值已修改，因為updatedAt日期/時間值未更新。 這會影響ABM功能，我們不會有新的資料來解決潛在客戶的帳戶。 目前沒有解決方法，但計畫未來解決此問題。

## 常見問題集 {#faq}

**為什麼我的CRM與[!DNL Marketo Measure Discover]的潛在客戶計數不同？**

由於此整合可讓我們為已從Marketo直接匯入的銷售機會建立接觸點，因此可能會有銷售機會未同步至CRM，因此Discover中的計數可能會高於CRM，因為僅針對CRM銷售機會推送接觸點。

**這如何取代我的資料？**

此整合實際上會將資料集合併到您目前的[!DNL Marketo Measure]執行個體中，因此不會取代任何專案。 我們希望從您目前的CRM Leads瞭解到，當我們下載2年的Marketo Leads時，只需更新該Lead記錄，即可顯示也有一個Marketo Lead相符。 所有這些都會在後端發生，且接觸點預計會維持不變。 我們也會因為合格的Marketo銷售機會而看到更多接觸點。 如果能夠找到與這些Marketo人員相符的網頁工作階段，我們會開始看到[!DNL Marketo Measure]中計數的接觸點。

**我只能從Marketo下載人員並切斷CRM連線嗎？**

目前不適用。 我們日後會提供此選項，但我們需要建置此Marketo整合的其他階段，以便將Marketo中的方案、商機和交易連結到[!DNL Marketo Measure]。

**您是否要匯入我所有的Marketo人員？**

目前，我們最早會從2018年1月1日匯入人員，因此我們至少有2年的資料，這和我們從CRM下載強制執行的行為相同。 建立Marketo連線後，我們將實施改善的行為，以下載滾動的2年時段。

我們也不會篩選任何人員型別，因此兩年期間內的所有人員都會被匯入，並符合接觸點的資格。

**什麼是SOLR？為何需要啟用它才能使用此功能？**

為您的Marketo執行個體啟用SOLR是開啟Marketo中硬體空間的簡單步驟，因此您的訂閱可以利用[!DNL Marketo Measure]整合。 若未啟用SOLR，我們將無法存取某些呼叫，這些呼叫原本可讓我們從您的Marketo執行個體下載合適的人員。
