---
unique-page-id: 18874594
description: 整合式廣告平台 —  [!DNL Marketo Measure]  — 產品檔案
title: 整合式廣告平台
exl-id: df30ee8a-8b07-4f14-94e8-cc482fca8b18
feature: APIs, Integration
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '1696'
ht-degree: 0%

---

# 整合式廣告平台 {#integrated-ad-platforms}

[!DNL Marketo Measure] 有與Google AdWords、Microsoft BingAds、 [!DNL Facebook] 廣告並連按兩下「促銷活動管理員」。 透過這些API連線， [!DNL Marketo Measure] 能夠輕鬆提取資料，並將其隨外部購買者應用程式推播至您的CRM。 不需要手動上傳成本或資料。 您的帳戶只需要連線並授權至 [!DNL Marketo Measure] 應用程式。 [!DNL Marketo Measure] 之後，會自動從平台下載行銷成本，並將其載入至 [!DNL Marketo Measure] 應用程式。 如果您選取為AdWords、BingAds或 [!DNL Facebook] 廣告、 [!DNL Marketo Measure] 會自動將其引數附加至廣告的URL。

## 如何連結Ad平台 {#how-to-connect-ad-platforms}

在詳細瞭解每個平台之前，我們將先探討如何將這些帳戶中的任何一個連線到 [!DNL Marketo Measure]. 首次登入 [!DNL Marketo Measure] 應用程式並導覽至 **[!UICONTROL Settings]** 下的選項 **[!UICONTROL My Account]** 定位字元於畫面左上方。 接下來，選取 **[!UICONTROL Connections]** 在 **[!UICONTROL Integrations]** 區段內。

如下圖所示，您會看到一個按鈕，可用來設定新的廣告連線。

![](assets/2.png)

在您按一下 [!UICONTROL Set up New Ads Connection] 按鈕時，畫面會隨即顯示一個視窗（如下所示），其中包含4個廣告 [!UICONTROL connect]離子型別。 按一下連線，就會出現另一個視窗要求認證。 輸入認證，然後按一下 [!UICONTROL authorize] 將帳戶連線至 [!DNL Marketo Measure].

![](assets/select-account-type.png)

## Google AdWords {#google-adwords}

當您在中建立廣告時 [!DNL Google AdWords]，您應使用手動標籤、自動標籤或建立追蹤範本等三種方式之一來標籤行銷活動。 手動標籤AdWords URL取決於您在廣告URL結尾定義和新增引數。 手動標籤可讓任何非Google平台輕鬆讀取引數所收集的資料。

「追蹤範本」是Google提供的工具，可新增其稱為ValueTrack引數的專案。 它們的工作方式與UTM和其他標籤引數相同。

## 啟用自動標籤時會發生什麼事 {#what-happens-when-auto-tagging-is-enabled}

[!DNL Marketo Measure] 在您的中搜尋追蹤範本 [!DNL AdWords] 帳戶：

* *選項A*：找到追蹤範本。 [!DNL Marketo Measure] 將其引數新增至範本。
* *選項B*：找到協力廠商重新導向。 如果在追蹤範本中找到協力廠商重新導向， [!DNL Marketo Measure] 無法採取任何動作。 您將需要手動新增 [!DNL Marketo Measure] 標籤到協力廠商系統。 例如，Kenshoo或Marin之類的競標管理工具就是第三方重新導向的範例。 進一步瞭解如何 [競標管理工具影響 [!DNL Marketo Measure]](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md){target="_blank"}.

* *選項C*：找不到追蹤範本。 [!DNL Marketo Measure] 將會掃描您的所有Ad目的地URL [!DNL Marketo Measure] 引數。 根據掃描，如果：
   * 找到引數：設定完成！
   * 找不到引數： [!DNL Marketo Measure] 會將其引數附加至廣告目的地URL的結尾。 [!DNL Marketo Measure] 會在新廣告建立後的兩小時內附加新廣告。 請記住，不會將引數新增至範本。

進一步瞭解我們的 [[!DNL AdWords] 自動標籤功能](/help/api-connections/utilizing-marketo-measures-api-connections/understanding-marketo-measure-adwords-tagging.md){target="_blank"}.

## 如何啟用 [!DNL Marketo Measure] Adwords的自動標籤 {#how-to-enable-marketo-measure-auto-tagging-for-adwords}

啟用前 [!DNL Marketo Measure] 自動標籤， **請確定您已在Adwords帳戶中的帳戶、行銷活動或廣告群組層級啟用追蹤範本。 此為任何Adwords帳戶的要求，該帳戶將會 [!DNL Marketo Measure] 已啟用自動標籤。** 啟用追蹤範本可防止廣告效益歷史記錄資料發生任何遺失。 請注意，在「關鍵字」、「網站連結」或「廣告」層級啟用追蹤範本，將會使廣告經過審查和核准程式，並可能重新啟動廣告的績效歷史記錄。 如果完全沒有啟用追蹤範本， [!DNL Marketo Measure] 將會附加 [!DNL Marketo Measure] 直接追蹤引數至廣告的「最終URL」，也可能會導致遺失廣告紀錄資料。

