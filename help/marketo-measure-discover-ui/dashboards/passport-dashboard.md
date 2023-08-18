---
description: Passport儀表板 —  [!DNL Marketo Measure]  — 產品
title: Passport儀表板
feature: Reporting
source-git-commit: 436e30c2a4138d780232d6ba9e64456d6277ac9b
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 3%

---

# Passport儀表板 {#passport-dashboard}

Passport儀表板可讓行銷人員在指定期間內透過不同階段轉換時，動態檢視潛在客戶、聯絡人和機會。 透過篩選特定日期，使用者也可以取得當天的記錄快照。

展示板回答的問題：

* 每個非終端機階段中，所選日期上有多少銷售機會、聯絡人或銷售機會？
* 在指定的期間內，有多少不同的潛在客戶或聯絡人會進行到每個暫時的階段？
   * _範例_：如果銷售機會A在2023年1月1日處於階段1，並在2023年3月31日之前進入階段5，則2023年第1季的Passport分析會將銷售機會A計入階段1到5。
* 在指定的時間範圍內，每個暫時階段傳遞了多少個不重複的機會？

<table style="table-layout:auto"> 
<tbody>
<tr> 
   <th>元件</th> 
   <th>說明</th>
   <th>日期型別</th>
   <th>鑽研欄位</th>
   <th>篩選器</th>
  </tr>
  <tr>
    <td>機會</td>
    <td><li>每個階段都會顯示在指定時間範圍內傳遞且具有BAT的Opportunity數量。</li>
<ul style="padding-left: 30px;"><li>如果機會在該範圍內的多個階段中進行，則會將其計入每個階段中。</li></ul>
<li>排除終端機階段，例如「已關閉的贏家」和「已關閉的輸家」。</li>
<li>開始和結束日期皆包含。</li>
<br/><img src="assets/passport-dashboard-1.png" width="600"></td>
    <td rowspan="2">轉換日期</td>
    <td></td>
    <td rowspan="2"><li>日期</li>
<li>管道</li>
<li>子管道</li>
<li>Campaign</li>
<li>區段</li></td>
  </tr>
  <tr>
    <td>潛在客戶/聯絡人</td>
    <td><li>每個階段都會顯示具有在指定時間範圍內通過他們的BT的Lead或Contact的數量。</li>
<ul style="padding-left: 30px;"><li>是否顯示「銷售機會」或「連絡人」取決於在「設定&gt;歸因設定&gt;預設儀表板物件」中設定的偏好設定。</li></ul>
<li>排除終端機階段，例如「已關閉的贏家」和「已關閉的輸家」。</li>
<li>開始和結束日期皆包含。</li>
<br/><img src="assets/passport-dashboard-2.png" width="600"></td>
    <td><li>銷售機會/聯絡人ID</li>
<li>銷售機會/聯絡人電子郵件</li>
<li>建立日期</li>
<li>目前階段</li>
<li>轉換日期</li>
<li>轉換截止日期</li></td>
  </tr>
</tbody>
</table>

>[!MORELIKETHIS]
>
>[探索儀表板基本知識](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
