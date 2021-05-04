---
title: 工作
description: 模式偵測器程式碼說明頁面
exl-id: 1be1db54-fc91-45d0-80b5-b2978eee1da8
translation-type: tm+mt
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 1%

---

# 工作{#wrk}

工作流程

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_overview"
>title="工作流程"
>abstract="WORK代碼標識與工作流模型或啟動程式相關的查找結果。 會報告這些值，因為自訂資產工作流程模型在升級為Cloud Service時AEM必須移轉。 作為AEMCloud Service，資產處理現在由資產微服務執行。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html" text="Asset Microservices"

`WRK` 標識與工作流模型或啟動程式相關的查找結果。會報告這些值，因為自訂資產工作流程模型在升級為Cloud Service時AEM必須移轉。

子類型用於標識當前檢測到的工作流問題類型。

* `custom.asset.workflow`:偵測自訂資產工作流程模型或啟動程式。

## 可能的影響和風險{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_guidance"
>title="實施指南"
>abstract="由於標準資產工作流程會自動支援我的資產Microservices，因此最佳實務是檢閱所有自訂資產工作流程模型或啟動程式，以在我們轉換為Cloud Service後，查看是否需要AEM這些工作流程。 資產工作流程的自訂作業需要移轉，AEM才能在資產工作流程移轉工具的協助下，以Cloud Service方式使用"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/asset-microservices-configure-and-use.html" text="快速入門- Asset Microservices"

* 傳統上，資產處理是使用在AEM Author例項上執行的資產工作流程來執行。 作為AEMCloud Service，資產處理現在由資產微服務執行。 (如需詳細資訊，請參閱[asset microservices overview](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html)。
* 標準資產工作流程會自動支援我的資產Microservices。
* 資產工作流程的自訂作業需要移轉，才AEM能當成Cloud Service。

## 可能的解決方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_tools"
>title="工具與資源"
>abstract="檢閱並計畫在自訂資產工作流程模型或啟動程式被識別後，執行資產工作流程移轉工具。 聯絡Adobe支援以取得說明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/asset-workflow-migration-tool.html" text="資產工作流程移轉工具"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 如果已識別自訂資產工作流程模型或啟動程式，計畫執行[資產工作流程移轉工具](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/asset-workflow-migration-tool.html)。
* 請參閱[開始使用資產微服務](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/asset-microservices-configure-and-use.html)以取得詳細資訊。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
