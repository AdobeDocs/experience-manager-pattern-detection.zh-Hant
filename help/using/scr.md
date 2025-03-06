---
title: SCR
description: 模式偵測器程式碼說明頁面。
source-git-commit: 8dd9a42a3bba63d62fa2469b0f78ca15a608b4f9
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 7%

---

# SCR {#scr}

## 背景 {#background}

SIF會識別與AEM 6.5 LTS不相容的AEM Screens使用方式。

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## 可能的解決方案 {#solutions}

尋找以下不同子型別的可能解決方案：

* `screens.bundles.detected` — 這些套件組合將在升級期間解除安裝。
* `screens.packages.detected` — 這些套件將在升級期間刪除。
* `screens.packages.dependency` — 從您的自訂套件移除對Screens的任何相依性。
* `screens.configs.detected` — 請確定您的自訂程式碼未使用任何Screens設定屬性。
* `screens.users.detected` — 請確定您未在自訂程式碼中使用Screens服務使用者。
* `screens.paths.detected` — 在確定Screens路徑未在AEM中使用後，請移除這些路徑。
* `screens.resource.type.detected` — 移除Screens資源型別使用狀況。
* `screens.usage` — 從您的自訂程式碼中移除Screens API。