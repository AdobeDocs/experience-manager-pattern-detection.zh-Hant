---
title: ASO
description: 模式偵測器程式碼說明頁面
translation-type: tm+mt
source-git-commit: a2c7137dd5cb2479bc0c6134d3afa58111049a68
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 4%

---


# ASO {#aso}

AEM系統概述

## 背景 {#background}

`ASO` 標識有關實例的一AEM般資訊。每個查找結果都提供特定類型系統資訊的一個值。

子類型用於標識不同類型的資訊：

* `aem.version`:版本AEM。
* `aem.product`:偵測產品AEM(商務、Forms等)的使用。
* `node.count`:特定類型（頁面、資產等）的近似節點計數。
* `node.store`:節點儲存實施類型(SegmentNodeStore、DocumentNodeStore)。
* `data.store`:資料存放區實作類型(FileDataStore、S3DataStore、AzureDataStore)。
* `maintenance.task`:維護任務。
* `slow.query`:慢速查詢。

## 可能的影響和風險{#implications-and-risks}

* 提供AEM了版本、節點計數、節點儲存和資料儲存實施類型，用於資訊用途。
* 自訂應用程式可能會依賴Cloud Service中不提供AEM的產品或功能。
* 使用不支援的功能進行升級可能會導致升級失敗和應用程式無法運作。

## 可能的解決方案{#solutions}

* 不建AEM議使用不支援的產品或功能進行升級，可能不支援。
* 請參閱[發行說明](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html)，以瞭解Cloud Service中的最AEM新變更。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
