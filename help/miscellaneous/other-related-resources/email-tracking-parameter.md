---
unique-page-id: 37356030
description: 電子郵件追蹤引數 —  [!DNL Marketo Measure]
title: 電子郵件追蹤引數
exl-id: e2cfd59e-ce4a-4cbb-b64a-828d1db7410f
feature: Tracking
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 2%

---

# 電子郵件追蹤引數 {#email-tracking-parameter}

[!DNL Marketo Measure]電子郵件追蹤引數可讓行銷人員將電子郵件點按視為表單提交，以便針對這些動作產生接觸點。 若不使用電子郵件追蹤引數，來自電子郵件的點進次數僅會視為「網頁造訪」，直到使用者透過表單提交或網頁聊天實際參與網站為止。

## 使用案例  {#use-cases}

**網路研討會報名**：行銷團隊會傳送一封電子郵件邀請函，其中含有單一按鈕以報名網路研討會。 由於電子郵件已含有個人的資訊，因此按一下滑鼠即可自動註冊。 登入頁面包含電子郵件追蹤引數，因此當使用者點進並登陸確認頁面時，[!DNL Marketo Measure]可以擷取電子郵件地址，並將點進視為表單填入，這會產生接觸點。

**內容下載**：內容行銷團隊想要推廣他們最近使用電子郵件中的直接下載連結所發佈的電子書。 建立電子郵件範本時，下載確認頁面會包含電子郵件追蹤引數，這樣當使用者點進時，[!DNL Marketo Measure]就可以擷取電子郵件地址。 不需要在網站上填寫表單，[!DNL Marketo Measure]便可以產生內容下載的接觸點。 這是因為電子郵件使用電子郵件追蹤引數將其抵達確認頁面。

## 運作方式 {#how-it-works}

當訪客進入您的網站時，[!DNL Marketo Measure]會預期找到具有電子郵件地址或[!DNL Salesforce] ID的登陸頁面，以便我們將該瀏覽與「表單提交」建立關聯，並產生該活動的接觸點。

身為客戶，您可以如常建置電子郵件範本。 一旦到了新增至您要追蹤之動作的登入頁面時，您必須決定權杖、變數標籤或巨集，您的行銷自動化平台可以接受以動態方式顯示每個人的值。

Marketo Measure接受下列值：電子郵件地址、Salesforce銷售機會Id或Salesforce聯絡人Id。

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
   <th><p>Token /標籤/巨集 </p></th> 
   <th><p>範例</p></th> 
   <th><p>支援材料</p></th> 
  </tr> 
  <tr> 
   <td><p>Marketo</p></td> 
   <td><p>{{lead.Email Address}} </p></td> 
   <td><p>https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId={{lead.EmailAddress}}</p></td> 
   <td><p>https://experienceleague.adobe.com/docs/marketo/using/product-docs/demand-generation/landing-pages/personalizing-landing-pages/tokens-overview.html?lang=zh-Hant</p></td> 
  </tr> 
  <tr> 
   <td><p>Pardot</p></td> 
   <td><p>%%email%% </p><p>或</p><p>%%user_crm_id%%</p></td> 
   <td><p>https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId=%%email%%</p></td> 
   <td><p>https://help.salesforce.com/s/articleView?language=en_US&id=pardot_variable_tags_reference.htm&type=5</p></td> 
  </tr> 
  <tr> 
   <td><p>Hubspot</p></td> 
   <td><p>（透過編輯器插入）</p></td> 
   <td><p>不適用</p></td> 
   <td><p>https://knowledge.hubspot.com/website-pages/personalize-your-content</p></td> 
  </tr> 
  <tr> 
   <td><p>動作</p></td> 
   <td><p>（透過訊息撰寫器插入）</p></td> 
   <td><p>不適用</p></td> 
   <td><p>https://connect.act-on.com/hc/en-us/articles/360033436074-How-to-Personalize-Email-Content-with-CRM-Data</p></td> 
  </tr> 
 </tbody> 
</table>

最後，在[!DNL Marketo Measure]內，您必須指定追蹤引數，讓[!DNL Marketo Measure]可以找到電子郵件或ID值。 預設值為「mailId」，如上面的範例和下面的熒幕擷圖所示。 在[!DNL Marketo Measure]的設定中輸入值，然後按一下&#x200B;**[!UICONTROL Save]**。

![](assets/one.png)
