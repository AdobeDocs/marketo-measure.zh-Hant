---
unique-page-id: 42762729
description: "[!DNL Marketo Engage] 計畫整合 —  [!DNL Marketo Measure]"
title: '"[!DNL Marketo Engage] 計畫整合」'
exl-id: c26087e3-d821-4fe7-bacd-eeaa1530a4b0
feature: Integration
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '1249'
ht-degree: 0%

---

# [!DNL Marketo Engage] 程式整合 {#marketo-engage-programs-integration}

透過 [!DNL Marketo Measure] 與整合 [!DNL Marketo Engage] 計畫，我們的客戶可以開始從Marketo計畫會員建立歸因追蹤的接觸點。 此功能可讓行銷人員從電子郵件或參與方案中開始追蹤看不到的成員 [!DNL Marketo Measure] javascript和應在歸因歷程中測量。

## 可用性 {#availability}

所有階層。

## 需求 {#requirements}

* 生產Marketo執行個體
* Production Salesforce或Microsoft Dynamics例項
* 任何付費 [!DNL Marketo Measure] 訂閱
* Marketo人員同步已啟用([!DNL Marketo Measure] 設定)
* Marketo程式已啟用([!DNL Marketo Measure] 設定)

## 設定 {#setup}

**規則**

1. 若要開始在Marketo程式中設定規則，請導覽至 **[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL Programs]**. 按一下 **+** 圖示以開始建立您的第一個規則。

   ![](assets/one.png)

   ![](assets/two.png)

1. 如果有助於追蹤規則，您可以選擇設定規則名稱。 您首先會從計畫和計畫成員資格欄位清單中選取要定義規則的欄位。 選取要檢查的運運算元和預期值，以繼續建立規則。

   ![](assets/three.png)

1. 在同一方塊內新增另一個陳述式，以在規則中設定「and」條件，或按一下方塊外的+圖示以設定「or」陳述式。

   ![](assets/four.png)

1. 選擇用來對應至接觸點日期的日期或日期/時間欄位。 若要檢視Marketo可用的值清單，請輸入大括弧 `{` 我們將顯示可用的欄位。

   ![](assets/five.png)

   >[!NOTE]
   >
   >如果您的規則想要擷取「活動日期」，或「方案成員」達到特定狀態的日期，您將需要利用 [!DNL Marketo Engage] 活動整合，並設定「進度變更狀態」活動型別的規則。

   ![](assets/six.png)

您完成的規則應該如下所示：

## 測試 {#test}

建立一些規則後，您可能想要測試該規則，以驗證您的陳述式是否符合您的程式。

1. 若要執行測試，請按一下 **[!UICONTROL TEST]** 按鈕，如下所示。

   ![](assets/seven.png)

1. 強制回應視窗會出現，您可在其中輸入來自Marketo的方案ID。

   ![](assets/eight.png)

   輸入ID並按一下 [!UICONTROL Test] 按鈕，我們的規則引擎將瀏覽每個規則，並判斷程式是否符合任何規則。 在下列範例中，您可以看到方案1002，稱為 [!DNL Marketo Measure] E-book有5個「方案成員」，而且因為顯示的規則而符合資格。

   規則會在具有5000個成員的樣本大小上執行。 如果您的程式包含超過5000個成員，我們可能不會檢查所有成員的相容性。 此工具僅作為檢查規則是否正確建構的一種方式。

   ![](assets/nine.png)

   您可以按一下「成員計數」，檢視符合方案資格的Marketo人員ID清單。

   ![](assets/ten.png)

## 頻道對應 {#channel-mapping}

從Marketo方案管道清單中，您將值對應至 [!DNL Marketo Measure] 您已在「設定」中建立的自訂行銷管道。 這些計畫產生的任何接觸點都會繼承您在此處選取的管道和子管道名稱。

1. 首先，瀏覽至 **[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL Offline Channels]**.

1. 在上方，您可以選擇對應至您的CRM Campaign型別，然後在下方，您會看到Marketo方案管道的選項。

1. 首先，選取應對應至值的管道，然後選擇性選取子管道。 完成後，按一下 **[!UICONTROL Save]** 在底部。

   ![](assets/eleven.png)

## 計畫成本 {#program-costs}

透過Marketo程式的資料匯入，成本會自動從期間成本下載，Marketo中的報告成本會在整個指派的月份中分發。 例如，如果在2021年1月報告$1000，則會將$1000分割為31天。 成本可在下列位置找到： [!DNL Marketo Measure Discover].

## 運作方式 {#how-it-works}

