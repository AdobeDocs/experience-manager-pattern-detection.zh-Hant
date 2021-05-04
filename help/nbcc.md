---
title: NBCC
description: 模式偵測器程式碼說明頁面
exl-id: fa6bdd3c-4deb-41ec-878d-4ea5dc1ddf60
translation-type: tm+mt
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 3%

---

# NBCC {#nbcc}

不向後相容的變更

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_nbcc_overview"
>title="不向後相容的變更"
>abstract="NBCC標識某些JCR節點或束以不相容方式更改的情況。 在升級前，客戶可能不知道此項變更。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="顯著變AEM更——作為Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hant" text="發行說明-AEM做為Cloud Service"

`NBCC` 標識某些JCR節點或捆綁包以不相容的方式更改的情況。在升級前，客戶可能不知道此項變更。

## 可能的影響和風險{#implications-and-risks}

* 依賴任何使用非向後相容變更的元件的功能可能會中斷，且可能無法正確解析。
* 升級後，客戶應用程式的某些功能AEM或某些功能可能無法正常運作。

## 可能的解決方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_nbcc_guidance"
>title="實施指南"
>abstract="最佳實務是檢閱自訂程式碼，並確保只覆蓋或參考向後相容的Sling元件。 聯絡Adobe支援以取得說明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html#platform" text="覆蓋"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 覆蓋或僅參考向後相容的Sling元件。
* 請考慮調整升級後`/libs`或搭售的資AEM源。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
