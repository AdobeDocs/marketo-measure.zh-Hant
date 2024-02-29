---
unique-page-id: 18874799
description: 頁面配置指示 —  [!DNL Marketo Measure]
title: 頁面配置指示
exl-id: 627377f0-d0cf-448c-a7b5-7eb5634b9627
feature: Salesforce
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 0%

---

# 頁面配置指示 {#page-layout-instructions}

>[!NOTE]
>
>您可能會看到指定&#39;&#39;的說明[!DNL Marketo Measure]&quot;，但仍在您的CRM中看到「Bizible」。 我們正致力於更新此專案，品牌重塑將很快反映在您的CRM中。

輕鬆檢視 [!DNL Marketo Measure] 資料，建議更新以下專案的頁面配置： [!UICONTROL Account]， [!UICONTROL Contact]， [!UICONTROL Lead]， [!UICONTROL Opportunity]、和 [!UICONTROL Campaign] 物件。 指示會針對下方的每個「物件頁面配置」細分。

若要開始，請先導覽至 [!DNL Salesforce] 安裝設定並找到 [!UICONTROL Customize] 標籤。

## 行銷活動物件 {#campaign-object}

建議您新增 [!DNL Marketo Measure] 欄位至您的SFDC Campaign，僅供沙箱使用。 這些欄位可用來測試接觸點產生。 在生產環境中，建議僅新增 [!DNL Marketo Measure] 大量更新接觸點日期按鈕。 不建議新增 [!DNL Marketo Measure] 欄位來進行生產，因為您可以建立Campaign同步規則。

1. 在「建置」選項中，選取 **[!UICONTROL Campaigns]**.

1. 按一下 **[!UICONTROL Page Layouts]**.

   ![](assets/1-1.jpg)

1. 按一下 **[!UICONTROL Edit]** ，位於您要更新的頁面配置旁。

   ![](assets/2-1.jpg)

1. 在 [!UICONTROL fields] 選項，選取 **[!UICONTROL Enable Buyer Touchpoints]** 欄位並拖曳到頁面上您想要的位置。 接下來，新增 **[!UICONTROL Touchpoint Start Date]** 和 **[!UICONTROL Touchpoint End Date]** 欄位。

   ![](assets/3-2.png)

1. 接下來，在頁面頂端按一下「[!UICONTROL Buttons]「快速尋找」選單中的「選項。

1. 拖曳 **[!UICONTROL Bulk Update Touchpoint Date]** 按鈕到您的自訂按鈕區段。

   ![](assets/4-1.jpg)

1. 按一下 **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >如果您使用多個Campaign記錄型別，則必須更新的 **[!UICONTROL Enable Buyer Touchpoints]** 欄位。 請參閱 [本文](/help/channel-tracking-and-setup/offline-channels/configurations-for-multiple-campaign-record-types.md) 以取得指示。

## 銷售機會 {#leads}

1. 在「建置」選項中，選取 **[!UICONTROL Leads]**.

1. 按一下 **[!UICONTROL Page Layouts]**.

1. 按一下 **[!UICONTROL Edit]** ，位於您要更新的頁面配置旁。 請記住，多個版面配置可包含「購買者接觸點」區段。

1. 按一下快速尋找功能表左側的VisualForce頁面選項。

1. 建立區段並將它命名為「購買者接觸點」。

   >[!NOTE]
   >
   >選取每個區段的「一欄」格式。

1. 拖曳 **[!UICONTROL Marketo Measure Lead Related List]** VisualForce頁面放入您的頁面配置區段。

   ![](assets/5-1.png)

1. 按一下 [!DNL VisualForce] 頁面，並將高度變更為100並啟用卷軸。

1. 返回功能表，選取 [!UICONTROL Canvas Apps] 區段，並在接觸點下方建立名為「Marketo Measure深入分析」的區段 [!DNL VisualForce] 區段建立時間。

   >[!NOTE]
   >
   >選取每個區段的「一欄」格式。

