---
description: 跨BT和BAT的接觸點位置和產生方式說明 —  [!DNL Marketo Measure]  — 產品檔案
title: 跨BT和的接觸點位置和產生方式說明 [!DNL BATs]
exl-id: 4903f917-a366-4767-a126-5216d2377399
feature: Touchpoints
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 0%

---

# 跨BT和的接觸點位置和產生方式說明 [!DNL BATs] {#explanation-of-touchpoint-positions-and-generation-across-bts-and-bats}

**產生接觸點位置並流經購買者歷程**

瞭解購買者接觸點位置及其觸發方式，對於成功使用報告至關重要 [!DNL Marketo Measure] 資料。 您會想要清楚瞭解潛在客戶在買家歷程中的行為，進而瞭解在接觸點資料中會是什麼樣子。 如需有關本主題的詳細資訊，建議您檢閱 [[!UICONTROL Touchpoint Generation & Mapping]](/help/configuration-and-setup/getting-started-with-marketo-measure/touchpoint-generation-and-mapping.md) 文章。

[!DNL Marketo Measure] 具有由購買者歷程中的不同步驟觸發的各種接觸點位置。 報告時 [!DNL Marketo Measure] 資料有兩組接觸點資料：購買者接觸點(BT)和購買者歸因接觸點(BAT)。 您可能會注意到這些資料集在與不同物件相關的位置稍有不同。 如需有關本主題的詳細資訊，建議您檢閱 [購買者接觸點(BT)和購買者歸因接觸點(BAT)之間的差異](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md) 文章。

**購買者接觸點(BT)**：這些是與個人及其歷程相關聯的接觸點，將是該個人專屬的。 下列現成可用的報表是根據購買者接觸點資料所建立。

* [!DNL Marketo Measure] 101：依ID的銷售機會
* [!DNL Marketo Measure] 101：依據管道的銷售機會
* [!DNL Marketo Measure] 101：銷售機會/聯絡人（依ID）
* [!DNL Marketo Measure] 101：銷售機會/聯絡人（依管道）

以下概述購買者接觸點位置，其說明個人在其歷程中的位置，以及他們為獲得該位置所採取的行動。

<table> 
 <tbody>
  <tr>
   <th>購買者接觸點(BT)位置</th> 
   <th>接觸點型別（可觸發接觸點的動作）</th> 
   <th>接觸點說明</th> 
  </tr>
  <tr>
   <td>首次接觸(FT)</td> 
   <td>網頁造訪</td> 
   <td>個人與您的品牌進行的第一個行銷互動</td> 
  </tr>
  <tr>
   <td>銷售機會建立(LC)</td> 
   <td>表單填寫 <strong>或</strong> 行銷活動/方案包含</td> 
   <td>個人填寫的第一個表單具有（通常是表單提交，但也可能是行銷活動/方案包含）</td> 
  </tr>
  <tr>
   <td>Post LC</td> 
   <td>表單填寫 <strong>或</strong> 行銷活動/方案包含</td> 
   <td>個人在LC之後完成的任何形式（或後續的行銷活動/方案包含）</td> 
  </tr>
 </tbody>
</table>

**購買者歸因接觸點(BATS)**：這些是與機會及其歷程相關聯的接觸點。 這些接觸點將連線至收入，因為它們會連線至商機及其連絡人。 下列現成可用的報表是根據購買者歸因接觸點資料所建立。

* [!DNL Marketo Measure] 101：依ID排列商機
* [!DNL Marketo Measure] 101：依ID管道的商機

<table> 
 <tbody>
  <tr>
   <th>購買者歸因接觸點(BAT)位置</th> 
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
   <td>表單填寫 <strong>或</strong> 行銷活動/方案包含</td> 
   <td>聯絡人的第一個表單填寫（通常是表單提交，但也可能是行銷活動/方案包含）</td> 
  </tr>
  <tr>
   <td>機會建立</td> 
   <td>表單填寫 <strong>或</strong> 網頁造訪 <strong>或</strong> 行銷活動/方案包含</td> 
   <td>建立Opp時最接近的行銷互動</td> 
  </tr> 
  <tr>
   <td>已關閉的贏家/輸家</td> 
   <td>表單填寫 <strong>或</strong> 網頁造訪 <strong>或</strong> 行銷活動/方案包含</td> 
   <td>最接近Opp關閉時的行銷互動（成功或失敗）</td> 
  </tr>
  <tr>
   <td>中間接觸</td> 
   <td>表單填寫 <strong>或</strong> 行銷活動/方案包含</td> 
   <td>當連絡人填寫線上表單時，表單未與里程碑接觸點一致</td> 
  </tr>
 </tbody>
</table>

[!DNL Marketo Measure] 這兩組接觸點資料可讓您清楚瞭解個人的歷程以及機會。 這兩個接觸點資料集為您提供從漏斗頂部到漏斗底部的清晰發生情況地圖。

下列範例顯示從購買者接觸點(BT)到購買者歸因接觸點(BAT)的資料流程。 在此範例中，人員A和人員B都是建立日期為2020年3月7日而結束日期為2020年6月5日的相同機會的一部分。

**人員A** 購買者接觸點資料集

* 首次接觸(FT) — 付費搜尋.AdWords - 9/1/2019
* 銷售機會建立(LC) - Organic Search.Google - 11/20/2019
* Post LC （表單填寫） — 網路研討會 — 3/4/2020

**人員B** 購買者接觸點資料集

* 首次接觸(FT) — 付費Social.Facebook - 8/26/2019
* 潛在客戶建立(LC) - Organic Search.Yahoo - 2/20/20
* Post LC （表單填寫） — 電子郵件 — 5/1/2020

**機會** 購買者歸因接觸點資料如下所示……

* 首次接觸(FT) — 付費Social.Facebook - 8/26/2019
   * (從 **人員B** 因為它們具有 _首次接觸_ （適用於帳戶/Opp）
* 銷售機會建立(LC) - Organic Search.Google - 11/20/2019
   * (從 **人員A** 因為它們具有 _銷售機會建立_ （適用於帳戶/Opp）
* 機會建立(OC) — 網路研討會 — 3/4/2020
   * (貼文LC接觸點來自 **人員A** 會是 _OC接觸點_ 因為這是我們最近一次與2020年3月7日所建立的Opportunity互動)
* 非公開 — 電子郵件 — 5/1/2020
   * (貼文LC接觸點來自 **人員B** 會是 _已關閉的成功接觸點_ 因為這是我們最近一次與機會互動（已於2020年5月6日關閉）
