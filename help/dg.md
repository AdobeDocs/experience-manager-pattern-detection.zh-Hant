---
title: DG
description: 模式偵測器程式碼說明頁面
exl-id: 7ee3b177-bd79-41cd-abaf-ece3ae98ce03
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 1%

---

# DG {#dg}

開發人員指引

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_overview"
>title="開發人員准則"
>abstract="DG程式碼可識別AEM 6.5和AEM作為Cloud Service之選定開發指引的偏差。 按照最佳做法可以提高系統的可維護性和效能。 雖然這些偏差中的某些可能在其他應用程式內容(包括舊版AEM)中不會發生問題，但當與AEM搭配使用作為Cloud Service時，這些偏差可能會造成問題。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html" text="AEM開發 — 准則和最佳作法"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html" text="AEM as a Cloud Service 開發方針"


`DG` 識別AEM 6.5 [和](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html) AEM as a  [Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html)所選開發准則的偏差。按照最佳做法可以提高系統的可維護性和效能。 雖然這些偏差中的某些可能在其他應用程式內容(包括舊版AEM)中不會發生問題，但當與AEM搭配使用作為Cloud Service時，這些偏差可能會造成問題。

子類型用於標識不同類型的檢測到的違規：

* `java.io.inputstream`:在應用程式 `java.io.InputStream` 碼中的使用。
* `maintenance.task.configuration`:特定定期維護活動的配置。
* `sling.commons.scheduler`:對已排程任務使用Sling Commons排程器API。

## 可能的影響和風險{#implications-and-risks}

* `java.io.inputstream`
   * 使用`java.io.InputStream`流式傳輸二進位資料可能會佔用記憶體資源，從而影響效能。 這尤其是個問題，因為AEM作為Cloud Service使用的容器中記憶體有限。

* `maintenance.task.configuration`
   * 先前需要明確設定的某些維護任務，現在會在AEM內以Cloud Service的形式自動設定和管理。
   * AEM as aCloud Service中的維護任務配置必須移入原始碼控制項。

* `sling.commons.scheduler`
   * 使用[Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html)依賴背景任務的應用程式可能無法如預期運作，因為AEM中無法保證以Cloud Service的形式執行。
   * AEM作為[背景任務和長時間執行的作業的Cloud Service開發准則](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#background-tasks-and-long-running-jobs)建議，以排程任務執行的程式碼必須假設其執行的執行個體可隨時執行。 因此，程式碼必須具有彈性且可繼續。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_guidance"
>title="實施指南"
>abstract="遵循AEM開發准則和最佳實務，客戶應審核其使用Sling Commons排程器的實作，並將其重新建構為Sling作業、重新建構系統維護工作、審核任何二進位資料串流，並重新調整其程式碼，以符合AEM作為Cloud Service的規範。"
>additional-url="https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing" text="Sling 工作"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/maintenance.html" text="AEM as aCloud Service中的維護任務"

* `java.io.inputstream`
   * 使用直接二進位上傳方法，將二進位檔直接新增至資料存放區。
   * 若為資產使用案例，請使用[aem-upload](https://github.com/adobe/aem-upload)。 對於其他類型的二進位檔，可依此相同模式建立自訂上傳邏輯模型。

* `maintenance.task.configuration`
   * 查看AEM as aCloud Service[維護任務](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/maintenance.html)文檔。
   * 確保[維護任務配置](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#maintenance-tasks-configuration-in-source-control)在原始碼控制中。

* `sling.commons.scheduler`
   * 將[Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html)的使用取代為[Sling Jobs](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing)，其至少有一次執行保證。
   * 如果可能，應避免長時間運行的作業。

* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決問題。
