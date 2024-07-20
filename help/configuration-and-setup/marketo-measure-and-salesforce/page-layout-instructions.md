---
unique-page-id: 18874799
description: 頁面配置指示 —  [!DNL Marketo Measure]
title: 頁面配置指示
exl-id: 627377f0-d0cf-448c-a7b5-7eb5634b9627
feature: Salesforce
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 0%

---

# 頁面配置指示 {#page-layout-instructions}

>[!NOTE]
>
>您可能會在檔案中看到指定&quot;[!DNL Marketo Measure]&quot;的說明，但在您的CRM中仍會看到&quot;Bizible&quot;。 我們正致力於更新此專案，品牌重塑將很快反映在您的CRM中。

若要輕鬆檢視[!DNL Marketo Measure]資料，建議更新[!UICONTROL Account]、[!UICONTROL Contact]、[!UICONTROL Lead]、[!UICONTROL Opportunity]和[!UICONTROL Campaign]物件的頁面配置。 指示會針對下方的每個「物件頁面配置」細分。

若要開始，請先導覽至您的[!DNL Salesforce]安裝設定，並找到[!UICONTROL Customize]標籤。

## 行銷活動物件 {#campaign-object}

建議您只為沙箱將[!DNL Marketo Measure]欄位新增到SFDC Campaign。 這些欄位可用來測試接觸點產生。 在生產環境中，建議僅新增[!DNL Marketo Measure]大量更新接觸點日期按鈕。 不建議將[!DNL Marketo Measure]欄位新增至生產環境，因為您可以建立Campaign同步規則。

1. 在您的「組建」選項中，選取&#x200B;**[!UICONTROL Campaigns]**。

1. 按一下&#x200B;**[!UICONTROL Page Layouts]**。

   ![](assets/1-1.jpg)

1. 按一下您要更新的頁面配置旁的&#x200B;**[!UICONTROL Edit]**。

   ![](assets/2-1.jpg)

1. 在「[!UICONTROL fields]」選項中，選取「**[!UICONTROL Enable Buyer Touchpoints]**」欄位，並將其拖曳到頁面上您想要的位置。 接下來，新增&#x200B;**[!UICONTROL Touchpoint Start Date]**&#x200B;和&#x200B;**[!UICONTROL Touchpoint End Date]**&#x200B;欄位。

   ![](assets/3-2.png)

1. 接著，在頁面頂端按一下快速尋找功能表中的&quot;[!UICONTROL Buttons]&quot;選項。

1. 將&#x200B;**[!UICONTROL Bulk Update Touchpoint Date]**&#x200B;按鈕拖曳至自訂按鈕區段。

   ![](assets/4-1.jpg)

1. 按一下&#x200B;**[!UICONTROL Save]**。

   >[!NOTE]
   >
   >如果您使用多個Campaign記錄型別，則必須更新&#x200B;**[!UICONTROL Enable Buyer Touchpoints]**&#x200B;欄位的挑選清單值。 請參考[本文章](/help/channel-tracking-and-setup/offline-channels/configurations-for-multiple-campaign-record-types.md)的說明。

## 銷售機會 {#leads}

1. 在您的「組建」選項中，選取&#x200B;**[!UICONTROL Leads]**。

1. 按一下&#x200B;**[!UICONTROL Page Layouts]**。

1. 按一下您要更新的頁面配置旁的&#x200B;**[!UICONTROL Edit]**。 請記住，多個版面配置可包含「購買者接觸點」區段。

1. 按一下快速尋找功能表左側的VisualForce頁面選項。

1. 建立區段並將它命名為「購買者接觸點」。

   >[!NOTE]
   >
   >選取每個區段的「一欄」格式。

1. 將&#x200B;**[!UICONTROL Marketo Measure Lead Related List]** VisualForce頁面拖曳至您的頁面配置區段。

   ![](assets/5-1.png)

1. 按一下「[!DNL VisualForce]」頁面中的扳手，然後將高度變更為100並啟用卷軸。

1. 回到功能表中，選取「[!UICONTROL Canvas Apps]」區段，並在您建立的接觸點[!DNL VisualForce]區段下建立名為「Marketo Measure Insights」的區段。

   >[!NOTE]
   >
   >選取每個區段的「一欄」格式。

