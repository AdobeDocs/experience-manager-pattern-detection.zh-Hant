---
title: NBCC
description: 模式偵測器程式碼說明頁面
translation-type: tm+mt
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 0%

---


# NBCC {#nbcc}

不向後相容的變更

## 背景 {#background}

`NBCC` 標識某些JCR節點或捆綁包以不相容的方式更改的情況。在升級前，客戶可能不知道此項變更。

## 可能的影響和風險{#implications-and-risks}

* 依賴任何使用非向後相容變更的元件的功能可能會中斷，且可能無法正確解析。
* 升級後，客戶應用程式的某些功能AEM或某些功能可能無法正常運作。

## 可能的解決方案{#solutions}

* 覆蓋或僅參考向後相容的Sling元件。
* 請考慮調整升級後`/libs`或搭售的資AEM源。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