設定好追蹤範本後，請依照下列指示啟用 [!DNL Marketo Measure] 自動標籤。 注意： [!DNL Marketo Measure] 也會在您的帳戶中自動標籤任何暫停的廣告。

1. 登入您的 [!DNL Marketo Measure] 帳戶位置 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}.

1. 前往 [!UICONTROL My Account] > [!UICONTROL Settings] > [!UICONTROL Integrations] > [!UICONTROL Connections].

   ![](assets/4.png)

1. 按一下將擁有的Adwords帳戶旁的鉛筆圖示 [!DNL Marketo Measure] 已啟用自動標籤。

   ![](assets/5.png)

1. 在右上角，切換 **[!UICONTROL Autotagging]** 切換至 **[!UICONTROL Yes]**. 在頁面底部，按一下 **[!UICONTROL Learn More]** 展開文字方塊並按一下 **[!UICONTROL Save]**. 自動標籤設定完成。

   ![](assets/6.png)

## 如何使用設定AdWords中的追蹤範本 [!DNL Marketo Measure] 引數 {#how-to-set-up-a-tracking-template-in-adwords-with-marketo-measure-parameters}

請記住，您應在「 」新增追蹤範本 [!UICONTROL Account]， [!UICONTROL Campaign] 或AdWords中的廣告群組層級。 如果您將追蹤範本新增到關鍵字、網站連結或廣告層級，您的廣告將需要經過稽核和核准程式，並且您可能會重新啟動廣告的績效歷史記錄。 進一步瞭解 [建立追蹤範本](https://support.google.com/adwords/answer/6076199?hl=en#tracking){target="_blank"}.

1. 登入您的 [!DNL Google AdWords] 帳戶。
1. 前往您的 [!UICONTROL Campaigns] 從左側導覽列檢視
1. 導覽至&quot;[!UICONTROL Settings]&quot;，也在左側導覽列中
1. 切換至&quot;[!UICONTROL Account Settings]&quot;上方檢視
1. 展開&quot;[!UICONTROL Tracking]「區段
1. 在追蹤範本中貼上下列其中一個文字字串以設定範本的值：

   * 如果您在所有URL都有問號，請使用下列URL文字：

   `{lpurl}&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

   * 如果您的任何URL都沒有問號，請新增下列URL文字：

   `{lpurl}?_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}*`

   為避免在手動標籤URL時發生錯誤，通常建議自動產生UTM引數。 這並不一定意味著使用AdWords自動標籤或 [!DNL Marketo Measure] 引數時，有多個工具可依據您提供的資訊，自動產生URL的引數，藉此簡化程式。

   >[!TIP]
   >
   >如果您收到指出追蹤範本無效的錯誤，請嘗試清除瀏覽器快取，然後再試一次 — 這通常可以解決問題。

## 如何自動為產生UTM標籤 [!DNL Google AdWords] {#how-to-automatically-generate-utm-tags-for-google-adwords}

UTM標籤一開始可能很難建立，但有許多工具可用來輕鬆使用UTM引數建立URL。 您可以使用下列任一資源或在網頁上搜尋更多工具。 請記住 [!DNL Marketo Measure] 不認可或保證這些平台與工具的任何內容。

**[!DNL Google URL]產生器**

Google URL Builder是使用UTM標籤建置格式正確的URL的標準工具。 只需輸入URL和每個引數的所需值，然後按一下「[!UICONTROL Generate URL]「。 如果要標籤的URL不多，這是理想的工具。 存取工具 [此處](https://support.google.com/analytics/answer/1033867?hl=en){target="_blank"}.

**EpikOne產生的Google試算表**

此試算表有一個公式可自動產生標籤的目的地URL。 若有大量連結需要標籤，這是絕佳的工具。 存取試算表 [此處](https://spreadsheets.google.com/ccc?key=p7c_HKcmspSUfEYSO0gskKw&amp;hl=en){target="_blank"}.

**Rafflecopter連結標籤工具**

Rafflecopter建立的試算表是經過修改的 [!DNL EpikOne's] 試算表。 它也包含將自動產生已標籤目的地連結以供您使用的公式。

這些工具都提供了有關如何使用和修改以符合您需求的詳細說明。 此工具可供使用 [此處](https://docs.google.com/spreadsheets/d/1QCIr1WUJQHE68cA4VTks2XE7nxuryaUymCEy_23-Oew/edit#gid=0){target="_blank"}.

**Effin令人驚歎的UTM建置器**

此工具是Chrome擴充功能，可讓您快速產生UTM標籤。 尋找它 [此處](https://chrome.google.com/webstore/detail/effin-amazing-utm-builder/eoaapiimcaimddnfhfnifgkinmpcbccp?hl=en){target="_blank"}.

## Bing Ads {#bing-ads}

Bing Ads是整合平台，可讓您啟用URL的自動標籤或使用協力廠商工具，例如 [!DNL Marketo Measure]，以標籤廣告。 [!DNL Bing Ads] 也仰賴UTM引數。

Bing Ads的自動標籤功能新增下列UTM引數：

* Utm_source
* Utm_medium
* Utm_term

Bing Ads的自動標籤也會新增下列自訂引數：

`_bt={adid}`

字串看起來像這樣：

`{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`

請務必注意 [!DNL Bing Ads] 可讓您在最終URL中使用引數的自訂標籤，以取得更精細的粒度（如果您想要的話），進而新增更多引數。

如有需要，可以使用追蹤範本，但並非必要 [!DNL Bing Ads] 和 [!DNL Marketo Measure] 以整合。 這是因為 [!DNL Bing] 允許在不變更歷史記錄的情況下編輯廣告，因此 [!DNL Marketo Measure] 能夠更新目的地URL。

自動標籤應透過以下方式啟用： [!DNL Marketo Measure] 這樣自訂 [!DNL Marketo Measure] 引數可自動附加。 使用Bing Ads不會發生失去過去廣告績效歷史記錄的風險。

造訪 [[!DNL Bing Ads]](https://advertise.bingads.microsoft.com/en-us/blog/post/august-2016/upgraded-urls-now-available-in-bing-ads-an-easier-way-to-manage-your-tracking-urls){target="_blank"} 網站，以取得在其平台上新增標籤的詳細資訊。

## facebook Ads {#facebook-ads}

此 [!DNL Marketo Measure] 與整合 [!DNL Facebook] 可讓其自動下載廣告資訊，並使用其引數標籤URL。 [!DNL Marketo Measure] 會透過我們的自動標籤提取行銷活動和廣告集資訊。 廣告集將填入我們的廣告群組名稱欄位。 如需在「 」上設定URL標籤的詳細資訊 [!DNL Facebook] 平台，請瀏覽 [!DNL Facebook] [企業](https://www.facebook.com/business/help/1016122818401732/?ref=u2u){target="_blank"} 頁面。

在使用啟用自動標籤之前 [!DNL Facebook Ads]，請將先前的效能歷史記錄匯出為CSV檔。 此時，當 [!DNL Marketo Measure] 標籤 [!DNL Facebook Ads] 及其_bf引數， [!DNL Facebook] 會將廣告讀為新廣告，並清除效能歷程記錄。 因此，如果對您和您的組織有價值，匯出先前績效的記錄很重要。

請注意，您可以連線至 [!DNL Facebook] 帳戶可隨時透過 [!DNL Marketo Measure] 不會遺失任何應用程式與資料，但只有在啟用自動標籤時，才會清除效能歷史記錄。

[請參閱本文](https://www.facebook.com/business/help/393890194130036){target="_blank"} facebook以取得匯出的詳細資訊 [!DNL Facebook] 廣告報表。

## linkedIn贊助內容 {#linkedin-sponsored-content}

linkedIn整合允許 [!DNL Marketo Measure] 標籤目的地URL [!DNL LinkedIn] 贊助內容，最終允許 [!DNL Marketo Measure] 追蹤使用者整個接觸點歷程，並將活動對應回特定 [!DNL LinkedIn] 行銷活動和創意。 這可提供客戶對其投資報酬率的深入分析 [!DNL LinkedIn] 活動。 [!DNL Marketo Measure] 會搜尋具有唯一性之創意 [!DNL LinkedIn] 共用並新增 `?_bl={creativeId}` 引數到其結尾。

因為 [!DNL LinkedIn] 「共用」可用於多個行銷活動和創意，我們要求客戶不要複製/複製/複製現有創意，以便維持其唯一性。 如果找到共用並偵測到它只用於一個Creative， [!DNL Marketo Measure] 可以將「共用」標示為原樣，而不需要重新建立任何「創意」或「共用」，而所有廣告歷史記錄（曝光數、點按數、共用數）將會保留。

找到可在多個創意人員之間共用的共用後， [!DNL Marketo Measure] 必須執行暫停、複製和重新標籤的程式，才能建立唯一的集合。 [!DNL Marketo Measure] 將會暫停並封存即時創意內容，這表示也會封存包含曝光數、點按數及社交分享的創意內容。

## 非整合平台 {#non-integrated-platforms}

針對未整合的平台 [!DNL Marketo Measure]，則 [!DNL Marketo Measure] 無法使用自動標籤功能。 需要手動新增引數。
