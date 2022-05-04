---
title: DG
description: 模式偵測器程式碼說明頁面
exl-id: 7ee3b177-bd79-41cd-abaf-ece3ae98ce03
source-git-commit: 27820ac7a28231641c887c05aa10ff1f617bfeb5
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 93%

---

# DG {#dg}

開發人員指導方針

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_overview"
>title="開發人員指導方針"
>abstract="DG 程式碼會識別 AEM 6.5 和 AEM as a Cloud Service 選定開發指導方針的偏離。遵循最佳實務可以改進系統的可維護性和效能。儘管其中部分的偏離可能在其他應用程式 (包括舊版 AEM) 內容中不成問題，但在 AEM as a Cloud Service 中使用時則可能會造成問題。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html" text="AEM 開發 - 指導方針與最佳實務"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html" text="AEM as a Cloud Service 開發指導方針"


`DG` 會識別 [AEM 6.5](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html) 和 [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html) 選定開發指導方針的偏離。遵循最佳實務可以改進系統的可維護性和效能。儘管其中部分的偏離可能在其他應用程式 (包括舊版 AEM) 內容中不成問題，但在 AEM as a Cloud Service 中使用時則可能會造成問題。

子類型用於識別偵測到的不同違規類型：

* `java.io.inputstream`：在應用程式的程式碼中使用了 `java.io.InputStream`。
* `maintenance.task.configuration`：某種定期維護活動的設定。
* `sling.commons.scheduler`：Sling Commons Scheduler API 用於已排程任務。
* `unsupported.asset.api`:在應用程式碼中使用不支援的Asset Manager API。

## 可能影響和風險 {#implications-and-risks}

* `java.io.inputstream`
   * 使用 `java.io.InputStream` 串流處理二進位資料，可能會消耗記憶體資源到影響效能的程度。由於 AEM as a Cloud Service 中所用容器的記憶體有限，這個問題特別大。

* `maintenance.task.configuration`
   * 以前需要明確設定的部分維護任務，現在是在 AEM as a Cloud Service 內自動設定和管理的。
   * AEM as a Cloud Service 中的維護任務設定必須移至原始檔控制系統。

* `sling.commons.scheduler`
   * 因為 AEM as a Cloud Service 中無法保證執行，所以相依於背景任務 (使用 [Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html)) 的應用程式可能無法如預期運作。
   * 對於[背景任務和長時間執行工作](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#background-tasks-and-long-running-jobs)的 AEM as a Cloud Service 開發指導方針建議，執行為已排程任務的程式碼必須假設執行所在的例項隨時都會停機。因此程式碼必須有韌性和可恢復性。

* `unsupported.asset.api`
   * 以下AssetManager的API在AEMas a Cloud Service上標籤為不支援。
      * createAssetForBinary
      * getAssetForBinary
      * removeAssetForBinary
      * 建立資產

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_guidance"
>title="實施指導"
>abstract="遵循 AEM 開發指導方針與最佳實務，客戶應檢閱 Sling Commons Scheduler 的使用實施並將其重組為 Sling 工作、重組其系統維護任務、檢閱任何二進位資料的串流處理並將其程式碼重構為符合 AEM as a Cloud Service。"
>additional-url="https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing" text="Sling 工作"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/maintenance.html" text="AEM as a Cloud Service 中的維護任務"

* `java.io.inputstream`
   * 使用直接二進位上傳方法，即二進位直接新增至資料存放區。
   * 對於資產使用案例，請使用 [aem-upload](https://github.com/adobe/aem-upload)。對於其他類型的二進位資料，自訂上傳邏輯可以仿照此相同模式。

* `maintenance.task.configuration`
   * 請檢閱 AEM as a Cloud Service [維護任務](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/maintenance.html)文件。
   * 請確定[維護任務設定](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#maintenance-tasks-configuration-in-source-control)是在原始檔控制系統中進行。

* `sling.commons.scheduler`
   * 將 [Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html) 取代為 [Sling 工作](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing)，後者有至少執行一次的保證。
   * 如有可能應避免長時間執行工作。

* `unsupported.asset.api`
   * 請不使用Asset Manager不支援的API，而是使用 [aem上載](https://github.com/adobe/aem-upload)。
* 請聯繫我們的 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以澄清或解決問題。
