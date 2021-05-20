---
title: URC
description: 模式偵測器程式碼說明頁面
exl-id: 1be61351-3e3e-4e51-973f-93f8bf9bf932
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# URC {#urc}

不支援的運行模式配置

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_overview"
>title="不支援的運行模式配置"
>abstract="URC會根據AEM作為Cloud Service不支援的執行模式名稱來識別設定的使用情形。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#custom-runmodes" text="支援的執行模式"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#runmodes" text="執行模式"

`URC` 識別以AEM作為Cloud Service不支援的執行模式名稱為基礎之設定的使用。

## 可能的影響和風險{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_guidance"
>title="實施指南"
>abstract="最佳實務是檢查應用程式中使用的所有執行模式是否均受支援，並確保它們遵循執行模式解析准則"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html#deploying" text="Runmode解析度指南"

* 在AEM as aCloud Service中，可用於執行模式的名稱集有限。
* 部署至AEM作為Cloud Service時，以不支援的執行模式名稱為基礎的設定將沒有任何作用。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_tools"
>title="工具和資源"
>abstract="檢閱WKND-legacy專案，了解如何讓URC違規與AEMCloud Service相容。 此外，檢閱Github上的URC違規範例，了解如何更新以自訂執行模式為基礎的OSGi設定，以符合AEM as aCloud Service。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc" text="WKND-Legacy專案"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc" text="URC違規示例 — Github"

* 檢閱此設定的使用，以判斷是否必要。
* 重新命名配置以使用支援的[運行模式名稱](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#custom-runmodes)之一，並遵循[運行模式解析指南](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html#runmode-resolution)。
* 檢閱[wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc)專案，並了解如何更正[URC違規](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc)並使其與AEM as aCloud Service相容。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決問題。
