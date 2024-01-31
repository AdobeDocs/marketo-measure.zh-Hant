---
description: 『[!DNL Marketo Measure] 終極資料完整性需求 —  [!DNL Marketo Measure]  — 產品檔案'
title: 『[!DNL Marketo Measure] 終極資料完整性要求
feature: Integration, Tracking, Attribution
exl-id: 8ad001d0-e9fe-46f5-b808-d6203a55a229
source-git-commit: 23890f24412e234f9ab7c08b684b6064eac5d0ed
workflow-type: tm+mt
source-wordcount: '1493'
ht-degree: 17%

---

# [!DNL Marketo Measure] 終極資料完整性需求 {#marketo-measure-ultimate-data-integrity-requirement}

[!DNL Marketo Measure] 驗證傳入的AEP資料集，確保資料充足且一致，以實現歸因。 若未符合資料完整性要求，資料集將會遭到 [!DNL Marketo Measure] 系統。 本檔案詳細說明資料完整性需求、提供資料檢查的查詢範例，並建議具有null值的必填欄位的解決方案。

## 實體物件 {#entity-object}

<table style="table-layout:auto">
  <tr>
    <th>XDM類別</th>
    <th>xdm欄位群組</th>
    <th>XDM路徑</th>
    <th>XDM型別</th>
    <th>資料來源欄位</th>
    <th>必填？</th>
    <th>附註</th>
  </tr>
  <tbody>
    <tr>
      <td colspan="7"><strong>帳戶</strong> (Marketo的Salesforce、公司和/或具名帳戶的帳戶)</td>
    </tr>
    <tr>
      <td rowspan="6">XDM商業帳戶</td>
      <td></td>
      <td>accountKey.sourceKey</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 123@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceID</td>
      <td>字串</td>
      <td>ID</td>
      <td>是</td>
      <td>例如 — 123</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceInstanceID</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceType</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>日期時間</td>
      <td>CreatedDate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>日期時間</td>
      <td>Modifieddate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>XDM商業帳戶細節</td>
      <td>帳戶名稱</td>
      <td>字串</td>
      <td>名稱</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong>Campaign</strong> (適用於Salesforce的Campaign、適用於Marketo的方案)</td>
    </tr>
    <tr>
      <td rowspan="8">XDM商業活動</td>
      <td></td>
      <td>campaignKey.sourceKey</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceID</td>
      <td>字串</td>
      <td>ID</td>
      <td>是</td>
      <td>例如 — 55555</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceInstanceID</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceType</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>日期時間</td>
      <td>CreatedDate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>日期時間</td>
      <td>Modifieddate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>campaignName</td>
      <td>字串</td>
      <td>名稱</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>campaignType</td>
      <td>字串</td>
      <td>CampaignType</td>
      <td>否</td>
      <td>用於頻道對應</td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="5">XDM商業活動細節</td>
      <td>channelname</td>
      <td>字串</td>
      <td>頻道名稱</td>
      <td>否</td>
      <td>用於頻道對應</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignStartDate</td>
      <td>日期時間</td>
      <td>開始日期</td>
      <td>否</td>
      <td>針對行銷活動成本</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignEndDate</td>
      <td>日期時間</td>
      <td>結束日期</td>
      <td>否</td>
      <td>針對行銷活動成本</td>
    </tr>
    <tr>
      <td></td>
      <td>actualCost.amount</td>
      <td>數字</td>
      <td>成本</td>
      <td>否</td>
      <td>針對行銷活動成本</td>
    </tr>
    <tr>
      <td></td>
      <td>actualCost.currencyCode</td>
      <td>
        <p>字串</p>
        <p>^[A-Z]{3}$</p>
      </td>
      <td>CurrencyIsoCode</td>
      <td>否</td>
      <td>針對行銷活動成本</td>
    </tr>
    <tr>
      <td colspan="7"><strong>促銷活動會員</strong> (Salesforce的Campaign會員、Marketo的計畫會員資格)</td>
    </tr>
    <tr>
      <td rowspan="14">XDM商業活動會員</td>
      <td></td>
      <td>campaignMemberKey.sourceKey</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 987654321@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignMemberKey.sourceID</td>
      <td>字串</td>
      <td>ID</td>
      <td>是</td>
      <td>例如 — 987654321</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignMemberKey.sourceInstanceID</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignMemberKey.sourceType</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>日期時間</td>
      <td>CreatedDate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>日期時間</td>
      <td>Modifieddate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceKey</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceID</td>
      <td>字串</td>
      <td>潛在客戶ID或聯絡人ID</td>
      <td>是</td>
      <td>
        <p>例如 — 333，根據資料來源表格，這有可能是銷售機會ID或聯絡人ID。</p>
        <p>潛在客戶或聯絡人的外部索引鍵</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceInstanceID</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceType</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceKey</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceID</td>
      <td>字串</td>
      <td>行銷活動ID</td>
      <td>是</td>
      <td>
        <p>例如 — 55555。</p>
        <p>Campaign的外部索引鍵</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceInstanceID</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceType</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="4">XDM商業活動會員細節</td>
      <td>b2b.personType</td>
      <td>字串</td>
      <td>「銷售機會」或「聯絡人」</td>
      <td>是</td>
      <td>根據資料來源表格，這應該設定為「銷售機會」或「聯絡人」。 建議在大部分使用案例中將它設為「聯絡」</td>
    </tr>
    <tr>
      <td></td>
      <td>memberstatus</td>
      <td>字串</td>
      <td>狀態</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>hasResponded</td>
      <td>布林值</td>
      <td>HasResponsed</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>firstRespondedDate</td>
      <td>日期時間</td>
      <td>FirstRespondedDate</td>
      <td>否</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong>個人</strong> (Salesforce、Marketo人員的聯絡人或銷售線索)</td>
    </tr>
    <tr>
      <td>XDM 設定檔</td>
      <td rowspan="11">XDM商業人士細節</td>
      <td>b2b.personKey.sourceKey</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personKey.sourceID</td>
      <td>字串</td>
      <td>ID</td>
      <td>是</td>
      <td>例如 — 333，根據資料來源表格，這有可能是銷售機會ID或聯絡人ID</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personKey.sourceInstanceID</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personKey.sourceType</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>workEmail.address</td>
      <td>
        <p>字串</p>
        <p>電子郵件</p>
      </td>
      <td>電子郵件</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personStatus</td>
      <td>字串</td>
      <td>狀態</td>
      <td><b><i>是（僅限潛在客戶個人型別）</i></b></td>
      <td>只有在b2b.personType為「銷售機會」時才需要</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>日期時間</td>
      <td>CreatedDate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>日期時間</td>
      <td>Modifieddate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.isConverted</td>
      <td>布林值</td>
      <td>IsConverted</td>
      <td><b><i>是（僅限潛在客戶個人型別）</i></b></td>
      <td>只有在b2b.personType為「銷售機會」時才需要</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personType</td>
      <td>字串</td>
      <td>「銷售機會」或「聯絡人」</td>
      <td>是</td>
      <td>根據資料來源表格，這應該設定為「銷售機會」或「聯絡人」。 建議在大部分使用案例中將它設為「聯絡」</td>
    </tr>
    <tr>
      <td></td>
      <td>extendedWorkDetails.jobTitle</td>
      <td>字串</td>
      <td></td>
      <td>否</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="4">XDM商業人士要素</td>
      <td>personComponents.sourceAccountKey.sourceKey</td>
      <td>字串</td>
      <td></td>
      <td>否</td>
      <td>
        <p>例如 — 123@999-abc-888.Marketo。</p>
        <p>sourceAccountKey欄位集僅對真正的連絡人記錄為「必要」，定義為連結至帳戶的人員記錄。 缺少它不會導致資料集遭到拒絕，但歸因結果將會關閉。</p>
        <p>personComponents是陣列，但Marketo Measure僅取用第一個元素personComponents[0]</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personComponents.sourceAccountKey.sourceID</td>
      <td>字串</td>
      <td>帳戶 ID</td>
      <td>否</td>
      <td>
        <p>例如 — 123。</p>
        <p>帳戶的外部索引鍵</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personComponents.sourceAccountKey.sourceInstanceID</td>
      <td>字串</td>
      <td></td>
      <td>否</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>personComponents.sourceAccountKey.sourceType</td>
      <td>字串</td>
      <td></td>
      <td>否</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td colspan="7"><strong>商機</strong> (Salesforce的機會、Marketo的機會)</td>
    </tr>
    <tr>
      <td rowspan="13">XDM商業機會</td>
      <td></td>
      <td>opportunityKey.sourceKey</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 77777@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceID</td>
      <td>字串</td>
      <td>ID</td>
      <td>是</td>
      <td>例如 — 77777</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceInstanceID</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceType</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>日期時間</td>
      <td>CreatedDate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>日期時間</td>
      <td>Modifieddate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceKey</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 123@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceID</td>
      <td>字串</td>
      <td>帳戶 ID</td>
      <td>是</td>
      <td>
        <p>例如 — 123。</p>
        <p>帳戶的外部索引鍵</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceInstanceID</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceType</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>機會名稱</td>
      <td>字串</td>
      <td>名稱</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunestage</td>
      <td>字串</td>
      <td>階段</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>機會型別</td>
      <td>字串</td>
      <td></td>
      <td>否</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="5">XDM商業機會詳細資料</td>
      <td>isWon</td>
      <td>布林值</td>
      <td>IsWon</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>isClosed</td>
      <td>布林值</td>
      <td>IsClosed</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>expectedCloseDate</td>
      <td>日期</td>
      <td>關閉日期</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityAmount.amount</td>
      <td>數字</td>
      <td>數量</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityAmount.currencyCode</td>
      <td>
        <p>字串</p>
        <p>^[A-Z]{3}$</p>
      </td>
      <td>CurrencyIsoCode</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong>機會聯絡人角色（只有在計畫使用機會聯絡人角色作為購買群組進行歸因時才需要）</strong></td>
    </tr>
    <tr>
      <td rowspan="16">XDM商業機會個人關係</td>
      <td></td>
      <td>personKey.sourceKey</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceID</td>
      <td>字串</td>
      <td>聯絡人ID</td>
      <td>是</td>
      <td>
        <p>例如 — 333。</p>
        <p>連絡人的外部索引鍵</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceInstanceID</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceType</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>isPrimary</td>
      <td>布林值</td>
      <td>主要的</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceKey</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 77777@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceID</td>
      <td>字串</td>
      <td>機會 ID</td>
      <td>是</td>
      <td>
        <p>例如 — 77777。</p>
        <p>機會的外部索引鍵</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceInstanceID</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceType</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityPersonKey.sourceKey</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 222222@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityPersonKey.sourceID</td>
      <td>字串</td>
      <td>ID</td>
      <td>是</td>
      <td>例如 — 222222</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityPersonKey.sourceInstanceID</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityPersonKey.sourceType</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>personRole</td>
      <td>字串</td>
      <td>角色</td>
      <td>否</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>日期時間</td>
      <td>CreatedDate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>日期時間</td>
      <td>Modifieddate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong>轉換率(僅在使用多種貨幣時需要；只能將一個轉換率資料集啟用至Marketo Measure)</strong></td>
    </tr>
    <tr>
      <td rowspan="7">轉換</td>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceKey</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 8888@0x012345.Salesforce</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceId</td>
      <td>字串</td>
      <td>ID</td>
      <td>是</td>
      <td>例如 — 8888</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceInstanceId</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 0x012345</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceType</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Salesforce</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>日期時間</td>
      <td>CreatedDate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>日期時間</td>
      <td>Modifieddate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>isDeleted</td>
      <td>布林值</td>
      <td></td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="5">幣別兌換率詳細資料</td>
      <td>conversionRate</td>
      <td>數字</td>
      <td>ConversionRate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>endDate</td>
      <td>日期</td>
      <td>NextStartDate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>startDate</td>
      <td>日期</td>
      <td>開始日期</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>sourceISOCode</td>
      <td>字串</td>
      <td>ISOCode</td>
      <td>是</td>
      <td>例如EUR</td>
    </tr>
    <tr>
      <td></td>
      <td>targetisocode</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>Marketo Measure中設定的預設貨幣代碼，例如USD</td>
    </tr>
  </tbody>
