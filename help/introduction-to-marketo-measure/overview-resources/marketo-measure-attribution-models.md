---
unique-page-id: 18874568
description: Marketo Measure歸因模型 — Marketo Measure — 產品檔案
title: Marketo Measure歸因模型
exl-id: d8f76f29-e7c9-4b2d-b599-e80fd93c4687
feature: Attribution
source-git-commit: aa12df4d0c77cdc677f78bcab19497806927ec2b
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 0%

---

# Marketo Measure歸因模型 {#marketo-measure-attribution-models}

Marketo Measure提供六種型別的歸因模型：

* 首次接觸
* 銷售機會建立
* U形
* W形
* 完整路徑
* 自訂模型

這些模型的複雜度各異。 首次接觸和銷售機會建立是我們的簡單單一接觸模型。 其餘四個是我們更複雜的多點觸控模型。 Marketo Measure歸因模型的結構反映了客戶歷程中發生的四個主要接觸點：

* 首次接觸(FT)
* 銷售機會建立(LC)
* 機會建立(OC)
* 成交單交易(CW)

![](assets/1-1.png)

在 **單次接觸模型**，歸因點數只會歸因至一個里程碑接觸點，因此命名為「單次接觸」。
在 **多重觸控模型**，大部分歸因點數會指派給兩個或多個里程碑接觸點。 剩餘的點數會歸因於發生在里程碑接觸點之間的接觸點。

接下來的幾個小節涵蓋每個歸因模型，以及歸因評分的指派方式。

## 單次接觸模型 {#single-touch-models}

**首次接觸模型**

首次接觸模型只會著重於銷售機會與您的組織進行的首次互動。 此模型將100%的歸因點數歸因於潛在客戶第一次知道您的公司時，即首次接觸(FT)。

說凱特造訪 `www.adobe.com` 首次透過Adwords廣告和檢視白皮書。 Adwords管道將會從該Opportunity接收100%的歸因評分。

![](assets/2.png)

**潛在客戶建立模型**

當潛在客戶提供其聯絡資訊並成為潛在客戶時，「銷售機會建立」模型會將100%的歸因點歸因於LC接觸點。

繼續上一個範例，在Kate第一次造訪後 `www.adobe.com` 透過Adwords，Austin透過Linkedin貼文造訪網站。 Austin填寫表單並成為Lead。 在此模型中，Linkedin會獲得100%的歸因評分。

![](assets/3.png)

## 多重觸控模型 {#multi-touch-models}

多重觸控模式適用於更長、更複雜的銷售週期。 如果某個帳戶/公司的幾個人涉及購買者的歷程，這些模型會特別有用。

**U形模型**

U形模型同時針對FT和LC接觸點。 在此模型中，FT和LC接觸點各獲得50%的收入評分。

凱特第一次造訪 `www.adobe.com` 透過Adwords廣告接收50%的歸因評分。 其餘50%將歸因於Linkedin促使奧斯汀填寫表單並成為潛在客戶的貼文。

![](assets/4.png)

**W形模型**

三個里程碑接觸點包含在W形模型中。 在此模型中，FT、LC和OC接觸點各歸因於30%的歸因點數。 其餘的10%會按比例歸因到三個里程碑接觸點之間發生的任何中介接觸點。

凱特和奧斯汀向同事希拉里提起Marketo Measure。 她透過Google搜尋找到內容片段，並填寫表格。 稍後，Austin會收到網路研討會註冊電子郵件，並填寫網站上的登錄檔格。 Kate與銷售代表討論有關Marketo Measure產品。

Hillary會收到含有定價頁面連結的電子郵件，並瀏覽該頁面。 然後為其帳戶建立機會。 Hillary對定價頁面的網頁瀏覽會獲得「機會建立」的評分，因為這是最接近「機會建立」日期的行銷互動。 每個里程碑接觸點都會獲得30%的歸因點數，而中介接觸點會獲得剩餘10%的歸因點數。

![](assets/5.png)

**完整路徑模型**

完整路徑模型包含所有四個里程碑接觸點。 FT、LC、OC和CW各獲得22.5%的收入評分，其餘10%平均分配給中介接觸。

機會建立後，Kate、Austin和Hillary決定將Marketo Measure推介給他們的CMO Elizabeth。 Elizabeth出席由Marketo Measure主辦的會議。 Kate在Linkedin上看到有關個案研究的文章，並填寫表格以下載內容。 伊麗莎白出席Marketo Measure主持的銷售晚宴。 晚餐後，她決定購買Marketo Measure並成為客戶。 在此案例中，銷售晚宴會歸因於已結束交易的22.5%收入點數。 FT、LC和OC接觸點也各獲得22.5%的評分。 中介接觸點會平均指派剩餘的10%收入評分。

![](assets/6.png)

**自訂歸因模型**

Marketo Measure也提供自訂歸因模型，讓使用者選擇要在其模型中包含哪些接觸點或自訂階段。 此外，使用者還能控制歸因到這些接觸點和階段的歸因點數百分比。 如果Opportunity沒有專門的中間接觸，該百分比將平均分配到其他位置。
