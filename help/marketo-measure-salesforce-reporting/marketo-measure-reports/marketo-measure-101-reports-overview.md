---
description: "[!DNL Marketo Measure] 101報表概觀 —  [!DNL Marketo Measure]"
title: '"[!DNL Marketo Measure] 101報表總覽」'
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
>您可能會看到指定&#39;&#39;的說明[!DNL Marketo Measure]&quot;，但仍在您的CRM中看到「Bizible」。 我們正致力於更新此專案，品牌重塑將很快反映在您的CRM中。

全部 [!DNL Marketo Measure] 客戶使用 [!DNL Marketo Measure] 和 [!DNL Salesforce] 有權存取其SFDC執行個體中的「購買者接觸點報告」資料夾。 此資料夾包含許多預先建立的報告，可幫助您開始使用購買者接觸點資料進行報告。

![](assets/bizible-101-reports-overview-1.png)

雖然其中許多報告已建立特定的報告目標，但共有六個&quot;_[!DNL Marketo Measure]101..._&quot;代表三種主要報告型別，涵蓋大部分的報告需求。

* 具有購買者接觸點的銷售機會
* [!DNL Marketo Measure] 具有購買者接觸點的人員
* 具有機會的購買者歸因接觸點

![](assets/bizible-101-reports-overview-2.png)

這些報表提供您任何專案所需的基本欄位和基礎結構 [!DNL Marketo Measure] 要建立的相關報告。 我們鼓勵所有客戶（新老客戶）在探索行銷歸因問題時，從這些報表開始。 以下提供這六項功能的說明」_[!DNL Marketo Measure]101..._「報告。

_如果您找不到「購買者接觸點報表」資料夾或六個&quot;_[!DNL Marketo Measure] 101..._」在該資料夾中的報告，請聯絡支援以尋求協助。_

**具有購買者接觸點的銷售機會** | 以下兩種變化，報告銷售機會及其購買者接觸點。 雖然兩者使用相同的基本報表型別，但會依不同量度（銷售機會ID與行銷管道）分組，以提供兩種重要的資料檢視。 此報表型別是專為漏斗報表頂端所設計，非常適合用於探索潛在客戶與行銷工作的互動方式。 在任何自訂作業之前，以下兩個報表會顯示下列內容：

**[!DNL Marketo Measure]101：依據管道的銷售機會** | 高階檢視您的行銷管道如何影響銷售機會的建立及其額外參與。
**[!DNL Marketo Measure]101：依ID的銷售機會** | 這會顯示「銷售機會」案例，且是更細微的報告，顯示每個個別「銷售機會」及其相關的「購買者接觸點」。

**有購買者接觸點的銷售機會/聯絡人** | 這些報表通常稱為 [!DNL Marketo Measure] 人員報表。 他們使用 [!DNL Marketo Measure] 自訂物件 _[!DNL Marketo Measure]個人_ ，而非上述報告中的Lead物件。

此 [!DNL Marketo Measure] Person Object將Lead和Contact物件關聯在一起。 立即可用， [!DNL Salesforce] 不提供在同一報告中使用Lead和Contact物件來建立報告的選項。 透過使用個人的唯一識別碼、其電子郵件、 [!DNL Marketo Measure] 「人員」可以在同一報表中同時報告「銷售機會」與「聯絡人」相關的「採購員接觸點」。 若要驗證您的任何專案，此報表型別是理想選擇 [!DNL Marketo Measure] 帳戶設定，因為這是最內含的接觸點報告層級。

以下兩個報表變數使用相同的報表型別，但依據不同的量度、人員ID （電子郵件）與行銷管道分組。 這些是漏斗頂端/漏斗中間報表，探索潛在客戶與聯絡人如何與行銷活動互動時，這些報表相當不錯。 在任何自訂作業之前，以下兩個報表會顯示下列內容：

**[!DNL Marketo Measure]101：銷售機會/聯絡人（依管道）** | 概略瞭解行銷管道如何影響潛在客戶或聯絡人的建立及其額外參與。 如果您想要瞭解行銷管道的總參與度，以及哪些行銷管道正在促成Salesforce例項中的全新名稱，此報表是理想的選擇。
**[!DNL Marketo Measure]101：依識別碼的銷售機會/聯絡人** | 這會顯示每個 [!DNL Marketo Measure] 個人的故事，而且是更細微的報告，會顯示每個人和其「購買者」接觸點，無論該接觸點是在他們身為「銷售機會」或「聯絡人」時發生。

**有購買者歸因接觸點的商機** | 最後兩個」_[!DNL Marketo Measure]101..._「報告是漏斗報告的底部，顯示與機會相關的購買者歸因接觸點資料。 這些報表的主要區別在於它們是由下列專案所建置 _購買者歸因接觸點_ 這些資料與Opportunity和Opportunity層級資料（例如收入）有關。 每當您想要檢視商機或歸因收入的報告時，都應使用此報告型別。 以下兩個報表使用相同的報表型別，但是它們會依不同的量度、機會ID與行銷管道分組。 在任何自訂作業之前，以下兩個報表會顯示下列內容：

**[!DNL Marketo Measure]101：依據管道的機會** | 概略瞭解行銷管道如何影響並帶動各商機的已歸因收入。
**[!DNL Marketo Measure]101：依ID排列商機** | 此精細的報告版本顯示商機的完整歷程。 在此報表中，您可以透過各種歸因模型，檢視與商機相關聯的每個「購買者歸因」接觸點及其歸因收入。

這被視為最佳實務，處理「_[!DNL Marketo Measure]101..._&quot;以範本形式報告，滿足您的報告需求。 從上述其中一個報表開始，可節省您的時間並確保您使用的相關欄位正確無誤 [!DNL Marketo Measure] 資料。 每次對「 」進行自訂時，請務必確定您「另存新檔」_[!DNL Marketo Measure]101..._」範本，以保留報表的原始變數。

「購買者接觸點報告」資料夾旨在協助您開始使用 [!DNL Marketo Measure] 報表，若要使用可操作的報表，您必須自訂這些報表，以便根據您的報表需求量身打造。 您將需要新增必要的篩選器，以確保報告內的記錄（及其相關接觸點）與您的報告目標一致。

當您熟悉&quot;_[!DNL Marketo Measure]101..._「報告」，您可能會想要從自訂報告型別重新建立它們，以滿足更多自訂報告需求。 建立 [[!DNL Marketo Measure] 自訂報表型別](/help/marketo-measure-salesforce-reporting/new-report-types/creating-custom-marketo-measure-report-types.md) 可讓您提取其他CRM報表中常用的自訂欄位。 這將幫助您完成以下任務 [!DNL Marketo Measure] 報告至下一個層級！
