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

比較方式 [!DNL Marketo Measure] 處理線上管道規則，您會發現離線管道規則不需要使用試算表。 不過，實作計畫中仍會提供工作表，因為這樣有助於您思考要以何種方式組織離線頻道。

試算表包含三欄：

![](assets/1-2.png)

**[!UICONTROL Salesforce]行銷活動型別**  — 新增中識別的行銷活動型別 [!DNL Salesforce] 此處

* 例如，這可能是電子郵件、網路研討會、會議，或您為此欄位建立的任何您想要歸因於接觸點的值。

**[!UICONTROL Channel]**  — 在此新增您的各種行銷管道

**[!UICONTROL Subchannel]**  — 在此新增任何對應的子管道

## 離線管道邏輯 {#offline-channel-logic}

[!DNL Marketo Measure] 離線管道邏輯由Campaign物件決定，尤其是 [!DNL Salesforce] 行銷活動型別。 每個離線工作量必須有 [!DNL Salesforce] 行銷活動型別，例如晚宴或商展，因為 [!DNL Marketo Measure] 仰賴此欄位來瞭解將對應至哪個管道和子管道。

SFDC促銷活動型別會出現在離線頻道的標籤中，列於下方 [!DNL Salesforce] 行銷活動型別。 請注意 [!DNL Marketo Measure] 只能為具有相關聯購買者接觸點的行銷活動匯入SFDC行銷活動型別。

![](assets/2-2.png)

您可以在此處建立管道/子管道對應，於 [!DNL Marketo Measure] 應用程式。 這可能需要在中建立新的管道和子管道。 [!DNL Marketo Measure] 此動作會在應用程式的「建立色版」區段中完成，如下圖所示。 需要為建立新的管道和子管道 [!DNL Marketo Measure] 以瞭解將接觸點推送至何處。 您可以決定要如何對應行銷活動型別。

![](assets/3-2.png)

## 管道對應範例 {#channel-mapping-example}

舉例來說，假設您參加 [!DNL Salesforce] 每年開會。 然而，每個會議都大不相同，並且具有獨特的目標對象。 您希望瞭解這兩種方法中哪一種能帶來更多價值。 在您的 [!DNL Salesforce] 環境，您可以為1月事件提供Campaign型別「會議」，為您的頻道命名「[!DNL Salesforce]，以及您的子頻道「1月會議」。

現在，您要對六月會議執行相同的動作。 您認為，由於這也是一個會議，因此可為其指定相同的促銷活動型別，在此例中為「會議」。 通道是相同的， [!DNL Salesforce]，而此第二次會議的子頻道為「六月會議」。 從組織的角度來看，這是合理的。 然而，這讓人非常困惑 [!DNL Marketo Measure] 邏輯來讀取和套用這些規則，因為兩個行銷活動具有相同的行銷活動型別。 [!DNL Marketo Measure] 指令碼無法將一個型別的資料對應到兩個不同的子管道。 這表示您需要為每個子管道建立新的「行銷活動型別」，但子管道可以有相同的管道。

以下是邏輯的範例， [!DNL Marketo Measure] 無法讀取：

![](assets/4-2.png)

在上述案例中，您將需要建立唯一的促銷活動型別，因為您無法將相同的促銷活動型別對應至兩個不同的子管道。 而是要設定如下的唯一型別：

![](assets/5-2.png)

管道地圖中必須包含任何現有的行銷活動型別，且應將「NULL」新增為管道。

請花點時間進入 [!DNL Salesforce] 以決定要納入的現有記錄型別的數量和性質，以及是否需要根據上述資訊建立其他行銷活動。 填寫完所有必要資訊後，即可上傳。

進一步瞭解 [離線同步 [!DNL Salesforce] 行銷活動與 [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md).

## 處理線上行銷工作的SFDC行銷活動 {#handling-sfdc-campaigns-for-online-marketing-efforts}

行銷團隊通常會建立 [!DNL Salesforce] 行銷活動，以追蹤各種數位行銷工作。 此做法沒有問題；不過，請務必以不同方式處理這些行銷活動，例如直接郵件或會議等真正的離線行銷活動。 與數位事件（在您網站上發生的互動）相關的行銷活動不應與同步 [!DNL Marketo Measure]. 同步這些行銷活動會導致接觸點重複，因為 [!DNL Marketo Measure] JavaScript已在追蹤線上工作。

處理線上活動行銷活動的另一個秘訣是對應 [!DNL Salesforce] 促銷活動型別設為NULL。 若要這麼做，請先在中建立管道 [!DNL Marketo Measure] 應用程式標題為NULL，如下圖所示。 此專案位於 [!DNL Marketo Measure] 下的應用程式 **建立頻道** 區段。 在不應同步的行銷活動意外同步時，此方法將有所幫助。 透過檢視一切在NULL下分組，很容易找到行銷活動並更正同步狀態。

![](assets/6-2.png)

## 在應用程式中輸入離線管道規則 {#entering-your-offline-channel-rules-to-the-app}

當您使用自訂規則編輯和更新試算表後，下一步就是在 [!DNL Marketo Measure] 應用程式 — 您實際上並不會上傳離線頻道的試算表。 而是要在選取清單方塊中輸入資訊，如下圖所示。 按一下「 」即可找到它 **[!UICONTROL Offline Channels]** 在 **[!UICONTROL Channels]** 區段。

![](assets/7-2.png)

>[!TIP]
>
>想要決定 _當_ a [!DNL Salesforce] 行銷活動型別被提取到 [!DNL Marketo Measure] 頻道對應？ 前往 **[!UICONTROL Setup]** > **[!UICONTROL Campaigns]** > **[!UICONTROL Fields]** > **[!UICONTROL Type]**. 然後您可以檢視哪些值在挑選清單中，以及哪些為非作用中。 非作用中專案不會顯示為我們的&quot;[!UICONTROL Offline Channels]「 」區段。 請注意，此程式可能需要幾分鐘到48小時的時間。

按一下 **[!UICONTROL Save]** 當您完成並 [!DNL Marketo Measure] 將上傳變更並重新處理資料。

>[!MORELIKETHIS]
>
>* [[!DNL Marketo Measure] Tutorials：對應離線頻道](https://experienceleague.adobe.com/en/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/mapping-offline-channels){target="_blank"}
>
>* [[!DNL Marketo Measure] Tutorials：同步離線行銷活動](https://experienceleague.adobe.com/en/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/syncing-offline-campaigns){target="_blank"}
>
>* [Marketo Engage計畫整合](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md#channel-mapping){target="_blank"}
