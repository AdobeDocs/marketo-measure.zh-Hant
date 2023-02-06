---
unique-page-id: 18874732
description: 設定UTM參數的最佳實務 —  [!DNL Marketo Measure]  — 產品檔案
title: 設定UTM參數的最佳作法
exl-id: 56019f41-b6ba-48c1-9bef-2a5f56d2d5f4
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 0%

---

# 設定UTM參數的最佳作法 {#best-practices-for-setting-up-utm-parameters}

UTM參數是分解行銷資料的絕佳方式。 [!DNL Marketo Measure] 使用並擷取所有UTM參數，以填入Salesforce和 [!DNL Marketo Measure] 應用程式。 利用這些資訊，您將能夠更細緻地了解銷售機會、銷售機會和已結/贏交易的來源。

您可以利用 [Google URL Builder](https://support.google.com/analytics/answer/1033867?hl=en){target="_blank"} to set up your UTM parameters and add them to your links within your marketing efforts. Use this [Google Spreadsheet](https://docs.google.com/spreadsheets/d/1QCIr1WUJQHE68cA4VTks2XE7nxuryaUymCEy_23-Oew/edit#gid=0){target="_blank"} 如果您想要更輕鬆地跟蹤所有UTM連結。

## 每個參數的高階值 {#high-level-values-for-each-parameter}

**utm_medium**:此欄位對應至「中」欄位。 使用utm_medium表示高階通道。

例如： [!UICONTROL Social], CPC，電子郵件，網頁，自然

請勿使用此欄位來呼叫子管道。

**utm_source**:此欄位對應至「接觸點來源」欄位。 使用utm_source定義潛在銷售線索的來源子通道。

例如：Facebook、Twitter、Linkedin、Drip_email、Email_blast、電子報。

保持簡單。 請勿使用此參數來表示廣告類型，例如重新定位、贊助等。 請勿新增utm_source = homepage、webdirect、website。 [!DNL Marketo Measure] 會自動為您填寫此資訊。

**utm_campaign**:此欄位對應至廣告促銷活動名稱。 使用utm_campaign，以在廣告平台中存在或在內部參照的方式表示促銷活動的標題。

這也是表示地理位置、廣告網路類型（顯示v.搜尋）等項目的好參數。

建議您使用底線而非空格，並避免使用標點符號。 這可降低瀏覽器在讀取參數時編碼錯誤的機率。

例如：AU_Idea_for_an_App_50k

**utm_content**:這會對應至「廣告內容」。 在utm_content參數中使用廣告標題。 如果是影像廣告，請使用廣告標題並納入廣告維度。

例如： [廣告標題] 200x400px

**utm_term**:這會對應至關鍵字文字。 使用此參數表示與引發廣告相關的關鍵字。

如果沒有與廣告相關的關鍵字，請將此參數留空。

例如：iPhone App Ideas

**保持簡單簡潔。 請勿複製工作、詞語和管道。**

我們設想UTM的等級如下：

中> [!UICONTROL Source] > [!UICONTROL Campaign] > [!UICONTROL Content/Term]

例如：若 [!UICONTROL display] 廣告放置在Facebook上，我們建議：

fakewebsite.com/

?utm_medium=social

&amp;utm_source=facebook

&amp;utm_campaign=Display_campaign_ID

&amp;utm_content=content_of_campaign

請注意，詞語/管道不會重複，而且此案例中不會使用utm_term。

如有任何問題，請洽詢您的客戶成功經理，或 [Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
