---
title: 歐
description: 模式偵測器程式碼說明頁面
source-git-commit: fdc3e8bdef27de971743a9ecb04d3912cf8e60ad
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 0%

---

# 歐 {#ou}

過期使用

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ou_overview"
>title="過期使用"
>abstract="OU會識別某些JCR節點(例如Sling或AEM元件或API OSGi匯出)以不相容方式變更或移除的情況。 升級前，客戶可能不知道此更改。 它們可能升級至不相容的版本，或完全無法使用。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="重大變更 — AEMas a Cloud Service"

`OU` 識別某些JCR節點(例如Sling或AEM元件或API OSGi匯出)以不相容方式變更或移除的情況。 升級前，客戶可能不知道此更改。 它們可能升級至不相容的版本，或完全無法使用。

由於預設未安裝舊版本，因此客戶應用程式可能無法正常運作。

## 可能的影響和風險 {#implications-and-risks}

* 依賴任何使用已棄用元件或API的元件的功能可能會中斷，且在升級後可能無法正確解析。
* 客戶應用程式的某些功能或某些AEM功能可能無法正常運作，或在升級後可能無法運作。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ou_guidance"
>title="實施指南"
>abstract="最佳實務是檢閱和調整客戶程式碼，以使用最新版AEM元件或API。 請聯絡Adobe支援以取得說明和說明。"
>additional-url="https://javadoc.io/doc/com.adobe.aem/aem-sdk-api/latest/index.html" text="Adobe Experience Manager SDK API"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 短期：安裝相容性套件可能有所幫助。
* 長期：調整客戶程式碼，使用最新版AEM元件或API。
* 請聯繫我們的 [AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) 以取得澄清或處理關注。
