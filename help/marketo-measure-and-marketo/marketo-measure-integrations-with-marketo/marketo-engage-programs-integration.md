---
unique-page-id: 42762729
description: '[!DNL Marketo Engage]方案整合 —  [!DNL Marketo Measure]'
title: '[!DNL Marketo Engage]個計畫整合'
exl-id: c26087e3-d821-4fe7-bacd-eeaa1530a4b0
feature: Integration
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '1249'
ht-degree: 0%

---

# [!DNL Marketo Engage]個方案整合 {#marketo-engage-programs-integration}

透過[!DNL Marketo Measure]與[!DNL Marketo Engage]計畫的整合，我們的客戶可以開始從Marketo計畫會員資格建立歸因追蹤的接觸點。 此功能可讓行銷人員從電子郵件或參與方案中開始追蹤方案會籍，這些方案在[!DNL Marketo Measure] JavaScript看不到且應在歸因歷程中測量。

## 可用性 {#availability}

所有階層。

## 需求 {#requirements}

* 生產Marketo執行個體
* Production Salesforce或Microsoft Dynamics例項
* 任何付費的[!DNL Marketo Measure]訂閱
* Marketo人員同步已啟用（[!DNL Marketo Measure]設定）
* 已啟用Marketo程式（[!DNL Marketo Measure]設定）

## 設定 {#setup}

**規則**

1. 若要開始在Marketo程式中設定規則，請瀏覽至&#x200B;**[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL Programs]**。 按一下&#x200B;**+**&#x200B;圖示以開始建立您的第一個規則。

   ![](assets/one.png)

   ![](assets/two.png)

1. 如果有助於追蹤規則，您可以選擇設定規則名稱。 您首先會從計畫和計畫成員資格欄位清單中選取要定義規則的欄位。 選取要檢查的運運算元和預期值，以繼續建立規則。

   ![](assets/three.png)

1. 在同一方塊內新增另一個陳述式，以在規則中設定「and」條件，或按一下方塊外的+圖示以設定「or」陳述式。

   ![](assets/four.png)

1. 選擇用來對應至接觸點日期的日期或日期/時間欄位。 若要檢視Marketo中可用的值清單，請輸入花括弧`{`，我們就會顯示可用的欄位。

   ![](assets/five.png)

   >[!NOTE]
   >
   >如果您的規則想要擷取活動日期，或方案成員達到特定狀態的日期，您將需要利用「[!DNL Marketo Engage]活動整合」，並為「進度變更狀態」活動型別設定規則。

   ![](assets/six.png)

您完成的規則應該如下所示：

## 測試 {#test}

建立一些規則後，您可能想要測試該規則，以驗證您的陳述式是否符合您的程式。

1. 若要執行測試，請按一下如下所示的&#x200B;**[!UICONTROL TEST]**&#x200B;按鈕。

   ![](assets/seven.png)

1. 強制回應視窗會出現，您可在其中輸入來自Marketo的方案ID。

   ![](assets/eight.png)

   一旦您輸入ID並按一下[!UICONTROL Test]按鈕，我們的規則引擎就會逐一檢視每個規則，並判斷程式是否符合任何規則。 在下列範例中，您可以看到名為[!DNL Marketo Measure]電子書的Program 1002有5個Program成員，而且因為顯示的規則而符合資格。

   規則會在具有5000個成員的樣本大小上執行。 如果您的程式包含超過5000個成員，我們可能不會檢查所有成員的相容性。 此工具僅作為檢查規則是否正確建構的一種方式。

   ![](assets/nine.png)

   您可以按一下「成員計數」，檢視符合方案資格的Marketo人員ID清單。

   ![](assets/ten.png)

## 頻道對應 {#channel-mapping}

從Marketo方案管道清單中，您要將值對應到您在「設定」中建立的[!DNL Marketo Measure]自訂行銷管道。 這些計畫產生的任何接觸點都會繼承您在此處選取的管道和子管道名稱。

1. 首先瀏覽至&#x200B;**[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL Offline Channels]**。

1. 在上方，您可以選擇對應至您的CRM Campaign型別，然後在下方，您會看到Marketo方案管道的選項。

