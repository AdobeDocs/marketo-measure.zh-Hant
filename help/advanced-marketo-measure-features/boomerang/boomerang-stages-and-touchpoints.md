---
unique-page-id: 18874558
description: Boomerang階段和接觸點 —  [!DNL Marketo Measure]
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

[!DNL Marketo Measure]已發行Boomerang Stage功能！ 建立「迴旋舞台」功能是為了讓[!DNL Marketo Measure]個銷售週期長的客戶更清楚地瞭解客戶的歷程。 此功能可讓行銷人員為Opportunity歷程中發生的所有階段轉變建立接觸點（例如當聯絡MQL時），然後移至SAL，再移回MQL階段。 當連絡人「重新進入MQL階段」或「重新進入MQL的階段」時，MQL會被視為回圈階段。 「迴旋移動階段」功能可與[!DNL Marketo Measure]自訂階段搭配使用。

## 此功能的功能 {#what-this-feature-does}

* 為商機歷程中發生的所有階段轉變建立「迴旋鏢」接觸點
* 追蹤任何自訂階段之間的重複轉換(例如： 當Contact MQL移至SAL，然後返回MQL階段時)
* 可讓您指定要在機會中包含多少以及哪一組階段轉變(例如： 前10個MQL或後5個MQL)
* 如果您是「自訂模型」使用者，便能決定歸因加權和要分配至每個階段的評分百分比(例如： 將歸因權重指定給第一個或最後一個MQL發生次數，或在所有發生次數之間平均分配歸因權重)

>[!NOTE]
>
>[如何設定Boomerang階段的相關說明](/help/advanced-marketo-measure-features/boomerang/setting-up-boomerang-stages.md)。

## Boomerang階段和接觸點在您的CRM中看起來是什麼樣子 {#what-boomerang-stages-and-touchpoints-look-like-in-your-crm}

如果沒有Boomerang階段（「之前」），您只會看到與Lead/Contact記錄相關聯的最新MQL或最新SQL接觸點。

![](assets/1.png)

使用Boomerang階段和接觸點，您會看到每個階段轉換中發生的接觸點。 這些迴旋接觸點的命名慣例如下：

**[階段名稱]-00.**

以下列範例為例，此[!DNL Marketo Measure]帳戶已將MQL和SQL納入boomerang階段，並已選擇每個階段顯示2個boomerang接觸點。

![](assets/2.png)

**MQL-01**&#x200B;是第一個MQL階段轉換。

接觸點位置中的數值表示階段轉換發生的順序。 最後一個回溯點要加上戳記為：

MQL-02 **（最後）**

## Boomerang階段如何變更您現有的資料 {#how-boomerang-stages-change-your-existing-data}

回零階段影響：

**依據管道的歸因**

* 由於[!DNL Boomerang Stages]會建立更多接觸點，這會變更歸因在目前存在於您資料中的接觸點之間的分配方式。 因此，這可能表示收入值會在行銷管道之間轉換。 在實作[!DNL Boomerang stages]前請先將此列入考量，或連絡您的客戶經理以取得更多資訊。

**任何使用「等於[接觸點位置]」的報表**

* 回饋式階段會為您的資料引入新的接觸點位置。 [!DNL Marketo Measure]正在變更接觸點位置的格式，以包含階段出現次數，例如&quot;MQL-01&quot;或&quot;MQL-05 （上一個）&quot;。 在此範例中，「迴旋移動階段」會影響任何使用「接觸點位置等於MQL」的報表。 若要調整這些報表，篩選器應改用「包含」運運算元。

## 常見問題集 {#faq}

**我可以在歸因模型中包含多少個迴旋鏢階段？**

您最多可以選取15個階段。

**問：每個階段可以有幾個「boomerang」接觸點？**

您最多可以在每個階段中選取10個boomerang接觸點。

**問：為什麼每個階段有10個回圈限制？**

[!DNL Marketo Measure]必須設定階段數限制，才能控制處理時間。 如果您選擇在歸因模型中納入所有15個迴旋鏢階段，且每個階段包含10個迴旋鏢接觸點，則每個銷售機會/聯絡人記錄可能會有超過150個接觸點。

**問：我有Data Warehouse。 我是否取得所有資料，或是Boomerang階段上限也適用於我？**

上限適用於Data Warehouse和CRM，因為[!DNL Marketo Measure]已設定處理限制。 Data Warehouse也會看到每個階段最多10個接觸點的限制。

**問：將Boomerang階段與自訂模型結合使用有何好處？**

搭配自訂模型使用[!UICONTROL Boomerang]階段可讓您將歸因加權指派給[!UICONTROL Boomerang]個接觸點，這會分配收入點數給這些階段。

若沒有自訂模型，[!DNL Marketo Measure]會為每個回圈和階段轉換建立接觸點，但不會將任何歸因點數指派給這些接觸點。 只有提交接觸點會提供歸因評分，而boomerang接觸點才有。 若沒有自訂模型，[!DNL Boomerang]個接觸點會被視為與「中間接觸」相同，並據此獲得歸因評分。
