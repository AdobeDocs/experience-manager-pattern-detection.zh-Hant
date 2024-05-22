---
title: IOI
description: 模式偵測器程式碼說明頁面。
exl-id: b6c9d11f-5189-4799-98c0-c2699dfe3f40
source-git-commit: 0d693e3ccadc81b59852914f115bb2fa2ea166b0
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 60%

---

# IOI {#ioi}

內部 Oak 匯入

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_overview"
>title="內部 Oak 匯入"
>abstract="IOI程式碼會識別客戶對內部Oak套件的使用，透過OSGi匯入這些套件。 它們會匯出而不使用任何特定版本。 Oak套件組合或低階AEM服務只會取用它們。"

`IOI` 會識別客戶對內部 Oak 套件的使用，透過 OSGi 匯入這些套件。它們會匯出而不使用任何特定版本。 Oak套件組合或低階AEM服務只會取用它們。
其中有些區域是由 `com.adobe.granite.repository`，會在啟動期間設定AEM的存放庫。 另一個範例是 `com.adobe.granite.maintenance.oak` Adobe 套件組合，它會包裝並提供 Oak 維護任務。

## 可能的影響和風險 {#implications-and-risks}

* 在未來的AEM版本中，內部匯出可能會移除，導致相依性中斷和直接相依於Oak的套件組合無作用。
* 內部匯出的 API 可能會變更。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_guidance"
>title="實施指導"
>abstract="客戶應檢閱其自訂程式碼，以識別這類 API 的使用方式，並將其重構為與 AEM as a Cloud Service 相容。請聯絡 Adobe 支援人員，取得協助或說明。"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 使用 Sling Resource API (或 JCR API)，而非低階存取。
* 避免依賴不屬於任何公用 API 或 SPI 的內部套件。
* 請聯絡 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以釐清或解決問題。
