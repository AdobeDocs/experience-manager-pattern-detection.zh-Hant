---
title: MI
description: 模式偵測器程式碼說明頁面。
exl-id: fa47ac63-1b5d-43b3-8acd-4a71c3fa714e
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: ht
source-wordcount: '196'
ht-degree: 100%

---

# MI {#mi}

設定錯誤問題

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_mi_overview"
>title="設定錯誤問題"
>abstract="MI 會識別 AEM 執行個體的設定問題"

`MI` (設定錯誤問題) 會識別 AEM 執行個體的設定問題。

子類型用於識別不同類型的資訊，例如：

* `sling.job.max.parallel`：識別最大並行設定為 -1 的 Sling 工作。
* `missing.maintenance.configuration`：識別缺少維護任務設定。

## 可能的影響和風險 {#implications-and-risks}

* `sling.job.max.parallel`
   * 值 -1 將替換為可用處理器的數量。這可能會導致 AEM 執行個體出現性能問題。
* `missing.maintenance.configuration`
   * 缺少維護任務設定可能會導致性能損失或執行個體損毀。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_mi_guidance"
>title="實施指導"
>abstract="請聯絡客戶服務以尋求協助。"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* `sling.job.max.parallel`
   * Adobe 建議將該值設為 0.5，以利用一半的可用處理器。
* `missing.maintenance.configuration`
   * 修訂清除：請參閱 [修訂清除](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-65/content/implementing/deploying/deploying/revision-cleanup)。關於設定的重要部分位於：[修訂清除 - 設定尾部和完全壓縮](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-65/content/implementing/deploying/deploying/revision-cleanup)。
   * Lucene 二進位檔案清除：請參閱[作業儀表板 - Lucene 二進位檔案清除](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-65/content/sites/administering/operations/operations-dashboard#lucene-binaries-cleanup)。
   * 資料存放區垃圾收集：請參閱[資料存放區垃圾收集](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-65/content/sites/administering/operations/data-store-garbage-collection)。
   * 工作流程清除：請參閱[定期清除工作流程實例](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-65/content/sites/administering/operations/workflows-administering#regular-purging-of-workflow-instances)。
   * 稽核記錄維護任務：請參閱[稽核記錄維護](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-65/content/sites/administering/operations/operations-audit-log)。
* 請聯絡 [Experience Manager 客戶服務團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以釐清或解決問題。
