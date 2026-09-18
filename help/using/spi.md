---
title: SPI
description: 模式偵測器程式碼說明頁面。
exl-id: 39f2d04e-c6e4-4da6-b000-0115bc2b87bf
source-git-commit: 29d702c9662fd185ef806123fc4f4a03a70d64aa
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 8%
---
# SPI {#spi}

## 背景 {#background}

SIF會識別與AEM 6.5 LTS不相容的Search和Promote使用方式。

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## 可能的解決方案 {#solutions}

尋找以下不同子型別的可能解決方案：

* `searchpromote.bundles.detected` — 這些套件組合將在升級期間解除安裝
* `earchpromote.packages.detected` — 這些套件將在升級期間刪除
* `searchpromote.packages.dependency` — 移除自訂套件可能有的任何Search and Promote相依性
* `searchpromote.usage` — 從您的自訂程式碼中移除Search和Promote API
* `searchpromote.users.detected` — 請勿在自訂程式碼中使用Search and Promote服務使用者
* `searchpromote.configs.detected` — 請勿在您的自訂程式碼中使用Search和Promote設定屬性。
