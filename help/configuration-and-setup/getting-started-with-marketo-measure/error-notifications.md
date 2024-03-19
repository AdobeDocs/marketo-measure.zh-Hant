---
description: 錯誤通知 —  [!DNL Marketo Measure]
title: 錯誤通知
feature: Fundamentals
exl-id: ed07eed6-ddeb-4856-a1ac-ea3d571283f6
source-git-commit: 20f886a0c6f448956ad2fda2d21a25f8d9a5a6af
workflow-type: tm+mt
source-wordcount: '1692'
ht-degree: 0%

---

# 錯誤通知 {#error-notifications}

以下是您可透過應用程式內通知或電子郵件收到的錯誤清單。 如果您收到任何這些訊息，請依照各自的疑難排解步驟進行。 如果這些步驟沒有解決問題，請連絡 [Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support).

若要在中檢視完整通知訊息 [!DNL Marketo Measure]，按一下 **檢視全部** 在「通知」標籤底部。

![](assets/error-notifications-1.png)

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
           <img src="assets/error-notifications-2.png">
          </p>
      </td>
    </tr>
    <tr>
      <td>CANNOT_EXECUTE_FLOW_TRIGGER</td>
      <td>Crm匯出期間發生錯誤： CANNOT_EXECUTE_FLOW_TRIGGER ：實體型別「Contact」為您的Salesforce管理員提供這些詳細資料。
限制超過您或您的組織已超過此功能的限制。 錯誤ID：123456</td>
      <td>無法儲存記錄，因為它不符合Salesforce組織中設定的觸發程式流程規則。</td>
      <td>檢閱通知訊息的完整詳細資料，並在Salesforce組織中檢閱流程觸發程式。
