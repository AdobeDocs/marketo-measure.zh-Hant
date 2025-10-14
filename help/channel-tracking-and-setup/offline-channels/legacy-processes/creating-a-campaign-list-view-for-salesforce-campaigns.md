---
unique-page-id: 18874718
description: 正在建立 [!DNL Salesforce Campaigns] - [!DNL Marketo Measure]的行銷活動清單檢視
title: 建立 [!DNL Salesforce] 行銷活動的行銷活動清單檢視
exl-id: 8c673ea3-ac24-4b3d-b67d-76888179c07a
feature: Channels
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# 建立[!DNL Salesforce]行銷活動的行銷活動清單檢視 {#creating-a-campaign-list-view-for-salesforce-campaigns}

瞭解如何針對您要與購買者接觸點同步的促銷活動建立「清單檢視」 。

>[!NOTE]
>
>本文會介紹過時的程式。 我們鼓勵使用者使用[新的、改良的應用程式內程式](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"}。

可建立的行銷活動清單檢視可讓您擁有「前往」位置來檢視及管理「型別」和「啟用購買者接觸點」欄位，以確保通知您離線行銷管道的每個[!DNL Salesforce]行銷活動皆已正確設定。

1. 前往[!DNL Salesforce]中的「行銷活動」索引標籤，並建立新的清單檢視
1. 將檢視命名為「要與[!DNL Marketo Measure]同步的促銷活動」。
1. 我們希望此清單只顯示我們要與[!DNL Marketo Measure]同步的那些行銷活動，因此我們需要幾個篩選器：

   * **型別** [等於] &#39;我們已對應至您的離線管道的所有行銷活動型別&#39;。 請參閱您的實作計畫或[!DNL Marketo Measure]中的「離線頻道」索引標籤([experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} ->我的帳戶 — >設定 — >離線頻道)。 您可以透過放大鏡圖示選取您想要的型別（已對應至離線行銷管道的型別）。

      * 每個篩選器最多選擇3種型別。 篩選欄位中的字元數量存在限制。 從每個篩選器3個型別開始，並視需要新增額外的「型別」篩選器列。

   * **建立日期** [大於或等於]您的[!DNL Marketo Measure]開始日期。 您可以在[!DNL Marketo Measure]應用程式的ROI儀表板中找到您的開始日期。 只要在虛線的日期範圍中選取「自從建立日期」，它就會顯示您的開始日期。
   * **&#42;記錄型別&#42;** — 若要在清單檢視中進行編輯，您必須為記錄型別新增篩選器。 您可能需要編輯的每個行銷活動記錄都需要相同記錄型別。

1. 編輯您選取的欄位以顯示於清單檢視中。 清單檢視的完整設定看起來應該像下面的範例：

   此檢視可讓您檢視行銷活動，並視需要編輯「型別」和「啟用購買者接觸點」欄位。 當您建立應與[!DNL Marketo Measure]同步的新行銷活動時，它們會出現在此檢視中，而且您可以直接從清單中管理這些行銷活動的所有設定。

   若要從清單檢視進行內嵌編輯，您必須確定在[!DNL Salesforce]設定中下列專案也為true：

   * **[!UICONTROL Setup]** > **[!UICONTROL User Interface]** > **[!UICONTROL Enable Inline Editing]**
   * 也需啟用已核取的增強型清單（位於內嵌編輯的方塊下方）
   * 確定具有欄位的許可權

>[!MORELIKETHIS]
>
>[排解清單檢視內嵌編輯的常見問題](http://help.salesforce.com/articleView?id=000003911&language=en_US&type=1){target="_blank"}
