---
title: OID
description: 模式偵測器程式碼說明頁面。
exl-id: 500e0d32-e75e-4abe-a96b-0692ce40c086
source-git-commit: 58fdb55e1f0c067dacf6825c4076465bc8c5d821
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 99%

---

# OID {#oid}

Oak 索引定義

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_overview"
>title="Oak 索引定義"
>abstract="OID 會識別與 Oak 索引定義相關的問題。它會識別對標準 Oak 索引定義所做的修改。它也會識別不相容於 AEM as a Cloud Service 的自訂 Oak 索引定義。每個 OID 發現的訊息都會識別該索引並提供額外資訊。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/operations/indexing#how-to-use" text="內容編製索引指導方針"

`OID` 會識別與 Oak 索引定義相關的問題。它會識別對標準 Oak 索引定義所做的修改。它也會識別不相容於 AEM as a Cloud Service 的自訂 Oak 索引定義。每個 `OID` 發現的訊息都會識別該索引並提供額外資訊。

子類型用於識別不同類型的資訊：

* `index.rule.violation`：不相容於 AEM as a Cloud Service 的自訂 Oak 索引
* `standard.index.modification`：對標準 Oak 索引的修改。

## 可能的影響和風險 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_guidance"
>title="實施指導"
>abstract="最佳實務是檢閱所有自訂索引，並依照內容編製索引準則進行重組。使用索引轉換器，將現有的自訂 Oak 索引定義移轉為 AEM as a Cloud Service 相容的自訂 Oak 索引定義。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure#oak-indexes" text="封裝指導方針"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/index-converter#refactoring-tools" text="索引轉換器"

* 在 AEM 升級期間，標準 Oak 索引定義的修改可能會遺失。
* Oak 定義是不可變、應使用客戶專案程式碼進行封裝，而且只能使用 Cloud Manager 進行部署。
* 所有 Oak 索引定義都應遵循 AEM as Cloud Service Oak 索引的命名慣例和其他規則。否則，可能會導致不良行為。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_tools"
>title="工具和資源"
>abstract="請檢閱 WKND 舊版專案以了解如何在專案中解決 OID 違規。也請檢閱 GitHub 上的 OID 違規範例，以了解如何使用索引轉換器工具轉換舊版索引，使其與 AEM as a Cloud Service 相容。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid" text="WKND-舊版專案"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid" text="OID 違規範例 - GitHub"

* 解決訊息中指出的索引規則違規。
* 若要部署新的或自訂的 Oak 索引定義，請遵循 AEM as a Cloud Service [封裝指導方針](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure)操作。
* 自訂 AEM 標準索引和新的自訂 Oak 索引定義都應遵循 AEM as a Cloud Service [內容編製索引指導方針](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/operations/indexing#preparing-the-new-index-definition)。
* 請檢閱 [WKND 舊版](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid)專案，了解如何更正 [OID 違規](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid)，使其與 AEM as a Cloud Service 相容。
* 請聯絡 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以釐清或解決問題。
* 使用[索引轉換器](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/index-converter#refactoring-tools)，將現有的自訂 Oak 索引定義移轉為 AEM as a Cloud Service 相容的自訂 Oak 索引定義。
