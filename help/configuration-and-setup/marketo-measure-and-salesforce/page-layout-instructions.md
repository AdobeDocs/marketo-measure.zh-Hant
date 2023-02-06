---
unique-page-id: 18874799
description: 頁面配置指示 —  [!DNL Marketo Measure]  — 產品檔案
title: 頁面配置指示
exl-id: 627377f0-d0cf-448c-a7b5-7eb5634b9627
source-git-commit: b910e5aedb9e178058f7af9a6907a1039458ce7a
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 1%

---

# 頁面配置指示 {#page-layout-instructions}

>[!NOTE]
>
>您可能會看到指定「[!DNL Marketo Measure]「 」，但仍可在CRM中看到「Bizible」。 我們正致力更新該更新，品牌重塑將很快反映在您的CRM中。

輕鬆查看 [!DNL Marketo Measure] 資料，建議更新 [!UICONTROL Account], [!UICONTROL Contact], [!UICONTROL Lead], [!UICONTROL Opportunity]，和 [!UICONTROL Campaign] 對象。 系統會針對下方的每個「物件頁面配置」劃分指示。

若要開始，請先導覽至 [!DNL Salesforce] 設定設定，並找出 [!UICONTROL Customize] 標籤。

## 促銷活動物件 {#campaign-object}

建議您新增 [!DNL Marketo Measure] 欄位至您的SFDC促銷活動，僅適用於沙箱。 欄位可用來測試接觸點產生。 在生產環境中，我們建議僅新增 [!DNL Marketo Measure] 「批量更新接觸點日期」按鈕。 我們不建議將 [!DNL Marketo Measure] 欄位至生產環境，因為您可以建立促銷活動同步規則。

1. 在「建置」選項中，選取 **[!UICONTROL Campaigns]**.

1. 按一下 **[!UICONTROL Page Layouts]**.

   ![](assets/1-1.jpg)

1. 按一下 **[!UICONTROL Edit]** 頁面配置旁邊。

   ![](assets/2-1.jpg)

1. 在 [!UICONTROL fields] 選項，選擇 **[!UICONTROL Enable Buyer Touchpoints]** 欄位，並將其拖曳到頁面上任何您想要的位置。 接下來，新增 **[!UICONTROL Touchpoint Start Date]** 和 **[!UICONTROL Touchpoint End Date]** 欄位。

   ![](assets/3-2.png)

1. 接下來，在頁面頂端按一下「[!UICONTROL Buttons]」選項。

1. 拖曳 **[!UICONTROL Bulk Update Touchpoint Date]** 按鈕，以便自訂按鈕區段。

   ![](assets/4-1.jpg)

1. 按一下 **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >如果您使用多個促銷活動記錄類型， **[!UICONTROL Enable Buyer Touchpoints]** 欄位需要更新。 請參考 [這篇文章](/help/channel-tracking-and-setup/offline-channels/configurations-for-multiple-campaign-record-types.md) 的說明。

## 銷售機會 {#leads}

1. 在「建置」選項中，選取 **[!UICONTROL Leads]**.

1. 按一下 **[!UICONTROL Page Layouts]**.

1. 按一下 **[!UICONTROL Edit]** 頁面配置旁邊。 請記住，多個頁面配置可包含「購買者接觸點」區段。

1. 按一下快速查找菜單左側的VisualForce頁選項。

1. 建立新區段，並將其命名為「購買者接觸點」。

   >[!NOTE]
   >
   >為這些區段選取「一欄」格式。

1. 拖曳 **[!UICONTROL Marketo Measure Lead Related List]** VisualForce頁面到您的頁面佈局部分。

   ![](assets/5-1.png)

1. 按一下 [!DNL VisualForce] 頁面並將高度變更為100並啟用捲軸。

1. 返回功能表，選取 [!UICONTROL Canvas Apps] 區段，並在接觸點下方建立名為「Marketo Measure Insights」的新區段 [!DNL VisualForce] 區段。

   >[!NOTE]
   >
   >為這些區段選取「一欄」格式。

