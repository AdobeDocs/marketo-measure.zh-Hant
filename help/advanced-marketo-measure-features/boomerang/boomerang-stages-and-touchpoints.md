---
unique-page-id: 18874558
description: 回力郎舞台和接觸點 —  [!DNL Marketo Measure]
title: 回味郎舞台和接觸點
exl-id: e58169a3-3637-4878-8a0e-1920d873ff52
feature: Boomerang, Touchpoints
source-git-commit: ea113b02b910fbc894311200aff83286636d4b32
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 0%

---

# 回味郎舞台和接觸點 {#boomerang-stages-and-touchpoints}

>[!AVAILABILITY]
>
>Boomerang功能僅針對2級和3級客戶啟用。 若要要求更高的客戶層級，請聯絡Adobe客戶團隊（您的客戶經理）。

[!DNL Marketo Measure] 已發行迴旋舞台功能！ 建立迴旋舞台功能是為了更清楚地顯示客戶的歷程 [!DNL Marketo Measure] 銷售週期長的客戶。 此功能可讓行銷人員為Opportunity歷程中發生的所有階段轉變建立接觸點（例如當聯絡MQL時），然後移至SAL，再移回MQL階段。 當連絡人「重新進入MQL階段」或「重新進入MQL的階段」時，MQL會被視為回圈階段。 「迴旋舞台」功能可與 [!DNL Marketo Measure] 自訂階段。

## 此功能的功能 {#what-this-feature-does}

* 為商機歷程中發生的所有階段轉變建立「迴旋鏢」接觸點
* 追蹤任何自訂階段之間的重複轉換(例如： 當Contact MQL移至SAL，然後返回MQL階段時)
* 可讓您指定要在機會中包含多少以及哪一組階段轉變(例如： 前10個MQL或後5個MQL)
* 如果您是「自訂模型」使用者，便能決定歸因加權和要分配至每個階段的評分百分比(例如： 將歸因權重指定給第一個或最後一個MQL發生次數，或在所有發生次數之間平均分配歸因權重)

>[!NOTE]
>
>[關於如何設定迴旋式舞台的說明](/help/advanced-marketo-measure-features/boomerang/setting-up-boomerang-stages.md).

## Boomerang階段和接觸點在您的CRM中看起來是什麼樣子 {#what-boomerang-stages-and-touchpoints-look-like-in-your-crm}

如果沒有Boomerang階段（「之前」），您只會看到與Lead/Contact記錄相關聯的最新MQL或最新SQL接觸點。

![](assets/1.png)

使用Boomerang階段和接觸點，您會看到每個階段轉換中發生的接觸點。 這些迴旋接觸點的命名慣例如下：

**[階段名稱]-00。**

以下列範例說明 [!DNL Marketo Measure] 帳戶已將MQL和SQL納入其回溯站階段，並已選擇在每個階段顯示2個回溯站接觸點。

![](assets/2.png)

**MQL-01** 是第一個MQL階段轉換。

接觸點位置中的數值表示階段轉換發生的順序。 最後一個回溯點要加上戳記為：

MQL-02 **（上次）**

## Boomerang階段如何變更您現有的資料 {#how-boomerang-stages-change-your-existing-data}

回零階段影響：

**依據管道的歸因**

* 從 [!DNL Boomerang Stages] 會建立更多接觸點，這會變更目前存在於您資料中的接觸點之間歸因的分配方式。 因此，這可能表示收入值會在行銷管道之間轉換。 實施前請先考量這一點 [!DNL Boomerang stages]，或聯絡您的客戶經理以取得更多資訊。

**任何使用「等於」的報表 [接觸點位置]&quot;**

* 回饋式階段會為您的資料引入新的接觸點位置。 [!DNL Marketo Measure] 正在變更接觸點位置的格式，以包含舞台出現位置，例如「MQL-01」或「MQL-05 （上一個）」。 在此範例中，「迴旋移動階段」會影響任何使用「接觸點位置等於MQL」的報表。 若要調整這些報表，篩選器應改用「包含」運運算元。

## 常見問題集 {#faq}

**在我的歸因模型中可以包含多少回溯期階段？**

您最多可以選取15個階段。

**問：每個階段可以有幾個「迴旋鏢」接觸點？**

您最多可以在每個階段中選取10個boomerang接觸點。

**問：為何每個階段有10個回圈數限制？**

[!DNL Marketo Measure] 必須限制階段數量，才能控制處理時間。 如果您選擇在歸因模型中納入所有15個迴旋鏢階段，且每個階段包含10個迴旋鏢接觸點，則每個銷售機會/聯絡人記錄可能會有超過150個接觸點。

**問：我有Data Warehouse。 我是否取得所有資料，或回溯階段上限也適用於我？**

上限適用於Data Warehouse和CRM，因為處理限制會 [!DNL Marketo Measure] 已準備就緒。 Data Warehouse也會看到每個階段最多10個接觸點的限制。

**問：搭配自訂模型使用迴旋舞台有何優點？**

使用 [!UICONTROL Boomerang] 使用自訂建模的階段可讓您將歸因加權指派給 [!UICONTROL Boomerang] 會將收入點數分配給這些階段的接觸點。

如果沒有自訂模型， [!DNL Marketo Measure] 會為每個boomerang和「階段」轉變建立接觸點，但不會將任何歸因點數指派給這些接觸點。 只有提交接觸點會提供歸因評分，而boomerang接觸點才有。 如果沒有自訂模型， [!DNL Boomerang] 接觸點會被視為與「中間接觸」相同，並據此獲得歸因評分。
