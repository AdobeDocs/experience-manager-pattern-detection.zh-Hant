---
title: MI
description: 模式偵測器程式碼說明頁面
source-git-commit: aa05ebcb54c6945a903c76add4f31e3279cd05b5
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 23%

---

# MI {#mi}

設定錯誤問題

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_mi_overview"
>title="設定錯誤問題"
>abstract="MI會識別AEM執行個體上的設定問題"

`MI`  設定錯誤問題會識別AEM執行個體上的設定問題。

子類型用於識別不同類型的資訊，例如：

* `sling.job.max.parallel`：識別最大平行設定設為–1的Sling作業。
* `missing.maintenance.configuration`：識別缺少的維護任務設定。

## 可能的影響和風險 {#implications-and-risks}

* `sling.job.max.parallel`
   * 值–1會取代為可用的處理器數目。 這可能會造成AEM執行個體發生效能問題。
* `missing.maintenance.configuration`
   * 缺少維護任務設定可能會導致效能損失或執行個體損毀。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_mi_guidance"
>title="實施指導"
>abstract="請聯絡客戶服務以尋求協助。"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* `sling.job.max.parallel`
   * 建議將該值設為0.5，以便使用一半的可用處理器。
* `missing.maintenance.configuration`
   * 修訂清理：請參閱 [修訂清理](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html). 有關設定的重要部分如下： [修訂清除 — 設定尾部與完全壓縮](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html#how-to-configure-full-and-tail-compaction).
   * Lucene二進位清理：請參閱 [操作控制面板 — Lucene二進位清理](https://experienceleague.adobe.com/docs/experience-manager-65/administering/operations/operations-dashboard.html#lucene-binaries-cleanup).
   * 資料存放區垃圾收集：請參考 [資料存放區垃圾收集](https://experienceleague.adobe.com/docs/experience-manager-65/administering/operations/data-store-garbage-collection.html).
   * 工作流程清除：請參閱 [定期清除工作流程例項](https://experienceleague.adobe.com/docs/experience-manager-65/administering/operations/workflows-administering.html#regular-purging-of-workflow-instances).
   * AuditLog維護任務：請參閱 [稽核記錄維護](https://experienceleague.adobe.com/docs/experience-manager-65/administering/operations/operations-audit-log.html).
* 請聯繫我們的 [Experience Manager 客戶服務團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以釐清或解決問題。