1. 拖曳 [!DNL Marketo Measure Insights] 將畫布應用程式新建立到該區段。 按一下 **儲存**. 有時候，由於Salesforce無法立即辨識頁面版面，因此必須先儲存頁面版面，才能拖曳至畫布應用程式中。 因此，建立新區段後，請儲存頁面版面，然後重新編輯以在該區段內拖曳畫布應用程式。 這會套用至每個物件。

   >[!NOTE]
   >
   >若 [!DNL Marketo Measure Insights] 畫布應用程式才能正常運作， [需要正確配置權限](/help/configuration-and-setup/marketo-measure-insights-canvas-app/marketo-measure-insights-configuration.md).

   >[!TIP]
   >
   >大部分客戶不會使用以(FT)或(LC)結尾的欄位，因為這些是 [!DNL Marketo Measure] 接觸點以物件形式存在。

如果您正在利用 [!DNL Marketo Measure] ABM功能， [請按一下這裡以取得其他頁面配置指示](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md).

## 聯繫人 {#contacts}

1. 在「建置」選項中，選取 **[!UICONTROL Contacts]**.

1. 按一下 **[!UICONTROL Page Layouts]**.

1. 選取您要編輯的「頁面配置」。

   轉到快速查找菜單中的「相關清單」選項，然後添加 **[!UICONTROL Buyer Touchpoints]** 相關清單。

1. 按一下扳手圖示，然後依此順序新增下列欄：

   * 購買者接觸點
   * 行銷管道
   * 接觸點來源
   * 廣告促銷活動名稱
   * 接觸點位置
   * 接觸點日期

1. 排序依據：接觸點日期，遞增。

   ![](assets/6.jpg)

1. 展開「按鈕」選項，然後取消選取 **[!UICONTROL New]**.

   ![](assets/7.png)

1. 返回 [!UICONTROL Related List] 選項，現在新增 **[!UICONTROL Buyer Attribution Touchpoint]** 相關清單。

1. 按一下扳手圖示，然後依此順序新增下列欄：

   * 歸因接觸點
   * 行銷管道
   * 機會
   * 廣告促銷活動名稱
   * 接觸點類型
   * 接觸點位置
   * 歸因% W形(_或最穩健的歸因模型，例如完整路徑或自訂_)
   * 收入W形(_或最穩健的歸因模型，例如完整路徑或自訂_)
   * 接觸點日期

1. 依接觸點排序 [!UICONTROL Date] > [!UICONTROL Ascending].

1. 展開「按鈕」區段並取消選取 **[!UICONTROL New]**.

1. 按一下 **[!UICONTROL Save]**.

## 機會 {#opportunities}

1. 在「建置」選項中，選取 **[!UICONTROL Opportunities]**.

1. 按一下 **[!UICONTROL Page Layouts]**.

1. 選取您要編輯的「頁面配置」。

1. 新增 **[!UICONTROL Buyer Attribution Touchpoint]** 「相關清單」，然後按一下扳手，即可為「機會」新增下列欄：

   * 歸因接觸點
   * 行銷管道
   * 連絡人
   * 廣告促銷活動名稱
   * 接觸點類型
   * 接觸點位置
   * 歸因% W形(_或最穩健的歸因模型，例如完整路徑或自訂_)
   * 收入W形(_或最穩健的歸因模型，例如完整路徑或自訂_)
   * 接觸點日期

1. 排序依據 [!UICONTROL Touchpoint Date] > [!UICONTROL Ascending].

1. 取消選擇 **[!UICONTROL New]** 在 [!UICONTROL Buttons] 區段。

1. 按一下 **[!UICONTROL Save]**.

## 帳戶 {#accounts}

1. 在「建置」選項中，選取 **[!UICONTROL Accounts]**.

1. 按一下 **[!UICONTROL Page Layouts]**.

1. 選取您要編輯的「頁面配置」。

1. 新增 **[!UICONTROL Buyer Attribution Touchpoint]** 「相關清單」 ，然後按一下扳手以新增下列欄：

   * 歸因接觸點
   * 行銷管道
   * 機會
   * 廣告促銷活動名稱
   * 接觸點類型
   * 接觸點位置
   * 歸因% W形(_或最穩健的歸因模型，例如完整路徑或自訂_)
   * 收入W形(_或最穩健的歸因模型，例如完整路徑或自訂_)
   * 接觸點日期

1. 依接觸點日期>升序排序。

1. 取消選擇 **[!UICONTROL New]** 在 [!UICONTROL Buttons] 區段。

1. 按一下 **[!UICONTROL Save]**.

如果您正在運用 [!DNL Marketo Measure] ABM功能，  [請按一下這裡以取得其他頁面配置指示](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md).
