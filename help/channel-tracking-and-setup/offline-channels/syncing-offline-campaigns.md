---
unique-page-id: 18874600
description: 同步離線促銷活動 —  [!DNL Marketo Measure]  — 產品檔案
title: 同步離線促銷活動
exl-id: a6f9e217-ff6e-474d-9f14-c6f6238c9e84
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 0%

---

# 同步離線促銷活動 {#syncing-offline-campaigns}

很難準確追蹤離線促銷活動，並了解它們與您的數位行銷活動有何不同。 [!DNL Marketo Measure] 可讓您在 [!DNL Salesforce]，即使在 [!DNL Salesforce] 要等到事件發生幾週後才會建立促銷活動。

## 同步之前 {#before-you-sync}

以下提供一些有效同步程式的秘訣：

* 離線促銷活動是指未線上發生的行銷互動。 這些包括活動、網路研討會和商展等行銷管道。 僅包含離線行銷活動。
* 如果您想要納入在安裝之前追蹤線上活動的促銷活動 [!DNL Marketo Measure]，請務必將「接觸點結束日期」設為在您網站上部署JavaScript的日期。
* 保留 [!DNL Marketo Measure] 在「離線管道」頁面上開啟應用程式，以便輕鬆識別不同的促銷活動類型，以及接觸點將分組到的行銷管道。

* 在點擊「[!UICONTROL Save]&quot;按鈕！

## 大量更新接觸點日期 {#bulk-update-touchpoint-date}

在 [!DNL Salesforce]，則促銷活動成員物件上的建立日期欄位會注意促銷活動成員新增至促銷活動的日期。 為了讓同步程式順利進行，請確定「購買者接觸點日期欄位」與「Salesforce促銷活動成員物件」上的日期相同。 此步驟是使用「[!UICONTROL Bulk Update Touchpoint Date button],&quot; _befor_ 選取 [!UICONTROL picklist] 選項（在「啟用購買者接觸點」欄位中）。

為什麼這很重要？ 想像一下，你的公司在1月的一個會議上贊助了一個展位。 在會議上，100人對您的產品表示了興趣，並提供了他們的聯繫資訊以接收電子郵件更新。 三週後，您終於在 [!DNL Salesforce] 跟蹤會議結果。

您的上傳日期會比會議日期晚三週。 若要修正此差異， [!UICONTROL Bulk Update Touchpoint Date] 按鈕來設定適當的日期。 下圖顯示按鈕。

![](assets/1-3.png)

在此情況下，它會以三週回填上傳日期。 此步驟應在設定「[!UICONTROL Enable Buyer Touchpoints]」欄位。

總之，如果您使用 [!UICONTROL Bulk Update Touchpoint Date] 按鈕，並將接觸點日期變更為事件日期， [!DNL Marketo Measure] 會為事件的實際日期（而非上傳日期）產生接觸點。

您也可以更新現有促銷活動上所有促銷活動成員的日期。 執行此操作時，請確定接觸點的日期是成員互動的日期。 只需按一下大量更新購買者接觸點日期，視需要篩選促銷活動成員清單，並在[!UICONTROL Select Date]「 」選項，新增與事件發生日期相同的日期。

>[!CAUTION]
>
>請務必更新接觸點日期 _befor_ 您會為所有促銷活動成員啟用接觸點。

![](assets/2-3.png)

## 如何建立促銷活動及同步購買者接觸點 {#how-to-create-a-campaign-and-sync-buyer-touchpoints}

若要在 [!DNL Salesforce]，導覽至 [!UICONTROL Campaigns] 頁簽和選擇&#39;[!UICONTROL New]&#39;，如下圖所示。 視您的 [!DNL Salesforce] 設定時，您可能需要按一下加號(+)圖示，將「促銷活動」新增至頂端列。

![](assets/3-3.png)

建立此促銷活動時，請按一下[!UICONTROL Enable Buyer Touchpoints]「 」欄位，並從選擇清單中選取下列其中一個選項：

![](assets/4-3.png)

* **包含所有促銷活動成員**
   * 此選項啟用 [!DNL Marketo Measure] 將接觸點歸因至每個促銷活動成員。

* **包含「已回應」促銷活動成員。**
   * 此選項會將接觸點套用至狀態為「已回應」的促銷活動成員。

* **排除所有促銷活動成員。**
   * 此選項不會將接觸點歸因於促銷活動中的任何成員，並作為促銷活動被有意排除的標幟 [!DNL Marketo Measure]. 如果您意外將促銷活動與購買者接觸點同步，您可以將狀態變更為「排除所有促銷活動成員」，接觸點將會移除。

一旦選擇了其中一個選項， [!DNL Marketo Measure] 會為每個促銷活動成員指派一個接觸點（若適用）。 新增至促銷活動的銷售機會或連絡人 _必須_ 有與其記錄相關聯的電子郵件地址，以便 [!DNL Marketo Measure] 來建立接觸點。 沒有電子郵件地址， [!DNL Marketo Measure] 不會將接觸點指派給促銷活動成員。

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] 大學：對應離線頻道](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c630eca34d9f0367662b77f)
>
>[[!DNL Marketo Measure] 大學：促銷活動物件欄位](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63007334d9f0367662b758)
