---
description: 說明BT和BAT之間的接觸點位置和產生 —  [!DNL Marketo Measure]  — 產品檔案
title: BT之間接觸點位置及產生的說明，以及 [!DNL BATs]
exl-id: 4903f917-a366-4767-a126-5216d2377399
source-git-commit: b910e5aedb9e178058f7af9a6907a1039458ce7a
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 0%

---

# BT之間接觸點位置及產生的說明，以及 [!DNL BATs] {#explanation-of-touchpoint-positions-and-generation-across-bts-and-bats}

**產生接觸點位置並瀏覽購買者歷程**

了解購買者接觸點位置及其觸發方式，對於成功透過 [!DNL Marketo Measure] 資料。 您會想要清楚了解潛在客戶在完成購買者歷程時的表現，進而了解接觸點資料中的外觀。 如需此主題的詳細內容，建議您檢閱 [[!UICONTROL Touchpoint Generation & Mapping]](/help/configuration-and-setup/getting-started-with-marketo-measure/touchpoint-generation-and-mapping.md) 文章。

[!DNL Marketo Measure] 有多種接觸點位置，是由購買者歷程中的各種步驟所觸發。 報告時 [!DNL Marketo Measure] 資料中有兩組接觸點資料：購買者接觸點(BT)和購買者歸因接觸點(BAT)。 您可能會注意到這些資料集與不同對象的位置稍有不同。 如需此主題的詳細內容，建議您檢閱 [購買者接觸點(BT)與購買者歸因接觸點(BAT)之間的差異](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md) 文章。

**購買者接觸點(BT)**:這些是與個人及其歷程相關聯的接觸點，且將是該個人專屬的接觸點。 以下現成報表是以購買者接觸點資料建立。

* [!DNL Marketo Measure] 101:按ID列出的銷售機會
* [!DNL Marketo Measure] 101:按渠道列出的銷售機會
* [!DNL Marketo Measure] 101:依ID的銷售機會/聯絡人
* [!DNL Marketo Measure] 101:按渠道列出的銷售機會/聯繫人

以下概述「購買者接觸點」位置，說明個人在歷程中的位置，以及為獲得該位置而採取的動作。

<table> 
 <tbody>
  <tr>
   <th>購買者接觸點(BT)位置</th> 
   <th>接觸點類型（可觸發接觸點的動作）</th> 
   <th>接觸點說明</th> 
  </tr>
  <tr>
   <td>首次接觸(FT)</td> 
   <td>網站造訪</td> 
   <td>個人與您品牌的首次行銷互動</td> 
  </tr>
  <tr>
   <td>銷售機會建立(LC)</td> 
   <td>表單填寫 <strong>或</strong> 促銷活動/計畫包含</td> 
   <td>填入個人的第一個表單（通常是表單提交，但也可能是促銷活動/方案包含）</td> 
  </tr>
  <tr>
   <td>Post LC</td> 
   <td>表單填寫 <strong>或</strong> 促銷活動/計畫包含</td> 
   <td>個人在LC後完成的任何表單（或後續的促銷活動/方案包含）</td> 
  </tr>
 </tbody>
</table>

**購買者歸因接觸點(BATS)**:這些是與Opportunity及其歷程相關聯的接觸點。 這些接觸點在連接到機會及其聯繫人時將與收入相連。 以下現成報表是以購買者歸因接觸點資料建立。

* [!DNL Marketo Measure] 101:按ID列出的銷售機會
* [!DNL Marketo Measure] 101:按ID渠道列出的銷售機會

<table> 
 <tbody>
  <tr>
   <th>購買者歸因接觸點(BAT)位置</th> 
   <th>接觸點類型（可觸發接觸點的動作）</th> 
   <th>接觸點說明</th> 
  </tr>
  <tr>
   <td>首次接觸(FT)</td> 
   <td>網站造訪</td> 
   <td>連絡人與您品牌進行的首次行銷互動</td> 
  </tr>
  <tr>
   <td>銷售機會建立(LC)</td> 
   <td>表單填寫 <strong>或</strong> 促銷活動/計畫包含</td> 
   <td>填寫聯絡人的第一份表單（通常是表單提交，但也可能是促銷活動/方案包含）</td> 
  </tr>
  <tr>
   <td>機會建立</td> 
   <td>表單填寫 <strong>或</strong> 網站造訪 <strong>或</strong> 促銷活動/計畫包含</td> 
   <td>建立Opp時最接近的行銷互動</td> 
  </tr> 
  <tr>
   <td>已關閉韓元/虧損</td> 
   <td>表單填寫 <strong>或</strong> 網站造訪 <strong>或</strong> 促銷活動/計畫包含</td> 
   <td>最接近Opp關閉時的行銷互動（Won或Lost）</td> 
  </tr>
  <tr>
   <td>中間接觸</td> 
   <td>表單填寫 <strong>或</strong> 促銷活動/計畫包含</td> 
   <td>當聯繫人填寫線上表單時，它與里程碑接觸點不重合</td> 
  </tr>
 </tbody>
</table>

[!DNL Marketo Measure] 有這兩組接觸點資料，以便清楚了解個人的歷程以及商機。 這兩個接觸點資料集可讓您清楚掌握從漏斗頂部到漏斗底部所發生的一切。

下列範例顯示從購買者接觸點(BT)到購買者歸因接觸點(BAT)的資料流程。 在此示例中，人員A和人員B都是同一Opportunity的一部分，該Opportunity的建立日期為3/7/2020，關閉日期為5/6/2020。

**人員A** 購買者接觸點資料集

* 首次接觸(FT) — 付費搜尋.AdWords - 9/1/2019
* 銷售機會建立(LC) — 有機搜尋。Google- 11/20/2019
* 貼文LC（表單填寫） — 網路研討會 — 3/4/2020

**人員B** 購買者接觸點資料集

* 首次接觸(FT) — 付費Social.Facebook- 8/26/2019
* 銷售機會建立(LC)- Organic Search.Yahoo - 2/20/2020
* 貼文LC（表單填寫） — 電子郵件 — 5/1/2020

**機會** 購買者歸因接觸點資料如下所示……

* 首次接觸(FT) — 付費Social.Facebook- 8/26/2019
   * 從 **人員B** 因為他們是真的 _首次接觸_ （針對帳戶/Opp）
* 銷售機會建立(LC) — 有機搜尋。Google- 11/20/2019
   * 從 **人員A** 因為他們是真的 _銷售機會建立_ （針對帳戶/Opp）
* 機會建立(OC) — 網路研討會 — 3/4/2020
   * (貼文LC接觸點來自 **人員A** 會是 _OC接觸點_ 因為這是我們最近一次與Opportunity的交互(在3/7/2020上建立)
* 已關閉韓元 — 電子郵件 — 5/1/2020
   * (貼文LC接觸點來自 **人員B** 會是 _閉合Won接觸點_ 因為這是我們最近一次與Opportunity的互動，在5/6/2020上結束)
