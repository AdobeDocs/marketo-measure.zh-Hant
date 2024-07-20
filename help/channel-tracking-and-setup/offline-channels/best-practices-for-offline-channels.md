---
description: 離線頻道的最佳作法 —  [!DNL Marketo Measure]
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

若要產生準確的[!DNL Marketo Measure]報表，您的行銷管道必須正確設定。 &#39;[!UICONTROL Marketing Channel]&#39;欄位會顯示接觸點可以屬於的最高層級行銷策略群組（例如，事件、網路研討會、內容整合等）。

設定行銷管道有兩個層面：線上和離線。 本檔案著重於針對設定及維護您的離線管道以及如何透過CRM Campaigns與[!DNL Marketo Measure]同步的[!DNL Marketo Measure]最佳實務建議。

離線管道有兩個主要方面：

1. 離線管道對應，此架構會告訴[!DNL Marketo Measure]離線接觸點屬於哪個管道和子管道
1. 離線Campaign同步，即建立離線接觸點

離線接觸點是從CRM Campaign建立，並用於追蹤無法透過在您網站頁面上實作的[!DNL Marketo Measure] JavaScript以數位方式追蹤的任何行銷互動。 當CRM行銷活動與[!DNL Marketo Measure]同步時，會為行銷活動中定義的行銷活動成員建立接觸點。

這些接觸點的「行銷管道」值以行銷活動上的「型別」欄位為基礎。 &#39;CRM Campaign Type&#39;到&#39;Marketing Channel&#39;和&#39;Subchannel&#39;的對映是在[!DNL Marketo Measure]帳戶設定的&#39;Offline Channel&#39;索引標籤中管理的。 確保您的離線管道對應正確且為最新狀態，將可保證您的離線接觸點資料已歸因至[!DNL Marketo Measure]報表內的正確行銷管道和子管道。

## 最佳實務 | 離線管道對應 {#best-practice-offline-channel-mapping}

無論您是第一次對應離線頻道，還是隻檢視離線頻道以檢查其準確性，請記住以下最佳實務。

* 為離線管道建立審慎的架構
   * 請花點時間思考行銷活動的組織方式，以及行銷活動如何融入[!DNL Marketo Measure]框架。 決定離線頻道中應該顯示哪些頻道和子頻道，以及哪些CRM行銷活動型別會區分這些頻道
* 先努力利用您目前的CRM Campaign「型別」值
   * 離線管道由CRM Campaign「型別」定義，不過可能需要建立自訂CRM Campaign「型別」值，以配合理想的離線管道和子管道值。 理想的自訂CRM Campaign「型別」值應該遵循如下所示的命名慣例：
      * 頻道 — 子頻道
      * 範例：事件 — 商展
      * 這可確保對應至子管道層級儘可能簡單明瞭
* 一個子管道只能對應至一個CRM行銷活動「型別」
   * 多個CRM Campaign「型別」可對映至單一管道，但只有一個CRM Campaign「型別」可對映至每個管道內的每個子管道
* 只有離線CRM促銷活動「型別」對應至離線頻道，因為只有離線促銷活動才會與[!DNL Marketo Measure]同步以建立接觸點：
   * ONLINE CRM Campaign的&#39;Types&#39;應該對應到[!UICONTROL Marketing Channel] = &quot;NULL&quot;。 建議使用此值，因為此值會成為「紅色旗標」，表示您的離線管道已檢閱，且對應至「NULL」的任何CRM Campaign「型別」均為線上「型別」，不應與[!DNL Marketo Measure]同步。 已經透過[!DNL Marketo Measure]線上功能與管道追蹤與Online CRM Campaign「型別」相關的接觸點。 同步這些行銷活動會產生「重複」接觸點/重複計數的風險

## 最佳實務 | 離線Campaign同步 {#best-practice-offline-campaign-sync}

* 確定每個CRM行銷活動的「型別」欄位都準確
   * 「型別」會針對在同步後源自促銷活動之任何接觸點，決定行銷管道和子管道
* 不論是使用CRM型Campaign同步方法（啟用購買者接觸點）還是[!DNL Marketo Measure]應用程式型同步方法（在您[!UICONTROL Marketo Measure]帳戶設定的&#39;[!UICONTROL Campaigns]&#39;標籤內的「自訂Campaign同步」），只有在促銷活動成員與Campaign和您的品牌有實際的離線參與時，才應該建立離線接觸點：
   * 對於離線頻道，例如活動或網路研討會：「註冊」通常透過網站上的表單提交和[!DNL Marketo Measure]線上功能進行追蹤。 因此，狀態為「已註冊」的Campaign成員不應收到Campaign的離線接觸點，以避免重複計算。 離線接觸點僅能代表活動或網路研討會的「出席情況」。
   * 某些離線頻道（例如內容整合）較為直接簡單，因為每個行銷活動會員都有相同的「已回應」狀態，這表示他們確實已回應行銷活動，在此情況下，就是從協力廠商網站下載內容，因此應該會收到離線接觸點
* 在[!DNL Marketo Measure]應用程式中使用「自訂促銷活動同步」方法時，請確定「接觸點日期」欄位是根據「促銷活動」或「促銷活動成員」的日期欄位，最能指出實際發生接觸點互動的時間
* 如果您需要覆寫來源為CRM Campaign之任何離線接觸點的「接觸點日期」，請使用「大量更新接觸點日期」按鈕。 「接觸點日期」必須儘可能準確，以確保接觸點擁有儘可能準確的「接觸點位置」，並進而擁有適當的歸因點數金額

## 維護最佳實務 {#best-practice-for-maintenance}

初始設定後，您的離線管道設定會繼續據此建立離線接觸點。 根據最佳實務，建議您每年至少審視離線設定兩次。 這保證了購買者接觸點資料的乾淨和準確。

此外，如果您變更促銷活動管理或程式，您必須確定正在更新[!DNL Marketo Measure]離線頻道對應及/或同步程式。

可能觸發您的團隊更新[!DNL Marketo Measure]中離線頻道設定的變更可能包括：

* CRM行銷活動「型別」已建立或已編輯
* 已建立或已編輯行銷活動成員「狀態」
* 如果透過「啟用購買者接觸點」欄位使用CRM Campaign同步方法，請確定已針對建立的每個CRM Campaign檢閱並更新此欄位。 如果此欄位被忽略，將不會有任何相關的離線接觸點資料
* 如果您從CRM Campaign遇到任何看起來像線上接觸點的離線接觸點（行銷管道= NULL），請確定已檢閱相關的CRM Campaign並停用同步

如果您的團隊最近遇到上述任何問題，[!DNL Marketo Measure]建議您檢閱離線管道對應和離線行銷活動，以進行適當的變更並確保它們已正確同步。

>[!MORELIKETHIS]
>
>* [離線頻道設定](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [自訂Campaign同步 — 應用程式同步](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [正在同步處理離線行銷活動 — CRM同步](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md)
>* [離線行銷活動與行銷活動成員 — CRM同步](/help/channel-tracking-and-setup/offline-channels/legacy-processes/campaigns-and-campaign-members.md)
>* [Campaign同步日期 — CRM同步](/help/channel-tracking-and-setup/offline-channels/legacy-processes/campaign-sync-dates.md)
>* 多個行銷活動記錄型別的[設定](/help/channel-tracking-and-setup/offline-channels/configurations-for-multiple-campaign-record-types.md)
>* [建立行銷活動清單檢視](/help/channel-tracking-and-setup/offline-channels/legacy-processes/creating-a-campaign-list-view-for-salesforce-campaigns.md)
>* [正在同步處理歷史資料](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-historical-data.md)
