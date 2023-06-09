---
title: DOPI
description: 模式偵測器程式碼說明頁面
exl-id: ae4df44d-43ca-438c-8373-11381b916af3
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 100%

---

# DOPI {#dopi}

已棄用的有序屬性索引

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_overview"
>title="已棄用的有序屬性索引"
>abstract="DOPI 程式碼會識別有序屬性索引定義 (primaryType=oak:QueryIndexDefinition 及 type=&quot;ordered&quot;) 的使用，有序屬性索引自 6.1 之後已棄用，在 6.2 中已移除。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/queries-and-indexing.html?lang=zh-Hant#the-ordered-index" text="有序索引 - 已棄用"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html" text="編製索引 - AEM as a Cloud Service"

`DOPI` 會識別有序屬性索引定義 (`primaryType=oak:QueryIndexDefinition` 及 `type="ordered"`) 的使用，有序屬性索引自 6.1 之後已棄用，在 6.2 中已移除。

## 可能影響和風險 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_guidance"
>title="實施指導"
>abstract="最佳實務是檢閱所有已棄用的有序索引，並將其移至支援的 Lucene 索引形式，以避免重大的效能問題或無作用的客戶要求。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/practices/best-practices-for-queries-and-indexing.html" text="最佳實務 - 查詢和編製索引"

* 部分查詢可能不會回應。
* 客戶功能可能不正確地運作。
* 由於已棄用的索引無效，所有會出現周遊警告或甚至錯誤以及重大效能損失。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_tools"
>title="工具和資源"
>abstract="請檢閱 WKND 舊版專案以了解如何將 DOPI 違規設為相容於 AEM Cloud Service。也請檢閱 Github 上的 DOPI 違規範例，以了解如何將舊版有序索引轉換為 AEM as a Cloud Service 支援的 Lucene 型索引。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi" text="WKND-舊版專案"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi" text="DOPI 違規範例 - Github"

* 修改索引定義以成為 (或將索引取代為) 支援的索引定義。(請參閱 [Oak 查詢和編製索引](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/queries-and-indexing.html))。
* 請檢閱 [WKND 舊版](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi)專案，了解如何更正 [DOPI 違規](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi)，使其與 AEM as a Cloud Service 相容。
* 請聯繫我們的 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以澄清或解決問題。
