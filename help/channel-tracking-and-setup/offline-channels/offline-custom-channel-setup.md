---
unique-page-id: 18874598
description: 離線自訂通道設定 —  [!DNL Marketo Measure]  — 產品檔案
title: 離線自訂通道設定
exl-id: c5697714-1a79-40bd-8b7c-e10768f4ef67
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '880'
ht-degree: 0%

---

# 離線自訂通道設定 {#offline-custom-channel-setup}

## 快速入門 {#getting-started}

與 [!DNL Marketo Measure] 處理線上管道規則時，您會發現離線管道規則不需要使用試算表。 不過，實作計畫中仍會提供工作表，因為這有助於思考您組織離線管道的方式。

試算表包含三欄：

![](assets/1-2.png)

**[!UICONTROL Salesforce]促銷活動類型**  — 新增在中識別的促銷活動類型 [!DNL Salesforce] 此處

* 例如，這可以是電子郵件、網路研討會、會議，或您為此欄位建立的任何值，您要將接觸點歸因於這些值。

**[!UICONTROL Channel]**  — 在此處新增各種行銷管道

**[!UICONTROL Subchannel]**  — 在此處新增任何對應的子頻道

## 離線頻道邏輯 {#offline-channel-logic}

[!DNL Marketo Measure] 離線通道邏輯由Campaign物件決定，尤其是 [!DNL Salesforce] 促銷活動類型。 每個離線工作都必須有 [!DNL Salesforce] 促銷活動類型，例如晚餐或商展，因為 [!DNL Marketo Measure] 依賴此欄位來了解要映射的通道和子通道。

SFDC促銷活動類型會顯示在「離線管道」的標籤中，列於 [!DNL Salesforce] 促銷活動類型。 請注意 [!DNL Marketo Measure] 只能為與購買者接觸點相關聯的促銷活動導入SFDC促銷活動類型。

![](assets/2-2.png)

這是您可在 [!DNL Marketo Measure] 應用程式。 這可能需要在 [!DNL Marketo Measure] 應用程式，可在應用程式的「建立管道」區段中完成，如下圖所示。 需要為 [!DNL Marketo Measure] 了解在何處推送接觸點。 您可以決定要如何對應促銷活動類型。

![](assets/3-2.png)

## 管道對應範例 {#channel-mapping-example}

例如，假設您參加兩個 [!DNL Salesforce] 每年開會。 但是，每個會議都大不相同，且目標對象不重複。 你想知道兩者中哪一種能帶來更多價值。 在 [!DNL Salesforce] 環境中，您可將1月事件的促銷活動類型命名為「會議」，將管道命名為「[!DNL Salesforce]、」和子頻道「1月會議」。

現在，你也想在6月的會議上這樣做。 您認為，因為這也是一個會議，所以可以給它指定相同的促銷活動類型，在此例中是「會議」。 通道是相同的， [!DNL Salesforce]，而第二次會議的子頻道是「六月會議」。 從組織角度看，這是有意義的。 然而，這對 [!DNL Marketo Measure] 讀取和套用這些規則的邏輯，因為兩個促銷活動具有相同的促銷活動類型。 [!DNL Marketo Measure] 指令碼無法將資料從一個類型映射到兩個不同的子通道。 這表示您需要為每個子管道建立新的促銷活動類型，但子管道可以有相同的管道。

以下是邏輯範例， [!DNL Marketo Measure] 無法閱讀：

![](assets/4-2.png)

在上述案例中，您會想要建立唯一的促銷活動類型，因為您無法將相同的促銷活動類型對應至兩個不同的子管道。 相反地，您會想要設定不重複類型，如下所示：

![](assets/5-2.png)

任何現有的促銷活動類型皆必須包含在您的管道對應中，且應新增「NULL」作為管道。

需要一些時間才能進入 [!DNL Salesforce] 以決定您要納入的現有記錄類型的數量和性質，以及您是否需要根據上述資訊建立其他促銷活動。 填妥所有必要資訊後，即可上傳。

深入了解 [離線 [!DNL Salesforce] 促銷活動 [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md).

## 處理SFDC促銷活動以開展線上營銷工作 {#handling-sfdc-campaigns-for-online-marketing-efforts}

行銷團隊常會建立 [!DNL Salesforce] 追蹤各種數位行銷工作的行銷活動。 這種做法沒有問題；不過，請務必以不同方式處理這些促銷活動，例如直接郵件或會議等真正的離線促銷活動。 與數位事件（網站上發生的互動）相關的促銷活動，不應與同步 [!DNL Marketo Measure]. 同步這些促銷活動會導致接觸點重複，因為 [!DNL Marketo Measure] JavaScript已在追蹤線上工作。

處理線上活動促銷活動的另一個秘訣是對應 [!DNL Salesforce] 促銷活動類型設為NULL。 若要這麼做，請先在 [!DNL Marketo Measure] 標題為NULL的應用程式，如下圖所示。 這可在 [!DNL Marketo Measure] 應用程式底下 **建立管道** 區段。 當意外同步不應同步的促銷活動時，此功能會很有幫助。 查看分組在NULL下的所有項目，即可輕鬆找到促銷活動並修正同步狀態。

![](assets/6-2.png)

## 將離線管道規則輸入至應用程式 {#entering-your-offline-channel-rules-to-the-app}

使用自訂規則編輯並更新試算表後，下一步是在 [!DNL Marketo Measure] 應用程式 — 您實際上不會上傳離線管道的試算表。 反之，您會在選擇清單方塊中輸入資訊，如下圖所示。 您可以按一下 **[!UICONTROL Offline Channels]** 在 **[!UICONTROL Channels]** 區段。

![](assets/7-2.png)

>[!TIP]
>
>想要判斷 _when_ a [!DNL Salesforce] 促銷活動類型會被拉入 [!DNL Marketo Measure] 通道對應？ 只要前往 **[!UICONTROL Setup]** > **[!UICONTROL Campaigns]** > **[!UICONTROL Fields]** > **[!UICONTROL Type]**. 接著，您便可查看選取清單中的值，以及非使用中的值。 非使用中的項目不會在「 」中顯示為可選類型[!UICONTROL Offline Channels]」部分。 請注意，此程式可能需要幾分鐘到48小時的時間。

按一下 **[!UICONTROL Save]** 等你做完之後 [!DNL Marketo Measure] 會上傳變更並重新處理資料。

>[!MORELIKETHIS]
>
>* [[!DNL Marketo Measure] 大學：對應離線頻道](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c630eca34d9f0367662b77f)
>
>* [[!DNL Marketo Measure] 大學：同步離線促銷活動](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63286e34d9f0367662b78b)
>
>* [Marketo Engage計畫整合](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md#channel-mapping)