</table>

## ExperienceEvent {#experienceevent}

<table style="table-layout:auto">
  <tr>
    <th>XDM類別</th>
    <th>xdm欄位群組</th>
    <th>XDM路徑</th>
    <th>XDM型別</th>
    <th>資料來源欄位</th>
    <th>必填？</th>
    <th>附註</th>
  </tr>
  <tbody>
    <tr>
      <td colspan="7"><strong>活動</strong></td>
    </tr>
    <tr>
      <td rowspan="3">XDM ExperienceEvent</td>
      <td></td>
      <td>_id</td>
      <td>字串</td>
      <td>ID</td>
      <td>是</td>
      <td>是</td>
    </tr>
    <tr>
      <td></td>
      <td>eventtype</td>
      <td>字串</td>
      <td>活動型別</td>
      <td>是</td>
      <td>是</td>
    </tr>
    <tr>
      <td></td>
      <td>timestamp</td>
      <td>日期時間</td>
      <td>活動日期</td>
      <td>是</td>
      <td>是</td>
    </tr>
    <tr>
      <td></td>
      <td>個人識別碼</td>
      <td>personKey.sourceKey</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>personKey.sourceID</td>
      <td>字串</td>
      <td>潛在客戶ID或聯絡人ID</td>
      <td>是</td>
      <td>
        <p>例如 — 333，根據資料來源表格，這有可能是銷售機會ID或聯絡人ID。</p>
        <p>潛在客戶或聯絡人的外部索引鍵</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>personKey.sourceInstanceID</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>personKey.sourceType</td>
      <td>字串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>新增至行銷活動</td>
      <td>leadOperation.addToCampaign.campaignKey.sourceKey</td>
      <td>字串</td>
      <td></td>
      <td>是（僅適用於leadOperation.addToCampaign型別）</td>
      <td>例如 — 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.addToCampaign.campaignKey.sourceId</td>
      <td>字串</td>
      <td>行銷活動ID</td>
      <td>是（僅適用於leadOperation.addToCampaign型別）</td>
      <td>
        <p>例如 — 55555。</p>
        <p>Campaign的外部索引鍵</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.addToCampaign.campaignKey.sourceInstanceId</td>
      <td>字串</td>
      <td></td>
      <td>是（僅適用於leadOperation.addToCampaign型別）</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.addToCampaign.campaignKey.sourceType</td>
      <td>字串</td>
      <td></td>
      <td>是（僅適用於leadOperation.addToCampaign型別）</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>促銷活動進度變更中的狀態</td>
      <td>leadOperation.campaignProgression.campaignKey.sourceKey</td>
      <td>字串</td>
      <td></td>
      <td>是（僅適用於leadOperation.campaignProgression型別）</td>
      <td>例如 — 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.campaignProgression.campaignKey.sourceId</td>
      <td>字串</td>
      <td>行銷活動ID</td>
      <td>是（僅適用於leadOperation.campaignProgression型別）</td>
      <td>
        <p>例如 — 55555。</p>
        <p>Campaign的外部索引鍵</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.campaignProgression.campaignKey.sourceInstanceId</td>
      <td>字串</td>
      <td></td>
      <td>是（僅適用於leadOperation.campaignProgression型別）</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.campaignProgression.campaignKey.sourceType</td>
      <td>字串</td>
      <td></td>
      <td>是（僅適用於leadOperation.campaignProgression型別）</td>
      <td>例如 — Marketo</td>
    </tr>
  </tbody>
