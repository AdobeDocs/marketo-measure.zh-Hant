---
description: '[!DNL Salesforce] 套件合併 —  [!DNL Marketo Measure]  — 產品檔案'
title: '''[!DNL Salesforce] 封裝合併'
exl-id: f1bd5dcb-d021-4140-b6b9-cdb40e566c4b
source-git-commit: dd3795288b1d579b078a32c78c9f08fd67a5f0e1
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 0%

---

# [!DNL Salesforce] 套件合併 {#salesforce-package-consolidation}

我們很高興宣佈即將對Marketo Measure Salesforce套件進行變更。 為了改善使用者體驗並簡化使用量，我們將所有現有套件整合為單一、完整的套件。

## 套件淘汰 {#package-retirement}

合併後，目前的V1、V2_EXT、V2_Security及所有報表套裝軟體將於2023年8月之後淘汰。 如果您已安裝V2套件，則必須將其更新至新的整合版本。

## 新的整合套件 {#new-consolidated-package}

新的整合V2套件整合了先前套件中的所有功能，提供改良的使用者體驗。 此更新的套件可讓您更有效地追蹤行銷和銷售績效，並可更深入地瞭解客戶行為。

我們已新增兩個新欄位來增強您的報告功能：

* form_name：現在可在BT/BAT物件中使用，此欄位可讓使用者根據表單名稱建立報表。
* user_touchpoint_id：此欄位可讓使用者建立具有不重複使用者接觸點計數的報告。

## 支援與轉換 {#support-and-transition}

我們瞭解這項變更可能需要調整，並致力於在整個過程中為您提供支援。 我們的 [支援團隊](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} 可隨時回答任何問題，並協助確保順利轉換至新的整合套件。

## 必要動作 {#retired-actions}

* 如果您已安裝V2套件，則必須將其更新至新的整合版本。
* 如果您有來自任何報告套件的報告或儀表板，則可以輕鬆地重新建立它們，而無需進行任何修改，因為使用的所有欄位都存在於合併的套件中。
* 如果您有使用V2_EXT套件中欄位的報表，您可以透過下列步驟在整合的套件中重新建立它們：
   * V2_EXT欄位中的所有資料都可在接觸點欄位中使用，因此您可以修改報表，透過在接觸點位置新增篩選器來從對應的V2接觸點欄位擷取資料。
   * 使用包含「外聯」文字的廣告內容FT擷取所有潛在客戶的範例報告。
      * V2_EXT查詢：
         * bizible2_ext__Ad_Content_FT__c包含外聯

![](assets/package-consolidation-1.png)

* 整合套件中的對應查詢：
   * bizible2__Touchpoint_Position__c包含FT和
   * bizible2__Ad_Content__c包含外聯

![](assets/salesforce-package-consolidation-2.png)

## 常見問題集 {#faq}

**合併的套件會與我現有套件中的欄位衝突嗎？**

在安裝整合套件之前，您不需要解除安裝套件。 欄位中不會發生衝突，因為它們將位於不同的名稱空間。

**如何從目前的套件回填資料？**

您可以建立票證 [具有支援](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} 用於回填和重新處理BT/BAT資料，以填入接觸點ID和表單ID欄位。

**整合封裝中是否有V1和V2_EXT封裝中的欄位？**

是. 整合的套件將包含V1中的相同欄位，並透過「接觸點」欄位進一步劃分物件和V2_EXT欄位。

**使用V2_EXT欄位的報表可以在整合的封裝中重新建立嗎？**

是. 請依照以下檔案中的步驟操作： [必要動作](#retired-actions) 區段。
