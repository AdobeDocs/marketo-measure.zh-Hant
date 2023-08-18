---
description: ROI控制面板 —  [!DNL Marketo Measure]  — 產品
title: ROI控制面板
hide: true
hidefromtoc: true
feature: Reporting
source-git-commit: f526b904fd3c04691ed784c259cb19fb24a5bd54
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 5%

---

# ROI控制面板 {#roi-dashboard}

ROI控制面板為行銷人員提供了跨管道、子管道和行銷活動的投資回報細微檢視。 它細緻地劃分成本和收入模式，同時重點指出每個銷售機會的成本、交易和機會等量度，以確保對行銷歸因的全面瞭解。

展示板回答的問題：

* 每個管道、子管道和行銷活動的ROI值為何？
* 成本和收入如何在每個管道、子管道和行銷活動中分配？
* 每個潛在客戶的成本、每個交易的成本，以及每個商機的成本是多少？

<table style="table-layout:auto"> 
<tbody>
 <tr> 
   <th>元件</th> 
   <th>說明</th>
   <th>鑽研欄位</th>
   <th>資料類型</th>
   <th>篩選器</th>
  </tr>
  <tr>
    <td>成本拼貼</td>
    <td>產生的總成本</td>
    <td>成本發生日期</td>
    <td><li>行銷活動ID</li>
<li>行銷活動名稱</li>
<li>管道</li>
<li>子管道</li>
<li>日期</li>
<li>支出</li></td>
    <td rowspan="15"><li>日期</li>
<li>歸因模型（設定）</li>
<li>管道</li>
<li>子管道</li>
<li>Campaign</li></td>
  </tr>
  <tr>
    <td>已歸因的收入圖磚</td>
    <td>已歸因的總收入</td>
    <td>關閉日期</td>
    <td><li>機會 ID</li>
<li>機會名稱</li>
<li>商機建立日期</li>
<li>商機結束日期</li>
<li>為已關閉(Y/N)</li>
<li>獲勝(Y/N)</li>
<li>歸因模型</li>
<li>已歸因的收入</li>
<li>已實現收入</li></td>
  </tr>
  <tr>
    <td>簡單ROI磚</td>
    <td>舊版ROI：指定時間範圍內的收入除以成本。 
    <li>成本：在篩選的日期期間中產生的成本。</li>
    <li>收入：在該時間範圍內「成功結案」商機的收入。</li></td>
    <td>關閉日期</td>
    <td>不適用</td>
  </tr>
  <tr>
    <td>已實現的ROI圖磚</td>
    <td>已實現的ROI：代表行銷活動在指定時間範圍內產生的接觸點實際結果。
    <li>成本：在篩選的日期期間中產生的成本。</li>
    <li>收入：從所有「成功交易」中實現收入，尤其是受概述時間範圍內接觸點影響的交易。</li>
    <br/><img src="assets/roi-dashboard-1.png" width="600"></td>
    <td>成本發生日期</td>
    <td>不適用</td>
  </tr>
  <tr>
    <td>新潛在客戶圖磚總數</td>
    <td>在指定期間內產生的新銷售機會總數（完整計數），包括接觸和未接觸的銷售機會。</td>
    <td>建立日期</td>
    <td rowspan="2">
    <li>銷售機會ID</li>
    <li>銷售機會電子郵件</li>
    <li>LC日期</li></td>
  </tr>
  <tr>
    <td>每個新潛在客戶圖磚的成本</td>
    <td>新銷售機會的總數（完整計數）除以成本。</td>
    <td>建立日期</td>
  </tr>
  <tr>
    <td>新機會圖磚總數</td>
    <td>在指定期間內產生的新商機（全數）總數，包括接觸和未接觸的銷售機會。</td>
    <td>建立日期</td>
    <td rowspan="2">
    <li>機會 ID</li>
    <li>機會名稱</li>
    <li>商機建立日期</li>
    <li>商機結束日期</li>
    <li>為已關閉(Y/N)</li>
    <li>獲勝(Y/N)</li>
    <li>目前階段</li></td>
  </tr>
  <tr>
    <td>每個新機會圖磚的成本</td>
    <td>新商機的總數（整數）除以成本。</td>
    <td>建立日期</td>
  </tr>
  <tr>
    <td>交易總計圖磚</td>
    <td>指定期間內完成的交易總數，包括沒有關聯接觸點的交易。</td>
    <td>關閉日期</td>
    <td><li>機會 ID</li>
