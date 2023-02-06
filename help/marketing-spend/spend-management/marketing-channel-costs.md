---
unique-page-id: 18874602
description: 行銷管道成本 —  [!DNL Marketo Measure]  — 產品檔案
title: 行銷管道成本
exl-id: 36ccaff3-db55-47bd-a24e-4aa1894f13e0
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '1279'
ht-degree: 0%

---

# 行銷管道成本 {#marketing-channel-costs}

使用的最基本好處之一 [!DNL Marketo Measure] 能夠將行銷工作直接與對收入的影響聯繫起來，並盡可能精細。 在接觸點層級可以看到投資回報。 為了利用此優勢，渠道成本只需上傳至 [!DNL Marketo Measure] 應用程式。 ROI報表會自動建立，並可在 **行銷ROI儀表板** in [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}.

[按一下這裡直接導覽至指示。](/help/marketing-spend/spend-management/marketing-channel-costs.md#uploading-marketing-costs)

此 [!DNL Marketo Measure] 「行銷支出」功能可讓客戶跨所有管道、子管道和行銷活動上傳其支出。 客戶新增的資料越多，收入歸因控制面板中的ROI報表就越多。

從直接廣告連線報告和匯入的成本會在最精細的層級自動提取，而且不需要上傳。 這包括我們目前與Google AdWords、Bing Ads、Doubleclick和Facebook的整合。

[按一下這裡直接導覽至常見問題集。](/help/marketing-spend/spend-management/marketing-channel-costs.md#faq)

## 定義 {#definitions}

**依促銷活動支出**

在最精細的層級，客戶可依個別促銷活動輸入支出，並在其個別管道中分組。 對於CRM促銷活動， [!DNL Marketo Measure] 已將促銷活動ID提取至另一欄，可協助您將離線促銷活動支出從CRM對應至此表格。 在此層級增加支出可讓客戶檢視促銷活動ROI，並依促銷活動最佳化效能。

所有促銷活動的總計不需要加總至在子管道或管道中輸入的任何值，但不能超過在子管道或管道中輸入的任何值。 如果總和小於在子管道或管道中輸入的值， [!DNL Marketo Measure] 會自動為「其他」新增一列，以彌補差異並填滿任何間隙。

**按子管道支出**

在較高層級，客戶可依子管道輸入支出，並將其分組在其管道下。 在此級別增加支出將使客戶能夠查看子渠道ROI，並按子渠道優化效能。

所有子管道的總計不需要加總至在管道中輸入的任何值，但不能超過在管道中輸入的任何值。 如果總和小於在管道中輸入的值， [!DNL Marketo Measure] 會自動為「其他」新增一列，以彌補差異並填滿任何間隙。

**依管道支出**

在最高層，客戶可依管道輸入支出。 在此級別增加支出將使客戶能夠查看渠道ROI，並按渠道優化效能。

**日期選擇器**

預設日期範圍將從您的開始日期開始為 [!DNL Marketo Measure] 直到當月。 為確保成本保持正確，您無法輸入未來月份的成本，但您可以輸入與合作夥伴關係前幾個月的成本 [!DNL Marketo Measure].

**篩選**

若要在「行銷支出」表格中縮小結果，請選取頂端的「管道」，以篩選掉其他管道。 如果您的團隊專注於單一管道，這個功能會很好用。

**搜尋**

使用「搜尋」方塊，從「管道」、「子管道」或「促銷活動」中尋找相符的文字。

**下載當前成本**

下載的CSV會從您目前的畫面中提取結果，這表示套用的任何日期、篩選器或搜尋都會依原樣下載。

**上傳CSV**

無論瀏覽器中是哪個檢視，如果是經過篩選的檢視，或是包含所有日期和管道的預設檢視，您都可以上傳任何CSV。

我們最常遇到的錯誤是日期欄的格式，這會在日期格式變更時發生，而且如果在Excel和/或Google工作表之間移動，可能會刻意發生。 請記住，日期應為MM-YY，因此應為9月12日，而非9月12日，或5月12日，而非05-12日。

## 開始之前 {#before-you-begin}

[!DNL Marketo Measure] 隨附13個預設管道，可供使用或擴充。 此外，還可建立最多40個線上和離線管道，以配合您獨特的行銷結構。 在此基礎上，可建立總計200個子頻道，以支援這些線上和離線頻道。

[!DNL Marketo Measure] 會從其具有API整合的平台(例如Bing Ads和Google AdWords)自動下載行銷管道成本。 未與整合的平台的成本 [!DNL Marketo Measure] 需要手動上傳。 上傳成本資料之前，應先設定行銷管道。

## 上傳行銷成本 {#uploading-marketing-costs}

設定或更新行銷管道和規則後，即可上傳相關成本。 若要這麼做，請遵循下列步驟：

**步驟1:導覽至 [!DNL Marketo Measure] 應用程式。**

前往 **[!UICONTROL My Account]** 按一下 **[!UICONTROL Settings]** 然後導覽至 **[!UICONTROL Marketing Spend]** 選項 **[!UICONTROL Reporting]** 區段。

![](assets/1.png)

**步驟2:下載目前成本CSV**

導覽至畫面右側，然後按一下 **[!UICONTROL Download Current Costs].** 此選項可讓您下載CSV格式的試算表。

![](assets/2.png)

**步驟3:開啟CSV檔案並進行變更**

您可以匯入檔案，並使用Google工作表、Apple編號、Microsoft Excel或您選擇的軟體來開啟它。 [!DNL Marketo Measure] 建議使用Google工作表。

導入工作表後，進行所需的更改，例如向管道和子管道添加成本或更新現有資訊。

檢查工作表中的邏輯規則。 每一列都應包含一個管道及其中一個子管道，以(.)分隔 最後點。 一致地使用此格式非常重要。

例如，若要將Facebook指定為子管道，將social指定為管道，應編寫如下規則：&quot;Social.Facebook&quot; 同樣地，若要追蹤離線事件，管道語法應為：「Events.Big Conference」 範例如下圖所示：

![](assets/3.png)

_其他附註_:

請勿修改試算表中的日期，因為這可能在上傳檔案時造成問題。

請勿將任何欄位留空。 即使沒有要添加的美元值，也輸入$0作為美元金額。

由於 [!DNL Marketo Measure] 會自動從其與這些平台的API連線提取此資料。

**步驟4:以CSV格式儲存檔案**

如果您使用Google工作表，請務必先下載檔案。 請勿排除或刪除任何每月資料，因為這會在嘗試將CSV檔案上傳至 [!DNL Marketo Measure] 稍後。

**步驟5:上傳CSV檔案**

前往 **[!UICONTROL Cost]** 區段 [!DNL Marketo Measure] 應用程式和按一下 **[!UICONTROL Upload.CSV]**. 系統會重新整理並反映新資訊。

## 常見問題集 {#faq}

**數字為何出現在CSV中**

如果未在較高層級（如管道或子管道）輸入任何值， [!DNL Marketo Measure] 會自動加總您的子層級，上傳檔案後就會顯示子層級。 此外，如果子代的總和小於為父代輸入的值， [!DNL Marketo Measure] 會新增「其他」列，以顯示總計中的差異。

**在我看到的清單中如何決定促銷活動？**

目前，我們的結果列出我們所看到的促銷活動，並獲得接觸點的評分。 如果有來自促銷活動的活動，我們會根據發生的接觸點日期來顯示促銷活動。

**要篩選的行和列太多了 — 我可以合併視圖嗎？**

您可以變更日期範圍、篩選管道或搜尋值，合併表格結果以更符合您的需求。

**為何無法上傳檔案？**

我們在 [!DNL Marketo Measure] 應用程式。 若要上傳檔案，您必須是「AccountAdmin」。 若要解決此問題，請向您的AccountAdmin請求存取權，或由您的AccountAdmin代表您上傳檔案。 您可以在下方找到使用者及其角色的清單 **[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL View/Add Account Users]**.
