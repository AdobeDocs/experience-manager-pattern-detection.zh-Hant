---
title: WRF
description: 模式偵測器程式碼說明頁面。
source-git-commit: 8dd9a42a3bba63d62fa2469b0f78ca15a608b4f9
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 8%

---

# WRF {#wrf}

## 背景 {#background}

WRF會識別不相容於AEM 6.5 LTS的We-Retail使用方式。

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## 可能的解決方案 {#solutions}

尋找以下不同子型別的可能解決方案：

* `weretail.bundles.detected` — 這些套件組合將在升級期間解除安裝
* `weretail.packages.detected` — 這些套件將在升級期間刪除
* `weretail.configs.detected` — 請勿在您的自訂程式碼中使用We.Retail設定屬性
* `weretail.packages.dependency` — 移除We.Retail上任何自訂套件的相依性
* `weretail.paths.detected` — 在確認您未使用Social後，可以刪除這些We.Retail路徑
* `weretail.resource.type.detected` — 移除We.Retail資源型別使用狀況
* `weretail.usage` — 從您的自訂程式碼中移除We.Retail API。