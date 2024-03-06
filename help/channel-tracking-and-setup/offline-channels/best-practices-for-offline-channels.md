---
description: 離線管道的最佳作法 —  [!DNL Marketo Measure]
title: 離線管道的最佳作法
exl-id: 71c50614-8d5b-469f-bc02-3cc489464a4e
feature: Channels
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 0%

---

# 離線管道的最佳作法 {#best-practices-for-offline-channels}

## 概觀 {#overview}

以取得精確的 [!DNL Marketo Measure] 報告，您的行銷管道必須正確設定。 「[!UICONTROL Marketing Channel]「欄位會顯示接觸點可所屬的最高層級行銷策略群組（例如，事件、網路研討會、內容整合等）。

設定行銷管道有兩個層面：線上和離線。 本檔案著重於 [!DNL Marketo Measure] 設定及維護離線管道的最佳作法建議，以及如何與同步 [!DNL Marketo Measure] 透過CRM Campaigns。

離線管道有兩個主要方面：

1. 離線管道對應，此架構會告知 [!DNL Marketo Measure] 離線接觸點屬於哪個管道和子管道
1. 離線Campaign同步，即建立離線接觸點

離線接觸點是從CRM Campaign建立的，並用於追蹤任何無法透過數位追蹤的行銷互動。 [!DNL Marketo Measure] 在您網站的頁面上實作的JavaScript。 CRM行銷活動與同步時 [!DNL Marketo Measure]，會為促銷活動中的已定義促銷活動成員建立接觸點。

這些接觸點的「行銷管道」值以行銷活動上的「型別」欄位為基礎。 「CRM行銷活動型別」與「行銷管道」和「子管道」的對應，是在的「離線管道」索引標籤中管理的。 [!DNL Marketo Measure] 帳戶設定。 確保您的離線管道對應正確且為最新狀態，將可保證您的離線接觸點資料已歸因至您網站內的正確行銷管道和子管道。 [!DNL Marketo Measure] 報表。

## 最佳實務 | 離線管道對應 {#best-practice-offline-channel-mapping}

無論您是第一次對應離線頻道，還是隻檢視離線頻道以檢查其準確性，請記住以下最佳實務。

* 為離線管道建立審慎的架構
   * 請花點時間思考行銷活動的組織方式，以及這些組織如何適合 [!DNL Marketo Measure] 框架。 決定離線頻道中應該顯示哪些頻道和子頻道，以及哪些CRM行銷活動型別會區分這些頻道
* 先努力利用您目前的CRM Campaign「型別」值
   * 離線管道由CRM Campaign「型別」定義，不過可能需要建立自訂CRM Campaign「型別」值，以配合理想的離線管道和子管道值。 理想的自訂CRM Campaign「型別」值應該遵循如下所示的命名慣例：
      * 頻道 — 子頻道
      * 範例：事件 — 商展
      * 這可確保對應至子管道層級儘可能簡單明瞭
* 一個子管道只能對應至一個CRM行銷活動「型別」
   * 多個CRM Campaign「型別」可對映至單一管道，但只有一個CRM Campaign「型別」可對映至每個管道內的每個子管道
* 只有離線CRM促銷活動「型別」對應至離線頻道，因為只有離線促銷活動才會與同步 [!DNL Marketo Measure] 若要建立接觸點：
   * ONLINE CRM Campaign的「型別」應該對應至 [!UICONTROL Marketing Channel] = &quot;NULL&quot;。 建議使用此值，因為它會成為「紅色旗標」，表示您的離線管道已檢閱，而任何對應至「NULL」的CRM Campaign「型別」為線上「型別」，不應與同步 [!DNL Marketo Measure]. 與線上CRM Campaign「型別」相關的接觸點已透過進行追蹤 [!DNL Marketo Measure] 線上功能和管道。 同步這些行銷活動會產生「重複」接觸點/重複計數的風險

## 最佳實務 | 離線Campaign同步 {#best-practice-offline-campaign-sync}

