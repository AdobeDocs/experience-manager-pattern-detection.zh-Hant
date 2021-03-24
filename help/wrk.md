---
title: 工作
description: 模式偵測器程式碼說明頁面
translation-type: tm+mt
source-git-commit: 2391ad7851d4e6634a7bacd684b08db44a9c78e8
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 1%

---


# 工作{#wrk}

工作流程

## 背景 {#background}

`WRK` 標識與工作流模型或啟動程式相關的查找結果。會報告這些值，因為自訂資產工作流程模型在升級為Cloud Service時AEM必須移轉。

子類型用於標識當前檢測到的工作流問題類型。

* `custom.asset.workflow`:偵測自訂資產工作流程模型或啟動程式。

## 可能的影響和風險{#implications-and-risks}

* 傳統上，資產處理是使用在AEM Author例項上執行的資產工作流程來執行。 作為AEMCloud Service，資產處理現在由資產微服務執行。 (如需詳細資訊，請參閱[asset microservices overview](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html)。
* 標準資產工作流程會自動支援我的資產Microservices。
* 資產工作流程的自訂作業需要移轉，才AEM能當成Cloud Service。

## 可能的解決方案{#solutions}

* 如果已識別自訂資產工作流程模型或啟動程式，計畫執行[資產工作流程移轉工具](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/asset-workflow-migration-tool.html)。
* 請參閱[開始使用資產微服務](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/asset-microservices-configure-and-use.html)以取得詳細資訊。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
