---
unique-page-id: 18874732
description: 設定UTM引數的最佳實務 —  [!DNL Marketo Measure]
title: 設定UTM引數的最佳作法
exl-id: 56019f41-b6ba-48c1-9bef-2a5f56d2d5f4
feature: UTM Parameters
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 0%

---

# 設定UTM引數的最佳作法 {#best-practices-for-setting-up-utm-parameters}

UTM引數是切分行銷資料的絕佳方式。 [!DNL Marketo Measure]使用並擷取所有UTM引數，以填入Salesforce和[!DNL Marketo Measure]應用程式中的欄位。 有了這些資訊，您就能更詳細地瞭解您的銷售機會、商機以及已結/已贏的交易來自何處。

您可以使用[Google URL產生器](https://support.google.com/analytics/answer/1033867?hl=en){target="_blank"}來設定您的UTM引數，並在行銷工作中將其新增至您的連結。 如果您想要以更簡單的方式追蹤所有UTM連結，請使用此[Google試算表](https://docs.google.com/spreadsheets/d/1QCIr1WUJQHE68cA4VTks2XE7nxuryaUymCEy_23-Oew/edit#gid=0){target="_blank"}。

## 每個引數的高階值 {#high-level-values-for-each-parameter}

**utm_medium**：此欄位對應到Medium欄位。 使用utm_medium表示高階通道。

例如，[!UICONTROL Social]、CPC、電子郵件、網頁、有機

請勿使用此欄位來呼叫子管道。

**utm_source**：此欄位對應到接觸點Source欄位。 使用utm_source來定義潛在客戶來源的子管道。

例如，Facebook、Twitter、Linkedin、Drip_email、Email_blast、電子報。

保持簡單。 請勿使用此引數來表示廣告型別，例如重新定位或贊助。 請勿新增utm_source = homepage， webdirect， website。 [!DNL Marketo Measure]會自動為您填寫此資訊。

**utm_campaign**：此欄位對應到廣告行銷活動名稱。 使用utm_campaign表示行銷活動的標題，如廣告平台中所有，或內部所參照。

這也是一個表示地理位置、廣告網路型別（顯示v.搜尋）等的好引數。

建議您使用底線而非空格，並避免使用標點符號。 這能減少瀏覽器讀取引數時發生編碼錯誤的可能性。

例如，AU_Idea_for_an_App_50k

**utm_content**：此專案對應至廣告內容。 在utm_content引數中使用廣告標題。 如果是影像廣告，請使用廣告標題並包含廣告尺寸。

例如，[廣告標題] 200x400px

**utm_term**：這對應到關鍵字文字。 此引數用於表示與廣告引發相關的關鍵字。

如果沒有與廣告相關的關鍵字，請將此引數留空。

例如，iPhone應用程式概念

**保持簡單明瞭。 不要重複工作、字詞和管道。**

我們將UTM階層想像如下：

Medium > [!UICONTROL Source] > [!UICONTROL Campaign] > [!UICONTROL Content/Term]

例如，如果在Facebook上刊登[!UICONTROL display]廣告，我們建議以下事項：

fakewebsite.com/

？utm_medium=social

&amp;utm_source=facebook

&amp;utm_campaign=Display_campaign_ID

&amp;utm_content=content_of_campaign

請注意，此情況下不會複製詞語/頻道，也不會使用utm_term。

如有任何問題，請聯絡Adobe客戶團隊（您的客戶經理）或[Marketo支援](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}。
