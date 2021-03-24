---
title: IOI
description: 模式偵測器程式碼說明頁面
translation-type: tm+mt
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 0%

---


# IOI {#ioi}

內部Oak匯入

## 背景 {#background}

`IOI` 識別客戶對內部Oak套件的使用，並透過OSGi匯入。它們通常匯出時不含任何特定版本，僅供其他Oak組合或低階服務使AEM用。

其中一些由`com.adobe.granite.repository`使用，後者在啟動過程中設定AEM儲存庫。 另一個範例是`com.adobe.granite.maintenance.oak`Adobe套件，它包住並提供Oak維護工作。

## 可能的影響和風險{#implications-and-risks}

* 在未來版本中AEM，可能會移除內部匯出，造成依賴項中斷和非作用中的搭售，視Oak而定。
* 內部匯出中的API可能會變更。

## 可能的解決方案{#solutions}

* 使用Sling Resource API（或JCR API），而非低階存取。
* 請避免依任何公用API或SPI中不包含的內部封裝而定。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。