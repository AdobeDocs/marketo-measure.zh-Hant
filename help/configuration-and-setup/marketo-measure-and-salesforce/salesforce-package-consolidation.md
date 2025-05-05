---
description: '[!DNL Salesforce]封裝合併 —  [!DNL Marketo Measure]'
title: '[!DNL Salesforce]封裝合併'
exl-id: ae559f5f-91bf-4504-9d5a-af47f95ca01f
feature: Salesforce
source-git-commit: 518a984b0d8d640290bd9b637221fcdc0948e5b9
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 1%

---

# [!DNL Salesforce]封裝合併 {#salesforce-package-consolidation}

為了改善使用者體驗並簡化使用流程，現有套件正在編譯為單一、完整的套件。

## 封裝淘汰 {#package-retirement}

由於此合併，目前的V1、V2_EXT、V2_Security及所有報表套裝軟體將於2023年8月之後淘汰。 如果您已安裝V2套件，則必須將其更新至新的整合版本。

## 新的整合套件 {#new-consolidated-package}

新的整合V2套件整合了先前套件中的所有功能，提供改良的使用者體驗。 此更新的套件可讓您更有效地追蹤行銷和銷售績效，並可更深入地瞭解客戶行為。

有兩個新欄位可增強您的報告功能：

* form_name：此欄位現在可在BT/BAT物件中使用，可讓使用者根據表單名稱建立報表。
* user_touchpoint_id：此欄位可讓使用者建立具有不重複使用者接觸點計數( Salesforce中的`bizible2__User_Touchpoint_V2__c`)的報告。

## 支援與轉換 {#support-and-transition}

[支援團隊](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}可以回答任何問題，並協助確保順利轉換至新的整合套件。

## 必要的動作 {#retired-actions}

* 如果您已安裝V2套件，則必須將其更新至新的整合版本。
* 如果您有來自任何報告套件的報告或儀表板，則可以輕鬆地重新建立它們，而無需進行任何修改，因為所有欄位都存在於合併套件中。
* 如果您有使用V2_EXT封裝中的欄位的報告，可以透過下列步驟在合併封裝中重新建立它們：
   * V2_EXT欄位中的所有資料都可在接觸點欄位中使用，因此您可以修改報表，透過在接觸點位置新增篩選器來從對應的V2接觸點欄位擷取資料。
   * 範例報告會擷取廣告內容FT包含「外聯」文字的所有銷售機會。
      * V2_EXT查詢：
         * bizible2_ext__Ad_Content_FT__c包含外聯

![](assets/package-consolidation-1.png)

* 整合封裝中的對應查詢：
   * bizible2__Touchpoint_Position__c包含FT AND
   * bizible2__Ad_Content__c包含外聯

![](assets/salesforce-package-consolidation-2.png)

## 常見問題集 {#faq}

**合併封裝會與我現有封裝中的欄位衝突嗎？**

在安裝整合套件之前，您不需要解除安裝套件。 欄位不會發生衝突，因為它們位於不同的名稱空間。

**如何從目前的套件回填資料？**

您可以填寫支援票證[&#128279;](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}以回填和重新處理BT/BAT資料，以填寫接觸點ID和表單ID欄位。

**V1和V2_EXT封裝中的欄位是否可以在整合封裝中使用？**

可以。整合套件包含的V1欄位與透過「接觸點」欄位的V2_EXT欄位與物件進一步劃分的欄位相同。

**使用V2_EXT欄位的報告可以在合併封裝中重新建立嗎？**

可以。請依照[必要動作](#retired-actions)區段中的步驟操作。
