---
description: 錯誤通知 —  [!DNL Marketo Measure]
title: 錯誤通知
feature: Fundamentals
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 0%

---

# 錯誤通知 {#error-notifications}

以下是您可透過應用程式內通知或電子郵件收到的錯誤清單。 如果您收到任何這些訊息，請依照各自的疑難排解步驟進行。 如果這些步驟沒有解決問題，請連絡 [Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support).

<table>
  <tbody>
    <tr>
      <th style="width:31%">錯誤碼</th>
      <th style="width:23%">通知範例</th>
      <th style="width:23%">說明</th>
      <th style="width:23%">疑難排解步驟</th>
    </tr>
    <tr>
      <td>API_DISABLED</td>
      <td>Crm匯入期間發生錯誤： API_DISABLED ：已針對此使用者停用API呼叫</td>
      <td>已為Marketo Measure使用者停用API許可權。</td>
      <td>請參閱以下Salesforce檔案： <a href="https://help.salesforce.com/s/articleView?language=en_US&amp;id=sf.branded_apps_commun_api_permset.htm&amp;type=5">如何啟用API存取</a>.</td>
    </tr>
    <tr>
      <td>API_LIMIT_EXCEEDED</td>
      <td>Crm匯出期間發生錯誤：PI_LIMIT_EXCEEDED</td>
      <td>已超過CRM的API限制（24小時）。</td>
      <td>如需調整API信用配置的協助，請參閱下列CRM檔案：</p>
          <ul>
            <li><a href="https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/service-protection-monitoring">Dynamics</a>
            </li>
            <li><a href="https://developer.salesforce.com/docs/atlas.en-us.salesforce_app_limits_cheatsheet.meta/salesforce_app_limits_cheatsheet/salesforce_app_limits_platform_api.htm">Salesforce</a>
            </li>
          </ul>
          <p>您也可以依照下列步驟調整Marketo Measure使用的CRM積分：</p>
          <ul>
            <li>瀏覽至 <b>設定</b> &gt; <b>CRM</b> &gt; <b>一般</b></li>
            <li>更新每日CRM API限制<br/>
              <ul>
                <li><b>注意：預設值為100,000</b></li>
              </ul>
            </li>
          </ul>
          <p>
           <img src="assets/error-notifications-1.png">
          </p>
      </td>
    </tr>
    <tr>
      <td>INVALID_ADOBE_ANALYTICS_CONFIGURATION</td>
      <td>Adobe Analytics匯出期間發生錯誤： INVALID_ANALYTICS_CONFIGURATION_ADOBE：錯誤：不允許上傳。 上傳前先確認資料來源結構描述。 資料來源Id：1234</td>
      <td>Adobe Analytics整合的設定不正確。</td>
      <td>請參閱下列說明文章，以確保設定正確無誤：
        <ul>
          <li>
            <a href="/help/marketo-measure-and-adobe/marketo-measure-integrations-with-adobe-analytics.md">Marketo Measure與Adobe Analytics整合</a>
          </li>
          <li>
            <a href="https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html">建立客戶屬性來源及上傳資料檔案</a>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>INVALID_CURRENCY_ISO_CODE</td>
      <td>廣告匯入期間發生錯誤： INVALID_CURRENCY_ISO_CODE： Marketo Measure不支援貨幣XXX。
      <p>
      廣告匯入期間發生錯誤： INVALID_CURRENCY_ISO_CODE ： Marketo Measure不支援帳戶1234的貨幣XXX。</td>
      <td>發生不支援的貨幣。</td>
      <td>在通知(廣告、Crm、Marketo)中指出的來源系統中，會確保與記錄關聯的貨幣具有支援且有效的貨幣。 支援的貨幣衍生自ISO貨幣標準。</td>
    </tr>
    <tr>
      <td>MISSING_CONVERTED_LEAD_PERMISSION</td>
      <td>Crm匯出期間發生錯誤： MISSING_CONVERTED_LEAD_PERMISSION</td>
      <td>Marketo Measure缺少「檢視/編輯轉換的潛在客戶」許可權</td>
      <td>如需在CRM中啟用此許可權的相關協助，請參閱下列Experience League檔案<br/>
          <a href="/help/marketo-measure-salesforce-reporting/additional-functionality/enabling-the-permission-to-edit-converted-leads.md">啟用許可權以編輯轉換的潛在客戶</a></td>
    </tr>
    <tr>
      <td>MISSING_FIELD_READ_PERMISSION</td>
      <td>Crm匯入期間發生錯誤： MISSING_FIELD_READ_PERMISSION ：實體型別'Event'： INVALID_FIELD：<br/>
    SystemModstamp，IsDeleted，WhoId，bizible2__Bizible_Touchpoint_Date__c</td>
      <td>Marketo Measure缺少必要欄位的讀取許可權。</td>
      <td>請參閱下列說明文章，以取得Marketo Measure所需許可權的指引：
        <ul>
          <li><a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/marketo-measure-dynamics-schema.md">Dynamics</a>
          </li>
          <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Salesforce</a>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>MISSING_ISREPLICATEABLE_PERMISSION</td>
      <td>Crm匯入期間發生錯誤： MISSING_ISREPLICATEABLE_PERMISSION ：我們缺少Campaign的IsReplicateable許可權</td>
      <td>Salesforce物件需要此許可權，我們才能讓您的Marketo Measure和Salesforce保持同步。</td>
      <td>請聯絡Salesforce支援，以取得設定物件的可複製許可權的相關協助。</td>
    </tr>
    <tr>
      <td>MISSING_OBJECT_READ_PERMISSION</td>
      <td>Crm匯入期間發生錯誤： MISSING_OBJECT_READ_PERMISSION ：實體型別Campaign'： CRM錯誤碼： MISSING_PERMISSION</td>
      <td>Marketo Measure缺少必要物件的讀取許可權。</td>
      <td rowspan="2">請參閱下列說明文章，以取得Marketo Measure所需許可權的指引：
          <ul>
            <li><a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/marketo-measure-dynamics-schema.md">Dynamics</a>
            </li>
            <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Salesforce</a>
            </li>
          </ul>
      </td>
    </tr>
    <tr>
      <td>MISSING_OBJECT_WRITE_PERMISSION</td>
      <td>Crm匯出期間發生錯誤： MISSING_OBJECT_WRITE_PERMISSION ：實體型別'bizible2_Bizible_Attribution_Touchpoint'： CRM錯誤碼： MISSING_PERMISSION</td>
      <td>Marketo Measure缺少必要物件的寫入許可權。</td>
    </tr>
    <tr>
      <td>NULL_EMPTY_CURRENCY_ISO_CODE</td>
      <td>
        <p>
          Crm匯入期間發生錯誤： NULL_EMPTY_CURRENCY_ISO_CODE：為RecordId 1234啟用MultiCurrency時，貨幣ISO代碼為NULL或空白
      </td>
      <td>貨幣必須是支援的ISO貨幣代碼。</td>
      <td>在通知(廣告、Crm、Marketo)中指出的來源系統中，會確保與記錄關聯的貨幣具有支援且有效的貨幣。 支援的貨幣衍生自ISO貨幣標準。</td>
    </tr>
    <tr>
      <td>OPERATION_TO_LARGE</td>
      <td>Crm匯入期間發生錯誤： OPERATION_TOO_LARGE ：我們需要「檢視所有資料」許可權才能成功查詢活動。</td>
      <td>CRM設定不允許Marketo Measure查詢足夠大的資料集</td>
      <td>授予Marketo Measure對指定物件的「檢視所有資料」許可權。
      <p>
      「檢視全部資料」許可權的更多資訊 <a href="https://developer.salesforce.com/docs/atlas.en-us.securityImplGuide.meta/securityImplGuide/users_profiles_view_all_mod_all.htm">可在此處找到</a>.</td>
    </tr>
    <tr>
      <td>不支援的_CRM_PACKAGE_VERSION</td>
      <td>Crm匯入期間發生錯誤： UNSUPPORTED_CRM_PACKAGE_VERSION ：更新您的CRM套件</td>
      <td>不再支援偵測到的目前套件。</td>
      <td>將您的套件升級至最新版本：
        <ul>
          <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/best-practices-for-marketo-measure-crm-package.md">最佳實務</a>
          </li>
          <li><a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md">Dynamics</a>
          </li>
          <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md">Salesforce</a>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>
