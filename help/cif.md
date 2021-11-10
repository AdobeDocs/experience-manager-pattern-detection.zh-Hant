---
title: CIF
description: 模式偵測器程式碼說明頁面
source-git-commit: b611b595267e60df8a15511a8a2b4b30b601df1b
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 2%

---

# CIF {#cif}

Commerce Integration Framework Classic

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_overview"
>title="Commerce Integration Framework Classic"
>abstract="CIF可識別與AEMas a Cloud Service不相容的Commerce Integration Framework傳統使用版本。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/introduction.html" text=" 內容與商務"

`CIF` CIF可識別與AEMas a Cloud Service不相容的Commerce Integration Framework傳統使用版本。 每個 `CIF` 結果會識別使用情形，並提供其他資訊。

子類型用於識別不同類型的資訊：

* `commerce.integration.framework.detected`:傳統版本的Commerce Integration Framework與AEM as a Cloud Service不相容。


## 可能的影響和風險 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_guidance"
>title="實施指南"
>abstract="最佳實務是檢閱Commerce Integration Framework的所有傳統版本使用情形。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/changes.html" text="CIF的重大變更"

* AEM as a Cloud Service不再支援傳統版本的Commerce Integration Framework。 會封鎖升級至AEMas a Cloud Service。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_tools"
>title="工具和資源"
>abstract="本指南可協助您識別Experience Manager Cloud Service移轉所需更新的領域。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/migration.html" text="CIF移轉指南"

* 對於Experience Manageras a Cloud Service,CIF附加元件是Adobe Commerce和第三方商務解決方案唯一支援的商務整合解決方案。 CIF附加元件會在Experience Manageras a Cloud Service時為客戶自動部署，不需手動部署。 請參閱 [AEM Commerce as a Cloud Service快速入門](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/storefront/getting-started.html).
* 若要支援專案部署CIFAdobe, [AEM CIF核心元件](https://github.com/adobe/aem-core-cif-components).
* AEM 6.5也可使用CIF附加元件，可透過 [Software Distribution入口網站](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html). 與CIF附加元件相容，可提供與Experience Manageras a Cloud Service的相同功能 — 不需要進行調整。
* 傳統CIF及其相依性已無法使用。 依賴此CIF版本(使用com.adobe.cq.commerce.api Java API)的程式碼必須調整為CIF附加元件及其原則。
