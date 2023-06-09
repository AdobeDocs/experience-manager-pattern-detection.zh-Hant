---
title: PCX
description: 模式偵測器程式碼說明頁面
exl-id: 7e3c1142-c349-4bce-b8de-8e91528f80a0
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 100%

---

# PCX {#pcx}

頁面複雜度

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_pcx_overview"
>title="頁面複雜度"
>abstract="PCX 會識別結構中有大量節點的頁面。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="重大變更 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="AEM as a Cloud Service - 發行說明"

`PCX` 會識別結構中有大量節點的頁面。

子類型用於識別不同類型的資訊：

* `page.complexity.medium`：頁面包含中等偏高的節點數目，可能會影響轉譯效能。
* `page.complexity.high`：頁面包含非常高的節點數目，極有可能會影響轉譯效能。

## 可能影響和風險 {#implications-and-risks}

* 頁面內的大量節點可能會影響其轉譯效能。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_pcx_guidance"
>title="實施指導"
>abstract="最佳實務是檢閱內容結構以降低頁面複雜度，這有助於改進頁面轉譯效能。請聯繫 Adobe 支援以尋求協助與澄清。"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 採取步驟減少頁面內的節點總數，包括：
   * 確認沒有不必要的容器。
   * 測試是否能以較少的容器實現相同的版面。
   * 簡化頁面內容。
   * 減少節點結構的深度。
   * 為了簡單起見，重構任何包含的體驗片段。
* 請聯繫我們的 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以澄清或解決問題。
