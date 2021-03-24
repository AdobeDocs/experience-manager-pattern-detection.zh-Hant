---
title: 奧伊
description: 模式偵測器程式碼說明頁面
translation-type: tm+mt
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 0%

---


# OAUI {#oaui}

OAuth使用者例項

## 背景 {#background}

`OAUI` 識別至少有一個與OAuth相關且需要正確移轉的設定使用者的模式。

當`rep:AuthorizableId`節點下方有名為`oauth`的子節點時，以`/home/user-path/user-node/oauth`的形式為用戶配置OAuth。

例如：`/home/users/ims/0001/R80w6XaUCBq3jHE47xDN/oauth`。

## 可能的影響和風險{#implications-and-risks}

* 使用OAuth設定的外部使用者，在依下列程式重新設定之前，將無法登入作者／發佈例項。

## 可能的解決方案{#solutions}

* 請洽詢您的Adobe代表，以討論使用者移轉的選項。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
