---
description: '[!DNL Marketo Measure]與Adobe Analytics的整合 —  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure]與 [!DNL Adobe Analytics]的整合'
exl-id: 3a125a15-eb74-454a-afb3-75746a1dfac6
feature: Integration
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 0%

---

# [!DNL Marketo Measure]與Adobe Analytics的整合 {#marketo-measure-integrations-with-adobe-analytics}

B2B客戶屬性整合可讓[!DNL Marketo Measure]和Adobe Analytics的共同使用者透過其與CRM （[!DNL Microsoft Dynamics]和[!DNL Salesforce]）的同步功能，利用衍生自[!DNL Marketo Measure]歸因引擎的寶貴中繼資料，擴充其[!DNL Adobe Analytics]使用者設定檔。 所有使用[!DNL Adobe Analytics]和[!DNL Marketo Measure]的客戶都可以免費使用。

>[!PREREQUISITES]
>
>您必須同時擁有[!DNL Marketo Measure]和[!DNL Adobe Analytics]的有效訂閱。

## 設定整合 {#configuring-the-integration}

1. 在您的Experience Cloud主控台中建立新的客戶屬性資料Source 。 您可在此找到[的詳細指示](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html)。

   記下下列資訊（在後續步驟中需要）：

   * 別名ID，可以是您希望它成為的任何值。 我們建議使用「marketomeasure_id」

   * FTP伺服器主機名稱和認證（使用者名稱和密碼）

1. 建立客戶屬性資料Source後，請導覽至「[!DNL Marketo Measure]」管理員功能表中的「**[!UICONTROL Integrations]** > **[!UICONTROL Connections]**」畫面，繼續設定程式。

1. 按一下&#x200B;**[!UICONTROL Set Up New Customer Attributes Connection]**&#x200B;按鈕，然後依照指示設定客戶屬性整合。 UI會提示您輸入您在核心服務主控台中建立客戶屬性Source時取得的別名ID和FTP連線資訊。 選取您要同步至您[!DNL Adobe Analytics]帳戶的帳戶屬性集。

   輸入您的Adobe IMS組織ID。 此ID會顯示在Adobe Experience CloudAdmin Console的右下角。 如需尋找此ID的詳細協助，請洽詢Adobe帳戶團隊（您的帳戶管理員）。

1. 在您完成[!DNL Marketo Measure]帳戶中的連線之後，必須返回Experience Cloud主控台以[驗證結構描述](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/validate-schema.html?lang=en)。 您不必擔心FTP檔案上傳，[!DNL Marketo Measure]已為您自動化該部分。 前往您在步驟1中建立的客戶屬性Source的「檢視/編輯」結構描述畫面，並告訴Adobe[!DNL Marketo Measure]代表您上傳的每個屬性的資料型別。 您也可以視需要為上傳的屬性建立新的顯示易記名稱。

   如果您選擇從CRM帳戶物件同步屬性，強烈建議您為這些屬性選擇新的顯示名稱，因為[!DNL Marketo Measure]只會填入這些屬性的API層級名稱，這些名稱通常對報表不友好。

1. 最後一個步驟是為您想要在其中使用屬性的Experience Cloud應用程式設定屬性訂閱。 您可以設定[!DNL Adobe Analytics]或[!DNL Adobe Target]的訂閱。  如需如何執行此動作的詳細資訊[，請前往這裡](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/subscription.html)。

## 屬性說明 {#attribute-descriptions}

當您建立B2B客戶屬性連線時，[!DNL Marketo Measure]會自動為您建立一組標準的B2B客戶屬性。 下表說明這些屬性。

除了下列屬性之外，您也可以上傳附加至CRM中帳戶物件的任何屬性。 如果有一個以上的帳戶繫結至指定的使用者，[!DNL Marketo Measure]會以分號分隔的清單填入所有相符的帳戶屬性值。

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
   <td>與指定網站訪客相關聯的帳戶名稱。 如果有一個以上的帳戶繫結至指定的使用者，[!DNL Marketo Measure]會以分號分隔的清單填入所有相符的帳戶名稱。<br/>
   <strong>注意：</strong> account.name是帳戶物件上name屬性的Salesforce-API層級名稱。 您可以在整合設定的結構描述驗證步驟（步驟4）中，為此屬性選擇更好的顯示名稱（例如「公司」）。</td>
  </tr>
  <tr> 
   <td>已歸因的收入 — 「模型」</td> 
   <td>根據[!DNL Marketo Measure]歸因引擎所計算，客戶與您CRM中成功交易的商機的關聯而歸因的收入。<br/>
   您的[!DNL Marketo Measure]訂閱所允許的每個歸因模型（例如，「已歸因的收入 — 完整路徑」）都有一個屬性。</td>
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

**關於屬性限制的備註**

透過此整合呈現的屬性會針對[!DNL Adobe Analytics]和[!DNL Adobe Target]中的合約屬性限制進行計數。 只有透過屬性訂閱（[設定整合專案](#configuring-the-integration)中的步驟5）浮現的屬性才會計入您訂閱應用程式的限制。

## 常見問題集 {#faqs}

**我要如何透過這項整合變更要共用的屬性集？**

若要讓[!DNL Marketo Measure]透過這項整合與您的Adobe IMS組織共用的屬性在[!DNL Adobe Analytics]中顯示和使用，該屬性必須透過核心服務主控台中設定的屬性訂閱浮現。 因此，如果您想要移除屬性，使其不再出現在[!DNL Adobe Analytics]中，只要刪除屬性訂閱即可達成此目的。

您也可以刪除[!DNL Marketo Measure]中的B2B客戶屬性連線，並使用您不想從連線設定中排除的屬性重新建立連線。 同樣地，若要將屬性新增至整合，您必須刪除現有連線，並使用新增至組態的所需屬性來建立新連線。

基於上述內容，強烈建議您在首次設定屬性連線時，儘可能在選取屬性時具有包容性。

**這項整合有哪些範例使用案例？**

1. 以帳戶為基礎的流量量度：您可以使用帳戶名稱屬性，在Adobe Analytics中建立一或多個目標帳戶的區段，並針對目標帳戶產生的流量子集分析網站流量量度。
1. 內容分析：使用收入量度來分析哪些網站內容最吸引最終購買您的產品或服務的客戶，或到達感興趣的特定漏斗階段的客戶。
1. 即時交易支援：通過分析與CRM中特定開放機會相關聯之使用者的網站行為，以可操作分析支援您的銷售團隊。
