---
unique-page-id: 35586105
description: 參與路徑 —  [!DNL Marketo Measure]
title: 參與路徑
exl-id: 104d803f-9f40-4ab6-872d-6432f8c087e9
feature: Reporting
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 0%

---

# 參與路徑 {#engagement-path}

「參與路徑」可讓您檢視銷售機會、連絡人、客戶及商機從首次接觸一直到結束的完整參與檢視。

![](assets/one-2.png)

## 圖磚說明 {#tile-description}

**事件型別：** 接觸點的型別（工作階段、CRM促銷活動、CRM事件、CRM任務、曝光數）

**購買者接觸點位置：** 潛在客戶/連絡人的接觸點位置

**購買者歸因接觸點位置：** 機會的購買者歸因接觸點位置

**接觸點日期：** 線上來源：參與發生的日期和時間。 離線事件：在Salesforce促銷活動中設定的日期和時間。 對於活動接觸點：在活動設定中參考的接觸點日期欄位

**電子郵件：** 與參與相關聯的電子郵件

**行銷接觸型別：** 參與型別（網頁瀏覽、網頁表單、網頁聊天、CRM、活動型別）

**頻道：** 帶動參與的行銷管道

**中：** 參與媒介

* 如果參與來自API連線平台(Adwords/BingAds)媒體，則是CPC
* 如果參與專案的登陸頁面包含utm_medium，我們會進行剖析
* 如果參與來自CRM行銷活動，則媒體來自CRM行銷活動的「型別」欄位

**網頁來源：** 此欄會顯示參與的來源

* 如果參與來自API連線的平台，網站來源會顯示廣告平台的名稱
* 如果接觸點來自自然搜尋，此欄位將顯示搜尋引擎的名稱
* 如果不#1或#2，且utm_source值存在於接觸點的登陸頁面URL中，則會在此處顯示該值
* 如果不#1或#2，而且沒有utm_source值，則反向連結URL的根網域將顯示在這裡。
* 如果以上都不顯示，這將會顯示Web Direct或Web

**與個人的第一次互動：** 如果接觸點是個人第一次互動，此欄會顯示「是」或「否」

**已歸因的收入：** 此欄會根據所選的歸因模型，顯示歸因於該接觸點的收入

## 篩選器說明 {#filter-description}

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th>篩選器名稱</th> 
   <th>說明</th> 
  </tr> 
  <tr> 
   <td><p>帳戶名稱/ID</p></td> 
   <td><p>透過右側的加號「+」新增篩選器，允許使用多個值。 多個篩選器值將具有「或」關係，這表示圖磚將顯示兩個篩選器值的結果。 如果任何篩選值無效，控制面板將不會產生無效值的結果，但仍會篩選為有效的篩選值。 不區分大小寫。</p></td> 
  </tr> 
  <tr> 
   <td><p>機會名稱/ID</p></td> 
   <td><p>透過右側的加號「+」新增篩選器，允許使用多個值。 多個篩選器值將具有「或」關係，這表示圖磚將顯示兩個篩選器值的結果。 如果任何篩選值無效，控制面板將不會產生無效值的結果，但仍會篩選為有效的篩選值。 不區分大小寫。</p></td> 
  </tr> 
  <tr> 
   <td><p>潛在客戶ID/電子郵件</p></td> 
   <td><p>透過右側的加號「+」新增篩選器，允許使用多個值。 多個篩選器值將具有「或」關係，這表示圖磚將顯示兩個篩選器值的結果。 如果任何篩選值無效，控制面板將不會產生無效值的結果，但仍會篩選為有效的篩選值。 不區分大小寫。</p></td> 
  </tr> 
  <tr> 
   <td><p>連絡人ID/電子郵件</p></td> 
   <td><p>透過右側的加號「+」新增篩選器，允許使用多個值。 多個篩選器值將具有「或」關係，這表示圖磚將顯示兩個篩選器值的結果。 如果任何篩選值無效，控制面板將不會產生無效值的結果，但仍會篩選為有效的篩選值。 不區分大小寫。</p><p>帳戶名稱/ID、銷售機會ID/電子郵件、聯絡人ID/電子郵件篩選是「或」關係，這表示如果銷售機會篩選和聯絡人篩選都有值，則會顯示其中一個ID的所有記錄。</p></td> 
  </tr> 
  <tr> 
   <td><p>歸因模型</p></td> 
   <td><p>指定計算已歸因收入的模式。 允許的值：「完整路徑歸因」、「首次接觸歸因」、「自訂模型歸因」、「潛在客戶建立歸因」、「U形歸因」、「W形歸因」。</p></td> 
  </tr> 
  <tr> 
   <td><p>事件型別</p></td> 
   <td><p>依使用者接觸點所依據的事件型別篩選歷程。 透過右側的加號「+」新增篩選器，允許使用多個值。 允許的值： 「Session」、「CRM Campaign」、「CRM Event」、「CRM Task」、「Impression」。</p></td> 
  </tr> 
  <tr> 
   <td><p>潛在客戶階段</p></td> 
   <td><p>依使用者接觸點所根據的潛在客戶階段篩選歷程。 透過右側的加號「+」新增篩選器，允許使用多個值。 篩選器預設為「等於」將顯示可選擇的建議，但建議使用「包含」作為階段上多個篩選器的篩選條件。</p></td> 
  </tr> 
  <tr> 
   <td><p>機會階段</p></td> 
   <td><p>依使用者接觸點所依據的機會階段篩選歷程。 透過右側的加號「+」新增篩選器，允許使用多個值。 篩選器預設為「等於」將顯示可選擇的建議，但建議使用「包含」作為階段上多個篩選器的篩選條件。</p></td> 
  </tr> 
  <tr> 
   <td><p>接觸點日期</p></td> 
   <td><p>依接觸點日期/時間篩選歷程。</p></td> 
  </tr> 
  <tr> 
   <td><p>使用者接觸點電子郵件</p></td> 
   <td><p>在使用者接觸點上依電子郵件篩選歷程。 這允許篩選與銷售機會/聯絡人/帳戶無關的電子郵件。</p></td> 
  </tr> 
  <tr> 
   <td><p>行銷接觸型別</p></td> 
   <td><p>依行銷接觸型別篩選歷程。</p></td> 
  </tr> 
  <tr> 
   <td><p>管道</p></td> 
   <td><p>依管道篩選歷程。</p></td> 
  </tr> 
  <tr> 
   <td><p>中</p></td> 
   <td><p>依媒體篩選歷程。</p></td> 
  </tr> 
  <tr> 
   <td><p>Web來源</p></td> 
   <td><p>依網站來源篩選歷程。</p></td> 
  </tr> 
  <tr> 
   <td><p>與個人的首次互動</p></td> 
   <td><p>使用者接觸點表格上的「是首次接觸」欄篩選歷程。</p></td> 
  </tr> 
  <tr> 
   <td><p>已歸因的收入</p></td> 
   <td><p>依已歸因的收入值篩選歷程。</p></td> 
  </tr> 
 </tbody> 
</table>
