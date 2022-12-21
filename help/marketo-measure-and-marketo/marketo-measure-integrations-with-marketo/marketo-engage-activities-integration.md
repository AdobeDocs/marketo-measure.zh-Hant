---
unique-page-id: 42762749
description: '"[!DNL Marketo Engage] 活動整合 —  [!DNL Marketo Measure]  — 產品檔案」'
title: '"[!DNL Marketo Engage] 活動整合」'
exl-id: 463ad9b2-e1bd-49dd-8bf5-0da7b7132f05
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '1608'
ht-degree: 0%

---

# [!DNL Marketo Engage] 活動整合 {#marketo-engage-activities-integration}

作為 [!DNL Marketo Measure] 和 [!DNL Marketo Engage] 整合，此項吸引Marketo活動的努力發揮了巨大作用。 透過Marketo活動，系統會追蹤事件，例如點擊電子郵件、變更分數或進行中的變更狀態 — 您可以縮小並定義這些活動類型，以選取符合接觸點資格的子集。 在這些活動上建立接觸點後，就會在參與歷程中追蹤這些接觸點，並與您的其他行銷管道（例如付費搜尋或合作夥伴行銷）一起測量。

## 需求 {#requirements}

* 生產Marketo例項
* 生產 [!DNL Salesforce] 或 [!DNL Microsoft Dynamics] 執行個體
* 任何已付 [!DNL Marketo Measure] 訂閱
* Marketo People Sync(啟用[!DNL Marketo Measure] 設定)
* Marketo計畫已啟用([!DNL Marketo Measure] 設定)
* Marketo活動已啟用([!DNL Marketo Measure] 設定)

## 設定 {#setup}

1. 若要開始設定Marketo活動，請導覽至 **我的帳戶** > **設定** > **活動**.

   ![](assets/one-1.png)

   ![](assets/two-1.png)

   首先需要選取您計畫要建立規則的活動類型清單。 不需要確切的活動類型數量，但我們也建議您不要讓接觸點超載，並淡化重要里程碑的重要性。 如此一來，追蹤相關參與的活動類型可能不會超過5種。

1. 按一下下方的下拉式功能表 [!UICONTROL Select Activities Types] 以開始選擇各種類型。

   ![](assets/three-1.png)

1. 選取您需要的所有活動後，您也會看到這些活動已填入您的 [!UICONTROL Selected Activities List] 以及 [!UICONTROL Define Rules].

   ![](assets/four-1.png)

1. 對於每個活動類型，您將需要定義一或多個規則，以決定哪些記錄符合接觸點的資格。 例如，我們將為「變更分數」活動類型新增規則，以便當Marketo人員達到90分或更高分數時，系統將建立接觸點。

1. 首先，視活動類型而定，您可能需要設定 [!DNL Marketo Measure] 行銷活動名稱，稍後可用於通道對應。 [!DNL Marketo Measure] 行銷活動名稱可在多個規則之間重複使用。 這有助於在單一管道規則中使用更廣泛的名稱。 並非所有活動類型都包含Marketo方案，因此需要命名作為第一步。

   以下範例說明額外步驟的外觀：

   ![](assets/five-1.png)

1. 在我們的「變更分數」範例中，我們不需要輸入促銷活動名稱，因為我們可以從Marketo計畫提取該資訊。 現在您可以建立規則運算式。 依照我們的範例，我們要選取欄位「[!UICONTROL New Value]&quot;，運算子為&quot;[!UICONTROL is greater than]」，值為90。

   您可以展開規則，並新增「and」或「or」陳述式來縮小結果範圍，以新增其他篩選器或條件。

   ![](assets/six-1.png)

   ![](assets/seven-1.png)

1. 最後，選擇應將哪些項目設為接觸點日期。 所有可用的日期或日期/時間欄位都會從Marketo顯示在此處。 除非您有自訂日期欄位，否則您會看到「[!UICONTROL Activity Date].&quot;

   ![](assets/eight-1.png)

1. 請務必按一下 **[!UICONTROL Save As Draft]** 這樣你才不會丟失變更。

   ![](assets/nine-1.png)

