---
title: URC
description: 模式偵測器程式碼說明頁面
exl-id: 1be61351-3e3e-4e51-973f-93f8bf9bf932
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 100%

---

# URC {#urc}

不支援的執行模式設定

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_overview"
>title="不支援的執行模式設定"
>abstract="URC 會識別基於 AEM as a Cloud Service 不支援執行模式名稱之設定的使用。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#custom-runmodes" text="支援的執行模式"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#runmodes" text="執行模式"

`URC` 會識別基於 AEM as a Cloud Service 不支援執行模式名稱之設定的使用。

## 可能影響和風險 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_guidance"
>title="實施指導"
>abstract="最佳實務是檢閱應用程式中使用的所有執行模式是否受支援，並確保其遵循執行模式解析指導方針。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html#deploying" text="執行模式解析指導方針"

* AEM as a Cloud Service 中可用的執行模式名稱集有限。
* 基於不支援之執行模式名稱的設定，在部署到 AEM as a Cloud Service 時沒有任何作用。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_tools"
>title="工具和資源"
>abstract="請檢閱 WKND 舊版專案以了解如何將 URC 違規設為相容於 AEM Cloud Service。也請檢閱 Github 上的 URC 違規範例，了解如何更新自訂執行模式型 OSGi 設定以遵守 AEM as a Cloud Service。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc" text="WKND-舊版專案"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc" text="URC 違規範例 - Github"

* 請檢閱此設定的使用，以決定其是否必要。
* 重新命名設定以使用其中一個支援的[執行模式名稱](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#custom-runmodes)，並遵循[執行模式解析指導方針](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html#runmode-resolution)。
* 請檢閱 [WKND 舊版](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc)專案，了解如何更正 [URC 違規](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc)，使其與 AEM as a Cloud Service 相容。
* 請聯繫我們的 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以澄清或解決問題。
