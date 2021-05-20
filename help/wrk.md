---
title: 工作
description: 模式偵測器程式碼說明頁面
exl-id: 1be1db54-fc91-45d0-80b5-b2978eee1da8
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 1%

---

# 工作 {#wrk}

工作流程

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_overview"
>title="工作流程"
>abstract="WRK代碼標識與工作流模型或啟動器相關的結果。 這些會回報，因為升級至AEM as aCloud Service時，必須移轉自訂資產工作流程模型。 以AEM作為Cloud Service，資產處理現在由資產微服務執行。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html" text="資產微服務"

`WRK` 標識與工作流模型或啟動器相關的結果。這些會回報，因為升級至AEM as aCloud Service時，必須移轉自訂資產工作流程模型。

子類型用於標識當前檢測到的工作流問題的類型。

* `custom.asset.workflow`:偵測自訂資產工作流程模型或啟動器。

## 可能的影響和風險{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_guidance"
>title="實施指南"
>abstract="由於標準資產工作流程可自動支援我的資產微服務，因此最佳實務是檢閱所有自訂資產工作流程模型或啟動器，查看我們轉換至AEM as aCloud Service後是否需要這些工作流程。 自訂資產工作流程需要移轉，才能在資產工作流程移轉工具的協助下，以AEM作為Cloud Service使用"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/asset-microservices-configure-and-use.html" text="快速入門 — 資產微服務"

* 傳統上，資產處理是透過在AEM Author例項上執行的資產工作流程來執行。 以AEM作為Cloud Service，資產處理現在由資產微服務執行。 (如需詳細資訊，請參閱[資產微服務概述](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html) 。
* 標準資產工作流程會自動支援我的資產微服務。
* 自訂資產工作流程需要移轉，才能以AEM作為Cloud Service。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_tools"
>title="工具和資源"
>abstract="在識別自訂資產工作流程模型或啟動器後，檢閱並計畫執行資產工作流程移轉工具。 請洽詢Adobe支援以取得說明和說明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/asset-workflow-migration-tool.html" text="資產工作流程移轉工具"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 如果已識別自訂資產工作流程模型或啟動器，計畫執行[資產工作流程移轉工具](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/asset-workflow-migration-tool.html)。
* 如需詳細資訊，請參閱[開始使用資產微服務](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/asset-microservices-configure-and-use.html) 。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決問題。
