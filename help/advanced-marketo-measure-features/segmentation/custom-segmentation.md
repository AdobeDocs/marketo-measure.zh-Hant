---
unique-page-id: 18874604
description: 自訂分段 —  [!DNL Marketo Measure]  — 產品檔案
title: 自訂分段
exl-id: c20a2add-250e-45ff-97a6-1b1c03351b6a
feature: Segmentation
source-git-commit: cc786cb3af08fa36af91ef22f4dba3072c9617eb
workflow-type: tm+mt
source-wordcount: '729'
ht-degree: 0%

---

# 自訂分段 {#custom-segmentation}

區段提供篩選中資料的功能 [!DNL Marketo Measure] ROI控制面板，以進一步深入研究特定資料集。 例如，區段可依地理區域或評分系統定義。

**為何選擇自訂分段？**

自訂分段可讓您依類別（篩選器名稱）和規則（篩選器值）篩選接觸點。 第1級客戶可獲得一個區段，第2級及更高等級可獲得十個。 根據您的ROI Dash指向的Object （Lead或Contact），您可以根據Lead/Contact Object上的欄位建立區段。 此外，您也可以根據在Opportunity物件上找到的任何欄位來建立區段。

**自訂分段功能何時有用？**

自訂分段可用於檢視特定記錄型別的資料。 對應篩選器邏輯後，您應該可以在 [!DNL Marketo Measure] 控制面板的「需求瀑布圖」檢視，也就是您在CRM中看到的相同資料。

**該如何設定？**

步驟1 — 決定您要檢視的資訊。

在使用此功能之前，請先瞭解您想要依據哪些接觸點資訊進行篩選。 請記得在CRM中為您的記錄型別使用完全相同的值。 此設定會從行銷漏斗的頂端篩選接觸點。

步驟2 — 登入並找到 [!UICONTROL Segments] 功能。

* 前往 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} 並登入
* 在 [!UICONTROL My Account] 索引標籤，選取 [!UICONTROL Settings]
* 選取 [!UICONTROL Segments] 從側邊欄的選項移至左側的 [!UICONTROL Reporting] 區段

步驟3 — 瞭解元件。

* 使用此圖例來瞭解此頁面上的各種圖示

![](assets/1.png)

步驟4 — 新增篩選規則。

* 首先，輸入類別名稱。 [!UICONTROL Business Type] 就是個例子。 完成後，按一下核取記號。 在新增區段之前，您必須輸入類別名稱
* 按一下加號以新增區段
* 輸入「區段」名稱。 例如，您可以有一個區段用於新業務、合作夥伴、續約或向上銷售

![](assets/2.png)

* 按一下加號圖示以顯示規則輸入欄位。 欄位挑選清單中的選項會直接從您的CRM中提取欄位

![](assets/3.png)

>[!NOTE]
>
>公式欄位無法在規則中使用，也不會出現在選擇清單中。 因為公式會在背景中計算，而且不會修改記錄， [!DNL Marketo Measure] 無法偵測記錄是否符合規則。

* 此 [!UICONTROL Value] 選項不是下拉式清單，必須手動輸入其值。 請務必檢視Salesforce組織中的值
* 對「商機」區段規則重複此程式
* 「其他」類別是將擷取任何未定義接觸點的預設區段。 您可以變更預設區段名稱
* 按一下垃圾桶圖示可刪除整個類別或類別中的個別規則。 或者，按一下鉛筆圖示來編輯類別或規則
* 您會注意到您有一個&quot;[!UICONTROL Save]」按鈕和「儲存並處理」按鈕。 使用「儲存」按鈕來儲存您所做的工作和隨時間發生的變更。 只有在您確定下列專案後，才使用「儲存並處理」按鈕：

   * 您的對應是準確的
   * 您已新增所有要在類別中追蹤的區段
   * 「儲存並處理」按鈕會觸發 [!DNL Marketo Measure] 以同步處理所有接觸點並套用您新增的新資訊。 此程式需要7天，在此期間，無法變更規則

**_其他附註：_**

如果未同時為「銷售機會/聯絡人」與「商機」設定規則，您只會看到資料的一部分。 更進一步說，如果您未設定「商機」規則，您只會看到沒有相關商機的銷售機會/聯絡人資料。 如果您未設定「銷售機會/聯絡人」的規則，也會發生同樣的情況，您只會看到沒有相關「銷售機會/聯絡人」的「商機」。

完成後，按一下 [!UICONTROL Save] 首先，仔細檢查所有專案，然後按一下 [!UICONTROL Save and Process]. 請記住，當您儲存並處理設定時，您將無法在7天內編輯設定，因為 [!DNL Marketo Measure] 正在重新格式化此期間的資料。

如果您是Marketo Measure Ultimate客戶，並將您的預設控制面板物件設定為Contact，請勿使用下列兩個特定於Lead的欄位([在此處瞭解更多](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"})。

* b2b.personStatus
* b2b.isConverted

**如何儲存產生的報表？**

您不能直接在使用者介面中儲存產生的報表。 不過， [!DNL Marketo Measure] 將區段名稱儲存在URL中，這樣就能將頁面加入書籤，保留每份報表的記錄。