**欄位對應**

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th>biz_ad_campaigns</th> 
   <th>Marketo</th> 
  </tr> 
  <tr> 
   <td>ID</td> 
   <td>ID</td> 
  </tr> 
  <tr> 
   <td>IS_DELETED</td> 
   <td>（透過API檢查程式是否仍然存在）</td> 
  </tr> 
  <tr> 
   <td><p>名稱</p></td> 
   <td>名稱</td> 
  </tr> 
 </tbody> 
</table>

| biz_campaign_members | Marketo |
|---|---|
| ID | 「MarketoProgramMembership」_ProgramId_Lead Id |
| MODIFIED_DATE | 更新時間 |
| CREATED_DATE | membershipDate |
| 銷售機會ID | Id （清單成員資格） |
| 潛在客戶電子郵件 | 電子郵件（清單成員資格） |
| 狀態 | progressionstatus |
| HAS_RESPONDED | 到達狀態 |
| 促銷活動名稱 | programName |
| CAMPAIGN_ID | programId |
| 行銷活動型別 | 頻道 |

## Cookie對應 {#cookie-mapping}

由於 [!DNL Marketo Measure] 與Marketo整合， [!DNL Marketo Measure] Cookie ID現在也已對應並與 [!DNL Marketo Munchkin Id]. 這有助於縮短將匿名首次接觸歸因於網路工作階段的差距，而非將FT和LC接觸均歸因於Marketo活動。 想像一下這種情況：

標籤上的點按次數 [!DNL Facebook] 廣告並登陸wayneenterprises.com，在那裡他受到了 [!DNL Marketo Measure] Id 123和 [!DNL Marketo Munchkin Id] 456. 沒有表單填寫。

Wayne企業行銷團隊會傳送電子郵件爆炸訊息給特定的目標銷售機會，其中一個是 `mark@email.com`.

`mark@email.com` 會收到電子郵件，然後點進並登陸wayneenterprises.com。 這會變成 `mark@email.com's` 第二次造訪 `wayneenterprise.com` 具有相同Cookie ID，但表單沒有填入，因此 [!DNL Marketo Measure]，仍為匿名訪客。

Wayne Enterprises行銷團隊會建立Marketo活動規則，以產生「按一下電子郵件」活動型別的接觸點。

今天的實作將為建立單一FT和LC接觸點 `mark@email.com` 從Marketo活動中的「按一下電子郵件」活動型別。

透過這項Cookie對應增強功能，FT將能回過頭來獲得 [!DNL Facebook] 廣告和LC將記入電子郵件的貸方。

>[!NOTE]
>
>有了Cookie對應行為，您可能會發現一些來自網頁造訪的LC接觸點。 潛在客戶出現在Marketo中時可能會沒有任何相關的活動，然後 [!DNL Marketo Measure] 下載該銷售機會、符合關聯的Cookie，然後將其追蹤到最近的網路工作階段，即使沒有建立該銷售機會的表單活動亦然。

## 常見問題集 {#faq}

**如何將接觸點日期設為進度日期，或我的方案成員發生狀態變更的日期？**

如果您的規則想要擷取「活動日期」，或「方案成員」達到特定狀態的日期，您將需要利用 [!DNL Marketo Engage] 活動整合，並設定「進度變更狀態」活動型別的規則。 否則， [!DNL Marketo Engage] 方案整合只會提供成員資格日期，這是將Marketo人員引進方案的第一個日期，即使存在多個狀態亦然。

**我可以取得接觸點日期的日期選項選擇清單嗎？**

若要觸發自動完成，請先輸入大括弧 `{` 在文字欄位中，則會顯示可用的欄位。

**如果我建立Marketo方案規則也有CRM Campaign規則，這些規則會計算兩次嗎？**

這取決於您的規則定義，但可能會。 您將需要評估規則集，這樣就不會有涵蓋方案與行銷活動的規則，因為我們不會針對類似的成員資格進行重複資料刪除或偵測。 一個可能的解決方案是，如果您希望Marketo成為您的單一信任來源，則將您的行銷活動規則複製到計畫中，然後移除行銷活動規則。 另一個選項是在規則中新增「CreatedOn」或「CreatedDate」條件，讓特定日期前的規則使用Campaign規則，而特定日期後的規則則使用Program規則。 有很多變通辦法，但需要一些規劃和協調。

**Marketo的計畫會籍自訂欄位是否可供定義？**

由於技術限制，我們目前無法支援計畫會員資格自訂欄位。 這些欄位一旦透過其他Marketo API提供使用，我們就會看到它們並供您使用。

**我如何知道要使用方案或活動？**

此 [!DNL Marketo Engage] 方案整合是根據某人是否為方案的方案成員來產生接觸點的簡單方法。 如果您想要根據人員變更至特定計畫狀態的時間來定義規則，請 [!DNL Marketo Engage] 活動整合將是您想要的設定，尤其是「進度變更狀態」活動型別。
