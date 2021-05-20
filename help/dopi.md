---
title: 多皮
description: 模式偵測器程式碼說明頁面
exl-id: ae4df44d-43ca-438c-8373-11381b916af3
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 0%

---

# 多皮 {#dopi}

已廢止的已排序屬性索引

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_overview"
>title="已廢止的已排序屬性索引"
>abstract="DOPI程式碼可識別有序屬性索引定義(primaryType=oak:QueryIndexDefinition AND type=&quot;ordered&quot;)的使用，自6.1起即已棄用，並於6.2中移除。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/queries-and-indexing.html?lang=en#the-ordered-index" text="有序索引 — 已廢止"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html" text="索引 — AEM作為Cloud Service"

`DOPI` 識別有序屬性索引定義(`primaryType=oak:QueryIndexDefinition` AND `type="ordered"`)的使用，自6.1起即已棄用，並於6.2中移除。

## 可能的影響和風險{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_guidance"
>title="實施指南"
>abstract="最佳做法是檢查所有已棄用的已排序索引，並將其移至支援的lucene索引形式，以避免出現重大效能問題或客戶需求不正常。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/practices/best-practices-for-queries-and-indexing.html" text="最佳實務 — 查詢和建立索引"

* 某些查詢可能沒有響應。
* 客戶功能可能運作不正確。
* 遍歷警告或甚至錯誤，以及嚴重的效能懲罰，因為已廢止的索引沒有作用。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_tools"
>title="工具和資源"
>abstract="查看WKND-legacy專案，了解如何讓DOPI違規與AEMCloud Service相容。 另外，在Github上檢閱DOPI違規範例，了解如何將舊版有序索引轉換為AEM as aCloud Service中支援的Lucene型索引。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi" text="WKND-Legacy專案"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi" text="DOPI違規示例 — Github"

* 修改索引定義，使其成為支援的索引定義，或用替換索引。 （請參閱[Oak查詢和索引](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/queries-and-indexing.html)）。
* 檢閱[wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi)專案，並了解如何更正[DOPI違規](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi)並使其與AEM as aCloud Service相容。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決問題。
