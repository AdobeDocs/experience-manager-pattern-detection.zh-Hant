---
title: SIF
description: 模式偵測器程式碼說明頁面。
source-git-commit: 8dd9a42a3bba63d62fa2469b0f78ca15a608b4f9
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 7%

---

# SIF {#sif}

## 背景 {#background}

SIF會識別與AEM 6.5 LTS不相容的社交使用。

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## 可能的解決方案 {#solutions}

尋找以下不同子型別的可能解決方案：

* `social.bundles.detected` — 這些套件組合將在升級期間解除安裝
* `social.packages.detected` — 這些套件將在升級期間刪除
* `social.packages.dependency` — 請從自訂套件中移除社交的套件相依性
* `social.nodes.detected` — 更新自訂程式碼以停止建立社交節點
* `social.configs.detected` — 請勿在自訂程式碼中使用社交設定屬性
* `social.users.detected` — 請勿在自訂程式碼中使用社交使用者
* `social.overlays.detected` — 移除社交覆蓋圖使用方式
* `social.paths.detected` — 在確定AEM中未使用這些路徑後，移除社交路徑
* `social.resource.type.detected` — 移除社交資源型別使用狀況
* `social.usage` — 從自訂程式碼中移除社交API。