1. 導覽至 **[!UICONTROL Attribute Mapping]** 標籤。

   ![](assets/ten-1.png)

1. 對於您選取的每個活動類型，您可以選擇將其他Marketo屬性對應至接觸點欄位，以便在中檢視和報告這些值 [!DNL Marketo Measure Discover] 或在CRM中。

   許多欄位已自動對應，且無法變更，以便與其他整合一致。 請參考下方的欄位對應區段，以尋找這些值。 對於某些活動類型，Marketo包含著陸頁面、反向連結頁面或瀏覽器的屬性，您可選擇對應至接觸點欄位。 在以下範例中，我們已提出一些可移除的其他建議。

1. 從您要對應的左欄選取「購買者接觸點」欄位。 接著，在「購買者接觸點」欄位中選取您要填入的Marketo屬性。 請記住，這些是選填的，除了這些外，還有其他對應 [!DNL Marketo Measure] 已經建立。

   可映射欄位：

   * 城市
   * 國家
   * 地區
   * 登陸頁面
   * 反向連結頁面
   * 表單頁面
   * 表單日期
   * 平台
   * 瀏覽器

   >[!NOTE]
   >
   >此清單中沒有廣告欄位，例如「廣告內容」或「關鍵字」，因為這些欄位是我們的廣告平台整合所保留的。

## 活動類型 {#activity-types}

有些活動類型會提供方案ID和方案名稱，因此您可輕鬆將其對應至購買者接觸點上的促銷活動ID和促銷活動名稱。 對於其他人，沒有程式關聯，因此部分規則定義將要求您建立 [!DNL Marketo Measure] 促銷活動名稱。 以下是各類別的清單：

**具有方案ID的活動類型**

發送電子郵件(6)\
電子郵件傳送(7)\
電子郵件已跳出(8)\
取消訂閱電子郵件(9)\
開啟電子郵件(10)\
按一下「電子郵件」(11)\
變更資料值(13)\
變更分數(22)\
添加到清單(24)\
進展中的更改狀態(104)\
Add to Nurture(113)\
改變後勁(115)

>[!NOTE]
>
>在我們預期方案ID的活動類型中，如果在沒有方案的情況下偵測到活動， [!DNL Marketo Measure] 將不接受作為合格接觸點，因為我們不能有空的促銷活動值。

**沒有方案ID的活動類型**

按一下連結(3)\
新銷售機會(12)\
同步銷售機會到SFDC(19)\
轉換銷售機會(21)\
更改所有者(23)\
從清單中刪除(25)\
SFDC活動(26)\
Email Burked Soft(27)\
從SFDC刪除銷售機會(29)\
合併銷售機會(32)\
添加到Opportunity(34)\
從Opportunity中刪除(35)\
更新機會(36)\
刪除銷售機會(37)\
發送警報(38)\
發送銷售電子郵件(39)\
開啟銷售電子郵件(40)\
按一下銷售電子郵件(41)\
新增至SFDC促銷活動(42)\
從SFDC促銷活動中移除(43)\
SFDC促銷活動中的更改狀態(44)\
接收銷售電子郵件(45)\
要求促銷活動(47)\
已退回銷售電子郵件(48)\
更改收入階段(101)\
手動更改收入階段(102)\
變更區段(108)\
呼叫Webhook(110)\
已轉發給好友電子郵件(111)\
已轉發給好友電子郵件(112)\
改變後繼軌跡(114)\
推送銷售機會至Marketo(145)\
同步至Microsoft(300)\
共用內容(400)參與對話(158)與(159)計畫對話約會(160)對話目標達到(161)自訂活動(xxx)的檔案

## 通道對應 {#channel-mapping}

