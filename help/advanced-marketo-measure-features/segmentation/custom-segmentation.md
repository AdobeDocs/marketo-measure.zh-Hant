---
unique-page-id: 18874604
description: 自訂區段 —  [!DNL Marketo Measure]  — 產品檔案
title: 自訂區段
exl-id: c20a2add-250e-45ff-97a6-1b1c03351b6a
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 0%

---

# 自訂區段 {#custom-segmentation}

區段提供篩選 [!DNL Marketo Measure] ROI控制面板，以進一步深入研究特定資料集。 例如，區段可由地理區域或分級系統定義。

**為何要自訂區段？**

「自訂分段」功能可讓您依一個類別和最多五個區段來篩選接觸點。 根據您的ROI破折號指向的對象（潛在客戶或聯繫人），您可以根據潛在客戶/聯繫人對象上找到的欄位建立段。 此外，您將能夠根據Opportunity對象上的任何欄位建立段。

**「自訂區段」功能何時有用？**

「自訂分段」可用來查看特定記錄類型的資料。 對應篩選邏輯後，您應該可以在 [!DNL Marketo Measure] 控制面板的「需求瀑布圖」檢視 — 您在CRM中看到的相同資料。

**如何設定？**

步驟1 — 決定您要查看的資訊。

使用此功能之前，請先了解要篩選的接觸點資訊。 請記得在您的CRM中使用確切值來處理記錄類型。 設定會從行銷漏斗的上到下篩選接觸點。

步驟2 — 登入並找出區段功能。

* 前往 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target=&quot;_blank&quot;}登入
* 在 [!UICONTROL My Account] 索引標籤，選取 [!UICONTROL Settings]
* 選擇 [!UICONTROL Segments] 從側邊欄的選項到左側， [!UICONTROL Reporting] 節

步驟3 — 了解元件。

* 使用此圖例可了解此頁上的各種表徵圖

![](assets/1.png)

步驟4 — 新增篩選規則。

* 首先，輸入類別名稱。 業務類型就是一個示例。 完成後，按一下複選標籤。 您必須先輸入類別名稱，才能新增區段
* 按一下加號以新增區段
* 輸入區段名稱。 例如，您可以有一個新業務、合作夥伴、續訂或向上銷售的區段

![](assets/2.png)

* 按一下加號圖示以顯示規則輸入欄位。 欄位選取清單中的選項會直接從CRM提取欄位

![](assets/3.png)

>[!NOTE]
>
>公式欄位無法在規則中使用，且不會出現在選取清單中。 因為公式在背景計算，而不修改記錄， [!DNL Marketo Measure] 無法檢測記錄是否符合規則。

* 值選項不是下拉式清單，其值必須手動輸入。 請務必檢查Salesforce組織中的值
* 對Opportunitys段規則重複此過程
* 「其他」類別是預設區段，會擷取任何未定義的接觸點。 您可以變更預設區段的名稱
* 按一下清除圖示以刪除整個類別或類別內的個別規則。 或者，按一下鉛筆圖示即可編輯類別或規則
* 您會發現您有「儲存」按鈕和「儲存並處理」按鈕。 使用「保存」按鈕保存您的工作和隨時間的變化。 只有在您確定：

   * 您的對應正確
   * 您已新增要在類別中追蹤的所有區段
   * 「儲存並處理」按鈕會觸發 [!DNL Marketo Measure] 同步所有接觸點並套用您新增的新資訊。 此程式需要7天，在此期間無法變更規則

**_其他附註：_**

如果未為Lead/Contacts和Opportunity設定規則，您將只看到一部分資料。 要詳細說明，如果您未設定Opportunity規則，則您將只看到Lead/Contact資料，而沒有與其關聯的Opportunity。 如果您沒有為Lead/Contact設定規則，則情況也一樣 — 您只會看到沒有關聯Lead/Contact的Opportunity。

完成後，按一下 [!UICONTROL Save] 首先，仔細檢查所有內容，然後按一下 [!UICONTROL Save and Process]. 請記住，儲存並處理時，您將無法編輯7天的設定，如 [!DNL Marketo Measure] 正在重新格式化資料。

**如何儲存產生的報表？**

您無法直接在使用者介面中儲存產生的報表。 不過， [!DNL Marketo Measure] 會將區段名稱儲存在URL中，以便您可以將頁面加入書籤以保留每個報表的記錄。
