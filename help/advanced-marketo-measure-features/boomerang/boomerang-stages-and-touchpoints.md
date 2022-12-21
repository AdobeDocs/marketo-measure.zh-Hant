---
unique-page-id: 18874558
description: 自美蘭舞台和接觸點 —  [!DNL Marketo Measure]  — 產品檔案
title: 自食其果級和接觸點
exl-id: e58169a3-3637-4878-8a0e-1920d873ff52
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 0%

---

# 自食其果級和接觸點 {#boomerang-stages-and-touchpoints}

[!DNL Marketo Measure] 已發佈我們的Boomerang Stage功能！ 建立Boomerang Stage功能是為了讓您更清楚地了解客戶的歷程 [!DNL Marketo Measure] 銷售週期較長的客戶。 此功能可讓行銷人員為Opportunity歷程中發生的所有階段轉變建立接觸點，例如，當聯繫MQL，然後移至SAL，然後回復到MQL階段時。 當聯繫人「重新進入MQL階段」或「重新進入MQL階段」時，我們將MQL視為「回歸階段」。 Boomerang Stage功能與 [!DNL Marketo Measure] 自訂階段。

## 此功能的功能 {#what-this-feature-does}

* 為在機會歷程中發生的所有階段轉變建立「回歸」接觸點
* 追蹤任何自訂階段之間的重複轉變(例如 當聯繫MQL時，移至SAL，然後返回MQL階段)
* 允許您指定希望包含在Opportunity中的階段轉變的數量和集(例如 前10個MQL或前5個MQL)
* 如果您是「自訂模型」使用者，便能決定要分配給這些各個階段的歸因加權和百分比評分(例如 將歸因權重指定給第一個或最後一個MQL發生次數，或將歸因加權平均分配給所有發生次數)

>[!NOTE]
>
>[如何設定Boomerang階段的說明](/help/advanced-marketo-measure-features/boomerang/setting-up-boomerang-stages.md).

## 在您的CRM中，自動回歸階段和接觸點看起來是什麼樣子 {#what-boomerang-stages-and-touchpoints-look-like-in-your-crm}

若沒有回歸階段（「之前」），您只會看到與銷售機會/聯繫人記錄相關聯的最新MQL或最新的SQL接觸點。

![](assets/1.png)

使用Boomerang階段和接觸點，您將會看到每個階段轉變發生的接觸點。 這些自食其果接觸點的命名慣例如下：

**[階段名稱]-00。**

以下範例為例，這 [!DNL Marketo Measure] 帳戶已在其自動回歸階段中包括MQL和SQL，並且已選擇在每個階段中顯示2個自動回歸接觸點。

![](assets/2.png)

**MQL-01** 是第一個MQL階段轉變。

接觸點位置中的數值將表示階段轉變發生的順序。 最後一個自食其果接觸點會加註為：

MQL-02 **（最後）**

## Boomerang階段如何更改您的現有資料 {#how-boomerang-stages-change-your-existing-data}

Boomerang階段將產生影響：

**依管道歸因**

* 自 [!DNL Boomerang Stages] 會建立更多接觸點，這將變更歸因在資料中目前存在的接觸點之間的分佈方式。 因此，這可能表示收入值會在行銷管道之間轉移。 在實施前，請考慮這一點 [!DNL Boomerang stages]，或請連絡您的帳戶管理員以取得詳細資訊。

**使用「等於」的任何報表 [接觸點位置]&quot;**

* Boomerang階段會將新的接觸點位置引入您的資料。 [!DNL Marketo Measure] 會變更接觸點位置的格式，以包含階段的發生，例如「MQL-01」或「MQL-05（最後）」。 使用此範例時，回歸階段會影響任何使用「接觸點位置等於MQL」的報表。 若要調整這些報表，篩選器應改用「包含」運算子。

## 常見問題集 {#faq}

**我的歸因模型中可以包含多少個回歸階段？**

最多可選擇15個階段。

**問：每個階段可以有多少個「自食其果」接觸點？**

每個階段最多可選取10個自飛接觸點。

**問：為什麼我們每階段只能有10次自食其果？**

[!DNL Marketo Measure] 必須限制階段數，才能控制處理時間。 如果您選擇將所有15個回飛舞台納入歸因模型，並將每個舞台10個回飛觸控點納入其中，則每個潛在接觸/聯絡記錄可能會有超過150個接觸點。

**問：我有Data Warehouse。 我是否獲得了所有資料，還是Boomerang Stages上限也適用於我？**

上限將套用至Data Warehouse和CRM，因為此處理限制 [!DNL Marketo Measure] 已就緒。 Data Warehouse也會看到每個階段10個接觸點的限制。

**問：將Boomerang階段與自訂模型搭配使用有何好處？**

使用 [!UICONTROL Boomerang] 具有自訂模型的階段可讓您將歸因加權指派給 [!UICONTROL Boomerang] 接觸點，將收入評分分配給這些階段。

若沒有自訂模型， [!DNL Marketo Measure] 會為每個boomerang和階段轉變建立接觸點，但不會將任何歸因評分指派給這些接觸點。 唯一可接收歸因評分的回歸接觸點是表單提交接觸點。 沒有自訂模型， [!DNL Boomerang] 接觸點會視為與「中繼接觸」相同，並因此獲得歸因評分。
