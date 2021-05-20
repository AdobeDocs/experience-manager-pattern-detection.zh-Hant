---
title: LOCP
description: 模式偵測器程式碼說明頁面
exl-id: a9993b58-7925-47c0-b774-b9ca8a4ee052
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 0%

---

# LOCP {#locp}

/libs覆寫自訂套件

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_overview"
>title="/libs覆寫自訂套件"
>abstract="LOCP可識別將內容傳送至/libs的自訂套件的偵測，這是反模式（ACL除外）。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html" text="可持續升級"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html#platform" text="Sling Resource Merger"

`LOCP` 識別將內容傳送至的自訂套件 `/libs`的偵測，這是反模式（ACL除外）。

## 可能的影響和風險{#implications-and-risks}

* 任何CFP、SP或主要AEM升級都可能會刪除或取代客戶程式碼。
* 在某些情況下，新內容可能未正確安裝。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_guidance"
>title="實施指南"
>abstract="客戶應檢閱其自訂程式碼和套件，以識別內容是否傳送至/lib，並重新調整以仰賴/apps底下的覆蓋內容，使其與AEM as aCloud Service相容。 請洽詢Adobe支援以取得說明和說明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html#platform" text="覆蓋"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 客戶包應將內容部署到`/apps`，而不是`/libs`。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決問題。