1. 首先，選取應對應至值的管道，然後選擇性選取子管道。 完成後，請按一下底部的&#x200B;**[!UICONTROL Save]**。

   ![](assets/eleven.png)

## 計畫成本 {#program-costs}

透過Marketo程式的資料匯入，成本會自動從期間成本下載，Marketo中的報告成本會在整個指派的月份中分發。 例如，如果在2021年1月報告$1000，則會將$1000分割為31天。 可以在[!DNL Marketo Measure Discover]中找到成本。

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

由於與Marketo整合[!DNL Marketo Measure]，[!DNL Marketo Measure] Cookie ID現在也已對應並與[!DNL Marketo Munchkin Id]同步。 這有助於縮短將匿名首次接觸歸因於網路工作階段的差距，而非將FT和LC接觸均歸因於Marketo活動。 想像一下這種情況：

標籤在[!DNL Facebook]廣告上的點按並登陸wayneenterprises.com，在那裡他被識別為[!DNL Marketo Measure] ID 123和[!DNL Marketo Munchkin Id] 456。 沒有表單填寫。

Wayne企業行銷團隊會傳送電子郵件爆炸訊息給特定目標銷售機會，其中一個是`mark@email.com`。

`mark@email.com`會收到電子郵件，然後點進並登陸wayneenterprises.com。 這會變成使用相同Cookie Id對`wayneenterprise.com`進行`mark@email.com's`次的第二次造訪，但沒有任何表單填入，因此對於[!DNL Marketo Measure]，他們仍然是匿名訪客。

Wayne Enterprises行銷團隊會建立Marketo活動規則，以產生「按一下電子郵件」活動型別的接觸點。

今天的實作將會從「按一下電子郵件」活動型別中的Marketo活動，為`mark@email.com`建立單一FT和LC接觸點。

透過此Cookie對應增強功能，FT將返回並取得對[!DNL Facebook]廣告的評分，而LC將取得對電子郵件的評分。

>[!NOTE]
>
>有了Cookie對應行為，您可能會發現一些來自網頁造訪的LC接觸點。 潛在客戶出現在Marketo中時可能沒有任何相關聯的活動，然後[!DNL Marketo Measure]下載該潛在客戶，與相關聯的Cookie相符，然後將其追蹤到最近的網頁工作階段，即使沒有建立該潛在客戶的表單活動也是如此。

## 常見問題集 {#faq}

**如何將接觸點日期設定為進度日期，或我的程式成員發生狀態變更的日期？**

如果您的規則想要擷取活動日期，或方案成員達到特定狀態的日期，您將需要利用「[!DNL Marketo Engage]活動整合」，並為「進度變更狀態」活動型別設定規則。 否則，[!DNL Marketo Engage]方案整合只會提供成員資格日期，這是將Marketo人員引進方案的第一個日期，即使存在多種狀態。

**我可以取得接觸點日期的日期選項選擇清單嗎？**

若要觸發自動完成，先在文字欄位中輸入大括弧`{`，然後會顯示可用的欄位。

**如果我建立Marketo方案規則並且也有CRM Campaign規則，它們會計算兩次嗎？**

這取決於您的規則定義，但可能會。 您將需要評估規則集，這樣就不會有涵蓋方案與行銷活動的規則，因為我們不會針對類似的成員資格進行重複資料刪除或偵測。 一個可能的解決方案是，如果您希望Marketo成為您的單一信任來源，則將您的行銷活動規則複製到計畫中，然後移除行銷活動規則。 另一個選項是在規則中新增「CreatedOn」或「CreatedDate」條件，讓特定日期前的規則使用Campaign規則，而特定日期後的規則則使用Program規則。 有很多變通辦法，但需要一些規劃和協調。

**Marketo的程式成員資格自訂欄位是否可供定義？**

由於技術限制，我們目前無法支援計畫會員資格自訂欄位。 這些欄位一旦透過其他Marketo API提供使用，我們就會看到它們並供您使用。

**我如何知道要使用方案或活動？**

[!DNL Marketo Engage]方案整合是根據某人是否為方案的方案成員來產生接觸點的簡單方式。 如果您有興趣根據人員變更至特定方案狀態的時間來定義規則，則[!DNL Marketo Engage]活動整合將是您想要的設定，尤其是「變更進度中的狀態」活動型別。
