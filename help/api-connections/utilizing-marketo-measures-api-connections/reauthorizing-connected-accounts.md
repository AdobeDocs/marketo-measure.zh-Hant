---
unique-page-id: 18874690
description: 重新授權連線帳戶 —  [!DNL Marketo Measure]
title: 重新授權連線的帳戶
exl-id: 7abd1d67-5bed-45bb-844f-0ffd23c3d7f8
feature: APIs, Integration
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 0%

---

# 重新授權連線的帳戶 {#reauthorizing-connected-accounts}

當帳戶與您的帳戶中斷連線時 [!DNL Marketo Measure] 帳戶，平台的狀態將變更為「需要授權」並顯示紅色鑰匙圖示。

如果您的廣告平台中斷連線， [!DNL Marketo Measure] 將無法下載成本資料，或者，如果您已啟用自動標籤，請附加 [!DNL Marketo Measure] 任何新建立廣告的UTM引數。 [!DNL Marketo Measure] 帳戶中斷連線時，將無法回溯附加UTM引數至任何從廣告平台建立的接觸點。

如果您的CRM平台中斷連線， [!DNL Marketo Measure] 將無法更新 [!DNL Marketo Measure] 資料或將任何新接觸點推送至您的組織。 重新建立CRM連線後， [!DNL Marketo Measure] 會推送帳戶中斷連線時所遺漏的任何資料。

![](assets/1-1.png)

## 重新授權已中斷連線的帳戶 {#re-authorizing-disconnected-accounts}

1. 前往 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} 並登入。
1. 選取 **[!UICONTROL Settings]** 在 [!UICONTROL My Account] tab鍵在左上角。
1. 在左側找到整合區段，然後按一下 **[!UICONTROL Connections]**.
1. 選取需要重新連線的帳戶旁的「紅色金鑰」符號。
1. 此時會出現一個快顯視窗，提示您提供帳戶的登入詳細資料。
