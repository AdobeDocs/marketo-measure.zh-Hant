---
unique-page-id: 18874558
description: 迴音廊舞台和接觸點 —  [!DNL Marketo Measure]  — 產品檔案
title: 迴音廊舞台和接觸點
exl-id: e58169a3-3637-4878-8a0e-1920d873ff52
source-git-commit: 01be819ccee1b3079b15a748480e9dacf6adb488
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 0%

---

# 迴音廊舞台和接觸點 {#boomerang-stages-and-touchpoints}

>[!AVAILABILITY]
>
>Boomerang功能僅對第3級客戶啟用。 若要要求更高的帳戶層級，請聯絡Adobe帳戶團隊（您的帳戶經理）。

[!DNL Marketo Measure] 已發佈我們的Boomerang Stage功能！ 建立Boomerang Stage功能是為了讓更多的人瞭解客戶的歷程， [!DNL Marketo Measure] 銷售週期長的客戶。 此功能可讓行銷人員為Opportunity歷程中發生的所有階段轉變建立接觸點，例如當聯絡MQL時，然後移至SAL，然後返回MQL階段。 當連絡人「重新進入MQL階段」或「重新進入MQL」時，我們將MQL視為回攻階段。 Boomerang Stage的功能與 [!DNL Marketo Measure] 自訂階段。

## 此功能的功能 {#what-this-feature-does}

* 為商機歷程中發生的所有階段轉變建立「回彈」接觸點
* 追蹤任何自訂階段之間的重複轉換(例如： 當Contact MQL移至SAL，然後返回MQL階段時)
* 可讓您指定要在機會中包含多少及哪一組階段轉變(例如： 前10個MQL或後5個MQL)
* 如果您是「自訂模型」使用者，便能決定歸因加權，以及要分配至每個階段的評分百分比(例如： 將歸因權重指定給第一個或最後一個MQL發生次數，或在所有發生次數之間平均分配歸因權重)

>[!NOTE]
>
>[如何設定迴音廊階段的指示](/help/advanced-marketo-measure-features/boomerang/setting-up-boomerang-stages.md).

## Boomerang階段和接觸點在您的CRM中看起來是什麼樣子 {#what-boomerang-stages-and-touchpoints-look-like-in-your-crm}

如果沒有Boomerang階段（「之前」），您只會看到與銷售機會/聯絡人記錄相關聯的最新MQL或最新SQL接觸點。

![](assets/1.png)

透過「迴音廊階段」和接觸點，您會看到每個階段轉變中發生的接觸點。 這些迴旋梁接觸點的命名慣例如下：

**[階段名稱]-00。**

以下列範例說明 [!DNL Marketo Measure] 帳戶已將MQL和SQL納入其迴音廊階段，並已選擇每個階段顯示2個迴音廊接觸點。

![](assets/2.png)

**MQL-01** 是第一個MQL階段轉換。

接觸點位置中的數值將代表階段轉換發生的順序。 最後一個boomerang接觸點將標籤為：

MQL-02 **（上次）**

## Boomerang階段如何變更您現有的資料 {#how-boomerang-stages-change-your-existing-data}

迴音廊階段將影響：

**依管道的歸因**

* 從 [!DNL Boomerang Stages] 會建立更多接觸點，而這會變更歸因在目前存在於您資料中的接觸點之間的分配方式。 因此，這可能表示收入值會在行銷管道之間轉換。 實作前請將此納入考量 [!DNL Boomerang stages]，或聯絡您的客戶經理以取得更多資訊。

**任何使用「等於」的報表 [接觸點位置]&quot;**

* 「回彈」階段會將新的接觸點位置引入您的資料。 [!DNL Marketo Measure] 會變更「接觸點位置」的格式，以包含舞台出現位置，例如「MQL-01」或「MQL-05 （上一個）」。 在此範例中，「Boomerang階段」將會影響使用「接觸點位置等於MQL」的任何報表。 若要調整這些報表，篩選器應改用「包含」運運算元。

## 常見問題集 {#faq}

**在我的歸因模型中可以包含多少個回溯期階段？**

您最多可以選取15個階段。

**問：每個階段可以有幾個「回彈」接觸點？**

每個階段最多可以選取10個迴音廊接觸點。

**問：為什麼每個階段最多只能有10個迴旋？**

[!DNL Marketo Measure] 為了控制處理時間，必須對階段數量進行限制。 如果您選擇在歸因模型中納入所有15個回攻角階段，每個階段包含10個回攻角接觸點，則每個銷售機會/聯絡人記錄可能會有超過150個接觸點。

**問：我有Data Warehouse。 我是否取得所有資料，或迴音階段上限也適用於我？**

上限將套用至Data Warehouse和CRM，因為處理限制 [!DNL Marketo Measure] 已準備就緒。 Data Warehouse也會看到每個階段最多10個接觸點的限制。

**問：搭配自訂模型使用「迴音廊階段」有何優點？**

使用 [!UICONTROL Boomerang] 使用自訂建模的階段可讓您指派歸因權重至 [!UICONTROL Boomerang] 會將收入點數分配給這些階段的接觸點。

若沒有自訂模型， [!DNL Marketo Measure] 會為每個回溯期和階段轉變建立接觸點，但不會將任何歸因點數指派給這些接觸點。 唯一會收到歸因評分的boomerang接觸點為表單提交接觸點。 如果沒有自訂模型， [!DNL Boomerang] 接觸點會被視為與「中間接觸」相同，並據此獲得歸因評分。
