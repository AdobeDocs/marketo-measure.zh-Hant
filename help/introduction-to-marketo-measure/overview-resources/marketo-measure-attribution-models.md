---
unique-page-id: 18874568
description: Marketo Measure歸因模型 — Marketo Measure — 產品檔案
title: Marketo Measure歸因模型
exl-id: d8f76f29-e7c9-4b2d-b599-e80fd93c4687
source-git-commit: 0aa263053aa8dd804b03a67ab446dc0cda3850c5
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 0%

---

# Marketo Measure歸因模型 {#marketo-measure-attribution-models}

Marketo Measure提供6種歸因模型：

* 首次接觸
* 銷售機會建立
* U形
* W形
* 完整路徑
* 自訂模型

這些模型的複雜性各不相同。 首次接觸和銷售機會建立是我們簡單的單次接觸模型。 其餘四種是更複雜、多點接觸的模型。 Marketo Measure的歸因模型結構反映了客戶歷程中發生的四個主要接觸點：

* 首次接觸(FT)
* 銷售機會建立(LC)
* 機會建立(OC)
* 閉元交易(CW)

![](assets/1-1.png)

在 **單點接觸模型**，則歸因評分只會歸因於一個里程碑接觸點，因此名稱為「單次接觸」。
在 **多觸點模型**，則大部分歸因評分會指派給兩個或多個里程碑接觸點。 剩餘評分歸因於里程碑接觸點之間發生的接觸點。

接下來的幾節將說明每個歸因模型，以及歸因評分的指派方式。

## 單次接觸模型 {#single-touch-models}

**首次接觸模型**

首次接觸模型只著重於銷售機會與您組織的首次互動。 此模型會將100%的歸因評分歸因於銷售機會第一次得知您的公司即首次接觸(FT)時。

假設Kate首次透過Adwords廣告造訪www.adobe.com並檢視白皮書。 Adwords管道將從該Opportunity獲得100%的歸因評分。

![](assets/2.png)

**銷售機會建立模型**

潛在客戶提供其聯絡資訊並成為銷售機會時，「銷售機會建立」模型會將100%的歸因評分歸因於LC接觸點。

繼續前一個範例，在Kate透過Adwords首次造訪www.adobe.com後，Austin透過Linkedin貼文造訪網站。 Austin填寫表格，成為Lead。 在此模型中，Linkedin將獲得100%的歸因評分。

![](assets/3.png)

## 多點接觸模型 {#multi-touch-models}

多點接觸模型適用於更長、更複雜的銷售週期。 如果某個帳戶/公司的數個人員參與購買者歷程，這些模型就特別實用。

**U形模型**

U形模型將重點放在FT和LC接觸點上。 在此模型中，英國《金融時報》和LC接觸點各獲得50%的收入評分。

Kate透過Adwords廣告首次造訪www.adobe.com ，將獲得50%的歸因評分。 剩下的50%將歸因於Linkedin的帖子，該帖子驅使奧斯汀填寫表格，成為領導。

![](assets/4.png)

**W形模型**

W形模型中包含三個里程碑接觸點。 在此模型中，FT、LC和OC接觸點各歸因於歸因評分的30%。 其餘10%會按比例歸因於三個里程碑接觸點之間發生的任何中間接觸點。

凱特和奧斯丁向同事希拉里提到Marketo Measure。 她通過谷歌搜索找到了一個內容，並填寫了表格。 之後，Austin會收到電子郵件，供網路研討會註冊，並填寫網站上的註冊表。 Kate與一個銷售代表談了一談Marketo Measure產品。

希拉里收到一封包含定價頁面連結的電子郵件，並瀏覽該頁面。 然後為其帳戶建立Opportunity。 希拉里訪問定價頁面的Web訪問獲得了機會建立的評分，因為它是最接近機會建立日期的最接近市場營銷交互。 每個里程碑接觸點都會獲派30%的歸因評分，而中介接觸點則歸因於其餘10%。

![](assets/5.png)

**完整路徑模型**

完整路徑模型包含所有四個里程碑接觸點。 英國《金融時報》、LC、OC和CW各獲得22.5%的收入評分，其餘10%在中間環節平均分配。

機會創造後，凱特、奧斯丁和希拉里決定向CMO伊麗莎白推銷Marketo Measure。 Elizabeth出席Marketo Measure主辦的會議。 Kate看到了Linkedin的一篇關於案例研究的帖子，並填寫了一份表格以下載內容。 伊麗莎白參加了由Marketo Measure主辦的銷售晚宴。 晚飯後，她決定購買Marketo Measure，成為客戶。 在此情況下，銷售晚宴將歸因於已結交交易的收入評分的22.5%。 英國《金融時報》、LC和OC接觸點也分別獲得22.5%的評分。 中介接觸點會平均分配其餘10%的收入評分。

![](assets/6.png)

**自訂歸因模型**

Marketo Measure也提供自訂歸因模型，讓使用者可以選擇要納入其模型中的接觸點或自訂階段。 此外，使用者還能控制歸因於這些接觸點和階段的百分比。
