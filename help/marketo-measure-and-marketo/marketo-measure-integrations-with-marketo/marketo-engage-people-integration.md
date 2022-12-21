---
unique-page-id: 37356395
description: '"[!DNL Marketo Engage] 人員整合 —  [!DNL Marketo Measure]  — 產品檔案」'
title: '"[!DNL Marketo Engage] 人員整合」'
exl-id: 51930e84-4ff8-4e35-9d44-ea017c24b051
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 0%

---

# [!DNL Marketo Engage] 人員整合 {#marketo-engage-people-integration}

Marketo People整合可讓 [!DNL Marketo Measure] 開始從Marketo下載人員，並開始將其追蹤的工作階段系結至個人，並將接觸點對應至其參與。 過去， [!DNL Marketo Measure] 只能將接觸點對應至CRM中的人員，因此這可協助行銷人員更快衡量其行銷工作，而非等待階段或觸發將其同步至CRM。

## 需求 {#requirements}

* 生產Marketo例項
* 生產 [!DNL Salesforce] 或 [!DNL Microsoft Dynamics] 執行個體
* 任何已付 [!DNL Marketo Measure] 訂閱
* 已啟用SOLR(請聯繫 [Marketo支援](https://nation.marketo.com/t5/Support/ct-p/Support) 啟用)

## 運作方式 {#how-it-works}

作為現有客戶， [!DNL Marketo Measure] 已從您的CRM下載人員。 標準流程是 [!DNL Marketo Measure] 下載人員，並將電子郵件地址對應至我們透過bizible.js追蹤的網路工作階段。

隨著Marketo人員下載的推出， [!DNL Marketo Measure] 現在可將網頁工作階段對應至較大的個人群，這些人員尚未與CRM同步。 我們通常會看到這個情況，因為內部程式會等到人們達到特定狀態，再推送至CRM。

當 [!DNL Marketo Measure] 成功將Marketo人員對應至網路工作階段，我們的處理程式將產生任何相關的接觸點，這些最終可在 [!DNL Marketo Measure Discover]. 如果Marketo人員被推送至CRM, [!DNL Marketo Measure] 會處理重複案例，並為CRM人員重新建立接觸點，並將初始集標示為「重複」。

為了讓我們偵測到這些重複項目，請確定您的 [!DNL Marketo-Salesforce] 或 [!DNL Marketo-Dynamics] 同步會填入Marketo人員的銷售機會和聯絡人ID。 如果ID正確同步，您應該可以在人員記錄上看到CRM ID，如下所示：

![](assets/5a.png)

![](assets/5b.png)

客戶可以選擇報告內的完整Marketo人員和CRM人員集 [!DNL Marketo Measure] 探索。 如果您只想報告CRM人員，建議您建立區段來篩選他們。

## [!DNL Marketo Measure Discover] {#marketo-measure-discover}

在 [!DNL Marketo Measure Discover]，您會看到Marketo和CRM銷售機會的總數。 若要僅報告Marketo人員或CRM銷售機會，您將要為來源建立區段類別，然後使用「來源系統」欄位為Marketo和CRM建立區段規則，以定義規則。 建立區段後，您會看到可用來篩選所有區段的來源類別 [!DNL Marketo Measure Discover] 控制面板。

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
   <td><p>修改日期</p></td> 
   <td><p>updatedAt<strong>*</strong></p></td> 
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
   <td><p>WEB_SITE</p></td> 
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
   <td><p>帳戶Id(L2A)</p></td> 
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

*有已知行為問題，Marketo公司實體中的欄位不會影響人員的updatedAt值，因此，如果網站或公司等相關欄位已更新， [!DNL Marketo Measure] 不會知道已修改這些值，因為updatedAt日期/時間值未更新。 這會影響ABM功能，因為我們沒有新的資料來解決銷售機會帳戶。 目前沒有解決辦法，但有計畫在未來解決這個問題。

## 常見問題集 {#faq}

**我的銷售機會計數為何在CRM和 [!DNL Marketo Measure Discover]?**

由於此整合可讓我們為已直接從Marketo匯入的銷售機會建立接觸點，因此可能有未同步至CRM的銷售機會，因此Discover中的計數可能會高於CRM，因為接觸點只會推送至CRM銷售機會。

**這會如何取代我的資料？**

此整合實際上會合併您目前的資料集 [!DNL Marketo Measure] 例項，因此不會取代任何內容。 從您目前的CRM Lead中，我們可以期待的是，當我們下載價值2年的Marketo Lead時，我們只需更新該Lead記錄，以顯示還有與Marketo Lead相符的項目。 所有發生在後端與接觸點的項目都預期會維持不變。 我們也預計會看到更多接觸點，因為符合資格的Marketo Lead。 如果我們能夠找到與Marketo人員相符的網路工作階段，就會開始看到計入的接觸點 [!DNL Marketo Measure].

**我只能從Marketo下載我的人員並切斷CRM連線嗎？**

此時此刻，否。 未來我們會有這個選擇，但我們需要構建這個Marketo整合的其他階段，以便我們能夠將從Marketo到 [!DNL Marketo Measure].

**你匯入我所有的Marketo人嗎？**

目前，我們最早會匯入1/1/2018人，這樣我們便至少擁有2年的資料，與我們透過CRM下載強制執行的相同行為。 建立Marketo連線後，我們將實作改良行為以下載滾動的2年期間。

我們也不會篩選任何人員類型，因此兩年期間內的所有人員都會被匯入，且符合接觸點資格。

**什麼是SOLR？為什麼我需要啟用它才能使用此功能？**

為Marketo執行個體啟用SOLR是開啟Marketo中硬體空間的瑣碎步驟，讓您的訂閱可運用 [!DNL Marketo Measure] 整合。 若未啟用SOLR，我們將無法存取某些呼叫，否則這些呼叫將允許我們從您的Marketo執行個體下載適當的人員。
