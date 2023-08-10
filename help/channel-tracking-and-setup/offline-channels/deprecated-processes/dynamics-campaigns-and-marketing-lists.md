---
unique-page-id: 18874610
description: Dynamics行銷活動和行銷清單 —  [!DNL Marketo Measure]  — 產品檔案
title: Dynamics行銷活動和行銷清單
exl-id: 7b3d4032-5edf-489d-b86b-1e2a5755b258
feature: Microsoft Dynamics
source-git-commit: e01738222e8845112892c0258cb084a4f0ebb257
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 0%

---

# Dynamics行銷活動和行銷清單 {#dynamics-campaigns-and-marketing-lists}

>[!NOTE]
>
>本文會介紹過時的程式。 我們鼓勵使用者使用 [新的、改良的應用程式內程式](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"}.

## 行銷活動 {#campaigns}

Dynamics行銷活動適合追蹤離線行銷活動，並將其納入全頻道歷程中。 行銷活動必須與潛在客戶或聯絡人相關，並可透過行銷活動回應或行銷清單累計至行銷活動。

## 行銷活動回應 {#campaign-responses}

當銷售機會或聯絡人直接新增到行銷活動時，輸入為行銷活動回應記錄。

![](assets/1.png)

## 啟用接觸點 {#enable-touchpoints}

若要在接觸點歷程中包含這些記錄，請針對要同步的Campaign回應型別提供幾個選項。 行銷活動記錄上，安裝的解決方案中應有一個自訂欄位，標籤為「[!UICONTROL Enable Buyer Touchpoints].」 如果沒有看見，則需要透過表單編輯器新增欄位。

![](assets/2.png)

您可以選擇將具有行銷活動回應的所有記錄包含在行銷活動中，或僅包含具有「感興趣」回應的記錄，或者在預設情況下，您完全不能包含行銷活動回應。 您可以讓欄位保持空白或明確選擇排除它。

[!DNL Marketo Measure] 不支援自訂回應值。

![](assets/3.png)

這些是Campaign回應的庫存回應值：

![](assets/4.png)

根據您的選擇，這些記錄現在符合Lead、Contact或Opportunity歷程中的接觸點資格。 如果他們符合資格，歷程中將會顯示「Dynamics Campaign」接觸點。

Campaign回應可能不會顯示的原因之一，是因為Lead/Contact已記錄「首次接觸」和/或「潛在客戶建立接觸」活動，且「PostLC」功能已停用或已達到其最大接觸點數量。

## 接觸點日期 {#touchpoint-date}

行銷活動的接觸點日期通常是行銷活動回應新增至行銷活動的日期。 如果已填入來自已安裝解決方案的自訂欄位（標示為「購買者接觸點日期」），則可以覆寫此欄位。 如果沒有看見，則需要透過表單編輯器新增欄位。

使用此欄位的常見範例是事件，其中事件的徽章掃描清單會在事件發生後新增至CRM天數，因此使用者實際上可以將「購買者接觸點日期」變更回事件發生時的日期。

![](assets/5.png)

## 行銷清單 {#marketing-lists}

行銷清單是將潛在客戶或聯絡人納入行銷歷程的另一種方式。 行銷清單對潛在客戶或聯絡人群組而言是唯一的，這表示使用者必須選取其清單是潛在客戶集還是聯絡人集。

[!DNL Marketo Measure] 僅支援靜態行銷清單。 我們不支援動態行銷清單，因為我們的處理需要我們檢查記錄的修改日期，但因為動態清單經常變更，所以沒有的修改日期 [!DNL Marketo Measure] 以檢查。 這要求您一整天持續下載完整的資料集。

![](assets/6.png)

上面的熒幕擷圖是銷售機會的行銷清單。 行銷清單與行銷活動相關聯，並可與多個行銷活動相關聯。 除非您僅為一個行銷活動建立一個行銷清單， [!DNL Marketo Measure] 不建議客戶使用行銷清單來追蹤其促銷活動。 銷售機會/聯絡人的相同確切清單不太可能適用於多個行銷活動的接觸點。

## 啟用接觸點 {#enable-touchpoints-1}

若要啟用接觸點的行銷清單，行銷活動記錄上會有個別的設定，標籤為「[!UICONTROL Sync Marketing Lists]，」是簡單的yes/no引數。 如果沒有看見，則需要透過表單編輯器新增欄位。 在行銷活動記錄上，您可以看到哪些行銷清單與行銷活動相關，因此您可以知道要啟用多少清單。

![](assets/7.png)

## 接觸點日期 {#touchpoint-date-1}

行銷清單的接觸點日期通常是ListMember建立的日期，因此銷售機會或連絡人會新增至行銷清單的日期。 如果已填入來自已安裝解決方案的自訂欄位（標示為「購買者接觸點日期」），則可以覆寫此欄位。 如果沒有看見，則需要透過表單編輯器新增欄位。

![](assets/8.png)

## 頻道對應 {#channel-mapping}

Dynamics行銷活動會使用「行銷活動型別」欄位在您的自訂行銷管道中分組。 您可以在Dynamics自訂功能表中變更這些專案。

「促銷活動型別」功能表中的值會被提取至 [!DNL Marketo Measure] 應用程式。 **[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL Offline Channels]**.

對於各種「促銷活動型別」，可將之對應至「管道」和「子管道」組合，使衍生自「促銷活動」的每個接觸點都具有正確對應的「管道」和「子管道」。

![](assets/9.png)

![](assets/10.png)

## Campaign同步日期 {#campaign-sync-date}

Dynamics客戶無法使用此功能

## 常見問題集 {#faq}

**我們是否可以在行銷清單上啟用接觸點，或僅在Dynamics中啟用行銷活動？**

您可以啟用行銷清單，但必須將其與行銷活動相關聯，因為同步行銷清單的選項存在於行銷活動中。

**我們可以在行銷活動中使用行銷活動回應和行銷清單嗎？**

是.
