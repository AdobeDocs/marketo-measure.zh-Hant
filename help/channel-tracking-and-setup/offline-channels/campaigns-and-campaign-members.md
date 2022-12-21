---
unique-page-id: 18874578
description: 促銷活動和促銷活動成員 —  [!DNL Marketo Measure]  — 產品檔案
title: 促銷活動和促銷活動成員
exl-id: e4e2b154-39ac-4295-a541-7fa6112672e3
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '1159'
ht-degree: 0%

---

# 促銷活動和促銷活動成員 {#campaigns-and-campaign-members}

[!DNL Salesforce] 促銷活動旨在追蹤與行銷方案或活動相關聯的銷售機會和聯絡人清單。 例如，這通常是網路研討會、註冊或展位造訪。 行銷人員可以選擇是否應將促銷活動評分計入接觸點歷程中。

## 啟用接觸點 {#enabling-touchpoints}

此 [!DNL Marketo Measure] [!DNL Salesforce] 套件會在促銷活動物件上包含標示為「啟用購買者接觸點」的欄位。 將欄位新增至頁面配置後，其顯示將類似於：

![](assets/1.png)

選擇清單中可用的選項有：

![](assets/2.png)

* 包含所有促銷活動成員 — 新增至促銷活動的每個銷售機會或聯絡人都會收到與該促銷活動相關聯的接觸點。
* 僅包含「已回應」促銷活動成員 — 只有促銷活動成員狀態為「已回應」的銷售機會或聯絡人會收到與該促銷活動相關聯的接觸點。
* 排除所有促銷活動成員 — 沒有任何銷售機會或聯絡人會收到與該促銷活動相關聯的接觸點。

請注意，促銷活動成員必須有與其記錄相關聯的電子郵件地址，才能 [!DNL Marketo Measure] 來建立接觸點。 沒有電子郵件地址， [!DNL Marketo Measure] 不會將接觸點指派給促銷活動成員。

## 促銷活動同步日期 {#campaign-sync-dates}

安裝軟體包後， [!DNL Marketo Measure] 也將包含Campaign物件上的2個日期欄位：接觸點開始日期和接觸點結束日期。

這些日期告訴 [!DNL Marketo Measure] 何時應開始或停止將促銷活動成員從促銷活動納入接觸點歷程。 您可以設定一個日期，或兩者皆可，或完全無。

## 接觸點開始日期的使用案例 {#use-case-for-touchpoint-start-date}

如果現有促銷活動用於追蹤銷售機會和聯繫人，但用戶只想在新系統或流程到位後開始測量，則他們決定設定一次開始日期 [!DNL Marketo Measure] 應該開始追蹤這些促銷活動成員。

## 接觸點結束日期的使用案例 {#use-case-for-touchpoint-end-date}

若未使用 [!DNL Marketo Measure]，您使用行銷自動化平台追蹤銷售機會的數位互動（IE表單提交），然後將這些銷售機會上傳至 [!DNL Saleforce] Campaign，您可以利用「接觸點結束日期」欄位。 您可以使用將「接觸點結束日期」設為開始日期 [!DNL Marketo Measure] 並啟用購買者接觸點，則這些銷售機會的每個數位互動都會建立為接觸點。 您將接觸點結束日期設為開始日期的原因為 [!DNL Marketo Measure] 因為未來，我們將透過javascript追蹤這些數位互動。

![](assets/3.png)

## 促銷活動成員 {#campaign-members}

促銷活動成員會巢狀內嵌於 [!UICONTROL Campaigns]，且與銷售機會或連絡人相關。 銷售機會或連絡人只能新增一次至促銷活動，這可能會因促銷活動的使用案例而產生問題。 同步促銷活動時，促銷活動成員資格會作為行銷活動，放入接觸點歷程，並視為表單填入。

## 購買者接觸點狀態 {#buyer-touchpoint-status}

如果已啟用， [!DNL Marketo Measure] 會將狀態值推送至已安裝套件中包含的4個不同欄位上的促銷活動成員：接觸點狀態（銷售機會）、接觸點狀態（聯繫人）、接觸點狀態（銷售機會）和接觸點狀態日期。 這可協助客戶稽核接觸點是否已建立為購買者接觸點或購買者歸因接觸點，視其相關物件而定。 接觸點狀態日期只是促銷活動成員上狀態更新的最後日期。

