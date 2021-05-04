---
title: ASO
description: 模式偵測器程式碼說明頁面
exl-id: 2ba416b7-80c1-4ec5-a6bf-d80f6d625b07
translation-type: tm+mt
source-git-commit: 449288e567adda9998a89e0ad5198fd5a4e93f35
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 5%

---

# ASO {#aso}

AEM系統概述

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_overview"
>title="AEM系統概述"
>abstract="ASO代碼標識有關實例的一AEM般資訊。 每個尋找都提供特定類型系統資訊的一個值，可協助您進行移轉規劃和重構工作。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="作AEM為Cloud Service-發行說明"

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

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_guidance"
>title="實施指南"
>abstract="透過ASO程式碼公開的資訊提供您環境的一般資訊AEM，包括版本、產品附加元件、系統層級資訊，且應針對Cloud Service中任何不支援的產品或功能進行AEM檢閱。 聯絡Adobe支援以取得說明。"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 不建AEM議使用不支援的產品或功能進行升級，可能不支援。
* 請參閱[發行說明](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hant)，以瞭解Cloud Service中的最AEM新變更。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
