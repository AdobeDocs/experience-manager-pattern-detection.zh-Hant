---
title: DG
description: 模式偵測器程式碼說明頁面。
exl-id: 7ee3b177-bd79-41cd-abaf-ece3ae98ce03
source-git-commit: dd60fb9fb21d534e7b6f264826d3cc1477def421
workflow-type: ht
source-wordcount: '596'
ht-degree: 100%

---

# DG {#dg}

開發人員指導方針

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_overview"
>title="開發人員指導方針"
>abstract="DG 程式碼會識別 AEM 6.5 和 AEM as a Cloud Service 選定開發指導方針的偏離。遵循最佳實務可以改進系統的可維護性和效能。儘管其中部分的偏離可能在其他應用程式 (包括舊版 AEM) 內容中不成問題，但在 AEM as a Cloud Service 中使用時則可能會造成問題。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-65/content/implementing/developing/introduction/dev-guidelines-bestpractices" text="AEM 開發 - 指導方針與最佳實務"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines" text="AEM as a Cloud Service 開發指導方針"


`DG` 會識別 [AEM 6.5](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-65/content/implementing/developing/introduction/dev-guidelines-bestpractices) 和 [AEM as a Cloud Service](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines) 選定開發指導方針的偏離。遵循最佳實務可以改進系統的可維護性和效能。儘管其中部分的偏離可能在其他應用程式 (包括舊版 AEM) 內容中不成問題，但在 AEM as a Cloud Service 中使用時則可能會造成問題。

子類型用於識別偵測到的不同違規類型：

* `java.io.inputstream`：在應用程式的程式碼中使用了 `java.io.InputStream`。
* `maintenance.task.configuration`：某種定期維護活動的設定。
* `sling.commons.scheduler`：Sling Commons Scheduler API 用於已排程任務。
* `unsupported.asset.api`：在應用程式程式碼中使用不受支援的 Asset Manager API。
* `javax.jcr.observation.EventListener`：在應用程式的程式碼中使用事件監聽程式。
* `custom.guava.cache`：在應用程式的程式碼中使用 Guava 快取。

## 可能的影響和風險 {#implications-and-risks}

* `java.io.inputstream`
   * 使用 `java.io.InputStream` 串流處理二進位資料，可能會消耗記憶體資源到影響效能的程度。這個問題是因為 AEM as a Cloud Service 中所用容器的記憶體有限所致。

* `maintenance.task.configuration`
   * 以前需要明確設定的部分維護任務，現在是在 AEM as a Cloud Service 內自動設定和管理的。
   * AEM as a Cloud Service 中的維護任務設定必須移至原始檔控制系統。

* `sling.commons.scheduler`
   * 因為 AEM as a Cloud Service 中無法保證執行，所以相依於背景任務 (使用 [Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html)) 的應用程式可能無法如預期運作。
   * 對於[背景任務和長時間執行工作](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines#background-tasks-and-long-running-jobs)的指導方針建議，執行為已排程任務的程式碼也必須假設執行所在的執行個體隨時都會停機。因此程式碼必須有韌性和可恢復性。

* `unsupported.asset.api`
   * 下列 AssetManager API 在 AEM as a Cloud Service 中被標記為不受支援。
      * createAssetForBinary
      * getAssetForBinary
      * removeAssetForBinary
      * createAsset

* `javax.jcr.observation.EventListener`
   * 依賴於事件監聽程式的應用程式可能無法如預期般運作，因為無法保證執行。

* `custom.guava.cache`
   * 使用 Guava 快取可能會導致 AEM 出現性能問題。


## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_guidance"
>title="實施指導"
>abstract="檢閱您在使用 Sling Commons Scheduler 方面的實施。將這些重組為 Sling Jobs、重組其系統維護任務，檢閱任何二進位資料的串流，並重構其程式碼以符合 AEM as a Cloud Service 的要求。"
>additional-url="https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing" text="Sling 工作"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/operations/maintenance" text="AEM as a Cloud Service 中的維護任務"

* `java.io.inputstream`
   * 使用直接二進位上傳方法，即二進位直接新增至資料存放區。
   * 對於資產使用案例，請參閱 [aem-upload](https://github.com/adobe/aem-upload)。對於其他類型的二進位資料，自訂上傳邏輯可以仿照此相同模式。

* `maintenance.task.configuration`
   * 請檢閱 AEM as a Cloud Service [維護任務](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/operations/maintenance)文件。
   * 請確定[維護任務設定](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/implementing/deploying/overview#maintenance-tasks-configuration-in-source-control)是在原始檔控制系統中進行。

* `sling.commons.scheduler`
   * 將 [Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html) 取代為 [Sling 工作](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing)，後者有至少執行一次的保證。
   * 如有可能應避免長時間執行工作。

* `unsupported.asset.api`
   * 不要再使用不受支援的 Asset Manager API，請參閱 [aem-upload](https://github.com/adobe/aem-upload)。

* `javax.jcr.observation.EventListener`
   * 與其使用事件監聽程式，建議將事件處理機制重構為 [Sling 工作](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing)，因為它提供了處理的保證。

* `custom.guava.cache`
   * 如果需要，應該在 AEM 外部建立快取。可以考慮外部快取解決方案。
* 請聯絡 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以釐清或解決問題。
