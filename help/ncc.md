---
title: NCC
description: 模式偵測器程式碼說明頁面
exl-id: 4a374956-c64e-43fc-8279-ed25f6ed5cb0
source-git-commit: 8b8d902dc5b5a8534475d256c199dc235bb35464
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 100%

---

# NCC {#ncc}

不相容變更

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ncc_overview"
>title="不相容變更"
>abstract="NCC 會識別部分 JCR 節點或套件組合以不相容方式變更的狀況。客戶在升級前可能未意識到這種變更。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="重大變更 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hant" text="發行說明 - AEM as a Cloud Service"

`NCC` 會識別部分 JCR 節點或套件組合以不相容方式變更的狀況。客戶在升級前可能未意識到這種變更。

## 可能影響和風險 {#implications-and-risks}

* 依賴使用不相容變更之任何元件的功能可能會損壞而無法正確解析。
* 在升級後，客戶應用程式的部分功能或部分 AEM 功能可能會無法正常運作。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ncc_guidance"
>title="實施指導"
>abstract="最佳實務是檢閱自訂程式碼，並確保只覆蓋或參考相容的 Sling 元件。請聯繫 Adobe 支援以尋求協助與澄清。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html#platform" text="覆蓋"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 只覆蓋或參考相容的 Sling 元件。
* 考慮在 AEM 升級後調整來自 `/libs` 或套件組合的資源。
* 請聯繫我們的 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以澄清或解決問題。
