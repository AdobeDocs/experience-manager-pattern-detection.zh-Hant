---
title: MI
description: 模式偵測器程式碼說明頁面。
exl-id: fa47ac63-1b5d-43b3-8acd-4a71c3fa714e
source-git-commit: 982ad1a6f43a29f2ee2284219757c8fc11b31ce0
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 54%

---

# MI {#mi}

設定錯誤問題

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_mi_overview"
>title="設定錯誤問題"
>abstract="MI 會識別 AEM 執行個體的設定問題"

MI設定錯誤問題會識別AEM執行個體上的設定問題。

子類型用於識別不同類型的資訊，例如：

* `sling.job.max.parallel`：識別最大並行設定為 -1 的 Sling 工作。
* `missing.maintenance.configuration`：識別缺少維護任務設定。

## 可能影響和風險 {#implications-and-risks}

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
   * Adobe建議將此值設定為0.5，以充分利用一半的可用處理器。
* `missing.maintenance.configuration`
   * 修訂清除：請參閱 [修訂清除](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/deploying/revision-cleanup). 關於設定的重要部分位於：[修訂清除 - 設定尾部和完全壓縮](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/deploying/revision-cleanup)。
   * Lucene二進位清理：請參閱 [操作控制面板 — Lucene二進位清理](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/operations/operations-dashboard#lucene-binaries-cleanup).
   * 資料存放區記憶體回收：請參閱 [資料存放區記憶體回收](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/operations/data-store-garbage-collection).
   * 工作流程永久刪除：請參閱 [定期清除工作流程執行個體](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/operations/workflows-administering#regular-purging-of-workflow-instances).
   * AuditLog維護作業：請參閱 [稽核記錄維護](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/operations/operations-audit-log).
* 聯絡 [Experience Manager客戶服務團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html) 以澄清或解決問題。