1. 拖曳 [!DNL Marketo Measure Insights] 將畫布應用程式放入新建立的區段中。 按一下 **儲存**. 有時候在放入畫布應用程式之前必須先儲存頁面配置，因為Salesforce無法立即辨識它。 所以在建立區段後，儲存頁面版面配置，然後重新編輯，將畫布應用程式拖曳到該區段中。 這適用於每個物件。

   >[!NOTE]
   >
   >對於 [!DNL Marketo Measure Insights] Canvas應用程式正常運作， [許可權必須正確設定](/help/configuration-and-setup/marketo-measure-insights-canvas-app/marketo-measure-insights-configuration.md).

   >[!TIP]
   >
   >大部分客戶不會使用結尾為(FT)或(LC)的欄位，因為這些欄位是 [!DNL Marketo Measure] 接觸點以物件形式存在。

如果您使用 [!DNL Marketo Measure] ABM功能， [按一下這裡以取得其他頁面配置指示](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md).

## 連絡人 {#contacts}

1. 在「建置」選項中，選取 **[!UICONTROL Contacts]**.

1. 按一下 **[!UICONTROL Page Layouts]**.

1. 選取您要編輯的頁面配置。

   前往快速尋找功能表中的「相關清單」選項，然後新增 **[!UICONTROL Buyer Touchpoints]** 相關清單。

1. 按一下扳手圖示，然後依此順序新增下列欄：

   * 購買者接觸點
   * 行銷管道
   * 接觸點來源
   * 廣告行銷活動名稱
   * 接觸點位置
   * 接觸點日期

1. 排序依據：接觸點日期，升序。

   ![](assets/6.jpg)

1. 展開按鈕選項並取消選取 **[!UICONTROL New]**.

   ![](assets/7.png)

1. 返回 [!UICONTROL Related List] 選單中的選項，現在新增 **[!UICONTROL Buyer Attribution Touchpoint]** 相關清單。

1. 按一下扳手圖示，然後依此順序新增下列欄：

   * 歸因接觸點
   * 行銷管道
   * 機會
   * 廣告行銷活動名稱
   * 接觸點型別
   * 接觸點位置
   * 歸因% W形(_或最強大的歸因模型，例如「完整路徑」或「自訂」_)
   * 收入W形(_或最強大的歸因模型，例如「完整路徑」或「自訂」_)
   * 接觸點日期

1. 依接觸點排序 [!UICONTROL Date] > [!UICONTROL Ascending].

1. 展開按鈕區段並取消選取 **[!UICONTROL New]**.

1. 按一下 **[!UICONTROL Save]**.

## 機會 {#opportunities}

1. 在「建置」選項中，選取 **[!UICONTROL Opportunities]**.

1. 按一下 **[!UICONTROL Page Layouts]**.

1. 選取您要編輯的頁面配置。

1. 新增 **[!UICONTROL Buyer Attribution Touchpoint]** 相關清單，然後按一下扳手，為「商機」新增下列欄：

   * 歸因接觸點
   * 行銷管道
   * 連絡人
   * 廣告行銷活動名稱
   * 接觸點型別
   * 接觸點位置
   * 歸因% W形(_或最強大的歸因模型，例如「完整路徑」或「自訂」_)
   * 收入W形(_或最強大的歸因模型，例如「完整路徑」或「自訂」_)
   * 接觸點日期

1. 排序依據： [!UICONTROL Touchpoint Date] > [!UICONTROL Ascending].

1. 取消選取 **[!UICONTROL New]** 在 [!UICONTROL Buttons] 區段。

1. 按一下 **[!UICONTROL Save]**.

## 帳戶 {#accounts}

1. 在「建置」選項中，選取 **[!UICONTROL Accounts]**.

1. 按一下 **[!UICONTROL Page Layouts]**.

1. 選取您要編輯的頁面配置。

1. 新增 **[!UICONTROL Buyer Attribution Touchpoint]** 相關清單，然後按一下扳手以新增下列欄：

   * 歸因接觸點
   * 行銷管道
   * 機會
   * 廣告行銷活動名稱
   * 接觸點型別
   * 接觸點位置
   * 歸因% W形(_或最強大的歸因模型，例如「完整路徑」或「自訂」_)
   * 收入W形(_或最強大的歸因模型，例如「完整路徑」或「自訂」_)
   * 接觸點日期

1. 依接觸點日期>升序排序。

1. 取消選取 **[!UICONTROL New]** 在 [!UICONTROL Buttons] 區段。

1. 按一下 **[!UICONTROL Save]**.

如果您使用 [!DNL Marketo Measure] ABM功能，檢閱 [其他頁面配置指示](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md).
