---
unique-page-id: 18874594
description: 整合式廣告平台 —  [!DNL Marketo Measure]
title: 整合式廣告平台
exl-id: df30ee8a-8b07-4f14-94e8-cc482fca8b18
feature: APIs, Integration
source-git-commit: 48962b999fdd16fe96d18708ec301e64a39bc76e
workflow-type: tm+mt
source-wordcount: '1644'
ht-degree: 0%

---

# 整合式廣告平台 {#integrated-ad-platforms}

[!DNL Marketo Measure]擁有與Google AdWords、Microsoft BingAds、[!DNL Facebook]個廣告和DoubleClick促銷活動管理員的API連線。 透過這些API連線，[!DNL Marketo Measure]能夠輕鬆提取資料，並將其連同外部購買者應用程式推播到您的CRM。 不需要手動上傳成本或資料。 您的帳戶只需要連線並授權至[!DNL Marketo Measure]應用程式即可。 然後[!DNL Marketo Measure]將自動從平台下載行銷成本，並將其載入至[!DNL Marketo Measure]應用程式。 如果您選取啟用AdWords、BingAds或[!DNL Facebook]廣告的自動標籤，[!DNL Marketo Measure]會自動將其引數附加至廣告的URL。

## 如何連結Ad平台 {#how-to-connect-ad-platforms}

在深入瞭解每個平台的具體資訊之前，我們將先探討如何將這些帳戶中的任何一個連結至[!DNL Marketo Measure]。 請先登入[!DNL Marketo Measure]應用程式並導覽至畫面左上方的&#x200B;**[!UICONTROL My Account]**&#x200B;標籤下的&#x200B;**[!UICONTROL Settings]**&#x200B;選項。 接著，在左側的&#x200B;**[!UICONTROL Integrations]**&#x200B;區段下選取&#x200B;**[!UICONTROL Connections]**。

如下圖所示，您會看到一個按鈕，可用來設定新的廣告連線。

![](assets/2.png)

按一下[!UICONTROL Set up New Ads Connection]按鈕後，會出現一個視窗（如下所示），其中包含4種廣告[!UICONTROL connect]離子型別。 按一下連線，就會出現另一個視窗要求認證。 輸入認證，然後按一下[!UICONTROL authorize]以連線帳戶至[!DNL Marketo Measure]。

![](assets/select-account-type.png)

## Google AdWords {#google-adwords}

當您在[!DNL Google AdWords]中建立廣告時，建議使用三種方式之一來標籤行銷活動：手動標籤、自動標籤或建立追蹤範本。 手動標籤AdWords URL取決於您在廣告URL結尾定義和新增引數。 手動標籤可讓任何非Google平台輕鬆讀取引數所收集的資料。

「追蹤範本」是Google提供的工具，可新增其稱為ValueTrack引數的專案。 它們的工作方式與UTM和其他標籤引數相同。

## 啟用自動標籤時會發生什麼事 {#what-happens-when-auto-tagging-is-enabled}

[!DNL Marketo Measure]在您的[!DNL AdWords]帳戶中搜尋追蹤範本：

* *選項A*：找到追蹤範本。 [!DNL Marketo Measure]將其引數新增至範本。
* *選項B*：找到第三方重新導向。 如果在追蹤範本中找到協力廠商重新導向，[!DNL Marketo Measure]無法採取任何動作。 您必須手動將[!DNL Marketo Measure]標籤新增至協力廠商系統。 例如，Kenshoo或Marin之類的競標管理工具就是第三方重新導向的範例。 深入瞭解[競標管理工具如何影響 [!DNL Marketo Measure]](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md){target="_blank"}。

* *選項C*：找不到追蹤範本。 [!DNL Marketo Measure]會掃描[!DNL Marketo Measure]引數的所有廣告目的地URL。 根據掃描，如果：
   * 找到引數：設定完成！
   * 找不到引數： [!DNL Marketo Measure]會將其引數附加至廣告目的地URL的結尾。 [!DNL Marketo Measure]會在建立新廣告後的兩小時內附加新廣告。 請記住，不會將引數新增至範本。

深入瞭解[[!DNL AdWords] 自動標籤功能](/help/api-connections/utilizing-marketo-measures-api-connections/understanding-marketo-measure-adwords-tagging.md){target="_blank"}。

## 如何啟用Adwords的[!DNL Marketo Measure]自動標籤 {#how-to-enable-marketo-measure-auto-tagging-for-adwords}

