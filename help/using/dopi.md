---
title: DOPI
description: 模式偵測器程式碼說明頁面。
exl-id: ae4df44d-43ca-438c-8373-11381b916af3
source-git-commit: dd60fb9fb21d534e7b6f264826d3cc1477def421
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 91%

---

# DOPI {#dopi}

已棄用的有序屬性索引

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_overview"
>title="已棄用的有序屬性索引"
>abstract="DOPI 代碼會識別使用有序屬性索引定義 (`primaryType=oak:QueryIndexDefinition` AND `type="ordered"`) 的情況。在 AEM 6.1 已棄用該定義，並在 AEM 6.2 刪除。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-65/content/implementing/deploying/deploying/queries-and-indexing#the-ordered-index" text="有序索引 - 已棄用"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/operations/indexing" text="編製索引 - AEM as a Cloud Service"

`DOPI`  識別有序屬性索引定義的使用(`primaryType=oak:QueryIndexDefinition` 和 `type="ordered"`)。 這些定義在AEM 6.1中已過時，在AEM 6.2中已移除。

## 可能的影響和風險 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_guidance"
>title="實施指導"
>abstract="最佳實務是檢閱所有已棄用的有序索引，並將其移至支援的 Lucene 索引形式，以避免重大的效能問題或無作用的客戶要求。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-65/content/implementing/deploying/practices/best-practices-for-queries-and-indexing" text="最佳實務 - 查詢和編製索引"

* 部分查詢可能不會回應。
* 客戶功能可能不正確地運作。
* 由於已棄用的索引無效，所有會出現周遊警告或甚至錯誤以及重大效能損失。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_tools"
>title="工具和資源"
>abstract="請檢閱 WKND 舊版專案以了解如何將 DOPI 違規設為相容於 AEM Cloud Service。亦請檢閱 GitHub 上的 DOPI 違規範例。您可以藉此了解如何將舊的有序索引轉換為 AEM as a Cloud Service 所支援的 Lucene 型索引。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi" text="WKND-舊版專案"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi" text="DOPI 違規範例 - GitHub"

* 編輯索引定義以成為 (或將索引替換為) 支援的索引定義。(請參閱 [Oak 查詢和編製索引](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-65/content/implementing/deploying/deploying/queries-and-indexing))。
* 請檢閱 [WKND 舊版](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi)專案，了解如何更正 [DOPI 違規](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi)，使其與 AEM as a Cloud Service 相容。
* 請聯絡 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以釐清或解決問題。