* 確定每個CRM行銷活動的「型別」欄位都準確
   * 「型別」會針對在同步後源自促銷活動之任何接觸點，決定行銷管道和子管道
* 使用CRM型Campaign同步方法（啟用購買者接觸點）或 [!DNL Marketo Measure] 應用程式型同步方法（自訂Campaign同步於）[!UICONTROL Campaigns]的「 」標籤 [!UICONTROL Marketo Measure] 帳戶設定)，只有在行銷活動會員與行銷活動及您的品牌有實際的離線參與時，才應該建立離線接觸點：
   * 對於離線頻道，例如活動或網路研討會：「註冊」通常透過網站上的表單提交進行追蹤，並且 [!DNL Marketo Measure] 線上功能。 因此，狀態為「已註冊」的Campaign成員不應收到Campaign的離線接觸點，以避免重複計算。 離線接觸點僅能代表活動或網路研討會的「出席情況」。
   * 某些離線頻道（例如內容整合）較為直接簡單，因為每個行銷活動會員都有相同的「已回應」狀態，這表示他們確實已回應行銷活動，在此情況下，就是從協力廠商網站下載內容，因此應該會收到離線接觸點
* 在中使用自訂Campaign同步方法時 [!DNL Marketo Measure] 應用程式中，請確定「接觸點日期」欄位是根據「促銷活動」或「促銷活動成員」的日期欄位，而此日期欄位最能代表實際發生接觸點互動的時間
* 如果您需要覆寫來源為CRM Campaign之任何離線接觸點的「接觸點日期」，請使用「大量更新接觸點日期」按鈕。 「接觸點日期」必須儘可能準確，以確保接觸點擁有儘可能準確的「接觸點位置」，並進而擁有適當的歸因點數金額

## 維護最佳實務 {#best-practice-for-maintenance}

初始設定後，您的離線管道設定會繼續據此建立離線接觸點。 根據最佳實務，建議您每年至少審視離線設定兩次。 這保證了購買者接觸點資料的乾淨和準確。

此外，如果您對Campaign管理或流程進行變更，請務必更新您的 [!DNL Marketo Measure] 離線管道對應和/或同步程式。

變更可能會觸發您的團隊更新中的離線頻道設定 [!DNL Marketo Measure] 可能包括：

* CRM行銷活動「型別」已建立或已編輯
* 已建立或已編輯行銷活動成員「狀態」
* 如果透過「啟用購買者接觸點」欄位使用CRM Campaign同步方法，請確定已針對建立的每個CRM Campaign檢閱並更新此欄位。 如果此欄位被忽略，將不會有任何相關的離線接觸點資料
* 如果您從CRM Campaign遇到任何看起來像線上接觸點的離線接觸點（行銷管道= NULL），請確定已檢閱相關的CRM Campaign並停用同步

如果您的團隊最近經歷過上述任何情況， [!DNL Marketo Measure] 建議您檢閱離線管道對應和離線行銷活動，進行適當的變更並確保已正確同步這些活動。

>[!MORELIKETHIS]
>
>* [離線管道設定](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [自訂Campaign同步 — 應用程式同步](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [同步離線行銷活動 — CRM同步](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md)
>* [離線Campaign與Campaign成員 — CRM同步](/help/channel-tracking-and-setup/offline-channels/legacy-processes/campaigns-and-campaign-members.md)
>* [Campaign同步日期 — CRM同步](/help/channel-tracking-and-setup/offline-channels/legacy-processes/campaign-sync-dates.md)
>* [多種行銷活動記錄型別的設定](/help/channel-tracking-and-setup/offline-channels/configurations-for-multiple-campaign-record-types.md)
>* [建立行銷活動清單檢視](/help/channel-tracking-and-setup/offline-channels/legacy-processes/creating-a-campaign-list-view-for-salesforce-campaigns.md)
>* [同步歷史資料](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-historical-data.md)
