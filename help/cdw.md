---
title: CDW
description: 模式偵測器程式碼說明頁面
source-git-commit: 04709ba74eedad903669aae589c605542e1e3b09
workflow-type: ht
source-wordcount: '185'
ht-degree: 100%

---

# CDW {#cdw}

自訂對話框 Widget

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cdw_overview"
>title="自訂對話框 Widget"
>abstract="CDW 可識別應該更新的自訂對話框 Widget，以便使其與 AEM as a Cloud Service 相容。"

`CDW` 自訂對話框 Widget 可識別自訂 CoralUI 和傳統對話框 Widget。應該更新這些 Widget，以便使其與 AEM as a Cloud Service 相容。

子類型用於識別不同類型的資訊，例如：

* `custom.coral.widget`：識別以 CoralUI 2 或 CoralUI 3 為根據的自訂對話框 Widget。
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
* 應該評估自訂 Coral 對話框 Widget 以便更新至 CoralUI 3。
* 請聯繫我們的 [Experience Manager 客戶服務團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以釐清或解決問題。
