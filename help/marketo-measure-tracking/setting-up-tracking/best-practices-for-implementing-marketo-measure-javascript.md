---
description: 實作最佳實務 [!DNL Marketo Measure] JavaScript - [!DNL Marketo Measure]  — 產品檔案
title: 實作最佳實務 [!DNL Marketo Measure] JavaScript
exl-id: 0359ad27-81e8-4902-a23a-49a5646a44d0
source-git-commit: cf144eb4bc9282ae6a260acd3735f24644292a19
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 0%

---

# 實作最佳實務 [!DNL Marketo Measure] JavaScript {#best-practices-for-implementing-marketo-measure-javascript}

## 總覽 {#overview}

此 [!DNL Marketo Measure] JavaScript會追蹤您的網頁訪客數位行銷互動，且是 [!DNL Marketo Measure] 可建立線上接觸點資料。 擁有 [!DNL Marketo Measure] 在整個網站上正確且全面部署的JavaScript將確保收集的工作階段資料會產生準確的接觸點資料。

部署時不一致 [!DNL Marketo Measure] JavaScript會在工作階段資料中造成中斷，進而導致下列結果：

* 管道/子管道歸因不正確
* 源資料丟失
* 高級別的錯誤直接流量
* 不一致的報表

[!DNL Marketo Measure] JavaScript是您 [!DNL Marketo Measure] 帳戶和成功的關鍵！

## 最佳實務 {#best-practice}

關於實作和管理 [!DNL Marketo Measure] JavaScript，請牢記下列最佳實務。

* 確認您的所有網域皆列在 [!DNL Marketo Measure] 帳戶
   * 如果您對您的網域有任何疑慮，請聯絡支援
* 在所有頁面上部署JavaScript。
   * 僅將JavaScript放在特定頁面上，會在您的工作階段資料中造成中斷，而造成不正確 [!DNL Marketo Measure] 資料
* 若為您網站上不想建立接觸點的表單，請務必新增 [!DNL Marketo Measure] 排除指令碼
   * 此排除指令碼將確保 [!DNL Marketo Measure] 不會中斷工作階段資料，且來源資料仍維持不變
      * 要隱藏的常見表單範例包括：
         * 客戶登入
         * 忘記密碼表單
         * 取消訂閱表單
         * 職業申請表
* 查看新增中的「其他考量事項」和「Forms要額外注意」小節 [!DNL Marketo Measure] 以下列出的指令碼資源，以檢查是否有任何可能需要特殊處理的情況

## 維護最佳實務 {#best-practice-for-maintenance}

若 [!DNL Marketo Measure] 初始實作期間會涵蓋JavaScript，若您的網站或管理JavaScript的團隊有所變更，可能會導致 [!DNL Marketo Measure] 追蹤。 建議您確認 [!DNL Marketo Measure] JavaScript每年正確且全面部署一次。 此外，如果貴組織的網站有任何類型的變更通訊協定檔案，請確定有部分說明 [!DNL Marketo Measure] JavaScript應保留/新增至所有新頁面。

其他可能觸發審核的原因包括……

* 行銷團隊的營業額
* 變更和更新您的網站結構
* 站點遷移
* 網域的變更
* 其他公司的收購及其Web屬性
