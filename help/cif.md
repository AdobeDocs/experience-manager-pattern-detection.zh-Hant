---
title: CIF
description: 模式偵測器程式碼說明頁面
exl-id: 500e0d32-e75e-4abe-a96b-0692ce40c086
source-git-commit: 84aea5b24e51ce5672826bad4ec126074bf24a09
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---

# CIF {#cif}

Commerce Integration Framework Classic

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_overview"
>title="Commerce Integration Framework Classic"
>abstract="CIF可識別與AEM作為Cloud Service不相容的Commerce Integration Framework傳統使用版本。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/introduction.html" text=" 內容與商務"

`CIF` CIF可識別與AEM作為Cloud Service不相容的Commerce Integration Framework傳統使用版本。每個`CIF`結果的訊息將識別使用情形並提供其他資訊。

子類型用於識別不同類型的資訊：

* `commerce.integration.framework.detected`:Commerce Integration Framework的傳統版本與AEM as aCloud Service不相容。


## 可能的影響和風險{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_guidance"
>title="實施指南"
>abstract="最佳實務是檢閱Commerce Integration Framework的所有傳統版本使用情形。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/changes.html" text="CIF的重大變更"

* AEM as a Cloud Service不再支援傳統版的Commerce Integration Framework。 這會封鎖升級至AEM as aCloud Service。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_tools"
>title="工具和資源"
>abstract="本指南可協助您識別Experience Manager Cloud Service移轉所需更新的領域。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/migration.html" text="CIF移轉指南"

* 針對Experience Manager作為Cloud Service,CIF附加元件是Adobe商務和第三方商務解決方案唯一支援的商務整合解決方案。 CIF附加元件會自動部署給Experience ManagerCloud Service的客戶，不需手動部署。 請參閱[AEM Commerce as aCloud Service快速入門](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/storefront/getting-started.html)。
* 若要支援專案部署CIFAdobe，請提供[AEM CIF核心元件](https://github.com/adobe/aem-core-cif-components)。
* AEM 6.5也可透過[Software Distribution入口網站](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html)使用CIF附加元件。 它與CIF附加元件相容，提供與Experience ManagerCloud Service相同的功能 — 不需要進行調整。
* 傳統CIF及其相依性已無法使用。 依賴此CIF版本(使用com.adobe.cq.commerce.api Java API)的程式碼必須調整為CIF附加元件及其原則。
