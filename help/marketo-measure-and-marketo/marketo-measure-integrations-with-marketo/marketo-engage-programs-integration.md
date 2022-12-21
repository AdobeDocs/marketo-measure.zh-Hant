---
unique-page-id: 42762729
description: '"[!DNL Marketo Engage] 計畫整合 —  [!DNL Marketo Measure]  — 產品檔案」'
title: '"[!DNL Marketo Engage] 計畫整合」'
exl-id: c26087e3-d821-4fe7-bacd-eeaa1530a4b0
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '1247'
ht-degree: 0%

---

# [!DNL Marketo Engage] 計畫整合 {#marketo-engage-programs-integration}

透過 [!DNL Marketo Measure] 整合 [!DNL Marketo Engage] 我們的客戶可以透過Marketo計畫會籍，開始建立歸因追蹤的接觸點。 此功能可讓行銷人員開始從未看到的電子郵件或參與方案追蹤方案成員資格 [!DNL Marketo Measure] javascript和應該在歸因歷程中測量。

## 可用性 {#availability}

所有層。

## 需求 {#requirements}

* 生產Marketo例項
* 生產Salesforce或Microsoft Dynamics例項
* 任何已付 [!DNL Marketo Measure] 訂閱
* Marketo People Sync(啟用[!DNL Marketo Measure] 設定)
* Marketo計畫已啟用([!DNL Marketo Measure] 設定)

## 設定 {#setup}

**規則**

1. 若要開始設定Marketo方案的規則，請導覽至 **[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL Programs]**. 按一下 **+** 圖示來開始建立第一個規則。

   ![](assets/one.png)

   ![](assets/two.png)

1. 如果有助於追蹤規則，您可以選擇設定規則的名稱。 您將首先從「方案」(Program)和「方案成員資格」(Program Members)欄位清單中選擇欄位以定義規則。 選取要檢查的運算子和預期值，以繼續建立規則。

   ![](assets/three.png)

1. 在相同方塊內新增其他陳述式，以在規則中設定「and」條件，或按一下方塊外的+圖示以設定「or」陳述式。

   ![](assets/four.png)

1. 選擇應使用哪個日期或日期/時間欄位來對應至接觸點日期。 若要查看Marketo中可用的值清單，請輸入大括弧 `{` 我們會顯示可用欄位。

   ![](assets/five.png)

   >[!NOTE]
   >
   >如果您的規則想要擷取活動日期或方案成員達到特定狀態的日期，您將要使用 [!DNL Marketo Engage] 活動整合，並設定「晉升中的變更狀態」活動類型的規則。

   ![](assets/six.png)

您已完成的規則應如下所示：

## 測試 {#test}

建立一些規則後，您可能希望對其進行測試，以驗證您的語句與您的程式匹配。

1. 若要執行測試，請按一下 **[!UICONTROL TEST]** 按鈕，如下所示。

   ![](assets/seven.png)

1. 強制回應隨即出現，您可在其中輸入Marketo的方案ID。

   ![](assets/eight.png)

   輸入ID並按一下 [!UICONTROL Test] 按鈕，我們的規則引擎將逐一檢查每個規則，並判斷程式是否符合任何規則。 在以下範例中，您會看到Program 1002，稱為 [!DNL Marketo Measure] Ebook有5個方案成員，因為顯示的規則而符合條件。

   規則以5000個成員的樣本大小運行。 如果您的程式包含5000多個成員，我們可能不會檢查所有成員的相容性。 此工具只是用來檢查規則是否正確建構的方法。

   ![](assets/nine.png)

   您可以按一下成員計數，查看方案中符合資格的Marketo People ID清單。

   ![](assets/ten.png)

## 通道對應 {#channel-mapping}

從Marketo計畫管道清單中，您會將值對應至 [!DNL Marketo Measure] 您在「設定」中建立的自訂行銷管道。 這些程式產生的任何接觸點都會繼承您在此處選取的管道和子管道名稱。

1. 首先，導覽至 **[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL Offline Channels]**.

1. 在頂端，您可以選擇對應至您的CRM促銷活動類型，然後在下方，您會看到Marketo計畫管道的選項。

1. 首先選取應對應至值的管道，然後選擇子管道。 完成後，按一下 **[!UICONTROL Save]** 在底部。

   ![](assets/eleven.png)

## 計畫成本 {#program-costs}

