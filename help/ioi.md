---
title: IOI
description: 模式偵測器程式碼說明頁面
exl-id: b6c9d11f-5189-4799-98c0-c2699dfe3f40
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 0%

---

# IOI {#ioi}

內部Oak匯入

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_overview"
>title="內部Oak匯入"
>abstract="IOI程式碼可識別客戶使用內部Oak套件，並透過OSGi匯入。 這些套件通常匯出時不含任何特定版本，且僅供其他Oak套件組合或低階AEM服務使用。"

`IOI` 識別客戶使用內部Oak套件，並透過OSGi匯入。這些套件通常匯出時不含任何特定版本，且僅供其他Oak套件組合或低階AEM服務使用。

其中一些由`com.adobe.granite.repository`使用，後者在啟動期間為AEM設定儲存庫。 另一個範例是`com.adobe.granite.maintenance.oak`Adobe套件組合，包住並提供Oak維護工作。

## 可能的影響和風險{#implications-and-risks}

* 在未來的AEM版本中，內部匯出可能會直接根據Oak移除，造成相依性中斷和非作用中套件組合。
* 內部匯出中的API可能會變更。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_guidance"
>title="實施指南"
>abstract="客戶應檢閱其自訂程式碼，以識別此類API的使用情況，並重新調整以與AEM作為Cloud Service相容。 請洽詢Adobe支援以取得說明和說明"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 使用Sling資源API（或JCR API），而非低階存取權。
* 請根據不屬於任何公用API或SPI的內部套件來避免。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決問題。
