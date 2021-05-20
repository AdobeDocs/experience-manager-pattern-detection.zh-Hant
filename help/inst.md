---
title: INST
description: 模式偵測器程式碼說明頁面
exl-id: 9b8129d7-63d7-4975-a68b-9ba704d01532
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 0%

---

# INST {#inst}

已安裝的對象

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_overview"
>title="已安裝的對象"
>abstract="INST識別客戶在AEM中安裝的自訂和第三方套件和套件組合。 這些報告有助於描述系統狀態和升級工作的一般範圍。 任何協力廠商套件都必須遵循AEM，作為Cloud Service開發和封裝准則。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html" text="開發准則 — AEM as aCloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/repository-structure-package.html" text="封裝准則 — AEM as aCloud Service"

`INST` 識別客戶已在AEM中安裝的自訂和協力廠商套件和套件組合。這些報告有助於描述系統狀態和升級工作的一般範圍。

安裝多個版本的套件時，只會報告最新版本。

偵測到的套件和套件組合不一定已針對AEM作為Cloud Service而最佳化。 任何協力廠商套件都應與其建立者或Adobe驗證，以與AEM作為Cloud Service相容。

子類型用於識別不同類型的資訊：

* `custom.bundle`:已安裝在AEM中的套件組合。
* `custom.package`:已在AEM中安裝的套件。

## 可能的影響和風險{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_guidance"
>title="實施指南"
>abstract="客戶無法再使用CRX封裝管理器安裝第三方封裝。 客戶應檢閱這些已安裝的成品，並需要進行結構和最佳化，才能與AEM搭配Cloud Service。 任何協力廠商套件都應與其建立者或Adobe驗證，以與AEM作為Cloud Service相容。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#embeddeds" text="在容器包中嵌入子包"


* 在AEM as aCloud Service中，無法使用CRX Package Manager安裝協力廠商套件。
* 依賴第三方套件的應用程式可能無法如預期運作，除非正確部署，才能搭配AEM作為Cloud Service運作。
* 協力廠商套件(如果未針對AEM as a Cloud Service進行最佳化)可能會產生不適當的行為。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_tools"
>title="工具和資源"
>abstract="查看WKND-legacy項目，了解如何使INST違規與AEMCloud Service相容。 此外，在Github上檢閱INST違規範例，了解如何更正並部署在AEM中作為Cloud Service。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst" text="WKND-Legacy專案"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst" text="INST違規示例 — Github"

* 在專案中，應使用Cloud Manager [部署程式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/using-cloud-manager/deploy-code.html#deployment-process)，將協力廠商套件部署至AEM。
* 檢閱如何在AEM as aCloud Service的專案中[內嵌協力廠商套件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#embedding-3rd-party-packages)。
* 協力廠商套件必須遵循AEM as aCloud Service[development](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html)和[packaging](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/repository-structure-package.html)准則。
* 檢閱[wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst)專案，並了解如何更正[INST違規](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst)並使其與AEM作為Cloud Service相容。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決問題。
