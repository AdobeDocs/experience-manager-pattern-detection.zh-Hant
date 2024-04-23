---
title: OID
description: 模式偵測器程式碼說明頁面。
exl-id: 500e0d32-e75e-4abe-a96b-0692ce40c086
source-git-commit: 616fa84f6237893243cffc8af28c7cbe76bf32d7
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 50%

---

# OID {#oid}

Oak 索引定義

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_overview"
>title="Oak 索引定義"
>abstract="OID 會識別與 Oak 索引定義相關的問題。它會識別對標準 Oak 索引定義所做的修改。它也會識別不相容於 AEM as a Cloud Service 的自訂 Oak 索引定義。每個OID發現的訊息都會識別該索引並提供額外資訊。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/operations/indexing#how-to-use" text="內容編製索引指導方針"

OID 會識別與 Oak 索引定義相關的問題。它會識別對標準 Oak 索引定義所做的修改。它也會識別不相容於 AEM as a Cloud Service 的自訂 Oak 索引定義。每個的訊息 `OID` 尋找會識別索引並提供其他資訊。

子類型用於識別不同類型的資訊：

* `index.rule.violation`：不相容於 AEM as a Cloud Service 的自訂 Oak 索引
* `standard.index.modification`：對標準 Oak 索引的修改。

## 可能影響和風險 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_guidance"
>title="實施指導"
>abstract="最佳實務是檢閱所有自訂索引，並根據內容編制索引指導方針進行重組。 使用索引轉換器，將現有的自訂Oak索引定義移轉為AEMas a Cloud Service相容的自訂Oak索引定義"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure#oak-indexes" text="封裝指導方針"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/index-converter#refactoring-tools" text="索引轉換器"

* 在 AEM 升級期間，標準 Oak 索引定義的修改可能會遺失。
* Oak 定義是不可變、應使用客戶專案程式碼進行封裝，而且只能使用 Cloud Manager 進行部署。
* 所有Oak索引定義都應遵循AEMas a Cloud Service中Oak索引的命名慣例和其他規則。 否則，可能會導致意外的行為。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_tools"
>title="工具和資源"
>abstract="請檢閱 WKND 舊版專案以了解如何在專案中解決 OID 違規。也請檢閱GitHub上的OID違規範例，以瞭解如何使用「索引轉換器」工具轉換舊版索引，使其與AEMas a Cloud Service相容。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid" text="WKND-舊版專案"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid" text="OID違規範例 — GitHub"

* 解決訊息中指出的索引規則違規。
* 若要部署新的或自訂的Oak索引定義，請依照AEMas a Cloud Service操作 [封裝指導方針](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure).
* 自訂AEM標準索引和新的自訂Oak索引定義應該遵循 [內容編制索引指導方針](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/operations/indexing#preparing-the-new-index-definition) 適用於AEMas a Cloud Service。
* 請檢閱 [WKND 舊版](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid)專案，了解如何更正 [OID 違規](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid)，使其與 AEM as a Cloud Service 相容。
* 聯絡 [AEM支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html) 以澄清或解決問題。
* 使用 [索引轉換器](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/index-converter#refactoring-tools) 將現有的自訂Oak索引定義移轉至AEMas a Cloud Service相容的自訂Oak索引定義。
