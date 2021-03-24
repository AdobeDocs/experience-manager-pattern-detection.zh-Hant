---
title: CTEM
description: 模式偵測器程式碼說明頁面
translation-type: tm+mt
source-git-commit: a2c7137dd5cb2479bc0c6134d3afa58111049a68
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 4%

---


# CTEM {#ctem}

自訂範本

## 背景 {#background}

`CTEM` 標識已安裝在上的自定義模AEM板。提供此資訊的目的是評估最佳實務。

範本由主要類型值&quot;cq:Template&quot;來識別。 子類型與此代碼一起使用，用於標識模板的類別：

* `custom.editable.template`:範本的路徑不以「/apps」開頭。
* `custom.static.template`:範本的路徑以&quot;/apps&quot;開頭。

## 可能的影響和風險{#implications-and-risks}

* 最佳實務是將所有靜態範本移至可編輯的範本。

## 可能的解決方案{#solutions}

* 利用[現代化工AEM具](https://opensource.adobe.com/aem-modernize-tools/)將靜態範本移轉至可編輯範本。
* 有關可編輯模板的詳細資訊，請訪問[Templates](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html)。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
