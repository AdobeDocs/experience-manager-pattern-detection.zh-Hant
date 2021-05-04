---
title: LOCP
description: 模式偵測器程式碼說明頁面
exl-id: a9993b58-7925-47c0-b774-b9ca8a4ee052
translation-type: tm+mt
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 0%

---

# LOCP {#locp}

/libs覆寫自訂封裝

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_overview"
>title="/libs覆寫自訂封裝"
>abstract="LOCP可識別將內容傳送到/libs的自訂封包的偵測，這是反模式（ACL除外）。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html" text="可持續升級"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html#platform" text="Sling Resource Merger"

`LOCP` 標識對自定義包的檢測，該包 `/libs`將內容發送到，這是反模式（ACL除外）。

## 可能的影響和風險{#implications-and-risks}

* 任何CFP、SP或主要升級版都可能會刪除或取代客AEM戶程式碼。
* 在某些情況下，新內容可能無法正確安裝。

## 可能的解決方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_guidance"
>title="實施指南"
>abstract="客戶應檢閱其自訂程式碼和套件，以識別內容是否傳送至/libs，並重新調整內容，以依賴覆蓋/apps下的內容，並將它與之相AEM容為Cloud Service。 聯絡Adobe支援以取得說明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html#platform" text="覆蓋"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 客戶套件應將內容部署至`/apps`，而非`/libs`。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
