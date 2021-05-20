---
title: 代表
description: 模式偵測器程式碼說明頁面
exl-id: e788deba-a301-404f-8e90-51f721409e69
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
>abstract="REP標識已啟用的複製代理。 這些報告是因為升級至AEM as aCloud Service時可能會解決問題。 AEM as aCloud Service使用Sling Content Distribution，將內容從作者發佈至發佈環境。 這是在AEM執行階段外部使用Adobe I/O的管道服務完成。這會在布建的AEM中自動設定為Cloud Service環境。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#replication-agents" text="重大變更 — AEM as aCloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#no-reverse-replication-agents" text="開發准則"

`REP` 標識已啟用的複製代理。這些報告是因為升級至AEM as aCloud Service時可能會解決問題。

AEM as aCloud Service使用[Sling Content Distribution](https://sling.apache.org/documentation/bundles/content-distribution.html)將內容從作者發佈至發佈環境。 這是在AEM執行階段外部使用Adobe I/O的管道服務完成。這會在布建的AEM中自動設定為Cloud Service環境。

## 可能的影響和風險{#implications-and-risks}

* 以AEM為Cloud Service的復寫設定已變更。 應查看所有當前複製代理，以查看哪些被標準功能替換、哪些配置必須移至代碼，哪些配置不受支援。
* 升級至AEM as aCloud Service時，應審查自訂程式碼或工作流程中復寫代理的使用情況。
* AEM作為Cloud Service最初不支援反向復寫。
* 不需要設定個別的Dispatcher排清代理程式。 這會在AEM中自動設定為Cloud Service環境。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_rep_guidance"
>title="實施指南"
>abstract="最佳實務是直接依賴復寫代理來檢閱、重構和最佳化自訂功能，並使其與AEM as aCloud Service相容。 請洽詢Adobe支援以取得說明和說明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#replication" text="復寫 — AEM as aCloud Service"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 請參閱AEM as aCloud Service[開發准則](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#no-reverse-replication-agents)和[復寫代理](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#replication-agents)的發行說明。
* 直接依賴複製代理來執行業務任務的功能進行審核、重構和優化。
* 查看[replication](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#replication)如何受AEM as aCloud Service中部署的影響。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決問題。
