---
title: WRK
description: 模式偵測器程式碼說明頁面
exl-id: 1be1db54-fc91-45d0-80b5-b2978eee1da8
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: ht
source-wordcount: '372'
ht-degree: 100%

---

# WRK {#wrk}

工作流程

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_overview"
>title="工作流程"
>abstract="WRK 程式碼會識別與工作流程模型或啟動器相關的發現。因為在升級為 AEM as a Cloud Service 時必須移轉自訂資產工作流程模型，所以報告了這些發現。在 AEM as a Cloud Service，資產處理現在是由資產微服務所執行。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html" text="資產微服務"

`WRK` 會識別與工作流程模型或啟動器相關的發現。因為在升級為 AEM as a Cloud Service 時必須移轉自訂資產工作流程模型，所以報告了這些發現。

子類型用於識別目前偵測到的工作流程類型。

* `custom.asset.workflow`：偵測到自訂資產工作流程模型或啟動器。

## 可能影響和風險 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_guidance"
>title="實施指導"
>abstract="由於資產微服務會自動支援標準資產工作流程，因此最佳實務是檢閱所有自訂資產工作流程模型或啟動器，以了解在轉變為 AEM as a Cloud Service 後是否需要它們。資產工作流程的自訂須透過資產工作流程移轉工具進行移轉，才能用於 AEM as a Cloud Service。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/asset-microservices-configure-and-use.html" text="快速入門 - 資產微服務"

* 資產處理傳統上是在 AEM 作者例項上透過資產工作流程所執行。在 AEM as a Cloud Service，資產處理現在是由資產微服務所執行。如需詳細資訊，請參閱[資產微服務總覽](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html)。
* 資產微服務會自動支援標準資產工作流程。
* 資產工作流程的自訂需要移轉，才能用於 AEM as a Cloud Service。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_tools"
>title="工具和資源"
>abstract="在識別出自訂資產工作流程模型或啟動器後，檢閱並規劃使用資產工作流程移轉工具。請聯繫 Adobe 支援以尋求協助與澄清。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/asset-workflow-migration-tool.html" text="資產工作流程移轉工具"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 在識別出自訂資產工作流程模型或啟動器後，請規劃使用[資產工作流程移轉工具](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/asset-workflow-migration-tool.html)。
* 如需詳細資訊，請參閱[開始使用資產微服務](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/asset-microservices-configure-and-use.html)。
* 請聯繫我們的 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以澄清或解決問題。
