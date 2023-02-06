---
unique-page-id: 18874730
description: 帳戶型行銷概述 —  [!DNL Marketo Measure]  — 產品檔案
title: 帳戶型行銷概述
exl-id: 2ead69c0-66da-439d-a0ba-25c73c4b308c
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 0%

---

# 帳戶型行銷概述 {#account-based-marketing-overview}

以下是ABM的簡要概述， [!DNL Marketo Measure] ABM功能，以及如何將其新增至 [!DNL Salesforce] 頁面配置。 要閱讀更多有關ABM的資訊，請查看 [本頁](https://www.marketo.com/account-based-marketing/){target="_blank"}.

直接導航到在 [!DNL Salesforce] 例項，請 [按一下這裡](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md#setting-up-abm-page-layout-in-salesforce){target="_blank"}.

## 什麼是ABM {#what-is-abm}

基於帳戶的營銷(ABM)是一種營銷策略，在這種策略中，您可以將目標定位並銷售給公司和整個帳戶，而不只是個人。 [!DNL Marketo Measure] 有助於行銷和銷售團隊運用其潛在客戶對帳對應功能和預測性參與分數執行成功的ABM策略。

為了讓我們的帳戶型行銷模型開始填入您的CRM中， [!DNL Marketo Measure] 需要符合下列條件：

* 您的CRM至少需要25個客戶，其中至少有一個Closed Won Opportunity，因此我們可以更好地評估「成功」客戶/Opportunity對您的業務的共性。
* 在硬幣的另一面，您的CRM至少需要25個帳戶，而不需要任何Closed Won Oppontity(所有Op必須位於我們的「Open」階段類別，或「Closed Lost」類別 — 這有助於我們評估貴組織中級別較低的帳戶的組成。

>[!NOTE]
>
>上述「壞帳」賬戶需要至少開啟12個月，而不需要累積已結韓元的期權；這是我們為模型用途判斷Opp是否過時的基本准則。

## 銷售機會對應 {#lead-to-account-mapping}

導向與賬戶映射是有效反導方針的關鍵部分。 透過銷售機會對應、潛在客戶或銷售機會，在他們與您的品牌互動時會歸類到相同的公司帳戶中。 這可讓您以一致的方式鎖定並銷售給同一家公司的個人。 沒有其他 [!DNL Salesforce] 開始受益於此功能所需的設定。 此 [!DNL Marketo Measure] 導致帳戶對應五種不同的匹配方法：

* 引導網站到帳戶網站
* 將電子郵件網域引導至帳戶網站網域
* 銷售機會公司名稱至帳戶名稱
* 引導公司到帳戶網站域
* 透過連絡人的電子郵件地址，將潛在客戶電子郵件地址上的網域與帳戶相符

## 預測性參與分數 {#predictive-engagement-score}

此 [!DNL Marketo Measure] 預測性參與分數(PES)是一個動態值，可說明特定帳戶如何參與您的行銷工作。 此分數有助於將帳戶分段至Target。 它是識別帳戶以更有效和更有效率地鎖定目標的寶貴工具。

演算法中有許多元件可計算PES。 使用間隔和年齡對分數變更，以及上次接觸點活動或頁面檢視有很大影響。 向帳戶添加新聯繫人也會影響PES。 以下是一些PES輸入的清單：

* 來自帳戶的頁面檢視總數
* 平均頁面檢視次數
* 賬戶中的平均人數
* 上次頁面檢視的年齡
* 頁面檢視的平均年齡
* 賬戶中的人數
* 特定重要頁面，以及過去30/60/90天內是否有造訪
* 如果帳戶有一筆已結的損失/贏取交易
* 關閉的可能性是多少？

>[!NOTE]
>
>您可能會注意到某些帳戶的預測性參與分數中有「N/A」或「 — 」（破折號）等級。

_「N/A」的級別意味著我們在模型上還沒有足夠的資料來生成真正的級別 — 如果有更多的資料，最終會給出一個級別。_
_等級為&quot;-&quot;（破折號）意味著由於時間限制、有時遺漏的程式等原因，我們的ABM程式尚未處理此帳戶。 如果您認為帳戶應該有等級，請根據其他類似帳戶或時間範圍，聯絡並讓 [!DNL Marketo Measure] 知道。_

## 在中設定ABM頁面配置 [!DNL Salesforce] {#setting-up-abm-page-layout-in-salesforce}

要開始使用PES，只需將PES欄位和相關清單添加到 [!DNL Salesforce].

1. 導覽至 **[!UICONTROL Setup]** > **[!UICONTROL Customize]** > **[!UICONTROL Accounts]** > **[!UICONTROL Page Layout]**. 然後選取您要編輯的頁面版面。
1. 前往 [!UICONTROL Fields] 並將「預測性參與分數」欄位移至「帳戶資訊」區段。

   ![](assets/1.png)

1. 最後，請前往 [!UICONTROL Related Lists] 並將「銷售機會」相關清單移入您的頁面版面。

   ![](assets/2.png)

1. 接下來，導覽至 **[!UICONTROL Setup]** > **[!UICONTROL Customize]** > **[!UICONTROL Leads]** > **[!UICONTROL Page Layout]** 並選擇要編輯的適當頁面佈局。
1. 按一下 **[!UICONTROL Fields]** 並新增 [!UICONTROL Account] 欄位，您可在此頁面中看到適合。

   ![](assets/3.png)

你都準備好了！

