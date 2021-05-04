---
title: IOI
description: 模式偵測器程式碼說明頁面
exl-id: b6c9d11f-5189-4799-98c0-c2699dfe3f40
translation-type: tm+mt
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
>abstract="IOI程式碼可識別客戶對內部Oak套件的使用，並透過OSGi匯入。 它們通常匯出時不含任何特定版本，僅供其他Oak組合或低階服務使AEM用。"

`IOI` 識別客戶對內部Oak套件的使用，並透過OSGi匯入。它們通常匯出時不含任何特定版本，僅供其他Oak組合或低階服務使AEM用。

其中一些由`com.adobe.granite.repository`使用，後者在啟動過程中設定AEM儲存庫。 另一個範例是`com.adobe.granite.maintenance.oak`Adobe套件，它包住並提供Oak維護工作。

## 可能的影響和風險{#implications-and-risks}

* 在未來版本中AEM，可能會移除內部匯出，造成依賴項中斷和非作用中的搭售，視Oak而定。
* 內部匯出中的API可能會變更。

## 可能的解決方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_guidance"
>title="實施指南"
>abstract="客戶應檢閱其自訂程式碼，以識別此類API的使用情形，並重新調整其與之相容AEM為Cloud Service。 聯絡Adobe支援以取得說明"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 使用Sling Resource API（或JCR API），而非低階存取。
* 請避免依任何公用API或SPI中不包含的內部封裝而定。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
