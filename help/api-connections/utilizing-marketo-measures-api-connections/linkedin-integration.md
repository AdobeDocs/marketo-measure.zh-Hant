---
unique-page-id: 35586080
description: linkedIn整合 —  [!DNL Marketo Measure]  — 產品檔案
title: linkedIn整合
exl-id: 705209ef-1ece-496c-ac2f-6a31055bd993
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '2594'
ht-degree: 0%

---

# linkedIn整合 {#linkedin-integration}

## 總覽 {#overview}

此 [!DNL Marketo Measure] 與LinkedIn的整合分為兩部分：

贊助內容：贊助內容整合可讓 [!DNL Marketo Measure] 標籤目標URL [!DNL LinkedIn] 最終允許 [!DNL Marketo Measure] 追蹤使用者完成其整個接觸點歷程，並將活動對應回特定 [!DNL LinkedIn] 行銷活動與創意。 這可為客戶提供其投資報酬率的深入分析 [!DNL LinkedIn] 活動。

第一代Forms:透過與LinkedIn的Lead Gen Forms整合，Marketo Measure可深入分析透過LinkedIn平台提交的表單。 這些表單填入會與來自您CRM或 [!DNL Marketo Engage] 例項，以便符合歸因的資格。 透過有助於產生表單的Campaign、Creative和Form的深入分析，團隊現在可以進一步最佳化其LinkedIn行銷和廣告支出。

## 可用性 {#availability}

可供所有客戶使用。

## 需求 {#requirements}

**促銷活動管理員角色**

針對 [!DNL Marketo Measure] 若要下載廣告資料和廣告成本資料，您必須在Campaign Manager中擁有下列其中一個角色：

* 帳單管理員
* 客戶經理
* 行銷活動管理員

