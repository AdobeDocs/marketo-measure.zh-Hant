---
unique-page-id: 18874602
description: 行銷管道成本 —  [!DNL Marketo Measure]  — 產品檔案
title: 行銷管道成本
exl-id: 36ccaff3-db55-47bd-a24e-4aa1894f13e0
feature: Channels, Spend Management
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '1279'
ht-degree: 0%

---

# 行銷管道成本 {#marketing-channel-costs}

使用最基本的好處之一 [!DNL Marketo Measure] 是將行銷工作直接連結至對收入之影響的能力，並擁有所需詳細程度。 您可以在接觸點層級看到投資報酬率。 若要利用這項優點，只需將管道成本上傳至 [!DNL Marketo Measure] 應用程式。 ROI報告會自動建立，並可在以下位置使用： **行銷ROI控制面板** 在 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}.

[按一下這裡直接導覽至指示。](/help/marketing-spend/spend-management/marketing-channel-costs.md#uploading-marketing-costs)

此 [!DNL Marketo Measure] 「行銷支出」功能可讓客戶跨所有管道、子管道和行銷活動上傳其支出。 客戶新增的資料越多，我們就能在收入歸因控制面板中顯示越多的ROI報表。

從直接廣告連線中報告和匯入的成本會在最精細的層級自動提取，無需上傳。 這包括我們目前與Google AdWords、Bing Ads、Doubleclick和Facebook的整合。

[按一下這裡直接導覽至常見問答集。](/help/marketing-spend/spend-management/marketing-channel-costs.md#faq)

## 定義 {#definitions}

**依據行銷活動的支出**

在最精細的層級，客戶可以依個別行銷活動輸入支出，並在其個別頻道中分組。 對於CRM Campaigns， [!DNL Marketo Measure] 已將Campaign ID提取至單獨的欄，以協助您將離線行銷活動支出從CRM對應至此表格。 在此層級新增支出，可讓客戶檢視Campaign ROI並依Campaign最佳化效能。

所有行銷活動的總計不需要加總至在子管道或管道輸入的任何值，但不能超過在子管道或管道輸入的任何值。 如果總和小於在子頻道或頻道中輸入的值， [!DNL Marketo Measure] 會自動為「其他」新增一列，以彌補差異並填滿任何間隙。

**依據子管道的支出**

在更高的層級，客戶可以按子管道輸入支出，分組在它的管道下。 在此層級新增支出，可讓客戶檢視子管道ROI，並依子管道最佳化效能。

所有子管道的總和不需要加總為在「管道」輸入的任何值，但不能超過在「管道」輸入的任何值。 如果總和小於在頻道輸入的值， [!DNL Marketo Measure] 會自動為「其他」新增一列，以彌補差異並填滿任何間隙。

**依據管道的支出**

最高層級的客戶可以依管道輸入支出。 在此層級增加支出，可讓客戶檢視管道ROI，並依管道最佳化效能。

**日期選取器**

預設日期範圍將從您的開始日期開始，包含 [!DNL Marketo Measure] 直到當月。 為確保成本保持正確，您無法輸入未來月份的成本，但您可在與合作之前輸入月份的成本 [!DNL Marketo Measure].

**篩選**

若要縮小「行銷支出」表格中的結果，選取頂端的「管道」以篩選掉其他管道。 如果您的團隊聚焦於單一管道，這會很有幫助。

**搜尋**

使用「搜尋」方塊，從「頻道」、「子頻道」或「促銷活動」中尋找相符的文字。

**下載目前成本**

下載的CSV將從您目前的畫面提取結果，這表示任何套用的日期、篩選器或搜尋都將依原樣下載。

**上傳CSV**

無論瀏覽器中的檢視是什麼，如果它是篩選檢視或包含所有日期和管道的預設檢視，您都可以上傳任何CSV。

我們面臨的最常見錯誤是日期欄的格式，如果日期格式改變，就會發生此錯誤，而且在Excel和/或Google工作表之間移動時可能會有意發生。 請記得日期應為MM-YY，因此Sep-12而非Sep-12，或May-12而非05-12。

## 開始之前 {#before-you-begin}

[!DNL Marketo Measure] 隨附有13個可使用或展開的預設管道。 此外，最多可建立40個線上和離線管道，以因應您獨特的行銷結構。 在此基礎上可建立總計200個子管道，以支援這些線上和離線管道。

[!DNL Marketo Measure] 會自動從與API整合的平台(例如Bing Ads和Google AdWords)下載行銷管道成本。 未與整合的平台成本 [!DNL Marketo Measure] 需要手動上傳。 行銷管道應於成本資料上傳前完成設定。

## 上傳行銷成本 {#uploading-marketing-costs}

一旦行銷管道和規則設定或更新後，相關成本便可上傳。 請依照下列步驟以執行此操作：

**步驟1：導覽至「 」中的「行銷支出」頁面 [!DNL Marketo Measure] 應用程式。**

前往 **[!UICONTROL My Account]** 功能表，按一下 **[!UICONTROL Settings]** 然後導覽至 **[!UICONTROL Marketing Spend]** 左側邊欄中的選項 **[!UICONTROL Reporting]** 區段。

![](assets/1.png)

**步驟2：下載目前成本CSV**

導覽至畫面右側，然後按一下 **[!UICONTROL Download Current Costs].** 此選項可讓您下載CSV格式的試算表。

![](assets/2.png)

**步驟3：開啟CSV檔案並進行變更**

您可以匯入檔案，並使用Google Sheets、Apple Numbers、Microsoft Excel或您選擇的軟體來開啟檔案。 [!DNL Marketo Measure] 建議使用Google工作表。

匯入工作表之後，進行所需的變更，例如將成本新增至管道和子管道，或更新現有資訊。

檢查工作表中的邏輯規則。 每一列應包含一個色版及其其中一個子色版，以(.)分隔 點在結尾。 請務必堅持使用此格式。

例如，若要將Facebook標示為子管道，將social標示為管道，則規則應編寫如下：「Social.Facebook」。 同樣地，若要追蹤離線事件，管道語法應為：&quot;Events.Big Conference&quot;。 範例如下圖所示：

![](assets/3.png)

_其他附註_：

請勿修改試算表中的日期，因為這會在上傳檔案時發生問題。

請勿將任何欄位留空。 即使沒有可新增的美元值，請輸入$0作為美元金額。

您不需要輸入或更新Bing Ads和Google AdWords成本，因為 [!DNL Marketo Measure] 自動從這些平台的API連線提取此資料。

**步驟4：將檔案儲存為CSV格式**

如果您使用Google Sheets，請務必先下載檔案。 請勿排除或刪除任何每月資料，因為嘗試將CSV檔案上傳到會造成困難 [!DNL Marketo Measure] 稍後。

**步驟5：上傳CSV檔案**

前往 **[!UICONTROL Cost]** 的區段 [!DNL Marketo Measure] 應用程式並按一下 **[!UICONTROL Upload.CSV]**. 系統將重新整理並反映新資訊。

## 常見問題集 {#faq}

**為什麼數字會出現在CSV中**

如果未在較高層級（如頻道或子頻道）輸入值， [!DNL Marketo Measure] 會自動為您加總子項層級，您的檔案上傳後就會顯示子項層級。 此外，如果子系的總和小於為父系輸入的值， [!DNL Marketo Measure] 將新增「其他」列以顯示總數中的差異。

**我看到的清單是如何決定行銷活動的？**

目前，我們的結果會列出我們已看到獲得接觸點評分的行銷活動。 如果行銷活動中有活動，我們會根據發生的接觸點日期顯示該行銷活動。

**要篩選的列和欄太多 — 我可以合併檢視嗎？**

您可以變更日期範圍、篩選管道或搜尋值，藉此合併表格結果以更符合您的需求。

**為何無法上傳檔案？**

我們在「 」中有不同的許可權集 [!DNL Marketo Measure] 應用程式。 若要上傳檔案，您必須是「帳戶管理員」。 若要解決此問題，請向您的帳戶管理員請求存取權，或請您的帳戶管理員代表您上傳檔案。 使用者及其角色的清單可在下找到 **[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL View/Add Account Users]**.
