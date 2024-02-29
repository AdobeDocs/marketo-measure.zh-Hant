---
description: 整合許可權概述 —  [!DNL Marketo Measure]
title: 整合許可權概述
feature: APIs, Integration
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '1286'
ht-degree: 1%

---

# 整合許可權概述 {#integration-permissions-overview}

本指南概述與Marketo Measure無縫整合的必要許可權，確保每個整合有效運作且沒有問題。

<table>
<thead>
  <tr>
    <th style="width:10%">整合</th>
    <th style="width:25%">資料類型
    <li>網路互動資料</li>
    <li>B2B系統資料</li>
    <li>廣告平台資料</li></th>
    <th style="width:25%">我們追蹤的內容</th>
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
    <br>
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
<br>
建議您在Dynamics中建立專屬的Marketo Measure使用者，以便我們透過匯出和匯入資料，進而避免您的CRM中其他使用者發生任何問題。 記下使用者名稱和密碼以及端點URL，因為建立Marketo Measure帳戶時會用到這些URL。
<p>
<b>安全性角色</b>
<br>
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
<br>
<a href="https://developers.facebook.com/docs/permissions/reference/ads_management/">ads_management</a>
<br>
<li>以程式設計方式建立行銷活動、管理廣告，以及擷取量度。</li>
<li>建立廣告管理工具，為廣告商提供創新解決方案和差異化的價值。</li>
<br>
<br>
<a href="https://developers.facebook.com/docs/permissions/reference/email">電子郵件</a>
<br>
<li>與人員通訊，讓他們使用與其Facebook設定檔相關聯的電子郵件地址登入您的應用程式。</li></td>
  </tr>
  <tr>
    <td>LinkedIn</td>
    <td>廣告平台資料
    <p>
    B2B系統資料（潛在客戶一般表單資料，包括表單和提交，分類為CRM活動）。</td>
    <td>Marketo Measure正在追蹤LinkedIn廣告行銷活動、創意和成本資料，以及Lead Gen Forms和回應。 我們會根據匯入的資料，產生LinkedIn接觸點，並將潛在客戶表單回應與客戶建立關聯。</td>
    <td><li>Marketo Measure需要行銷活動經理或客戶經理角色才能下載成本資料。 （範圍列1）</li>
    <br>
    <li>Marketo Measure需要超級管理員（頁面管理員角色，範圍列2）或潛在客戶Forms管理員（付費媒體管理員角色，範圍列3）來存取潛在客戶一般表單資料</li>
    <br>
    <li>超級管理員（頁面管理員角色，範圍列2）或贊助的內容海報（付費媒體管理員角色，範圍列3）是Marketo Measure操控自動標籤的必要專案</li>
    <p>
    <b>範圍</b>
    <br>
    <a href="https://www.linkedin.com/campaignmanager/accounts">在入口網站中設定使用者角色(需要登入LinkedIn帳戶)</a> - <a href="https://www.linkedin.com/help/lms/answer/a425731/user-roles-and-functions-in-campaign-manager">使用者角色概觀</a>：使用者角色、檢視及管理使用者許可權、指派角色，例如帳戶管理員或行銷活動管理員
    <p>
    <a href="https://www.linkedin.com/help/linkedin/answer/a570172/add-or-remove-admins-on-your-showcase-page?lang=en">設定頁面管理員角色 —  <a href="https://www.linkedin.com/help/linkedin/answer/a541981/linkedin-page-admin-roles-overview">頁面管理員角色定義</a>：頁面管理員角色，在需要的管理員頁面上
    <p>
    <a href="https://www.linkedin.com/help/linkedin/answer/a570172/add-or-remove-admins-on-your-showcase-page?lang=en">設定付費媒體管理員角色（尋找付費媒體管理員） - <a href="https://www.linkedin.com/help/linkedin/answer/a554540">付費媒體管理員定義</a>：付費媒體管理員角色</td>
  </tr>
  <tr>
    <td>DoubleClick</td>
    <td>廣告平台資料</td>
    <td>Marketo Measure會追蹤帳戶、廣告商、行銷活動、 （自訂）登陸頁面、廣告、創意、位置和網站。</td>
    <td><li>需要使用者的主要Google帳戶電子郵件地址</li>
