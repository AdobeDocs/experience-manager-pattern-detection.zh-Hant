---
title: OID
description: 模式偵測器程式碼說明頁面
exl-id: 500e0d32-e75e-4abe-a96b-0692ce40c086
translation-type: tm+mt
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 0%

---

# OID {#oid}

Oak Index Definition

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_overview"
>title="Oak Index Definition"
>abstract="OID可識別與Oak索引定義相關的問題。 它可識別對標準Oak索引定義所做的修改。 它也會將與不相容的自訂Oak索引定義識AEM別為Cloud Service。 每個OID查找結果的消息將標識索引並提供其他資訊。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html#how-to-use" text="內容索引指南"

`OID` 識別與Oak索引定義相關的問題。它可識別對標準Oak索引定義所做的修改。 它也會將與不相容的自訂Oak索引定義識AEM別為Cloud Service。 每個`OID`查找結果的消息將標識索引並提供其他資訊。

子類型用於標識不同類型的資訊：

* `custom.index.violation`:自訂Oak索引與AEMCloud Service不相容。
* `standard.index.modification`:標準Oak索引的修改。

## 可能的影響和風險{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_guidance"
>title="實施指南"
>abstract="最佳做法是審查所有自訂索引，並依據內容索引准則進行重新架構。 利用Index Converter將現有的自訂Oak索引定義移轉AEM為Cloud Service相容的自訂Oak索引定義"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#oak-indexes" text="封裝准則"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/index-converter.html#refactoring-tools" text="索引轉換器"

* 在升級期間，對標準Oak索引定義的修改可能會AEM遺失。
* Oak定義是不可變的，應與客戶專案代碼一起封裝，且僅應使用Cloud Manager部署。
* 所有Oak索引定義都應遵循Oak索引的命名慣例和其他規則，作為AEMCloud Service。 那些不會導致不想要的行為的行為。

## 可能的解決方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_tools"
>title="工具與資源"
>abstract="查看WKND-legacy項目，瞭解如何在您的項目中解決OID違規問題。 此外，在Github上查看OID違規示例，瞭解如何使用「索引轉換器」工具轉換舊索引，並將其與作AEM為Cloud Service相容。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid" text="WKND-Legacy Project"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid" text="OID違規示例- Github"

* 解決消息中標識的索引規則違規。
* 以&lt;AEMa0/>封裝准則](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html)的Cloud Service方式部署新的或自訂的Oak索引定義。[
* 自訂AEM的標準索引和新的自訂Oak索引定義應遵循[內容索引方針](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html#preparing-the-new-index-definition)，做為AEMCloud Service。
* 檢閱[wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid)專案，並瞭解如何更正[OID違規](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid)並將其與作為AEMCloud Service相容。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
* 運用[Index Converter](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/index-converter.html#refactoring-tools)將現有的自訂Oak索引定義移轉AEM為Cloud Service相容的自訂Oak索引定義。
