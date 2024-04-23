---
title: IOI
description: 模式偵測器程式碼說明頁面。
exl-id: b6c9d11f-5189-4799-98c0-c2699dfe3f40
source-git-commit: 616fa84f6237893243cffc8af28c7cbe76bf32d7
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 89%

---

# IOI {#ioi}

內部 Oak 匯入

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_overview"
>title="內部 Oak 匯入"
>abstract="IOI 程式碼會識別客戶對內部 Oak 套件的使用，透過 OSGi 匯入這些套件。它們通常在沒有特定版本的情況下匯出，僅供其他 Oak 套件組合或低階 AEM 服務使用。"

`IOI` 會識別客戶對內部 Oak 套件的使用，透過 OSGi 匯入這些套件。它們通常在沒有特定版本的情況下匯出，僅供其他 Oak 套件組合或低階 AEM 服務使用。

`com.adobe.granite.repository` 會使用其中部分的套件，在啟動期間設定 AEM 的存放庫。另一個範例是 `com.adobe.granite.maintenance.oak` Adobe 套件組合，它會包裝並提供 Oak 維護任務。

## 可能影響和風險 {#implications-and-risks}

* 在未來的 AEM 版本中，內部匯出可能會移除，導致相依性中斷和直接相依於 Oak 的套件組合無作用。
* 內部匯出的 API 可能會變更。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_guidance"
>title="實施指導"
>abstract="客戶應檢閱其自訂程式碼，以識別這類 API 的使用方式，並將其重構為與 AEM as a Cloud Service 相容。請聯絡Adobe支援以尋求協助或澄清。"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 使用 Sling Resource API (或 JCR API)，而非低階存取。
* 避免依賴不屬於任何公用 API 或 SPI 的內部套件。
* 聯絡 [AEM支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html) 以澄清或解決問題。