在啟用[!DNL Marketo Measure]自動標籤之前，**請確定您已在Adwords帳戶中的帳戶、行銷活動或廣告群組層級啟用追蹤範本。 任何已啟用[!DNL Marketo Measure]自動標籤的Adwords帳戶都需要此專案。**&#x200B;啟用追蹤範本可防止廣告效能歷程記錄資料遺失。 請注意，在「關鍵字」、「網站連結」或「廣告」層級啟用追蹤範本，將導致廣告經過稽核和核准程式，並可能重新啟動廣告的績效歷史記錄。 如果完全沒有啟用追蹤範本，[!DNL Marketo Measure]會將[!DNL Marketo Measure]追蹤引數直接附加至廣告的「最終URL」，這也會造成廣告歷程記錄資料遺失。

設定好追蹤範本後，請依照下列指示啟用[!DNL Marketo Measure]自動標籤。 注意： [!DNL Marketo Measure]也會在您的帳戶中自動標籤任何暫停的廣告。

1. 在[experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}登入您的[!DNL Marketo Measure]帳戶。

1. 前往「[!UICONTROL My Account] > [!UICONTROL Settings] > [!UICONTROL Integrations] > [!UICONTROL Connections]」。

   ![](assets/4.png)

1. 按一下將啟用[!DNL Marketo Measure]自動標籤的Adwords帳戶旁的鉛筆圖示。

   ![](assets/5.png)

1. 在右上角，將&#x200B;**[!UICONTROL Autotagging]**&#x200B;切換至&#x200B;**[!UICONTROL Yes]**。 在頁面底部，按一下&#x200B;**[!UICONTROL Learn More]**&#x200B;以展開文字方塊並按一下&#x200B;**[!UICONTROL Save]**。 自動標籤設定完成。

   ![](assets/6.png)

## 如何使用[!DNL Marketo Measure]引數在AdWords中設定追蹤範本 {#how-to-set-up-a-tracking-template-in-adwords-with-marketo-measure-parameters}

