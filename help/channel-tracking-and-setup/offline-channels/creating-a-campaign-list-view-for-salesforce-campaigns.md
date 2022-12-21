---
unique-page-id: 18874718
description: 建立促銷活動清單檢視 [!DNL Salesforce Campaigns] - [!DNL Marketo Measure]  — 產品檔案
title: 建立促銷活動清單檢視 [!DNL Salesforce] 行銷活動
exl-id: 8c673ea3-ac24-4b3d-b67d-76888179c07a
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---

# 建立促銷活動清單檢視 [!DNL Salesforce] 行銷活動 {#creating-a-campaign-list-view-for-salesforce-campaigns}

了解如何為您想要與購買者接觸點同步的促銷活動建立清單檢視。

可建立的促銷活動清單檢視可讓您有「轉至」位置來檢視及管理「類型」和「啟用購買者接觸點」欄位，以確保您的每個 [!DNL Salesforce] 可正確設定通知離線行銷管道的行銷活動。

1. 標題至 [!DNL Salesforce] 和建立新清單視圖
1. 將檢視命名為「要同步的促銷活動」 [!DNL Marketo Measure].&quot;
1. 我們希望此清單只顯示我們想要同步的促銷活動 [!DNL Marketo Measure] 因此，我們需要一些篩選條件：

   * **類型** [等於] 「我們已對應至離線頻道的所有促銷活動類型」。 請參閱您的實作計畫或離線頻道標籤，位於 [!DNL Marketo Measure] ([experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target=&quot;_blank&quot;} ->我的帳戶 — >設定 — >離線頻道)。 您可以透過放大鏡圖示選取您想要的類型（對應至離線行銷管道的類型）。

      * 每個篩選器最多選擇3個類型。 篩選欄位中可以有字元數限制。 從每個篩選器的3個類型開始，並視需要新增其他「類型」篩選器列。
   * **建立日期** [大於或等於] 您的 [!DNL Marketo Measure] 開始日期。 您可以在ROI控制面板中的 [!DNL Marketo Measure] 應用程式。 只要在破折號的日期範圍中選取「自建立日期起」，就會顯示您的開始日期。
   * **&#42;記錄類型&#42;**  — 若要在「清單檢視」中進行編輯，您需要為「記錄類型」新增篩選器。 您可能需要編輯的每個促銷活動記錄都必須是相同的記錄類型。


1. 編輯要在清單檢視中顯示的選定欄位。 清單檢視的完整設定應如下所示：

   此檢視可讓您查看您的促銷活動，並視需要編輯「類型」和「啟用購買者接觸點」欄位。 當您建立應與同步的新促銷活動時 [!DNL Marketo Measure]，它們會出現在此檢視中，而您可以直接從清單中管理這些促銷活動的所有設定。

   若要從「清單檢視」進行內嵌編輯，您必須確定下列項目在您的 [!DNL Salesforce] 設定：

   * **[!UICONTROL Setup]** > **[!UICONTROL User Interface]** > **[!UICONTROL Enable Inline Editing]**
   * 還需要勾選「啟用增強清單」（位於內嵌編輯方塊的下方）
   * 請務必擁有欄位的權限

>[!MORELIKETHIS]
>
>[疑難排解清單檢視內嵌編輯的常見問題](http://help.salesforce.com/articleView?id=000003911&amp;language=en_US&amp;type=1){target=&quot;_blank&quot;}
