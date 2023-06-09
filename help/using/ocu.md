---
title: OCU
description: 模式偵測器程式碼說明頁面
exl-id: cb28c727-415d-436c-ab74-cf7f1f34f7c7
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: ht
source-wordcount: '298'
ht-degree: 100%

---

# OCU {#ocu}

已棄用：過時的程式碼使用方式 (取代為 OU，過時的使用方式)

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ocu_overview"
>title="過時的程式碼使用方式"
>abstract="OCU 會識別部分 JCR 節點 (例如 Sling 或 AEM 元件，或是 API OSGi 匯出) 以不相容方式變更或移除的狀況。客戶在升級前可能未意識到這種變更。這些節點可能會升級為不相容的版本或完全無法使用。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="重大變更 - AEM as a Cloud Service"

`OCU` 會識別部分 JCR 節點 (例如 Sling 或 AEM 元件，或是 API OSGi 匯出) 以不相容方式變更或移除的狀況。客戶在升級前可能未意識到這種變更。這些節點可能會升級為不相容的版本或完全無法使用。

由於預設不會安裝舊版，因此客戶應用程式可能無法正確運作。

## 可能影響和風險 {#implications-and-risks}

* 在升級後，依賴使用已棄用元件或 API 之任何元件的功能可能會損壞而無法正確解析。
* 在升級後，客戶應用程式的部分功能或部分 AEM 功能可能會無法正常運作或無法作用。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ocu_guidance"
>title="實施指導"
>abstract="最佳實務是檢閱並調整客戶程式碼以使用最新版 AEM 元件或 API。請聯繫 Adobe 支援以尋求協助與澄清。"
>additional-url="https://javadoc.io/doc/com.adobe.aem/aem-sdk-api/latest/index.html" text="Adobe Experience Manager SDK API"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 短期：安裝相容性套件可能有幫助。
* 長期：調整客戶程式碼以使用最新版 AEM 元件或 API。
* 請聯繫我們的 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以澄清或解決問題。
