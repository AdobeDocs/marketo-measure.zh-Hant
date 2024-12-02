---
description: '[!DNL Marketo Measure]報告範本 — Power BI- [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure]報告範本 — Power BI'
exl-id: c296b8f9-4033-4723-9a71-63a458640d27
feature: Reporting
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '2526'
ht-degree: 0%

---

# [!DNL Marketo Measure]報告範本 — Power BI {#marketo-measure-report-template-power-bi}

## 快速入門 {#getting-started}

您可以在[這裡](https://github.com/adobe/Marketo-Measure-BI-Templates){target="_blank"}存取Power BI報告範本。

開啟Adobe[!DNL Marketo Measure]報表範本Power BI檔案。

![](assets/marketo-measure-report-template-power-bi-1.png)

您可以在[!DNL Data Warehouse]資訊頁上的[!DNL Marketo Measure] UI中找到您特定的伺服器、倉儲和結構描述資訊。 有關如何找到此頁面的說明，請參閱[這裡](/help/marketo-measure-data-warehouse/data-warehouse-access-reader-account.md){target="_blank"}。

QueryFilterStartDate和QueryFilterEndDate引數是用來限制匯入的資料量。 這些引數必須採用SQL格式，因為它們是傳送給[!DNL Snowflake]的查詢中所使用的。 例如，如果您想要將資料限制在過去兩年，QueryFilterStartDate會是`dateadd` (year，-2，current_date())。 這些引數會與datetime資料型別進行比較，因此建議使用`dateadd` (day，1，current_date())讓QueryFilterEndDate將所有資料傳回目前時間。

## 資料連線 {#data-connection}

開啟檔案時輸入的引數可用來建構從資料倉儲匯入表格的原生查詢。 您仍需要設定與您的[!DNL Snowflake]執行個體的資料連線。 為此，您需要相同的伺服器和倉儲名稱以及您的使用者名稱和密碼。 如需在何處尋找使用者名稱及重設密碼的詳細資訊，請參閱[此處](/help/marketo-measure-data-warehouse/data-warehouse-access-reader-account.md){target="_blank"}。

## 資料匯入 {#data-import}

若要改善報表效能，並充分利用Power Query中的轉換功能，請使用匯入儲存方法來設定此範本。

### 查詢參數 {#query-parameters}

為了限制匯入到模型中的資料，每個表格都使用原生查詢作為來源來設定。 原生查詢需要核准才能執行，您必須為每個查詢按一下「執行」。 只有在第一次執行查詢或引數變更時，才需要此步驟。

![](assets/marketo-measure-report-template-power-bi-2.png)

所有查詢都會篩選掉已刪除的列，而[!UICONTROL facts]表格會設定為篩選到修改日期介於輸入為引數的開始和結束日期之間的列。

>[!NOTE]
>
>由於日期篩選器會套用至列的修改日期，因此在報告超出限制日期範圍的日期時請務必謹慎。 例如，修改日期範圍僅限於過去兩年。 這可能包括事件日期為三年前的事件，但最近已修改。 然而，三年前事件的報告傳回不完整的結果，因為並非所有列都在兩年時間範圍內被修改。

![](assets/marketo-measure-report-template-power-bi-3.png)

下清單格被視為事實表格；修改日期的日期限制已新增到這些查詢。

* 活動
* 接觸點
* 潛在客戶接觸點
* 歸因接觸點
* 成本
* 網站表單
* Session
* 促銷活動會員
* 任務
* 活動
* 銷售機會/聯絡人階段轉換
* 機會階段轉換

下清單格被視為維度表格；這些查詢沒有設定日期限制。

* 帳戶
* Campaign
* 連絡人
* 轉換率
* 機會
* 銷售機會
* 階段
* Channel

## 資料轉換 {#data-transformations}

Power Query中的資料已套用一些轉換。 若要檢視任何表格的特定轉換，請開啟Power Query，瀏覽至表格，並記下視窗左側的「已套用的步驟」。 以下概述一些特定轉換。

![](assets/marketo-measure-report-template-power-bi-4.png)

### 已移除的欄 {#removed-columns}

為了簡化資料模型並移除多餘和不必要的資料，我們減少了從原始[!DNL Snowflake]表格匯入Power BI的欄數。 移除的欄包括不必要的外部索引鍵、透過與模型中其他表格的關係套用更好的非正規化維度資料、稽核欄以及用於內部[!DNL Marketo Measure]處理的欄位。 您可以視業務需求新增或移除欄。 導覽至任何表格中「Source」步驟之後的「已移除其他欄」步驟，按一下齒輪圖示，然後更新所提供清單中選取的欄。

>[!NOTE]
>
>* 新增其他外部索引鍵值時請小心。 Power BI通常設定為自動偵測模型中的關係，而新增外部索引鍵值可能會導致表格之間出現不想要的連結，和/或停用現有的關係。
>
>* [!DNL Marketo Measure]資料倉儲中的大多數資料表都包含非正規化的維度資料。 我們已儘可能標準化並清除Power BI中的模型，以提高效能和資料準確度。 在事實表格中加入任何其他非正規化欄位時，請務必小心，這樣可能會破壞跨表格的維度篩選，並可能導致不準確的報告。


![](assets/marketo-measure-report-template-power-bi-5.png)

### 已重新命名欄 {#renamed-columns}

已重新命名表格和欄，使其更方便使用，並標準化命名慣例。 若要檢視欄名稱變更，請導覽至任何表格中「已移除其他欄」步驟後面的「已重新命名欄」步驟。

![](assets/marketo-measure-report-template-power-bi-6.png)

### 已重新命名區段 {#renamed-segments}

由於區段名稱是可自訂的，因此在Snowflake Data Warehouse中會有通用的欄名稱。 [!DNL BIZ_SEGMENT_NAMES]是一個對應表格，其中列出一般區段名稱及其對應的自訂區段名稱，定義於[!DNL Marketo Measure] UI中的區段區段。 「區段名稱」表格可用來重新命名「潛在客戶接觸點」和「歸因接觸點」表格中的區段欄。 如果自訂區段不存在，則保留一般區段名稱。

![](assets/marketo-measure-report-template-power-bi-7.png)

### 區分大小寫：ID轉換 {#case-sensitive-id-conversion}

[!DNL Marketo Measure]資料有一些資料表，其中的主索引鍵(ID)值區分大小寫，也就是接觸點和Campaign。 驅動Power BI模型層的資料引擎不區分大小寫，因此會產生「重複」ID值。 為了保持這些關鍵值的區分大小寫功能，我們已實施轉換步驟，將不可見的字元附加至小寫字元，以便在資料引擎層中進行評估時保留ID的唯一性。 您可以在[這裡] (https://blog.crossjoin.co.uk/2019)找到有關問題的詳細資訊以及我們使用方法的詳細步驟
/10/06/power-bi-and-case-sensitivity/){target="_blank"}。 這些區分大小寫的ID值會標示為「聯結ID」，並作為關係層中的聯結金鑰使用。 我們已從報告層隱藏聯結ID，讓報表中使用的原始ID值保持可見，因為隱藏的字元可能會干擾剪下
/貼上函式和篩選。

![](assets/marketo-measure-report-template-power-bi-8.png)

![](assets/marketo-measure-report-template-power-bi-9.png)

### 已新增的列 {#rows-added}

為了將貨幣轉換功能新增至模型中的計算，我們在「商機」和「成本」表格中新增了公司轉換率欄。 此欄位中的值會在資料列層次新增，並透過聯結至日期與幣別ID的「兌換率」表格來評估。 如需此模型中貨幣轉換運作方式的詳細資訊，請參閱本檔案中的[貨幣轉換](#currency-conversion)一節。

![](assets/marketo-measure-report-template-power-bi-10.png)

儲存在[!DNL Snowflake]中的轉換率表格包含每個轉換的日期範圍。 Power BI不允許在計算上加入條件（即介於日期範圍之間）。 為了聯結日期，我們在「轉換率」表格中新增了步驟，以展開資料列，讓轉換日期範圍內的每個日期都有一列。

![](assets/marketo-measure-report-template-power-bi-11.png)

## 資料模型 {#data-model}

按一下下方影像以取得其完整大小版本。

[![](assets/marketo-measure-report-template-power-bi-12.png)](/help/bi-report-templates/assets/power-bi-data-model.png){target="_blank"}

### 關係和資料流程 {#relationships-and-data-flow}

用於建立接觸點的事件資料儲存在[!UICONTROL Session]、[!UICONTROL Task]、[!UICONTROL Event]、[!UICONTROL Activity]和Campaign成員資料表中。 這些事件表格會透過各自的ID聯結至接觸點表格，如果事件產生接觸點，詳細資料會儲存在接觸點表格中。

潛在客戶接觸點和歸因接觸點會儲存在各自的表格中，並提供指向接觸點表格的連結。 潛在客戶及歸因接觸點的大部分維度資料都源自其對應接觸點的連結。

在此模型中，促銷活動和管道維度會連結至接觸點，因此這些維度的所有報表都會透過此連結進行，並代表事件資料的維度報表可能不完整。 這是因為許多事件在處理至接觸點之前，都沒有這些維度的連結。 注意：某些事件（例如工作階段）確實有促銷活動與頻道維度的直接連結。 如果需要在工作階段層級報告這些維度，建議您為此建立個別的資料模型。

成本資料儲存在[!DNL Snowflake]資料倉儲成本表內的不同彙總層次。 對於所有廣告提供者，行銷活動層級資料可彙總至頻道層級。 因此，此模型會根據&quot;campaign_is_aggregatable_cost&quot;旗標提取成本資料。 自助式成本只能在管道層級提交，並且不需要具有行銷活動資料。 為了儘可能提供最準確的成本報告，會根據「channel_is_aggregatable_cost」旗標提取自我報告的成本。 匯入成本資料的查詢會以下列邏輯寫入：如果ad_provider = &quot;SelfReported&quot;，則channel_is_aggregatable_cost = true，否則為campaign_is_aggregatable_cost = true。

成本資料和接觸點資料有一些共同的維度，因此兩個事實表格都與「促銷活動」和「管道」維度表格有關聯。

在此模型的內容中，[!UICONTROL Lead]、[!UICONTROL Contact]、[!UICONTROL Account]和[!UICONTROL Opportunity]資料會視為維度資料，並直接聯結至[!UICONTROL Lead]接觸點和[!UICONTROL Attribution]接觸點表格。

### 新增的表格 {#added-tables}

**日期**

由於Power BI僅允許一欄表格之間的關係，因此新增了「日期」維度表格，以方便包含金額（「商機」與「成本」）的表格與「轉換率」表格之間的必要聯結。 請參閱貨幣轉換區段，以取得在此模型中如何計算貨幣轉換的詳細資訊。

**測量**

已將所有測量新增至專用的「測量」表格。 它未連線到模型，但作為儲存所有測量的單一位置，以方便使用。

**歸因模型**

已新增個別表格來儲存歸因模型的名稱。 此表用於建立篩選器，這些篩選器允許使用者在歸因收入計算的歸因模型之間切換。

### 貨幣轉換 {#currency-conversion}

「兌換率」表格中的匯率代表兌換公司幣別金額所需的值。 轉換至任何幣別需要雙重轉換，首先從原始幣別轉換至公司幣別，然後再從公司幣別轉換至選取的幣別。 此鏈結在模型中的第一個步驟，是將具有公司轉換率的欄位新增至具有金額、商機及成本的表格。 本檔案的「資料轉換」一節的「新增的列」標題中會詳細說明這些步驟。 從原始幣別轉換成公司幣別，是將值除以這個新增的欄。 下一步是將公司貨幣值乘以兌換率表格中與所選貨幣相對應的匯率。

* 將原始值轉換為公司幣別值/公司兌換率=以公司幣別表示的值
* 將值從公司轉換為選取的貨幣值（以公司貨幣表示） `*`選取貨幣的轉換率=選取貨幣的值

由於轉換率不須為靜態，而且可依指定的日期範圍變更，因此所有貨幣轉換計算都必須在資料列層次執行。 同樣地，由於兌換率與特定日期範圍相關，因此查詢計算必須在計量的DAX內執行，因此可以在貨幣代碼和日期上定義關係。

若無法識別兌換率，此模型中的貨幣兌換測量會以1.0值取代匯率。 已建立個別測量來顯示測量的貨幣值，並在計算包含多個貨幣值（即無法將值轉換為選取的貨幣）時發出警報。

![](assets/marketo-measure-report-template-power-bi-13.png)

## 資料定義 {#data-definitions}

已將表格、自訂欄和測量的定義新增至Power BI模型。

![](assets/marketo-measure-report-template-power-bi-14.png)

![](assets/marketo-measure-report-template-power-bi-15.png)

![](assets/marketo-measure-report-template-power-bi-16.png)

若要檢視直接來自[!DNL Snowflake]之資料行的定義，請參閱[資料倉儲檔案](/help/marketo-measure-data-warehouse/data-warehouse-schema.md){target="_blank"}

## 範本和探索之間的差異 {#discrepancies-between-templates-and-discover}

### 已歸因的收入 {#attributed-revenue}

潛在客戶接觸點和歸因接觸點會繼承原始接觸點的維度資料。 報表範本模型會從關係到接觸點收集所有繼承的維度資料，而在探索模型中，維度資料會反正規化為「銷售機會」和「歸因」接觸點記錄。 整體已歸因收入或已歸因的管道收入值應在兩個報表之間對齊。 不過，如果依維度資料（管道、子管道或促銷活動）劃分或篩選收入，可能會發現不一致之處。 如果範本和探索之間的維度收入量不相符，則範本報表資料集中可能缺少接觸點記錄。 當有「銷售機會」或「歸因」接觸點記錄，但資料集中的接觸點表格中沒有匯入報表的對應記錄時，就會發生這種情況。 由於這些表格是依修改日期篩選，因此「銷售機會/歸因接觸點」記錄的修改可能比接觸點記錄更晚，因此「銷售機會/歸因接觸點」已匯入資料集，而原始接觸點記錄則否。 若要修正此問題，請擴大接觸點表格的篩選日期範圍，或考慮一併移除日期限制。 注意：接觸點是大型表格，因此請考慮較完整的資料集和必須匯入的資料量之間的利弊。

### 成本 {#cost}

範本中的成本報告僅適用於行銷活動和頻道層級，不過，對於某些廣告提供者（即創意、關鍵字、廣告群組等），探索以較低詳細程度報告的優惠方案。 如需有關如何在範本中模型化成本資料的詳細資訊，請參閱本檔案的「資料模型」一節。 如果[!UICONTROL Discover]中的維度篩選器設為管道或促銷活動，則管道、子管道和促銷活動層級的成本應在Discover和報告範本之間保持一致。

### ROI {#roi}

由於ROI是從「歸因收入」和「成本」計算而得，這兩種計算中可能出現的相同差異，可能在ROI中產生，原因也相同，如這些章節中所述。

### 接觸點 {#touchpoints}

這些量度（如報表範本中所示）不會反映在Discover中。 目前兩者無法直接比較。

### 網站流量 {#web-traffic}

報表範本資料模型會透過工作階段與接觸點之間的關係，將頻道、子頻道和行銷活動維度資料標準化。 這與「探索」資料模型不同，後者會將這些維度非標準化為工作階段。 由於這項區別，Discover和報告範本之間的造訪和訪客的整體計數應該相符，但是，一旦依維度顯示或篩選，這些數字就預計不會一致。 這是因為範本中的維度資料僅適用於產生接觸點（即非匿名事件）的Web事件。 如需詳細資訊，請參考本檔案的[資料模型](#data-model)區段。

[!DNL Discover]和範本之間的網站表單總數可能有小差異。 這是因為報告範本中的資料模型會透過與工作階段的關係，然後透過接觸點來取得網站表單的維度資料；在少數情況下，網站表單資料沒有相關的工作階段。

### 潛在客戶與帳戶 {#leads-and-accounts}

所接觸帳戶的維度報表在Discover和範本之間可能略有不同，同樣是因為維度模型來自接觸點和潛在客戶接觸點或歸因接觸點之間的關係。 如需詳細資訊，請參閱「已歸因的收入」一節中概述的詳細資訊。

Discover中的所有銷售機會計數皆為已歸因的銷售機會計數，且在報表範本中接觸了銷售機會。 因此，此測量在這兩個報表之間無法直接比較。

### 參與路徑 {#engagement-path}

Discover中的[!UICONTROL Engagement Path]報告與範本之間沒有直接的比較。 [!DNL Discover]中的報表是根據接觸點建立模型，而範本中的報表是根據歸因接觸點建立模型。 範本僅聚焦於機會及其相關接觸點，而非顯示所有接觸點資料。

### 交易速度 {#deal-velocity}

範本中的這個報告與Discover中Velocity控制面板上的「交易速度」圖磚之間應該沒有差異。