</table>

## 支援的體驗事件型別 {#experienceevent-type-supported}

<table style="table-layout:auto">
  <tr>
    <th>事件型別</th>
    <th>XDM事件型別</th>
    <th>說明</th>
  </tr>
  <tbody>
    <tr>
      <td>新銷售機會</td>
      <td>leadOperation.newLead</td>
      <td>用於記錄新行銷線索的建立和詳細資訊</td>
    </tr>
    <tr>
      <td>轉換潛在客戶</td>
      <td>leadOperation.convertLead</td>
      <td>當行銷線索轉換為指派給銷售使用者的符合銷售條件的聯絡人時使用</td>
    </tr>
    <tr>
      <td>有趣的時刻</td>
      <td>leadOperation.interestingMoment</td>
      <td>用於追蹤潛在客戶的高價值活動</td>
    </tr>
    <tr>
      <td>填寫表單</td>
      <td>web.formFilledOut</td>
      <td>若有人填寫網頁上的表單時，可用於擷取詳細資訊</td>
    </tr>
    <tr>
      <td>取消訂閱電子郵件</td>
      <td>directMarketing.emailUnsubscribed</td>
      <td>若有人取消訂閱電子郵件時，可用於擷取詳細資訊</td>
    </tr>
    <tr>
      <td>開啟電子郵件</td>
      <td>directMarketing.emailOpened</td>
      <td>若有人開啟行銷電子郵件時，可用於擷取詳細資訊</td>
    </tr>
    <tr>
      <td>按一下電子郵件</td>
      <td>directMarketing.emailClicked</td>
      <td>若有人點選行銷電子郵件中的連結時，可用於擷取詳細資訊</td>
    </tr>
    <tr>
      <td>進度中的變更狀態</td>
      <td>leadOperation.statusInCampaignProgressionChanged</td>
      <td>若潛在客戶在促銷活動中的狀態改變時，可用於擷取詳細資訊</td>
    </tr>
    <tr>
      <td>新增至參與計畫（新增至Nurture）</td>
      <td>leadOperation.addToCampaign</td>
      <td>用於將個人新增至特定行銷活動。</td>
    </tr>
  </tbody>
