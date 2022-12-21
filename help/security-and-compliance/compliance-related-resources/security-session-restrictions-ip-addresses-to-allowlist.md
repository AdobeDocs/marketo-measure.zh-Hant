---
unique-page-id: 18874706
description: 安全工作階段限制 — 允許清單的IP位址 — Marketo測量 — 產品檔案
title: 安全會話限制 — 允許清單的IP地址
exl-id: aaf5190f-893c-4872-8d03-93f516e70a59
source-git-commit: b9d9e3110e87be0d6311c17b0ef76dfad8735a00
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 3%

---

# 安全會話限制：允許清單的IP位址 {#security-session-restrictions-ip-addresses-to-allowlist}

如果有 [會話安全設定](https://help.salesforce.com/articleView?id=admin_sessions.htm&amp;type=0)已設定{target=&quot;_blank&quot;} ，以防止特定IP位址推送/提取資料至您的 [!DNL Salesforce] 例項中，我們需要列出下列IP範圍，允許 [!DNL Marketo Measure] 將資料推送至 [!DNL Salesforce]:

* 52.162.84.192 - 52.162.84.207
* 23.100.229.112 - 23.100.229.127
* 20.186.163.0 - 20.186.163.15

若要新增 [!DNL Marketo Measure] 在Salesforce中，按一下「IP到信任的IP範圍」 **[!UICONTROL Setup]** > **[!UICONTROL Administration Setup]** > **[!UICONTROL Security Controls]** > **[!UICONTROL Network Access]** > **[!UICONTROL New]**.

![](assets/1.png)
