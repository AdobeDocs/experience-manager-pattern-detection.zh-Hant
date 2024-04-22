---
title: DOPI
description: 模式偵測器程式碼說明頁面。
exl-id: ae4df44d-43ca-438c-8373-11381b916af3
source-git-commit: 982ad1a6f43a29f2ee2284219757c8fc11b31ce0
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 43%

---

# DOPI {#dopi}

已棄用的有序屬性索引

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_overview"
>title="已棄用的有序屬性索引"
>abstract="DOPI程式碼會識別有序屬性索引定義的使用(`primaryType=oak:QueryIndexDefinition` AND type=&quot;ordered&quot;)，這已從6.1開始棄用，在6.2中已移除。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/deploying/queries-and-indexing#the-ordered-index" text="有序索引 - 已棄用"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/operations/indexing" text="編製索引 - AEM as a Cloud Service"

DOPI會識別有序屬性索引定義的使用(`primaryType=oak:QueryIndexDefinition` 和 `type="ordered"`)，這些元件自6.1之後已淘汰，並在6.2中移除。

## 可能影響和風險 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_guidance"
>title="實施指導"
>abstract="最佳實務是檢閱所有過時的有序索引，並將其移至支援的Lucene索引形式，以避免重大效能問題或無法運作的客戶需求。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/practices/best-practices-for-queries-and-indexing" text="最佳實務 - 查詢和編製索引"

* 部分查詢可能不會回應。
* 客戶功能可能不正確地運作。
* 由於已棄用的索引無效，所有會出現周遊警告或甚至錯誤以及重大效能損失。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_tools"
>title="工具和資源"
>abstract="請檢閱 WKND 舊版專案以了解如何將 DOPI 違規設為相容於 AEM Cloud Service。也請檢閱GitHub上的DOPI違規範例，以瞭解如何將舊版有序索引轉換為AEMas a Cloud Service支援的Lucene型索引。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi" text="WKND-舊版專案"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi" text="DOPI違規範例 — GitHub"

* 修改索引定義，使其成為（或取代為）支援的索引定義。 (請參閱 [Oak 查詢和編製索引](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/deploying/queries-and-indexing))。
* 請檢閱 [WKND 舊版](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi)專案，了解如何更正 [DOPI 違規](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi)，使其與 AEM as a Cloud Service 相容。
* 聯絡 [AEM支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html) 以澄清或解決問題。
