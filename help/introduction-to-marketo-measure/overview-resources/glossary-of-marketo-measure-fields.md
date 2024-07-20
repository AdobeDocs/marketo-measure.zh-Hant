---
unique-page-id: 18874586
description: Marketo Measure欄位字彙表 — Marketo Measure — 產品檔案
title: Marketo Measure欄位字彙表
exl-id: 8e23b102-6d4f-4919-b361-04d1b184e710
feature: Fundamentals
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '3213'
ht-degree: 0%

---

# Marketo Measure欄位字彙表 {#glossary-of-marketo-measure-fields}

本文提供從Marketo Measure基本套件新增至Salesforce的所有Marketo Measure欄位字彙表。 您也會找到可在哪一個物件上找到「欄位」的資訊，以及每個「欄位」填入資訊的方式。

如需每個Marketo Measure欄位都相關的物件地圖，[請按一下這裡](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md)。

[A](#a) · [B](#b) · [C](#c) · [D](#d) · [E](#e) · [F](#f) · [G](#g) · H · I · J · [K](#k) · [L](#l) · [M](#m) · N · [O](#o) · [P](#p) · [R 25} · [S](#s) · [T](#t) · [U](#u) · [V](#v) · W · X · Y · Z](#r)

## A {#a}

**帳戶** | 在Buyer Attribution Touchpoint上找到

此欄位會填入與BAT相關聯的帳戶名稱。

**廣告行銷活動ID** | 可在Buyer Touchpoint、Buyer Attribution Touchpoint上找到

有三種方式可填入此欄位：

`1)`如果接觸點來自付費搜尋工作（AdWords或BingAds），則來自廣告平台的廣告促銷活動ID將顯示在這裡。

`2)`如果接觸點並非來自付費搜尋，則會使用登陸頁面URL的utm_campaign值填入欄位。

例如`http://info.marketomeasure.com/adwords-for-lead-generation?utm_source=Event&utm_medium=booth&utm_campaign=Marketo%20Virtual%20Event%20sep2014`

在此範例中，廣告促銷活動ID會顯示： __GAId__ 2014年9月行銷虛擬事件

`3)`如果接觸點來自離線Salesforce行銷活動（會議、晚餐等），則廣告行銷活動ID將會顯示Salesforce行銷活動ID

如果以上都不含，此欄位將為空白。

**廣告行銷活動名稱** | Buyer Touchpoint、Buyer Attribution Touchpoint

`1)`如果接觸點來自付費搜尋(AdWords/Bing Ads)，則來自廣告平台的廣告行銷活動名稱將顯示在這裡。

`2)`如果接觸點並非來自付費搜尋，且登陸頁面URL包含utm_campaign的值，則會在此處填入該值。

`3)`如果接觸點來自Salesforce行銷活動，則Salesforce行銷活動的名稱將顯示在這裡。

`4)`這將以針對在您的Marketo Measure帳戶中建置的活動所產生的接觸點定義的行銷活動名稱填入。

如果以上都不含，此欄位將為空白。

**廣告行銷活動名稱(FT)** | Buyer Touchpoint

此欄位的填入方式與廣告行銷活動名稱相同。 不過，此欄位會特別顯示產生首次接觸點的廣告行銷活動的名稱。

**廣告行銷活動名稱(LC)** | Buyer Touchpoint

此欄位的填入方式與廣告行銷活動名稱相同。 不過，此欄位會明確顯示產生「銷售機會建立」接觸點的廣告促銷活動名稱。

**廣告內容** | Buyer Touchpoint、Buyer Attribution Touchpoint

`1)`如果接觸點來自付費搜尋(AdWords/Bing Ads)，欄位將會顯示廣告平台的完整廣告復本。

`2)`如果接觸點不是來自付費搜尋，此欄位會在登陸頁面URL中顯示utm_content值。

`3)`這將使用產生接觸點之相關活動的主體值填入。

如果以上皆非，此欄位將為空白。

**廣告目的地URL** | Buyer Touchpoint、Buyer Attribution Touchpoint

`1)`如果接觸點來自付費搜尋，此欄位將顯示您從搜尋引擎按一下廣告後，被導向的URL目的地。

如果接觸點並非來自付費搜尋，則欄位將為空白。

**廣告群組ID** | Buyer Touchpoint、Buyer Attribution Touchpoint

`1)`如果接觸點來自付費搜尋，則來自AdWords/Bing Ads的廣告群組ID將顯示在這裡。

如果接觸點並非來自付費搜尋，則欄位將為空白。

**廣告群組名稱** | Buyer Touchpoint、Buyer Attribution Touchpoint

`1)`如果接觸點來自付費搜尋，則來自AdWords/Bing Ads的廣告群組名稱將顯示在這裡。

如果接觸點並非來自付費搜尋，則欄位將為空白。

**廣告ID** | Buyer Touchpoint、Buyer Attribution Touchpoint

`1)`如果接觸點來自付費搜尋，則來自AdWords/Bing Ads的廣告ID將顯示在這裡。

`2)`如果接觸點是由CRM活動產生，則會將活動外部ID填入此接觸點。

如果接觸點並非來自付費搜尋，則欄位將為空白。

**歸因%自訂模型** | Buyer Attribution Touchpoint

如果您使用自訂歸因模型，此欄位會根據您在自訂模型中設定的值，顯示歸屬於接觸點的收入百分比。

如果您未使用自訂模型，此欄位將為空白。

**歸因%首次接觸** | Buyer Attribution Touchpoint

此欄位將根據首次接觸模型顯示歸屬於接觸點的收入百分比。

**歸因%已滿** | Buyer Attribution Touchpoint

此欄位將根據完整路徑模型顯示歸屬於接觸點的收入百分比。

**歸因%銷售機會建立** | Buyer Attribution Touchpoint

此欄位將根據銷售機會建立模型顯示歸屬於接觸點的收入百分比。

**歸因% U形** | Buyer Attribution Touchpoint

此欄位將會根據U形模型顯示歸屬於接觸點的收入百分比。

**歸因% W形** | Buyer Attribution Touchpoint

此欄位將會根據W形模型顯示歸屬於接觸點的收入百分比。

[按一下這裡返回頁面頂端](#top)

## B {#b}

**Marketo Measure機會金額** | Salesforce機會

如果您使用自訂「金額」欄位來報告Opportunity收入，Marketo Measure將無法讀取這些自訂「金額」欄位。 Marketo Measure機會金額是隱藏的欄位，用來建立工作流程，讓Marketo Measure可讀取機會上的自訂金額欄位。

**瀏覽器** | Buyer Touchpoint、Buyer Attribution Touchpoint

此欄位會顯示網頁工作階段期間使用的網頁瀏覽器型別(Chrome、Safari、Firefox等)。

[按一下這裡返回頁面頂端](#top)

## C {#c}

**連絡人** | Buyer Touchpoint、Buyer Attribution Touchpoint

欄位會顯示接觸點所屬的聯絡人。

**計數 — 自訂模型** | Buyer Attribution Touchpoint

如果您使用自訂歸因模型，此欄位會以小數形式顯示根據您自訂模型中設定的值指定給接觸點的收入點數百分比。

如果您未使用自訂模型，此欄位將為空白。

**計數 — 自訂模型** | Buyer Touchpoint

如果您使用自訂歸因模型，此欄位會根據您在自訂模型中設定的值，以小數格式顯示指定給接觸點的歸因點數百分比。 由於此欄位與Buyer Touchpoint物件有關，因此並非收入評分的反映，而只是歸因評分。

如果您未使用自訂模型，此欄位將為空白。

**計數 — 首次接觸** | Buyer Attribution Touchpoint

此欄位以小數形式顯示根據首次接觸模型給予接觸點的收入點數百分比。

**計數 — 首次接觸** | Buyer Touchpoint

此欄位以小數形式顯示根據首次接觸模型給予接觸點的歸因點數百分比。 如果接觸點是首次接觸，此欄位一律為1.0 （表示100%歸因評分）。 如果接觸點不是首次接觸，此欄位將一律為0 （表示0 %歸因評分）。

由於此欄位與Buyer Touchpoint物件有關，因此並非收入評分的反映，而只是歸因評分。

**計數 — 完整路徑** | Buyer Attribution Touchpoint

此欄位以小數形式顯示根據完整路徑模型指定給接觸點的收入百分比。

**計數 — 建立銷售機會接觸** | Buyer Attribution Touchpoint

此欄位以小數形式顯示根據「銷售機會建立模型」指定給接觸點的收入點數百分比。

**計數 — 建立銷售機會接觸** | Buyer Touchpoint

此欄位以小數形式顯示根據「銷售機會建立模型」指定給接觸點的歸因點數百分比。 如果接觸點是銷售機會建立接觸，此欄位一律為1.0 （表示100%歸因評分）。 如果接觸點不是「銷售機會建立」接觸，此欄位將一律為0 （表示0%歸因評分）。

由於此欄位與Buyer Touchpoint物件有關，因此並非收入評分的反映，而只是歸因評分。

**計數 — U形** | Buyer Attribution Touchpoint

此欄位以小數形式顯示根據U形模型給予接觸點的收入點數百分比。

**計數 — U形** | Buyer Touchpoint

此欄位以小數形式顯示根據U形模型給予接觸點的歸因點數百分比。 在U形模型中，評分會由首次接觸、銷售機會建立接觸以及首次接觸與銷售機會建立接觸之間發生的任何中介表單提交所分攤。

由於此欄位與Buyer Touchpoint物件有關，因此並非收入評分的反映，而只是歸因評分。

**計數 — W形** | Buyer Attribution Touchpoint

此欄位以小數形式顯示根據W形模型給予接觸點的點數百分比。

[按一下這裡返回頁面頂端](#top)

## 第{#d}天

報告日期 | Marketo Measure ABTest， Marketo Measure活動

Marketo Measure事件 — 使用者在您的網站上採取特定動作，並啟用事件的日期

Marketo Measure ABTest — 使用者參與您網站上的A/B測試的日期

[按一下這裡返回頁面頂端](#top)

## E {#e}

**事件名稱** | Marketo Measure事件

此欄位會顯示觸發事件的動作名稱（即頁面檢視）。

**事件值** | Marketo Measure事件

事件的說明（即首頁）

**實驗名稱** | Marketo Measure ABTest

此欄位會顯示實驗的名稱（即試用按鈕）

**實驗識別碼** |Marketo Measure AB測試

每個實驗的唯一識別碼

[按一下這裡返回頁面頂端](#top)

## F {#f}

表單URL | Buyer Touchpoint、Buyer Attribution Touchpoint

此欄位將顯示發生表單填寫的頁面URL的簡短版本（無UTM引數）

表單URL — 原始 | Buyer Touchpoint、Buyer Attribution Touchpoint

此欄位顯示表單填寫發生的整個頁面URL，包括UTM引數

[按一下這裡返回頁面頂端](#top)

## G {#g}

地理城市 | Buyer Touchpoint、Buyer Attribution Touchpoint

此欄位會顯示潛在客戶/連絡人造訪您網站的城市名稱。 這是透過反向IP查詢來完成。

地理國家/地區 | Buyer Touchpoint、Buyer Attribution Touchpoint

此欄位會顯示負責人/連絡人造訪您網站的國家/地區。 這是透過反向IP查詢來完成。

地理區域 | Buyer Touchpoint、Buyer Attribution Touchpoint

此欄位會顯示潛在客戶/連絡人造訪您網站的地區或州。 這是透過反向IP查詢來完成。

[按一下這裡返回頁面頂端](#top)

## K {#k}

**關鍵字識別碼** | Buyer Touchpoint、Buyer Attribution Touchpoint

如果接觸點來自付費搜尋，此欄位將會顯示廣告平台(Adwords/BingAds)的關鍵字ID。

如果此接觸點並非來自付費搜尋，則此欄位將為空白。

**關鍵字MatchType** | Buyer Touchpoint、Buyer Attribution Touchpoint

如果接觸點來自付費搜尋，此欄位將會顯示廣告平台(Adwords/Bing)的相符型別。

**關鍵字文字** | Buyer Touchpoint、Buyer Attribution Touchpoint

`1)`如果接觸點來自付費搜尋，此欄位將會顯示廣告平台(Adwords/BingAds)的關鍵字文字，或登陸頁面URL中_bk引數的值。

例如`http://info.marketomeasure.com/intro-guide-b2b-marketing-attribution?_bt=12345678&_bk=marketing%20attribution&_bm=p&gclid=ABc123def456ghi789jkl`

`2)`如果接觸點並非來自付費搜尋，此欄位將會顯示登陸頁面URL的utm_term值。

`http://www.marketomeasure.com/blog/lead-generation?utm_source=linkedin&utm_medium=Social&utm_campaign=ABC%20Blog&utm_content=Lead%20Gen&utm_term=lead%20gen`。

如果接觸點並非來自付費搜尋，或沒有utm_term值，則此欄位將為空白。

[按一下這裡返回頁面頂端](#top)

## L {#l}

**登陸頁面** | Buyer Touchpoint、Buyer Attribution Touchpoint

此欄位會顯示網頁工作階段期間造訪的第一個網頁的URL縮短版本（無UTM引數）。

**登陸頁面 — 原始** | Buyer Touchpoint、Buyer Attribution Touchpoint

此欄位會顯示網頁工作階段期間第一個造訪之網頁的整個URL （包括UTM引數）。

**銷售機會** | Buyer Touchpoint， Marketo Measure人員

此欄位會顯示接觸點所屬的銷售機會名稱。

[按一下這裡返回頁面頂端](#top)

## M {#m}

**行銷管道** | Buyer Touchpoint、Buyer Attribution Touchpoint

此欄位會顯示接觸點所屬行銷活動或行銷管道的一般群組（即付費搜尋、直接、社交等）。 系統會根據您在Marketo Measure應用程式中設定管道的方式，將接觸點分組。 如需有關行銷管道的詳細資訊，或如何設定您的管道，[請按一下這裡](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)。

**行銷管道 — 路徑** | Buyer Touchpoint、Buyer Attribution Touchpoint

此欄位會顯示行銷管道，以及接觸點所屬的子管道。 在以下範例中，「行銷管道 — 路徑」是Social.Linkedin，其中行銷管道是Social，而子管道是LinkedIn。

![](assets/1-3.png)

**Medium** | Buyer Touchpoint、Buyer Attribution Touchpoint

`1)`如果接觸點來自付費搜尋，則來自Adwords/BingAds的媒體將顯示在這裡（即CPC）。

`2)`如果接觸點並非來自付費搜尋，此欄位會顯示登陸頁面URL的utm_medium值。

`3)`如果接觸點來自離線行銷活動，此欄位將會在Salesforce行銷活動中顯示「型別」欄位。

`4)`這將使用產生接觸點之相關活動的活動型別值填入。

如果上述動作都無法執行，Marketo Measure會自動設定Medium值。

[按一下這裡返回頁面頂端](#top)

O

**商機** | Buyer Attribution Touchpoint

此欄位會顯示BAT所屬的機會。

[按一下這裡返回頁面頂端](#top)

P

**平台** | Buyer Touchpoint、Buyer Attribution Touchpoint

此欄位會顯示電腦或電話的型別，以及在網頁工作階段期間使用的作業系統型別。

[按一下這裡返回頁面頂端](#top)

R

**反向連結頁面** | Buyer Touchpoint、Buyer Attribution Touchpoint

此欄位會顯示潛在客戶/聯絡人上次前往您網站的網頁之URL （不含UTM引數）。

例如：

- 如果接觸點來自付費/有機搜尋，欄位會顯示搜尋引擎的URL

- 如果接觸點來自Social，欄位會顯示社交網站的URL (即LinkedIn)

**反向連結頁面 — 原始** | Buyer Touchpoint、Buyer Attribution Touchpoint

此欄位會顯示與反向連結頁面相同的資訊，除了此欄位會顯示整個反向連結URL （包括UTM引數）。

**收入 — 自訂模型** | Buyer Attribution Touchpoint

如果您使用自訂歸因模型，此欄位會顯示根據您在自訂模型中設定的歸因百分比，歸因到接觸點的美元收入金額。

如果您未使用自訂模型，則金額將為0。

**收入 — 首次接觸** | Buyer Attribution Touchpoint

此欄位會顯示根據首次接觸模型中的歸因百分比，歸因到接觸點的美元收入金額。

**收入 — 完整路徑** | Buyer Attribution Touchpoint

此欄位會顯示根據完整路徑模型中的歸因百分比，歸因到接觸點的美元收入金額。

**收入 — 潛在客戶建立接觸** | Buyer Attribution Touchpoint

此欄位會顯示根據潛在客戶建立模型中的歸因百分比，歸因到接觸點的美元收入金額。

**收入 — U形** | Buyer Attribution Touchpoint

此欄位會顯示根據U形模型中歸因百分比歸因於接觸點的美元收入金額。

**收入 — W形** | Buyer Attribution Touchpoint

此欄位會顯示根據W形模型中歸因百分比歸因於接觸點的美元收入金額。

[按一下這裡返回頁面頂端](#top)

S

**Salesforce行銷活動** | Buyer Touchpoint、Buyer Attribution Touchpoint

此欄位會顯示接觸點所屬的Salesforce Campaign。

**搜尋片語** | Buyer Touchpoint、Buyer Attribution Touchpoint

如果接觸點來自付費或自然搜尋，此欄位將顯示輸入搜尋引擎的搜尋詞語。 然而，基於隱私權考量，這項資訊通常無法取得。

**區段** | Buyer Attribution Touchpoint

此欄位會顯示接觸點所屬的區段。 這將取決於您在Marketo Measure應用程式中設定分段規則的方式。

[按一下這裡返回頁面頂端](#top)

T

**接觸點日期** | Buyer Touchpoint、Buyer Attribution Touchpoint

`1)`如果接觸點來自線上來源，此欄位會顯示接觸點發生的日期和時間。

`2)`如果接觸點來自離線事件，此欄位將會顯示Salesforce Campaign中設定的日期與時間，或是來自Campaign同步規則中選取的日期欄位。

`3)`如果接觸點來自活動，此欄位將顯示在活動規則中選取為接觸點日期的欄位的日期和時間。

**接觸點日期（英尺）** | Buyer Touchpoint

這是與接觸點日期相同的欄位，不過此欄位會特別顯示首次接觸點發生的日期和時間。

**接觸點日期(LC)** | Buyer Touchpoint

這是與接觸點日期的相同欄位，不過此欄位會特別顯示「銷售機會建立」接觸點發生的日期和時間。

**接觸點位置** | Buyer Touchpoint、Buyer Attribution Touchpoint

此欄位會顯示接觸點的位置。 接觸點的位置反映了客戶歷程中的主要里程碑接觸點（即FT、Form、LC、OC、Closed）。 接觸點的位置取決於它發生在客戶歷程中的時間，而單一接觸點可以有多個位置。 不同的接觸點位置如下：

首次接觸(FT) — 某人第一次與您的品牌進行行銷互動

銷售機會建立(LC) — 最先知道的行銷互動（通常是表單提交或Salesforce促銷活動包含）

表單 — 訪客填寫線上表單時

機會建立(OC) — 建立Opp時最近的行銷互動

已關閉 — Opp關閉時最接近的行銷互動（獲勝或失敗）

**接觸點Source** | Buyer Touchpoint、Buyer Attribution Touchpoint

`1)`如果接觸點來自付費搜尋，此欄位將會顯示廣告平台的名稱(AdWords/BingAds)

`2)`如果接觸點來自有機搜尋，此欄位將顯示搜尋引擎的名稱

`3)`如果不是#1或#2，且utm_source值存在於接觸點的登陸頁面URL中，則會在此處顯示該值

`4)`如果接觸點產生自CRM Campaign，此將填入為CRM Campaign。

`5)`如果接觸點是由CRM活動產生，此將填入為CRM活動。

如果以上皆非，此欄位將會填入為「網頁直接」或「網頁」。

**接觸點Source (FT)** | Buyer Touchpoint

這是與接觸點Source相同的欄位，不過此欄位會明確顯示首次接觸接觸點的來源。

**接觸點Source (LC)** | Buyer Touchpoint

這是與接觸點Source相同的欄位，不過此欄位會明確顯示「銷售機會建立」接觸點的來源。

**接觸點型別** | 可在Buyer Touchpoint和Buyer Attribution Touchpoint上找到。

此欄位將顯示接觸點的互動型別。 它會顯示為：JavaScript接觸點的網頁瀏覽、網頁表單或網頁聊天。 若為CRM Campaign接觸點，將顯示為CRM。 它會填入活動接觸點的任務或事件型別。

[按一下這裡返回頁面頂端](#top)

U

**唯一識別碼** | Buyer Touchpoint、Buyer Attribution Touchpoint

與每個接觸點相關聯的唯一ID

**使用者ID** | Marketo Measure ABTest

以最佳化方式提供每次使用的唯一識別碼

[按一下這裡返回頁面頂端](#top)

## 版本{#v}

**變數** | Marketo Measure ABTest

A/B測試的變數名稱

**變數ID** | Marketo Measure ABTest

每個A/B測試變數的唯一識別碼。

[按一下這裡返回頁面頂端](#top)
