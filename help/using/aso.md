---
title: ASO
description: 模式偵測器程式碼說明頁面。
exl-id: 2ba416b7-80c1-4ec5-a6bf-d80f6d625b07
source-git-commit: 0d693e3ccadc81b59852914f115bb2fa2ea166b0
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 100%

---

# ASO {#aso}

AEM 系統總覽

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_overview"
>title="AEM 系統總覽"
>abstract="ASO 程式碼會識別 AEM 執行個體的一般資訊。每個發現都會提供某特定系統資訊類型的一個值，以協助您進行移轉規劃和重構。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="AEM as a Cloud Service - 發行說明"

`ASO` 會識別 AEM 執行個體的一般資訊。每個發現都會提供某特定系統資訊類型的一個值。

子類型用於識別不同類型的資訊：

* `aem.version`：AEM 版本。
* `aem.product`：偵測到使用了 AEM 產品 (Commerce、Forms 等等)。
* `node.count`：某種類型 (頁面、資產等等) 的大約節點數和節點總計。
* `node.store`：節點存放區實施類型 (SegmentNodeStore、DocumentNodeStore) 及其大小。
* `data.store`：資料存放區實施類型 (FileDataStore、S3DataStore、AzureDataStore)。
* `maintenance.task`：維護任務。
* `slow.query`：緩慢查詢。
* `group.membership`：群組中的使用者和子群組數目 (僅限直接/已宣告的成員)。
* `cqtag.count`：CQ 標記資產數目。
* `smarttag.count`：智慧標記資產數目。
* `ccom.version`：核心元件套件的版本。
* `instance.type`：AEM 執行個體類型 (編寫|發佈)。
* `unprocessed.asset.count`：未處理的資產數目。
* `vanity.url.count`：虛名 URL 的數量。
* `index.size`：總計可移轉 Lucene 指數大小。
* `workflow.count`：處於執行和過時狀態的編寫工作流程數量。
* `jvm.arguments`：啟動 AEM 時新增到命令列的 JVM 引數。

## 可能的影響和風險 {#implications-and-risks}

* AEM 版本、節點數、群組成員資格、節點存放區、資料存放區實施類型、CQ 標記數、智慧標記數、核心元件版本和 AEM 執行個體類型和未處理資產計數僅供參考。
* 更多的虛名 URL (>1000) 可能會給 Dispatcher 和查詢成本昂貴的 Publish 伺服器帶來負擔。
* 自訂應用程式可能依賴 AEM as a Cloud Service 中未提供的產品或功能。
* 升級若包含不支援的功能，可能會導致升級失敗和應用程式無作用。
* 處於執行或過時狀態的編寫工作流程數量過大可能會降低性能。
* 查詢緩慢可能會降低系統效能。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_guidance"
>title="實施指導"
>abstract="透過 ASO 程式碼公開的資訊會提供 AEM 環境的一般訊資訊，包括版本、產品附加元件和系統層級資訊。檢閱 AEM as a Cloud Service 中是否有任何不受支援的產品或功能。請聯絡 Adobe 支援人員，取得協助或說明。"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 不建議對不支援的產品或功能進行 AEM 升級，這可能不受支援。
* 未處理的資產必須加以處理，並且必須將資產 `jcr:content` 節點上的 `dam:assetState` 屬性設定為「已處理」。或者，您應該在移轉到 AEMaaCS 之前，從移轉集中刪除這些資產。
* 虛名 URL 可以替換為 Apache Rewrites。
* 如需解決查詢緩慢的問題，請參閱[文件](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-65/content/implementing/developing/bestpractices/troubleshooting-slow-queries)。
* 請參閱[發行說明](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current)以了解 AEM as a Cloud Service 的最新變更。
* 請聯絡 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以釐清或解決問題。
