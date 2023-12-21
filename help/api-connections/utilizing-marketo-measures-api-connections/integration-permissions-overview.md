---
description: 整合許可權概述 —  [!DNL Marketo Measure]  — 產品檔案
title: 整合許可權概述
hide: true
hidefromtoc: true
feature: APIs, Integration
source-git-commit: d7ded9075f7f5831314d59294327f1e4928baf8a
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 2%

---

# 整合許可權概述 {#integration-permissions-overview}

本指南概述與Marketo Measure無縫整合的必要許可權，確保每個整合有效運作且沒有問題。

<table>
<thead>
  <tr>
    <th style="width:10%">整合</th>
    <th style="width:20%">資料類型
    <li>網路互動資料</li>
    <li>B2B系統資料</li>
    <li>廣告平台資料</li></th>
    <th style="width:30%">我們追蹤的內容</th>
    <th style="width:40%">許可權需求</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Salesforce</td>
    <td>B2B系統資料    
</td>
    <td>Marketo Measure正在追蹤：
    <p>
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
<p>
建立的接觸點和其他資料會寫入帳戶、行銷活動、CampaignMember、Case、Contact、Lead和Opportunity的自訂雙機碼欄位中。</td>
    <td><b>Salesforce連線使用者許可權（必要）</b>
    <p>
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
    <td>Dynamics</td>
    <td>B2B系統資料</td>
    <td>Marketo Measure正在追蹤：
    <p>
    <li>帳戶
<li>Activityparty
<li>活動指標
<li>Campaign
<li>CampaignItem （系統中的CampaignList）
<li>CampaignResponse （系統中的CampaignMember）
<li>連絡人
<li>銷售機會
<li>清單（系統中的MarketingList）
<li>ListMember （系統中的MarketingListMember）
<li>機會
<li>組織
<li>TransactionCurrency （我們系統中的CurrencyConversionRange和CurrencyStatus）
<li>約會， CampaignActivity，電子郵件，傳真， IncidentResolution，信件， PhoneCall， RecurringAppointmentMaster， ServiceAppointment，工作
<li>bizible2_bizible_abtest
<li>bizible2_bizible_attribution_touchpoint
<li>bizible2_bizible_event
<li>bizible2_bizible_history
<li>bizible2_bizible_touchpoint
<p>
建立的接觸點和其他資料會寫入帳戶、行銷活動、CampaignResponse、Contact、Lead、List、Opportunity和PhoneCall的自訂雙機碼欄位中</td>
    <td><b>Marketo Measure使用者許可權</b>
<p>
建議您在Dynamics中建立專屬的Marketo Measure使用者，以便我們透過匯出和匯入資料，進而避免您的CRM中其他使用者發生任何問題。 記下使用者名稱和密碼以及端點URL，因為建立Marketo Measure帳戶時會用到這些URL。
<p>
<b>安全性角色</b>
<p>
如果您的組織使用Dynamics安全性角色，請確定已連線的使用者或專用的Marketo Measure使用者擁有所需實體的足夠讀取/寫入許可權。
<br>
安全性角色位於此處：設定&gt;安全性&gt;安全性角色
<br>
針對Marketo Measure自訂實體，我們需要所有實體的完整許可權。
<p>
<b>Dynamics Standard欄位許可權</b>
<br>
<a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/marketo-measure-dynamics-schema.md">Marketo Measure Dynamics結構</a>
<p>
<b>Dynamics自訂欄位許可權</b>
<br>
對於潛在客戶或聯絡人實體上客戶想要用於自訂隱藏/移除接觸點設定規則的任何欄位，我們需要「讀取」存取權。
<br>
我們需要Lead或Opportunity實體上任何欄位的READ存取權，客戶想要將其用於區段規則或階段對應。
<br>
我們需要Campaign、CampaignResponse和List實體上任何客戶想要用於同步Campaign/MarketingList成員的欄位的「讀取」存取權。
</td>
  </tr>
  <tr>
    <td>Facebook</td>
    <td>廣告平台資料</td>
    <td>我們將Facebook整合至：
<p>
<li>匯入客戶廣告資料</li>
<li>匯入客戶廣告成本資料</li>
<li>附加url引數以更新使用者端的廣告</li>
<p>
Marketo Measure會追蹤帳戶、行銷活動、廣告群組、廣告、篩選器ID和URL。</td>
    <td><li>需要有ads_management許可權才能建立行銷活動、管理廣告或擷取廣告量度。</li>
<li>使用者必須具備電子郵件許可權，才能登入其Facebook電子郵件。</li>
<p>
<b>範圍</b>
<p>
<a href="https://developers.facebook.com/docs/permissions/reference/ads_management/">ads_management</a>
<br>
<li>以程式設計方式建立行銷活動、管理廣告，以及擷取量度。</li>
<li>建立廣告管理工具，為廣告商提供創新解決方案和差異化的價值。</li>
<p>
<a href="https://developers.facebook.com/docs/permissions/reference/email">電子郵件</a>
<br>
<li>與人員通訊，讓他們使用與其Facebook設定檔相關聯的電子郵件地址登入您的應用程式。</li></td>
  </tr>
  <tr>
    <td>LinkedIn</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>DoubleClick</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>AdWords</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Bing</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Marketo Engage</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Adobe Analytics</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Bizible Javascript</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
</tbody>
</table>
