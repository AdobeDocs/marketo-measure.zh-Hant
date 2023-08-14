---
unique-page-id: 42762749
description: '"[!DNL Marketo Engage] 活動整合 —  [!DNL Marketo Measure]  — 產品檔案」'
title: '"[!DNL Marketo Engage] 活動整合」'
exl-id: 463ad9b2-e1bd-49dd-8bf5-0da7b7132f05
feature: Integration
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '1608'
ht-degree: 0%

---

# [!DNL Marketo Engage] 活動整合 {#marketo-engage-activities-integration}

作為整體的一部分 [!DNL Marketo Measure] 和 [!DNL Marketo Engage] 整合，這種提取Marketo活動的努力扮演了重要的角色。 透過Marketo活動，系統會追蹤事件，例如按一下電子郵件、變更分數或進度中的變更狀態 — 這些活動型別可以精簡並定義，以選取符合接觸點資格的子集。 在這些活動上建立接觸點後，即會在參與歷程中進行追蹤，並與您的其他行銷管道一起測量，例如付費搜尋或合作夥伴行銷。

## 需求 {#requirements}

* 生產Marketo執行個體
* 生產 [!DNL Salesforce] 或 [!DNL Microsoft Dynamics] 例項
* 任何付費 [!DNL Marketo Measure] 訂閱
* Marketo人員同步已啟用([!DNL Marketo Measure] 設定)
* Marketo程式已啟用([!DNL Marketo Measure] 設定)
* Marketo活動已啟用([!DNL Marketo Measure] 設定)

## 設定 {#setup}

1. 若要開始設定Marketo活動，請導覽至 **我的帳戶** > **設定** > **活動**.

   ![](assets/one-1.png)

   ![](assets/two-1.png)

   首先需要選取您計畫建立規則的活動型別清單。 不需要固定數量的活動型別，但我們也建議您不要讓接觸點過載，並淡化重要里程碑的重要性。 話雖如此，您不需要超過5個活動型別即可追蹤相關參與。

1. 按一下下方的下拉式功能表 [!UICONTROL Select Activities Types] 以開始選擇各種型別。

   ![](assets/three-1.png)

1. 選取所有需要的活動後，您也會看到它們已填入至 [!UICONTROL Selected Activities List] 以及在 [!UICONTROL Define Rules].

   ![](assets/four-1.png)

1. 對於每個活動型別，您將需要定義一或多個規則來決定哪些記錄適用於接觸點。 例如，我們會新增「變更分數」活動型別的規則，以便在Marketo人員達到90分或以上時系統建立接觸點。

1. 首先，視活動型別而定，您可能需要設定 [!DNL Marketo Measure] 稍後可用於管道對應的促銷活動名稱。 [!DNL Marketo Measure] 行銷活動名稱可在多個規則中重複使用。 這有助於在單一管道規則中使用更廣泛的名稱。 並非所有活動型別都包含Marketo程式，因此第一個步驟需要名稱。

   以下是該額外步驟的範例：

   ![](assets/five-1.png)

1. 在「變更分數」範例中，我們不需要輸入行銷活動名稱，因為我們可以從Marketo方案提取該資訊。 現在您可以建立規則運算式。 依照我們的範例，我們要選取欄位&quot;[!UICONTROL New Value]「 」加上運運算元「[!UICONTROL is greater than]」的URL區段。

   您可以展開規則，並新增「and」或「or」陳述式來縮小結果範圍，藉此新增其他篩選器或條件。

   ![](assets/six-1.png)

   ![](assets/seven-1.png)

1. 最後，選擇我們應該使用什麼作為接觸點日期。 所有可用的日期或日期/時間欄位將會從Marketo顯示在這裡。 除非您有自訂日期欄位，否則您將會看到「[!UICONTROL Activity Date].」

   ![](assets/eight-1.png)

1. 請務必按一下 **[!UICONTROL Save As Draft]** 讓您的變更不會遺失。

   ![](assets/nine-1.png)

1. 導覽至 **[!UICONTROL Attribute Mapping]** 標籤。

   ![](assets/ten-1.png)

