---
title: CDW
description: 模式偵測器程式碼說明頁面。
exl-id: a9e9dae8-0aa2-4679-a3c1-418cab01cfda
source-git-commit: d1c652a8a45a081661ffe4443f85fcc932947541
workflow-type: ht
source-wordcount: '139'
ht-degree: 100%

---

# CDW {#cdw}

自訂對話框 Widget

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cdw_overview"
>title="自訂對話框 Widget"
>abstract="CDW 可識別應該更新的自訂對話框 Widget，以便使其與 AEM as a Cloud Service 相容。"

`CDW`  (`Custom Dialog Widgets`) 可識別自訂傳統對話框 Widget。這些 Widget 應該更新為與 AEM as a Cloud Service 相容。

子類型是用來識別資訊，例如：

* `custom.classic.widget`：識別以 ExtJs 為根據的自訂對話框 Widget。

## 可能的影響和風險 {#implications-and-risks}

* Classic UI 無法再用於 AEM as a Cloud Service。標準製作介面是已啟用觸控的 UI。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cdw_guidance"
>title="實施指導"
>abstract="請聯絡客戶服務以尋求協助。"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 自訂傳統對話框 Widget 應該從 ExtJS 轉換為 [CoralUI](https://developer.adobe.com/experience-manager/reference-materials/6-5/coral-ui/coralui3/getting-started.html)。
* 請聯絡 [Experience Manager 客戶服務團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以釐清或解決問題。
