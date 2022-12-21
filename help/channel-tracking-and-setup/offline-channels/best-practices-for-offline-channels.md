---
description: 離線頻道最佳實務 —  [!DNL Marketo Measure]  — 產品檔案
title: 離線頻道最佳實務
exl-id: 71c50614-8d5b-469f-bc02-3cc489464a4e
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 0%

---

# 離線頻道最佳實務 {#best-practices-for-offline-channels}

## 總覽 {#overview}

要準確 [!DNL Marketo Measure] 報表，您的行銷管道必須正確設定。 「[!UICONTROL Marketing Channel]「 」欄位顯示接觸點可屬於的最高層級行銷策略群組（例如，事件、網路研討會、內容整合等）。

設定行銷管道有兩個方面：線上和離線。 本檔案將著重於 [!DNL Marketo Measure] 設定和維護離線管道的最佳實務建議，以及這些管道的同步方式 [!DNL Marketo Measure] 透過CRM促銷活動。

離線通道有兩個主要方面：

1. 離線管道對應，此架構會告訴 [!DNL Marketo Measure] 離線接觸點屬於哪個管道和子管道
1. 離線促銷活動同步，即建立離線接觸點

離線接觸點是從CRM促銷活動建立，用來追蹤任何無法透過 [!DNL Marketo Measure] 在您網站的頁面上實作的JavaScript。 當CRM促銷活動同步至 [!DNL Marketo Measure]，則會為促銷活動中定義的促銷活動成員建立接觸點。

這些接觸點的「行銷管道」值是以促銷活動上的「類型」欄位為基礎。 「CRM促銷活動類型」與「行銷管道」和「子管道」的對應，是在您的 [!DNL Marketo Measure] 帳戶設定。 確保您的離線管道對應正確且最新，將可確保您的離線接觸點資料歸屬於您內正確的行銷管道和子管道 [!DNL Marketo Measure] 報告。

## 最佳實務 |離線通道對應 {#best-practice-offline-channel-mapping}

無論您是第一次對應離線管道，還是只是檢閱管道以檢查準確性，請牢記下列最佳實務。

* 為離線管道建立審慎的架構
   * 請花點時間思考行銷活動的組織方式，以及行銷活動與 [!DNL Marketo Measure] 框架。 決定離線頻道中應代表哪些頻道和子頻道，以及哪些CRM促銷活動類型可區分這些頻道
* 請先努力利用您目前的CRM促銷活動「類型」值
   * 離線管道由CRM促銷活動「類型」定義，但是，自訂CRM促銷活動「類型」值可能需要建立，以容納理想的離線管道和子管道值。 理想的自訂CRM促銷活動「類型」值應具備下列命名慣例：
      * 管道 — 子管道
      * 範例：活動 — 商展
      * 這可確保映射至子通道級別盡可能簡單和乾淨
* 一個子管道只能對應至一個CRM促銷活動「類型」
   * 多個CRM促銷活動「類型」可對應至單一管道，但每個管道內的每個子管道僅能對應一個CRM促銷活動「類型」
* 只有離線CRM促銷活動「類型」應對應至離線通道，因為只有離線促銷活動才會與同步 [!DNL Marketo Measure] 若要建立接觸點：
   * 線上CRM促銷活動「類型」應對應至 [!UICONTROL Marketing Channel] = &quot;NULL&quot;。 建議使用此值，因為它的作用是「紅色標幟」，表示您的離線管道已被審核，且對應至「NULL」的任何CRM促銷活動「類型」為「線上類型」，不應與同步 [!DNL Marketo Measure]. 與線上CRM促銷活動「類型」相關的接觸點將已透過 [!DNL Marketo Measure] 線上功能和通道。 同步這些促銷活動可能會導致「重複」接觸點/重複計數

## 最佳實務 |離線促銷活動同步 {#best-practice-offline-campaign-sync}

* 確定每個CRM促銷活動的「類型」欄位正確
   * 「類型」會決定同步後，來自促銷活動的任何接觸點的行銷管道和子管道
* 無論使用CRM型促銷活動同步方法（啟用購買者接觸點），還是 [!DNL Marketo Measure] 應用程式型同步方法(在「[!UICONTROL Campaigns]「 」頁簽 [!UICONTROL Marketo Measure] 帳戶設定)，則只有在促銷活動成員與促銷活動和您的品牌有實際的離線參與時，才應建立離線接觸點：
   * 對於「活動」或「網路研討會」等離線管道：「註冊」通常會透過網站上的表單提交來追蹤，而 [!DNL Marketo Measure] 線上功能。 因此，狀態為「已註冊」的促銷活動成員不應從促銷活動接收離線接觸點，以避免重複計數。 離線接觸點應只代表「出席」參加活動或網路研討會。
   * 某些離線管道（例如內容整合）通常更簡單明瞭，因為每個促銷活動成員都有相同的「回應」狀態，代表他們確實回應了促銷活動，在這種情況下，請在第三方網站上下載內容，因此應該會收到離線接觸點
* 在 [!DNL Marketo Measure] 應用程式中，請確定「接觸點日期」欄位是以來自促銷活動或促銷活動成員的日期欄位為基礎，該欄位最能指示接觸點互動實際發生的時間
* 如果您需要覆寫來自CRM促銷活動之任何離線接觸點的「接觸點日期」，請運用「大量更新接觸點日期」按鈕。 「接觸點日期」必須盡可能準確，以確保接觸點擁有盡可能準確的「接觸點位置」，因此，歸因評分的適當數量

## 維護最佳實務 {#best-practice-for-maintenance}

一開始設定後，您的離線管道設定會繼續據此建立離線接觸點。 建議您每年至少檢閱兩次離線設定，這是最佳作法。 這可確保購買者接觸點資料乾淨且準確。

此外，如果您對促銷活動管理或程式進行任何變更，則需要確定您正在更新 [!DNL Marketo Measure] 離線通道對應和/或同步程式。

可能觸發您的團隊對 [!DNL Marketo Measure] 可能包括：

* 已建立或編輯CRM促銷活動「類型」
* 已建立或編輯促銷活動成員「狀態」
* 如果透過「啟用購買者接觸點」欄位使用CRM促銷活動同步方法，請務必針對所建立的每個CRM促銷活動審核並更新此欄位。 如果忽略此欄位，則不會有任何相關的離線接觸點資料
* 如果您遇到CRM促銷活動中任何看似線上接觸點（行銷管道= NULL）的離線接觸點，請確定已檢閱相關CRM促銷活動，且已停用同步

如果你的團隊最近遇到過上述情況， [!DNL Marketo Measure] 建議您檢閱離線管道對應和離線促銷活動，進行適當的變更，並確保同步正確。

>[!MORELIKETHIS]
>
>* [離線頻道設定](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [自訂促銷活動同步 — 應用程式同步](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [同步離線促銷活動 — CRM同步](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md)
>* [離線促銷活動與促銷活動成員 — CRM同步](/help/channel-tracking-and-setup/offline-channels/campaigns-and-campaign-members.md)
>* [促銷活動同步日期 — CRM同步](/help/channel-tracking-and-setup/offline-channels/campaign-sync-dates.md)
>* [多種促銷活動記錄類型的設定](/help/channel-tracking-and-setup/offline-channels/configurations-for-multiple-campaign-record-types.md)
>* [建立促銷活動清單檢視](/help/channel-tracking-and-setup/offline-channels/creating-a-campaign-list-view-for-salesforce-campaigns.md)
>* [同步歷史資料](/help/channel-tracking-and-setup/offline-channels/syncing-historical-data.md)

