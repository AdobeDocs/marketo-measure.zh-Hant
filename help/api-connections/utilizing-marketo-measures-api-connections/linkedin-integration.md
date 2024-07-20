---
unique-page-id: 35586080
description: linkedIn整合 —  [!DNL Marketo Measure]
title: linkedIn整合
exl-id: 705209ef-1ece-496c-ac2f-6a31055bd993
feature: APIs, Integration
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '2644'
ht-degree: 0%

---

# linkedIn整合 {#linkedin-integration}

## 概觀 {#overview}

與LinkedIn的[!DNL Marketo Measure]整合分為兩個部分：

贊助內容： 「贊助內容」整合可讓[!DNL Marketo Measure]在[!DNL LinkedIn]個廣告上標籤目的地URL，這最終可讓[!DNL Marketo Measure]追蹤使用者的整個接觸點歷程，並將活動對應回特定的[!DNL LinkedIn]行銷活動和創意。 這可提供客戶[!DNL LinkedIn]活動投資報酬率的深入分析。

Lead Gen Forms：透過與LinkedIn的Lead Gen Forms整合，Marketo Measure可深入瞭解透過LinkedIn平台提交的表單。 這些表單填寫會比對您CRM或[!DNL Marketo Engage]執行個體的銷售機會，因此符合歸因資格。 透過對有助於產生表單的行銷活動、創意和表單的深入分析，團隊現在可以進一步最佳化其LinkedIn行銷和廣告支出。

## 可用性 {#availability}

可供所有使用者使用。

## 需求 {#requirements}

**行銷活動經理角色**

若要讓[!DNL Marketo Measure]能夠下載廣告資料和廣告成本資料，您必須在「行銷活動管理員」中擁有下列其中一個角色：

* 帳單管理員
* 客戶經理
* 行銷活動管理員

