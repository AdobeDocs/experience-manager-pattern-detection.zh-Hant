---
title: URC
description: 模式偵測器程式碼說明頁面
exl-id: 1be61351-3e3e-4e51-973f-93f8bf9bf932
translation-type: tm+mt
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# URC {#urc}

不支援的執行模式設定

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_overview"
>title="不支援的執行模式設定"
>abstract="URC識別基於運行模式名稱的配置的使用，該運行模式名稱在中不AEM作為Cloud Service。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#custom-runmodes" text="支援的執行模式"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#runmodes" text="執行模式"

`URC` 標識基於運行模式名稱的配置的使用，該運行模式名稱在中不AEM作為Cloud Service。

## 可能的影響和風險{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_guidance"
>title="實施指南"
>abstract="最佳實務是檢視應用程式中使用的所有執行模式是否受到支援，並確保它們符合執行模式解析准則"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html#deploying" text="執行模式解析度指南"

* 作為Cloud Service，可用於運行模式的AEM名稱集是有限的。
* 部署至Cloud Service時，基於不支援執行模式名稱的設定將不會產生任AEM何影響。

## 可能的解決方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_tools"
>title="工具與資源"
>abstract="檢閱WKND-legacy專案，瞭解如何讓URC違規與AEMCloud Service相容。 此外，請在Github上檢閱URC違規範例，瞭解如何更新自訂執行模式的OSGi組態，以便將它AEM視為Cloud Service。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc" text="WKND-Legacy Project"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc" text="URC違規示例- Github"

* 檢視此設定的使用，以判斷是否必要。
* 將配置更名為使用支援的[運行模式名稱](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#custom-runmodes)之一，並遵循[運行模式解析准則](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html#runmode-resolution)。
* 檢閱[wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc)專案，並瞭解如何校正[URC違規](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc)並將其與作為Cloud ServiceAEM相容。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