1. 對於您選取的每個活動型別，您都可以選擇將其他Marketo屬性對應至接觸點欄位，以便您可以檢視和報告這些值，在 [!DNL Marketo Measure Discover] 或CRM中的。

   許多欄位會自動對應，且無法變更以便與我們的其他整合一致。 請參考下方的欄位對應區段以尋找這些值。 對於某些活動型別，Marketo包含您可選擇對應至接觸點欄位的登陸頁面或反向連結頁面或瀏覽器的屬性。 在下列範例中，我們提出一些其他建議，這些建議可移除。

1. 從左欄中選取您要對應的購買者接觸點欄位。 接著，在「購買者接觸點」欄位中選擇要填入的Marketo屬性。 請記住，這些是選用的其他對應，位於這些對應 [!DNL Marketo Measure] 已建立。

   可對應欄位：

   * 城市
   * 國家
   * 區域
   * 登陸頁面
   * 反向連結頁面
   * 表單頁面
   * 表單日期
   * 平台
   * 瀏覽器

   >[!NOTE]
   >
   >此清單中不提供「廣告內容」或「關鍵字」等廣告欄位，因為這些欄位是為我們的廣告平台整合而保留。

## 活動型別 {#activity-types}

有些活動型別會提供方案ID和方案名稱，因此可輕鬆將其對應至購買者接觸點上的促銷活動ID和促銷活動名稱。 其他人則沒有程式關聯，因此部分規則定義會要求您建立 [!DNL Marketo Measure] 行銷活動名稱。 以下是每個類別的清單：

**具有計畫ID的活動型別**

傳送電子郵件(6)\
電子郵件已送達(7)\
電子郵件已退回(8)\
取消訂閱電子郵件(9)\
開啟電子郵件(10)\
按一下電子郵件(11)\
變更資料值(13)\
變更分數(22)\
新增至清單(24)\
進度中的變更狀態(104)\
新增至Nurture (113)\
變更Nurture步調(115)

>[!NOTE]
>
>在我們期望方案ID的活動型別中，如果偵測到活動時未使用方案， [!DNL Marketo Measure] 將不接受這作為合格的接觸點，因為我們的Campaign值不能為null。

**沒有計畫ID的活動型別**

按一下連結(3)\
新銷售機會(12)\
同步處理銷售機會至SFDC (19)\
轉換銷售機會(21)\
變更擁有者(23)\
從清單移除(25)\
SFDC活動(26)\
電子郵件已軟退回(27)\
從SFDC刪除銷售機會(29)\
合併銷售機會(32)\
新增至機會(34)\
從機會移除(35)\
更新機會(36)\
刪除銷售機會(37)\
傳送警報(38)\
傳送銷售電子郵件(39)\
開啟銷售電子郵件(40)\
按一下銷售電子郵件(41)\
新增至SFDC Campaign (42)\
從SFDC Campaign移除(43)\
變更SFDC Campaign中的狀態(44)\
接收銷售電子郵件(45)\
請求行銷活動(47)\
銷售電子郵件已退回(48)\
變更收入階段(101)\
手動變更收入階段(102)\
變更區段(108)\
呼叫Webhook (110)\
轉寄給朋友的電子郵件(111)\
已收到轉寄給朋友的電子郵件(112)\
變更培養軌跡(114)\
將銷售機會推送至Marketo (145)\
將銷售機會同步至Microsoft (300)\
共用內容(400)參與對話方塊(158)與(159)互動的對話方塊約會已排程(160)對話方塊目標已達到(161)自訂活動(xxx)

## 頻道對應 {#channel-mapping}