深入瞭解： [促銷活動管理員](https://www.linkedin.com/help/lms/answer/a425731/user-roles-and-functions-in-campaign-manager)中的使用者角色和功能。

**付費媒體管理員角色**

若要讓[!DNL Marketo Measure]能夠建立/更新贊助的創意內容，您必須具備下列其中一個付費媒體管理員角色：

* 贊助內容海報
* Forms銷售機會經理

深入瞭解： [LinkedIn頁面管理員角色](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview)。

我們&#x200B;**不**&#x200B;需要其他[!DNL LinkedIn]個角色才能進行整合。 這些角色經常被誤認為必要的角色，因此請注意，它們是有區別的！

**頁面管理員角色**

若要讓[!DNL Marketo Measure]能夠從潛在客戶一般表單下載/整合潛在客戶，您必須擁有下列頁面管理員角色：

* 超級管理員

深入瞭解： [LinkedIn頁面管理員角色](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview)。

## linkedIn廣告型別 {#linkedin-ad-types}

[!DNL Marketo Measure]將支援：

**贊助內容：**&#x200B;贊助內容可讓您將內容傳送給關注您公司之成員以外的[!DNL LinkedIn]摘要。 贊助內容可以鎖定在特定對象，無論何時何地，只要廣告商在[!DNL LinkedIn]平台上橫跨案頭、行動裝置和平板電腦，都可以協助他們觸及到[!DNL LinkedIn]位成員。 支援Lead Gen Forms的贊助內容。

[!DNL Marketo Measure]支援的贊助內容廣告格式型別為單一影像廣告和視訊廣告(透過Lead Gen Forms)。 由於結構描述的複雜性，我們不支援轉盤廣告。

[!DNL Marketo Measure]不支援贊助訊息、文字廣告或動態廣告。

![](assets/one.png)

>[!TIP]
>
>對於源自非贊助內容來源的任何行銷活動/支出（例如「文字廣告」或「贊助的InMail」行銷活動型別），[!DNL Marketo Measure]不會&#x200B;_從本質上支援這些行銷活動型別的追蹤_。 如果您想要同時追蹤這些促銷活動的支出，以及您的「贊助內容」支出，請務必使用我們的行銷支出CSV以手動方式記錄所述的支出。

## 運作方式：贊助內容 {#how-it-works-sponsored-content}

>[!NOTE]
>
>在第一次使用之前，必須透過導覽至[!DNL Marketo Measure] [!UICONTROL Settings] > [!UICONTROL Integrations] > [!UICONTROL Ads] > [!UICONTROL Enable LinkedIn Lead Gen Forms]來啟用此功能設定。

**[!DNL LinkedIn's]獨特的自動標籤需求**

[!DNL Marketo Measure]可以自動標籤您的登入頁面，協助追蹤您的[!DNL LinkedIn]行銷活動績效。

[!DNL Marketo Measure]將搜尋具有唯一LinkedIn共用的創意內容，並在結尾新增`?_bl={creativeId}`引數。

**正在複製共用**

透過此[!DNL Marketo Measure/LinkedIn]整合，我們要求客戶不要複製/複製/複製現有創意內容。 如果找到「共用」且偵測到它只用於一個Creative，[!DNL Marketo Measure]可以將「共用」標示為原樣，而不需要重新建立任何Creative或Shares，並且所有廣告歷史記錄（曝光數、點按數、共用）都將保留。

一旦發現共用可跨多個創意內容共用，[!DNL Marketo Measure]就必須執行暫停、複製和重新標籤的程式，才能建立唯一集合。 [!DNL Marketo Measure]將暫停並封存即時創意，因此會清除廣告歷史記錄（包括曝光數、點按數和社交分享），以正確自動標籤所有內容。

往後，[!DNL Marketo Measure]建議您不要複製任何[!DNL LinkedIn]個共用，並儘可能將所有創意和共用保持獨特，這樣我們就能在不清除廣告歷史記錄的情況下新增追蹤。

**縮短的URL**

額外步驟的原因是LinkedIn允許目的地URL為縮短的URL （bit.ly、goog.le等），這表示[!DNL Marketo Measure]看不到較長且已解析的URL，而[!DNL Marketo Measure]需要新增追蹤引數至已解析的URL。 為了解決此問題，[!DNL Marketo Measure]在重新建立廣告之前會尋找縮短的URL、展開URL，然後使用已解析的URL及其所有引數建立新廣告，允許[!DNL Marketo Measure]新增標籤。 建立新廣告會清除廣告歷程記錄（曝光數、點按數、分享數），因此需要許可權才能標籤縮短的URL。

如果您大量使用縮短的URL，可能會嚴重影響您的創意成果。 建議您不要再使用縮短的URL，這樣[!DNL Marketo Measure]就可以標籤登入頁面，而無須建立新廣告並清除廣告歷程記錄。

**處理序**

讓我們從一些範例開始。 假設我們有....

創意A ：共用123\
創意B ：共用234\
創意C ：共用234\
創意D ：共用234

![](assets/two.png)

`1)` [!DNL Marketo Measure]將先檢視所有狀態為「作用中」的行銷活動、創意和共用。 [!DNL Marketo Measure]不會標籤已暫停、已封存或已取消的廣告。 如果廣告已暫停，然後設定為[!UICONTROL active]，則當它再次生效時，我們將標籤它。 如果我們能找到唯一的共用，表示它並未用於多個創意內容或行銷活動（例如，創意內容A ：共用123），則[!DNL Marketo Measure]會將我們的自訂引數`>> ?_bl={creativeId}`新增到共用URL。

`2)`現在，如果共用已共用並失去其唯一性（例如，Creative B ： Share 234和Creative C ： Share 234和Creative D ： Share 234），[!DNL Marketo Measure]將暫停並封存所有類似的創意（可能是Creative B、Creative C和Creative D）。

`3)` [!DNL Marketo Measure]將建立3個新創意（Creative E、Creative F和Creative G），以複製已封存的Creative B內容。

`4)` [!DNL Marketo Measure]也將建立3個複製Share 234內容的新共用、Share 345、Share 456和Share 567，但會有自己的唯一`?_bl`標籤。

`5)` [!DNL Marketo Measure]必須定期檢查共用是否未共用，如果共用，我們將在上述步驟2重新啟動程式。

>[!NOTE]
>
>實作這表示我們的客戶將會遺失創意B的廣告歷史：共用234、創意C ：共用234和創意D ：共用234，因為現在分別透過Creative E ：共用345、共用F ：共用456和創意G ：共用567重新建立。

![](assets/three.png)

## 運作方式：領導新一代Forms {#how-it-works-lead-gen-forms}

**[!DNL LinkedIn's]獨特的自動標籤需求**

[!DNL Marketo Measure]可以自動標籤您的登入頁面，協助追蹤您的[!DNL LinkedIn]行銷活動績效。

[!DNL Marketo Measure]將搜尋具有唯一LinkedIn共用的創意內容，並在結尾新增`?_bl={creativeId}`引數。

**處理序**

透過[!DNL LinkedIn's]廣告表單API和廣告表單回應API，我們能夠收集廣告帳戶的表單提交資料，並將電子郵件地址與CRM或Marketo的銷售機會建立關聯。

linkedIn表單可能包含多個電子郵件地址。 下載表單回應時，我們會尋找具有下列優先順序的電子郵件地址：工作電子郵件、電子郵件地址（主要表單欄位）或具有有效電子郵件值的自訂欄位。

無論行銷活動或創意狀態為何，所有表單回應都會產生接觸點。 [!DNL Marketo Measure]有90天的回顧限制，因此[!DNL Marketo Measure]無法存取超過90天的表單回應，但[!DNL Marketo Measure]與[!DNL LinkedIn]整合啟用時間越長，透過[!DNL Marketo Measure]看到的潛在客戶一般表單接觸點就越多。

>[!NOTE]
>
>linkedIn成本仍會下載為贊助內容行銷活動的一部分。

**在CRM或Marketo中追蹤潛在客戶一般人員Forms**

在[!DNL Marketo Measure]與LinkedIn Lead Gen Forms整合存在之前，客戶通常會將表單提交推送至Marketo方案及/或CRM Campaign，以追蹤表單並接收這些活動的歸因。 啟用Lead Gen Forms設定後，我們希望確保這些表單提交不會重複計算。 檢查下列專案：

* CRM物件上的「啟用購買者接觸點」欄位設為「無」或「排除所有促銷活動成員」
* 更新任何相關的Marketo計畫或Marketo活動規則
* 更新任何相關的CRM Campaign規則

>[!NOTE]
>
>linkedIn API具有90天的回顧限制，因此如果您正在使用Marketo或CRM規則，建議您將規則的結束日期設定為您在[!DNL Marketo Measure]中啟用整合的日期之前的90天。

## 接觸點詳細資訊 {#touchpoint-details}

在[!DNL Marketo Measure]在LinkedIn創意上成功標籤您的登陸頁面後，您就可以在接觸點上檢視已解析的廣告資料。 以下是您應會看到的資料值對應：

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th style="width:30%">接觸點欄位</th> 
   <th>範例值</th> 
  </tr> 
  <tr> 
   <td>廣告ID</td>
   <td>84186224</td>
  </tr> 
  <tr> 
   <td>廣告內容</td>
   <td>copy-1-image-2-man 95%的行#B2B人員認為需求建立策略是成功的。 深入瞭解： [!DNL https]：//lnkd.in/jgdi50vKrgv</td>
  </tr> 
  <tr> 
   <td>廣告群組ID</td>
   <td>(空白)</td>
  </tr> 
  <tr> 
   <td>廣告群組名稱</td>
   <td>(空白)</td>
  </tr> 
  <tr> 
   <td>廣告行銷活動ID</td>
   <td>138949954</td>
  </tr> 
  <tr> 
   <td>廣告行銷活動名稱</td>
   <td>SU - COM帳戶 — 需求技能</td>
  </tr> 
  <tr> 
   <td>廣告目的地URL <b>*</b></td>
   <td>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders?_bl=84186217</td> 
  </tr> 
  <tr> 
   <td>表單URL</td> 
   <td>info.bizible.com/demo</td> 
  </tr> 
  <tr> 
   <td>表單URL — 原始</td> 
   <td>info.bizible.com/demo</td> 
  </tr> 
  <tr> 
   <td>關鍵字ID</td> 
   <td>(空白)</td> 
  </tr> 
  <tr> 
   <td>關鍵字元合型別</td> 
   <td>(空白)</td> 
  </tr> 
  <tr> 
   <td>登陸頁面</td> 
   <td>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders</td> 
  </tr> 
  <tr> 
   <td>登陸頁面 — 原始</td> 
   <td>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders?_bl=84186217</td> 
  </tr> 
  <tr> 
   <td>行銷管道</td> 
   <td>付費社交</td> 
  </tr> 
  <tr> 
   <td>行銷管道 — 路徑</td> 
   <td>付費Social.LinkedIn</td> 
  </tr> 
  <tr> 
   <td>中</td> 
   <td>"cpc"或"Lead Gen Form"</td> 
  </tr> 
  <tr> 
   <td>反向連結頁面</td> 
   <td>www.linkedin.com/</td> 
  </tr> 
  <tr> 
   <td>反向連結頁面 — 原始</td> 
   <td>www.linkedin.com/</td> 
  </tr> 
  <tr> 
   <td>搜尋片語</td> 
   <td>(空白)</td> 
  </tr> 
  <tr> 
   <td>接觸點型別</td> 
   <td>網路表單</td>
  </tr> 
  <tr> 
   <td>接觸點Source</td>
   <td>LinkedIn</td>
  </tr> 
 </tbody> 
</table>

**&#42;** _「廣告目的地URL」欄位僅填入贊助的內容。 未為Forms銷售機會層代_&#x200B;填入此值。

<br>

## 成本 {#costs}

由於[!DNL Marketo Measure]與[!DNL LinkedIn]直接整合，因此我們每天都會下載每個行銷活動和創意的錄製支出。 客戶不需要再在[!DNL Marketo Measure]應用程式中報告[!DNL LinkedIn]支出。

如同其他廣告整合，[!DNL Marketo Measure]已定義行銷管道規則來放置所有[!DNL LinkedIn]行銷活動、創意和成本。 若要使用規則，客戶將會想要為其「付費[!DNL LinkedIn]」工作插入新列。 可以是新的或現有的管道。 在「反向連結」欄中，使用定義「[[!DNL LinkedIn] Paid]」，[!DNL Marketo Measure]已將其定義為任何具有[!DNL Marketo Measure]標籤的接觸點。

![](assets/four.png)

## [!DNL Marketo Measure]個探索 {#marketo-measure-discover}

已對[!DNL Marketo Measure] Discover進行一些增強功能，以支援Lead Gen Forms報告。

**付費媒體展示板**

潛在客戶Gen Forms動態磚：包含LinkedIn表單填入數的新動態磚。 鑽研此計數會顯示活動ID、表單日期、表單名稱和電子郵件地址。

**參與路徑展示板**

事件歷程：針對透過整合形成的表單，包含「活動」事件型別和媒體「潛在客戶一般表單」。 鑽研檢視包含Campaign、創意和表單詳細資料。

## 贊助內容常見問題集 {#sponsored-content-faq}

**什麼是Dark Share？**

黑暗分享是從未在公司頁面上張貼過的貼文，而且會立即建立並直接新增為「創意」。 為了讓[!DNL Marketo Measure]建立的創意內容不會出現在公司頁面頂端，並再次獲得提升，系統會使用黑暗共用，以便能夠在幕後啟動。

**[!DNL Marketo Measure]實際標籤哪些狀態？**

[!DNL LinkedIn]行銷活動和創意有四種不同的狀態：作用中、已暫停、已封存和已取消。 我們只會標籤作用中的行銷活動和創意內容。 標籤其他狀態會再次將其設定為「使用中」。 [!DNL Marketo Measure]不會標籤「已暫停、已封存或已取消的行銷活動」或「創意」，但如果狀態變更為「作用中」，則會繼續標籤。

**[!DNL Marketo Measure]用來標籤的值是多少？**

在目的地URL結尾，[!DNL Marketo Measure]正在新增引數`&_bl={creativeId}`，其中`{creativeId}`是來自LinkedIn的創作ID。 使用創作ID，[!DNL Marketo Measure]也可以判斷促銷活動ID，因為[!DNL LinkedIn]具有相當基本的廣告結構，因為每個創意只能屬於一個促銷活動。

**當[!DNL Marketo Measure]建立新版本的舊創意後，會發生什麼事？**

當[!DNL Marketo Measure]重新建立共用並將其放入新創意中時，舊創意會封存。 這也是為什麼[!DNL Marketo Measure]不會標籤已封存的行銷活動或創意 — 否則會無限期地重複使用[!DNL Marketo Measure]嘗試標籤。

**為什麼建立的廣告目的地URL不符合我的原始廣告？**

[!DNL Marketo Measure]需要將追蹤引數新增到已解析的URL，但API中顯示的URL可能是縮短的URL，沒有出現所有引數。 為了解決這個問題，[!DNL Marketo Measure]在重新建立新增之前會尋找縮短的URL，將其解析，然後使用解析的URL及其所有引數建立新廣告，允許[!DNL Marketo Measure]新增標籤。

**您是否標籤我所有的廣告？ 我沒有在所有登陸頁面上看到bl引數？**

我們觀察到某些行銷人員會將影像連結放入目的地URL （無法標籤[!DNL Marketo Measure]），因此我們在廣告內容中搜尋該URL。 如果[!DNL Marketo Measure]具有標籤縮短的URL的許可權，我們會展開該URL並加上標籤，但由於LinkedIn的複製結構，它會自動在文字中縮短。 標籤會留在LinkedIn的短URL中，短URL會出現在接觸點的「廣告內容」欄位中，而非「登陸頁面 — 原始」欄位中。

**糟糕，我的團隊中有人不小心複製了一個共用。 我可以暫停它嗎？**

沒關係。 [!DNL Marketo Measure]將以程式設計方式檢查不再唯一的共用，這表示它已被複製到其他的Creative。 偵測到副本後，[!DNL Marketo Measure]將依照平常的流程標籤並建立新廣告。

**我的廣告先前擱置檢閱。 為什麼在[!DNL Marketo Measure]標籤它之後它再次擱置檢閱？**

linkedIn要求所有已建立或修改的廣告在張貼前都必須通過正常的安全性程式。 [!DNL Marketo Measure]嘗試儘快攔截廣告，因為它每6小時掃描一次新廣告，但透過[!DNL LinkedIn's]個額外的步驟，可能會延遲幾個小時的啟動。

**我的廣告中有2個URL。 哪一個被標籤？**

兩者。 [!DNL Marketo Measure]整合可讓我們從廣告中的點進影像標籤目的地URL，但也會自動更新廣告說明中的縮短URL。

![](assets/five.png)

**我已連線我的[!DNL LinkedIn ads]帳戶。 為什麼[!DNL Marketo Measure]沒有標籤我的連結？**

已連線的[!DNL LinkedIn]使用者需要適當的編輯存取權，這表示使用者必須是帳戶管理員、行銷活動管理員或創意管理員。

**如何知道我的創意是否會複製？ 我是否能看到我的創意人員使用相同的共用？**

[!DNL LinkedIn]報表中未提供共用ID，因此沒有明確且顯而易見的方式可檢查創意與共用對應。 如果您懷疑創意可能是復本，您可以從[!DNL LinkedIn]行銷活動管理員中開啟廣告以手動方式檢查，這會在新標籤中開啟廣告，而您可以在URL中找到共用ID。

![](assets/six.png)

## Forms銷售機會總管常見問題集 {#lead-gen-forms-faq}

**此增強功能的成本為何？**

此方案包含在任何付費的[!DNL Marketo Measure]訂閱中。

**整合是否可以回溯？**

是，我們將從LinkedIn下載歷史廣告表單回應，不過回顧期間的上限為90天。 啟用[!DNL Marketo Measure]與LinkedIn整合的時間越長，透過[!DNL Marketo Measure]看到的潛在客戶一般表單接觸點就越多。

沒有選項可設定下載的特定日期，但如果有需要隱藏的接觸點，您可以選擇設定接觸點刪除規則。

**如果我已經在使用[!DNL Marketo Measure] LinkedIn廣告整合，這是否會自動啟用？**

不會，我們不會自動開始為所有客戶下載，但在設定中啟用此功能是非常簡單的開關。

**是否有表單資料？**

可透過[!DNL Marketo Measure] Discover取得表單資料，包括表單ID和表單名稱。 CRM中的接觸點物件尚未提供表單詳細資料。

**先前已同步至Marketo方案或CRM行銷活動的任何[!DNL LinkedIn]銷售機會有什麼改變？**

建議您調整任何[!DNL Marketo Measure]規則，以從這些特定方案或行銷活動產生接觸點，以避免重複。 linkedIn API具有90天的回顧限制，因此如果您正在使用Marketo或CRM規則，建議您將規則的結束日期設定為您在[!DNL Marketo Measure]中啟用整合的日期之前的90天。 從此刻起，[!DNL Marketo Measure]可以下載這些銷售機會，為您提供更深入的分析和詳細資訊。

**是否包含任何自動標籤或追蹤？**

否，這與其他[!DNL Marketo Measure]整合不同。 我們不修改登入頁面（因為沒有點進登入頁面），而是從LinkedIn下載相關資訊，並將它們視為[!DNL Marketo Measure]中的活動。
