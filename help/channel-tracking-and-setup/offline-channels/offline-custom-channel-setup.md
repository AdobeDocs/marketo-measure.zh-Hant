---
unique-page-id: 18874598
description: 離線自訂頻道設定 —  [!DNL Marketo Measure]
title: 離線自訂頻道設定
exl-id: c5697714-1a79-40bd-8b7c-e10768f4ef67
feature: Channels
source-git-commit: b84909fbb34a1d8f739ebeea3400ef8816e17d32
workflow-type: tm+mt
source-wordcount: '858'
ht-degree: 0%

---

# 離線自訂頻道設定 {#offline-custom-channel-setup}

## 快速入門 {#getting-started}

相較於[!DNL Marketo Measure]處理線上管道規則的方式，您會發現離線管道規則不需要使用試算表。 不過，實作計畫中仍會提供工作表，因為這樣有助於您思考要以何種方式組織離線頻道。

試算表包含三欄：

![](assets/1-2.png)

**[!UICONTROL Salesforce]行銷活動型別** — 在此新增[!DNL Salesforce]中識別的行銷活動型別

* 例如，這可能是電子郵件、網路研討會、會議，或您為此欄位建立的任何您想要歸因於接觸點的值。

**[!UICONTROL Channel]** — 在此新增您的各種行銷管道

**[!UICONTROL Subchannel]** — 在此新增任何對應的子管道

## 離線管道邏輯 {#offline-channel-logic}

[!DNL Marketo Measure]離線管道邏輯是由Campaign物件決定，尤其是[!DNL Salesforce]促銷活動型別。 每個離線工作都必須有[!DNL Salesforce]行銷活動型別，例如晚宴或商展，因為[!DNL Marketo Measure]依賴此欄位來瞭解要對應到哪個頻道和子頻道。

SFDC促銷活動型別會出現在離線頻道的標籤中，列在[!DNL Salesforce]促銷活動型別下。 請注意，[!DNL Marketo Measure]只能為具有相關聯購買者接觸點的行銷活動匯入SFDC行銷活動型別。

![](assets/2-2.png)

您可以在此處在[!DNL Marketo Measure]應用程式中建立管道/子管道對應。 這可能需要在[!DNL Marketo Measure]應用程式中建立新的管道和子管道，這項作業會在應用程式的「建立管道」區段中完成，如下圖所示。 需要為[!DNL Marketo Measure]建立新的管道和子管道，以瞭解要推送接觸點的位置。 您可以決定要如何對應行銷活動型別。

![](assets/3-2.png)

## 管道對應範例 {#channel-mapping-example}

例如，假設您每年出席兩個[!DNL Salesforce]會議。 然而，每個會議都大不相同，並且具有獨特的目標對象。 您希望瞭解這兩種方法中哪一種能帶來更多價值。 在您的[!DNL Salesforce]環境中，您可以為1月事件提供Campaign型別「會議」，將您的頻道命名為「[!DNL Salesforce]」，並將子頻道命名為「1月會議」。

現在，您要對六月會議執行相同的動作。 您認為，由於這也是一個會議，因此可為其指定相同的促銷活動型別，在此例中為「會議」。 頻道相同，[!DNL Salesforce]，而且此第二次會議的子頻道是「六月會議」。 從組織的角度來看，這是合理的。 但是，讀取和套用這些規則會讓[!DNL Marketo Measure]邏輯非常困惑，因為兩個行銷活動具有相同的行銷活動型別。 [!DNL Marketo Measure]指令碼無法將一個型別的資料對應到兩個不同的子管道。 這表示您需要為每個子管道建立新的「行銷活動型別」，但子管道可以有相同的管道。

以下是[!DNL Marketo Measure]無法讀取的邏輯範例：

![](assets/4-2.png)

在上述案例中，您將需要建立唯一的促銷活動型別，因為您無法將相同的促銷活動型別對應至兩個不同的子管道。 而是要設定如下的唯一型別：

![](assets/5-2.png)

管道地圖中必須包含任何現有的行銷活動型別，且應將「NULL」新增為管道。

請花點時間進入[!DNL Salesforce]，以決定要納入的現有記錄型別的數目和性質，以及是否需要根據上述資訊建立其他行銷活動。 填寫完所有必要資訊後，即可上傳。

深入瞭解[離線同步 [!DNL Salesforce] 與 [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md)的促銷活動。

## 處理線上行銷工作的SFDC行銷活動 {#handling-sfdc-campaigns-for-online-marketing-efforts}

行銷團隊通常會建立[!DNL Salesforce]個行銷活動以追蹤各種數位行銷工作。 此做法沒有問題；不過，請務必以不同方式處理這些行銷活動，例如直接郵件或會議等真正的離線行銷活動。 與數位事件（在您網站上發生的互動）相關的行銷活動不應與[!DNL Marketo Measure]同步。 同步這些行銷活動會導致接觸點重複，因為[!DNL Marketo Measure] JavaScript已在追蹤線上工作。

處理線上活動行銷活動的另一個秘訣是將行銷活動型別[!DNL Salesforce]對應至NULL。 若要這麼做，請先在標題為NULL的[!DNL Marketo Measure]應用程式中建立頻道，如下圖所示。 您可以在&#x200B;**建立管道**&#x200B;區段下的[!DNL Marketo Measure]應用程式中找到此專案。 在不應同步的行銷活動意外同步時，此方法將有所幫助。 透過檢視一切在NULL下分組，很容易找到行銷活動並更正同步狀態。

![](assets/6-2.png)

## 在應用程式中輸入離線管道規則 {#entering-your-offline-channel-rules-to-the-app}

當您使用自訂規則編輯並更新試算表後，下一步就是在[!DNL Marketo Measure]應用程式中重新建立此管道對應 — 您實際上並不會上傳離線管道的試算表。 而是要在選取清單方塊中輸入資訊，如下圖所示。 按一下&#x200B;**[!UICONTROL Channels]**&#x200B;區段下的&#x200B;**[!UICONTROL Offline Channels]**&#x200B;即可找到此專案。

![](assets/7-2.png)

>[!TIP]
>
>想要決定&#x200B;_何時_&#x200B;將[!DNL Salesforce]行銷活動型別提取到[!DNL Marketo Measure]管道對應中？ 前往「**[!UICONTROL Setup]** > **[!UICONTROL Campaigns]** > **[!UICONTROL Fields]** > **[!UICONTROL Type]**」。 然後您可以檢視哪些值在挑選清單中，以及哪些為非作用中。 非作用中專案不會在&quot;[!UICONTROL Offline Channels]&quot;區段中顯示為可選取的型別。 請注意，此程式可能需要幾分鐘到48小時的時間。

完成時按一下「**[!UICONTROL Save]**」，[!DNL Marketo Measure]將上傳變更並重新處理資料。

>[!MORELIKETHIS]
>
>* [[!DNL Marketo Measure] Tutorials：對應離線頻道](https://experienceleague.adobe.com/zh-hant/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/mapping-offline-channels){target="_blank"}
>
>* [[!DNL Marketo Measure] Tutorials：同步處理離線行銷活動](https://experienceleague.adobe.com/zh-hant/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/syncing-offline-campaigns){target="_blank"}
>
>* [Marketo Engage程式整合](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md#channel-mapping){target="_blank"}
