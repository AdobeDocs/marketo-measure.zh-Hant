---
unique-page-id: 37356030
description: 電子郵件追蹤參數 —  [!DNL Marketo Measure]  — 產品檔案
title: 電子郵件追蹤參數
exl-id: e2cfd59e-ce4a-4cbb-b64a-828d1db7410f
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 1%

---

# 電子郵件追蹤參數 {#email-tracking-parameter}

此 [!DNL Marketo Measure] 電子郵件追蹤參數可讓行銷人員將電子郵件點按視為表單提交，以便為這些動作產生接觸點。 若不使用電子郵件追蹤參數，在使用者透過表單提交或網路聊天實際參與網站之前，來自電子郵件的點進只會被視為「網路造訪」。

## 使用案例  {#use-cases}

**網路研討會註冊**:行銷團隊會傳送電子郵件邀請函，並附上單一按鈕，以報名參加網路研討會。 由於電子郵件已包含人員的資訊，因此只要按一下，就會自動註冊。 登錄頁面包含電子郵件追蹤參數，因此當使用者點進並登陸確認頁面時， [!DNL Marketo Measure] 可擷取電子郵件地址，並將點進視為表單填入，進而產生接觸點。

**內容下載**:內容行銷團隊想要促銷他們最近發佈的電子書，其中包含來自電子郵件的直接下載連結。 建置電子郵件範本時，下載確認頁面會包含電子郵件追蹤參數，以便使用者點進 [!DNL Marketo Measure] 可擷取電子郵件地址。 無需在網站上填寫表格， [!DNL Marketo Measure] 可為透過電子郵件發生的內容下載產生接觸點，因為透過電子郵件追蹤參數，內容下載至確認頁面。

## 運作方式 {#how-it-works}

當訪客進入您的網站時， [!DNL Marketo Measure] 預期會找到包含電子郵件地址或 [!DNL Salesforce] ID，以便讓該次造訪與「表單提交」建立關聯，並為該活動產生接觸點。

身為客戶，您會像平常一樣建立電子郵件範本。 一旦需要針對您要追蹤的動作將新增至登錄頁面，您就需要決定Token、變數標籤，或您的行銷自動化平台接受的巨集，以動態顯示每個個人的值。

Marketo Measure接受下列值：電子郵件地址、Salesforce銷售機會Id或Salesforce聯繫人Id。

## 標籤範例 {#tag-examples}

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><p>行銷自動化</p></th> 
   <th><p>代號/標籤/巨集 </p></th> 
   <th><p>範例</p></th> 
   <th><p>支撐材料</p></th> 
  </tr> 
  <tr> 
   <td><p>Marketo</p></td> 
   <td><p>{{lead.電子郵件地址}} </p></td> 
   <td><p>https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId={{lead.EmailAddress}}</p></td> 
   <td><p>https://docs.marketo.com/display/public/DOCS/Tokens+Overview#TokensOverview-PersonTokens</p></td> 
  </tr> 
  <tr> 
   <td><p>帕爾多</p></td> 
   <td><p>%%電子郵件%% </p><p>或</p><p>%%user_crm_id%</p></td> 
   <td><p>https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId=%%email%%</p></td> 
   <td><p>https://help.salesforce.com/articleView?id=pardot_variable_tags_reference.htm&amp;type=5</p></td> 
  </tr> 
  <tr> 
   <td><p>輪轂點</p></td> 
   <td><p>（透過編輯器插入）</p></td> 
   <td><p>不適用</p></td> 
   <td><p>https://knowledge.hubspot.com/cos-general/how-to-use-personalization-with-your-content</p></td> 
  </tr> 
  <tr> 
   <td><p>Act-On</p></td> 
   <td><p>（透過訊息撰寫器插入）</p></td> 
   <td><p>不適用</p></td> 
   <td><p>https://connect.act-on.com/hc/en-us/articles/360033436074-How-to-Personalize-Email-Content-with-CRM-Data</p></td> 
  </tr> 
 </tbody> 
</table>

最後，在 [!DNL Marketo Measure]，您必須指定追蹤參數，才能 [!DNL Marketo Measure] 可以找到電子郵件或Id值。 預設值為「mailId」，如上方範例和下方螢幕擷取所示。 在的「設定」中輸入值 [!DNL Marketo Measure]，然後按一下 **[!UICONTROL Save]**.

![](assets/one.png)
