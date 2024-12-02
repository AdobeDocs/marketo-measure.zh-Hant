---
description: '[!DNL Marketo Measure] 101報表總覽 —  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] 101報表總覽'
exl-id: 83977b81-8055-47fd-8a6b-5ef32d280269
feature: Reporting
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 0%

---

# [!DNL Marketo Measure] 101報表總覽 {#marketo-measure-101-reports-overview}

>[!NOTE]
>
>您可能會在檔案中看到指定&quot;[!DNL Marketo Measure]&quot;的說明，但在您的CRM中仍會看到&quot;Bizible&quot;。 我們正致力於更新此專案，品牌重塑將很快反映在您的CRM中。

所有使用[!DNL Marketo Measure]和[!DNL Salesforce]的[!DNL Marketo Measure]客戶都可以存取其SFDC執行個體中的「購買者接觸點報告」資料夾。 此資料夾包含許多預先建立的報告，可幫助您開始使用Buyer Touchpoint資料製作報告。

![](assets/bizible-101-reports-overview-1.png)

雖然這些報表中有許多已建立特定的報告目標，但共有六個&quot;_[!DNL Marketo Measure]101..._&quot;由三種主要報告型別代表，涵蓋大部分的報告需求。

* 具有購買者接觸點的銷售機會
* [!DNL Marketo Measure]個人具有購買者接觸點
* 具有機會的購買者歸因接觸點

![](assets/bizible-101-reports-overview-2.png)

這些報告為您提供您想要建立的任何[!DNL Marketo Measure]相關報告所需的基本欄位和基礎結構。 我們鼓勵所有客戶（新老客戶）在探索行銷歸因問題時，從這些報表開始。 在下方，您將會找到六個「_[!DNL Marketo Measure]101..._」報告的說明。

_若您在該資料夾中找不到「購買者接觸點報告」資料夾或六個「_[!DNL Marketo Measure] 101..._」報告，請聯絡支援以尋求協助。_

具有購買者接觸點的&#x200B;**銷售機會** | 以下兩種變化，報告銷售機會及其購買者接觸點。 雖然兩者使用相同的基本報表型別，但會依不同量度（銷售機會ID與行銷管道）分組，以提供兩種重要的資料檢視。 此報表型別是專為漏斗報表頂端所設計，非常適合用於探索潛在客戶與行銷工作的互動方式。 在任何自訂作業之前，以下兩個報表會顯示下列內容：

**[!DNL Marketo Measure]101：管道的銷售機會** | 高階檢視您的行銷管道如何影響銷售機會的建立及其額外參與。
**[!DNL Marketo Measure]101：依ID**&#x200B;的銷售機會 | 這會顯示「銷售機會」案例，且是更細微的報告，顯示每個個別「銷售機會」及其相關的「購買者接觸點」。

有購買者接觸點的&#x200B;**銷售機會/聯絡人** | 這些報告通常稱為「[!DNL Marketo Measure]人員」報告。 他們使用[!DNL Marketo Measure]自訂物件&#x200B;_[!DNL Marketo Measure]Person_，與上述報告中的Lead物件相反。

[!DNL Marketo Measure]個人物件將潛在客戶與連絡人物件關聯在一起。 [!DNL Salesforce]未提供立即可用選項，無法在同一份報表中使用Lead和Contact物件來建立報表。 透過使用個人的唯一識別碼（其電子郵件）將銷售線索與聯絡人物件建立關聯，[!DNL Marketo Measure]個人便可在相同報表中報告銷售線索與聯絡人相關的購買者接觸點。 此報告型別最適合用於驗證任何[!DNL Marketo Measure]帳戶設定，因為此為最內含的接觸點報告層級。

以下兩個報表變數使用相同的報表型別，但依據不同的量度、人員ID （電子郵件）與行銷管道分組。 這些是漏斗頂端/漏斗中間報表，探索潛在客戶與聯絡人如何與行銷活動互動時，這些報表相當不錯。 在任何自訂作業之前，以下兩個報表會顯示下列內容：

**[!DNL Marketo Measure]101：依據管道的銷售機會/聯絡人** | 概略瞭解行銷管道如何影響潛在客戶或聯絡人的建立及其額外參與。 如果您想要瞭解行銷管道的總參與度，以及哪些行銷管道在Salesforce執行個體中促成全新的名稱，此報表是您理想的選擇。
**[!DNL Marketo Measure]101：依ID**&#x200B;的銷售機會/連絡人 | 這會顯示每個[!DNL Marketo Measure]個人的劇本，且是更細微的報告，可顯示每個個人及其購買者接觸點，無論該接觸點是在他們身為銷售機會或聯絡人時發生。

**有購買者歸因接觸點的機會** | 最後兩個「_[!DNL Marketo Measure]101..._」報表是顯示與機會相關的Buyer Attribution Touchpoint資料的漏斗報表底部。 這些報表的主要差異在於，這些報表是由&#x200B;_購買者歸因接觸點_&#x200B;所建置，這些接觸點與「機會」和「機會」層級的資料（例如收入）有關。 每當您想要檢視商機或歸因收入的報告時，都應使用此報告型別。 以下兩個報表使用相同的報表型別，但是它們會依不同的量度、機會ID與行銷管道分組。 在任何自訂作業之前，以下兩個報表會顯示下列內容：

**[!DNL Marketo Measure]101：依據管道的機會** | 概略瞭解行銷管道如何影響並帶動各商機的已歸因收入。
**[!DNL Marketo Measure]101：依ID列出的商機** | 此精細的報告版本顯示商機的完整歷程。 在此報表中，您可以看到與機會相關聯的每個Buyer Attribution Touchpoint，以及透過各種歸因模型產生的歸因收入。

將&quot;_[!DNL Marketo Measure]101..._&quot;報告視為符合您報告需求的範本，這被視為最佳作法。 從上述其中一個報表開始，可以節省您的時間，並確保您使用的是與[!DNL Marketo Measure]資料相關的正確欄位。 每次對&quot;_[!DNL Marketo Measure]101..._&quot;範本進行自訂時，請務必確定您「另存新檔」，以保留報表的原始變數。

「Buyer Touchpoint報表」資料夾的設計目的，是協助您開始使用[!DNL Marketo Measure]報表，針對可操作報表，您需要自訂這些報表，以便根據您的報表需求量身打造。 您將需要新增必要的篩選器，以確保報告內的記錄（及其相關接觸點）與您的報告目標一致。

當您熟悉&quot;_[!DNL Marketo Measure]101..._&quot;報告時，您可能想要從自訂報告型別重新建立它們，以滿足更多自訂報告需求。 建立[[!DNL Marketo Measure] 自訂報表型別](/help/marketo-measure-salesforce-reporting/new-report-types/creating-custom-marketo-measure-report-types.md)可讓您提取您可能常用於其他CRM報表的自訂欄位。 這將協助您將[!DNL Marketo Measure]報告提升到新的境界！
