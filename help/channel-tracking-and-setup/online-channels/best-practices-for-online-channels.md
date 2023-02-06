---
description: 線上管道最佳實務 —  [!DNL Marketo Measure]  — 產品檔案
title: 線上管道最佳實務
exl-id: 766cb01c-98b3-492d-bb35-e0a78b76333a
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 0%

---

# 線上管道最佳實務 {#best-practices-for-online-channels}

## 概觀 {#overview}

要準確 [!DNL Marketo Measure] 報表，您的行銷管道必須正確設定。 行銷管道欄位會顯示接觸點可隸屬的行銷活動的最高層級群組（例如付費搜尋、直接、社交等）。

設定行銷管道有兩個方面：線上和離線。 本檔案將著重於 [!DNL Marketo Measure] 設定及維護線上管道的最佳實務建議。

線上管道規則是指引您了解 [!DNL Marketo Measure] 映射您的數位接觸點，即透過 [!DNL Marketo Measure] JS。 如果這些規則不完整或未正確排序，則接觸點可歸因於不正確的管道，因此會降低報表的準確度。 確保您的線上管道規則正確且最新，將可確保將您的數位資料歸屬於您 [!DNL Marketo Measure] 報告。

## 最佳實務 {#best-practice}

無論您是第一次設定規則，還是只是檢閱規則以檢查正確性，請牢記下列最佳實務。

請花點時間思考行銷活動的組織方式，以及行銷活動與 [!DNL Marketo Measure] 框架。 決定線上管道中應代表哪些管道和子管道，以及哪些促銷活動、UTM參數或反向連結網站可區分這些管道。

請記住：

* 所有數位通道和子通道都應至少使用一個規則來表示
   * 如果管道不會將訪客帶往您的網站，則不是線上管道
* 一個管道/子管道可以有多個規則
   * 可將多個規則視為「投放更寬的網」，以確保每個接觸點皆正確對應。 通常，參數可能會不正確地新增或完全遺漏，因此，有多個規則來擷取通道/子通道是確保對應正確性的好辦法。
* [!DNL Marketo Measure] 邏輯會從試算表的頂端列開始，依遞減順序排列接觸點對應的優先順序
   * [!DNL Marketo Measure] 讀取每個規則（列），尋找true並首次符合。 接著，接觸點會對應至該管道/子管道
   * 請勿依字母順序排序工作表，因為這會干擾邏輯規則。
* 維護括弧內的規則，不編輯或添加到括弧內的規則(示例； [AdWords付費搜尋] 或 [Facebook付費] )
   * 這些都是現成的 [!DNL Marketo Measure] 內建邏輯的規則，這些規則會系結 [!DNL Marketo Measure] 整合。 將該管道/子管道區段的這些規則列為優先順序，以確保 [!DNL Marketo Measure] 整合功能可如設計般運作。
* 上傳檔案後，七天內無法變更任何規則
   * [!DNL Marketo Measure] 利用此時間處理和更新接觸點，因此，請務必在上傳前仔細檢查規則。

## 維護最佳實務 {#best-practice-for-maintenace}

儲存並處理後，「線上管道」規則會持續運作，將您的數位接觸點分段。 不過，某些變更或案例會導致您想要檢閱線上管道設定。 [!DNL Marketo Measure] 建議您每6個月檢閱一次線上管道規則。 這將確保您的 [!DNL Marketo Measure] 資料與您對線上管道/子管道的內部定義以及您對UTM的使用方式一致。

可能觸發您的團隊執行線上管道維護的其他項目包括…….

* 新數位頻道/子頻道已推出
* 更新或更改UTM參數
* 管道組織或命名慣例的變更
* 行銷團隊的營業額

如果您的團隊最近遇到過上述任何情況 [!DNL Marketo Measure] 建議您檢閱線上管道規則，並進行適當的變更。

>[!MORELIKETHIS]
>
>* [線上頻道設定](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [UTM參數](/help/channel-tracking-and-setup/online-channels/utm-parameters.md)
>* [行銷管道和子管道](/help/channel-tracking-and-setup/online-channels/marketing-channels-and-subchannels.md)
>* [UTM最佳作法](/help/channel-tracking-and-setup/online-channels/best-practices-for-setting-up-utm-parameters.md)

