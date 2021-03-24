---
title: URC
description: 模式偵測器程式碼說明頁面
translation-type: tm+mt
source-git-commit: ae3e162da40441fba39e6e9d283c495d15f40ba1
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 0%

---


# URC {#urc}

不支援的執行模式設定

## 背景 {#background}

`URC` 標識基於運行模式名稱的配置的使用，該運行模式名稱在中不AEM作為Cloud Service。

## 可能的影響和風險{#implications-and-risks}

* 作為Cloud Service，可用於運行模式的AEM名稱集是有限的。
* 部署至Cloud Service時，基於不支援執行模式名稱的設定將不會產生任AEM何影響。

## 可能的解決方案{#solutions}

* 檢視此設定的使用，以判斷是否必要。
* 將配置更名為使用支援的[運行模式名稱](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#custom-runmodes)之一，並遵循[運行模式解析准則](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html#runmode-resolution)。
* 檢閱[wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc)專案，並瞭解如何校正[URC違規](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc)並將其與作為Cloud ServiceAEM相容。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