![](assets/4.png)

## 購買者接觸點日期 {#buyer-touchpoint-date}

安裝軟體包後， [!DNL Marketo Measure] 也包含「促銷活動成員」上標示為「購買者接觸點日期」的欄位。 這可讓使用者覆寫 [!DNL Marketo Measure] 會用於接觸點記錄上的接觸點日期。

如果清單是在事件實際發生後上傳的天/周/月，則此為必要操作。 有多種方法可一次更新所有記錄，請詳見下文。

![](assets/5.png)

若要了解您是否需要使用「購買者接觸點日期」，以下說明日期的決定方式 [!DNL Marketo Measure] 取決於 [!UICONTROL Sync Type] 已針對促銷活動選取。

若 [!UICONTROL Sync Type] 設為「包含所有促銷活動成員」，則設定接觸點日期的優先順序會從上到下：

* 購買者接觸點日期
* 促銷活動成員建立日期

若 [!UICONTROL Sync Type] 設為「僅包含&#39;已回應&#39;促銷活動成員」，則設定接觸點日期的優先順序會從上到下：

* 購買者接觸點日期
* 首次回應日期
   * 狀態變更為「已回應」且為標準時，就會自動設定「首次回應日期」 [!DNL Salesforce] 無法變更的欄位

* 促銷活動成員建立日期

## 大量更新接觸點日期 {#bulk-update-touchpoint-date}

已安裝的大量更新接觸點日期包含在 [!DNL Marketo Measure] [!DNL Salesforce] 套件和按鈕必須新增至頁面配置。

![](assets/6.png)

如果需要更新大量促銷活動成員記錄，您可以使用 [!UICONTROL Bulk Update Touchpoint Date] 按鈕進行成批編輯。

如果有不重複的使用案例未涵蓋此介面，您也可以使用 [資料載入器](https://dataloader.io/){target=&quot;_blank&quot;}可匯出記錄、進行變更，然後將記錄上傳回。

首先，請搜尋記錄，並篩選您要為其設定購買者接觸點日期的記錄。

>[!CAUTION]
>
>有一個搜尋無法運作，如下列範例所示。 UI不支援搜尋空的購買者接觸點日期（以下搜尋無法運作）:

![](assets/7.png)

如果您不需要使用搜尋，而只是將日期套用至每個促銷活動成員記錄，請使用「[!UICONTROL Include All Records]「核取方塊（請參閱下方的螢幕截圖），該核取方塊將會檢查所有頁面上的所有記錄。

從日曆選擇器中選取日期和時間。 如果要選取目前的日期和時間，請按一下日曆選擇器旁顯示的日期/時間。

設定日期和時間後，按一下 **[!UICONTROL Update Selected Records]** 按鈕以應用更改。

![](assets/8.png)

## 促銷活動成本 {#campaign-costs}

了解Campaign成本 [本文](/help/marketing-spend/spend-management/crm-campaign-costs.md).

## 促銷活動成員移除 {#campaign-member-removal}

這樣 [!DNL Marketo Measure] 跟上Salesforce中已刪除的任何記錄，無論這些記錄是Leads還是Accounts或Opportunity，都是在API中查看這些記錄，並跟蹤某個條目被標籤為「IsDeleted」。 不幸的是，Salesforce針對Campaign成員推出了從促銷活動刪除這些促銷活動成員的不同方法，而且實際上這些成員被標示為「已移除」而非「已刪除」，因此問題在於接觸點仍以Salesforce存在，而這些Campaign成員與已刪除的促銷活動成員相關。

為了解決這個問題， [!DNL Marketo Measure] 已建立 [!DNL Marketo Measure] 每當刪除促銷活動成員，然後刪除對應的接觸點時，便要追蹤的歷史記錄物件和觸發器。 **您需要 [!DNL Marketo Measure] 行銷分析套件V6.15或更新版本** 來使用此功能。

>[!CAUTION]
>
>請記住，此觸發器不會追蹤任何過去已移除的促銷活動成員，因此這只會持續運作。 如果您需要移除大量過去的促銷活動成員接觸點，請聯絡 [Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;}。

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] 大學：促銷活動物件欄位](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63007334d9f0367662b758)
>
>[[!DNL Marketo Measure] 大學：對應離線頻道](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c630eca34d9f0367662b77f)
