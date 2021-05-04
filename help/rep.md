---
title: REP
description: 模式偵測器程式碼說明頁面
exl-id: e788deba-a301-404f-8e90-51f721409e69
translation-type: tm+mt
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 2%

---

# [!DNL REP] {#rep}

複寫代理

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_rep_overview"
>title="複寫代理"
>abstract="REP標識已啟用的複製代理。 由於升級為Cloud Service時可能會出現問題，因此會報告AEM這些問題。 作AEM為Cloud Service使用Sling Content Distribution將內容從作者散發至發佈環境。 這是在執行階段外使AEM用Adobe I/O的管線服務進行。這會在布建的環境中自AEM動設定為Cloud Service環境。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#replication-agents" text="顯著變AEM更——作為Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#no-reverse-replication-agents" text="開發指南"

`REP` 標識已啟用的複製代理。由於升級為Cloud Service時可能會出現問題，因此會報告AEM這些問題。

作AEM為Cloud Service使用[Sling Content Distribution](https://sling.apache.org/documentation/bundles/content-distribution.html)將內容從作者散發至發佈環境。 這是在執行階段外使AEM用Adobe I/O的管線服務進行。這會在布建的環境中自AEM動設定為Cloud Service環境。

## 可能的影響和風險{#implications-and-risks}

* 複製的配置已更改，AEM作為Cloud Service。 應審查所有當前的複製代理，以查看哪些被標準功能取代、哪些配置必須移至代碼，哪些配置不受支援。
* 在升級到Cloud Service時，應審查在自定義代碼或工作流中對複製代理的AEM任何使用。
* 反向複製最初不支援AEM作為Cloud Service。
* 不需要配置單獨的調度器刷新代理。 這會自動在中設AEM定為Cloud Service環境。

## 可能的解決方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_rep_guidance"
>title="實施指南"
>abstract="最佳做法是直接依賴複製代理來審查、調整和優化自定義功能，並使其與作為的AEMCloud Service相容。 聯絡Adobe支援以取得說明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#replication" text="複製-AEM作為Cloud Service"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 請參見AEM[Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#no-reverse-replication-agents)《開發指南》，以及[複製代理](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#replication-agents)的發行說明。
* 直接依賴複製代理執行業務任務來審查、重構和優化功能。
* 瞭解[replication](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#replication)如何受部署作為Cloud Service的AEM影響。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
