---
title: 多皮
description: 模式偵測器程式碼說明頁面
exl-id: ae4df44d-43ca-438c-8373-11381b916af3
translation-type: tm+mt
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 0%

---

# DOPI {#dopi}

已過時的有序屬性索引

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_overview"
>title="已過時的有序屬性索引"
>abstract="DOPI程式碼可識別有序屬性索引定義(primaryType=oak:QueryIndexDefinition AND type=&quot;ordered&quot;)的使用，這些定義自6.1起已過時，在6.2中已移除。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/queries-and-indexing.html?lang=en#the-ordered-index" text="有序索引——已過時"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html" text="索引-AEM作為Cloud Service"

`DOPI` 識別自6.1以來已過時且在6.2中已移除的有序屬性索引定義(`primaryType=oak:QueryIndexDefinition` AND `type="ordered"`)的使用。

## 可能的影響和風險{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_guidance"
>title="實施指南"
>abstract="最佳做法是查看所有已過時的有序索引，並將其移動到支援形式的lucene索引，以避免出現嚴重的效能問題或客戶要求不起作用。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/practices/best-practices-for-queries-and-indexing.html" text="最佳做法——查詢和索引"

* 某些查詢可能無法響應。
* 客戶功能可能運作不正確。
* 遍歷警告或甚至錯誤，以及由於淘汰索引而造成的嚴重效能損失都沒有作用。

## 可能的解決方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_tools"
>title="工具與資源"
>abstract="檢閱WKND-legacy專案，瞭解如何讓DOPI違規與AEMCloud Service相容。 此外，在Github上查看DOPI違規示例，瞭解如何將舊有有序索引轉換為基於Lucene的索引，這些索引在中作為AEMCloud Service受支援。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi" text="WKND-Legacy Project"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi" text="DOPI違規示例- Github"

* 將索引定義修改為支援的索引定義，或將索引替換為支援的索引定義。 （請參閱[Oak Queries and Indexing](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/queries-and-indexing.html)）。
* 檢閱[wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi)專案，並瞭解如何校正[DOPI違規](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi)並將其與作為AEMCloud Service相容。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
