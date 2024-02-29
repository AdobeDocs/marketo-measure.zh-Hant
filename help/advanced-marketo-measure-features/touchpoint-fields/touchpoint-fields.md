---
unique-page-id: 37355835
description: 接觸點欄位 —  [!DNL Marketo Measure]
title: 接觸點欄位
exl-id: d6c2bd60-5341-4a52-939a-942afc093306
feature: Touchpoints
source-git-commit: 518a984b0d8d640290bd9b637221fcdc0948e5b9
workflow-type: tm+mt
source-wordcount: '1945'
ht-degree: 0%

---

# 接觸點欄位 {#touchpoint-fields}

過去，當客戶使用 [!DNL Marketo Measure] 在我們沒有直接標籤整合的情況下，我們的客戶成功團隊會教育客戶如何適當地標籤他們的登陸頁面，以便他們使用正確的UTM格式，並且我們可以解析他們的廣告。 其中部分客戶不使用UTM，而是使用自己的標籤引數，這表示使用具備以下功能的新標籤結構來編輯其所有廣告網路中的所有登入頁面可能相當費時 [!DNL Marketo Measure] 強制執行。 為了適應它們的標籤結構，我們現在接受可以使用我們的規則定義對應的自訂引數。 目標是要因應客戶對其自訂追蹤引數的使用方式，因此我們不需要要求他們變更其URL結構。

>[!AVAILABILITY]
>
>現在可於第2級與第3級中完整細分。

>[!NOTE]
>
>這是進階功能，僅由Professional Services設定。

## 啟用功能 {#enabling-the-feature}

從 [!DNL Marketo Measure] 設定功能表，導覽至「接觸點欄位」頁面。 從那裡，您可以透過選取 **是** 在 **啟用計算欄位**. 啟用後，您就可以自由建立接觸點欄位。

![](assets/one.png)

## 操作說明 {#how-to}

若要建立計算欄位，請記住，使用者可執行三種不同的動作：擷取、對應至和串連。 這些也稱為定義計算欄位的運運算元。

擷取

