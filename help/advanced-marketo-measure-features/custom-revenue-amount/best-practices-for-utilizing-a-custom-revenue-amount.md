---
description: 使用自訂收入金額的最佳實務 —  [!DNL Marketo Measure]
title: 使用自訂收入金額的最佳實務
exl-id: 553bd75a-512a-4733-a24b-8112eb420afc
feature: Custom Revenue Amount
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# 使用自訂收入金額的最佳實務 {#best-practices-for-utilizing-a-custom-revenue-amount}

## 概觀 {#overview}

[!DNL Marketo Measure]的核心功能是能夠將收入點數指派給整個購買者歷程中的行銷接觸點。 準確收入歸因的關鍵在於[!DNL Marketo Measure]能夠參考機會上的正確收入金額，而機會會透過各種歸因模型分佈於各個行銷接觸點。

除非實作期間另有指定，否則您的[!DNL Marketo Measure]執行個體將設定為參考收入歸因的標準機會金額（SFDC預設值）。 不過，對於許多[!DNL Marketo Measure]帳戶，此欄位無法反映機會的正確收入金額。 在這些情況下，[!DNL Marketo Measure]提供設定[!DNL Marketo Measure]的自訂收入金額的功能，以便在歸因接觸點(BAT)間參考和分發。

## 最佳實務 {#best-practice}

設定自訂收入金額時，請記住以下最佳實務，以確保您的[!DNL Marketo Measure]歸因資料正確且一致！

注意事項：

* 選取正確且適用於所有商機的收入欄位
   * 建議的ARR或合約總值
* 不要使用公式欄位
* 如果您使用自訂收入金額進行貨幣轉換，則[!UICONTROL Marketo Measure Multiple Currencies]功能為偏好方法。
   * [!DNL Marketo Measure]多重貨幣功能參考在[!DNL Salesforce]中建立的轉換率，以最佳方式確保貨幣轉換之間的一致性。 這可讓您繼續使用標準「金額」（SFDC預設值），或與[!DNL Salesforce]轉換率相關的任何其他自訂金額欄位。
* 如果您更新要[!DNL Marketo Measure]參考的Amount欄位，請使用資料載入器更新過去的Opportunities，以確保您的收入資料一致，並透過工作流程填入適當的欄位

## 維護最佳實務 {#best-practice-for-maintenance}

每年檢閱您的收入金額設定，即可確保您的歸因資料正確無誤，並與組織其他收入報表保持一致。

如果您使用自訂收入金額，請依照以下方式檢查收入設定。

* 在您的[!DNL Marketo Measure]帳戶中，移至CRM底下的&#39;[!UICONTROL Opportunities]&#39;區段
* 識別[!UICONTROL Custom Opportunity Amount]欄位，此處應列出您的[!UICONTROL custom revenue amount API]欄位
* 確認這仍是正確的欄位
* 也請您的[!DNL Salesforce]管理員確認[!DNL Salesforce]中的自訂收入金額工作流程仍在執行中

除了每年審查外，某些組織變更可能表示需要審查收入金額設定……

* 您行銷團隊中的營業額
* 「自訂收入」欄位的變更
* 組織變更收入報告方式

>[!MORELIKETHIS]
>
>* [使用自訂收入金額欄位](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
>* [使用資料載入器更新自訂金額欄位](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md)
>* [多幣別總覽](/help/advanced-marketo-measure-features/multi-currency/overview.md)
>* [多重貨幣設定](/help/advanced-marketo-measure-features/multi-currency/settings.md)