</table>

上表不支援的事件型別使用「有趣的時刻」事件型別。 新增自訂欄位以指出子型別「有趣的時刻」。

## 資料檢查的查詢範例 {#query-examples-for-data-inspection}

以下是檢查AEP資料湖中擷取資料集的查詢範例清單。 若要對您的資料集使用這些資料集，請將下列查詢範例中的表格名稱取代為您實際的資料集表格名稱。

我們預期所有計數均為0。

對於personType欄位，我們預期只有「銷售機會」或「聯絡人」值，而且沒有null值。

對於所有「連絡人」個人記錄，我們預期會有「帳戶」外部索引鍵。

對於「銷售機會」人員記錄，「帳戶」外部索引鍵不存在且不是必要的。 如果您選擇將「銷售機會」人員記錄擷取為「聯絡人」人員記錄（建議使用），則不需要此類人員記錄上的「帳戶」外部索引鍵。

### XDM商業帳戶 {#xdm-business-account}

```
select 'account source id', count(*) from salesforce_account where accountKey.sourceId is null
union all
select 'account source type', count(*) from salesforce_account where accountKey.sourceType is null
union all
select 'account source instance id', count(*) from salesforce_account where accountKey.sourceInstanceId is null
union all
select 'account source key', count(*) from salesforce_account where accountKey.sourceKey is null
union all
select 'account name', count(*) from salesforce_account where accountName is null
union all
select 'created date', count(*) from salesforce_account where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_account where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM商業活動 {#xdm-business-campaign}

```
select 'campaign source id', count(*) from salesforce_campaign where campaignKey.sourceId is null
union all
select 'campaign source type', count(*) from salesforce_campaign where campaignKey.sourceType is null
union all
select 'campaign source instance id', count(*) from salesforce_campaign where campaignKey.sourceInstanceId is null
union all
select 'campaign source key', count(*) from salesforce_campaign where campaignKey.sourceKey is null
union all
select 'campaign name', count(*) from salesforce_campaign where campaignName is null
union all
select 'created date', count(*) from salesforce_campaign where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_campaign where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM商業活動會員 {#xdm-business-campaign-member}

```
select 'campaign member source id', count(*) from salesforce_campaign_member where campaignMemberKey.sourceId is null
union all
select 'campaign member source type', count(*) from salesforce_campaign_member where campaignMemberKey.sourceType is null
union all
select 'campaign member source instance id', count(*) from salesforce_campaign_member where campaignMemberKey.sourceInstanceId is null
union all
select 'campaign member source key', count(*) from salesforce_campaign_member where campaignMemberKey.sourceKey is null
union all
select 'campaign source id', count(*) from salesforce_campaign_member where campaignKey.sourceId is null
union all
select 'campaign source type', count(*) from salesforce_campaign_member where campaignKey.sourceType is null
union all
select 'campaign source instance id', count(*) from salesforce_campaign_member where campaignKey.sourceInstanceId is null
union all
select 'campaign source key', count(*) from salesforce_campaign_member where campaignKey.sourceKey is null
union all
select 'person source id', count(*) from salesforce_campaign_member where personKey.sourceId is null
union all
select 'person source type', count(*) from salesforce_campaign_member where personKey.sourceType is null
union all
select 'person source instance id', count(*) from salesforce_campaign_member where personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from salesforce_campaign_member where personKey.sourceKey is null
union all
select distinct 'person type', b2b.personType from salesforce_campaign_member
union all
select 'member status', count(*) from salesforce_campaign_member where memberStatus is null
union all
select 'has responded', count(*) from salesforce_campaign_member where hasResponded is null
union all
select 'created date', count(*) from salesforce_campaign_member where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_campaign_member where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM業務人員 {#xdm-business-person}

```
select 'person source id', count(*) from marketo_person where b2b.personKey.sourceId is null
union all
select 'person source type', count(*) from marketo_person where b2b.personKey.sourceType is null
union all
select 'person source instance id', count(*) from marketo_person where b2b.personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from marketo_person where b2b.personKey.sourceKey is null
union all
select 'email', count(*) from marketo_person where workEmail.address is null
union all
select 'Lead - person status', count(*) from marketo_person where b2b.personType = 'Lead' and b2b.personStatus is null
union all
select 'Lead - is converted', count(*) from marketo_person where b2b.personType = 'Lead' and b2b.isConverted is null
union all
select distinct 'person type', b2b.personType from marketo_person
union all
select 'created date', count(*) from marketo_person where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from marketo_person where extSourceSystemAudit.lastUpdatedDate is null;
```

```
select 'person source id', count(*) from salesforce_contact where b2b.personKey.sourceId is null
union all
select 'person source type', count(*) from salesforce_contact where b2b.personKey.sourceType is null
union all
select 'person source instance id', count(*) from salesforce_contact where b2b.personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from salesforce_contact where b2b.personKey.sourceKey is null
union all
select 'email', count(*) from salesforce_contact where workEmail.address is null
union all
select 'Lead - person status', count(*) from salesforce_contact where b2b.personType = 'Lead' and b2b.personStatus is null
union all
select 'Lead - is converted', count(*) from salesforce_contact where b2b.personType = 'Lead' and b2b.isConverted is null
union all
select distinct 'person type', b2b.personType from salesforce_contact
union all
select 'account source id', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceId is null
union all
select 'account source type', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceType is null
union all
select 'account source instance id', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceInstanceId is null
union all
select 'account source key', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceKey is null
union all
select 'created date', count(*) from salesforce_contact where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_contact where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM商業機會 {#xdm-business-opportunity}

```
select 'opportunity source id', count(*) from salesforce_opportunity where opportunityKey.sourceId is null
union all
select 'opportunity source type', count(*) from salesforce_opportunity where opportunityKey.sourceType is null
union all
select 'opportunity source instance id', count(*) from salesforce_opportunity where opportunityKey.sourceInstanceId is null
union all
select 'opportunity source key', count(*) from salesforce_opportunity where opportunityKey.sourceKey is null
union all
select 'account source id', count(*) from salesforce_opportunity where accountKey.sourceId is null
union all
select 'account source type', count(*) from salesforce_opportunity where accountKey.sourceType is null
union all
select 'account source instance id', count(*) from salesforce_opportunity where accountKey.sourceInstanceId is null
union all
select 'account source key', count(*) from salesforce_opportunity where accountKey.sourceKey is null
union all
select 'opportunity name', count(*) from salesforce_opportunity where opportunityName is null
union all
select 'opportunity stage', count(*) from salesforce_opportunity where opportunityStage is null
union all
select 'is won', count(*) from salesforce_opportunity where isWon is null
union all
select 'is closed', count(*) from salesforce_opportunity where isClosed is null
union all
select 'expected close date', count(*) from salesforce_opportunity where expectedCloseDate is null
union all
select 'opportunity amount', count(*) from salesforce_opportunity where opportunityAmount.amount is null
union all
select 'currency code', count(*) from salesforce_opportunity where opportunityAmount.currencyCode is null
union all
select 'created date', count(*) from salesforce_opportunity where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_opportunity where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM ExperienceEvent {#xdm-experienceevent}

```
select 'id', count(*) from marketo_activity where _id is null
union all
select 'event type', count(*) from marketo_activity where eventType is null
union all
select 'timestamp', count(*) from marketo_activity where timestamp is null
union all
select 'person source id', count(*) from marketo_activity where personKey.sourceId is null
union all
select 'person source type', count(*) from marketo_activity where personKey.sourceType is null
union all
select 'person source instance id', count(*) from marketo_activity where personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from marketo_activity where personKey.sourceKey is null
union all
select 'addToCampaign campaign id', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceId is null
union all
select 'addToCampaign campaign type', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceType is null
union all
select 'addToCampaign campaign instance id', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceInstanceId is null
union all
select 'addToCampaign campaign key', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceKey is null
union all
select 'statusInCampaignProgressionChanged campaign id', count(*) from marketo_activity where eventType = 'leadOperation.campaignProgression.campaignKey.sourceKey' and leadOperation.campaignProgression.campaignKey.sourceId is null
union all
select 'statusInCampaignProgressionChanged campaign type', count(*) from marketo_activity where eventType = 'leadOperation.campaignProgression.campaignKey.sourceKey' and leadOperation.campaignProgression.campaignKey.sourceType is null
union all
select 'statusInCampaignProgressionChanged campaign instance id', count(*) from marketo_activity where eventType = 'leadOperation.campaignProgression.campaignKey.sourceKey' and leadOperation.campaignProgression.campaignKey.sourceInstanceId is null
union all
select 'statusInCampaignProgressionChanged campaign key', count(*) from marketo_activity where eventType = 'leadOperation.campaignProgression.campaignKey.sourceKey' and leadOperation.campaignProgression.campaignKey.sourceKey is null;
```

```
select 'id', count(*) from salesforce_task where _id is null
union all
select 'event type', count(*) from salesforce_task where eventType is null
union all
select 'timestamp', count(*) from salesforce_task where timestamp is null
union all
select 'person source id', count(*) from salesforce_task where personKey.sourceId is null
union all
select 'person source type', count(*) from salesforce_task where personKey.sourceType is null
union all
select 'person source instance id', count(*) from salesforce_task where personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from salesforce_task where personKey.sourceKey is null;
```

### 轉換 {#conversion}

```
select 'conversion rate', count(*) from currency_conversion_rate where conversionRate is null
union all
select 'end date', count(*) from currency_conversion_rate where endDate is null
union all
select 'start date', count(*) from currency_conversion_rate where startDate is null
union all
select 'source ISO Code', count(*) from currency_conversion_rate where sourceISOCode is null
union all
select 'target ISO Code', count(*) from currency_conversion_rate where targetISOCode is null
union all
select 'source id', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceId is null
union all
select 'source type', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceType is null
union all
select 'source instance id', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceInstanceId is null
union all
select 'source key', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceKey is null
union all
select 'created date', count(*) from salesforce_contact where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_contact where extSourceSystemAudit.lastUpdatedDate is null;
```

## 具有NULL值之必要欄位的建議解決方案 {#recommended-solution-for-required-fields-with-a-null-value}

我們建議在欄位對應中使用計算欄位，以將欄位預設為非NULL值。 以下是兩個範例：

* 如果某些機會記錄的opportunityName為Null，請在欄位對應中建立並使用下列計算欄位
   * `iif(name != null && trim(name) != "", name, "Unknown")`

* 如果部分experienceevent記錄的leadOperation.campaignProgression.campaignID為Null，請在欄位對應中建立並使用以下計算欄位
   * `iif(leadOperation.campaignProgression.campaignID != null && leadOperation.campaignProgression.campaignID != "" , to_object("sourceType", "Marketo", "sourceInstanceID", "123-abc-321", "sourceID", leadOperation.campaignProgression.campaignID, "sourceKey", concat(leadOperation.campaignProgression.campaignID,"@123-abc-321.Marketo")), iif(eventType == "leadOperation.statusInCampaignProgressionChanged", to_object("sourceType", "Marketo", "sourceInstanceID", "123-abc-321", "sourceID", "Unknown", "sourceKey", "Unknown@123-abc-321.Marketo"), null))`
