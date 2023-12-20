---
description: 整合許可權概述 —  [!DNL Marketo Measure]  — 產品檔案
title: 整合許可權概述
hide: true
hidefromtoc: true
feature: APIs, Integration
source-git-commit: 4953d6c51a87669ced0a13e2a54810d14976585c
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 3%

---

# 整合許可權概述 {#integration-permissions-overview}

本指南概述與Marketo Measure無縫整合的必要許可權，確保每個整合有效運作且沒有問題。

<table>
<thead>
  <tr>
    <th>整合</th>
    <th>資料類型
    <li>網路互動資料</li>
    <li>B2B系統資料</li>
    <li>廣告平台資料</li></th>
    <th>我們追蹤的內容</th>
    <th>許可權需求</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Salesforce</td>
    <td>B2B系統資料    
</td>
    <td>Marketo Measure正在追蹤：
    <br>
    <li>帳戶</li>
<li>Campaign</li>
<li>CampaignMember</li>
<li>連絡人</li>
<li>CurrencyConversionRange</li>
<li>貨幣狀態</li>
<li>事件</li>
<li>FieldHistory （銷售機會、連絡人和商機）</li>
<li>銷售機會</li>
<li>機會</li>
<li>Opportunactrole</li>
<li>機會歷史記錄</li>
<li>任務</li>
<br>
建立的接觸點和其他資料會寫入帳戶、行銷活動、CampaignMember、Case、Contact、Lead和Opportunity的自訂雙機碼欄位中。</td>
    <td><b>Salesforce連線使用者許可權（必要）</b>
    <br>
    <b>為專用使用者設定的Marketo Measure管理員許可權：</b> 允許SFDC管理員在Marketo測量物件上執行CRUD操作。
    <br>
    <b>檢視和編輯轉換的潛在客戶許可權集：</b> 這可讓Marketo Measure在銷售機會轉換為聯絡人後裝飾銷售機會。
    <br>
    <b>Salesforce行銷使用者核取方塊：</b> 「行銷使用者」核取方塊可讓使用者建立行銷活動並使用「行銷活動匯入精靈」。
    <br>
    <b>Marketo Measure Standard使用者：</b> 讓使用者能從Marketo Measure物件讀取記錄。
    <p>
    <b>Salesforce標準欄位許可權</b>
    <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Salesforce標準物件與存取</a>
    <p>
    <b>Salesforce自訂欄位許可權</b>
    <br>
    我們提供功能設定，用於儲存客戶可以使用的自訂Salesforce欄位。 如果這些功能設定已定義，那麼我們需要「讀取」存取儲存在功能設定中的每個Salesforce欄位(例如，如果CustomLeadSourceField設定值等於「LeadSource__c」，那麼我們需要「讀取」存取此欄位)。
    </td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
</tbody>
</table>
