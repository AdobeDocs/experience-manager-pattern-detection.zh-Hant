---
title: DG
description: 模式偵測器程式碼說明頁面
exl-id: 7ee3b177-bd79-41cd-abaf-ece3ae98ce03
translation-type: tm+mt
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 1%

---

# DG {#dg}

開發人員方針

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_overview"
>title="開發人員准則"
>abstract="DG程式碼會識別6.5和AEM6.5所選開發指南AEM的偏差情形。 遵循最佳實務可改善系統的可維護性和效能。 雖然這些偏差中的某些部分在其他應用程式環境中（包括舊版）可能不是問題，但AEM當與Cloud Service搭配使用時，可能AEM會造成問題。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html" text="開AEM發——准則與最佳實務"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html" text="AEM as a Cloud Service 開發方針"


`DG` 識別所選6.5開發指 [南的偏](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html)  [差](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html)，並AEM視為Cloud Service。遵循最佳實務可改善系統的可維護性和效能。 雖然這些偏差中的某些部分在其他應用程式環境中（包括舊版）可能不是問題，但AEM當與Cloud Service搭配使用時，可能AEM會造成問題。

子類型用於標識不同類型的檢測違規：

* `java.io.inputstream`:在應用程式 `java.io.InputStream` 碼中的使用。
* `maintenance.task.configuration`:特定定期維護活動的配置。
* `sling.commons.scheduler`:對排程工作使用Sling Commons Scheduler API。

## 可能的影響和風險{#implications-and-risks}

* `java.io.inputstream`
   * 使用`java.io.InputStream`串流二進位資料會耗用記憶體資源至影響效能的程度。 這尤其是因為容器中用作Cloud Service的可用記憶體有AEM限，所以

* `maintenance.task.configuration`
   * 一些以前需要顯式配置的維護任務現在會自動配置並作為AEMCloud Service管理。
   * 作為Cloud Service的維AEM護任務配置必須移入源控制。

* `sling.commons.scheduler`
   * 依賴於使用[Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html)背景工作的應用程式可能無法如預期般運作，因為執行無法保AEM證為Cloud Service。
   * 作為&lt;a0/AEM>後台任務和長期運行的作業的Cloud Service開發准則，建議以計畫任務方式執行的代碼必須假定它正在運行的實例可以隨時關閉。 [](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#background-tasks-and-long-running-jobs)因此，程式碼必須具彈性且可繼續。

## 可能的解決方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_guidance"
>title="實施指南"
>abstract="根據開AEM發方針和最佳實務，客戶應檢視其Sling Commons Scheduler的使用實作，並將其重新架構至Sling Jobs、重新架構其系統維護工作、審查任何二進位資料的串流，並重新調整其程式碼以符合AEMCloud Service。"
>additional-url="https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing" text="Sling 工作"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/maintenance.html" text="維護任AEM務作為Cloud Service"

* `java.io.inputstream`
   * 使用直接二進位上傳方法，將二進位檔直接新增至資料儲存區。
   * 對於資產使用案例，請使用[aem-upload](https://github.com/adobe/aem-upload)。 對於其他類型的二進位檔案，自訂上傳邏輯可以在此相同模式之後建立模型。

* `maintenance.task.configuration`
   * 以&lt;AEMa0/>維護任務](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/maintenance.html)Cloud Service文檔形式查看。[
   * 確保[維護任務配置](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#maintenance-tasks-configuration-in-source-control)處於源控制中。

* `sling.commons.scheduler`
   * 將[Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html)的使用取代為[Sling Jobs](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing)，後者具有至少一次的執行保證。
   * 如果可能，應避免長時間運行的作業。

* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