更多詳情： [行銷活動管理員中的使用者角色和功能](https://www.linkedin.com/help/lms/answer/a425731/user-roles-and-functions-in-campaign-manager).

**付費媒體管理員角色**

針對 [!DNL Marketo Measure] 若要建立/更新贊助創意素材，您必須有下列其中一個付費媒體管理員角色：

* 贊助內容海報
* 首席Forms經理

更多詳情： [linkedIn頁面管理員角色](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview).

還有其他 [!DNL LinkedIn] 我們所做的角色 **not** 需要進行整合。 這些角色通常被誤認為是必要的角色，因此請注意，這是有區別的！

**頁面管理員角色**

針對 [!DNL Marketo Measure] 若要從銷售機會一般表單下載/整合銷售機會，您必須具備下列頁面管理員角色：

* 超級管理員

更多詳情： [linkedIn頁面管理員角色](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview).

## linkedIn廣告類型 {#linkedin-ad-types}

[!DNL Marketo Measure] 將支援：

**贊助內容：** 贊助內容可讓您將內容傳送至 [!DNL LinkedIn] 除了那些關注您公司的人之外的成員資訊。 贊助內容可以定位在特定對象，並可協助廣告商觸及 [!DNL LinkedIn] 會員無論身在何處、何時都參與 [!DNL LinkedIn] 平台（案頭、行動裝置和平板電腦）。 支援具有Lead Gen Forms的贊助內容。

所支援的贊助內容廣告格式類型 [!DNL Marketo Measure] 是單一影像廣告和視訊廣告(透過Lead Gen Forms)。 由於結構的複雜性，我們不支援轉盤廣告。

[!DNL Marketo Measure] 不支援贊助訊息、文字廣告或動態廣告。

![](assets/one.png)

>[!TIP]
>
>對於來自非贊助內容來源的任何促銷活動/支出（例如「文字廣告」或「贊助郵件」的促銷活動類型）, [!DNL Marketo Measure] does _not_ 即支援這些促銷活動類型的追蹤。 如果您想追蹤促銷活動的「支出」（例如「贊助內容」支出），請務必使用我們的「行銷支出」CSV，以手動記錄「支出」。

## 運作方式：贊助內容 {#how-it-works-sponsored-content}

>[!NOTE]
>
>首次使用前，必須導覽至 [!DNL Marketo Measure] [!UICONTROL Settings] > [!UICONTROL Integrations] > [!UICONTROL Ads] > [!UICONTROL Enable LinkedIn Lead Gen Forms].

**[!DNL LinkedIn's]獨特的自動標籤需求**

[!DNL Marketo Measure] 可協助您追蹤 [!DNL LinkedIn] 透過自動標籤登錄頁面來提升行銷活動績效。

[!DNL Marketo Measure] 將搜尋具有不重複LinkedIn共用的創作，並新增 `?_bl={creativeId}` 參數到結尾。

**複製共用**

用這個 [!DNL Marketo Measure/LinkedIn] 整合後，我們要求客戶不要複製/複製/複製現有創作元素。 如果找到共用，且偵測到該共用僅用於一個創作， [!DNL Marketo Measure] 可以原樣標籤「共用」，而無須重新建立任何創作或分享，且所有廣告歷史記錄（曝光數、點按、分享）將會保留。

一旦發現多個創作元素之間共用共用， [!DNL Marketo Measure] 必須執行暫停、複製和重新標籤的程式，才能建立唯一集。 [!DNL Marketo Measure] 會暫停並封存即時創作素材，因此會清除廣告歷史記錄，包括曝光數、點按和社交分享，以便正確地自動標籤所有內容。

今後， [!DNL Marketo Measure] 建議您不要複製任何 [!DNL LinkedIn] 分享並盡可能保留所有創意和分享的獨特性，這樣我們就可以直接新增追蹤，而無須清除廣告記錄。

**縮短的URL**

額外步驟的原因是LinkedIn允許目標URL是縮短的URL（bit.ly、goog.le等），這表示 [!DNL Marketo Measure] 看不到長且已解析的URL，而 [!DNL Marketo Measure] 需要將追蹤參數新增至解析的URL。 為了解決這個問題， [!DNL Marketo Measure] 在重新建立廣告前尋找縮短的URL，展開URL，然後使用解析的URL及其所有參數建立新廣告，允許 [!DNL Marketo Measure] 來新增標籤。 建立新廣告會清除廣告歷史記錄（曝光數、點按、分享），因此需要標籤縮短URL的權限。

如果您大量使用縮短的URL，這可能會嚴重影響您的創意素材。 建議您不再使用縮短的URL，這樣 [!DNL Marketo Measure] 可以標籤登錄頁面，而無須建立新廣告並清除廣告歷史記錄。

**程式**

先舉幾個例子。 假設我們…….

創意A :共用123\
創作B :共234股\
創作C :共234股\
創作D :共234股

![](assets/two.png)

`1)` [!DNL Marketo Measure] 會先查看狀態為「作用中」的所有促銷活動、創作和分享。 [!DNL Marketo Measure] 不會標籤暫停、封存或取消的廣告。 如果廣告暫停，則設為 [!UICONTROL active]，當它再次作用中時，我們會加上標籤。 如果我們可以找到獨特的共用，表示它不會用於多個創意素材或促銷活動（例如創意A）:股份123), [!DNL Marketo Measure] 會新增自訂參數 `>> ?_bl={creativeId}` 到共用URL。

`2)` 現在，如果共用且失去其獨特性(例如Creative B :Share 234和Creative C :Share 234和Creative D :共234股), [!DNL Marketo Measure] 會暫停並封存所有類似的創意素材（包括創意B、創意C和創意D）。

`3)` [!DNL Marketo Measure] 將建立3個新創意素材，即Creative E、Creative F和Creative G，以複製已封存的Creative B內容。

`4)` [!DNL Marketo Measure] 還將建立3個新股份，即Share 345、Share 456和Share 567，這些股份將複製Share 234的內容，但它將有其自己的獨特 `?_bl` 標籤。

`5)` [!DNL Marketo Measure] 必須定期檢查共用是否未共用，如果共用，我們將在上述步驟2重新啟動程式。

>[!NOTE]
>
>實作這項目表示我們的客戶將會遺失創意B的廣告記錄：Share 234, Creative C :Share 234和Creative D :共用234，因為現在這是透過Creative E重新建立：345股、F股：Share 456和Creative G :分別持有567股。

![](assets/three.png)

## 運作方式：引領時代Forms {#how-it-works-lead-gen-forms}

**程式**

通過 [!DNL LinkedIn's] 廣告表單API和廣告表單回應API，我們可以收集廣告帳戶的表單提交資料，並將電子郵件地址與來自CRM或Marketo的銷售機會建立關聯。

linkedIn表單可包含多個電子郵件地址。 下載表單回應時，我們會尋找優先順序如下的電子郵件地址：使用有效的電子郵件值處理電子郵件、電子郵件地址（主要表單欄位）或自訂欄位。

無論促銷活動或創作狀態為何，所有表單回應都會產生接觸點。 [!DNL Marketo Measure] 有90天回顧限制，因此 [!DNL Marketo Measure] 無法存取超過90天的表單回應，但 [!DNL Marketo Measure] 和 [!DNL LinkedIn] 整合已啟用，透過 [!DNL Marketo Measure].

>[!NOTE]
>
>linkedIn成本仍會下載為贊助內容促銷活動的一部分。

**在CRM或Marketo中追蹤銷售機會Forms**

在 [!DNL Marketo Measure] 而LinkedIn Lead Gen Forms整合已存在，客戶推送其表單提交至Marketo計畫和/或CRM促銷活動以追蹤表單並接收這些活動的歸因是常見的作法。 啟用Lead Gen Forms設定後，我們要確定這些表單提交不會重複計算。 請檢查以下內容：

* CRM物件上的「啟用購買者接觸點」欄位設為「無」或「排除所有促銷活動成員」
* 更新任何相關的Marketo計畫或Marketo活動規則
* 更新任何相關的CRM促銷活動規則

>[!NOTE]
>
>LinkedIn API有90天回顧限制，因此若您使用Marketo或CRM規則，建議您將規則的結束日期設為啟用整合之日的前90天 [!DNL Marketo Measure].

## 接觸點詳細資訊 {#touchpoint-details}

一次 [!DNL Marketo Measure] 已成功標籤LinkedIn創意內容上的登錄頁面，您就可以在接觸點上檢視已解析的廣告資料。 以下是您應該看到的資料值對應：

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th>接觸點欄位</th> 
   <th>範例值</th> 
  </tr> 
  <tr> 
   <td><p>廣告Id </p></td> 
   <td><p>84186224 </p></td> 
  </tr> 
  <tr> 
   <td><p>廣告內容 </p></td> 
   <td><p>95%的行銷人員認為需求建立#B2B略是成功的。 更多詳情： [!DNL https]://lnkd.in/jgdi50vKrgv</p></td> 
  </tr> 
  <tr> 
   <td><p>廣告群組Id </p></td> 
   <td><p>(空白) </p></td> 
  </tr> 
  <tr> 
   <td><p>廣告群組名稱 </p></td> 
   <td><p>(空白) </p></td> 
  </tr> 
  <tr> 
   <td><p>廣告促銷活動Id </p></td> 
   <td><p>138949954 </p></td> 
  </tr> 
  <tr> 
   <td><p>廣告促銷活動名稱 </p></td> 
   <td><p>SU - COM帳戶 — 需求技能 </p></td> 
  </tr> 
  <tr> 
   <td><p>廣告目標URL </p></td> 
   <td><p>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders?_bl=84186217 </p></td> 
  </tr> 
  <tr> 
   <td><p>表單URL </p></td> 
   <td><p>info.bizible.com/demo </p></td> 
  </tr> 
  <tr> 
   <td><p>表單URL — 原始 </p></td> 
   <td><p>info.bizible.com/demo </p></td> 
  </tr> 
  <tr> 
   <td><p>關鍵字Id </p></td> 
   <td><p>(空白) </p></td> 
  </tr> 
  <tr> 
   <td><p>關鍵字匹配類型 </p></td> 
   <td><p>(空白) </p></td> 
  </tr> 
  <tr> 
   <td><p>登陸頁面 </p></td> 
   <td><p>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders </p></td> 
  </tr> 
  <tr> 
   <td><p>登陸頁面 — 原始 </p></td> 
   <td><p>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders?_bl=84186217 </p></td> 
  </tr> 
  <tr> 
   <td><p>行銷管道 </p></td> 
   <td><p>付費社交 </p></td> 
  </tr> 
  <tr> 
   <td><p>行銷管道 — 路徑 </p></td> 
   <td><p>付費Social.LinkedIn </p></td> 
  </tr> 
  <tr> 
   <td><p>中 </p></td> 
   <td><p>"cpc"或"Lead Gen Form"</p></td> 
  </tr> 
  <tr> 
   <td><p>反向連結頁面 </p></td> 
   <td><p>www.linkedin.com/ </p></td> 
  </tr> 
  <tr> 
   <td><p>反向連結頁面 — 原始 </p></td> 
   <td><p>www.linkedin.com/ </p></td> 
  </tr> 
  <tr> 
   <td><p>塞拉赫片語 </p></td> 
   <td><p>(空白) </p></td> 
  </tr> 
  <tr> 
   <td><p>接觸點類型 </p></td> 
   <td><p>網路表單 </p></td> 
  </tr> 
  <tr> 
   <td><p>接觸點來源 </p></td> 
   <td><p>LinkedIn </p></td> 
  </tr> 
 </tbody> 
</table>

## 成本 {#costs}

因為 [!DNL Marketo Measure] 與 [!DNL LinkedIn]，我們會每天下載每次行銷活動和創意內容的錄制支出。 客戶無需報告 [!DNL LinkedIn] 在 [!DNL Marketo Measure] 應用程式。

如同其他廣告整合， [!DNL Marketo Measure] 已定義行銷管道規則，以放置 [!DNL LinkedIn] 行銷活動、創意和成本。 若要使用規則，客戶會想為其付費插入新列 [!DNL LinkedIn] 努力。 可以是新管道或現有管道。 在反向連結欄中，使用定義&quot;[[!DNL LinkedIn] 已付]」 [!DNL Marketo Measure] 定義為具有 [!DNL Marketo Measure] 標籤。

![](assets/four.png)

## [!DNL Marketo Measure] Discover {#marketo-measure-discover}

已對 [!DNL Marketo Measure] Discover以支援Lead Gen Forms報表。

**付費媒體展示板**

Lead Gen Forms磁貼：包含LinkedIn表單填入計數的新圖磚。 穿透鑽取此計數會顯示活動ID、表單日期、表單名稱和電子郵件地址。

**參與路徑板**

事件歷程：包含整合後所提供表單的「活動」事件類型和中等「銷售機會一般表單」。 穿透鑽取視圖包括促銷活動、創作和表單詳細資訊。

## 贊助內容常見問題集 {#sponsored-content-faq}

**什麼是暗共用？**

「隱藏共用」是貼文，從未張貼在公司頁面上，且會立即建立，並直接新增為創意內容。 所以 [!DNL Marketo Measure] — 建立的創作元素不會出現在公司的頁面頂端並再次獲得促銷，因此會使用深色共用，以便在幕後啟動。

**狀態的作用 [!DNL Marketo Measure] 標籤？**

a上有四種不同的狀態 [!DNL LinkedIn] 行銷活動與創意：活動、暫停、封存和取消。 我們只會標籤作用中的促銷活動和創作。 標籤其他狀態後，系統會將其重新設為「作用中」。 [!DNL Marketo Measure] 不會標籤「已暫停」、「已封存」或「已取消」促銷活動或創作，但如果狀態變更為「作用中」，則會繼續標籤。

**這有什麼價值 [!DNL Marketo Measure] 用於標籤嗎？**

目的地URL的結尾處， [!DNL Marketo Measure] 是新增參數 `&_bl={creativeId}`，其中 `{creativeId}` 是來自LinkedIn的創作ID。 有了創意ID, [!DNL Marketo Measure] 也可以判斷促銷活動ID，因為 [!DNL LinkedIn] 具有相當基本的廣告結構，因為每個創意內容只能屬於一個促銷活動。

**我以前的創意會怎麼樣 [!DNL Marketo Measure] 會建立新版本嗎？**

當 [!DNL Marketo Measure] 重新建立「共用」並將其置於新的「創意」中，舊的「創意」就會被封存。 這也是為什麼 [!DNL Marketo Measure] 不會標籤已封存的促銷活動或創作，否則會與 [!DNL Marketo Measure] 正在嘗試無限期地標籤它。

**為何建立的廣告目的地URL不符合我的原始廣告？**

[!DNL Marketo Measure] 需要將追蹤參數新增至解析的URL，但API中顯示的URL可能是短URL，不會顯示所有參數。 為了解決這個問題， [!DNL Marketo Measure] 在重新建立新增前，先尋找縮短的URL，將其解析，然後使用解析的URL及其所有參數建立新廣告，以允許 [!DNL Marketo Measure] 來新增標籤。

**你在標籤我所有的廣告嗎？ 我沒有在所有登陸頁面上看見bl參數？**

我們觀察到有些行銷人員會將影像連結放入目的地URL, [!DNL Marketo Measure] 無法標籤，因此我們會在廣告內容中搜尋URL。 若 [!DNL Marketo Measure] 有標籤縮短URL的權限，我們會擴增該URL和標籤，但由於LinkedIn的複製結構，該URL和標籤會自動縮短。 標籤會顯示在LinkedIn縮短的URL中，而會顯示在接觸點的「廣告內容」欄位中，而非「登陸頁面 — 原始」欄位中。

**哦，不，我隊裡有人不小心克隆了一個共用。 我可以暫停一下嗎？**

沒關係。 [!DNL Marketo Measure] 會以程式設計方式檢查是否有已不再唯一的分享，這表示該分享已複製至不同的創意內容。 一旦檢測到該副本， [!DNL Marketo Measure] 會遵循通常的流程來標籤及建立新廣告。

**我的廣告以前正在等待審核。 為什麼它在之後重新等待審核 [!DNL Marketo Measure] 標籤了？**

linkedIn要求所有已建立或修改的廣告在張貼之前，都須先經過一般的安全程式。 [!DNL Marketo Measure] 會嘗試盡快截斷廣告，因為廣告每6小時掃描一次新廣告，但使用 [!DNL LinkedIn's] 額外步驟，則可能會將啟動延遲數小時。

**我的廣告上有2個URL。 哪個被標籤了？**

都有。 此 [!DNL Marketo Measure] 整合功能可讓我們從廣告中的點進影像標籤目標URL，但也會自動更新廣告說明中縮短的URL。

![](assets/five.png)

**我已連接 [!DNL LinkedIn ads] 帳戶。 為什麼不 [!DNL Marketo Measure] 標籤我的連結嗎？**

已連接 [!DNL LinkedIn] 使用者需要有適當的編輯存取權，這表示使用者必須是帳戶管理員、促銷活動管理員或創意經理。

**如何知道我的創作是否會複製？ 我可以看看我的創意人員是否使用相同分享？**

共用ID未提供於 [!DNL LinkedIn] 報表，因此沒有明確且明確的方式可檢查創意到共用對應。 如果您懷疑創意內容可能是副本，您可以從 [!DNL LinkedIn] 行銷活動管理員 — 這會在新標籤中開啟廣告，您會在URL中找到共用ID。

![](assets/six.png)

## 主導一代Forms常見問題集 {#lead-gen-forms-faq}

**此增強的成本為何？**

此優惠方案包含在任何付費項目中 [!DNL Marketo Measure] 訂閱。

**整合是否可回溯？**

是的，我們將從LinkedIn下載歷史廣告表單回應，不過僅限90天回顧期間。 越長 [!DNL Marketo Measure] 且已啟用LinkedIn整合，透過 [!DNL Marketo Measure].

沒有選項可設定要下載的特定日期，但如果有需要隱藏的接觸點，您可以選擇設定「接觸點刪除」規則。

**如果我已使用 [!DNL Marketo Measure] linkedIn廣告整合？**

不會，我們不會為所有客戶自動開始下載，但在設定中啟用此功能是一個非常簡單的開關。

**表單資料可用嗎？**

表單資料可透過 [!DNL Marketo Measure] 包括表單ID和表單名稱的探索。 CRM中的接觸點物件尚未提供表單詳細資料。

**任何 [!DNL LinkedIn] 先前已同步至Marketo方案或CRM促銷活動的銷售機會？**

建議您調整 [!DNL Marketo Measure] 規則，從這些特定方案或促銷活動產生接觸點以避免重複。 LinkedIn API有90天回顧限制，因此若您使用Marketo或CRM規則，建議您將規則的結束日期設為啟用整合之日的前90天 [!DNL Marketo Measure]. 從現在開始， [!DNL Marketo Measure] 可以下載這些銷售機會，以提供更深入的分析和詳細資訊。

**是否涉及任何自動標籤或追蹤？**

不，這和其他 [!DNL Marketo Measure] 整合。 我們不會修改登錄頁面（因為沒有點進登錄頁面），而只會從LinkedIn下載相關資訊，並將它們視為內的活動 [!DNL Marketo Measure].
