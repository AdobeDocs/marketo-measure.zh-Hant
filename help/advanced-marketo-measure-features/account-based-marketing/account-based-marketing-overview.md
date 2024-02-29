---
unique-page-id: 18874730
description: 瞭解Account-Based Marketing (ABM)，以及AdobeMarketo Measure如何協助行銷和銷售團隊執行成功的ABM策略。
title: 帳戶型行銷概觀
exl-id: 2ead69c0-66da-439d-a0ba-25c73c4b308c
feature: Account-based Marketing
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 0%

---

# 帳戶型行銷概觀 {#account-based-marketing-overview}

以下各節提供ABM的簡要概觀， [!DNL Marketo Measure] ABM功能，以及如何將其新增至 [!DNL Salesforce] 版面配置。 若要深入瞭解ABM，請檢閱Adobe [ABM部落格](https://business.adobe.com/blog/basics/account-based-marketing){target="_blank"}.

有關設定ABM的詳細說明，請參閱 [!DNL Salesforce] 執行個體，前往 [在Salesforce中設定ABM頁面配置](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md#setting-up-abm-page-layout-in-salesforce){target="_blank"}.

## 什麼是ABM {#what-is-abm}

以帳戶為基礎的行銷ABM是一種行銷策略，您可將目標鎖定並銷售給整個公司和帳戶，而不僅僅是個人。 [!DNL Marketo Measure] 協助行銷與銷售團隊透過其銷售線索對帳戶對應功能與預測性參與分數，執行成功的ABM策略。

為了我們的帳戶型行銷模型開始填入您的CRM， [!DNL Marketo Measure] 需要符合下列條件：

* 您的CRM需要至少25個擁有至少一個已結束贏取機會的帳戶，以更好地評估您的企業「成功」帳戶/機會的共同點。
* 另一方面，您的CRM需要至少25個帳戶，且沒有任何「已結案且勝訴的機會」（所有opp必須處於「開啟」階段類別或「已結案且敗訴的」類別），這有助於我們評估是什麼導致貴組織中等級較低的帳戶。

>[!NOTE]
>
>上述「不良」帳戶必須開放至少12個月，且不會累積「已關閉的贏家」；這是判斷Opp是否因模型目的而過期的基本准則。

## 銷售線索與帳戶的對應 {#lead-to-account-mapping}

銷售線索與帳戶的對映是有效業餘資產管理方法的重要部分。 透過銷售線索與帳戶對應，潛在客戶或潛在客戶在與您的品牌互動時分組到相同的公司帳戶中。 這可讓您以一致的方式鎖定目標，並銷售給來自相同公司的個人。 不需額外付費 [!DNL Salesforce] 開始受益於此功能所需的設定。 此 [!DNL Marketo Measure] 銷售線索帳戶對應五種不同的比對方法：

* 將網站引向帳戶網站
* 帳戶網站網域的潛在客戶電子郵件網域
* 潛在客戶公司名稱與帳戶名稱
* 將公司導向帳戶網站網域
* 透過連絡人的電子郵件地址將潛在客戶電子郵件地址上的網域與帳戶進行比對

>[!NOTE]
>
>每個Lead會依照上述方法的優選順序，嘗試和一個Account進行比對。 進行比對後，會立即在潛在客戶上設定AccountId，且不會使用其他方法進行比對。 如果潛在客戶已有有效的AccountId，則會略過該潛在客戶。

## 預測性參與分數 {#predictive-engagement-score}

此 [!DNL Marketo Measure] 預測性參與分數（或PES）是動態值，可說明特定帳戶與行銷工作的參與程度。 此分數有助於將帳戶分段至目標。 這是識別帳戶，以更有效率且有效率地鎖定目標的寶貴工具。

有許多元件會進入計算PES的演演算法。 造訪間隔和年齡對分數變更有很大的影響，還有上次接觸點活動或頁面檢視。 將新連絡人新增到帳戶也會影響PES。 以下是部分PES輸入的清單：

* 來自帳戶的頁面檢視總數
* 平均頁面檢視次數
* 帳戶中的平均人數
* 最後一頁檢視的年齡
* 頁面檢視的平均年齡
* 帳戶中的人數
* 特定重要頁面以及過去30/60/90天內是否有造訪
* 如果帳戶具有已結束的失敗/成功交易
* 關閉遺失/成功的機率

>[!NOTE]
>
>您可能會注意到某些帳戶的預測性參與分數中的等級為「N/A」或「 — 」（破折號）。

_等級「N/A」僅表示該帳戶上沒有足夠的資料可讓模型產生真正的等級 — 有了更多資料，最終將會提供等級。_
_等級「 — 」（破折號）表示ABM處理尚未處理此帳戶，因為時間限制，偶爾會遺漏處理等等。 如果您認為某個帳戶應該有根據其他類似帳戶或時間範圍的等級，請聯絡並讓 [!DNL Marketo Measure] 知道。_

## 在中設定ABM頁面配置 [!DNL Salesforce] {#setting-up-abm-page-layout-in-salesforce}

若要開始使用PES，您必須將PES欄位和「相關清單」新增到適當的版面配置中 [!DNL Salesforce].

1. 瀏覽至 **[!UICONTROL Setup]** > **[!UICONTROL Customize]** > **[!UICONTROL Accounts]** > **[!UICONTROL Page Layout]**. 然後選取您要編輯的頁面配置。
1. 前往 [!UICONTROL Fields] 並將「預測性參與分數」欄位移動到「帳戶資訊」區段中。

   ![](assets/1.png)

1. 最後，前往 [!UICONTROL Related Lists] 並將「銷售機會」相關清單移至您的頁面配置。

   ![](assets/2.png)

1. 接下來，導覽至 **[!UICONTROL Setup]** > **[!UICONTROL Customize]** > **[!UICONTROL Leads]** > **[!UICONTROL Page Layout]** 並選取您要編輯的適當版面配置。
1. 按一下 **[!UICONTROL Fields]** 並新增 [!UICONTROL Account] 您認為適合頁面的欄位。

   ![](assets/3.png)

一切就緒！

