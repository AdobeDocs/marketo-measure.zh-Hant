---
description: BT與BAT之間的接觸點位置和產生方式說明 —  [!DNL Marketo Measure]
title: BT和 [!DNL BATs]的接觸點位置和產生方式說明
exl-id: 4903f917-a366-4767-a126-5216d2377399
feature: Touchpoints
source-git-commit: cd5597a681f388a5b5c743dadd38bf3127811bff
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 0%

---

# BT和[!DNL BATs]的接觸點位置和產生方式說明 {#explanation-of-touchpoint-positions-and-generation-across-bts-and-bats}

**產生接觸點位置並流經購買者歷程**

瞭解Buyer Touchpoint位置及其觸發方式對於成功使用[!DNL Marketo Measure]資料報告至關重要。 您想要清楚瞭解潛在客戶在購買者歷程中的行為，進而瞭解在接觸點資料中會是什麼樣子。 如需此主題的詳細內容，建議您檢閱[[!UICONTROL Touchpoint Generation & Mapping]](/help/configuration-and-setup/getting-started-with-marketo-measure/touchpoint-generation-and-mapping.md)文章。

[!DNL Marketo Measure]具有由購買者歷程中的不同步驟觸發的各種接觸點位置。 針對[!DNL Marketo Measure]資料製作報表時，會有兩組接觸點資料：「購買者接觸點(BT)」和「購買者歸因接觸點(BAT)」。 您可能會注意到這些資料集在與不同物件相關的位置稍有不同。 如需此主題的詳細內容，建議您檢閱[購買者接觸點(BT)與購買者歸因接觸點(BAT)](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md)之間的差異。

**購買者接觸點(BT)**：這些是與個人及其歷程相關聯的接觸點，將是該個人專屬的。 下列現成可用的報表是以Buyer Touchpoint資料為基礎所建置。

* [!DNL Marketo Measure] 101：依ID的銷售機會
* [!DNL Marketo Measure] 101：依據管道的銷售機會
* [!DNL Marketo Measure] 101：銷售機會/聯絡人識別碼
* [!DNL Marketo Measure] 101：銷售機會/聯絡人（依管道）

以下概述Buyer Touchpoint位置，說明個人在其歷程中的位置，以及他們為獲得該位置所採取的行動。

<table> 
 <tbody>
  <tr>
   <th>Buyer Touchpoint (BT)位置</th> 
   <th>接觸點型別（可觸發接觸點的動作）</th> 
   <th>接觸點說明</th> 
  </tr>
  <tr>
   <td>首次接觸(FT)</td> 
   <td>網頁造訪</td> 
   <td>個人與您品牌的第一次行銷互動</td> 
  </tr>
  <tr>
   <td>銷售機會建立(LC)</td> 
   <td>表單填入<strong>或</strong>行銷活動/方案包含</td> 
   <td>第一個表單會填入個人擁有（通常是表單提交，但也可能是行銷活動/方案包含）</td> 
  </tr>
  <tr>
   <td>Post LC</td> 
   <td>表單填入<strong>或</strong>行銷活動/方案包含</td> 
   <td>個人在LC之後完成的任何形式（或後續的行銷活動/方案包含）</td> 
  </tr>
 </tbody>
</table>

**購買者歸因接觸點(BAT)**：這些是與商機及其歷程相關聯的接觸點。 這些接觸點與收入相關聯，因為它們與機會及其聯絡人相關聯。 下列現成可用的報表是以Buyer Attribution Touchpoint資料為基礎所建置。

* [!DNL Marketo Measure] 101：依據識別碼的機會
* [!DNL Marketo Measure] 101：依ID管道的商機

<table> 
 <tbody>
  <tr>
   <th>Buyer Attribution Touchpoint (BAT)位置</th> 
   <th>接觸點型別（可觸發接觸點的動作）</th> 
   <th>接觸點說明</th> 
  </tr>
  <tr>
   <td>首次接觸(FT)</td> 
   <td>網頁造訪</td> 
   <td>連絡人與您的品牌進行的首次行銷互動</td> 
  </tr>
  <tr>
   <td>銷售機會建立(LC)</td> 
   <td>表單填入<strong>或</strong>行銷活動/方案包含</td> 
   <td>聯絡人的第一個表單填寫（通常是表單提交，但也可能是行銷活動/方案包含）</td> 
  </tr>
  <tr>
   <td>機會建立</td> 
   <td>表單填寫<strong>或</strong>網頁造訪<strong>或</strong>行銷活動/方案包含</td> 
   <td>建立Opp時最接近的行銷互動</td> 
  </tr> 
  <tr>
   <td>已關閉的贏家/輸家</td> 
   <td>表單填寫<strong>或</strong>網頁造訪<strong>或</strong>行銷活動/方案包含</td> 
   <td>最接近Opp關閉時的行銷互動（成功或失敗）</td> 
  </tr>
  <tr>
   <td>中間接觸</td> 
   <td>表單填入<strong>或</strong>行銷活動/方案包含</td> 
   <td>當連絡人填寫線上表單時，表單未與里程碑接觸點一致</td> 
  </tr>
 </tbody>
</table>

[!DNL Marketo Measure]擁有這兩組接觸點資料，可以清楚瞭解個人的歷程和機會。 這兩個接觸點資料集為您提供從漏斗頂部到漏斗底部的清晰發生情況地圖。

下列範例說明資料從購買者接觸點(BT)流向購買者歸因接觸點(BAT)的流程。 在此範例中，人員A和人員B都是建立日期為2020年3月7日而結束日期為2020年6月5日的相同機會的一部分。

**人員A** Buyer Touchpoint資料集

* 首次接觸(FT) — 付費搜尋.AdWords - 9/1/2019
* 銷售機會建立(LC) - Organic Search.Google - 11/20/2019
* Post LC （表單填寫） — 網路研討會 — 3/4/2020

**人員B** Buyer Touchpoint資料集

* 首次接觸(FT) — 付費Social.Facebook - 8/26/2019
* 潛在客戶建立(LC) - Organic Search.Yahoo - 2/20/20
* Post LC （表單填寫） — 電子郵件 — 5/1/2020

**商機** Buyer Attribution Touchpoint資料將讀取如下……

* 首次接觸(FT) — 付費Social.Facebook - 8/26/2019
   * （來自&#x200B;**人員B**，因為他們具有帳戶/Opp的真&#x200B;_首次接觸_）
* 銷售機會建立(LC) - Organic Search.Google - 11/20/2019
   * （來自&#x200B;**人員A**，因為他們擁有帳戶/Opp的真&#x200B;_銷售機會建立_）
* 機會建立(OC) — 網路研討會 — 3/4/2020
   * （**人員A**&#x200B;的Post LC接觸點將是&#x200B;_OC接觸點_，因為這是我們最近一次與2020年3月7日建立的商機互動）
* 非公開 — 電子郵件 — 5/1/2020
   * （**人員B**&#x200B;的Post LC接觸點將是&#x200B;_已關閉的成功接觸點_，因為這是我們最近一次不得不在2020年5月6日關閉商機的互動）
