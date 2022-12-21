---
description: '"[!DNL Marketo Measure] 整合Adobe Analytics - [!DNL Marketo Measure]  — 產品檔案」'
title: "[!DNL Marketo Measure] 與 [!DNL Adobe Analytics]"
exl-id: 3a125a15-eb74-454a-afb3-75746a1dfac6
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 0%

---

# [!DNL Marketo Measure] 與Adobe Analytics整合 {#marketo-measure-integrations-with-adobe-analytics}

B2B客戶屬性整合可讓共同的使用者 [!DNL Marketo Measure] 和Adobe Analytics，讓他們 [!DNL Adobe Analytics] 具有衍生自之有價值中繼資料的使用者設定檔 [!DNL Marketo Measure] 歸因引擎，並透過其與CRM的同步功能([!DNL Microsoft Dynamics] 和 [!DNL Salesforce])。 所有使用 [!DNL Adobe Analytics] 和 [!DNL Marketo Measure].

>[!PREREQUISITES]
>
>您必須同時擁有兩個的有效訂閱 [!DNL Marketo Measure] 和 [!DNL Adobe Analytics].

## 設定整合 {#configuring-the-integration}

1. 首先，在您的Experience Cloud主控台中建立新的客戶屬性資料來源。 詳細指示 [可在此處找到](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html).

   請注意下列資訊，因為您會在程式的後續步驟中需要這些資訊：

   * 別名ID，可以是您想要的任何值。 我們建議使用「marketomeasure_id」

   * FTP伺服器主機名稱和憑證（使用者名稱和密碼）

1. 建立客戶屬性資料來源後，請導覽至 **[!UICONTROL Integrations]** > **[!UICONTROL Connections]** 螢幕 [!DNL Marketo Measure] 管理功能表。

1. 按一下 **[!UICONTROL Set Up New Customer Attributes Connection]** 按鈕，並依照指示設定客戶屬性整合。 在核心服務主控台中建立客戶屬性來源時，UI會提示您輸入別名ID和FTP連線資訊，以及選取您要同步至您的帳戶屬性集 [!DNL Adobe Analytics] 帳戶。

   您也需要輸入Adobe IMS組織ID。 此ID會顯示在您的Adobe Experience CloudAdmin Console的右下角。 如需尋找此ID的詳細說明，請洽詢您的客戶成功經理。

1. 完成在 [!DNL Marketo Measure] 帳戶，您必須回到Experience Cloud主控台才能 [驗證結構](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/validate-schema.html). 您不需擔心FTP檔案上傳， [!DNL Marketo Measure] 已自動完成。 您只需前往步驟1中建立之客戶屬性來源的「檢視/編輯」結構畫面，並告訴Adobe每個屬性的資料類型為何 [!DNL Marketo Measure] 已代表您上傳。 您也可以視需要為已上傳的屬性建立新的易記顯示名稱。

   如果您選擇從CRM帳戶物件同步屬性，強烈建議您為屬性選擇新的顯示名稱，如 [!DNL Marketo Measure] 只會填入這些屬性的API層級名稱，這些名稱通常不適合用於報表。

1. 最後一個步驟是為您要在中使用屬性的Experience Cloud應用程式配置屬性訂閱。  您可以為 [!DNL Adobe Analytics] 或 [!DNL Adobe Target].  有關如何執行此操作的更多資訊 [可在此處找到](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/subscription.html).

## 屬性說明 {#attribute-descriptions}

建立新的B2B客戶屬性連線時， [!DNL Marketo Measure] 會自動為您建立標準B2B客戶屬性集。 下表介紹了這些屬性。

除了下列屬性外，您也可以上傳附加至CRM中帳戶物件的任何屬性。 如果有多個帳戶系結至指定的使用者， [!DNL Marketo Measure] 會以分號分隔的清單填入所有相符的帳戶屬性值。

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td><b>屬性名稱</b></td> 
   <td><b>說明</b></td>
  </tr> 
  <tr> 
   <td>Account.Name</td> 
   <td>與指定網站訪客相關聯的帳戶名稱。 如果有多個帳戶系結至指定的使用者， [!DNL Marketo Measure] 會以分號分隔的清單填入所有相符的帳戶名稱。<br/>
   <strong>注意：</strong> account.name是帳戶物件上name屬性的Salesforce-API層級名稱。 在整合設定的「結構驗證」步驟（步驟4）中，您可以為此屬性選擇更佳的顯示名稱（例如「公司」）。</td>
  </tr>
  <tr> 
   <td>歸因收入 — 型號</td> 
   <td>此客戶因與CRM中的閉門機會關聯而獲得的收入，由 [!DNL Marketo Measure] 歸因引擎。<br/>
   您的每個歸因模型都會有下列其中一個屬性 [!DNL Marketo Measure] 訂閱可用於（例如「歸因收入 — 完整路徑」）。</td>
  </tr>
  <tr> 
   <td>最深的漏斗階段</td> 
   <td>與給定用戶關聯的任何開放機會的最深漏斗階段。</td>
  </tr>
  <tr> 
   <td>開放機會</td> 
   <td>根據您的CRM資料，指定使用者系結的商機ID清單（以分號分隔）。</td>
  </tr> 
 </tbody> 
</table>

**關於屬性限制的備注**

請注意，透過這項整合呈現的屬性仍會計入中的合約屬性限制 [!DNL Adobe Analytics] 和 [!DNL Adobe Target]. 僅透過屬性訂閱呈現的屬性( [設定整合](#configuring-the-integration))會計入您所訂閱應用程式的上限。

## 常見問題集 {#faqs}

**如何透過這項整合變更要共用的屬性集？**

為了共用的屬性 [!DNL Marketo Measure] 透過這項整合顯示並用於 [!DNL Adobe Analytics]，則需透過核心服務主控台中設定的屬性訂閱呈現。 因此，如果要移除屬性，使其不再顯示於 [!DNL Adobe Analytics]，您只需刪除屬性訂閱即可達成此目標。

您也可以刪除 [!DNL Marketo Measure] 並使用您不再想從連線設定中共用已排除的屬性重新建立。 同樣地，若要將屬性新增至整合，您需要刪除現有連線，並建立新連線，將所需的屬性新增至設定。

基於上述，強烈建議在首次設定屬性連線時，在選取屬性時應盡可能包容。

**此整合的一些範例使用案例為何？**

1. 帳戶型流量量度：您可以使用帳戶名稱屬性，在Adobe Analytics中建立一或多個目標帳戶的區段，並僅分析源自目標帳戶之流量子集的網站流量量度。
1. 內容分析：使用收入量度來分析哪些網站內容最吸引最終購買您的產品或服務的客戶，或觸及特定漏斗階段的客戶。
1. 即時交易支援：分析與您CRM中特定開放商機相關聯的使用者的網站行為，以可操作的分析為您的銷售團隊提供服務。
