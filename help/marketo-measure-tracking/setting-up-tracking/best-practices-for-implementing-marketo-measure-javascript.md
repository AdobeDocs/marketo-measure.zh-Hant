---
description: 實作 [!DNL Marketo Measure] JavaScript - [!DNL Marketo Measure]的最佳作法
title: 實作 [!DNL Marketo Measure] JavaScript的最佳作法
exl-id: 0359ad27-81e8-4902-a23a-49a5646a44d0
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---

# 實作[!DNL Marketo Measure] JavaScript的最佳實務 {#best-practices-for-implementing-marketo-measure-javascript}

## 概觀 {#overview}

[!DNL Marketo Measure] JavaScript會追蹤您的網頁訪客數位行銷互動，是[!DNL Marketo Measure]建立線上接觸點資料的能力的關鍵。 在整個網站上正確且全面地部署[!DNL Marketo Measure] JavaScript，可確保收集的工作階段資料產生正確的接觸點資料。

[!DNL Marketo Measure] JavaScript部署中的不一致會導致工作階段資料中斷，進而導致下列情形：

* 不正確的管道/子管道歸因
* 來源資料遺失
* 高水準的錯誤直接流量
* 不一致的報表

[!DNL Marketo Measure] JavaScript是您[!DNL Marketo Measure]帳戶的基本部分，也是您成功的關鍵！

## 最佳實務 {#best-practice}

實施及管理[!DNL Marketo Measure] JavaScript時，請記住下列最佳實務。

* 確認您的[!DNL Marketo Measure]帳戶中列出了您的所有網域
   * 如果您對網域有任何疑慮，請聯絡支援服務
* 在所有頁面中部署JavaScript。
   * 僅將JavaScript放在某些頁面上會導致工作階段資料中斷，進而導致[!DNL Marketo Measure]資料不正確
* 對於您網站上您不想要建立接觸點的表單，請務必新增[!DNL Marketo Measure]排除指令碼
   * 此排除指令碼將確保[!DNL Marketo Measure]工作階段資料不會中斷，並且來源資料會保留在適當位置
      * 要隱藏的常見表單範例有：
         * 客戶登入
         * 忘記密碼表單
         * 取消訂閱表單
         * 職涯申請表
* 檢閱下列新增[!DNL Marketo Measure]指令碼資源的「其他考量事項」和「Forms格外留意」區段，以檢查任何可能需要特殊處理的情境

## 維護最佳實務 {#best-practice-for-maintenance}

雖然[!DNL Marketo Measure] JavaScript的設定涵蓋於初始實作期間，但變更您的網站或管理網站的團隊可能會導致[!DNL Marketo Measure]追蹤中斷。 建議您確認已正確且完整地部署[!DNL Marketo Measure] JavaScript，每年一次。 此外，如果您的組織有任何型別的網站變更通訊協定檔案，請確定有一部分說明[!DNL Marketo Measure] JavaScript應保留/新增至所有新頁面。

可能觸發檢閱JavaScript設定的其他原因包括……

* 您行銷團隊中的營業額
* 網站結構的變更和更新
* 網站移轉
* 您的網域變更
* 贏取其他公司及其網頁屬性
