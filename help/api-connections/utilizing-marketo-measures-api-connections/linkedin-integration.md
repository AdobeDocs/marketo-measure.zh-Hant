---
unique-page-id: 35586080
description: linkedIn整合 —  [!DNL Marketo Measure]  — 產品檔案
title: linkedIn整合
exl-id: 705209ef-1ece-496c-ac2f-6a31055bd993
feature: APIs, Integration
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '2594'
ht-degree: 0%

---

# linkedIn整合 {#linkedin-integration}

## 概觀 {#overview}

此 [!DNL Marketo Measure] 與LinkedIn的整合分為兩個部分：

贊助內容：贊助內容整合可讓 [!DNL Marketo Measure] 標籤目的地URL [!DNL LinkedIn] 廣告，最終允許 [!DNL Marketo Measure] 追蹤使用者整個接觸點歷程，並將活動對應回特定 [!DNL LinkedIn] 行銷活動和創意。 這可提供客戶對其投資報酬率的深入分析 [!DNL LinkedIn] 活動。

Lead Gen Forms：透過與LinkedIn的Lead Gen Forms整合，Marketo Measure可深入瞭解透過LinkedIn平台提交的表單。 這些表單填寫會比對來自您CRM或 [!DNL Marketo Engage] 執行個體，因此他們符合歸因資格。 透過對有助於產生表單的行銷活動、創意和表單的深入分析，團隊現在可以進一步最佳化其LinkedIn行銷和廣告支出。

## 可用性 {#availability}

可供所有客戶使用。

## 需求 {#requirements}

**行銷活動經理角色**

的 [!DNL Marketo Measure] 若要能夠下載Ads資料和廣告成本資料，您必須在「行銷活動管理員」中擔任下列角色之一：

* 帳單管理員
* 客戶經理
* 行銷活動管理員

