---
title: ASO
description: 模式偵測器程式碼說明頁面
exl-id: 2ba416b7-80c1-4ec5-a6bf-d80f6d625b07
source-git-commit: 3e05ecb2c78b0ebf97d334cf592347b54255c75f
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 4%

---

# ASO {#aso}

AEM系統概述

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_overview"
>title="AEM系統概述"
>abstract="ASO程式碼可識別AEM例項的一般資訊。 每個結果都提供特定類型系統資訊的一個值，可協助您進行移轉規劃和重構工作。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="AEMas a Cloud Service — 發行說明"

`ASO` 識別AEM例項的一般資訊。 每個結果提供特定類型系統資訊的一個值。

子類型用於識別不同類型的資訊：

* `aem.version`:AEM版本。
* `aem.product`:偵測AEM產品(商務、Forms等)的使用。
* `node.count`:特定類型（頁面、資產等）的約略節點計數 和總節點數。
* `node.store`:節點儲存實施類型(SegmentNodeStore、DocumentNodeStore)及其大小。
* `data.store`:資料儲存實作類型(FileDataStore、S3DataStore、AzureDataStore)。
* `maintenance.task`:維護任務。
* `slow.query`:查詢速度慢。
* `group.membership`:組中的用戶和子組（僅直接/聲明成員）數。

## 可能的影響和風險 {#implications-and-risks}

* AEM版本、節點計數、群組成員資格以及節點存放區和資料存放區實作類型僅供參考。
* 自訂應用程式可能需仰賴AEM as a Cloud Service中未提供的產品或功能。
* 使用不支援的功能進行升級可能會導致升級失敗和應用程式無法正常運作。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_guidance"
>title="實施指南"
>abstract="透過ASO程式碼公開的資訊提供AEM環境的一般資訊，包括版本、產品附加元件、系統層級資訊，且應針對AEMas a Cloud Service中任何不支援的產品或功能進行審閱。 請聯絡Adobe支援以取得說明和說明。"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 不建議使用不支援的產品或功能進行AEM升級，也可能不支援。
* 檢閱 [發行說明](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hant) 了解AEM as a Cloud Service的最新變更。
* 請聯繫我們的 [AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) 以取得澄清或處理關注。