請記住，您應該在AdWords中的[!UICONTROL Account]、[!UICONTROL Campaign]或廣告群組層級新增追蹤範本。 如果您將追蹤範本新增到關鍵字、網站連結或廣告層級，您的廣告將需要經過稽核和核准程式，並且您可能會重新啟動廣告的績效歷史記錄。 深入瞭解[建立追蹤範本](https://support.google.com/adwords/answer/6076199?hl=en#tracking){target="_blank"}。

1. 登入您的[!DNL Google AdWords]帳戶。
1. 從左側導覽列移至您的[!UICONTROL Campaigns]檢視
1. 導覽至[!UICONTROL Settings]，左側導覽列中也有此標籤
1. 切換至頂端的&quot;[!UICONTROL Account Settings]&quot;檢視
1. 展開&quot;[!UICONTROL Tracking]&quot;區段
1. 在追蹤範本中貼上下列其中一個文字字串以設定範本的值：

   * 如果您在所有URL都有問號，請使用下列URL文字：

   `{lpurl}&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

   * 如果您的任何URL都沒有問號，請新增下列URL文字：

   `{lpurl}?_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}*`

   為避免在手動標籤URL時發生錯誤，通常建議自動產生UTM引數。 這並不一定意味著使用AdWords或[!DNL Marketo Measure]引數自動標籤，有多種工具可依據您提供的資訊自動產生URL的引數，藉此簡化程式。

   >[!TIP]
   >
   >如果您收到指出追蹤範本無效的錯誤，請嘗試清除瀏覽器快取，然後再試一次 — 這通常可解決此問題。

## 如何自動產生[!DNL Google AdWords]的UTM標籤 {#how-to-automatically-generate-utm-tags-for-google-adwords}

UTM標籤一開始可能很難建立，但有許多工具可用來輕鬆使用UTM引數建立URL。 您可以使用下列任一資源或在網頁上搜尋更多工具。 請記住，[!DNL Marketo Measure]不認可或保證這些平台與工具的任何內容。

**[!DNL Google URL]產生器**

Google URL Builder是使用UTM標籤建置格式正確的URL的標準工具。 輸入URL和每個引數的所需值，然後按一下&quot;[!UICONTROL Generate URL]&quot;。 如果要標籤的URL不多，這是理想的工具。 在[這裡](https://support.google.com/analytics/answer/1033867?hl=en){target="_blank"}存取工具。

由EpikOne產生的&#x200B;**Google試算表**

此試算表有一個公式可自動產生標籤的目的地URL。 若有大量連結需要標籤，這是絕佳的工具。 在[這裡](https://spreadsheets.google.com/ccc?key=p7c_HKcmspSUfEYSO0gskKw&hl=en){target="_blank"}存取試算表。

**Rafflecopter連結標籤工具**

Rafflecopter建立的試算表是[!DNL EpikOne's]試算表的修改版本。 它也包含將自動產生已標籤目的地連結以供您使用的公式。

這些工具都提供了有關如何使用和修改以符合您需求的詳細說明。 工具可在[這裡](https://docs.google.com/spreadsheets/d/1QCIr1WUJQHE68cA4VTks2XE7nxuryaUymCEy_23-Oew/edit#gid=0){target="_blank"}取得。

**Effin令人驚豔的UTM產生器**

此工具是Chrome擴充功能，可讓您快速產生UTM標籤。 在[這裡](https://chrome.google.com/webstore/detail/effin-amazing-utm-builder/eoaapiimcaimddnfhfnifgkinmpcbccp?hl=en){target="_blank"}找到它。

## Bing Ads {#bing-ads}

Bing Ads是整合平台，可讓您啟用URL的自動標籤，或使用協力廠商工具（例如[!DNL Marketo Measure]）來標籤廣告。 [!DNL Bing Ads]也依賴UTM引數。

我們的整合支援以下廣告型別：

* 文字廣告
* 行動裝置廣告
* 展開的文字廣告


Bing Ads的自動標籤功能新增下列UTM引數：

* Utm_source
* Utm_medium
* Utm_term

Bing Ads的自動標籤也會新增下列自訂引數：

`_bt={adid}`

字串看起來像這樣：

`{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`

請務必注意，如果您願意，[!DNL Bing Ads]可讓您在最終URL中使用其自訂標籤來新增更多引數，以獲得更多精細度。

如有需要，可以使用追蹤範本，但[!DNL Bing Ads]和[!DNL Marketo Measure]不需要整合。 這是因為[!DNL Bing]允許在不變更歷史記錄的情況下編輯廣告，因此[!DNL Marketo Measure]能夠更新目的地URL。

應透過[!DNL Marketo Measure]啟用自動標籤，以便可自動附加自訂[!DNL Marketo Measure]引數。 使用Bing Ads不會發生失去過去廣告績效歷史記錄的風險。

造訪[[!DNL Bing Ads]](https://advertise.bingads.microsoft.com/en-us/blog/post/august-2016/upgraded-urls-now-available-in-bing-ads-an-easier-way-to-manage-your-tracking-urls){target="_blank"}網站，瞭解在其平台上新增標籤的詳細資訊。

## facebook Ads {#facebook-ads}

[!DNL Marketo Measure]與[!DNL Facebook]的整合可讓其自動下載廣告資訊，並使用其引數標籤URL。 [!DNL Marketo Measure]將透過我們的自動標籤提取行銷活動和廣告集資訊。 廣告集將填入我們的廣告群組名稱欄位。 如需在[!DNL Facebook]平台上設定URL標籤的詳細資訊，請造訪[!DNL Facebook] [企業](https://www.facebook.com/business/help/1016122818401732/?ref=u2u){target="_blank"}頁面。

使用[!DNL Facebook Ads]啟用自動標籤之前，必須將先前的效能記錄匯出為CSV。 此時，當[!DNL Marketo Measure]使用其_bf引數標籤[!DNL Facebook Ads]時，[!DNL Facebook]會將廣告讀取為全新並清除效能記錄。 因此，如果對您和您的組織有價值，匯出先前績效的記錄很重要。

請注意，您可以隨時將[!DNL Facebook]帳戶連線至[!DNL Marketo Measure]應用程式，不會遺失任何資料 — 唯有啟用自動標籤時，才會清除效能歷程記錄。

如需匯出[!DNL Facebook]廣告報告的詳細資訊，請參閱Facebook的[本文章](https://www.facebook.com/business/help/393890194130036){target="_blank"}。

## linkedIn贊助內容 {#linkedin-sponsored-content}

linkedIn整合可讓[!DNL Marketo Measure]在[!DNL LinkedIn]贊助的內容上標籤目的地URL，這最終可讓[!DNL Marketo Measure]追蹤使用者整個接觸點歷程，並將活動對應回特定的[!DNL LinkedIn]行銷活動和創意。 這可提供客戶[!DNL LinkedIn]活動投資報酬率的深入分析。 [!DNL Marketo Measure]將搜尋具有唯一[!DNL LinkedIn]共用的創意內容，並在結尾新增`?_bl={creativeId}`引數。

由於[!DNL LinkedIn]共用可用於多個行銷活動和創作，因此我們要求客戶不要複製/複製/複製現有創作，以便維持其唯一性。 如果找到「共用」且偵測到它只用於一個Creative，[!DNL Marketo Measure]可以將「共用」標示為原樣，而不需要重新建立任何Creative或Shares，並且所有廣告歷史記錄（曝光數、點按數、共用）都將保留。

一旦發現共用可跨多個創意內容共用，[!DNL Marketo Measure]就必須執行暫停、複製和重新標籤的程式，才能建立唯一集合。 [!DNL Marketo Measure]將暫停並封存即時創意內容，這表示也會封存包含曝光、點按和社交分享的創意內容。

## 非整合平台 {#non-integrated-platforms}

對於未與[!DNL Marketo Measure]整合的平台，無法使用[!DNL Marketo Measure]自動標籤功能。 需要手動新增引數。
