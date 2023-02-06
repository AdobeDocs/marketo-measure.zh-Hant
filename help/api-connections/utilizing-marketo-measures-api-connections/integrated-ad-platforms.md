---
unique-page-id: 18874594
description: 整合廣告平台 —  [!DNL Marketo Measure]  — 產品檔案
title: 整合廣告平台
exl-id: df30ee8a-8b07-4f14-94e8-cc482fca8b18
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '1696'
ht-degree: 0%

---

# 整合廣告平台 {#integrated-ad-platforms}

[!DNL Marketo Measure] 具有與Google AdWords、Microsoft BingAds、 [!DNL Facebook] 廣告和DoubleClick促銷活動管理員。 透過這些API連線， [!DNL Marketo Measure] 可輕鬆提取資料，並連同外部購買者應用程式推送至您的CRM。 無需手動上傳成本或資料。 相反，您的帳戶只需連線並授權至 [!DNL Marketo Measure] 應用程式。 [!DNL Marketo Measure] 然後會自動從平台下載行銷成本，並將其載入至 [!DNL Marketo Measure] 應用程式。 如果您選取為AdWords、BingAds或 [!DNL Facebook] 廣告， [!DNL Marketo Measure] 會自動將其參數附加至廣告的URL。

## 如何連接廣告平台 {#how-to-connect-ad-platforms}

在了解每個平台的具體資訊之前，我們會先討論如何將任何這些帳戶連結至 [!DNL Marketo Measure]. 首先登入 [!DNL Marketo Measure] 應用程式，並導覽至 **[!UICONTROL Settings]** 選項 **[!UICONTROL My Account]** 標籤。 下一步，選擇 **[!UICONTROL Connections]** 在 **[!UICONTROL Integrations]** 區段。

如下圖所示，您會看到設定新廣告連線的按鈕。

![](assets/2.png)

在您按一下 [!UICONTROL Set up New Ads Connection] 按鈕，視窗（如下所示）將隨四個廣告彈出 [!UICONTROL connect]離子類型。 按一下「連接」，將出現另一個窗口，詢問憑據。 輸入憑據，然後按一下 [!UICONTROL authorize] 將帳戶連接到 [!DNL Marketo Measure].

![](assets/select-account-type.png)

## Google AdWords {#google-adwords}

當您在 [!DNL Google AdWords]，建議您透過三種方式之一來標籤促銷活動：手動標籤、自動標籤或建立追蹤範本。 手動標籤AdWords URL有賴於您定義並在廣告URL的結尾新增參數。 手動標籤可讓任何非Google平台輕鬆讀取參數所收集的資料。

「追蹤範本」是Google提供的工具，可新增其所呼叫的ValueTrack參數。 它們的運作方式與UTM和其他標籤參數相同。

## 啟用自動標籤時會發生什麼事 {#what-happens-when-auto-tagging-is-enabled}

[!DNL Marketo Measure] 在您的 [!DNL AdWords] 帳戶：

* *選項A*:找到追蹤範本。 [!DNL Marketo Measure] 將其參數新增至範本。
* *選項B*:找到第三方重新導向。 若在追蹤範本中找到第三方重新導向， [!DNL Marketo Measure] 無法採取任何操作。 您需要手動新增 [!DNL Marketo Measure] 標籤。 第三方重新導向的範例是像Kenshoo或Marin這樣的競標管理工具。 深入了解 [競標管理工具 [!DNL Marketo Measure]](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md){target="_blank"}.

* *選項C*:找不到追蹤範本。 [!DNL Marketo Measure] 會掃描 [!DNL Marketo Measure] 參數。 根據掃描，如果：
   * 找到參數：設定完成！
   * 找不到參數： [!DNL Marketo Measure] 會將其參數附加至廣告目的地URL的結尾。 [!DNL Marketo Measure] 在建立新廣告後的兩小時內附加新廣告。 請記住，參數不會新增至範本。

深入了解我們的 [[!DNL AdWords] 自動標籤功能](/help/api-connections/utilizing-marketo-measures-api-connections/understanding-marketo-measure-adwords-tagging.md){target="_blank"}.

## 如何啟用 [!DNL Marketo Measure] Adwords的自動標籤 {#how-to-enable-marketo-measure-auto-tagging-for-adwords}

啟用前 [!DNL Marketo Measure] 自動標籤， **請確定您已在Adwords帳戶的「帳戶」、「促銷活動」或「廣告群組」層級啟用追蹤範本。 這是任何將擁有 [!DNL Marketo Measure] 啟用自動標籤。** 啟用追蹤範本可防止廣告效能歷史記錄資料中的任何遺失。 請注意，在關鍵字、網站連結或廣告層級啟用追蹤範本，會導致廣告經過審核和核准程式，並可能會重新啟動廣告的效能記錄。 如果完全未啟用追蹤範本， [!DNL Marketo Measure] 會附加 [!DNL Marketo Measure] 直接追蹤參數至廣告的「最終URL」，這也可能導致廣告歷史資料遺失。

