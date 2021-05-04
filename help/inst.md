---
title: INST
description: 模式偵測器程式碼說明頁面
exl-id: 9b8129d7-63d7-4975-a68b-9ba704d01532
translation-type: tm+mt
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
>abstract="INST標識客戶已安裝的定製和第三方包AEM和捆綁包。 這些報告有助於描述系統的狀態和升級工作的一般範圍。 任何協力廠商套件都必須遵AEM守Cloud Service開發與包裝准則。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html" text="開發指AEM引——作為Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/repository-structure-package.html" text="包裝准則-AEM作為Cloud Service"

`INST` 識別客戶已安裝的自訂和協力廠商套件AEM和套件。這些報告有助於描述系統的狀態和升級工作的一般範圍。

當安裝了多個版本的軟體包時，僅報告最新版本。

檢測到的包和包不一定已優化AEM為Cloud Service。 任何協力廠商套件都應以其製作者或Adobe來驗證，以便與AEMCloud Service相容。

子類型用於標識不同類型的資訊：

* `custom.bundle`:已安裝在中的包AEM。
* `custom.package`:已安裝的軟體包AEM。

## 可能的影響和風險{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_guidance"
>title="實施指南"
>abstract="客戶無法再使用CRX Package Manager安裝第三方套件。 客戶應檢閱這些已安裝的對象，並需要進行結構化和優化，以便將其作AEM為Cloud Service使用。 任何協力廠商套件都應以其製作者或Adobe來驗證，以便與AEMCloud Service相容。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#embeddeds" text="將子包嵌入容器包中"


* 在中，不能使用CRX Package Manager安裝第三方包AEM作為Cloud Service。
* 依賴第三方套件的應用程式可能無法如預期般運作，直到正確部署後才能AEM當成Cloud Service使用。
* 第三方供應商包(如果未針對雲服務進AEM行優化)可能會導致不想要的行為。

## 可能的解決方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_tools"
>title="工具與資源"
>abstract="查看WKND-legacy項目，瞭解如何使INST違規與AEMCloud Service相容。 此外，在Github上查看INST違規示例以瞭解如何更正此漏洞並將其作為AEMCloud Service部署。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst" text="WKND-Legacy Project"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst" text="INST違規示例- Github"

* 應使用Cloud Manager [部AEM署過程](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/using-cloud-manager/deploy-code.html#deployment-process)將第三方軟體包部署到項目中。
* 檢視如何將[內嵌在專案中的協力廠商套件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#embedding-3rd-party-packages)做為AEMCloud Service。
* 第三方包裝必須遵AEM守Cloud Service[development](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html)和[封裝](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/repository-structure-package.html)准則。
* 檢閱[wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst)專案，並瞭解如何校正[INST違規](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst)，並將其與之相容AEM為Cloud Service。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