通過導入Marketo程式的資料，成本會自動從期間成本下載，而Marketo中報告的成本會在分配的月份中分配。 例如，如果2021年1月報告了$1000，則$1000會平分31天。 成本位於 [!DNL Marketo Measure Discover].

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
   <td>（透過API檢查方案是否仍存在）</td> 
  </tr> 
  <tr> 
   <td><p>名稱</p></td> 
   <td>名稱</td> 
  </tr> 
 </tbody> 
</table>

| biz_campaign_members | Marketo |
|---|---|
| ID | &quot;MarketoProgramMembership&quot;_ProgramId_Lead Id |
| 修改日期 | updatedAt |
| CREATED_DATE | membersingDate |
| LEAD_ID | Id（清單成員資格） |
| LEAD_EMAIL | 電子郵件（清單成員資格） |
| 狀態 | progressionStatus |
| HAS_RESPONSED | reacedStatus |
| CAMPAIGN_NAME | programName |
| CAMPAIGN_ID | programId |
| CAMPAIGN_TYPE | 頻道 |

## Cookie對應 {#cookie-mapping}

由於 [!DNL Marketo Measure] 與Marketo的整合， [!DNL Marketo Measure] Cookie ID現在也已對應並同步至 [!DNL Marketo Munchkin Id]. 這有助於縮小間隙，將匿名的首次接觸歸因於Web工作階段，而非將FT和LC接觸歸因於Marketo活動。 想像一下這種情景：

在 [!DNL Facebook] 在wayneenterprises.com上，他在網站上與 [!DNL Marketo Measure] Id 123和 [!DNL Marketo Munchkin Id] 456。 不會填表。

Wayne企業營銷團隊向特定目標線索發送電子郵件，其中一個是 `mark@email.com`.

`mark@email.com` 收到電子郵件，點進並登陸wayneenterprises.com。 這會變成 `mark@email.com's` 第二次瀏覽 `wayneenterprise.com` 使用相同的Cookie Id，但沒有表單填入，因此 [!DNL Marketo Measure]，仍為匿名訪客。

Wayne Enterprises Marketing團隊會建立Marketo活動規則，以產生「點按電子郵件」活動類型的接觸點。

今天的實作將為 `mark@email.com` 從「點擊電子郵件」活動類型的「Marketo活動」。

透過這項Cookie對應增強功能，英國《金融時報》將回頭獲得評分 [!DNL Facebook] 廣告和LC會被評為電子郵件。

>[!NOTE]
>
>有了Cookie對應行為，您可能會發現某些來自網站造訪的LC接觸點。 銷售機會可能出現在Marketo中，且沒有任何相關的活動，然後 [!DNL Marketo Measure] 已下載該lead，符合相關的cookie，然後追蹤到最新的web工作階段，即使沒有建立lead的表單活動亦然。

## 常見問題集 {#faq}

**如何將接觸點日期設定為進展日期，或狀態變更發生在方案成員的日期？**

如果您的規則想要擷取活動日期或方案成員達到特定狀態的日期，您將要使用 [!DNL Marketo Engage] 活動整合，並設定「晉升中的變更狀態」活動類型的規則。 否則， [!DNL Marketo Engage] 方案整合僅提供會員資格日期，即使存在多種狀態，也是將Marketo人員納入方案的第一個日期。

**我可以取得接觸點日期的日期選項選擇清單嗎？**

若要觸發自動完成，請從輸入大括弧開始 `{` 在文字欄位中，將顯示可用欄位。

**如果我建立Marketo計畫規則，並且也有CRM促銷活動規則，它們會計算兩次嗎？**

這取決於你的規則定義，但可能是。 您會想要評估規則集，以便沒有涵蓋方案和促銷活動的規則，因為我們不會刪除重複資料或偵測類似成員資格。 一個可能的解決方案是，如果您希望Marketo成為唯一的真相來源，請將您的促銷活動規則複製到方案，然後移除促銷活動規則。 另一個選項是在規則中新增「CreatedOn」或「CreatedDate」條件，讓特定日期之前的規則在特定日期之後使用Campaign規則，而規則在特定日期之後將使用Program規則。 有很多解決辦法，但需要一些規劃和協調。

**Marketo的方案成員資格自訂欄位可供定義嗎？**

由於技術限制，目前無法支援方案成員自訂欄位。 透過其他Marketo API取得這些欄位後，這些欄位將會公開給我們並供您使用。

**如何知道要使用方案還是活動？**

此 [!DNL Marketo Engage] 方案整合是根據人員是否為方案的方案成員而生成接觸點的簡單方法。 如果您想要根據人員變更為特定方案狀態的時間來定義規則，則 [!DNL Marketo Engage] 活動整合將是您需要的設定，尤其是「晉升中的變更狀態」活動類型。
