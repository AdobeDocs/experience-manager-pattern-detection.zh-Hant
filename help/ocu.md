---
title: OCU
description: 模式偵測器程式碼說明頁面
exl-id: cb28c727-415d-436c-ab74-cf7f1f34f7c7
translation-type: tm+mt
source-git-commit: 76dc944f1592118920f89c513faf456b8aa443a9
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 0%

---

# OCU {#ocu}

過期的程式碼使用

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ocu_overview"
>title="過期的程式碼使用"
>abstract="OCU會識別某些JCR節點(例如Sling或AEM元件或API OSGi匯出)以不相容的方式變更或移除的情形。 在升級前，客戶可能不知道此項變更。 它們可能會升級為不相容的版本，或完全無法使用。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="顯著變AEM更——作為Cloud Service"

`OCU` 識別某些JCR節點(例如Sling或AEM元件或API OSGi匯出)以不相容方式變更或移除的情形。在升級前，客戶可能不知道此項變更。 它們可能會升級為不相容的版本，或完全無法使用。

由於舊版本預設未安裝，因此客戶應用程式可能無法正常運作。

## 可能的影響和風險{#implications-and-risks}

* 依賴任何使用已過時元件或API的元件的功能可能會中斷，而且升級後可能無法正確解析。
* 客戶應用程式的某些功能或AEM某些功能可能無法正常運作，或在升級後可能無法作用。

## 可能的解決方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ocu_guidance"
>title="實施指南"
>abstract="最佳實務是檢閱並調整客戶程式碼，以使用最新版AEM的元件或API。 聯絡Adobe支援以取得說明。"
>additional-url="https://javadoc.io/doc/com.adobe.aem/aem-sdk-api/latest/index.html" text="Adobe Experience ManagerSDK API"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 短期：安裝相容性軟體包可能會有所幫助。
* 長期：調整客戶程式碼，以使用最新版AEM的元件或API。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
