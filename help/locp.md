---
title: LOCP
description: 模式偵測器程式碼說明頁面
translation-type: tm+mt
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 1%

---


# LOCP {#locp}

/libs覆寫自訂封裝

## 背景 {#background}

`LOCP` 標識對自定義包的檢測，該包 `/libs`將內容發送到，這是反模式（ACL除外）。

## 可能的影響和風險{#implications-and-risks}

* 任何CFP、SP或主要升級版都可能會刪除或取代客AEM戶程式碼。
* 在某些情況下，新內容可能無法正確安裝。

## 可能的解決方案{#solutions}

* 客戶套件應將內容部署至`/apps`，而非`/libs`。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
