---
title: AC
description: 模式偵測器程式碼說明頁面。
source-git-commit: 8dd9a42a3bba63d62fa2469b0f78ca15a608b4f9
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 7%

---

# AC {#ac}

## 背景 {#background}

AC會識別與AEM 6.5 LTS不相容的Assets套件組合使用方式

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## 可能的解決方案 {#solutions}

尋找以下不同子型別的可能解決方案：

* `asset.bundles.detected` — 此套件組合將在升級期間解除安裝。
* `asset.usage` — 從自訂程式碼中移除任何資產評等和資產目錄元件相依性。 若適用，請變更程式碼以使用新的API `List<Scene7ConfigSetting>` `com.day.cq.dam.scene7.api.model.Scene7ViewerConfig#getSettingsList()`。
* `asset.overlays.detected` — 需要移除在Assets評等和目錄元件上建立的覆蓋圖。
* `asset.resource.type.detected` — 移除自訂程式碼中Assets評等元件resourcetype的任何使用方式。
* `asset.paths.detected` — 移動這些路徑底下的任何客戶內容，並在確定這些路徑未用於AEM後予以移除。