瞭解更多： [Campaign Manager中的使用者角色和功能](https://www.linkedin.com/help/lms/answer/a425731/user-roles-and-functions-in-campaign-manager).

**付費媒體管理員角色**

的 [!DNL Marketo Measure] 若要能夠建立/更新贊助的創作專案，您必須具備下列其中一個付費媒體管理員角色：

* 贊助內容海報
* Forms銷售機會經理

瞭解更多： [linkedIn頁面管理員角色](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview).

還有其他的 [!DNL LinkedIn] 我們執行的角色 **非** 需要我們的整合。 這些角色經常被誤認為必要的角色，因此請注意它們之間有所差異！

**頁面管理員角色**

的 [!DNL Marketo Measure] 若要能夠從lead gen forms下載/整合銷售機會，您必須具備以下頁面管理員角色：

* 超級管理員

瞭解更多： [linkedIn頁面管理員角色](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview).

## linkedIn廣告型別 {#linkedin-ad-types}

[!DNL Marketo Measure] 將支援：

**贊助內容：** 贊助內容可讓您將內容傳送至 [!DNL LinkedIn] 除了追蹤您公司的人以外的成員摘要。 贊助內容可以定位至特定對象，並幫助廣告商觸及特定對象 [!DNL LinkedIn] 成員無論何時何地參與 [!DNL LinkedIn] 跨案頭、行動裝置和平板電腦的平台。 支援Lead Gen Forms的贊助內容。

支援的贊助內容廣告格式型別 [!DNL Marketo Measure] 是單一影像廣告和影片廣告(透過Lead Gen Forms)。 由於結構描述的複雜性，我們不支援轉盤廣告。

[!DNL Marketo Measure] 不支援贊助訊息、文字廣告或動態廣告。

![](assets/one.png)

>[!TIP]
>
>對於源自非贊助內容來源的任何促銷活動/支出（例如「文字廣告」或「贊助的InMail」的促銷活動型別）， [!DNL Marketo Measure] 會 _非_ 本身就支援追蹤這些促銷活動型別。 如果您想要同時追蹤這些促銷活動的支出，以及您的「贊助內容」支出，請務必使用我們的行銷支出CSV以手動方式記錄所述的支出。

## 運作方式：贊助內容 {#how-it-works-sponsored-content}

>[!NOTE]
>
>首次使用前，您必須透過導覽至「 」以啟用此功能設定。 [!DNL Marketo Measure] [!UICONTROL Settings] > [!UICONTROL Integrations] > [!UICONTROL Ads] > [!UICONTROL Enable LinkedIn Lead Gen Forms].

**[!DNL LinkedIn's]獨特的自動標籤需求**

[!DNL Marketo Measure] 有助於追蹤您的 [!DNL LinkedIn] 藉由自動標籤您的登入頁面，獲得行銷活動績效。

[!DNL Marketo Measure] 將搜尋具有唯一LinkedIn分享的創意產品，並新增 `?_bl={creativeId}` 引數到其結尾。

**複製共用**

使用這個 [!DNL Marketo Measure/LinkedIn] 整合，我們要求客戶不要複製/複製/複製現有的創意內容。 如果找到共用並偵測到它只用於一個Creative， [!DNL Marketo Measure] 可以將「共用」標示為原樣，而不需要重新建立任何「創意」或「共用」，而所有廣告歷史記錄（曝光數、點按數、共用數）將會保留。

找到可在多個創意人員之間共用的共用後， [!DNL Marketo Measure] 必須執行暫停、複製和重新標籤的程式，才能建立唯一的集合。 [!DNL Marketo Measure] 將會暫停並封存即時創意內容，因此會清除廣告歷史記錄（包括曝光數、點按數和社交分享），以正確自動標籤所有內容。

往後， [!DNL Marketo Measure] 建議您不要複製任何 [!DNL LinkedIn] 共用並儘可能保持所有創意和共用內容的不重複，因此我們只需新增追蹤功能，無需清除廣告歷程記錄。

**縮短的URL**

額外步驟的原因是LinkedIn允許目的地URL為縮短URL （bit.ly、goog.le等），這表示 [!DNL Marketo Measure] 看不到長且已解析的URL和 [!DNL Marketo Measure] 需要將追蹤引數新增到解析的URL。 為了解決這個問題， [!DNL Marketo Measure] 會在重新建立廣告之前尋找縮短的URL，展開URL，然後使用解析的URL及其所有引數建立新廣告，允許 [!DNL Marketo Measure] 以新增標籤。 建立新廣告會清除廣告歷程記錄（曝光數、點按數、分享數），因此需要許可權才能標籤縮短的URL。

如果您大量使用縮短的URL，可能會嚴重影響您的創意成果。 建議您不要再使用縮短的URL，以便 [!DNL Marketo Measure] 可以標籤登入頁面，而無須建立新廣告並清除廣告歷程記錄。

**程式**

讓我們從一些範例開始。 假設我們有....

創意A ：共用123\
創意B ：共用234\
創意C ：共用234\
創意D ：共用234

![](assets/two.png)

`1)` [!DNL Marketo Measure] 將首先檢視所有狀態為「作用中」的行銷活動、創意和共用。 [!DNL Marketo Measure] 將不會標籤已暫停、已封存或已取消的廣告。 如果廣告暫停，則設為 [!UICONTROL active]，我們會在它再次啟用時加上標籤。 如果可以找到唯一的共用，表示它不會用於多個創意內容或行銷活動（例如，創意內容A ：共用123）， [!DNL Marketo Measure] 將新增我們的自訂引數 `>> ?_bl={creativeId}` 至共用URL。

`2)` 現在，如果共用了且失去其唯一性（例如，Creative B ： Share 234和Creative C ： Share 234和Creative D ： Share 234）， [!DNL Marketo Measure] 將暫停並封存所有類似的創意內容（包括Creative B、Creative C和Creative D）。

`3)` [!DNL Marketo Measure] 將會建立3個新創意元素，即Creative E、Creative F和Creative G，這些元素會複製已封存的Creative B內容。

`4)` [!DNL Marketo Measure] 也會建立3個新共用、Share 345、Share 456和Share 567，以複製Share 234的內容，但會有自己獨特的內容 `?_bl` 標籤。

`5)` [!DNL Marketo Measure] 將必須定期檢查共用是否未共用，如果共用，我們會在上述步驟2重新啟動程式。

>[!NOTE]
>
>實作這表示我們的客戶將會遺失創意B的廣告歷史：共用234、創意C ：共用234和創意D ：共用234，因為現在分別透過Creative E ：共用345、共用F ：共用456和創意G ：共用567重新建立。

![](assets/three.png)

## 運作方式：領導新一代Forms {#how-it-works-lead-gen-forms}

**程式**

到 [!DNL LinkedIn's] 廣告表單API和廣告表單回應API，我們就能收集廣告帳戶的表單提交資料，並從CRM或Marketo將電子郵件地址關聯至銷售機會。

linkedIn表單可能包含多個電子郵件地址。 下載表單回應時，我們會尋找具有下列優先順序的電子郵件地址：工作電子郵件、電子郵件地址（主要表單欄位）或具有有效電子郵件值的自訂欄位。

無論行銷活動或創意狀態為何，所有表單回應都會產生接觸點。 [!DNL Marketo Measure] 有90天的回溯限制，因此 [!DNL Marketo Measure] 無法存取90天以前的表單回應，但 [!DNL Marketo Measure] 和 [!DNL LinkedIn] 啟用整合後，透過看到的潛在客戶一般表單接觸點會越多 [!DNL Marketo Measure].

>[!NOTE]
>
>linkedIn成本仍會下載為贊助內容行銷活動的一部分。

**在CRM或Marketo中追蹤銷售機會總成Forms**

早於 [!DNL Marketo Measure] linkedIn Lead Gen Forms整合已經存在，客戶通常會將表單提交推送至Marketo方案及/或CRM Campaign，以追蹤表單並接收這些活動的歸因。 啟用Lead Gen Forms設定後，我們希望確保這些表單提交不會重複計算。 請檢查下列專案：

* CRM物件上的「啟用購買者接觸點」欄位設為「無」或「排除所有促銷活動成員」
* 更新任何相關的Marketo計畫或Marketo活動規則
* 更新任何相關的CRM Campaign規則

>[!NOTE]
>
>linkedIn API具有90天的回顧限制，因此如果您使用Marketo或CRM規則，建議您將規則的結束日期設為您在中啟用整合的日期之前的90天 [!DNL Marketo Measure].

## 接觸點詳細資訊 {#touchpoint-details}

一次 [!DNL Marketo Measure] 已成功在LinkedIn creative上標籤您的登陸頁面，您將能夠在接觸點上檢視已解決的廣告資料。 以下是您應會看到的資料值對應：

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
   <td><p>廣告ID </p></td> 
   <td><p>84186224 </p></td> 
  </tr> 
  <tr> 
   <td><p>廣告內容 </p></td> 
   <td><p>copy-1-image-2-man 95%的行#B2B人員認為需求建立策略是成功的。 瞭解更多： [!DNL https]：//lnkd.in/jgdi50vKrgv</p></td> 
  </tr> 
  <tr> 
   <td><p>廣告群組ID </p></td> 
   <td><p>(空白) </p></td> 
  </tr> 
  <tr> 
   <td><p>廣告群組名稱 </p></td> 
   <td><p>(空白) </p></td> 
  </tr> 
  <tr> 
   <td><p>廣告行銷活動ID </p></td> 
   <td><p>138949954 </p></td> 
  </tr> 
  <tr> 
   <td><p>廣告行銷活動名稱 </p></td> 
   <td><p>SU - COM帳戶 — 需求技能 </p></td> 
  </tr> 
  <tr> 
   <td><p>廣告目的地URL </p></td> 
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
   <td><p>關鍵字ID </p></td> 
   <td><p>(空白) </p></td> 
  </tr> 
  <tr> 
   <td><p>關鍵字元合型別 </p></td> 
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
   <td><p>搜尋片語 </p></td> 
   <td><p>(空白) </p></td> 
  </tr> 
  <tr> 
   <td><p>接觸點型別 </p></td> 
   <td><p>網路表單 </p></td> 
  </tr> 
  <tr> 
   <td><p>接觸點來源 </p></td> 
   <td><p>LinkedIn </p></td> 
  </tr> 
 </tbody> 
</table>

## 成本 {#costs}

因為 [!DNL Marketo Measure] 與直接整合 [!DNL LinkedIn]，我們每天都會下載每個行銷活動和創意的錄製支出。 客戶不需要報告 [!DNL LinkedIn] 花費在 [!DNL Marketo Measure] 應用程式。

就像其他廣告整合一樣， [!DNL Marketo Measure] 已定義行銷管道規則來放置全部 [!DNL LinkedIn] 行銷活動、創意和成本。 若要使用規則，客戶會想要為其「已付」插入新列 [!DNL LinkedIn] 努力。 可以是新的或現有的管道。 在反向連結欄中，使用定義「[」[!DNL LinkedIn] 已付費]」，其中 [!DNL Marketo Measure] 已定義為任何具有下列專案的接觸點： [!DNL Marketo Measure] 標籤之間。

![](assets/four.png)

## [!DNL Marketo Measure] 探索 {#marketo-measure-discover}

已進行一些增強功能 [!DNL Marketo Measure] 探索如何支援Lead Gen Forms報告。

**付費媒體展示板**

潛在客戶Gen Forms動態磚：包含LinkedIn表單填入數的新動態磚。 鑽研此計數會顯示活動ID、表單日期、表單名稱和電子郵件地址。

**參與路徑板**

事件歷程：針對透過整合形成的表單，包含「活動」事件型別和媒體「潛在客戶一般表單」。 鑽研檢視包含Campaign、創意和表單詳細資料。

## 贊助內容常見問題集 {#sponsored-content-faq}

**什麼是Dark Share？**

黑暗分享是從未在公司頁面上張貼過的貼文，而且會立即建立並直接新增為「創意」。 因此 [!DNL Marketo Measure]-created Creative不會出現在公司頁面頂端並再次獲得提升，會使用黑暗共用，以便在幕後啟動。

**狀態功能 [!DNL Marketo Measure] 是否實際標籤？**

在上，有四種不同的狀態 [!DNL LinkedIn] 行銷活動和創意：作用中、已暫停、已封存和已取消。 我們只會標籤作用中的行銷活動和創意內容。 標籤其他狀態會再次將其設定為「使用中」。 [!DNL Marketo Measure] 將不會標籤「已暫停、已封存或已取消的行銷活動」或「創意」，但如果狀態變更為「作用中」，則會繼續標籤。

**什麼值才會 [!DNL Marketo Measure] 使用來標籤嗎？**

在目的地URL結尾， [!DNL Marketo Measure] 正在新增引數 `&_bl={creativeId}`，其中 `{creativeId}` 是LinkedIn的創作ID。 使用創作Id， [!DNL Marketo Measure] 也可以判斷促銷活動ID，因為 [!DNL LinkedIn] 有相當基本的廣告結構，因為每個廣告只能屬於一個行銷活動。

**我的舊創意曾經發生了什麼事 [!DNL Marketo Measure] 會建立其新版本嗎？**

時間 [!DNL Marketo Measure] 重新建立共用並將其放入新創意中，舊創意會存檔。 這也是為什麼 [!DNL Marketo Measure] 不會標籤已封存的行銷活動或創意 — 否則會循環 [!DNL Marketo Measure] 正在嘗試無限期地標籤它。

**為什麼已建立廣告的目的地URL不符合我的原始廣告？**

[!DNL Marketo Measure] 需要將追蹤引數新增到已解析的URL，但API中顯示的URL可能是縮短的URL，而不會出現所有引數。 為了解決這個問題， [!DNL Marketo Measure] 在重新建立新增之前會尋找縮短的URL、將其解析，然後使用解析的URL及其所有引數建立新廣告，允許 [!DNL Marketo Measure] 以新增標籤。

**您是否標籤我所有的廣告？ 我沒有在所有登陸頁面上看到bl引數？**

我們觀察到一些行銷人員會將影像連結放入目的地URL，而 [!DNL Marketo Measure] 無法標籤，因此我們會搜尋廣告內容中的URL。 如果 [!DNL Marketo Measure] 具有標籤縮短的URL的許可權，我們將展開該URL和標籤，但由於LinkedIn的複製結構，其文字會自動縮短。 標籤會留在LinkedIn的短URL中，短URL會出現在接觸點的「廣告內容」欄位中，而非「登陸頁面 — 原始」欄位中。

**糟糕，我的團隊中有人不小心複製了一個共用。 我可以暫停它嗎？**

沒關係。 [!DNL Marketo Measure] 將以程式設計方式檢查不再唯一的共用，這表示它已被複製到不同的Creative。 偵測到副本後， [!DNL Marketo Measure] 會依照平常的流程來標籤和建立新廣告。

**我的廣告先前有擱置中的檢閱。 為何之後會再次擱置檢閱 [!DNL Marketo Measure] 已標籤？**

linkedIn要求所有已建立或修改的廣告在張貼前都必須通過正常的安全性程式。 [!DNL Marketo Measure] 會嘗試儘快攔截廣告，因為它每6小時掃描一次新廣告，但使用 [!DNL LinkedIn's] 額外步驟可能會將啟動延遲數小時。

**我的廣告上有2個URL。 哪一個會加上標籤？**

兩者。 此 [!DNL Marketo Measure] 整合可讓我們從廣告中的點進影像標籤目的地URL，但也會自動更新廣告說明中的縮短URL。

![](assets/five.png)

**我已連線我的 [!DNL LinkedIn ads] 帳戶。 為什麼不是 [!DNL Marketo Measure] 標籤我的連結？**

連線的 [!DNL LinkedIn] 使用者需要有適當的編輯存取權，這表示使用者必須是帳戶管理員、行銷活動管理員或創意管理員。

**如何知道我的創意是否會複製？ 我是否可檢視我的創意人員是否使用相同的共用？**

中未提供共用ID [!DNL LinkedIn] 因此，沒有明確且顯而易見的方式可檢查創意分享對應。 如果您懷疑某創意內容可能是復本，您可以從內開啟廣告以手動檢查 [!DNL LinkedIn] 行銷活動管理員 — 這會在新標籤中開啟廣告，而您可以在URL中找到共用ID。

![](assets/six.png)

## Forms銷售機會總管常見問題集 {#lead-gen-forms-faq}

**這項增強功能的成本為何？**

此優惠方案包含在任何付費專案中 [!DNL Marketo Measure] 訂閱。

**整合是否可回溯？**

是，我們將從LinkedIn下載歷史廣告表單回應，不過回顧期間的上限為90天。 「 」變得 [!DNL Marketo Measure] 在啟用LinkedIn整合後，您透過以下連結可看見更多Lead Gen Form接觸點： [!DNL Marketo Measure].

沒有選項可設定下載的特定日期，但如果有需要隱藏的接觸點，您可以選擇設定接觸點刪除規則。

**如果我已經在使用 [!DNL Marketo Measure] linkedIn廣告整合？**

不會，我們不會自動開始為所有客戶下載，但在設定中啟用此功能是非常簡單的開關。

**是否有可用的表單資料？**

表單資料可透過以下方式取得： [!DNL Marketo Measure] 探索表單識別碼和表單名稱。 CRM中的接觸點物件尚未提供表單詳細資料。

**任何專案會發生什麼事 [!DNL LinkedIn] 之前已同步至Marketo方案或CRM行銷活動的潛在客戶？**

建議您調整任何 [!DNL Marketo Measure] 從這些特定「方案」或「行銷活動」產生接觸點以避免重複的規則。 linkedIn API具有90天的回顧限制，因此如果您使用Marketo或CRM規則，建議您將規則的結束日期設為您在中啟用整合的日期之前的90天 [!DNL Marketo Measure]. 從此刻起， [!DNL Marketo Measure] 可以下載這些銷售機會，為您提供更深入的分析和詳細資訊。

**其中是否包含任何自動標籤或追蹤？**

否，這與其他不同 [!DNL Marketo Measure] 整合。 由於登陸頁面中沒有點進次數，因此我們只從LinkedIn下載相關資訊，並將其視為內的活動，而非修改登陸頁面 [!DNL Marketo Measure].
