---
unique-page-id: 18874718
description: 建立行銷活動清單檢視 [!DNL Salesforce Campaigns] - [!DNL Marketo Measure]  — 產品檔案
title: 建立行銷活動清單檢視 [!DNL Salesforce] 行銷活動
exl-id: 8c673ea3-ac24-4b3d-b67d-76888179c07a
feature: Channels
source-git-commit: e01738222e8845112892c0258cb084a4f0ebb257
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---

# 建立行銷活動清單檢視 [!DNL Salesforce] 行銷活動 {#creating-a-campaign-list-view-for-salesforce-campaigns}

瞭解如何針對您要與購買者接觸點同步的促銷活動建立「清單檢視」 。

>[!NOTE]
>
>本文會介紹過時的程式。 我們鼓勵使用者使用 [新的、改良的應用程式內程式](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"}.

可建立的Campaign清單檢視可讓您擁有「前往」位置，以檢視和管理「型別」和「啟用購買者接觸點」欄位，以確保 [!DNL Salesforce] 已正確設定通知離線行銷管道的行銷活動。

1. 前往中的行銷活動標籤 [!DNL Salesforce] 並建立新的清單檢視
1. 將檢視命名為「要同步處理的行銷活動」 [!DNL Marketo Measure].」
1. 我們希望此清單只顯示我們要同步處理的行銷活動 [!DNL Marketo Measure] 因此我們需要幾個篩選器：

   * **型別** [等於] 「我們已對應至您的離線頻道的所有Campaign型別」。 請參閱您的實作計畫或中的「離線頻道」索引標籤 [!DNL Marketo Measure] ([experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} ->我的帳戶 — >設定 — >離線頻道)。 您可以透過放大鏡圖示選取您想要的型別（已對應至離線行銷管道的型別）。

      * 每個篩選器最多選擇3種型別。 篩選欄位中的字元數量存在限制。 從每個篩選器3個型別開始，並視需要新增額外的「型別」篩選器列。

   * **建立日期** [大於或等於] 您的 [!DNL Marketo Measure] 開始日期。 您可以在ROI控制面板的 [!DNL Marketo Measure] 應用程式。 只要在虛線的日期範圍中選取「自從建立日期」，它就會顯示您的開始日期。
   * **&#42;記錄型別&#42;**  — 若要在「清單檢視」中進行編輯，您必須新增「記錄型別」的篩選器。 您可能需要編輯的每個行銷活動記錄都需要相同記錄型別。

1. 編輯您選取的欄位以顯示於清單檢視中。 清單檢視的完整設定看起來應該像下面的範例：

   此檢視可讓您檢視行銷活動，並視需要編輯「型別」和「啟用購買者接觸點」欄位。 當您建立應與其同步的新行銷活動時 [!DNL Marketo Measure]，這些設定會顯示在此檢視中，而您可以直接從清單中管理這些行銷活動的所有設定。

   若要從清單檢視進行內嵌編輯，您必須確定在 [!DNL Salesforce] 設定：

   * **[!UICONTROL Setup]** > **[!UICONTROL User Interface]** > **[!UICONTROL Enable Inline Editing]**
   * 也需啟用已核取的增強型清單（位於內嵌編輯的方塊下方）
   * 確定具有欄位的許可權

>[!MORELIKETHIS]
>
>[疑難排解清單檢視內嵌編輯的常見問題](http://help.salesforce.com/articleView?id=000003911&amp;language=en_US&amp;type=1){target="_blank"}
