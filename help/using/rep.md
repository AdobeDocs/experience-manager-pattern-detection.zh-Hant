---
title: REP
description: 模式偵測器程式碼說明頁面
exl-id: e788deba-a301-404f-8e90-51f721409e69
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: ht
source-wordcount: '462'
ht-degree: 100%

---

# [!DNL REP] {#rep}

複寫代理

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_rep_overview"
>title="複寫代理"
>abstract="REP 會識別已啟用的複寫代理。由於在升級為 AEM as a Cloud Service 時可能存在應解決的問題，因此報告了這些複寫代理。AEM as a Cloud Service 使用 Sling 內容發佈，將內容從作者環境散發到發佈環境。這是在 AEM 執行階段之外使用 Adobe I/O 管線服務完成的，並在已佈建的 AEM as a Cloud Service 環境中自動設定的。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#replication-agents" text="重大變更 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#no-reverse-replication-agents" text="開發指導方針"

`REP` 會識別已啟用的複寫代理。由於在升級為 AEM as a Cloud Service 時可能存在應解決的問題，因此報告了這些複寫代理。

子類型用於識別不同類型的資訊：

* `forward.replication`：識別已啟用的正向複寫代理。
* `reverse.replication`：識別已啟用的反向複寫代理。
* `standard.replication.agent.modification`：識別已啟用的修改後標準複寫代理。
* `custom.replication.agent.detection`：識別已啟用的自訂複寫代理。

AEM as a Cloud Service 使用 [Sling 內容發佈](https://sling.apache.org/documentation/bundles/content-distribution.html)，將內容從作者環境散發到發佈環境。這是在 AEM 執行階段之外使用 Adobe I/O 管線服務完成的，並在已佈建的 AEM as a Cloud Service 環境中自動設定的。

## 可能影響和風險 {#implications-and-risks}

* 複寫設定已隨著 AEM as a Cloud Service 有所改變。應檢閱所有目前的複寫代理，以了解哪些取代為標準功能、哪些設定必須移至程式碼，以及哪些不受支援。
* 在升級到 AEM as a Cloud Service 時，應檢閱自訂程式碼或工作流程中的任何複寫代理使用。
* AEM as a Cloud Service 最初不支援反向複寫。
* 無需設定單獨的發送器排清代理。這是在 AEM as a Cloud Service 環境中自動設定的。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_rep_guidance"
>title="實施指導"
>abstract="最佳實務是檢閱、重構和最佳化直接相依於複寫代理的自訂功能，使其與 AEM as a Cloud Service 相容。請聯繫 Adobe 支援以尋求協助與澄清。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#replication" text="複寫 - AEM as a Cloud Service"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 請參閱 AEM as a Cloud Service [開發指導方針](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#no-reverse-replication-agents)和[複寫代理](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#replication-agents)的發行說明。
* 檢閱、重構和最佳化直接相依於複寫代理的功能以執行商業任務。
* 了解[複寫](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#replication)如何受到 AEM as a Cloud Service 部署影響。
* 請聯繫我們的 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以澄清或解決問題。
