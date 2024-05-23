---
title: WRK
description: 模式偵測器程式碼說明頁面。
exl-id: 1be1db54-fc91-45d0-80b5-b2978eee1da8
source-git-commit: dd60fb9fb21d534e7b6f264826d3cc1477def421
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 90%

---

# WRK {#wrk}

工作流程

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_overview"
>title="工作流程"
>abstract="WRK 程式碼會識別與工作流程模型或啟動器相關的發現。因為在升級為 AEM as a Cloud Service 時必須移轉自訂資產工作流程模型，所以會提供這些發現的報告。在 AEM as a Cloud Service，由資產微服務執行資產處理。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/assets/asset-microservices-overview" text="資產微服務"

`WRK` 會識別與工作流程模型或啟動器相關的發現。報告這些識別，因為當升級為AEMas a Cloud Service時，必須移轉自訂資產工作流程模型。

子類型用於識別目前偵測到的工作流程類型。

* `custom.asset.workflow`：偵測到自訂資產工作流程模型或啟動器。

## 可能的影響和風險 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_guidance"
>title="實施指導"
>abstract="資產微服務會自動支援標準資產工作流程。因此，最佳實務是檢查所有自訂資產工作流程模型或啟動器。在檢查時，您可以了解轉換到 AEM as a Cloud Service 之後是否需要它們。資產工作流程自訂化必須透過資產工作流程移轉工具進行移轉，才能用於 AEM as a Cloud Service。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/assets/manage/asset-microservices-configure-and-use" text="快速入門 - 資產微服務"

* 資產處理傳統上是在 AEM 製作執行個體上透過資產工作流程所執行。透過AEMas a Cloud Service，資產微服務會執行資產處理。 如需詳細資訊，請參閱[資產微服務概觀](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/assets/asset-microservices-overview)。
* 資產微服務會自動支援標準資產工作流程。
* 資產工作流程的自訂需要移轉，才能用於 AEM as a Cloud Service。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_tools"
>title="工具和資源"
>abstract="在識別出自訂資產工作流程模型或啟動器後，檢閱並規劃使用資產工作流程移轉工具。請聯絡 Adobe 支援人員，取得協助或說明。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/asset-workflow-migration-tool" text="資產工作流程移轉工具"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 在識別出自訂資產工作流程模型或啟動器後，請規劃使用[資產工作流程移轉工具](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/asset-workflow-migration-tool)。
* 如需詳細資訊，請參閱[開始使用資產微服務](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/assets/manage/asset-microservices-configure-and-use)。
* 請聯絡 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以釐清或解決問題。
