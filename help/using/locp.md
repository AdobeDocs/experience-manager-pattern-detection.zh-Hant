---
title: LOCP
description: 模式偵測器程式碼說明頁面。
exl-id: a9993b58-7925-47c0-b774-b9ca8a4ee052
source-git-commit: 2881b122773a8a5ad09fb9a14ae35b4a83dae20d
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 65%

---

# LOCP {#locp}

/libs 覆寫自訂套件

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_overview"
>title="/libs 覆寫自訂套件"
>abstract="LOCP會識別偵測到自訂套件傳送內容給 `/libs`，這是反模式（除非有ACL）。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-65/content/implementing/deploying/upgrading/sustainable-upgrades" text="永續升級"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger#platform" text="Sling 資源合併"

`LOCP` 會識別偵測到自訂套件傳送內容給 `/libs`，這是反模式 (但 ACL 情況為例外)。

## 可能的影響和風險 {#implications-and-risks}

* 在任何 CFP、SP 或主要 AEM 升級時，客戶程式碼可能會被刪除或取代。
* 有時新內容可能未正確安裝。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_guidance"
>title="實施指導"
>abstract="客戶應檢閱其自訂程式碼和套件，以識別內容是否傳送至 `/libs`. 如有必要，請將其重構為依賴/apps下的覆蓋內容，並使其與AEMas a Cloud Service相容。 請聯絡 Adobe 支援人員，取得協助或說明。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger#platform" text="覆蓋"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 客戶套件應將內容部署至 `/apps` 而非 `/libs`。
* 如果您需要釐清或解決問題，請聯絡 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)。
