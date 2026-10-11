---
title: SCR
description: 模式偵測器程式碼說明頁面。
exl-id: 13b14cc2-f70b-45ff-a62d-dee647311d84
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
source-git-commit: baa8f6dbf24b735348ed6b27f1e885b5078859ce
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
