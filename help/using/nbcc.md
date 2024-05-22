---
title: NBCC
description: 模式偵測器程式碼說明頁面。
exl-id: fa6bdd3c-4deb-41ec-878d-4ea5dc1ddf60
source-git-commit: 0d693e3ccadc81b59852914f115bb2fa2ea166b0
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 67%

---

# NBCC {#nbcc}

已棄用：不向後相容變更 (取代為 NCC，不相容變更)

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_nbcc_overview"
>title="不向後相容變更"
>abstract="NBCC會識別部分JCR節點或套件組合以不相容方式變更的狀況。 客戶在升級前可能未意識到這種變更。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes" text="重大變更 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="發行說明 - AEM as a Cloud Service"

`NBCC`  識別部分JCR節點或套件組合以不相容方式變更的狀況。 客戶在升級前可能未意識到這種變更。

## 可能的影響和風險 {#implications-and-risks}

* 依賴使用不向後相容變更之任何元件的功能可能會損壞而無法正確解析。
* 在升級後，客戶應用程式的部分功能或部分 AEM 功能可能會無法正常運作。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_nbcc_guidance"
>title="實施指導"
>abstract="最佳實務是檢閱自訂程式碼，並確保只覆蓋或參考向後相容的 Sling 元件。請聯絡 Adobe 支援人員，取得協助或說明。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-65/content/implementing/developing/platform/overlays#platform" text="覆蓋"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 只覆蓋或參考向後相容的 Sling 元件。
* 考慮調整來自的資源 `/libs` 或AEM升級後的套件組合。
* 請聯絡 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以釐清或解決問題。
