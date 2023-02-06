---
description: '"[!DNL Marketo Measure] 報表範本 — Tableau - [!DNL Marketo Measure]  — 產品檔案」'
title: '"[!DNL Marketo Measure] 報表範本 — Tableau」'
exl-id: 18963be9-5c6e-4454-8244-b50460e2bed5
source-git-commit: 1b0d043e9015f2f8e2f6a3a2a49849bb792c7f21
workflow-type: tm+mt
source-wordcount: '2296'
ht-degree: 0%

---

# [!DNL Marketo Measure] 報表範本 — Tableau {#marketo-measure-report-template-tableau}

## 快速入門 {#getting-started}

您可以存取 [!DNL Tableau] 報表範本 [此處](https://github.com/adobe/Marketo-Measure-BI-Templates){target="_blank"}.

開啟 [!DNL Adobe Marketo Measure] 報表範本Tableau活頁簿檔案。

您需要將現有連線資料更新為特定Snowflake連線資訊。 按一下 [!UICONTROL Edit Connection] 按鈕，並遵循 [[!UICONTROL Data Connection]](#data-connection) 一節。

![](assets/marketo-measure-report-template-tableau-1.png)

## 資料連線 {#data-connection}

您需要設定與Snowflake例項的資料連線。 為此，您需要伺服器名稱以及用戶名和密碼。 有關在何處查找此資訊和重設密碼（如果需要）的詳細資訊將記錄在案 [此處](/help/marketo-measure-data-warehouse/data-warehouse-access-reader-account.md){target="_blank"}.

![](assets/marketo-measure-report-template-tableau-2.png)

您還需要輸入初始SQL命令。 這支援在此資料模型中使用自訂查詢。 要輸入的命令是「使用架構」 `<your schema name>`」。 您可以在 [!UICONTROL data warehouse connections] 頁面，請參閱上述檔案。

![](assets/marketo-measure-report-template-tableau-3.png)

### 自定義SQL查詢 {#custom-sql-queries}

因為 [!DNL Tableau] 將資料源篩選器應用於整體查詢，而不是應用於篩選器所設定的單個表，我們已選擇對模型中的每個表使用自定義SQL。 這可讓模型篩選掉表格層級的已刪除和重複列。 例如，當套用為資料來源篩選時，會話。_deleted_date為null將添加到查詢的where子句中，導致出現以下查詢。

**新增至資料來源的篩選器**

```
--A deleted session removes this row completely and the touchpoint data is lost. Select *
   From Touchpoint    tp
      join Session sn
      on tp.session_id = sn.session_id 
 Where tp._deleted_date is null
    and sn._deleted_date is null
```

不過，這有誤，因為如果刪除工作階段，但未刪除對應的接觸點，則會從資料集中移除接觸點資料。 我們希望接觸點資料出現在資料集中，因為接觸點尚未刪除。 新增自訂SQL可確保在表層級套用篩選條件，進而產生下列查詢。

**透過自訂SQL套用的篩選器**

```
--A deleted session only removes the session related data, and the touchpoint data is preserved. Select *
   From Touchpoint       tp
      join Session sn
      on tp.session_id          = sn.session_id 
      and sn._deleted_date      is null
  Where tp._deleted_date is null
```

## 資料轉換 {#data-transformations}

已對中的資料套用一些轉換 [!DNL Tableau] 從原狀Snowflake。 這些轉換大多套用在自訂SQL查詢中，這些查詢會在 [!DNL Tableau] 模型。 要查看用於生成表的自定義SQL，請按一下右鍵表名並選擇「編輯自定義SQL查詢」。 以下概述了某些特定轉換。

![](assets/marketo-measure-report-template-tableau-4.png)

![](assets/marketo-measure-report-template-tableau-5.png)

### 移除的欄 {#removed-columns}

為了簡化資料模型並移除多餘和不必要的資料，我們已減少從原始Snowflake表匯入Tableau的欄數。 刪除的列包括不必要的外鍵、通過與模型中其他表的關係更好地利用的異常維資料、審計列和用於內部的欄位 [!DNL Marketo Measure] 處理。 您可以根據業務需要，通過編輯自定義SQL的「選擇」部分中的導入列清單來添加或刪除列。

>[!NOTE]
>
>資料倉庫中的大多數表都包含不正常的維資料。 我們已在 [!DNL Tableau] 盡可能改善效能和資料準確度。 在事實表中加入任何其他非正常欄位時，請務必小心，這可能會中斷各表的維篩選，並且可能導致報告不準確。

### 重新命名的欄 {#renamed-columns}

表格和欄已重新命名，讓它們更方便使用，並標準化命名慣例。 要查看列名更改，請參考建立表的自定義SQL陳述式。

### 新增的列 {#rows-added}

為了將貨幣轉換功能添加到模型中的計算，我們在Opportunity和Cost表中都添加了公司轉換率和目標轉換率列。 這些列中的值將在行級別添加，通過在日期和貨幣ID上與「轉換率」表聯合來計算。 由於Tableau不允許數值表格共用多個維度表格，因此轉換率會直接新增至使用該表格的表格。 如需貨幣轉換在此模型中如何運作的詳細資訊，請參閱 [貨幣轉換](#currency-conversion) 一節。

![](assets/marketo-measure-report-template-tableau-6.png)

有幾個地方有兩張桌子 [!DNL Snowflake] 已與聯合組合，以在 [!DNL Tableau] 資料模型。 在這些情況下，已新增「類型」欄，以指出 [!DNL Snowflake] 表格，並指定該列代表的實體。 如需已結合表格的詳細資訊，請參閱本檔案中的關係和資料流程一節。

![](assets/marketo-measure-report-template-tableau-7.png)

### 區段名稱 {#segment-names}

由於區段名稱可自訂，因此在Snowflake資料倉庫中會有一般欄名稱。 [!DNL BIZ_SEGMENT_NAMES] 是對應表格，列出一般區段名稱及其對應的自訂區段名稱，如 [!DNL Marketo Measure] UI。 如果您使用自訂區段名稱，且想要更新 [!DNL Tableau] 要合併這些，請使用此表格並手動更名Tableau模型中的列。 區段欄位位於「銷售機會」和「歸因接觸點」表格中，只需重新命名一次。

此 [!UICONTROL CATEGORY] 欄會列出類別編號，而SEGMENT_NAME欄則會有其對應的自訂區段名稱。

![](assets/marketo-measure-report-template-tableau-8.png)

名稱可透過兩種方式更新。 第一個選項是更新自定義SQL。 在此範例中，已根據「區段名稱」表格的對應來重新命名類別1-6。

![](assets/marketo-measure-report-template-tableau-9.png)

另一個選項是直接重新命名 [!DNL Tableau] 表格。

![](assets/marketo-measure-report-template-tableau-10.png)

## 資料模型 {#data-model}

按一下下面的影像以獲得其完整大小版本。

[![](assets/marketo-measure-report-template-tableau-11.png)](/help/bi-report-templates/assets/tableau-data-model.png){target="_blank"}

### 關係和資料流 {#relationships-and-data-flow}

用於建立接觸點的事件資料會儲存在 [!UICONTROL Session], [!UICONTROL Task], [!UICONTROL Event], [!UICONTROL Activity]，和 [!UICONTROL Campaign Member] 表格。 這些事件表格會透過其個別ID連結至接觸點表格，如果事件導致接觸點，詳細資料會儲存在接觸點表格中。

銷售機會接觸點和歸因接觸點會結合至此模型中的一個表格，並附上接觸點表格的連結。 已新增「接觸點類型」欄，以指定列是「銷售機會」或「歸因」接觸點。 銷售機會和歸因接觸點的大部分維度資料，都來自其對應接觸點的連結。

將機會階段轉變和銷售機會階段轉變組合到此模型中的一個表中，並帶有指向 [!UICONTROL Lead and Attribution] 接觸點表格。 已添加「轉換類型」列，以指定行是「機會」還是「銷售機會」階段轉換。

成本和接觸點資料共用管道和促銷活動維度。 不過，Tableau在模擬數值表格之間共用維度的能力上有限。 由於我們僅限一個共用維度表格，因此管道和促銷活動資料已合併為一個表格。 在Tableau中，這些維度是使用兩個維度的交叉連結合併為一個表格：管道和行銷活動。 唯一id是透過串連管道和促銷活動id來建立。 「接觸點」和「成本」表格會新增相同的id值，以建立與此合併維度表格的關係。

![](assets/marketo-measure-report-template-tableau-12.png)

在此模型中，促銷活動和管道維度會連結至接觸點，因此有關這些維度的所有報表都是透過此連結，這表示關於事件資料的維度報表可能不完整。 這是因為許多事件在處理至接觸點後，才會有這些維度的連結。

>[!NOTE]
>
>某些事件（例如「工作階段」）確實具有直接連結至「促銷活動」和「管道」維度。 如果需要在工作階段層級報告這些維度，建議為此建立個別的資料模型。

成本資料儲存在Snowflake資料倉庫成本表內不同的聚合層。 對於所有廣告提供者，行銷活動層級的資料可統計至管道層級。 因此，此模型會根據「campaign_is_aggregatable_cost」標幟提取成本資料。 自我報告的成本只能在渠道層級提交，而且不需要有Campaign資料。 為了盡可能提供最準確的成本報告，會根據「channel_is_aggregatable_cost」標籤提取自報成本。 導入成本資料的查詢使用以下邏輯寫入：如果ad_provider = &quot;SelfReported&quot;，則channel_is_aggregatable_cost = true, else campaign_is_aggregatable_cost = true。

在這個模型的背景下， [!UICONTROL Contact], [!UICONTROL Account]，和 [!UICONTROL Opportunity] 資料會視為維度資料，並直接連結至「銷售機會」和「歸因接觸點」表格。

### 貨幣轉換 {#currency-conversion}

「折換率」表中的折換率表示從公司幣種折換金額所需的值。 轉換為任何貨幣需要雙重轉換，首先從原始貨幣轉換為公司貨幣，然後從公司貨幣轉換為所選貨幣。 模型中此鏈的第一步是將具有這些轉換率的兩列添加到具有金額、機會和成本的表中。 在本檔案的新增列一節中會詳細說明這些步驟。 由於轉換率不須為靜態，且可依指定的日期範圍變更，因此所有貨幣轉換計算必須在列層級執行。 從原始貨幣轉換為公司貨幣包括將值除以公司折換率，然後乘以目標折換率。 目標轉換率由所選貨幣參數值決定。

* 將原始值轉換為公司幣種值/公司折換率=以公司幣種表示的值
* 以公司幣種將值從公司折換為選定幣種值 `*` 選定貨幣的轉換率=選定貨幣中的值

![](assets/marketo-measure-report-template-tableau-13.png)

如果無法識別任何轉換率，此模型中的貨幣轉換度量會取代1.0的值。 已建立單獨的度量，以顯示度量的貨幣值，如果計算包括多個貨幣值，則發出警告（即無法將某個值轉換為所選貨幣）。 這些度量（「成本幣種」和「收入幣種」）在顯示「成本」或「收入」資料的任何視覺效果中都包括為工具提示。

![](assets/marketo-measure-report-template-tableau-14.png)

## 資料定義 {#data-definitions}

定義已新增至 [!DNL Tableau model] 用於參數、自定義列和測量。

![](assets/marketo-measure-report-template-tableau-15.png)

檢視直接來自的欄的定義 [!DNL Snowflake]，請參閱 [資料倉儲檔案](/help/marketo-measure-data-warehouse/data-warehouse-schema.md){target="_blank"}.

## 範本和Discover之間的差異 {#discrepancies-between-templates-and-discover}

### 歸屬收入 {#attributed-revenue}

銷售機會接觸點和歸因接觸點會繼承原始接觸點的維度資料。 報表範本模型會從與接觸點的關係中，來源所有繼承的維度資料，而在Discover模型中，維度資料會非正常地歸因至銷售機會和歸因接觸點記錄。 總的歸因收入或歸因管道收入值應在兩個報表之間對齊。 不過，當依維度資料（管道、子管道或促銷活動）劃分或篩選收入時，可能會發現差異。 如果範本與Discover之間的維度收入額不相符，則範本報表資料集中很可能缺少接觸點記錄。 當有「銷售機會」或「歸因接觸點」記錄，但「接觸點」表格中沒有匯入至報表的資料集對應的記錄時，就會發生此情況。 由於這些表格是依修改日期篩選，因此潛在客戶/歸因接觸點記錄修改的時間可能比接觸點記錄更近，因此潛在客戶/歸因接觸點已匯入資料集，而原始接觸點記錄則並非如此。 若要修正此問題，請擴大接觸點表格的篩選日期範圍，或考慮將日期限制全部移除。

>[!NOTE]
>
>接觸點是大表格，因此請考量比較完整資料集與必須匯入的資料量之間的取捨。

### 成本 {#cost}

範本中的成本報表僅適用於促銷活動和管道層級，不過，Discover會針對某些廣告提供者（例如創意、關鍵字、廣告群組等）提供較低粒度層級的報表。 有關如何在模板中建模成本資料的詳細資訊，請參考 [!UICONTROL Data Model] 一節。 如果 [!UICONTROL Discover] 設為管道或促銷活動時，管道、子管道和促銷活動層級的成本應會與Discover和報表範本對齊。

### ROI {#roi}

由於ROI是從「歸因收入」和「成本」中計算的，因此這兩種計算中可能出現的差異在ROI中也會出現，原因與這些部分中所述的相同。

### 接觸點 {#touchpoints}

如報表範本所示，這些量度不會在Discover中鏡像。 目前無法直接比較兩者。

### 網路流量 {#web-traffic}

報表範本資料模型會透過工作階段與接觸點之間的關係，標準化管道、子管道和促銷活動維度資料。 這與Discover資料模型不同，Discover資料模型會將這些維度規範為工作階段。 由於有此區別，造訪和訪客的整體計數應與Discover與報表範本相符，不過，一旦依維度顯示或篩選，這些數字就不會排成一行。 這是因為範本中的維度資料僅適用於導致接觸點（即非匿名事件）的Web事件。 如需詳細資訊，請參閱 [資料模型](#data-model) 一節。

之間的網站表單總數之間可能會有細微差異 [!DNL Discover] 和模板。 這是因為報表範本中的資料模型依次透過「工作階段」和「接觸點」關係，取得「網站表單」的維度資料；有些情況下網站表單資料沒有關聯的工作階段。

### 銷售機會和帳戶 {#leads-and-accounts}

所接觸帳戶的維度報表可能略有不同 [!DNL Discover] 和範本，這又是因為維度模型來自接觸點和潛在客戶接觸點或歸因接觸點之間的關係。 如需詳細資訊，請參閱歸因收入一節中概述的詳細資訊。

中的所有銷售機會計數 [!UICONTROL Discover] 是歸因銷售機會計數，而在報表範本中，量度是 [!UICONTROL leads] 碰過。 因此，這項措施的兩個報告之間沒有直接的比較。

### 參與路徑 {#engagement-path}

兩者之間沒有直接比較 [!UICONTROL Engagement Path] 報告 [!DNL Discover] 和模板。 中的報表 [!DNL Discover] 會根據接觸點建立模型，而範本中的報表則是根據歸因接觸點建立模型。 範本僅著重於機會及其相關接觸點，而非顯示所有接觸點資料。

### 交易速度 {#deal-velocity}

範本中的此報表與Discover中Velocity控制面板上的「交易速度」方塊之間不應有差異。