在您具備追蹤範本後，請依照下列指示啟用 [!DNL Marketo Measure] 自動標籤。 注意： [!DNL Marketo Measure] 也會在您的帳戶中自動標籤任何暫停的廣告。

1. 登入 [!DNL Marketo Measure] 帳戶 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}.

1. 前往 [!UICONTROL My Account] > [!UICONTROL Settings] > [!UICONTROL Integrations] > [!UICONTROL Connections].

   ![](assets/4.png)

1. 按一下Adwords帳戶旁的鉛筆圖示，該帳戶會 [!DNL Marketo Measure] 啟用自動標籤。

   ![](assets/5.png)

1. 在右上角，切換 **[!UICONTROL Autotagging]** 切換至 **[!UICONTROL Yes]**. 在頁面底部，按一下 **[!UICONTROL Learn More]** 展開文本框，然後按一下 **[!UICONTROL Save]**. 自動標籤設定已完成。

   ![](assets/6.png)

## 如何在AdWords中設定追蹤範本，使用 [!DNL Marketo Measure] 參數 {#how-to-set-up-a-tracking-template-in-adwords-with-marketo-measure-parameters}

請記住，您應在 [!UICONTROL Account], [!UICONTROL Campaign] 或AdWords中的廣告群組層級。 如果您將追蹤範本新增至關鍵字、網站連結或廣告層級，您的廣告將需要經過審核和核准程式，而您可能會重新啟動廣告的效能記錄。 深入了解 [建立追蹤範本](https://support.google.com/adwords/answer/6076199?hl=en#tracking){target="_blank"}.

1. 登入您的 [!DNL Google AdWords] 帳戶。
1. 前往 [!UICONTROL Campaigns] 從左側導覽列檢視
1. 導覽至「[!UICONTROL Settings]」，也位於左側導覽列中
1. 切換至「[!UICONTROL Account Settings]&quot;從頂部查看
1. 展開「[!UICONTROL Tracking]&quot;部分
1. 在追蹤範本中貼上下列其中一個文字字串，以設定範本的值：

   * 如果所有URL中都有問號，請使用下列URL文字：

   `{lpurl}&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

   * 如果您的任何URL上沒有問號，請新增下列URL文字：

   `{lpurl}?_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}*`

   為避免在手動標籤URL時發生錯誤，通常建議自動產生UTM參數。 這不一定表示使用AdWords或 [!DNL Marketo Measure] 參數，有多種工具可根據您提供的資訊自動產生URL的參數，以簡化程式。

   >[!TIP]
   >
   >如果您收到指出追蹤範本無效的錯誤，請嘗試清除瀏覽器快取並再次嘗試，這通常能解決問題。

## 如何自動為 [!DNL Google AdWords] {#how-to-automatically-generate-utm-tags-for-google-adwords}

UTM標籤一開始可能很難建立，但有許多工具可用來使用UTM參數輕鬆建立URL。 您可以使用下列任一資源，或在網頁上搜尋更多工具。 請記住 [!DNL Marketo Measure] 不會認可或保證這些平台和工具提供任何功能。

**[!DNL Google URL]建立器**

Google URL Builder是標準工具，可用來建置帶有UTM標籤的格式正確的URL。 只需輸入URL和每個參數所需的值，然後按一下「[!UICONTROL Generate URL]」。 如果您只有少數幾個要標籤的URL，這是理想的工具。 存取工具 [此處](https://support.google.com/analytics/answer/1033867?hl=en){target="_blank"}.

**Google EpikOne生成的電子錶格**

此試算表有一個公式，可自動產生已標籤的目的地URL。 如果需要標籤大量連結，這是絕佳的工具。 存取試算表 [此處](https://spreadsheets.google.com/ccc?key=p7c_HKcmspSUfEYSO0gskKw&amp;hl=en){target="_blank"}.

**Rafflecopter連結標籤工具**

由Rafflecopter建立的試算表是經修改的 [!DNL EpikOne's] 試算表。 它還包含一個公式，該公式將自動生成標籤目標連結供您使用。

這些工具都提供如何使用和修改以符合您需求的詳細說明。 工具可供使用 [此處](https://docs.google.com/spreadsheets/d/1QCIr1WUJQHE68cA4VTks2XE7nxuryaUymCEy_23-Oew/edit#gid=0){target="_blank"}.

**Effin Amazin UTM Builder**

此工具是Chrome擴充功能，可讓您快速產生UTM標籤。 找到它 [此處](https://chrome.google.com/webstore/detail/effin-amazing-utm-builder/eoaapiimcaimddnfhfnifgkinmpcbccp?hl=en){target="_blank"}.

## Bing Ads {#bing-ads}

Bing Ads是整合平台，可讓您為URL啟用自動標籤，或使用協力廠商工具，例如 [!DNL Marketo Measure]，以標籤廣告。 [!DNL Bing Ads] 也依賴UTM參數。

Bing Ads的自動標籤功能新增了下列UTM參數：

* Utm_source
* Utm_medium
* Utm_term

Bing Ads的自動標籤也新增下列自訂參數：

`_bt={adid}`

字串看起來會像這樣：

`{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`

請務必注意 [!DNL Bing Ads] 可讓您在最終URL中使用其自訂標籤，以取得更精細的粒度（如果您想要的話），以新增更多參數。

如有需要，可以使用追蹤範本，但不需要 [!DNL Bing Ads] 和 [!DNL Marketo Measure] 整合。 這是因為 [!DNL Bing] 可在不變更歷史記錄的情況下編輯廣告，因此 [!DNL Marketo Measure] 能夠更新目標URL。

自動標籤應透過 [!DNL Marketo Measure] 這樣， [!DNL Marketo Measure] 參數可自動附加。 不會遺失Bing Ads過去廣告績效記錄的風險。

造訪 [[!DNL Bing Ads]](https://advertise.bingads.microsoft.com/en-us/blog/post/august-2016/upgraded-urls-now-available-in-bing-ads-an-easier-way-to-manage-your-tracking-urls){target="_blank"} 網站，以取得在其平台上新增標籤的詳細資訊。

## Facebook Ads {#facebook-ads}

此 [!DNL Marketo Measure] 整合 [!DNL Facebook] 可讓其自動下載廣告資訊，並使用其參數標籤URL。 [!DNL Marketo Measure] 會透過自動標籤來提取促銷活動和廣告集資訊。 廣告集會填入廣告群組名稱欄位。 如需在 [!DNL Facebook] 平台，請造訪 [!DNL Facebook] [業務](https://www.facebook.com/business/help/1016122818401732/?ref=u2u){target="_blank"} 頁面。

在啟用自動標籤之前，請使用 [!DNL Facebook Ads]，請務必將先前的效能歷史記錄匯出為CSV。 此時，當 [!DNL Marketo Measure] 標籤 [!DNL Facebook Ads] 帶有_bf參數， [!DNL Facebook] 將廣告讀為全新內容，並刪除效能記錄。 因此，如果先前績效的記錄對您和您的組織有價值，請務必匯出該記錄。

請注意，您可以連接 [!DNL Facebook] 帳戶 [!DNL Marketo Measure] 應用程式且不會遺失任何資料，只有啟用自動標籤時，效能歷史記錄才會遭到清除。

[請參閱這篇文章](https://www.facebook.com/business/help/393890194130036){target="_blank"} 從Facebook取得有關匯出的詳細資訊 [!DNL Facebook] 廣告報表。

## linkedIn贊助內容 {#linkedin-sponsored-content}

LinkedIn整合可讓 [!DNL Marketo Measure] 標籤目標URL [!DNL LinkedIn] 贊助內容，最終允許 [!DNL Marketo Measure] 追蹤使用者完成其整個接觸點歷程，並將活動對應回特定 [!DNL LinkedIn] 行銷活動與創意。 這可為客戶提供其投資報酬率的深入分析 [!DNL LinkedIn] 活動。 [!DNL Marketo Measure] 將搜尋具有唯一 [!DNL LinkedIn] 共用和新增 `?_bl={creativeId}` 參數到結尾。

因為 [!DNL LinkedIn] 共用可用於多個促銷活動和創作元素，我們要求客戶不要複製/複製/複製現有創作元素，以保持其獨特性。 如果找到共用，且偵測到該共用僅用於一個創作， [!DNL Marketo Measure] 可以原樣標籤「共用」，而無須重新建立任何創作或分享，且所有廣告歷史記錄（曝光數、點按、分享）將會保留。

一旦發現多個創作元素之間共用共用， [!DNL Marketo Measure] 必須執行暫停、複製和重新標籤的程式，才能建立唯一集。 [!DNL Marketo Measure] 會暫停並封存即時創意素材，這表示包含曝光數、點按和社交分享的創意素材也會封存。

## 非整合平台 {#non-integrated-platforms}

針對未與整合的平台 [!DNL Marketo Measure], [!DNL Marketo Measure] 無法使用自動標籤功能。 需要手動新增參數。
