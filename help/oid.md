---
title: OID
description: 模式偵測器程式碼說明頁面
exl-id: 500e0d32-e75e-4abe-a96b-0692ce40c086
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 0%

---

# OID {#oid}

Oak索引定義

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_overview"
>title="Oak索引定義"
>abstract="OID可識別與Oak索引定義相關的問題。 其可識別對標準Oak索引定義所進行的修改。 它也會識別與AEM不相容的自訂Oak索引定義，作為Cloud Service。 每個OID查找結果的消息將標識索引並提供附加資訊。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html#how-to-use" text="內容索引指南"

`OID` 識別與Oak索引定義相關的問題。其可識別對標準Oak索引定義所進行的修改。 它也會識別與AEM不相容的自訂Oak索引定義，作為Cloud Service。 每個`OID`結果的訊息將識別索引並提供其他資訊。

子類型用於識別不同類型的資訊：

* `custom.index.violation`:自訂Oak索引與AEM as aCloud Service不相容。
* `standard.index.modification`:標準Oak索引的修改。

## 可能的影響和風險{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_guidance"
>title="實施指南"
>abstract="最佳實務是檢閱所有自訂索引，並依照內容索引准則加以重新建構。 運用Index Converter將現有的自訂Oak索引定義移轉至AEM作為與Cloud Service相容的自訂Oak索引定義"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#oak-indexes" text="包裝指南"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/index-converter.html#refactoring-tools" text="索引轉換器"

* 在AEM升級期間，對標準Oak索引定義的修改可能會遺失。
* Oak定義不可修改，應與客戶專案代碼一併封裝，且僅應使用Cloud Manager部署。
* 所有Oak索引定義都應遵循命名慣例和AEM中Oak索引的其他規則，做為Cloud Service。 那些不會造成不良行為的人。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_tools"
>title="工具和資源"
>abstract="查看WKND-legacy項目，了解如何在您的項目中解決OID違規。 另外，在Github上檢閱OID違規範例，了解如何使用「索引轉換工具」來轉換舊版索引，並使其與AEM作為Cloud Service相容。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid" text="WKND-Legacy專案"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid" text="OID違規示例 — Github"

* 解決消息中標識的索引規則違規。
* 遵循AEM作為Cloud Service[封裝准則](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html)以部署新的或自訂的Oak索引定義。
* 自訂的AEM標準索引和新的自訂Oak索引定義應遵循AEM作為Cloud Service的[內容索引准則](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html#preparing-the-new-index-definition)。
* 檢閱[wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid)專案，並了解如何更正[OID違規](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid)並使其與AEM as aCloud Service相容。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決問題。
* 運用[Index Converter](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/index-converter.html#refactoring-tools)將現有的自訂Oak索引定義移轉至AEM，作為與Cloud Service相容的自訂Oak索引定義。
