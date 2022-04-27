---
title: ASO
description: 模式偵測器程式碼說明頁面
exl-id: 2ba416b7-80c1-4ec5-a6bf-d80f6d625b07
source-git-commit: a3b610f2028c4923344672dd71c2bd5d252a35c4
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 77%

---

# 麻生 {#aso}

AEM 系統總覽

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_overview"
>title="AEM 系統總覽"
>abstract="ASO 程式碼會識別 AEM 例項的一般資訊。每個發現都會提供某特定系統資訊類型的一個值，以協助您進行移轉規劃和重構。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="AEM as a Cloud Service - 發行說明"

`ASO` 會識別 AEM 例項的一般資訊。每個發現都會提供某特定系統資訊類型的一個值。

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
* `instance.type`：AEM 例項類型 (作者|發佈)。
* `unprocessed.asset.count`：未處理的資產數目。
* `vanity.url.count`：虛名 URL 的數量。

## 可能影響和風險 {#implications-and-risks}

* 提AEM供了版本、節點計數、組成員身份、節點儲存、資料儲存實現類型、CQ標籤計數、智慧標籤計數、核心元件版本、實例類型AEM和未處理資產計數，以供參考。
* 虛擬URL(>1000)的數量越多，就會給Dispatcher和Publish伺服器載入昂貴的查詢。
* 自訂應用程式可能依賴 AEM as a Cloud Service 中未提供的產品或功能。
* 升級若包含不支援的功能，可能會導致升級失敗和應用程式無作用。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_guidance"
>title="實施指導"
>abstract="透過 ASO 程式碼公開的資訊會提供 AEM 環境的一般資訊，包括版本、產品附加元件、系統等級資訊，應檢閱這些資訊以了解 AEM as a Cloud Service 不支援的任何產品或功能。請聯繫 Adobe 支援以尋求協助與澄清。"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 不建議對不支援的產品或功能進行 AEM 升級，這可能不受支援。
* 必須處理未處理的資產，並且必須將資產的jcr:content節點上的dam:assetState屬性設定為「已處理」，或在遷移到AEMaaCS之前從遷移集中刪除這些資產。
* 虛擬URL可以替換為Apache重寫。
* 請檢閱[發行說明](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hant)以了解 AEM as a Cloud Service 最新變更。
* 請聯繫我們的 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以澄清或解決問題。
