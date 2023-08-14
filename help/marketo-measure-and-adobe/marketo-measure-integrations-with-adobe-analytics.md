---
description: '"[!DNL Marketo Measure] 與Adobe Analytics的整合 —  [!DNL Marketo Measure]  — 產品檔案」'
title: "[!DNL Marketo Measure] 與整合 [!DNL Adobe Analytics]"
exl-id: 3a125a15-eb74-454a-afb3-75746a1dfac6
feature: Integration
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 0%

---

# [!DNL Marketo Measure] Adobe Analytics的整合 {#marketo-measure-integrations-with-adobe-analytics}

B2B客戶屬性整合可讓共同使用者 [!DNL Marketo Measure] 和Adobe Analytics，讓其 [!DNL Adobe Analytics] 包含衍生自的重要中繼資料的使用者設定檔 [!DNL Marketo Measure] 歸因引擎及其與CRM的同步功能([!DNL Microsoft Dynamics] 和 [!DNL Salesforce])。 所有使用的客戶都可以免費使用 [!DNL Adobe Analytics] 和 [!DNL Marketo Measure].

>[!PREREQUISITES]
>
>您必須同時擁有兩個的有效訂閱 [!DNL Marketo Measure] 和 [!DNL Adobe Analytics].

## 設定整合 {#configuring-the-integration}

1. 首先，請在Experience Cloud主控台中建立新的客戶屬性資料來源。 詳細指示 [可在此處找到](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html).

   請記下下列資訊，因為您將需要這些資訊來完成程式中的後續步驟：

   * 別名ID，可以是您希望它成為的任何值。 我們建議使用「marketomeasure_id」

   * FTP伺服器主機名稱和認證（使用者名稱和密碼）

1. 建立客戶屬性資料來源後，請導覽至「 」以繼續設定程式。 **[!UICONTROL Integrations]** > **[!UICONTROL Connections]** 中的畫面 [!DNL Marketo Measure] 管理功能表。

1. 按一下 **[!UICONTROL Set Up New Customer Attributes Connection]** 按鈕並依照指示設定客戶屬性整合。 UI會提示您輸入您在核心服務主控台中建立客戶屬性來源時所取得的別名ID和FTP連線資訊，並選取您要同步至的帳戶屬性集 [!DNL Adobe Analytics] 帳戶。

   您還需要輸入您的Adobe IMS組織ID。 此ID會顯示在Adobe Experience CloudAdmin Console的右下角。 如需尋找此ID的詳細協助，請洽詢Adobe帳戶團隊（您的帳戶管理員）。

1. 一旦您完成在中建立連線， [!DNL Marketo Measure] 帳戶，您必須返回Experience Cloud主控台，才能 [驗證結構](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/validate-schema.html). 您不須擔心FTP檔案上傳， [!DNL Marketo Measure] 已為您自動化該部分。 您只需要前往在步驟1建立的客戶屬性來源的「檢視/編輯」結構描述畫面，告訴Adobe每個屬性的資料型別為何， [!DNL Marketo Measure] 已代表您上傳。 您也可以視需要為上傳的屬性建立新的顯示易記名稱。

   如果您選擇從CRM帳戶物件同步屬性，強烈建議您為這些屬性選擇新的顯示名稱，如 [!DNL Marketo Measure] 只會填入這些屬性的API層級名稱，這些名稱通常對報表不友好。

1. 最後一個步驟是為您想要在其中使用屬性的Experience Cloud應用程式設定屬性訂閱。  您可以設定訂閱 [!DNL Adobe Analytics] 或 [!DNL Adobe Target].  如何執行此動作的詳細資訊 [可在此處找到](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/subscription.html).

## 屬性說明 {#attribute-descriptions}

當您建立新的B2B客戶屬性連線時， [!DNL Marketo Measure] 將會自動為您建立一組標準的B2B客戶屬性。 下表說明這些屬性。

除了下列屬性之外，您也可以上傳附加至CRM中帳戶物件的任何屬性。 如果有一個以上的帳戶繫結至指定的使用者， [!DNL Marketo Measure] 會以分號分隔的清單填入所有相符的帳戶屬性值。

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
   <td>與指定網站訪客相關聯的帳戶名稱。 如果有一個以上的帳戶繫結至指定的使用者， [!DNL Marketo Measure] 會以分號分隔的清單填入所有相符的帳戶名稱。<br/>
   <strong>注意：</strong> account.name是帳戶物件上name屬性的Salesforce-API層級名稱。 在整合設定的「結構描述驗證」步驟中（步驟4），您可以為此屬性選擇更好的顯示名稱（例如「公司」）。</td>
  </tr>
  <tr> 
   <td>已歸因的收入 — 「模型」</td> 
   <td>根據客戶與您CRM中成功交易的機會的關聯性而歸屬於此客戶的收入，計算方式為 [!DNL Marketo Measure] 歸因引擎。<br/>
   您所使用的每個歸因模型都會有以下其中一項屬性： [!DNL Marketo Measure] 訂閱可允許（例如「歸因收入 — 完整路徑」）。</td>
  </tr>
  <tr> 
   <td>最深漏斗階段</td> 
   <td>與指定使用者相關聯之任何開啟機會的最深漏斗階段。</td>
  </tr>
  <tr> 
   <td>開啟機會</td> 
   <td>根據您的CRM資料，指定使用者繫結之機會ID的清單（以分號分隔）。</td>
  </tr> 
 </tbody> 
</table>

**關於屬性限制的附註**

請注意，透過這項整合呈現的屬性仍會計入您的合約屬性限制 [!DNL Adobe Analytics] 和 [!DNL Adobe Target]. 僅限透過「屬性訂閱」顯示的屬性（中的步驟5） [設定整合](#configuring-the-integration))將計算在您訂閱應用程式的限制中。

## 常見問答 {#faqs}

**我要如何透過這項整合變更要共用的屬性集？**

為了共用屬性 [!DNL Marketo Measure] 至您的Adobe IMS組織，以便在以下位置顯示和使用： [!DNL Adobe Analytics]，需要透過核心服務主控台中設定的屬性訂閱來呈現。 因此，如果要移除屬性，使其不再出現在 [!DNL Adobe Analytics]，只要刪除屬性訂閱即可達成此目的。

您也可以刪除中的B2B客戶屬性連線 [!DNL Marketo Measure] ，然後使用您不想再從連線設定中排除的屬性重新建立連線。 同樣地，若要將屬性新增至整合，您必須刪除現有連線，並使用新增至設定的所需屬性建立新連線。

基於上述內容，強烈建議您在首次設定屬性連線時，儘可能在選取屬性時具有包容性。

**這項整合有哪些範例使用案例？**

1. 以帳戶為基礎的流量量度：您可以使用帳戶名稱屬性，在Adobe Analytics中建立一或多個目標帳戶的區段，並針對目標帳戶產生的流量子集分析網站流量量度。
1. 內容分析：使用收入量度來分析哪些網站內容最吸引最終購買您的產品或服務的客戶，或到達感興趣的特定漏斗階段的客戶。
1. 即時交易支援：通過分析與CRM中特定開放機會相關聯之使用者的網站行為，以可操作分析支援您的銷售團隊。