1. 將[!DNL Marketo Measure Insights]畫布應用程式拖曳到新建立的區段中。 按一下&#x200B;**儲存**。 有時候在放入畫布應用程式之前必須先儲存頁面配置，因為Salesforce無法立即辨識它。 所以在建立區段後，儲存頁面版面配置，然後重新編輯，將畫布應用程式拖曳到該區段中。 這適用於每個物件。

   >[!NOTE]
   >
   >若要讓[!DNL Marketo Measure Insights] Canvas App正常運作，[許可權必須正確設定](/help/configuration-and-setup/marketo-measure-insights-canvas-app/marketo-measure-insights-configuration.md)。

   >[!TIP]
   >
   >大部分客戶不使用結尾為(FT)或(LC)的欄位，因為它們是[!DNL Marketo Measure]接觸點以物件存在之前的舊版欄位。

如果您使用[!DNL Marketo Measure] ABM功能，[請按一下這裡以取得其他版面配置指示](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md)。

## 連絡人 {#contacts}

1. 在您的「組建」選項中，選取&#x200B;**[!UICONTROL Contacts]**。

1. 按一下&#x200B;**[!UICONTROL Page Layouts]**。

1. 選取您要編輯的頁面配置。

   前往快速尋找功能表中的[相關清單]選項，然後新增&#x200B;**[!UICONTROL Buyer Touchpoints]**&#x200B;相關清單。

1. 按一下扳手圖示，然後依此順序新增下列欄：

   * Buyer Touchpoint
   * 行銷管道
   * 接觸點Source
   * 廣告行銷活動名稱
   * 接觸點位置
   * 接觸點日期

1. 排序依據：接觸點日期，升序。

   ![](assets/6.jpg)

1. 展開[按鈕]選項並取消選取&#x200B;**[!UICONTROL New]**。

   ![](assets/7.png)

1. 返回功能表中的[!UICONTROL Related List]選項，現在新增&#x200B;**[!UICONTROL Buyer Attribution Touchpoint]**&#x200B;相關清單。

1. 按一下扳手圖示，然後依此順序新增下列欄：

   * 歸因接觸點
   * 行銷管道
   * 機會
   * 廣告行銷活動名稱
   * 接觸點型別
   * 接觸點位置
   * 歸因% W形（_或最強大的歸因模型，例如Full Path或Custom_）
   * 收入W形（_或最強大的歸因模型，例如Full Path或Custom_）
   * 接觸點日期

1. 依接觸點[!UICONTROL Date] > [!UICONTROL Ascending]排序。

1. 展開[按鈕]區段並取消選取&#x200B;**[!UICONTROL New]**。

1. 按一下&#x200B;**[!UICONTROL Save]**。

## 機會 {#opportunities}

1. 在您的「組建」選項中，選取&#x200B;**[!UICONTROL Opportunities]**。

1. 按一下&#x200B;**[!UICONTROL Page Layouts]**。

1. 選取您要編輯的頁面配置。

1. 新增&#x200B;**[!UICONTROL Buyer Attribution Touchpoint]**&#x200B;相關清單，然後按一下扳手，為機會新增下列欄：

   * 歸因接觸點
   * 行銷管道
   * 連絡人
   * 廣告行銷活動名稱
   * 接觸點型別
   * 接觸點位置
   * 歸因% W形（_或最強大的歸因模型，例如Full Path或Custom_）
   * 收入W形（_或最強大的歸因模型，例如Full Path或Custom_）
   * 接觸點日期

1. 排序依據： [!UICONTROL Touchpoint Date] > [!UICONTROL Ascending]。

1. 在[!UICONTROL Buttons]區段中取消選取&#x200B;**[!UICONTROL New]**。

1. 按一下&#x200B;**[!UICONTROL Save]**。

## 帳戶 {#accounts}

1. 在您的「組建」選項中，選取&#x200B;**[!UICONTROL Accounts]**。

1. 按一下&#x200B;**[!UICONTROL Page Layouts]**。

1. 選取您要編輯的頁面配置。

1. 新增&#x200B;**[!UICONTROL Buyer Attribution Touchpoint]**&#x200B;相關清單，然後按一下扳手以新增下列欄：

   * 歸因接觸點
   * 行銷管道
   * 機會
   * 廣告行銷活動名稱
   * 接觸點型別
   * 接觸點位置
   * 歸因% W形（_或最強大的歸因模型，例如Full Path或Custom_）
   * 收入W形（_或最強大的歸因模型，例如Full Path或Custom_）
   * 接觸點日期

1. 依接觸點日期>升序排序。

1. 在[!UICONTROL Buttons]區段中取消選取&#x200B;**[!UICONTROL New]**。

1. 按一下&#x200B;**[!UICONTROL Save]**。

如果您使用[!DNL Marketo Measure] ABM功能，請檢閱[額外的頁面配置指示](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md)。
