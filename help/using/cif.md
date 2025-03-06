---
title: CIF
description: 模式偵測器程式碼說明頁面。
exl-id: cf9d5f62-c9dd-4f56-982c-1b5b19c81506
source-git-commit: 8dd9a42a3bba63d62fa2469b0f78ca15a608b4f9
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 76%

---

# CIF {#cif}

Commerce Integration Framework Classic

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_overview"
>title="Commerce Integration Framework Classic"
>abstract="CIF 會識別不相容於 AEM as a Cloud Service 的 Commerce Integration Framework Classic 版本使用方式。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/content-and-commerce/introduction" text=" Content and Commerce"

`CIF` 會識別不相容於 AEM as a Cloud Service 的 Commerce Integration Framework Classic 版本使用方式。每個 `CIF` 發現的訊息都會識別該使用方式並提供額外資訊。

子類型用於識別不同類型的資訊：

* `commerce.integration.framework.detected`：不相容於 AEM as a Cloud Service 的 Commerce Integration Framework Classic 版本。


## 可能的影響和風險 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_guidance"
>title="實施指導"
>abstract="最佳實務是檢閱所有 Commerce Integration Framework Classic 版本使用方式。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/content-and-commerce/changes" text="CIF 重大變更"

* AEM as a Cloud Service 不再支援 Commerce Integration Framework Classic 版本。它會防止升級到 AEM as a Cloud Service。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_tools"
>title="工具和資源"
>abstract="本指南幫助識別 Experience Manager Cloud Service 移轉時必須更新的區域。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/content-and-commerce/migration" text="CIF 移轉指南"

* CIF 附加元件是 Experience Manager as a Cloud Service 唯一支援用於 Adobe Commerce 和第三方商務解決方案的商務整合解決方案。Experience Manager as a Cloud Service 上會自動部署 CIF 附加元件，客戶不需手動部署。請參閱 [AEM Commerce as a Cloud Service 快速入門](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/content-and-commerce/storefront/getting-started)。
* 為支援部署 CIF 的專案，Adobe 提供了 [AEM CIF 核心元件](https://github.com/adobe/aem-core-cif-components)。
* [軟體發佈入口網站](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html)也提供了適用於 AEM 6.5 的 CIF 附加元件。它是相容的，提供和適用於 Experience Manager as a Cloud Service 的 CIF 附加元件相同的功能，不需調整。
* Classic CIF 及其相依性已不再可用。依賴此 CIF 版本 (使用 com.adobe.cq.commerce.api Java™ API) 的程式碼必須調整為 CIF 附加元件及其原則。

此外，尋找以下不同子型別的可能解決方案：

* `commerce.bundles.detected` — 這些套件組合將在升級期間解除安裝
* `commerce.packages.detected` — 這些套件將在升級期間刪除
* `commerce.packages.dependency` — 從自訂套件中移除對Commerce的任何相依性
* `commerce.nodes.detected` — 更新自訂程式碼以不建立CQ Commerce節點
* `commerce.configs.detected` — 請勿在自訂程式碼中使用CQ Commerce設定屬性
* `commerce.users.detected` — 請勿在自訂程式碼中使用CQ Commerce服務使用者
* `commerce.overlays.detected` — 移除CQ Commerce覆蓋圖使用方式
* `commerce.paths.detected` — 在確定AEM上未使用這些路徑後，移除商務路徑
* `commerce.resource.type.detected` — 移除Commerce資源型別使用狀況
* `commerce.usage` — 移除自訂程式碼中的CQ Commerce API。
