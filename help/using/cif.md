---
title: CIF
description: 模式偵測器程式碼說明頁面
exl-id: cf9d5f62-c9dd-4f56-982c-1b5b19c81506
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 100%

---

# CIF {#cif}

Commerce Integration Framework Classic

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_overview"
>title="Commerce Integration Framework Classic"
>abstract="CIF 會識別不相容於 AEM as a Cloud Service 的 Commerce Integration Framework Classic 版本使用方式。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/introduction.html" text=" Content and Commerce"

`CIF` 會識別不相容於 AEM as a Cloud Service 的 Commerce Integration Framework Classic 版本使用方式。每個 `CIF` 發現的訊息都會識別該使用方式並提供額外資訊。

子類型用於識別不同類型的資訊：

* `commerce.integration.framework.detected`：不相容於 AEM as a Cloud Service 的 Commerce Integration Framework Classic 版本。


## 可能影響和風險 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_guidance"
>title="實施指導"
>abstract="最佳實務是檢閱所有 Commerce Integration Framework Classic 版本使用方式。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/changes.html" text="CIF 重大變更"

* AEM as a Cloud Service 不再支援 Commerce Integration Framework Classic 版本。它會防止升級到 AEM as a Cloud Service。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_tools"
>title="工具和資源"
>abstract="本指南幫助識別 Experience Manager Cloud Service 移轉時須更新的區域。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/migration.html" text="CIF 移轉指南"

* CIF 附加元件是 Experience Manager as a Cloud Service 唯一支援用於 Adobe Commerce 和第三方商務解決方案的商務整合解決方案。Experience Manager as a Cloud Service 上會自動部署 CIF 附加元件，客戶不需手動部署。請參閱 [AEM Commerce as a Cloud Service 快速入門](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/storefront/getting-started.html)。
* 為支援部署 CIF 的專案，Adobe 提供了 [AEM CIF 核心元件](https://github.com/adobe/aem-core-cif-components)。
* [軟體發佈入口網站](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html)也提供了適用於 AEM 6.5 的 CIF 附加元件。它是相容的，提供和適用於 Experience Manager as a Cloud Service 的 CIF 附加元件相同的功能，不需調整。
* Classic CIF 及其相依性已不再可用。依賴此 CIF 版本 (使用 com.adobe.cq.commerce.api Java API) 的程式碼必須調整為 CIF 附加元件及其原則。