<li>機會名稱</li>
<li>商機建立日期</li>
<li>商機結束日期</li>
<li>為已關閉(Y/N)</li>
<li>獲勝(Y/N)</li>
<li>目前階段</li>
<li>貨幣</li>
<li>歸因模型</li>
<li>已歸因的收入</li>
<li>已實現收入</li></td>
  </tr>
  <tr>
    <td>依管道的成本和收入圖表</td>
    <td>同時說明成本和收入的長條圖，旨在提供各個管道、子管道和促銷活動相關數值的比較透視。
    <br/><img src="assets/roi-dashboard-2.png" width="600"></td>
    <td>關閉日期</td>
    <td>成本：
<br/>
<li>行銷活動ID</li>
<li>行銷活動名稱</li>
<li>管道</li>
<li>子管道</li>
<li>成本發生日期</li>
<li>貨幣</li>
<li>支出</li>
<p>
收入：
<br/>
<li>機會 ID</li>
<li>機會名稱</li>
<li>商機建立日期</li>
<li>商機結束日期</li>
<li>為已關閉(Y/N)</li>
<li>獲勝(Y/N)</li>
<li>已歸因的收入</li>
<li>歸因模型</li>
<li>已歸因的收入</li>
<li>已實現收入</li></td>
  </tr>
  <tr>
    <td>隨時間推移實現與簡單ROI</td>
    <td>顯示已實現和簡單ROI之間比較的時間序列折線圖，追蹤其隨時間的進展。
    <br/><img src="assets/roi-dashboard-3.png" width="600"></td>
    <td>簡單ROI：成本產生日期與結束日期
    <p>已實現ROI：成本產生日期與接觸點日期</td>
    <td>不適用</td>
  </tr>
  <tr>
    <td>隨時間變化的成本圖表</td>
    <td>顯示季度/每月總成本的棧疊長條圖，依個別管道分段，以取得詳細劃分。
    <br/><img src="assets/roi-dashboard-4.png" width="600"></td>
    <td>成本發生日期</td>
    <td rowspan="2"><li>行銷活動ID</li>
<li>行銷活動名稱</li>
<li>管道</li>
<li>子管道</li>
<li>成本發生日期</li>
<li>貨幣</li>
<li>支出</li></td>
  </tr>
  <tr>
    <td>依據管道的成本圖表</td>
    <td>顯示依管道分段的行銷支出的長條圖。
    <br/><img src="assets/roi-dashboard-5.png" width="600"></td>
    <td>成本發生日期</td>
  </tr>
  <tr>
    <td>ROI摘要表格</td>
    <td>此表格顯示依個別管道分段的歸因收入、成本和ROI，以取得詳細劃分。
<p>
<b>欄:</b>
<p>
<li>管道/子管道/行銷活動</li>
<li>成本</li>
<li>已歸因的收入</li>
<li>簡單ROI</li>
<li>實現的投資報酬率</li>
<li>未實現的管道</li>
<ul style="padding-left: 30px;"><li>在指定時間範圍內從與行銷活動相關聯的接觸點（開放商機）進行管道</li></ul></td>
    <td>簡單ROI：成本產生日期與結束日期
    <p>已實現ROI：成本產生日期與接觸點日期</td>
    <td>不適用</td>
  </tr>
  <tr>
    <td>行銷支出表格</td>
    <td>此表格顯示成本、新銷售機會、商機以及依個別管道劃分的已結束交易，以進行詳細劃分。
<p>
<b>欄:</b>
<p>
<li>管道/子管道/行銷活動</li>
<li>成本</li>
<li>新銷售機會</li>
<li>每個新潛在客戶的成本</li>
<li>新商機</li>
<li>每個新機會的成本</li>
<li>交易已結束</li>
<li>每筆交易結案成本</li></td>
    <td><li>成本：成本發生日期</li>
<li>新銷售機會：建立日期</li>
<li>新商機：建立日期</li>
<li>交易已結束：結束日期</li></td>
    <td>不適用</td>
  </tr>
</tbody>
</table>
