---
description: 線上管道的最佳作法 —  [!DNL Marketo Measure]
title: 線上管道的最佳作法
exl-id: 766cb01c-98b3-492d-bb35-e0a78b76333a
feature: Channels
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 0%

---

# 線上管道的最佳作法 {#best-practices-for-online-channels}

## 概觀 {#overview}

以取得精確的 [!DNL Marketo Measure] 報告，您的行銷管道必須正確設定。 行銷管道欄位會顯示接觸點可屬於的最高層級行銷活動群組（例如，付費搜尋、直接、社交等）。

設定行銷管道有兩個層面：線上和離線。 本檔案著重於 [!DNL Marketo Measure] 設定及維護線上管道的最佳實務建議。

線上頻道規則為操作指引 [!DNL Marketo Measure] 對應您的數位接觸點，亦即任何透過 [!DNL Marketo Measure] 您網站上的JS。 如果這些規則不完整，或未正確排序，則會將接觸點歸因於錯誤的管道，因此會降低報表的正確性。 確保您的線上管道規則正確且為最新狀態，將可保證您的數位資料已歸因至您系統中的正確管道和子管道。 [!DNL Marketo Measure] 報表。

## 最佳實務 {#best-practice}

無論是第一次設定規則，還是檢閱規則以檢查準確性，請記住以下最佳實務。

請花點時間思考行銷活動的組織方式，以及這些組織如何適合 [!DNL Marketo Measure] 框架。 決定線上頻道中應該顯示哪些頻道和子頻道，以及哪些促銷活動、UTM引數或反向連結網站將這些頻道彼此區分開來。

注意事項：

* 所有數位頻道和子頻道至少應用一個規則表示
   * 如果頻道沒有促使人們進入您的網站，則不是線上頻道
* 一個管道/子管道可以有多個規則
   * 您可以將多個規則視為「投射更寬的網路」，以確保每個接觸點都正確對應。 通常可以不正確新增或完全遺漏引數，因此擁有多個規則來擷取管道/子管道是確保對應正確性的好方法。
* [!DNL Marketo Measure] 邏輯會從試算表的上方列開始，依遞減順序排列接觸點對應的優先順序，並向下進行
   * [!DNL Marketo Measure] 讀取每個規則（列），尋找真和第一個符合。 然後，接觸點會對映至該管道/子管道
   * 請勿以字母順序排序工作表，因為這會干擾邏輯規則。
* 維護括弧內的規則，請勿編輯或新增至括弧內的規則(例如； [AdWords付費搜尋] 或 [facebook已付費] )
   * 這些是現成可用的 [!DNL Marketo Measure] 具有內建邏輯的規則，這些邏輯與 [!DNL Marketo Measure] 整合。 將這些規則設為該管道/子管道區段的最高優先順序，以確保 [!DNL Marketo Measure] 整合功能能夠如預期運作。
* 上傳檔案後，您七天內無法變更任何規則
   * [!DNL Marketo Measure] 利用此時間處理和更新接觸點，因此請務必在上傳前仔細檢查規則。

## 維護最佳實務 {#best-practice-for-maintenace}

儲存及處理線上管道規則後，這些規則會持續運作以儲存您的數位接觸點。 不過，某些變更或情況會導致您檢閱線上頻道設定。 [!DNL Marketo Measure] 建議您每六個月檢閱一次線上管道規則。 這可確保 [!DNL Marketo Measure] 資料會與您線上頻道/子頻道的內部定義以及UTM的使用方式保持一致。

可能觸發您的團隊進行線上頻道維護的其他專案包括....

* 新的數位頻道/子頻道已推出
* UTM引數已更新或變更
* 管道組織或命名慣例的變更
* 您行銷團隊中的營業額

如果您的團隊最近經歷過上述任何情況 [!DNL Marketo Measure] 建議您檢閱線上管道規則，並進行適當的變更。

>[!MORELIKETHIS]
>
>* [線上頻道設定](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [UTM引數](/help/channel-tracking-and-setup/online-channels/utm-parameters.md)
>* [行銷管道和子管道](/help/channel-tracking-and-setup/online-channels/marketing-channels-and-subchannels.md)
>* [UTM最佳作法](/help/channel-tracking-and-setup/online-channels/best-practices-for-setting-up-utm-parameters.md)
