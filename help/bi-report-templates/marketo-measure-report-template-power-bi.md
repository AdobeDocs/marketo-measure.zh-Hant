---
description: '"[!DNL Marketo Measure] 報表範本 — Power BI- [!DNL Marketo Measure]  — 產品檔案」'
title: '"[!DNL Marketo Measure] 報表範本 — Power BI」'
exl-id: c296b8f9-4033-4723-9a71-63a458640d27
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '2569'
ht-degree: 0%

---

# [!DNL Marketo Measure] 報表範本 — Power BI {#marketo-measure-report-template-power-bi}

## 快速入門 {#getting-started}

您可以存取Power BI報表範本 [此處](https://github.com/adobe/Marketo-Measure-BI-Templates){target=&quot;_blank&quot;}。

開啟Adobe [!DNL Marketo Measure] 報表範本Power BI檔案。

![](assets/marketo-measure-report-template-power-bi-1.png)

您可以在 [!DNL Marketo Measure] 上的UI [!DNL Data Warehouse] 資訊頁面。 如何找到此頁面的說明已詳細說明 [此處](/help/marketo-measure-data-warehouse/data-warehouse-access-reader-account.md){target=&quot;_blank&quot;}。

QueryFilterStartDate和QueryFilterEndDate參數用於限制導入的資料量。 這些參數必須採用SQL格式，如同在傳送至的查詢中所用 [!DNL Snowflake]. 例如，如果要將資料限制為過去兩年，則QueryFilterStartDate將是dateadd(year,-2,current_date())。 這些參數會與日期時間資料類型進行比較，因此建議使用dateadd(day,1,current_date())，使QueryFilterEndDate將所有資料返回到當前時間。

## 資料連線 {#data-connection}

開啟檔案時輸入的參數用於構造從資料倉庫導入表的本機查詢。 您仍需要設定與 [!DNL Snowflake] 例項。 為此，您需要相同的伺服器和倉庫名稱以及用戶名和密碼。 有關在何處查找用戶名和重置密碼（如果需要）的詳細資訊將記錄在案 [此處](/help/marketo-measure-data-warehouse/data-warehouse-access-reader-account.md){target=&quot;_blank&quot;}。

## 資料匯入 {#data-import}

為了改善報表效能，並利用Power Query中的轉換功能，我們選擇使用匯入儲存方法來設定此範本。

### 查詢參數 {#query-parameters}

為了限制導入到模型中的資料，每個表都使用本地查詢作為源進行設定。 本機查詢需要核准才能執行，您將需要按一下每個查詢的執行。 只有在首次執行查詢或參數變更時，才需要執行此步驟。

![](assets/marketo-measure-report-template-power-bi-2.png)

所有查詢都會篩選掉已刪除的列，而 [!UICONTROL facts] 表格的設定是篩選為在輸入為參數的開始日期和結束日期之間具有修改日期的列。

>[!NOTE]
>
>由於日期篩選條件會套用至行的修改日期，因此在報告超出限制日期範圍的日期時請小心。 例如，修改的日期範圍限於過去兩年。 這可以包括事件日期為三年前的事件，但最近已修改。 不過，三年前事件的報表將會傳回不完整的結果，因為並非所有列都會在兩年的時間範圍內修改。

![](assets/marketo-measure-report-template-power-bi-3.png)

下表作為事實表處理；已將修改日期的日期限制新增至這些查詢。

* 活動
* 接觸點
* 銷售機會接觸點
* 歸因接觸點
* 成本
* 網站表單
* 工作階段
* 促銷活動成員
* 任務
* Event
* 銷售機會/接觸階段轉變
* 機會階段轉換

下表作為維表處理；沒有為這些查詢設定日期限制。

* 帳戶
* 行銷活動
* 連絡人
* 轉換率
* 機會
* 銷售機會
* 階段
* 管道

## 資料轉換 {#data-transformations}

對Power Query中的資料應用了一些轉換。 要查看任何表的特定轉換，請開啟「電源查詢」，導航至表，並注意窗口左側的「應用步驟」。 以下概述了某些特定轉換。

![](assets/marketo-measure-report-template-power-bi-4.png)

### 移除的欄 {#removed-columns}

為了簡化資料模型並移除多餘和不必要的資料，我們減少了從原始Power BI匯入的欄數 [!DNL Snowflake] 表格。 刪除的列包括不必要的外鍵、通過與模型中其他表的關係更好地利用的異常維資料、審計列和用於內部的欄位 [!DNL Marketo Measure] 處理。 您可以視需要新增或移除欄，以符合業務需求。 導覽至任何表格中「來源」步驟之後的「移除其他欄」步驟，按一下齒輪圖示，然後更新提供清單中選取的欄。

>[!NOTE]
>
>* 新增其他外鍵值時請小心。 Power BI通常被設定為自動檢測模型中的關係和添加外鍵值可能導致表之間不期望的連結和/或禁用現有關係。
>
>* 中的大多數表 [!DNL Marketo Measure] 資料倉庫包含非正常的維資料。 我們已致力標準化及清理Power BI中的模型，以改善效能和資料準確度。 在事實表中加入任何其他非正常欄位時，請務必小心，這可能會中斷各表的維篩選，並且可能導致報告不準確。



![](assets/marketo-measure-report-template-power-bi-5.png)

### 重新命名的欄 {#renamed-columns}

表格和欄已重新命名，讓它們更方便使用，並標準化命名慣例。 若要檢視欄名稱變更，請導覽至任何表格中「移除其他欄」步驟之後的「重新命名的欄」步驟。

![](assets/marketo-measure-report-template-power-bi-6.png)

### 重新命名的區段 {#renamed-segments}

由於區段名稱可自訂，因此在Snowflake資料倉庫中會有一般欄名稱。 [!DNL BIZ_SEGMENT_NAMES] 是對應表格，列出一般區段名稱及其對應的自訂區段名稱，定義於 [!DNL Marketo Measure] UI。 「區段名稱」表格可用來重新命名「銷售機會接觸點」和「歸因接觸點」表格中的區段欄。 如果沒有自訂區段存在，則會保留一般區段名稱。

![](assets/marketo-measure-report-template-power-bi-7.png)

### 區分大小寫的ID轉換 {#case-sensitive-id-conversion}

[!DNL Marketo Measure] 資料有幾個表格，其中主要索引鍵(ID)值區分大小寫，即接觸點和促銷活動。 驅動Power BI模型層的資料引擎不區分大小寫，因此會產生「重複」ID值。 為了保留這些鍵值的區分大小寫性，我們實施了轉換步驟，將不可見字元附加到小寫字元，在資料引擎層評估時保留ID的唯一性。 有關問題的詳細資訊，以及我們所使用方法的詳細步驟，請參閱 [此處] (https://blog.crossjoin.co.uk/2019 /10/06/power-bi-and-case-sensitive/){target=&quot;_blank&quot;}。 這些區分大小寫的ID值標籤為「連接ID」，並用作關係層中的連接鍵。 我們已從報表層隱藏「連結ID」，讓原始ID值可見並用於報表，因為隱藏的字元可能會干擾剪下/貼上功能和篩選。

![](assets/marketo-measure-report-template-power-bi-8.png)

![](assets/marketo-measure-report-template-power-bi-9.png)

### 新增的列 {#rows-added}

為了將貨幣轉換功能添加到模型中的計算，我們在Opportunity和Cost表中都添加了公司轉換率列。 此列中的值將添加到行級別，通過在日期和貨幣ID上與「轉換率」表聯合來計算。 如需貨幣轉換在此模型中如何運作的詳細資訊，請參閱 [貨幣轉換](#currency-conversion) 一節。

![](assets/marketo-measure-report-template-power-bi-10.png)

儲存於 [!DNL Snowflake] 包含每個轉換的日期範圍。 Power BI不允許在計算上使用聯接條件（即日期範圍之間）。 為了在日期加入，我們在「轉換率」表格中新增了步驟，以展開列，讓轉換日期範圍內的每個日期都有一列。

![](assets/marketo-measure-report-template-power-bi-11.png)

## 資料模型 {#data-model}

按一下下面的影像以獲得其完整大小版本。

[![](assets/marketo-measure-report-template-power-bi-12.png)](/help/bi-report-templates/assets/power-bi-data-model.png){target=&quot;_blank&quot;}

### 關係和資料流 {#relationships-and-data-flow}

用於建立接觸點的事件資料會儲存在 [!UICONTROL Session], [!UICONTROL Task], [!UICONTROL Event], [!UICONTROL Activity]，和促銷活動成員表格。 這些事件表格會透過其個別ID連結至接觸點表格，如果事件導致接觸點，詳細資料會儲存在接觸點表格中。

銷售機會接觸點和歸因接觸點會儲存在自己的表格中，並附有接觸點表格的連結。 銷售機會和歸因接觸點的大部分維度資料，都來自其對應接觸點的連結。

在此模型中，促銷活動和管道維度會連結至接觸點，因此有關這些維度的所有報表都是透過此連結，這表示關於事件資料的維度報表可能不完整。 這是因為許多事件在處理至接觸點後，才會有這些維度的連結。 注意：有些事件（例如「工作階段」）確實具有直接連結至「促銷活動」和「管道」維度。 如果需要在工作階段層級報告這些維度，建議為此建立個別的資料模型。

成本資料儲存在 [!DNL Snowflake] 資料倉庫成本表。 對於所有廣告提供者，行銷活動層級的資料可統計至管道層級。 因此，此模型會根據「campaign_is_aggregatable_cost」標幟提取成本資料。 自行報告的成本只能在渠道層級提交，不需要有Campaign資料。 為了盡可能提供最準確的成本報告，會根據「channel_is_aggregatable_cost」標籤提取自報成本。 導入成本資料的查詢使用以下邏輯寫入：如果ad_provider = &quot;SelfReported&quot;，則channel_is_aggregatable_cost = true, else campaign_is_aggregatable_cost = true。

成本資料和接觸點資料有一些共同的維度，因此兩個數值表格都與「促銷活動」和「管道」維度表格有關係。

在這個模型的背景下， [!UICONTROL Lead], [!UICONTROL Contact], [!UICONTROL Account]，和 [!UICONTROL Opportunity] 資料會視為維度資料，並直接連結至 [!UICONTROL Lead] 接觸點和 [!UICONTROL Attribution] 接觸點表格。

### 新增表格 {#added-tables}

**日期**

由於Power BI僅允許在一列上建立表之間的關係，因此添加了日期維表，以便在包含金額（Opportunity和Cost）的表和轉換率表之間進行必要的連接。 請參閱貨幣轉換區段，深入了解在此模型中如何計算貨幣轉換。

**測量值**

所有措施都已添加到專門的措施表中。 它未連接到模型，而是作為儲存所有測量的單個位置，以方便使用。

**歸因模型**

已新增另一個表格，以儲存歸因模型的名稱。 此表格用於建立篩選器，讓使用者可在歸因模型之間切換歸因收入計算。

### 貨幣轉換 {#currency-conversion}

「折換率」表中的折換率表示從公司幣種折換金額所需的值。 轉換為任何貨幣需要雙重轉換，首先從原始貨幣轉換為公司貨幣，然後從公司貨幣轉換為所選貨幣。 模型中此鏈的第一步是向具有金額、機會和成本的表中添加一個具有轉換率的列。 本檔案「資料轉換」區段的「新增列」標題中會詳細說明這些步驟。 從原始貨幣轉換為公司貨幣，包括將值除以此添加列。 下一步是將公司貨幣值乘以「轉換率」表中與所選貨幣對應的比率。

* 將原始值轉換為公司幣種值/公司折換率=以公司幣種表示的值
* 以公司幣種將值從公司折換為選定幣種值 `*` 選定貨幣的轉換率=選定貨幣中的值

由於轉換率不須為靜態，且可依指定的日期範圍變更，因此所有貨幣轉換計算必須在列層級執行。 同樣地，由於轉換率屬於特定日期範圍，因此必須在度量的DAX內執行查找計算，以便可以在貨幣代碼和日期上定義關係。

如果無法識別任何轉換率，此模型中的貨幣轉換度量會取代1.0的值。 已建立單獨的度量，以顯示度量的貨幣值，如果計算包括多個貨幣值（即，無法將值轉換為所選貨幣），則發出警告。

![](assets/marketo-measure-report-template-power-bi-13.png)

## 資料定義 {#data-definitions}

已將定義新增至表格、自訂欄和測量的Power BI模型。

![](assets/marketo-measure-report-template-power-bi-14.png)

![](assets/marketo-measure-report-template-power-bi-15.png)

![](assets/marketo-measure-report-template-power-bi-16.png)

檢視直接來自的欄的定義 [!DNL Snowflake]，請參閱 [資料倉儲檔案](/help/marketo-measure-data-warehouse/data-warehouse-schema.md){target=&quot;_blank&quot;}

## 範本和Discover之間的差異 {#discrepancies-between-templates-and-discover}

### 歸屬收入 {#attributed-revenue}

銷售機會接觸點和歸因接觸點會繼承原始接觸點的維度資料。 報表範本模型會從與接觸點的關係中，來源所有繼承的維度資料，而在Discover模型中，維度資料會非正常地歸因至銷售機會和歸因接觸點記錄。 總的歸因收入或歸因管道收入值應在兩個報表之間對齊。 不過，當依維度資料（管道、子管道或促銷活動）劃分或篩選收入時，可能會發現差異。 如果範本與Discover之間的維度收入額不相符，則範本報表資料集中很可能缺少接觸點記錄。 當有「銷售機會」或「歸因接觸點」記錄，但「接觸點」表格中沒有匯入至報表的資料集對應的記錄時，就會發生此情況。 由於這些表格是依修改日期篩選，因此潛在客戶/歸因接觸點記錄修改的時間可能比接觸點記錄更近，因此潛在客戶/歸因接觸點已匯入資料集，而原始接觸點記錄則並非如此。 若要修正此問題，請擴大接觸點表格的篩選日期範圍，或考慮將日期限制全部移除。 注意：接觸點是大表格，因此請考量比較完整資料集與必須匯入的資料量之間的取捨。

### 成本 {#cost}

範本中的成本報表僅適用於促銷活動和管道層級，不過，Discover會針對某些廣告提供者（例如創意、關鍵字、廣告群組等）提供較低粒度層級的報表。 有關如何在模板中建模成本資料的詳細資訊，請參閱本文檔的「資料模型」部分。 如果 [!UICONTROL Discover] 設為管道或促銷活動時，管道、子管道和促銷活動層級的成本應會與Discover和報表範本對齊。

### ROI {#roi}

由於ROI是從「歸因收入」和「成本」中計算的，因此這兩種計算中可能出現的差異在ROI中也會出現，原因與這些部分中所述的相同。

### 接觸點 {#touchpoints}

如報表範本所示，這些量度不會在Discover中鏡像。 目前無法直接比較兩者。

### 網路流量 {#web-traffic}

報表範本資料模型會透過工作階段與接觸點之間的關係，標準化管道、子管道和促銷活動維度資料。 這與Discover資料模型不同，Discover資料模型會將這些維度規範為工作階段。 由於有此區別，造訪和訪客的整體計數應與Discover與報表範本相符，不過，一旦依維度顯示或篩選，這些數字就不會排成一行。 這是因為範本中的維度資料僅適用於導致接觸點（即非匿名事件）的Web事件。 如需詳細資訊，請參閱 [資料模型](#data-model) 一節。

之間的網站表單總數之間可能會有細微差異 [!DNL Discover] 和模板。 這是因為報表範本中的資料模型依次透過「工作階段」和「接觸點」關係，取得「網站表單」的維度資料；有些情況下網站表單資料沒有關聯的工作階段。

### 銷售機會和帳戶 {#leads-and-accounts}

Discover和範本之間帳戶接觸的維度報表可能略有不同，這又是因為維度模型來自接觸點和接觸點或歸因接觸點之間的關係。 如需詳細資訊，請參閱歸因收入一節中概述的詳細資訊。

Discover中的所有潛在客戶計數都是歸因潛在客戶計數，而在報表範本中，度量是接觸的潛在客戶。 因此，這項措施的兩個報告之間沒有直接的比較。

### 參與路徑 {#engagement-path}

兩者之間沒有直接比較 [!UICONTROL Engagement Path] 報表和範本。 中的報表 [!DNL Discover] 會根據接觸點建立模型，而範本中的報表則是根據歸因接觸點建立模型。 範本僅著重於機會及其相關接觸點，而非顯示所有接觸點資料。

### 交易速度 {#deal-velocity}

範本中的此報表與Discover中Velocity控制面板上的「交易速度」方塊之間不應有差異。
