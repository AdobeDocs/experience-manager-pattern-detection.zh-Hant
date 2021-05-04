---
title: PCX
description: 模式偵測器程式碼說明頁面
exl-id: 7e3c1142-c349-4bce-b8de-8e91528f80a0
translation-type: tm+mt
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 3%

---

# PCX {#pcx}

頁面複雜性

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_pcx_overview"
>title="頁面複雜性"
>abstract="PCX標識在其結構中包含大量節點的頁。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="顯著變AEM更——作為Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hant" text="作AEM為Cloud Service-發行說明"

`PCX` 標識結構中包含大量節點的頁。

子類型用於標識不同類型的資訊：

* `page.complexity.medium`:頁面包含的節點數量適中，可能會影響演算效能。
* `page.complexity.high`:頁面包含的節點數很多，可能會影響演算效能。

## 可能的影響和風險{#implications-and-risks}

* 頁面中的大量節點可能會影響其演算效能。

## 可能的解決方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_pcx_guidance"
>title="實施指南"
>abstract="最佳實務是檢閱內容結構以降低頁面複雜度，進而有助於改善頁面演算效能。 聯絡Adobe支援以取得說明"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 採取步驟減少頁面內的節點總數，包括：
   * 確認沒有不必要的容器。
   * 測試使用較少的容器，是否能達到相同的版面配置。
   * 簡化頁面內容。
   * 降低節點結構的深度。
   * 重新整合任何包含的體驗片段，以簡化工作。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
