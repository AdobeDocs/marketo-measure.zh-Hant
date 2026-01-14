---
description: 列出Salesforce IP範圍以允許清單，以便在執行工作階段限制時Marketo Measure可以連線
title: 安全性工作階段限制 — 允許清單的IP位址
exl-id: aaf5190f-893c-4872-8d03-93f516e70a59
feature: Tracking
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 0%

---

# 安全性工作階段限制：允許清單的IP位址 {#security-session-restrictions-ip-addresses-to-allowlist}

如果已經有[工作階段安全性設定](https://help.salesforce.com/articleView?id=admin_sessions.htm&type=0){target="_blank"}防止特定IP位址推送/提取資料到您的[!DNL Salesforce]執行個體，我們將需要下列IP範圍加入允許清單，以允許[!DNL Marketo Measure]推送資料到[!DNL Salesforce]：

* 52.162.84.192 - 52.162.84.207
* 23.100.229.112 - 23.100.229.127
* 20.186.163.0 - 20.186.163.15

若要將[!DNL Marketo Measure]個IP新增至Salesforce中的受信任IP範圍，請按一下&#x200B;**[!UICONTROL Setup]** > **[!UICONTROL Administration Setup]** > **[!UICONTROL Security Controls]** > **[!UICONTROL Network Access]** > **[!UICONTROL New]**。

![](assets/compliance-resources-1.png)