此 [!UICONTROL extracts] 運運算元從另一個位置提取欄位的值，例如：促銷活動欄位、潛在客戶欄位，或是在更進階的使用案例中， [從登入頁面擷取自訂引數](https://docs.google.com/document/d/1NRViyCsXvPKbCTfGW32Yi2vWBjMDRF7bzkzKj9s2DDA/edit?ts=5e20b482#heading=h.xxwtissvw4){target="_blank"}. It then places it onto a Touchpoint Field (See [Maps To Example](https://docs.google.com/document/d/1NRViyCsXvPKbCTfGW32Yi2vWBjMDRF7bzkzKj9s2DDA/edit?ts=5e20b482#heading=h.xxwtissvw4){target="_blank"} #2)。

**範例#1**

聯絡人上有自訂欄位campaign_source__c，客戶想將其放置到接觸點以進行報告。 您可以定義規則以建立名為「促銷活動來源」的計算欄位，並將值拖放至該欄位。

目標：使用自訂欄位的值，並將其放在接觸點物件上，以更輕鬆地進行報告。

* 建立計算欄位並標示為「促銷活動來源」
* 從搜尋Contact.Campaign_Source__c欄位開始定義規則
* 使用運運算元「extracts」，因為我們需要從引數中提取值
* 若要從欄位中擷取完整字串，我們會使用運算式「(」。&#42;)」

   * **(** 標籤擷取的開始
   * **)** 標籤擷取的結尾
   * **.&#42;** 會告訴我們正在擷取完整的字串

![](assets/two.png)

**範例#2**

此功能啟用的常見使用案例是從URL字串的自訂引數提取值。 如果您使用UTM以外的引數，但想要將值剖析至接觸點欄位，這會很有用。

**連結：** `https://www.adobe.com/blog/marketing-revenue-reporting-overview?promo=5OFF` 或 `https://www.adobe.com/blog/marketing-revenue-reporting-overview?promo=25OFF`.\
**目標：** 建立名為「折扣代碼」的自訂欄位，並捨棄傳入的值「5OFF」或「25OFF」。

* 建立計算欄位並加上標籤「折扣代碼」
* 從搜尋Touchpoint.Session.LandingPage欄位開始定義規則
* 使用運運算元「extracts」，因為我們需要從引數中提取值
* 若要擷取促銷的值，我們會將該值定義為「promo=(\w+)」

   * **(** 標籤擷取的開始
   * **)** 標籤擷取的結尾
   * **\w** 會告訴我們正在擷取包含0-9的「單字」
   * **+** 將會擷取引數的完整值，而且字元數沒有限制
   * 請注意，您使用的是正斜線，而不是反斜線

![](assets/three.png)

**範例#3**

讓我們嘗試擷取追蹤程式碼的類似範例，例如： `https://www.adobe.com/blog/marketing-revenue-reporting-overview?cid=123456`.

**目標：** 建立計算欄位，並使用cid引數的值標示為「Adobe Campaign Id」。

* 建立計算欄位並加上標籤「Adobe Campaign Id」
* 從搜尋Touchpoint.Session.LandingPage欄位開始定義規則
* 使用運運算元「extracts」，因為我們需要從引數中提取值
* 若要擷取「123456」值，我們會將該值定義為「cid=(\d{6})」

   * **(** 標籤擷取的開始
   * **)** 標籤擷取的結尾
   * **\d** 會告訴我們正在擷取「數字」
   * **{6}** 是我們擷取的字元數

![](assets/four.png)

**範例#4**

由於您的登入頁面愈來愈複雜，且您有多個追蹤引數，因此您可能需要建立多個接觸點欄位，並多次擷取值，例如：
`https://www.adobe.com/blog/marketing-revenue-reporting-overview?trackID=123456&country=US&campaign_ID=7890`.

**目標：** 使用引數中的個別值，為「目標國家/地區」和「自訂促銷活動ID」建立多個計算欄位。

* 建立計算欄位並標示為「目標國家/地區」
* 從搜尋Touchpoint.Session.LandingPage欄位開始定義規則
* 使用運運算元「extracts」，因為我們需要從引數中提取值
* 若要擷取「美國」值，我們會將該值定義為「country=(\w{2})」

   * **(** 標籤擷取的開始
   * **)** 標籤擷取的結尾
   * **\w** 告訴我們正在擷取「單字」
   * **{2}** 是我們擷取的字元數

* 建立計算欄位並加上標籤「自訂行銷活動Id」
* 從搜尋Touchpoint.Session.LandingPage欄位開始定義規則
* 使用運運算元「extracts」，因為我們需要從引數中提取值
* 若要擷取「123456」值，我們會將該值定義為「campaign_ID=(\d{6})」

   * **(** 標籤擷取的開始
   * **)** 標籤擷取的結尾
   * **\d** 會告訴我們正在擷取「數字」
   * **{6}** 是我們擷取的字元數

![](assets/five.png)

**將對應至**

此 [!UICONTROL maps to] operator會建立需要轉譯或分組為其他值的值表。 這通常採取鍵值的形式，其中程式碼代表好記的名稱，需要對應到該好記名稱。

**範例#1**

您針對跨多個管道執行的「夏季促銷活動結束」和「黑色星期五」促銷活動所建立的行銷活動數。 除了其他可能的值外，您想要建立名為「方案」的計算欄位，並將任何具有「夏季促銷活動結束」或「黑色星期五促銷活動」的接觸點對應到「方案」值，例如「促銷活動」。

![](assets/six.png)

**範例#2**

現在我們已瞭解如何擷取並對應至欄位，接下來讓我們合併這些動作，以先從引數擷取值，然後將其對應至更好記的名稱。 讓我們從這個登陸頁面開始： `https://www.adobe.com/blog/marketing-revenue-reporting-overview?BZ=04-01-09-03-10`.

**目標：** 建立多個計算欄位，其中第一個數字對應至區域，第二個數字對應至產品，第三個對應至方案，第四個對應至角色，第五個對應至媒體平台。 然後，將數值對應至「易記名稱」。

* 建立計算欄位並標示為「區域」
* 從搜尋Touchpoint.Session.LandingPage欄位開始定義規則
* 使用運運算元&quot;[!UICONTROL extracts]」因為我們需要從引數中取出值
* 若要擷取「04」值，我們會將該值定義為「BZ=(\d{2})-\d{2}-\d{2}-\d{2}-\d{2}-\d{2}」

   * **(** 標籤擷取的開始

      * 請注意，由於我們僅擷取4，因此只有第一個數字有左括弧
   * **)** 標籤擷取的結尾

      * 請注意，由於我們僅擷取4，因此只有第一個數字有右括弧
   * **\d** 會告訴我們正在擷取「數字」
   * **{2}** 是我們擷取的字元數



* 按一下 [!UICONTROL Save]. 您必須先儲存新欄位，才能用於下一個規則！
* 接下來，我們要將第一個數字的所有可能值對應到其易記名稱
* 建立計算欄位並加上標籤「Region_Name」
* 從搜尋擷取的欄位開始，以定義規則。 在這種情況下， [!DNL Touchpoint.Region]
* 使用運運算元&quot;[!UICONTROL maps to]」因為我們想要為每個數字建立與其值的對應
* 您會看到一個表格，其中列出每個對應。 最後，看起來會像這樣：
* 根據對應和上述URL，使用此登陸頁面的接觸點「Region_Value」將是「EMEA」
* 對其餘4組數字重複擷取和對應

   * 若要擷取01，您可將值定義為&quot;BZ=\d{2}-**(\d{2})**-\d{2}-\d{2}-\d{2}」
   * 若要擷取09，您可將值定義為&quot;BZ=\d{2}-\d{2}-**(\d{2})**-\d{2}-\d{2}」
   * 若要擷取03，您可將值定義為&quot;BZ=\d{2}-\d{2}-\d{2}-**(\d{2})**-\d{2}」
   * 若要擷取10，您可將值定義為&quot;BZ=\d{2}-\d{2}-\d{2}-\d{2}-\d{2}-**(\d{2})**&quot;

![](assets/seven.png)

**串連**

此 [!UICONTROL concatenates] 運運算元將多個欄位的值結合為單一欄位。 這對於建立可跨不同欄位提取資料的自訂值很有用，以便

**範例#1**

Segment__c和Grade__c的Opportunity物件上有個別欄位，使用者想將它們合併到接觸點物件上的單一欄位以進行報告。 串連欄位後，您會看到Enterprise_A或Mid-Market_B之類的值。

![](assets/eight.png)

## 接觸點欄位和區段 {#touchpoint-fields-and-segments}

現在，URL中的值已剖析並存在於接觸點上，您將會在任何使用接觸點欄位的地方看到新欄位，例如建立區段或定義接觸點刪除規則。

此產品版本提供使用接觸點欄位建立區段的功能。 之前無法使用接觸點欄位來建置區段。

![](assets/nine.png)

為了更輕鬆建立區段，現在可以從建立的接觸點欄位建立動態區段。 例如，如果您建立了剖析地理區域的接觸點欄位，而非針對每個可能區域建立區段，您可以設定一個區段，而我們會為每個例項建立區段，此時會出現新值。 如果屬性（例如郵遞區號）需要剖析並作為區段使用，這會非常有用！

您的設定看起來會類似於下面的熒幕擷圖。 「區段名稱」會使用大括弧以動態拉入接觸點欄位值，藉此搜尋您的欄位。

![](assets/ten.png)

規則會參考相同的接觸點欄位，並搜尋「不等於null」的值。

![](assets/eleven.png)

## 常見問題集 {#faq}

**我們可以建立的接觸點欄位數量是否有上限？**

有100個欄位的限制。

**我未在挑選清單中看到我剛才建立的新接觸點欄位。 這個檔案在哪裡？**

建立規則後，別忘了儲存規則。 如果您沒有看到新欄位，請檢查您是否儲存。 您必須先儲存新欄位，才能用於下一個規則。

>[!NOTE]
>
>由於複雜程度，使用「對應」運運算元的接觸點欄位無法用於其他接觸點欄位。

**使用哪個運算式從單一登陸頁面擷取多個引數？**

就像在擷取範例#4位中一樣，您需要建立多個欄位來擷取每個引數。 因此，如果您有五個不同的值，您將建立五個接觸點欄位來擷取每個值。

**為什麼我在「 」中看不到新欄位 [!DNL Marketo Measure] 綱要？**

需要執行額外的工作，才能在中公開新欄位 [!DNL Marketo Measure] Data Warehouse結構描述。 目前，欄位會透過設定和設定公開，因此您可以在建立區段或建立接觸點刪除規則時使用接觸點欄位。

**如何驗證我的擷取運算式是否有效並提取正確的值？**

有一個線上工具([[!DNL https]：//regex101.com/](https://regex101.com/){target="_blank"})來執行並測試運算式。 如果運算式有效，則顯示綠色，如果無效則顯示紅色。 此外， [!UICONTROL explanation] 右上方的方塊很有幫助，會告訴您正在擷取的內容。

![](assets/twelve.png)

![](assets/thirteen.png)
