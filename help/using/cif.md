---
title: CIF
description: 模式偵測器程式碼說明頁面。
exl-id: cf9d5f62-c9dd-4f56-982c-1b5b19c81506
source-git-commit: 616fa84f6237893243cffc8af28c7cbe76bf32d7
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 52%

---

# CIF {#cif}

Commerce Integration Framework Classic

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_overview"
>title="Commerce Integration Framework Classic"
>abstract="CIF會識別不相容於AEMas a Cloud Service的Commerce integration framework使用傳統版本。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/content-and-commerce/introduction" text=" Content and Commerce"

CIF CIF會識別不相容於AEMas a Cloud Service的Commerce integration framework使用傳統版本。 每個的訊息 `CIF` 尋找可識別該使用方式並提供額外資訊。

子類型用於識別不同類型的資訊：

* `commerce.integration.framework.detected`：不相容於 AEM as a Cloud Service 的 Commerce Integration Framework Classic 版本。


## 可能影響和風險 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_guidance"
>title="實施指導"
>abstract="最佳實務是檢閱所有 Commerce Integration Framework Classic 版本使用方式。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/content-and-commerce/changes" text="CIF 重大變更"

* AEM as a Cloud Service 不再支援 Commerce Integration Framework Classic 版本。它會防止升級到 AEM as a Cloud Service。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_tools"
>title="工具和資源"
>abstract="本指南有助於識別您必須更新以進行Experience Manager Cloud Service移轉的區域。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/content-and-commerce/migration" text="CIF 移轉指南"

* 若為Experience Manageras a Cloud Service，CIF附加元件是Adobe Commerce和協力廠商商務解決方案唯一支援的商務整合解決方案。 Experience Manager as a Cloud Service 上會自動部署 CIF 附加元件，客戶不需手動部署。請參閱 [AEM Commerce as a Cloud Service 快速入門](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/content-and-commerce/storefront/getting-started)。
* 為了支援部署CIF的專案，Adobe提供 [AEM CIF核心元件](https://github.com/adobe/aem-core-cif-components).
* CIF附加元件也適用於AEM 6.5，提供方式為 [軟體發佈入口網站](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html). 它是相容的，提供和適用於 Experience Manager as a Cloud Service 的 CIF 附加元件相同的功能，不需調整。
* Classic CIF 及其相依性已不再可用。依賴此CIF版本(使用com.adobe.cq.commerce.api Java™ API)的程式碼必須調整為CIF附加元件及其原則。
