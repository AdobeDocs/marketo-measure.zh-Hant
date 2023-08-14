---
description: 使用自訂收入金額的最佳實務 —  [!DNL Marketo Measure]  — 產品檔案
title: 使用自訂收入金額的最佳實務
exl-id: 553bd75a-512a-4733-a24b-8112eb420afc
feature: Custom Revenue Amount
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# 使用自訂收入金額的最佳實務 {#best-practices-for-utilizing-a-custom-revenue-amount}

## 概觀 {#overview}

的核心功能 [!DNL Marketo Measure] 是指在整個購買者歷程中，將收入點數指派給行銷接觸點的能力。 準確收入歸因的關鍵是 [!DNL Marketo Measure] 以參考商機的正確收入金額，而機會收入金額會透過各種歸因模型分佈於各個行銷接觸點。

除非實作期間另有指定，否則 [!DNL Marketo Measure] 執行個體將設定為參考收入歸因的標準「機會金額」（SFDC預設）。 不過，對許多人來說 [!DNL Marketo Measure] 科目，此欄位無法反映「商機」的正確收入金額。 在這些情況下， [!DNL Marketo Measure] 提供設定自訂收入金額的功能 [!DNL Marketo Measure] 在歸因接觸點(BAT)間參照和分佈。

## 最佳實務 {#best-practice}

設定自訂收入金額時，請記住以下最佳實務，以確保您的 [!DNL Marketo Measure] 歸因資料準確且一致！

注意事項：

* 選取正確且適用於所有商機的收入欄位
   * 建議的ARR或合約總值
* 不要使用公式欄位
* 如果您使用自訂收入金額進行貨幣轉換，則 [!UICONTROL Marketo Measure Multiple Currencies] 偏好使用的方法是功能。
   * 此 [!DNL Marketo Measure] 多幣別功能參考中建立的兌換率 [!DNL Salesforce] 以最好地確保貨幣轉換之間的一致性。 這可讓您繼續使用標準「金額」（SFDC預設值），或與相關的任何其他自訂金額欄位 [!DNL Salesforce] 轉換率。
* 如果您要更新「金額」欄位 [!DNL Marketo Measure] 若要參考，請使用資料載入器更新過去的機會，以確保您的收入資料一致，並透過工作流程填入適當的欄位

## 維護最佳實務 {#best-practice-for-maintenance}

每年檢閱您的收入金額設定，即可確保您的歸因資料正確無誤，並與組織其他收入報表保持一致。

如果您使用「自訂收入金額」，請依照以下步驟檢查收入設定。

* 在您的 [!DNL Marketo Measure] 帳戶，前往「[!UICONTROL Opportunities]&#39;區段在CRM底下
* 識別 [!UICONTROL Custom Opportunity Amount] 欄位，此處為您的 [!UICONTROL custom revenue amount API] 欄位應列出
* 確認這仍是正確的欄位
* 此外，請 [!DNL Salesforce] 管理員確認中的自訂收入金額工作流程 [!DNL Salesforce] 仍在執行中

除了每年審查外，某些組織變更可能表示需要審查收入金額設定……

* 您行銷團隊中的營業額
* 「自訂收入」欄位的變更
* 組織變更收入報告方式

>[!MORELIKETHIS]
>
>* [使用自訂收入金額欄位](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
>* [使用資料載入器更新自訂金額欄位](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md)
>* [多幣別概要](/help/advanced-marketo-measure-features/multi-currency/overview.md)
>* [多貨幣設定](/help/advanced-marketo-measure-features/multi-currency/settings.md)
