---
description: '[!DNL Marketo Measure]報告範本 — Tableau - [!DNL Marketo Measure]'
title: "[!DNL Marketo Measure]報告範本 — Tableau"
exl-id: 18963be9-5c6e-4454-8244-b50460e2bed5
feature: Reporting
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '2275'
ht-degree: 0%

---

# [!DNL Marketo Measure]報告範本 — Tableau {#marketo-measure-report-template-tableau}

## 快速入門 {#getting-started}

您可以在[這裡](https://github.com/adobe/Marketo-Measure-BI-Templates){target="_blank"}存取[!DNL Tableau]報告範本。

開啟[!DNL Adobe Marketo Measure]報表範本Tableau活頁簿檔案。

您需要將現有的連線資料更新為特定Snowflake連線資訊。 按一下「[!UICONTROL Edit Connection]」按鈕，並依照本檔案[[!UICONTROL Data Connection]](#data-connection)章節中概述的步驟操作。

![](assets/marketo-measure-report-template-tableau-1.png)

## 資料連線 {#data-connection}

您需要設定與Snowflake執行個體的資料連線。 為此，您需要伺服器名稱以及您的使用者名稱和密碼。 如需尋找此資訊及重設密碼的詳細資訊，請參閱[此處](/help/marketo-measure-data-warehouse/data-warehouse-access-reader-account.md){target="_blank"}。

![](assets/marketo-measure-report-template-tableau-2.png)

您還需要輸入初始SQL命令。 這支援在此資料模型中使用自訂查詢。 要輸入的命令是「使用結構描述`<your schema name>`」。 您可以在[!UICONTROL data warehouse connections]頁面中找到您的結構描述名稱，請參閱上方參考的檔案。

![](assets/marketo-measure-report-template-tableau-3.png)

### 自訂SQL查詢 {#custom-sql-queries}

由於[!DNL Tableau]將資料來源篩選器套用至整體查詢，而不是套用至篩選器所設定的個別資料表，因此我們選擇對模型中的每個資料表使用自訂SQL。 這可讓模型篩選掉表格層級中已刪除和重複的列。 例如，當套用為資料來源篩選器時，工作階段。_deleted_date is null將會新增到查詢的where子句中，導致下列查詢。

**篩選器已新增到資料Source**

```
--A deleted session removes this row completely and the touchpoint data is lost. Select *
   From Touchpoint    tp
      join Session sn
      on tp.session_id = sn.session_id 
 Where tp._deleted_date is null
    and sn._deleted_date is null
```

不過，這是不正確的，因為如果工作階段已刪除，但未刪除對應的接觸點，則會從資料集中移除接觸點資料。 我們想要接觸點資料出現在資料集中，因為尚未刪除接觸點。 新增自訂SQL可確保篩選條件套用在表格層級，進而產生下列查詢。

透過自訂SQL套用的&#x200B;**篩選器**

```
--A deleted session only removes the session related data, and the touchpoint data is preserved. Select *
   From Touchpoint       tp
      join Session sn
      on tp.session_id          = sn.session_id 
      and sn._deleted_date      is null
  Where tp._deleted_date is null
```

## 資料轉換 {#data-transformations}

[!DNL Tableau]中的資料已從Snowflake的原始狀態套用一些轉換。 這些轉換中的大多數都套用到自訂SQL查詢，這些查詢會在[!DNL Tableau]模型中產生表格。 若要檢視用來產生表格的自訂SQL，請在表格名稱上按一下滑鼠右鍵，然後選取「編輯自訂SQL查詢」。 以下概述一些特定轉換。

![](assets/marketo-measure-report-template-tableau-4.png)

![](assets/marketo-measure-report-template-tableau-5.png)

### 已移除的欄 {#removed-columns}

為了簡化資料模型，並移除多餘和不必要的資料，我們減少了從原始Snowflake表格匯入Tableau的欄數。 移除的欄包括不必要的外部索引鍵、透過與模型中其他表格的關係更適合使用的非正規化維度資料、稽核欄以及用於內部[!DNL Marketo Measure]處理的欄位。 您可以根據業務需求新增或移除欄，方法是編輯自訂SQL的「選取」區段中的匯入欄清單。

>[!NOTE]
>
>Data Warehouse中的大多數表格都包含非正規化的維度資料。 我們已儘可能在[!DNL Tableau]中標準化並清理模型，以提高效能和資料準確度。 在事實表格中加入任何其他非正規化欄位時，請務必小心，這樣可能會破壞跨表格的維度篩選，並可能導致不準確的報告。

### 已重新命名欄 {#renamed-columns}

已重新命名表格和欄，使其更方便使用，並標準化命名慣例。 若要檢視資料欄名稱變更，請參照建立表格的自訂SQL敘述句。

### 已新增的列 {#rows-added}

為了將貨幣轉換功能新增至模型中的計算，我們在「商機」和「成本」表格中新增了公司轉換率和目標轉換率欄。 這些資料欄中的值會在資料列層次新增，並透過聯結至日期與幣別ID的「兌換率」表格來評估。 由於Tableau不允許事實表格共用多個維度表格，因此轉換率會直接新增至使用它的表格。 如需此模型中貨幣轉換運作方式的詳細資訊，請參閱本檔案中的[貨幣轉換](#currency-conversion)一節。

![](assets/marketo-measure-report-template-tableau-6.png)

有些地方，來自[!DNL Snowflake]的兩個資料表已經與聯合結合，以便在[!DNL Tableau]資料模型中建立一個資料表。 在這些執行個體中，已新增「型別」欄，以指出它來自哪個[!DNL Snowflake]資料表，並指定資料列代表的實體。 如需已合併表格的詳細資訊，請參閱本檔案的「關係與資料流程」一節。

![](assets/marketo-measure-report-template-tableau-7.png)

### 區段名稱 {#segment-names}

由於區段名稱是可自訂的，因此在Snowflake Data Warehouse中會有通用的欄名稱。 [!DNL BIZ_SEGMENT_NAMES]為對應表格，其中列出一般區段名稱及其對應的自訂區段名稱，如[!DNL Marketo Measure] UI中的區段區段所定義。 如果您使用自訂區段名稱，並且想要更新您的[!DNL Tableau]模型以合併這些名稱，請使用此表格並手動重新命名Tableau模型內的欄。 區段欄位位於「銷售機會」和「歸因接觸點」表格中，且只需重新命名一次。

[!UICONTROL CATEGORY]欄列示類別編號，而SEGMENT_NAME欄具有其對應的自訂區段名稱。

![](assets/marketo-measure-report-template-tableau-8.png)

名稱可以兩種方式更新。 第一個選項是更新自訂SQL。 在此範例中，已根據「區段名稱」表格的對應重新命名類別1-6。

![](assets/marketo-measure-report-template-tableau-9.png)

另一個選項是直接重新命名[!DNL Tableau]表格中的資料行。

![](assets/marketo-measure-report-template-tableau-10.png)

## 資料模型 {#data-model}

按一下下方影像以取得其完整大小版本。

[![](assets/marketo-measure-report-template-tableau-11.png)](/help/bi-report-templates/assets/tableau-data-model.png){target="_blank"}

### 關係和資料流程 {#relationships-and-data-flow}

用於建立接觸點的事件資料儲存在[!UICONTROL Session]、[!UICONTROL Task]、[!UICONTROL Event]、[!UICONTROL Activity]和[!UICONTROL Campaign Member]資料表中。 這些事件表格會透過各自的ID聯結至接觸點表格，如果事件產生接觸點，詳細資料會儲存在接觸點表格中。

潛在客戶接觸點和歸因接觸點將合併到此模型中的同一個表格中，並附有指向接觸點表格的連結。 已新增「接觸點型別」欄，以指定列是「銷售機會」或「歸因」接觸點。 潛在客戶及歸因接觸點的大部分維度資料都源自其對應接觸點的連結。

在此模型中，機會階段轉換和潛在客戶階段轉換會合併到一個表格中，並附有[!UICONTROL Lead and Attribution]接觸點表格的連結。 已新增「轉變型別」欄，以指定列是「機會」還是「銷售機會」階段轉變。

成本和接觸點資料會共用「管道」和「促銷活動」維度。 不過，Tableau在事實表格之間建立共用維度模型的能力有限。 由於我們限制只能有一個共用維度表格，因此「管道」和「促銷活動」資料已合併至一個表格。 在Tableau中使用兩個維度的交叉聯結將它們合併到一個表格中：頻道和促銷活動。 此唯一ID是透過串連管道和促銷活動ID所建立。 這個相同的ID值會新增至「接觸點」和「成本」表格，以建立與此合併維度表格的關係。

![](assets/marketo-measure-report-template-tableau-12.png)

在此模型中，促銷活動和管道維度會連結至接觸點，因此這些維度的所有報表都會透過此連結進行，並代表事件資料的維度報表可能不完整。 這是因為許多事件在處理至接觸點之前，都沒有這些維度的連結。

>[!NOTE]
>
>有些事件（例如工作階段）確實有促銷活動和管道維度的直接連結。 如果需要在工作階段層級報告這些維度，建議您為此建立個別的資料模型。

成本資料儲存在Snowflake資料倉儲「成本」表格中的不同彙總層次。 對於所有廣告提供者，行銷活動層級資料可彙總至頻道層級。 因此，此模型會根據&quot;campaign_is_aggregatable_cost&quot;旗標提取成本資料。 自助式成本只能在管道層級提交，並且不需要具有行銷活動資料。 為了儘可能提供最準確的成本報告，會根據「channel_is_aggregatable_cost」旗標提取自我報告的成本。 匯入成本資料的查詢會以下列邏輯寫入：如果ad_provider = &quot;SelfReported&quot;，則channel_is_aggregatable_cost = true，否則為campaign_is_aggregatable_cost = true。

在此模型的內容中，銷售機會、[!UICONTROL Contact]、[!UICONTROL Account]和[!UICONTROL Opportunity]資料會視為維度資料，並直接聯結至銷售機會和歸因接觸點表格。

### 貨幣轉換 {#currency-conversion}

「兌換率」表格中的匯率代表兌換公司幣別金額所需的值。 轉換至任何幣別需要雙重轉換，首先從原始幣別轉換至公司幣別，然後再從公司幣別轉換至選取的幣別。 此鏈結在模型中的第一個步驟，是將具有這些轉換率的兩個欄位新增至具有金額、「商機」及「成本」的表格。 本檔案的「新增的列數」一節會詳細說明這些步驟。 由於轉換率不須為靜態，而且可依指定的日期範圍變更，因此所有貨幣轉換計算都必須在資料列層次執行。 從原始幣別轉換為公司幣別，是將值除以公司兌換率，然後乘以目標兌換率。 目標轉換率由所選的貨幣引數值決定。

* 將原始值轉換為公司幣別值/公司兌換率=以公司幣別表示的值
* 將值從公司轉換為選取的貨幣值（以公司貨幣表示） `*`選取貨幣的轉換率=選取貨幣的值

![](assets/marketo-measure-report-template-tableau-13.png)

若無法識別兌換率，此模型中的貨幣兌換測量會以1.0值取代匯率。 已建立個別測量來顯示測量的貨幣值，並在計算包含多個貨幣值（即無法將值轉換為選取的貨幣）時發出警報。 這些測量（成本貨幣和收入貨幣）會包含在任何顯示成本或收入資料的視覺效果中，作為工具提示。

![](assets/marketo-measure-report-template-tableau-14.png)

## 資料定義 {#data-definitions}

已將引數、自訂欄和測量的定義新增至[!DNL Tableau model]。

![](assets/marketo-measure-report-template-tableau-15.png)

若要檢視直接來自[!DNL Snowflake]之資料行的定義，請參閱[資料倉儲檔案](/help/marketo-measure-data-warehouse/data-warehouse-schema.md){target="_blank"}。

## 範本和探索之間的差異 {#discrepancies-between-templates-and-discover}

### 已歸因的收入 {#attributed-revenue}

潛在客戶接觸點和歸因接觸點會繼承原始接觸點的維度資料。 報表範本模型會從關係到接觸點收集所有繼承的維度資料，而在探索模型中，維度資料會反正規化為「銷售機會」和「歸因」接觸點記錄。 整體已歸因收入或已歸因的管道收入值應在兩個報表之間對齊。 不過，如果依維度資料（管道、子管道或促銷活動）劃分或篩選收入，可能會發現不一致之處。 如果範本和探索之間的維度收入量不相符，則範本報表資料集中可能缺少接觸點記錄。 當有「銷售機會」或「歸因」接觸點記錄，但資料集中的接觸點表格中沒有匯入報表的對應記錄時，就會發生這種情況。 由於這些表格是依修改日期篩選，因此「銷售機會/歸因接觸點」記錄的修改可能比接觸點記錄更晚，因此「銷售機會/歸因接觸點」已匯入資料集，而原始接觸點記錄則否。 若要修正此問題，請擴大接觸點表格的篩選日期範圍，或考慮一併移除日期限制。

>[!NOTE]
>
>接觸點是大型表格，因此請考慮較完整的資料集和必須匯入的資料量之間的利弊。

### 成本 {#cost}

範本中的成本報告僅可用於行銷活動和頻道層級，但是，對於某些廣告提供者（例如創意、關鍵字、廣告群組等），以較低精細度的層級探索優惠報告。 如需有關如何在範本中模型化成本資料的詳細資訊，請參閱本檔案的[!UICONTROL Data Model]區段。 如果[!UICONTROL Discover]中的維度篩選器設為管道或促銷活動，則管道、子管道和促銷活動層級的成本應在Discover和報告範本之間保持一致。

### ROI {#roi}

由於ROI是從「歸因收入」和「成本」計算而得，這兩種計算中可能出現的相同差異，可能在ROI中產生，原因也相同，如這些章節中所述。

### 接觸點 {#touchpoints}

這些量度（如報表範本中所示）不會反映在Discover中。 目前兩者無法直接比較。

### 網站流量 {#web-traffic}

報表範本資料模型會透過工作階段與接觸點之間的關係，將頻道、子頻道和行銷活動維度資料標準化。 這與「探索」資料模型不同，後者會將這些維度非標準化為工作階段。 由於這項區別，Discover和報告範本之間的造訪和訪客的整體計數應該相符，但是，一旦依維度顯示或篩選，這些數字就預計不會一致。 這是因為範本中的維度資料僅適用於產生接觸點（即非匿名事件）的Web事件。 如需詳細資訊，請參考本檔案的[資料模型](#data-model)區段。

[!DNL Discover]和範本之間的網站表單總數可能有小差異。 這是因為報告範本中的資料模型會透過與工作階段的關係，然後透過接觸點來取得網站表單的維度資料；在少數情況下，網站表單資料沒有相關的工作階段。

### 潛在客戶與帳戶 {#leads-and-accounts}

[!DNL Discover]和範本之間所接觸帳戶的維度報表可能會稍微不同，這同樣是因為維度模型來自接觸點和潛在客戶接觸點或歸因接觸點之間的關係。 如需詳細資訊，請參閱「已歸因的收入」一節中概述的詳細資訊。

[!UICONTROL Discover]中的所有潛在客戶計數皆為已歸因的潛在客戶計數，且在報表範本中，量度已[!UICONTROL leads]次接觸。 因此，此測量在這兩個報表之間無法直接比較。

### 參與路徑 {#engagement-path}

[!DNL Discover]中的[!UICONTROL Engagement Path]報告與範本之間沒有直接比較。 [!DNL Discover]中的報表是根據接觸點建立模型，而範本中的報表是根據歸因接觸點建立模型。 範本僅聚焦於機會及其相關接觸點，而非顯示所有接觸點資料。

### 交易速度 {#deal-velocity}

範本中的這個報告與Discover中Velocity控制面板上的「交易速度」圖磚之間應該沒有差異。
