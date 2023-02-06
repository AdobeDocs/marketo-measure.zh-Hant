---
description: 使用自訂收入金額的最佳實務 —  [!DNL Marketo Measure]  — 產品檔案
title: 使用自訂收入金額的最佳實務
exl-id: 553bd75a-512a-4733-a24b-8112eb420afc
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# 使用自訂收入金額的最佳實務 {#best-practices-for-utilizing-a-custom-revenue-amount}

## 概觀 {#overview}

的核心功能 [!DNL Marketo Measure] 是指在整個購買者歷程中，將收入評分指派給行銷接觸點的能力。 準確歸因的關鍵是 [!DNL Marketo Measure] 以參考Opportunity上正確的收入額，而Opportunity又通過各種歸因模型分佈在各個行銷接觸點。

除非在實施期間另有指定，否則您的 [!DNL Marketo Measure] 實例將被設定為引用收入歸因的標準機會金額（SFDC預設值）。 然而，對許多人而言 [!DNL Marketo Measure] 帳戶，此欄位不反映Opportunity的準確收入額。 在這些情況下， [!DNL Marketo Measure] 提供設定自訂收入金額的功能 [!DNL Marketo Measure] 在歸因接觸點(BAT)間參照和分發。

## 最佳實務 {#best-practice}

設定自訂收入金額時，請謹記下列最佳實務，以確保您的 [!DNL Marketo Measure] 歸因資料準確且一致！

請記住：

* 選擇準確且用於所有Opportunity的收入欄位
   * 我們建議使用ARR或總合約值
* 請勿使用公式欄位
* 如果您使用「自訂收入額」進行貨幣轉換，則 [!UICONTROL Marketo Measure Multiple Currencies] 功能是偏好的方法。
   * 此 [!DNL Marketo Measure] 多貨幣功能會參考在 [!DNL Salesforce] 以最佳地確保貨幣轉換之間的一致。 這允許您繼續使用標準「金額」（SFDC預設值）或與 [!DNL Salesforce] 轉換率。
* 如果您更新想要的「金額」欄位 [!DNL Marketo Measure] 若要參考，請使用Data Loader更新過去的Opportunity ，以確保您的收入資料一致，並透過工作流程填入正確欄位

## 維護最佳實務 {#best-practice-for-maintenance}

每年檢閱收入金額設定，將可確保您的歸因資料正確無誤，並與貴組織其餘的收入報表保持一致。

如果您使用自訂收入金額，請依照下列方式檢查收入設定。

* 在 [!DNL Marketo Measure] 帳戶，轉到「[!UICONTROL Opportunities]CRM下的「 」節
* 識別 [!UICONTROL Custom Opportunity Amount] 欄位，給你 [!UICONTROL custom revenue amount API] 欄位應列出
* 確認這仍是正確的欄位
* 還有 [!DNL Salesforce] 管理員確認 [!DNL Salesforce] 仍在執行

除了每年審核外，某些組織變更可能表示需要審核收入金額設定……

* 行銷團隊的營業額
* 自訂收入欄位的變更
* 組織對收入報告方式的變更

>[!MORELIKETHIS]
>
>* [使用自訂收入金額欄位](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
>* [使用資料載入器更新自訂量欄位](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md)
>* [多貨幣概觀](/help/advanced-marketo-measure-features/multi-currency/overview.md)
>* [多貨幣設定](/help/advanced-marketo-measure-features/multi-currency/settings.md)

