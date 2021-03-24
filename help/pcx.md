---
title: PCX
description: 模式偵測器程式碼說明頁面
translation-type: tm+mt
source-git-commit: 2391ad7851d4e6634a7bacd684b08db44a9c78e8
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---


# PCX {#pcx}

頁面複雜性

## 背景 {#background}

`PCX` 標識結構中包含大量節點的頁。

子類型用於標識不同類型的資訊：

* `page.complexity.medium`:頁面包含的節點數量適中，可能會影響演算效能。
* `page.complexity.high`:頁面包含的節點數很多，可能會影響演算效能。

## 可能的影響和風險{#implications-and-risks}

* 頁面中的大量節點可能會影響其演算效能。

## 可能的解決方案{#solutions}

* 採取步驟減少頁面內的節點總數，包括：
   * 確認沒有不必要的容器。
   * 測試使用較少的容器，是否能達到相同的版面配置。
   * 簡化頁面內容。
   * 降低節點結構的深度。
   * 重新整合任何包含的體驗片段，以簡化工作。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
