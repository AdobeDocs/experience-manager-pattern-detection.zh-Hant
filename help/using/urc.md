---
title: URC
description: 模式偵測器程式碼說明頁面。
exl-id: 1be61351-3e3e-4e51-973f-93f8bf9bf932
source-git-commit: 982ad1a6f43a29f2ee2284219757c8fc11b31ce0
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 24%

---

# URC {#urc}

不支援的執行模式設定

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_overview"
>title="不支援的執行模式設定"
>abstract="URC會識別基於AEMas a Cloud Service不支援之執行模式名稱之設定的使用。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes#custom-runmodes" text="支援的執行模式"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/deploying/overview#runmodes" text="執行模式"

URC會識別基於AEMas a Cloud Service不支援之執行模式名稱之設定的使用。

## 可能影響和風險 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_guidance"
>title="實施指導"
>abstract="最佳實務是檢閱應用程式中使用的所有執行模式是否受支援，並確保其遵循執行模式解析指導方針"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/deploying/configuring-osgi#deploying" text="執行模式解析指導方針"

* 可用於在AEMas a Cloud Service中執行各種模式的名稱集是有限的。
* 基於不支援之執行模式名稱的設定，在部署至AEMas a Cloud Service時不會生效。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_tools"
>title="工具和資源"
>abstract="請檢閱 WKND 舊版專案以了解如何將 URC 違規設為相容於 AEM Cloud Service。也請檢閱GitHub上的URC違規範例，以瞭解如何更新自訂執行模式型OSGi設定以遵守AEMas a Cloud Service。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc" text="WKND-舊版專案"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc" text="URC違規範例 — GitHub"

* 請檢閱此設定的使用，以便您判斷其是否必要。
* 使用其中一個支援的重新命名設定 [執行模式名稱](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes#custom-runmodes) 和追隨 [執行模式解析指導方針](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/deploying/configuring-osgi#runmode-resolution).
* 請檢閱 [WKND 舊版](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc)專案，了解如何更正 [URC 違規](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc)，使其與 AEM as a Cloud Service 相容。
* 聯絡 [AEM支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html) 以澄清或解決問題。
