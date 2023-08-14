---
unique-page-id: 18874558
description: 回力郎舞台和接觸點 —  [!DNL Marketo Measure]  — 產品檔案
title: 回味郎舞台和接觸點
exl-id: e58169a3-3637-4878-8a0e-1920d873ff52
feature: Boomerang, Touchpoints
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 0%

---

# 回味郎舞台和接觸點 {#boomerang-stages-and-touchpoints}

>[!AVAILABILITY]
>
>Boomerang功能僅針對第3級客戶啟用。 若要要求更高的帳戶層級，請聯絡Adobe帳戶團隊（您的帳戶經理）。

[!DNL Marketo Measure] 已發佈我們的迴旋舞台功能！ 建立迴旋舞台功能是為了更清楚地顯示客戶的歷程 [!DNL Marketo Measure] 銷售週期長的客戶。 此功能可讓行銷人員為Opportunity歷程中發生的所有階段轉變建立接觸點，例如當聯絡MQL時，然後移至SAL，然後返回MQL階段。 當連絡人「重新進入MQL階段」或「重新進入MQL」時，我們會將MQL視為回圈階段。 「迴旋舞台」功能可與 [!DNL Marketo Measure] 自訂階段。

## 此功能的功能 {#what-this-feature-does}

* 為商機歷程中發生的所有階段轉變建立「迴旋鏢」接觸點
* 追蹤任何自訂階段之間的重複轉換(例如： 當Contact MQL移至SAL，然後返回MQL階段時)
* 可讓您指定要在機會中包含多少以及哪一組階段轉變(例如： 前10個MQL或後5個MQL)
* 如果您是「自訂模型」使用者，便能決定歸因加權和要分配至每個階段的評分百分比(例如： 將歸因權重指定給第一個或最後一個MQL發生次數，或在所有發生次數之間平均分配歸因權重)

>[!NOTE]
>
>[關於如何設定迴旋式舞台的說明](/help/advanced-marketo-measure-features/boomerang/setting-up-boomerang-stages.md).

## Boomerang階段和接觸點在您的CRM中看起來是什麼樣子 {#what-boomerang-stages-and-touchpoints-look-like-in-your-crm}

如果沒有Boomerang階段（「之前」），您只會看到與Lead/Contact記錄相關聯的最新MQL或最新的SQL接觸點。

![](assets/1.png)

透過「回力行階段」和接觸點，您會看到每個階段轉換中發生的接觸點。 這些迴旋接觸點的命名慣例如下：

**[階段名稱]-00。**

以下列範例說明 [!DNL Marketo Measure] 帳戶已將MQL和SQL納入其回溯站階段，並已選擇在每個階段顯示2個回溯站接觸點。

![](assets/2.png)

**MQL-01** 是第一個MQL階段轉換。

接觸點位置中的數值將代表階段轉換發生的順序。 最後一個回溯點要加上戳記為：

MQL-02 **（上次）**

## Boomerang階段如何變更您現有的資料 {#how-boomerang-stages-change-your-existing-data}

回力行階段將影響：

**依據管道的歸因**

* 從 [!DNL Boomerang Stages] 會建立更多接觸點，進而變更歸因在資料中目前存在的接觸點之間的分配方式。 因此，這可能表示收入值將在行銷管道之間轉換。 實施前請先考量這一點 [!DNL Boomerang stages]，或聯絡您的客戶經理以取得更多資訊。

**任何使用「等於」的報表 [接觸點位置]&quot;**

* 迴旋鏢階段會將新的接觸點位置引入您的資料。 [!DNL Marketo Measure] 正在變更接觸點位置的格式，以包含舞台出現位置，例如「MQL-01」或「MQL-05 （上一個）」。 在此範例中，「回溯點階段」會影響任何使用「接觸點位置等於MQL」的報表。 若要調整這些報表，篩選器應改用「包含」運運算元。

## 常見問題集 {#faq}

**在我的歸因模型中可以包含多少回溯期階段？**

您最多可以選取15個階段。

**問：每個階段可以有幾個「迴旋鏢」接觸點？**

您最多可以在每個階段中選取10個迴旋接觸點。

**問：為什麼每個階段最多只能有10個迴旋？**

[!DNL Marketo Measure] 為了控制處理時間，必須對階段數量進行限制。 如果您選擇在歸因模型中納入所有15個迴旋鏢階段，且每個階段包含10個迴旋鏢接觸點，則每個銷售機會/聯絡人記錄可能會有超過150個接觸點。

**問：我有Data Warehouse。 我是否取得所有資料，或回溯階段上限也適用於我？**

上限將套用至Data Warehouse和CRM，因為處理限制會 [!DNL Marketo Measure] 已準備就緒。 Data Warehouse也會看到每個階段最多10個接觸點的限制。

**問：搭配自訂模型使用迴旋舞台有何優點？**

使用 [!UICONTROL Boomerang] 使用自訂建模的階段可讓您將歸因加權指派給 [!UICONTROL Boomerang] 會將收入點數分配給這些階段的接觸點。

如果沒有自訂模型， [!DNL Marketo Measure] 會為每個回圈和階段轉變建立接觸點，但不會將任何歸因點數指派給這些接觸點。 唯一會收到歸因點數的回圈接觸點為表單提交接觸點。 如果沒有自訂模型， [!DNL Boomerang] 接觸點會被視為與「中間接觸」相同，並據此獲得歸因評分。
