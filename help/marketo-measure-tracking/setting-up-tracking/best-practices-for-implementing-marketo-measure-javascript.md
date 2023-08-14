---
description: 實作的最佳作法 [!DNL Marketo Measure] JavaScript - [!DNL Marketo Measure]  — 產品檔案
title: 實作的最佳作法 [!DNL Marketo Measure] JavaScript
exl-id: 0359ad27-81e8-4902-a23a-49a5646a44d0
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 0%

---

# 實作的最佳作法 [!DNL Marketo Measure] JavaScript {#best-practices-for-implementing-marketo-measure-javascript}

## 概觀 {#overview}

此 [!DNL Marketo Measure] JavaScript會追蹤您的網站訪客數位行銷互動，是 [!DNL Marketo Measure] 能夠建立線上接觸點資料。 擁有 [!DNL Marketo Measure] 在整個網站上正確且完整部署的JavaScript，可確保收集的工作階段資料產生精確的接觸點資料。

部署中的不一致 [!DNL Marketo Measure] JavaScript會導致工作階段資料中斷，進而導致下列情況：

* 不正確的管道/子管道歸因
* 來源資料遺失
* 高水準的錯誤直接流量
* 不一致的報表

[!DNL Marketo Measure] JavaScript是您的 [!DNL Marketo Measure] 帳戶和成功金鑰！

## 最佳實務 {#best-practice}

實作及管理您的 [!DNL Marketo Measure] JavaScript，請記住以下最佳實務。

* 確認您的所有網域都列在中 [!DNL Marketo Measure] 帳戶
   * 如果您對網域有任何疑慮，請聯絡支援人員
* 在所有頁面上部署JavaScript。
   * 僅將JavaScript放在某些頁面上會導致工作階段資料中斷，進而導致不正確 [!DNL Marketo Measure] 資料
* 對於您網站上不想從中建立接觸點的表單，請務必新增 [!DNL Marketo Measure] 排除指令碼
   * 此排除指令碼將確保 [!DNL Marketo Measure] 工作階段資料不會中斷，而來源資料仍會保留
      * 要隱藏的常見表單範例有：
         * 客戶登入
         * 忘記密碼表單
         * 取消訂閱表單
         * 職涯申請表
* 檢閱新增的「其他考量事項」和「Forms格外留意」章節 [!DNL Marketo Measure] 下面列出的指令碼資源以檢查任何可能需要特殊處理的情境

## 維護最佳實務 {#best-practice-for-maintenance}

當設定 [!DNL Marketo Measure] 初次實施期間涵蓋JavaScript，若變更您的網站或管理網站的團隊，可能導致以下作業中斷： [!DNL Marketo Measure] 追蹤。 建議您確認 [!DNL Marketo Measure] JavaScript每年會正確完整部署一次。 此外，如果您的組織有任何型別的網站變更通訊協定檔案，請確保有一部分說明 [!DNL Marketo Measure] 所有新頁面都應保留/新增JavaScript。

觸發檢閱JavaScript設定的其他原因包括……

* 您行銷團隊中的營業額
* 網站結構的變更和更新
* 網站移轉
* 您的網域變更
* 贏取其他公司及其網頁屬性
