---
title: CDW
description: 模式偵測器程式碼說明頁面
source-git-commit: 04709ba74eedad903669aae589c605542e1e3b09
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# CDW {#cdw}

自定義對話框小部件

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cdw_overview"
>title="自定義對話框小部件"
>abstract="CDW標識應更新的自定義對話框小部件以與AEMas a Cloud Service相容。"

`CDW`  「自定義對話框小部件」標識自定義CoralUI和「經典」對話框小部件。 應更新這些內容，使其與AEMas a Cloud Service相容。

子類型用於識別不同類型的資訊，例如：

* `custom.coral.widget`:根據CoralUI 2或CoralUI 3標識自定義對話框小部件。
* `custom.classic.widget`:基於ExtJ標識自定義對話框小部件。

## 可能影響和風險 {#implications-and-risks}

* Classic UI 無法再用於 AEM as a Cloud Service。標準製作介面是已啟用觸控的 UI。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cdw_guidance"
>title="實施指導"
>abstract="請聯絡客戶服務以尋求協助。"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 應將「自定義經典對話框小部件」從ExtJS轉換為 [珊瑚UI](https://developer.adobe.com/experience-manager/reference-materials/6-5/coral-ui/coralui3/getting-started.html)。
* 應評估自定義Coral對話框小部件以更新到CoralUI 3。
* 請聯繫我們的 [Experience Manager 客戶服務團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以澄清或解決問題。
