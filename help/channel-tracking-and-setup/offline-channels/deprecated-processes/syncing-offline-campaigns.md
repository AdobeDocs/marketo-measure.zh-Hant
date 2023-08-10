---
unique-page-id: 18874600
description: 同步離線行銷活動 —  [!DNL Marketo Measure]  — 產品檔案
title: 同步離線行銷活動
exl-id: a6f9e217-ff6e-474d-9f14-c6f6238c9e84
feature: Channels
source-git-commit: e01738222e8845112892c0258cb084a4f0ebb257
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 0%

---

# 同步離線行銷活動 {#syncing-offline-campaigns}

準確地追蹤離線行銷活動，並瞭解其與您數位行銷工作的比較情形，可能相當困難。 [!DNL Marketo Measure] 可讓您追蹤接觸點並將其歸因於中的離線行銷活動 [!DNL Salesforce]，即使在 [!DNL Salesforce] 行銷活動要等到事件幾週後才會建立。

>[!NOTE]
>
>本文會介紹過時的程式。 我們鼓勵使用者使用 [新的、改良的應用程式內程式](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"}.

## 同步之前 {#before-you-sync}

以下是有效率同步程式的一些秘訣：

* 離線行銷活動是指不會線上上發生的行銷互動。 其中包括行銷管道，例如活動、網路研討會及商展。 僅包含離線行銷活動。
* 如果您想要納入在安裝前追蹤線上活動的行銷活動 [!DNL Marketo Measure]，請務必將接觸點結束日期設為您的網站上部署JavaScript的日期。
* 保留「 」會很有幫助 [!DNL Marketo Measure] 應用程式會在離線管道頁面上開啟，以便輕鬆識別不同的促銷活動型別，以及接觸點要合併到的行銷管道。

* 在點選「」之前仔細檢查所有專案[!UICONTROL Save]」按鈕！

## 大量更新接觸點日期 {#bulk-update-touchpoint-date}

在 [!DNL Salesforce]，促銷活動成員物件上的建立日期欄位會記下促銷活動成員新增至促銷活動的日期。 為了讓同步處理順利進行，請確定「購買者接觸點日期」欄位的日期與「Salesforce促銷活動成員物件」上的日期相同。 此步驟是使用&quot;[!UICONTROL Bulk Update Touchpoint Date button]，」 _早於_ 您選取 [!UICONTROL picklist] 「啟用購買者接觸點」欄位中的選項。

為什麼這很重要？ 想像一下，您的公司在1月的一次會議上贊助了一個展位。 在大會中，有100個人對您的產品表示興趣，並提供他們的連絡資訊以接收電子郵件更新。 三週後，您終於在中建立行銷活動 [!DNL Salesforce] 以追蹤會議結果。

您的上傳日期會晚於會議日期三週。 若要修正此差異， [!UICONTROL Bulk Update Touchpoint Date] 按鈕可用於設定適當的日期。 按鈕如下圖所示。

![](assets/1-3.png)

在這種情況下，上傳日期會回填三週。 此步驟應在設定&quot;[!UICONTROL Enable Buyer Touchpoints]「欄位。

總而言之，如果您使用 [!UICONTROL Bulk Update Touchpoint Date] 按鈕並將接觸點日期變更為事件日期， [!DNL Marketo Measure] 將會針對事件的實際日期（而非上傳日期）產生接觸點。

您也可以更新現有行銷活動上所有行銷活動成員的日期。 這樣做時，請確定接觸點的日期是成員互動的日期。 只要按一下「大量更新購買者接觸點日期」、適當篩選行銷活動成員清單，以及在「[!UICONTROL Select Date]」選項位於行銷活動成員清單上方，新增與事件發生相同的日期。

>[!CAUTION]
>
>請務必更新接觸點日期 _早於_ 您可以為所有行銷活動成員啟用接觸點。

![](assets/2-3.png)

## 如何建立行銷活動並同步購買者接觸點 {#how-to-create-a-campaign-and-sync-buyer-touchpoints}

若要在中建立行銷活動 [!DNL Salesforce]，導覽至 [!UICONTROL Campaigns] 標籤並選取「[!UICONTROL New]&#39;如下圖所示。 根據您的 [!DNL Salesforce] 設定，您可能需要按一下加號(+)圖示，將Campaigns新增至頂端列。

![](assets/3-3.png)

建立此行銷活動時，按一下「[!UICONTROL Enable Buyer Touchpoints]」欄位，並從選擇清單中選取下列其中一個選項：

![](assets/4-3.png)

* **包含所有行銷活動成員**
   * 此選項會啟用 [!DNL Marketo Measure] 將接觸點歸因於每個行銷活動成員。

* **包含「已回應」的行銷活動成員。**
   * 此選項會將接觸點套用至狀態為「已回應」的行銷活動成員。

* **排除所有行銷活動成員。**
   * 此選項不會將接觸點歸因於行銷活動中的任何成員，並作為故意將行銷活動排除在外的標幟 [!DNL Marketo Measure]. 如果您曾經在意外情況下將促銷活動與購買者接觸點同步，您可以將狀態變更為「排除所有促銷活動成員」，且接觸點將會移除。

一旦選擇其中一個， [!DNL Marketo Measure] 會為每位行銷活動會員指派一個接觸點（如適用）。 新增至行銷活動的銷售機會或聯絡人 _必須_ 擁有與其記錄關聯的電子郵件地址，以便 [!DNL Marketo Measure] 以建立接觸點。 如果沒有電子郵件地址， [!DNL Marketo Measure] 不會將接觸點指派給行銷活動成員。

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] 大學：對應離線頻道](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c630eca34d9f0367662b77f)
>
>[[!DNL Marketo Measure] University：促銷活動物件欄位](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63007334d9f0367662b758)