有關流程觸發器的Salesforce檔案 <a href="https://admin.salesforce.com/blog/2023/what-is-a-record-triggered-flow#:~:text=A%20record%2Dtriggered%20flow%20allows,is%20created%20and%2For%20updated">可在此處找到</a>.
      </td>
    </tr>
    <tr>
      <td>CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY</td>
      <td>Crm匯出期間發生錯誤： CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY ：實體型別'Lead'： CRM錯誤碼： CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY， CRM錯誤訊息： System.LimitException：超過頂端CPU時間限制，RecordId： 0123456
      <p>
      Crm匯出期間發生錯誤： CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY ：實體型別'Account'： CRM錯誤碼： CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY， CRM錯誤訊息：無法更新實體型別：帳戶，RecordId： 0123456</td>
      <td>觸發器阻止更新或插入物件。
      <p>
      或
      <p>
      物件缺少許可權。</td>
      <td>檢閱導致插入/更新失敗的觸發程式碼。 如需有關觸發器的更多詳細資訊，請參閱以下Salesforce檔案：
        <ul>
          <li><a href="https://help.salesforce.com/s/articleView?id=sf.code_manage_triggers.htm&amp;type=5">Apex觸發器</a>
          </li>
          <li><a href="https://admin.salesforce.com/blog/2023/what-is-a-record-triggered-flow#:~:text=A%20record%2Dtriggered%20flow%20allows,is%20created%20and%2For%20updated">流量觸發器</a>
          </li>
        </ul>
        <p>
        提供所有必要的許可權給 <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Marketo Measure使用者</a>.
      </td>
    </tr>
    <tr>
      <td>DUPLICATES_DETECTED</td>
      <td>Crm匯出期間發生錯誤： DUPLICATES_DETECTED ：實體型別「Contact」： CRM錯誤碼： DUPLICATES_DETECTED， CRM ErrorMessage：您正在建立重複的記錄。 我們建議您改用現有記錄。RecordId： 0123456</td>
      <td>匯入至Salesforce組織的記錄已經存在。</td>
      <td><a href="https://help.salesforce.com/s/articleView?id=000390009&amp;type=1">停用「重複規則」設定</a> 以允許重複專案。
          <p>
          從中排除Marketo Measure專用使用者 <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">自訂驗證規則</a>.</td>
    </tr>
    <tr>
      <td>DUPLICATE_VALUE</td>
      <td>Crm匯出期間發生錯誤： DUPLICATE_VALUE ：實體型別「銷售機會」： CRM錯誤碼： DUPLICATE_VALUE， CRM錯誤訊息：發現重複值： Email_Unique__c重複識別碼為123的記錄上的值，記錄識別碼： 456</td>
      <td>匯入至Salesforce組織的欄位不允許重複值。</td>
      <td>取消核取 <a href="https://help.salesforce.com/s/articleView?id=000390009&amp;type=1">「不重複核取方塊」</a> （位於Salesforce）。
          <p>
          從中排除Marketo Measure專用使用者 <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">自訂驗證規則</a>.</td>
    </tr>
    <tr>
      <td>實體_IS_LOCKED</td>
      <td>Crm匯出期間發生錯誤： ENTITY_IS_LOCKED ：實體型別「Account」： CRM錯誤碼： ENTITY_IS_LOCKED， CRM錯誤訊息：此記錄已鎖定。 如果您需要編輯，請聯絡您的管理員。RecordId： 0123456</td>
      <td>當記錄處於核准流程中，並且不是當前核准者或系統管理員的使用者嘗試編輯記錄時。</td>
      <td>
        <ul>
          <li>解決Salesforce組織中該記錄的未決核准流程。</li>
          <li>從中排除Marketo Measure專用使用者 <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">自訂驗證規則</a>.
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>FIELD_FILTER_VALIDATION_EXCEPTION</td>
      <td>Crm匯出期間發生錯誤： FIELD_FILTER_VALIDATION_EXCEPTION ：實體型別「銷售機會」： CRM錯誤碼： FIELD_FILTER_VALIDATION_EXCEPTION，欄位： User__C， CRM ErrorMessage：值不存在或不符合篩選條件。 請選取角色為「Account Executive， Inside Sales」的使用者；記錄ID：0123456</td>
      <td>已修改的記錄不再滿足物件上定義的查閱篩選器。</td>
      <td>檢查Marketo Measure嘗試修改的物件上的篩選器。 另請參閱 <a href="https://help.salesforce.com/s/articleView?id=000384756&amp;type=1">此Salesforce文章</a> 以瞭解如何檢查物件上的濾鏡。</td>
    </tr>
    <tr>
      <td>FIELD_INTEGRITY_EXCEPTION</td>
      <td>在Crm匯出期間發生錯誤： FIELD_INTEGRITY_EXCEPTION ：實體型別'Lead'： CRM ErrorCode： FIELD_INTEGRITY_EXCEPTION，欄位：國家/地區， CRM ErrorMessage：此國家/地區發生問題，即使它看起來可能正確。 請從有效國家/地區清單中選取國家/地區。：國家/地區，記錄ID：0123456</td>
      <td>預期的記錄型別不符。</td>
      <td>這種情況最常見的原因是未遵循Salesforce組織中設定的州/國家/地區命名標準，因為「州/國家」欄位已標準化，僅接受某些挑選清單值。 若要解決此問題，您可以：
        <ul>
          <li>更新記錄，以遵循組織對該欄位的接受值。 請連絡您的SFDC管理員以取得接受的值清單。</li>
          <li><a href="https://help.salesforce.com/s/articleView?id=sf.admin_state_country_picklist_enable.htm&amp;type=5">停用州/國家/地區選擇清單</a>.
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>INACTIVE_OWNER_OR_USER</td>
      <td>在Crm匯出期間發生錯誤： INACTIVE_OWNER_OR_USER ：實體型別「連絡人」： CRM錯誤碼： INACTIVE_OWNER_OR_USER， CRM錯誤訊息：以非作用中使用者[1234]作為連絡人執行操作，記錄識別碼： 0123456</td>
      <td>Marketo Measure缺少「以非作用中擁有者更新記錄」許可權。</td>
      <td>授予Marketo Measure "<a href="https://help.salesforce.com/s/articleView?id=000386699&amp;type=1">更新非作用中擁有者的記錄</a>「許可權。</td>
    </tr>
    <tr>
      <td>UNFFECTED_ACCESS_OR_READONLY</td>
      <td>Crm匯出期間發生錯誤： UNSUPPORTED_ACCESS_OR_READONLY ：實體型別「Account」： CRM錯誤碼： UNSUPPORTED_ACCESS_OR_READONLY， CRM ErrorMessage：物件識別碼的存取許可權不足：[123]，記錄識別碼： 456</td>
      <td>Marketo Measure缺少物件/欄位的許可權，或物件為唯讀。</td>
      <td>請參閱以下內容 <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Experience League文章</a> 以取得Marketo Measure所需許可權的指引。</td>
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
      <td>MISSING_BIZIBLE_CUSTOM_FIELDS_PERMISSIONS</td>
      <td>Crm匯出期間發生錯誤： MISSING_BIZIBLE_CUSTOM_FIELDS_PERMISSIONS ：實體型別「Campaign」： CRM錯誤碼： INVALID_FIELD_FOR_INSERT_UPDATE，欄位： bizible2__UniqueId__c， CRM錯誤訊息：無法建立/更新欄位： bizible2__UniqueId__c。請檢查此欄位的安全性設定，並確認您的設定檔或許可權集已讀取/寫入。</td>
      <td>Marketo Measure缺少bizible欄位的許可權。</td>
      <td>我們要求所有首碼為「bizible2__」的欄位具有讀取和寫入許可權。 您可以找到這些欄位的完整清單 <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">本文章</a>.</td>
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
      <td>MISSING_RECORD_OBJECT_PERMISSIONS</td>
      <td>Crm匯出期間發生錯誤： MISSING_RECORD_OBJECT_PERMISSIONS ：實體型別'bizible2__Bizible_Touchpoint__c'： CRM錯誤碼： INFIRMED_ACCESS_ON_CROSS_REFERENCE_ENTITY，欄位：帳戶， CRM ErrorMessage：存取許可權不足，無法存取互動參照ID： 0123456</td>
      <td>Marketo Measure缺少許可權。</td>
      <td>此錯誤有幾個特定於Salesforce組織的原因。 以下是幾個可解決此問題的常見疑難排解步驟：
        <ul>
          <li>檢閱每個所需的全部許可權 <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">物件與欄位</a>.</li>
          <li>從中排除Marketo Measure專用使用者 <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">自訂驗證規則</a>.</li>
          <li>授予Marketo Measure »<a href="https://developer.salesforce.com/docs/atlas.en-us.securityImplGuide.meta/securityImplGuide/users_profiles_view_all_mod_all.htm">全部修改</a>「許可權。</li>
        </ul>
      </td>
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
      <td>RECORD_NON-COMPLIANT_WITH_VALIDATION_RULES</td>
      <td>在Crm匯出期間發生錯誤： RECORD_NON-COMPLIANT_WITH_VALIDATION_RULES ：實體型別'Lead'： CRM錯誤碼： FIELD_CUSTOM_VALIDATION_EXCEPTION，欄位： Lead_Status_Reason__c， CRM ErrorMessage：您必須選取潛在客戶狀態原因，記錄識別碼： 0123456</td>
      <td>要更新的記錄不符合Salesforce組織中設定的驗證規則。</td>
      <td>從中排除Marketo Measure專用使用者 <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">自訂驗證規則</a>.
      <p>
      更新您的 <a href="https://help.salesforce.com/s/articleView?id=sf.fields_about_field_validation.htm&amp;type=5">驗證規則</a>.</td>
    </tr>
    <tr>
      <td>RESTRICT_PICKLIST_VALUES_ENABLED</td>
      <td>Crm匯出期間發生錯誤： RESTRICT_PICKLIST_VALUES_ENABLED ：實體型別'Campaign'： CRM錯誤碼： INVALID_OR_NULL_FOR_RESTRICTED_PICKLIST，欄位： Aries_of_Interest__c， CRM ErrorMessage：受限挑選清單欄位的值錯誤：未知</td>
      <td>當在挑選清單欄位的設定中啟用「將挑選清單限製為值集中定義的值」時，或插入欄位中的值在物件的記錄型別中無法使用。</td>
      <td>停用Salesforce組織中的限制選取清單設定。
          <p>
          從中排除Marketo Measure專用使用者 <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">自訂驗證規則</a>.
      </td>
    </tr>
    <tr>
      <td>REQUIRED_FIELD_MISSING</td>
      <td>Crm匯出期間發生錯誤： MISSING_REQUIRED_FIELD ：實體型別「Lead」： CRM錯誤碼： REQUIRED_FIELD_MISSING，欄位： Product_Type__c， CRM ErrorMessage：缺少必要欄位：[Product_Type__c]，RecordId： 0123456</td>
      <td>當驗證規則指定物件上需要欄位時。</td>
      <td>從中排除Marketo Measure專用使用者 <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">自訂驗證規則</a>.
      </td>
    </tr>
    <tr>
      <td>未知的例外狀況</td>
      <td>Crm匯出期間發生錯誤： UNKNOWN_EXCEPTION ：實體型別'Contact'： CRM ErrorCode： UNKNOWN_EXCEPTION， CRM ErrorMessage：入口網站使用者不能擁有合作夥伴帳戶，RecordId： 0123456</td>
      <td>Salesforce中發生未處理的例外狀況。</td>
      <td>如果問題仍然存在，請向Salesforce提出案例，並複製錯誤訊息中的數值。</td>
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
