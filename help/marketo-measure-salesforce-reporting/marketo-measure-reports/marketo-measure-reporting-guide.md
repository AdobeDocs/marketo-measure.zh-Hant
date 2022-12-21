---
description: '"[!DNL Marketo Measure] 報表指南 —  [!DNL Marketo Measure]  — 產品檔案」'
title: '"[!DNL Marketo Measure] 報告指南」'
exl-id: 9b991f9e-c187-4b43-b0a8-8ed3e9a6056b
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '6392'
ht-degree: 0%

---

# [!DNL Marketo Measure] 報表指南 {#marketo-measure-reporting-guide}

>[!NOTE]
>
>您可能會看到指定「[!DNL Marketo Measure]「 」，但仍可在CRM中看到「Bizible」。 我們正致力更新該更新，品牌重塑將很快反映在您的CRM中。

在建立 [!DNL Marketo Measure] 報告，最重要的是確認 [!DNL Marketo Measure] 帳戶設定經過審核及設定，以確保報表中的資料準確無誤，且能反映您的業務特性。 此外，報表專案在遵循結構化程式時效果最佳。 賈斯汀·諾里斯， [!DNL Marketo Measure] 來自以下機構的權力使用者、宣傳者和合作夥伴 [佩爾庫托](https://perkuto.com/) 專業總結 [如何在 [!DNL Marketo Measure]](https://perkuto.com/blog/turning-attribution-data-into-actionable-insights/):

**建立目標**:「我們要問的第一個問題是『我們為什麼要衡量？ Lori Wizdo的 [Forrester Research](https://go.forrester.com/) 用一個 [Marketo網路講座](https://www.marketo.com/webinars/beyond-revenue-performance-real-kpis-of-b2b-marketing/). 據她說，「我們的措施是證明或驗證一項決策或營銷的價值，或是改善（流程改進）。」 我們補充說，來自良好衡量的洞察力也為行銷規劃程式提供投入和指引。

所以在你開始之前，必須明確你的目標，你要回答的問題，或者你要解決的問題。 你想講什麼故事？ 會因此做出哪些決定？ 這些基本面因素往往被考慮得不周全，導致所有參與者都感到沮喪。」

**報表設計**:「接下來，您需要設計報表，並決定報表所包含的特定維度、量度和資料集。 常見的體驗是為商務使用者提供他們想要的，只有讓他們仍覺得他們的需求未得到滿足。 這是因為商務使用者實際尋找的洞察力並非一律包含在其要求的報表中。 好的分析師（或MOPS上有分析師的人）會提出澄清問題、建立共同定義（「那麼，你真正指的是什麼？」），甚至勾勒出最終報告的視覺效果，以確保協調一致。 只有在那時，您才會建立報表，並知道您有一套可靠的要求。」

**報表建置**:「一旦你去建築，遇到路障或死衚衕的情況並不少見。 例如，您可能會發現您缺少必要的資料點，或您的物件沒有以您需要的方式連結。 為了解決這些問題，我也認為，了解報告「機器」中「機殼底下」發生的情況至關重要。 這種流利性將讓您能夠快速確定報告請求，並評估其是否可實現（如果不能實現，則更容易設計創意解決方案）。」

讓我們看看「帽子下」，更清楚地了解 [!DNL Marketo Measure] 歸因報表電腦執行。

## 採購員接觸點對象(CRM) {#buyer-touchpoint-objects-crm}

在最高層，根據兩個不同的購買者接觸點物件，有兩個報表類別：這些類別決定 [!DNL Marketo Measure] 要報告的資料：與 _個別_，或與 _商機_.

1. **購買者接觸點** (BT)/個人/參與總數

   * 常用於「漏斗頂端」(TOFU)量度，以及與 _個人_ (銷售機會、聯繫人、 [!DNL Marketo Measure] 人員)
   * BT可用來了解與 **人**，因為其中包含每個人員的完整接觸點歷史記錄。 提醒您，這些接觸點是在CRM中針對匿名的首次接觸、銷售機會建立接觸，以及您選擇從離線促銷活動或活動同步的任何後續表單提交或接觸點而建立。

1. **購買者歸因接觸點** (BAT)/機會/帳戶層級/收入

   * 常用於「漏斗中間和/或底部」（MOFU和BOFU）量度及與 _機會_.
   * BAT代表與 **商機** （通過Opportunity Contact Role或通過共用帳戶ID，具體取決於您的設定）。 與僅與人相關的BT不同，BAT也可以與 **收入**. 因此，您將使用BAT回答與機會相關的問題，包括已開啟或關閉的機會數，或已獲得的管道價值和收入。

>[!NOTE]
>
>BAT是從BT建立的。 基本上，追蹤會透過BT從個別層級開始。 在Account上建立Opportunity後，將引用同一帳戶下Contacts的所有BT，並有資格建立與Opportunity相關的BAT，因此您將根據您嘗試回答的問題使用一個或另一個：與「人員」量度（BT報告）相關的問題，或與「機會」量度（BAT報告）相關的問題

支援文章： [購買者接觸點與購買者歸因接觸點之間的差異](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md#configuration-and-setup)

## 購買者接觸點(BT) {#buyer-touchpoint-bt}

購買者接觸點(BT)是物件，用來追蹤某人與您的行銷資料之間的每個行銷互動。 每個個人的(銷售機會/聯絡人/[!DNL Marketo Measure] Person)歷程將由其相關BT代表。 在 [!DNL Marketo Measure]，個人的歷程包含：

1. 這個人是如何與我們的品牌互動的？ (首次接觸或 _FT_)
1. 此人是如何轉換/成為已知/成為銷售機會的？ (銷售機會建立或 _LC_)
1. 自成為銷售機會以來，此人還是如何與我們的品牌和行銷資料互動的？ (_PostLC_)

購買者接觸點可用來回答與 _人_ （「人員」由CRM內的Lead或Contact表示），例如Lead/Contact生成或贏取度量，而不是Opportunity相關度量。 例如：

* 哪些渠道提供的銷售機會最多？
* 建立新Lead的成本是多少？
* 我的銷售機會/聯絡人與哪些內容接洽？
* 特定標題、角色、角色的行銷故事是什麼？
* 哪些通道驅動MQL或其他Lead/Contact狀態？

主要是，公司需要知道，「我的銷售機會/聯繫人來自何處？」 在過去，系統會以單一、一維的值（例如「銷售機會來源」）來回應此問題。 不過，如上#1和#2中所述，我們知道Lead在成為Lead的過程中可以有多個接觸點。 「購買者接觸點」可讓我們深入了解代表銷售機會產生方式的兩個最重要互動：首次接觸和潛在客戶建立接觸。 購買者接觸點也 _多維度_ 這表示這些資料包含大量行銷資料，主要是人員來自何處（行銷管道），以及參與的人員（內容）。

此 [歸因模型](/help/introduction-to-marketo-measure/overview-resources/marketo-measure-attribution-models.md) 提供以人物為基礎之量度的最佳分析包括：

* **首次接觸** - 100%歸因歸因歸因於Lead的首次接觸(FT)
* **銷售機會建立**  — 銷售機會建立接觸(LC)的100%歸因評分
* **U形**  — 多點接觸，40%歸英國《金融時報》，40%歸信用證

<table> 
 <tbody>
  <tr>
   <td><img src="assets/bizible-reporting-guide-1.png"></td> 
   <td>U形模型旨在為任何「購買者接觸點」提供評分，這些接觸點概述銷售機會成為銷售機會的方式。 雖然這些銷售機會的後續接觸點也可回報以了解其他參與（貼文LC），但它們不是 <strong>銷售機會建立歷程</strong> 因此，它們在英國《金融時報》、LC或U形模型中沒有獲得任何歸因評分。<p>

&#42;最常見的U形歸因是FT和LC之間50/50均分。 如果銷售機會在與首次接觸相同的工作階段中轉換，則單一接觸點將同時代表FT和LC接觸點位置。 因此，100%的歸因會授予單一接觸點。</td>
</tr>
 </tbody>
</table>

這些模型著重於早期互動和漏斗參與的頂端。 U形歸因是建議的模型，因為它會影響FT和LC接觸點，確保將評分給予影響Lead建立的任何接觸。 不過，如果您想要更詳細地了解Lead歷程中的這些特定部分，則可從首次接觸和銷售機會建立接觸模型中獲得更多深入分析。

## 使用購買者接觸點(BT)的建議報表 {#recommended-reports-using-the-buyer-touchpoint-bt}

1. **銷售機會與購買者接觸點**

**1.1 |行銷管道新增銷售機會**

依欄位「行銷管道」匯總銷售機會的購買者接觸點資料，是最高層級的檢視，代表哪些管道/策略正在影響新銷售機會的建立。 圍繞「日期類型」=「建立日期」建構此報表，可確保在報表中建立「淨新銷售機會」（當銷售機會在您的CRM中建立時）的同類群組。

<table> 
 <tbody>
  <tr>
   <td>問題</td> 
   <td>哪些行銷管道影響Lead的建立？</td> 
  </tr>
  <tr>
   <td>報表類型</td> 
   <td>銷售機會和購買者接觸點(CRM)<br>
   量度：銷售機會([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>日期欄位/日期類型</td> 
   <td>銷售機會建立日期(CRM)/建立日期(Discover)</td> 
  </tr>
  <tr>
   <td>日期範圍</td> 
   <td><i>選擇所需日期範圍</i></td> 
  </tr>
  <tr>
   <td>群組/Dimension</td> 
   <td>行銷管道</td> 
  </tr>
  <tr>
   <td>最佳模型</td> 
   <td>首次接觸、銷售機會建立、 <strong>U形</strong><br>
   *加總CRM報表中的「計數」欄位（計數 — 首次接觸、計數 — 銷售機會建立、計數 — U形）</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>對於任何「具有採購員接觸點的銷售機會」報表類型，請從自訂名為「[!DNL Marketo Measure] 101 |按渠道銷售。 此報表是現成可用的，而且是如上表所述預先建立的絕佳沙箱，可根據更具體的報表需求快速自訂。

**1.2 |依促銷活動新增銷售機會（或更精細的分析）**

如需「行銷管道新增銷售機會」報表(1.1)中所匯總資料的更詳細分析，請在促銷活動層級新增其他摘要。 這不僅可讓您了解哪些「行銷管道」推動新銷售機會建立，更具體而言，這些管道中哪些促銷活動成效最佳：

<table> 
 <tbody>
  <tr>
   <td>問題</td> 
   <td>什麼 <i>行銷活動</i> 是否會影響Lead進而創造？</td> 
  </tr>
  <tr>
   <td>報表類型</td> 
   <td>銷售機會和購買者接觸點(CRM)<br>
   量度：銷售機會([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>日期欄位/日期類型</td> 
   <td>銷售機會建立日期(CRM)/建立日期(Discover)</td> 
  </tr>
  <tr>
   <td>日期範圍</td> 
   <td><i>選擇所需日期範圍</i></td> 
  </tr>
  <tr>
   <td>群組/Dimension</td> 
   <td>廣告促銷活動名稱(CRM)</td> 
  </tr>
  <tr>
   <td>最佳模型</td> 
   <td>首次接觸、銷售機會建立、 <strong>U形</strong><br>
   *加總CRM報表中的「計數」欄位（計數 — 首次接觸、計數 — 銷售機會建立、計數 — U形）</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>將報表與「購買者接觸點」物件中的其他可用欄位一起匯總，以取得更精細的分析。 若要這麼做，請設定其他群組(CRM)或維度(Discover)。 視管道（可能代表您的角色）而定，除了您希望獲得深入分析的促銷活動層級，可能會有其他詳細資訊。 讓我們深入探討「付費搜尋」，例如下表中的……

<table> 
 <tbody>
  <tr>
   <td>問題</td> 
   <td>什麼 <i>關鍵字</i> 是否會影響Lead進而創造？</td> 
  </tr>
  <tr>
   <td>報表類型</td> 
   <td>銷售機會和購買者接觸點(CRM)<br>
   量度：銷售機會([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>篩選器</td> 
   <td>行銷管道=付費搜尋</td> 
  </tr>
  <tr>
   <td>日期欄位/日期類型</td> 
   <td>銷售機會建立日期(CRM)/建立日期(Discover)</td> 
  </tr>
  <tr>
   <td>日期範圍</td> 
   <td><i>選擇所需日期範圍</i></td> 
  </tr>
  <tr>
   <td>群組/Dimension</td> 
   <td>關鍵字文字(CRM)/關鍵字(Discover)</td> 
  </tr>
  <tr>
   <td>最佳模型</td> 
   <td>首次接觸、銷售機會建立、 <strong>U形</strong><br>
   *加總CRM報表中的「計數」欄位（計數 — 首次接觸、計數 — 銷售機會建立、計數 — U形）</td> 
  </tr>
 </tbody>
</table>

粒度層級可能依管道而異。 建議的方法是問自己，「我是否希望更詳細地了解『X頻道』呢？」 付費搜尋管理員可能也對其他維度感興趣，例如：

* 廣告促銷活動名稱
* 廣告內容
* 廣告群組

但是，事件管理員可能更有興趣了解建立哪些特定事件或哪些類型的事件影響了最多銷售機會：

* 廣告促銷活動名稱/ Salesforce促銷活動=特定事件
* 媒體=促銷活動「類型」

**提醒**:可能需要將其他篩選條件新增至上述或下方列出的任何報表變數。 這些篩選條件將是貴組織專屬的，且是您的行銷作業或銷售作業團隊可協助提供建議的項目。 組織在所有報表中執行相同的篩選器，以確保報表盡可能簡潔準確，這並非罕見。 常見範例可能包括：

* 從測試中篩選掉任何內部記錄，通常依電子郵件地址
* 根據您的業務部門特定的特定「記錄類型」進行篩選

**1.3 |依內容新增銷售機會（僅限CRM報表）**

<table> 
 <tbody>
  <tr>
   <td>問題</td> 
   <td>什麼 <i>內容</i> 是否會影響Lead進而創造？</td> 
  </tr>
  <tr>
   <td>報表類型</td> 
   <td>銷售機會和購買者接觸點(CRM)</td> 
  </tr>
  <tr>
   <td>日期欄位</td> 
   <td>銷售機會建立日期</td> 
  </tr>
  <tr>
   <td>日期範圍</td> 
   <td><i>選擇所需日期範圍</i></td> 
  </tr>
  <tr>
   <td>群組/Dimension</td> 
   <td>登陸頁面<br> 
   表單URL</td> 
  </tr>
  <tr>
   <td>最佳模型</td> 
   <td>首次接觸、銷售機會建立、 <strong>U形</strong><br></td> 
  </tr>
 </tbody>
</table>

**提醒**:針對數位內容/資產製作報表的兩個主要欄位為「登陸頁面」和「表單URL」。 如果銷售機會在其「著陸」（著陸頁面）的相同頁面上轉換（提交表單），則這兩個值可能相同， _hever_，有時這些值會不同。 例如，銷售機會可以按一下Facebook上的連結，將其帶往您網站的頁面（這會是「著陸頁面」值）。 然後，銷售機會可以離開該頁面，繼續在網站上的工作階段，最終在另一頁上提交表單（表單URL）。 這會在單一接觸點中加以摘要，代表銷售機會的來源（行銷管道）、將他們帶到網站的內容（登陸頁面），以及他們最後下載的內容（表單URL）。 「表單URL」也是針對其他與可下載內容（例如「聯絡我們」或「示範請求」表單）無關的表單製作報表的登入欄位。

>[!TIP]
>
>透過其他篩選器深入分析特定「內容」
>
>* 篩選依據：「著陸頁面」包含（例如）:
   >   * /部落格
   >   * /ebook
   >   * /網路研討會
>
>* 或：「表單URL」包含（例如）
   >   * /contact
   >   * /demo


基於「內容」的報表在報告漏斗的任何部分時都能提供極大價值，但最常用於漏斗頂端，以便對Leads初始參與提供額外的深入分析。 考慮到「有機搜尋」往往是推動初始參與(FT)時最強的渠道，「促銷活動」層級的資料也沒有那麼多。

「內容」型報表非常適合用於深入分析促成銷售機會的原因，尤其是在較高層級的行銷管道中，此例中是「有機搜尋」。

**1.4 |指定日期範圍內的銷售機會參與總數**

<table> 
 <tbody>
  <tr>
   <td>問題</td> 
   <td>哪些行銷管道最受歡迎 <i>總銷售機會參與</i> 過去（周/月/季）?</td> 
  </tr>
  <tr>
   <td>報表類型</td> 
   <td>銷售機會和購買者接觸點(CRM)<br> 
   量度：銷售機會([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>日期欄位/日期類型</td> 
   <td>接觸點日期</td> 
  </tr>
  <tr>
   <td>日期範圍</td> 
   <td><i>選擇所需日期範圍</i></td> 
  </tr>
  <tr>
   <td>群組/Dimension</td> 
   <td>行銷管道（或更精細）</td> 
  </tr>
  <tr>
   <td>最佳模型*</td> 
   <td>*此報表不是透過歸因模型來測量銷售機會的來源，而是更關於 <i>接觸點總數（參與量）</i>，包括銷售機會建立接觸後的活動。 接觸點的記錄總數會反映哪些管道的銷售機會參與次數最多。</td> 
  </tr>
 </tbody>
</table>

**提醒**:以「接觸點日期」為報表基準，是了解特定日期範圍內行銷績效的最反映方式。 「接觸點日期」的建構方式不僅會讓歸因與管道、促銷活動或內容相關，也會顯示接觸點發生的時間。 這是了解特定時間點發生的行銷活動最有效的方式，也是衡量行銷影響的建議方式，因為與同時投資的行銷支出相比。 進行任何行銷支出或ROI分析時，均建議使用此方法（請參閱5.1）。

**2. 具有購買者接觸點的行銷合格銷售機會**

最常見的報告之一不僅側重於新的銷售機會或銷售機會級別參與，更具體地說，是「市場銷售合格銷售機會」(MQL)。 在報告MQL時，有幾種不同的方法，具體取決於 [!DNL Marketo Measure] 您有權存取的功能。

**2.1 |按管道列出的行銷合格銷售機會（多點接觸）**

這種衡量行銷對影響MQL的影響的方法實質上是「行銷管道新增銷售機會」(1.1)報告的延續，但以其他標準衡量的銷售機會更具體地是MQL。 此處仍建議使用U形歸因模型，以識別哪些行銷管道和內容產生銷售機會，然後 _like_ 要成為MQL:

<table> 
 <tbody>
  <tr>
   <td>問題</td> 
   <td>哪些行銷管道最擅長產生新銷售機會， <i>MQL</i>?</td> 
  </tr>
  <tr>
   <td>報表類型</td> 
   <td>銷售機會和購買者接觸點(CRM)<br> 
   量度：銷售機會([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>篩選器</td> 
   <td>MQL = true*<br>
   *<i>MQL的定義可能因組織而異。 確保 [!DNL Marketo Measure] 系統會使用與其他以MQL為基礎的報表相同的欄位，篩選MQL的報表。 區段篩選器的建立方式與 [!DNL Marketo Measure] 探索。</i></td> 
  </tr>
  <tr>
   <td>日期欄位/日期類型</td> 
   <td>MQL日期（或等值）/建立日期([!DNL Marketo Measure] Discover)<br> <i>如果CRM中不提供「MQL日期」選項，CRM報表中也可使用「銷售機會建立日期」。 請務必記住，您在其中使用的日期欄位會定義同類資料集。</i></td> 
  </tr>
  <tr>
   <td>日期範圍</td> 
   <td><i>選擇所需日期範圍</i></td> 
  </tr>
  <tr>
   <td>群組/Dimension</td> 
   <td>行銷管道</td> 
  </tr>
  <tr>
   <td>最佳模型</td> 
   <td>首次接觸、銷售機會建立、 <strong>U形</strong><br> 
   加總CRM報表中的「計數」欄位（計數 — 首次接觸、計數 — 銷售機會建立、計數 — U形）</td> 
  </tr>
 </tbody>
</table>

**2.2 |按管道列出的行銷合格銷售機會（僅限單次接觸，CRM）**

這種衡量行銷對影響MQL的影響的方法更側重於確定 _單一接觸點_ 是Lead達到MQL之前的上次接觸。

>[!NOTE]
>
>為了運行此報告，為了跟蹤目的（漏斗階段），需要「MQL」的「銷售機會狀態」值來定義MQL階段。 如果未透過「銷售機會狀態」欄位追蹤MQL，則必須使用「自訂階段」自訂歸因模型功能，才能在 [!DNL Marketo Measure] 帳戶設定。

<table> 
 <tbody>
  <tr>
   <td>問題</td> 
   <td>推送Lead時哪些行銷管道最強大，以達到MQL狀態？</td> 
  </tr>
  <tr>
   <td>報表類型</td> 
   <td>銷售機會和購買者接觸點(CRM)<br>
   <i>此報告僅可在CRM報告內執行。 無法篩選 [!DNL Marketo Measure] Discover</i></td> 
  </tr>
  <tr>
   <td>篩選器</td> 
   <td><strong>接觸點位置包含「MQL」</strong></td> 
  </tr>
  <tr>
   <td>日期欄位/日期類型</td> 
   <td>MQL日期（或等值）</td> 
  </tr>
  <tr>
   <td>日期範圍</td> 
   <td><i>選擇所需日期範圍</i></td> 
  </tr>
  <tr>
   <td>群組/Dimension</td> 
   <td>行銷管道</td> 
  </tr>
  <tr>
   <td>最佳模型</td> 
   <td><i>由於此報表是在單一接觸點上篩選，因此銷售機會層級歸因模型沒有相關性。 與「銷售機會參與報表」(1.4)一樣，此處會利用接觸點記錄數來了解哪些管道最強（每個銷售機會只會有一個MQL接觸點）。</i></td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>探索其他群組或維度，進一步了解MQL。 如其他「具有購買者接觸點的銷售機會」報表中所述，購買者接觸點提供的精細度遠勝於行銷管道。 「內容」型報表也可與上述任一MQL報表結合，以更清楚了解哪些內容最能影響MQL。

**3. [!DNL MARKETO MEASURE] 具有購買者接觸點的人員**

還有第三種習俗 [!DNL Marketo Measure] 物件，在報告人員相關量度時非常有用： **the [!DNL Marketo Measure] 人員(BP)**. BP解決了如何在同一份報表中同時表示Lead和Contacts資訊的古老問題。 它會聯合與「人員」( [!DNL Marketo Measure] 人員ID是其電子郵件地址)。 無論是作為Lead還是Contact,BP都作為橋梁對象，幫助跨Lead和Contact的報告，在製作更精密的人員報告時非常有用。

此 [!DNL Marketo Measure] 人員僅與其中一個接觸點物件(即購買者接觸點(BT))相關。 這表示無法將其用於機會或收入相關量度。 A &#39;[!DNL Marketo Measure] 「人員」和「購買者接觸點」的報表類型十分有助於了解 _總計參與_ 因為它顯示所有BT，無論BT與Lead還是Contact更具體。 例如，如果您有使用Salesforce促銷活動來追蹤事件，則CRM促銷活動中可能有促銷活動成員存在，作為銷售機會或聯絡人。 [!DNL Marketo Measure] 將建立促銷活動成員的接觸點，但無 [!DNL Marketo Measure] 「人員」、標準「Salesforce」報表需要兩個不同的報表，以了解 _total_ 您從事件擁有的接觸點：一個是「與購買者接觸點接觸的銷售機會」，另一個是「與購買者接觸點的接觸」。 其他幾個 [!DNL Marketo Measure] 以下列出以人員為基礎的報告使用案例：

**3.1 [!DNL Marketo Measure] 已下載「電子書」或「白皮書」的人員（下載總數）**

此報表與銷售機會層級的「內容」報表相同。 不過，與其想要測量每個內容的可歸因銷售機會數量，請使用 [!DNL Marketo Measure] 人員報告有助於了解總數 _下載次數_ 如果資產被限制（接觸點總數代表下載/表單提交總數）。

<table> 
 <tbody>
  <tr>
   <td>問題</td> 
   <td>有多少人下載了特定資產？</td> 
  </tr>
  <tr>
   <td>報表類型</td> 
   <td>[!DNL Marketo Measure] 人員與購買者接觸點(CRM)</td> 
  </tr>
  <tr>
   <td>篩選器</td> 
   <td>「表單URL」包含（例如）<br>
   <li>/ebook</li>
   <li>/whitepaper</li>
   <i>以上的篩選值僅為範例。 實際值將以每個組織的URL結構為基礎。</i></td> 
  </tr>
  <tr>
   <td>日期欄位/日期類型</td> 
   <td>接觸點日期 <i>（資產下載時間）</i></td> 
  </tr>
  <tr>
   <td>日期範圍</td> 
   <td><i>選擇所需日期範圍</i></td> 
  </tr>
  <tr>
   <td>群組/Dimension</td> 
   <td>表單URL</td> 
  </tr>
  <tr>
   <td>最佳模型</td> 
   <td>此報告與其說是關於測量銷售機會或聯絡人來自歸因模型的位置，不如說是關於 <i>接觸點總數（參與量）</i>，包括銷售機會建立接觸後的活動。 透過這份報告，我們希望了解 <i>參與總額</i>. 接觸點的記錄總數會反映下載次數最多的資產。</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>對於任何 [!DNL Marketo Measure] 人員報表類型，首先自訂預先建立的報表，標題為「**[!DNL Marketo Measure]101 |按渠道列出的銷售機會/聯繫人**&#39;。 此報表是現成可用的，非常棒 [!DNL Marketo Measure] 以人為基礎的沙箱。 此功能已預先建立，可根據更具體的報告需求快速自訂。

>[!TIP]
>
>您可以使用此報表，從「購買者接觸點」物件深入分析任何行銷維度的參與總計，而不只是範例中所示的內容下載。 反之，可將報表依「行銷管道」或「廣告促銷活動名稱」等維度分組或篩選，以便最了解資料庫中銷售機會和聯絡人的參與總數。 只需將報表中的篩選器或群組變更為接觸點物件中其他欄位所代表的其他維度的零。

**3.2 [!DNL Marketo Measure] 已註冊參加活動的人員（僅限CRM）**

_只有在您的網站上托管註冊表單時，才適用此報表 [!DNL Marketo Measure] 可進行數位追蹤。_

<table> 
 <tbody>
  <tr>
   <td>問題</td> 
   <td>什麼行銷管道在推動我的事件註冊？</td> 
  </tr>
  <tr>
   <td>報表類型</td> 
   <td>[!DNL Marketo Measure] 人員與購買者接觸點(CRM)</td> 
  </tr>
  <tr>
   <td>篩選器</td> 
   <td>「表單URL」包含（例如）<br>
   <li>/事件</li>
   <i>以上的篩選值僅為範例。 實際值將以每個組織的URL結構為基礎。</i></td> 
  </tr>
  <tr>
   <td>日期欄位/日期類型</td> 
   <td>接觸點日期 <i>（提交登記表時）</i></td> 
  </tr>
  <tr>
   <td>日期範圍</td> 
   <td><i>選擇所需日期範圍</i></td> 
  </tr>
  <tr>
   <td>群組/Dimension</td> 
   <td>表單URL<br>
   行銷管道</td> 
  </tr>
  <tr>
   <td>最佳模型</td> 
   <td>此報告與其說是關於測量銷售機會或聯絡人來自歸因模型的位置，不如說是關於 <i>接觸點總數（註冊數量）</i>，包括銷售機會建立接觸後的活動。 透過此報表，我們將深入了解推動事件註冊的因素。 每個「行銷管道」的接觸點總記錄計數，會反映哪些管道吸引最多註冊。</td> 
  </tr>
 </tbody>
</table>

此報表的主要功用在於，購買者接觸點資料也會提供行銷管道資料。 雖然您已可深入了解已註冊參與您事件的人數，但此報表也可深入分析哪些數位行銷管道、來源及/或促銷活動將使用者帶至您的網站，然後註冊該事件。

>[!TIP]
>
>在想要深入了解網路研討會註冊或隨選網路研討會下載時（如果是封閉式資產），也可以採用相同的方法。 如果這些表單托管於您網站的不重複頁面，唯一的差異是「表單URL」中的篩選值。 但目標是相同的。 它會回答以下問題：「我的哪些行銷管道吸引最多的註冊/隨需網路研討會下載。

**3.3 [!DNL Marketo Measure] 具有購買者接觸點的人員（接觸點驗證）**

考慮到 [!DNL Marketo Measure] 「人員」可讓我們針對單一報表中的所有接觸點製作報表，這是驗證資料時理想的報表類型。 我們希望確保不會忽略任何可能顯示「行銷管道」設定位置的接觸點（如需「行銷管道」設定的詳細資訊，請參閱下方連結的支援文章）。

* [線上自訂通道設定](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
* [離線自訂通道設定](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)

基本上，接觸點資料會反映 [!DNL Marketo Measure] 和可進行稽核，以確保您的設定符合下列項目的輸入：UTM參數值、轉介頁面或促銷活動類型。 如果接觸點資料與您的設定不符，則最可能需要調整某些項目。 除了「行銷管道」設定，您還可以檢視接觸點資料，以判斷可能需要的接觸點 [抑制](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md) 或 [分段](/help/advanced-marketo-measure-features/segmentation/custom-segmentation.md). 建議您在「[!DNL Marketo Measure] 人員與購買者接觸點報表（若可能），會在每月或每季結束時顯示。 這可確保您的歸因盡可能準確。 「[!DNL Marketo Measure] 101 |可用的渠道銷售機會/聯繫人報告是一個很好的起點。 如果尚未包含下列欄位以檢閱部分最重要的設定片段，請加入：

* **行銷管道**  — 路徑=行銷管道。子管道(值設定於 [!DNL Marketo Measure])
* **接觸點來源** = utm_source
* **中** = utm_medium（線上接觸點）或CRM促銷活動類型（離線接觸點）
* **反向連結頁面** （已使用「線上通道」設定）
* **登陸頁面 — 原始** （使用「線上頻道」設定）也是「設定」之「接觸點設定」標籤中觸控點隱藏的通用輸入)
* **表單URL** （在「設定」的「接觸點設定」標籤中隱藏接觸點的通用輸入）

**購買者歸因接觸點(BAT)**

購買者歸因接觸點(BAT)表示與Opportunity連接的所有聯繫人的相關接觸點（通過Opportunity Contact Roles或通過共用帳戶ID，具體取決於您的設定）。 與BT（主要與人有關）不同，BAT可以與收入相關聯。 因此，您將使用BAT來回答與機會相關的問題，主要是開啟的 _機會/管道收入_ 關閉的韓元 _機會/交易/收入_. 當在與Contact相同的帳戶下建立Opportunity時，即通過Contact的BT記錄建立BAT（BT不會轉換為BAT）。 BT資料只是用於建立附加記錄 — 然後與Opportunity相關的BAT)。

「購買者歸因接觸點」可讓我們更深入地測量漏斗中的行銷影響。 _您要測量的漏斗深度，可由各種多點接觸歸因模型來表示_.

考慮到BAT與Opportunity的主要關係，它們用於回答以下問題：

* 我的哪些行銷活動影響了最多的Opportunity?
* 每個行銷管道可新增多少管道收入？
* 上個季度，我的哪些促銷活動的投資回報率最高？

此 [歸因模型](/help/introduction-to-marketo-measure/overview-resources/marketo-measure-attribution-models.md) 提供基於機會的量度的最佳洞察包括：

**W形** - 「_管線模型_&#39;。 W形模型中包含三個里程碑接觸點。 在此模型中，FT、LC和OC接觸點各歸因於歸因評分的30%。 其餘10%會平均歸因於三個里程碑接觸點之間發生的任何中間接觸點。

<table> 
 <tbody>
  <tr>
   <td><img src="assets/bizible-reporting-guide-2.png"></td> 
   <td>此模型基本上總結了新Opportunity的歷程，這通常與生成新Pipeline Revenue同義。<p>
   <p>
   當您想要評估行銷對新商機或新管道產生的影響時，建議使用W形模型。</td> 
  </tr>
 </tbody>
</table>

**完整路徑** - 「_封閉Won模型_&#39;。 此模型包含四個里程碑接觸點：FT、LC、OC和關閉。 每個Opportunity信用額的22.5%都得到，其餘10%在中間環節中平均分配。

<table> 
 <tbody>
  <tr>
   <td><img src="assets/bizible-reporting-guide-3.png"></td> 
   <td>此模型主要總結了已結束成功交易的歷程，這通常等同於已結束成功的收入/預訂。<p>
   <p>
   若要評估行銷對已結成的成功交易或已結成的成功收入的影響，建議使用完整路徑模型。</td> 
  </tr>
 </tbody>
</table>

此模型主要總結了已結束成功交易的歷程，這通常等同於已結束成功的收入/預訂。

若要評估行銷對已結成的成功交易或已結成的成功收入的影響，建議使用完整路徑模型。

**自訂** - [!DNL Marketo Measure] 也提供「自訂歸因」模型，讓使用者可以選擇要納入其模型中的接觸點或自訂階段。 此外，使用者可以控制歸因於這些接觸點和階段的歸因評分百分比。 根據自定義模型的設定，它最適合用於測量Opportunity和Pipeline OR、Deals和Closed Won Revenue。 在報表中使用時，請記住這一點。

>[!NOTE]
>
>自訂歸因模型是並非所有客戶都能使用的額外功能。 請連絡您的客戶成功經理，以進一步了解如何將此功能新增至您的帳戶。

通常，行銷人員需要知道「我的商機來自何處？」 與銷售機會層級報表類似，此問題在歷史上以單一、一維度的值（例如主要促銷活動來源）回答。 但是，我們知道，與單一接觸的單一接觸點相比，在開發Opportunity方面投入的資源要多得多。 通常有多個接觸點，來自不同渠道和多個利益相關方，這些接觸點將影響Opportunity的建立。 使用 [!DNL Marketo Measure]，我們可以顯示帳戶中的所有接觸點，以便最好地了解機會的來源。 但是，除此之外，我們還可以繼續顯示在建立Opportunity之後發生的任何接觸點，直到Opportunity關閉為止。 這不僅使我們能夠採用多接觸方法來了解Opportunity的來源，還使我們能夠了解影響Opportunity的因素，以結束並最終代表已結束的韓元收入。 這可讓您深入了解不同的問題，例如「行銷對影響交易以完成有何影響？」、「是什麼行銷推動了結，贏得了收入？」 最終，「我的哪些營銷努力都看到了最大的ROI？」

## 使用購買者歸因接觸點(BAT)的建議報表 {#recommended-reports-using-the-buyer-attribution-touchpoint}

**4.1 |按行銷管道列出的新商機**

依欄位「行銷管道」匯總您的Opportunity的購買者歸因接觸點資料，是最高層級的檢視，代表哪些管道/策略正在影響新Opportunity的建立。 圍繞「日期類型」 = 「Opportunity Created Date」構建此報表，可確保我們還根據CRM中實際建立Opportunity的時間來匯總報表。 接觸點可能是從以前的某個時間開始的，但它們仍與已在定義的日期範圍內建立的Opportunity相關，因此會獲得歸因評分，因為這些評分被認定為影響Opportunity。

<table> 
 <tbody>
  <tr>
   <td>問題</td> 
   <td>什麼 <i>行銷管道</i> 是否會影響創造機會？</td> 
  </tr>
  <tr>
   <td>報表類型</td> 
   <td>具有商機(CRM)的購買者歸因接觸點<br> 
   量度：機會([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>篩選器</td> 
   <td>
   <li>機會階段* <i>(可選，具體取決於您希望限制到報告的哪些Opportunity。 例如，您可能只想報告仍與「Open」Opportunity關聯的BAT</i></li>
   <li>Opportunity Type(通常篩選某些Opportunity，例如「新業務」，而 <i>all</i> 機會)</li><br>
   *應利用「機會類型」的區段篩選器，位於 [!DNL Marketo Measure] Discover</td> 
  </tr>
  <tr>
   <td>日期欄位/日期類型</td> 
   <td>業務機會建立日期(CRM)/建立日期(Discover)</td> 
  </tr>
  <tr>
   <td>日期範圍</td> 
   <td><i>選擇所需日期範圍</i></td> 
  </tr>
  <tr>
   <td>群組/Dimension</td> 
   <td>行銷管道</td> 
  </tr>
  <tr>
   <td>最佳模型</td> 
   <td><strong>W形</strong><br>
   加總CRM報表中的「W形」欄位（計數 — W形、收入 — W形）</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>對於任何「具有機會的購買者歸因接觸點」報表類型，請先自訂預先建立的報表，標題為「[!DNL Marketo Measure] 101 |按渠道列出的機會&#39;。 此報表是現成可用的，而且是如上表所述預先建立的絕佳沙箱，可根據更具體的報表需求快速自訂(報表使用現成的完整路徑模型，因此請務必自訂報表，加入任何其他歸因模型（在此例中為W形模型）。

>[!TIP]
>
>上述報告也將用於了解還應歸因多少貨幣。 使用BAT在Opportunity級別報告時，有兩個關鍵度量可匯總：貨幣（Opportunity的金額）和Opportunity記錄本身。 在上例中，我們將更具體地衡量未結的Opportunity和新的管道收入。

>[!TIP]
>
>將報表與「購買者歸因接觸點」物件中的其他可用欄位一起匯總，即可獲得更精細的分析。 這與在「銷售機會」層級搭配「購買者接觸點」(1.2)時的方式相同。 若要這麼做，請新增其他群組(CRM)或維度(Discover)。 根據管道（可能代表您的角色），您可能希望獲得更多深入分析的促銷活動層級以外的其他詳細資訊。 讓我們深入探討下列「付費搜尋」：

<table> 
 <tbody>
  <tr>
   <td>問題</td> 
   <td>哪個 <i>關鍵字</i> 來自付費搜尋廣告的管道收入最多？
</td> 
  </tr>
  <tr>
   <td>報表類型</td> 
   <td>具有商機(CRM)的購買者歸因接觸點<br> 
   量度：機會([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>篩選器</td> 
   <td>
   <li>行銷管道=付費搜尋</li>
   <li>機會階段* <i>(可選，具體取決於您希望限制到報告的哪些Opportunity。 此範例以Pipeline Revenue為基礎，定義於 [!DNL Marketo Measure] 由代表潛在收入/開放管道的「開放」商機)</i></li>
   <li>Opportunity Type(通常篩選某些Opportunity，例如「新業務」，而 <i>all</i> 機會)</li><br>
   *應利用「機會類型」的區段篩選器，位於 [!DNL Marketo Measure] Discover</td> 
  </tr>
  <tr>
   <td>日期欄位/日期類型</td> 
   <td>業務機會建立日期</td> 
  </tr>
  <tr>
   <td>日期範圍</td> 
   <td><i>選擇所需日期範圍</i></td> 
  </tr>
  <tr>
   <td>群組/Dimension</td> 
   <td>關鍵字文字(CRM)<br> 
   關鍵字(Discover)</td> 
  </tr>
  <tr>
   <td>最佳模型</td> 
   <td><strong>W形</strong><br>
   加總CRM報表中的「W形」欄位（計數 — W形、收入 — W形）</td> 
  </tr>
 </tbody>
</table>

**4.2 |依行銷管道的交易**

此報告基本上與第一個「購買者歸因接觸點」範例(4.1)相同，只是量度已從未結的Opportunity變更為已結的成功交易。 量度應一律是決定要使用的歸因模型。 考慮到我們現在正在查看已完成的成功交易及其相關BAT，我們應使用一個代表整個購買者歷程（交易）的模型。 這可確保購買者歷程期間的任何行銷接觸追蹤都會獲得歸因評分：

<table> 
 <tbody>
  <tr>
   <td>問題</td> 
   <td>什麼 <i>行銷管道</i> 是否會影響交易完成？</td> 
  </tr>
  <tr>
   <td>報表類型</td> 
   <td>具有商機(CRM)的購買者歸因接觸點<br> 
   量度：交易([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>篩選器</td> 
   <td>
   <li>機會階段(<i>報告中只應包含Closed Won Opportunity</i>)或</li>
   <li>Opportunity Won = True</li>
   <li>Opportunity Type(通常篩選某些Opportunity，例如「新業務」，而不是所有機會)<br>
   </td> 
  </tr>
  <tr>
   <td>日期欄位/日期類型</td> 
   <td>業務機會結束日期</td> 
  </tr>
  <tr>
   <td>日期範圍</td> 
   <td><i>選擇所需日期範圍</i></td> 
  </tr>
  <tr>
   <td>群組/Dimension</td> 
   <td>行銷管道</td> 
  </tr>
  <tr>
   <td>最佳模型</td> 
   <td><strong>完整路徑</strong><br>
   加總CRM報表中的「完整路徑」欄位（計數 — 完整路徑、收入 — 完整路徑）</td> 
  </tr>
 </tbody>
</table>

**提醒**:請務必記住篩選您要包含在基於BAT的報告中的特定Opportunity，尤其是當出現「Open Opportunity和Pipeline Revenue」時，「交易和結案贏得收入」。 這通常通過「機會階段」篩選器完成（「機會成功」= true/false篩選器在此也非常有用）。

**5. ROI([!DNL Marketo Measure] 僅限Discover)**

此 [!DNL Marketo Measure] Discover控制面板可提供行銷績效的高階檢視，使用 [!DNL Marketo Measure] 歸因資料。 這些匯總的控制面板提供關鍵行銷支出和ROI資料，這些資料在您的CRM報表中無法使用。 此預先建立的環境可讓您檢視行銷績效，並與ROI資料保持一致，讓您能針對行銷做出可操作的決策。

>[!TIP]
>
>每當您有與ROI、支出或成本相關的問題時， [!DNL Marketo Measure] Discover將是最佳的報表位置！

此 [!DNL Marketo Measure] Discover控制面板由購買者接觸點和購買者歸因接觸點資料，以及關鍵CRM資料組成。 中CRM報表與報表之間的主要差異 [!DNL Marketo Measure] Discover是指Discover中的接觸點資料會以「匯總」的方式呈現，並以維度（行銷管道、促銷活動等）匯總 與個別接觸點記錄相反，這些記錄可以匯總。 [!DNL Marketo Measure] Discover在高層級上用於了解您的哪些工作對Lead、Opp、Deals產生了最大影響，以及應將多少收入歸因於這些工作。 透過各種歸因模型計算歸因收入後（建議使用完整路徑來歸因已結束的收入/預訂），我們就可以根據相同維度（行銷管道、子管道或促銷活動）中的花費來測量收入。 這樣我們就能 **ROI**.

>[!TIP]
>
>在Discover中報告時，最重要的事項之一，就是您要用來篩選的資料類型。 日期類型將決定哪個資料集 [!DNL Marketo Measure] 正在各種圖磚中使用。

* **接觸點日期**:顯示指定時間範圍內具有「接觸點日期」的相關資料
* **建立日期**:顯示指定時間範圍內具有「建立日期」的相關資料
* **結束日期**:顯示指定時間範圍內具有「關閉日期」的相關資料

報告 [!DNL Marketo Measure] Discover，建議使用「日期類型」=「接觸點日期」。 為釐定每筆投資之回報，我們需要確保將收益歸入投資當日。 「日期類型」=「接觸點日期」可確保以此方式構建報表，而不是建立Opportunity（建立日期）或關閉（關閉日期）時。 讓我們更仔細地看看：

以下強調的篩選條件對於以下主題中的ROI為重點的報表至關重要： [!DNL Marketo Measure] （您很可能會在「概述」、「CMO」或「ROI」展示板中設定這些篩選）:

**5.1 | 「概述」展示板中的ROI**

![](assets/bizible-reporting-guide-4.png)

「日期」範圍不僅會設定接收歸因的接觸點同類群組（依接觸點日期），也會定義「支出」圖磚或欄所代表的範圍。
[!DNL Marketo Measure] 只要查看「日期」範圍，即可判斷總支出或行銷管道、子管道或行銷活動層級的支出金額，請參閱下列內容：

![](assets/bizible-reporting-guide-5.png)

上方的螢幕擷取畫面顯示過去3個完整月的行銷支出資料。 在此範例中，所有管道均花費$12,970。 此數字由行銷支出資料組成 [!DNL Marketo Measure] 與任何已連線廣告帳戶(Google AdWords、Bing Ads、Facebook Ads、LinkedIn、DoubleClick)整合，以及任何已在您的帳戶內上傳或從CRM中的Campaign記錄自動提取的額外行銷支出。 此範例也顯示有多少已結且未結的「收入」也可歸因於相同日期範圍內發生的接觸點（綠色方塊）。 以下是ROI的計算方式：來自相同日期範圍內投資之接觸點應佔收入：

![](assets/bizible-reporting-guide-6.png)

**提醒**: [!DNL Marketo Measure] 將「收入」定義為已結束的won收入或預訂，並將「Pipeline收入」定義為 _來自未結商機的未結/潛在收入_.

上述ROI報表的另一個重要收穫是紅色方塊中代表的「管道收入」。 這意味著，從過去3個完整月投資的12,970美元，我們目前將705,199美元的「收入」歸因於已結束的「收入」，但我們也將6,905,532美元的未結潛在收入（「管道收入」）歸因於從同一投資建立的接觸點！ 我們預計會看到「管道收入」中隨著時間而關閉的一部分，提供「收入」數字，因此，ROI數字會隨著時間而增加。 「支出」數字已固定，因為過去3個完整月內，我們無法及時返回以花費更多。 在任何ROI報表中使用「接觸點日期」的「日期類型」非常重要：它會定義&#x200B;**我**)，並確保&#x200B;**R**)收入歸因歸因於源自投資的相同接觸點（每花費一美元，多少錢？）。

>[!TIP]
>
>篩選行銷管道、子管道及/或行銷活動，您知道行銷支出資料完整且準確。 上述範例適用於所有行銷管道，但如果某些管道未上傳相關的行銷支出資料，則ROI報表可能會不準確。 請參閱下列範例，這次是在「ROI」展示板中，該展示板著重於「付費搜尋」行銷管道中的行銷活動，此管道透過整合提供精細的行銷支出資料。

![](assets/bizible-reporting-guide-7.png)