<li>存取Campaign Manager 360帳戶所需的Campaign Manager許可權</li>
<ul>
<li>檢視和管理DoubleClick廣告商報告</li>
<li>檢視和管理DoubleClick行銷活動經理顯示廣告行銷活動</li>
<p>
    <b>範圍</b>
    <br>
    <a href="https://www.googleapis.com/auth/userinfo.email">https://www.googleapis.com/auth/userinfo.email</a>：檢視您的主要Google帳戶電子郵件地址
    <p>
     <a href="https://www.googleapis.com/auth/dfareporting">https://www.googleapis.com/auth/dfareporting</a>：檢視及管理廣告商的DoubleClick報表
    <p>
     <a href="https://www.googleapis.com/auth/dfatrafficking">https://www.googleapis.com/auth/dfatrafficking</a>：檢視及管理您的DoubleClick Campaign Manager (DCM)顯示廣告行銷活動</td>
  </tr>
  <tr>
    <td>AdWords</td>
    <td>廣告平台資料</td>
    <td>我們將AdWords整合至：
<p>
<li>匯入客戶廣告資料</li>
<li>匯入客戶廣告成本資料</li>
<li>附加url引數/更新URL追蹤範本，以更新使用者端的廣告</li>
<p>
Marketo Measure會追蹤促銷活動、廣告群組、創意、網站連結和關鍵字。</td>
    <td><li>需要使用者的主要Google帳戶電子郵件地址</li>
<p>
    <b>範圍</b>
    <br>
    <a href="https://www.googleapis.com/auth/userinfo.email">https://www.googleapis.com/auth/userinfo.email</a>：檢視您的主要Google帳戶電子郵件地址</td>
  </tr>
  <tr>
    <td>Bing</td>
    <td>廣告平台資料</td>
    <td>Marketo Measure會追蹤帳戶、行銷活動、廣告群組、創意和關鍵字。</td>
    <td><li>使用者必須透過其Microsoft帳戶授予「離線存取權」(即使未登入，也會授予Marketo Measure對一般使用者UserInfo的存取權)。 另請參閱 <a href="https://learn.microsoft.com/en-us/deployoffice/overview-extended-offline-access">Microsoft的頁面</a> 操作說明。</li>
<p>
    <b>範圍</b>
    <br>
    <a href="https://learn.microsoft.com/en-us/deployoffice/overview-extended-offline-access">https://learn.microsoft.com/en-us/deployoffice/overview-extended-offline-access</a>：保留您已授予許可權之資料的存取權。</td>
  </tr>
  <tr>
    <td>Marketo Engage</td>
    <td>B2B系統資料</td>
    <td>Marketo整合可讓Marketo Measure收集Marketo活動、人員、計畫和計畫成員資格。 此外，Marketo Measure會追蹤Marketo Cookie (Munchkin ID)，將Marketo網路活動連結至Marketo Measure主要接觸點， <a href="/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md#cookie-mapping">如此處所述</a>：
    <p>
    <i>由於Marketo Measure與Marketo整合，Marketo Measure Cookie ID現在也與Marketo Munchkin ID對應及同步。 這有助於縮短將匿名首次接觸歸因於網路工作階段的差距，而非將FT和LC接觸均歸因於Marketo活動。</i>
    </td>
    <td>客戶必須建立專用的Marketo Engage API使用者，並向Marketo Measure提供認證。 不需要其他許可權設定。 <a href="/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/set-up-marketo-connection.md#configuring-the-integration">瞭解更多</a>.</td>
  </tr>
  <tr>
    <td>Adobe Analytics</td>
    <td>B2B系統資料</td>
    <td>B2B客戶屬性整合可讓Marketo Measure和Adobe Analytics的共同使用者透過衍生自Marketo Measure歸因引擎的寶貴中繼資料，以及透過其與CRM (Microsoft Dynamics和Salesforce)的同步功能，擴充其Adobe Analytics使用者設定檔。 <a href="/help/marketo-measure-and-adobe/marketo-measure-integrations-with-adobe-analytics.md">瞭解更多</a>.</td>
    <td>客戶必須向Marketo Measure提供別名ID和FTP伺服器認證，才能將資料上傳至其Analytics執行個體。
    <p>
    請記下下列資訊，因為您將需要這些資訊來完成程式中的後續步驟：
    <p>
    <li>別名ID，可以是您希望它成為的任何值。 我們建議使用「marketomeasure_id」</li>
    <li>FTP伺服器主機名稱和認證（使用者名稱和密碼）</li>
    <p>
    <a href="/help/marketo-measure-and-adobe/marketo-measure-integrations-with-adobe-analytics.md#configuring-the-integration">瞭解更多</a></td>
  </tr>
  <tr>
    <td>Bizible Javascript</td>
    <td></td>
    <td><a href="/help/marketo-measure-tracking/setting-up-tracking/data-collected-by-javascript.md">bizible.js收集哪些資料</a>.</td>
    <td></td>
  </tr>
</tbody>
</table>

>[!MORELIKETHIS]
>
>[錯誤通知](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}
