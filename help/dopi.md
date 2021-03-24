---
title: 多皮
description: 模式偵測器程式碼說明頁面
translation-type: tm+mt
source-git-commit: ae3e162da40441fba39e6e9d283c495d15f40ba1
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---


# DOPI {#dopi}

已過時的有序屬性索引

## 背景 {#background}

`DOPI` 識別自6.1以來已過時且在6.2中已移除的有序屬性索引定義(`primaryType=oak:QueryIndexDefinition` AND `type="ordered"`)的使用。

## 可能的影響和風險{#implications-and-risks}

* 某些查詢可能無法響應。
* 客戶功能可能運作不正確。
* 遍歷警告或甚至錯誤，以及由於淘汰索引而造成的嚴重效能損失都沒有作用。

## 可能的解決方案{#solutions}

* 將索引定義修改為支援的索引定義，或將索引替換為支援的索引定義。 （請參閱[Oak Queries and Indexing](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/queries-and-indexing.html)）。
* 檢閱[wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi)專案，並瞭解如何校正[DOPI違規](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi)並將其與作為AEMCloud Service相容。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