若為具有方案ID的活動型別中的任何規則，則Marketo方案頻道由方案決定。 我們使用「方案頻道」來對應到您的自訂離線頻道，因此您需要確定您的頻道已正確設定 [如這裡指示](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md#channel-mapping).

對於沒有方案ID的活動型別中的任何規則，您的第一步是建立行銷活動名稱。 使用此行銷活動名稱來設定您的自訂線上頻道 [已在此處佈局](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

如果您的Marketo活動管道未正確設定，則您的新接觸點可能會落在「其他」管道下。

## 計畫成本 {#program-costs}

透過Marketo程式的資料匯入，成本會自動從期間成本下載，Marketo中的報告成本會在整個指派的月份中分發。 例如，如果在2021年1月報告$1000，則會將$1000分割為31天。 成本可在下列位置找到： [!DNL Marketo Measure Discover].

## Cookie對應 {#cookie-mapping}

由於 [!DNL Marketo Measure] 與Marketo整合， [!DNL Marketo Measure] Cookie ID現在也已對應並與 [!DNL Marketo Munchkin Id]. 這有助於縮短將匿名首次接觸歸因於網路工作階段的差距，而非將FT和LC接觸均歸因於Marketo活動。 想像一下這種情況：

Mark在Facebook廣告上點選後進入wayneenterprises.com ，在那裡他受到了 [!DNL Marketo Measure] Id 123和 [!DNL Marketo Munchkin Id] 456. 沒有表單填寫。

Wayne企業行銷團隊會傳送電子郵件爆炸訊息給特定的目標銷售機會，其中一個是 `mark@email.com`.

`mark@email.com` 收到電子郵件，點進並登陸 `wayneenterprises.com`. 這會變成 `mark@email.com's` 第二次造訪 `wayneenterprise.com` 具有相同Cookie ID，但表單沒有填入，因此 [!DNL Marketo Measure]，仍為匿名訪客。

Wayne Enterprises行銷團隊會建立Marketo活動規則，以產生「按一下電子郵件」活動型別的接觸點。

今天的實作將為建立單一FT和LC接觸點 `mark@email.com` 從Marketo活動中的「按一下電子郵件」活動型別。

透過這項Cookie對應增強功能，FT將能回到Facebook廣告並取得點數，而LC則會取得電子郵件的點數。

>[!NOTE]
>
>有了Cookie對應行為，您可能會發現一些來自網頁造訪的LC接觸點。 潛在客戶出現在Marketo中時可能會沒有任何相關的活動，然後 [!DNL Marketo Measure] 下載該銷售機會、符合關聯的Cookie，然後將其追蹤到最近的網路工作階段，即使沒有建立該銷售機會的表單活動亦然。

## 常見問題集 {#faq}

**如何知道要建立Marketo方案規則或Marketo活動規則？**

此 [!DNL Marketo Engage] 方案整合是根據某人是否為方案的方案成員來產生接觸點的簡單方法。 如果您有興趣根據人員變更為特定計畫狀態的時間來定義規則， [!DNL Marketo Engage] 活動整合將是您想要的設定，尤其是「進度變更狀態」活動型別，好讓您的接觸點日期可以對應至系統產生的活動日期。

**為什麼我的接觸點型別名稱會遭到截斷？**

「接觸點型別」欄位建立於 [!DNL Marketo Measure] 包含16個字元的套件。 不幸的是，變更欄位的字元限制需要取代現有欄位並建立新欄位。 「接觸點型別」的值是「活動型別」，也設定在「媒體」欄位中。

**為什麼我的自訂活動型別沒有出現在可用活動清單中？**

我們僅顯示「已核准」自訂活動型別，不會顯示「草稿」或「已核准草稿」。

**如何決定要為哪些活動型別產生接觸點？**

雖然您可以建立的活動型別數目沒有限制，我們通常建議不要超過5個活動型別。 判斷哪些行銷活動足夠相關以成為接觸點歷程的一部分需要時間。 例如，「取消訂閱電子郵件」可能不是要追蹤的重要接觸點，但包含其他篩選器的「按一下電子郵件」可能很好。 這因每個組織和每個團隊而異，因此我們建議您與團隊合作，一起腦力激盪最佳方法。

**我的瀏覽器名稱為何遭到截斷？**

此 [!DNL Marketo Measure] 瀏覽器名稱的硬性限製為20個字元，不過我們從Marketo取得的使用者代理程式值往往是較長的字串。

BrowserInfo.Name\
BrowserInfo.Version\
PlatformInfo.Name\
PlatformInfo.Version
