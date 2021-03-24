---
title: OCU
description: 模式偵測器程式碼說明頁面
translation-type: tm+mt
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# OCU {#ocu}

過期的程式碼使用

## 背景 {#background}

`OCU` 識別某些JCR節點(例如Sling或AEM元件或API OSGi匯出)以不相容方式變更或移除的情形。在升級前，客戶可能不知道此項變更。 它們可能會升級為不相容的版本，或完全無法使用。

由於舊版本預設未安裝，因此客戶應用程式可能無法正常運作。

## 可能的影響和風險{#implications-and-risks}

* 依賴任何使用已過時元件或API的元件的功能可能會中斷，而且升級後可能無法正確解析。
* 客戶應用程式的某些功能或AEM某些功能可能無法正常運作，或在升級後可能無法作用。

## 可能的解決方案{#solutions}

* 短期：安裝相容性軟體包可能會有所幫助。
* 長期：調整客戶程式碼，以使用最新版AEM的元件或API。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