對於具有方案ID的活動類型中的任何規則，Marketo方案管道是由方案決定。 我們會使用Program Channel對應至您的自訂離線頻道，因此您必須確定已正確設定您的頻道 [此處說明](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md#channel-mapping).

對於沒有方案ID的活動類型中的任何規則，您的第一步是建立促銷活動名稱。 使用此促銷活動名稱來設定您的自訂線上頻道 [在這裡](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

如果您Marketo活動的管道未正確設定，則您的新接觸點可能會落在「其他」管道下。

## 計畫成本 {#program-costs}

通過導入Marketo程式的資料，成本會自動從期間成本下載，而Marketo中報告的成本會在分配的月份中分配。 例如，如果2021年1月報告了$1000，則$1000會平分31天。 成本位於 [!DNL Marketo Measure Discover].

## Cookie對應 {#cookie-mapping}

由於 [!DNL Marketo Measure] 與Marketo的整合， [!DNL Marketo Measure] Cookie ID現在也已對應並同步至 [!DNL Marketo Munchkin Id]. 這有助於縮小間隙，將匿名的首次接觸歸因於Web工作階段，而非將FT和LC接觸歸因於Marketo活動。 想像一下這種情景：

在Facebook廣告上標籤點擊，然後登陸wayneenterprises.com，讓他在那裡獲得Cookie [!DNL Marketo Measure] Id 123和 [!DNL Marketo Munchkin Id] 456。 不會填表。

Wayne企業營銷團隊向特定目標線索發送電子郵件，其中一個是 `mark@email.com`.

`mark@email.com` 收到電子郵件，並點進及登陸 `wayneenterprises.com`. 這會變成 `mark@email.com's` 第二次瀏覽 `wayneenterprise.com` 使用相同的Cookie Id，但沒有表單填入，因此 [!DNL Marketo Measure]，仍為匿名訪客。

Wayne Enterprises Marketing團隊會建立Marketo活動規則，以產生「點按電子郵件」活動類型的接觸點。

今天的實作將為 `mark@email.com` 從「點擊電子郵件」活動類型的「Marketo活動」。

透過此Cookie對應增強功能，英國《金融時報》會回頭獲得Facebook廣告的評分，而LC會獲得電子郵件的評分。

>[!NOTE]
>
>有了Cookie對應行為，您可能會發現某些來自網站造訪的LC接觸點。 銷售機會可能出現在Marketo中，且沒有任何相關的活動，然後 [!DNL Marketo Measure] 已下載該lead，符合相關的cookie，然後追蹤到最新的web工作階段，即使沒有建立lead的表單活動亦然。

## 常見問題集 {#faq}

**如何知道要建立Marketo方案規則還是Marketo活動規則？**

此 [!DNL Marketo Engage] 方案整合是根據人員是否為方案的方案成員而生成接觸點的簡單方法。 如果您想要根據人員變更為特定方案狀態的時間來定義規則，則 [!DNL Marketo Engage] 活動整合將是您想要的設定，尤其是「進展中的變更狀態」活動類型，以便您的接觸點日期可對應至系統產生的活動日期。

**為何我的接觸點類型名稱遭截斷？**

觸控點類型欄位是在 [!DNL Marketo Measure] 16個字元的套件。 很可惜，變更欄位的字元限制需要淘汰現有欄位並建立新欄位。 「接觸點類型」的值是「活動類型」，也會在「中」欄位中設定。

**為什麼我的自訂活動類型沒有出現在可用活動清單中？**

我們只顯示「已核准」自訂活動類型，而不顯示「草稿」或「已核准」。

**如何判斷要為哪個活動類型產生接觸點？**

雖然您可以建立的活動類型數目沒有限制，但一般建議不要超過5個活動類型。 判斷哪些行銷活動與接觸點歷程的相關程度，需要花費時間。 例如，「取消訂閱電子郵件」可能不是要追蹤的重要接觸點，但「點按電子郵件」搭配其他篩選器可能是個好接觸點。 這因每個組織和每個團隊而異，因此我們建議您與團隊合作，集中討論此處的最佳方法。

**為什麼我的瀏覽器名稱被切斷？**

此 [!DNL Marketo Measure] 「瀏覽器名稱」的硬式限制為20個字元，不過從Marketo取得的使用者代理值通常會是較長的字串。

BrowserInfo.Name\
BrowserInfo.Version\
PlatformInfo.Name\
PlatformInfo.Version
