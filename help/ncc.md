---
title: NCC
description: 模式偵測器程式碼說明頁面
source-git-commit: fdc3e8bdef27de971743a9ecb04d3912cf8e60ad
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 3%

---

# NCC {#ncc}

不相容的變更

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ncc_overview"
>title="不相容的變更"
>abstract="NCC可識別某些JCR節點或套件組合以不相容方式變更的情況。 升級前，客戶可能不知道此更改。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="重大變更 — AEMas a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hant" text="發行說明 — AEMas a Cloud Service"

`NCC` 識別某些JCR節點或套件組合以不相容方式變更的情況。 升級前，客戶可能不知道此更改。

## 可能的影響和風險 {#implications-and-risks}

* 依賴使用不相容變更的任何元件的功能可能會失效，且可能無法正確解析。
* 升級後，客戶應用程式的某些功能或AEM功能可能無法正常運作。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ncc_guidance"
>title="實施指南"
>abstract="最佳實務是檢閱自訂程式碼，並確保只覆蓋或參照相容的Sling元件。 請洽詢Adobe支援以取得說明和說明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html#platform" text="覆蓋"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 覆蓋或僅參考相容的Sling元件。
* 考慮調整來自 `/libs` 或AEM升級後的套件組合。
* 請聯繫我們的 [AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) 以取得澄清或處理關注。
