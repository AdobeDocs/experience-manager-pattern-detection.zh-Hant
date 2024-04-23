---
title: LOCP
description: 模式偵測器程式碼說明頁面……
exl-id: a9993b58-7925-47c0-b774-b9ca8a4ee052
source-git-commit: 616fa84f6237893243cffc8af28c7cbe76bf32d7
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 57%

---

# LOCP {#locp}

/libs 覆寫自訂套件

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_overview"
>title="/libs 覆寫自訂套件"
>abstract="LOCP 會識別偵測到自訂套件傳送內容給 /libs，這是反模式 (但 ACL 情況為例外)。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/upgrading/sustainable-upgrades" text="永續升級"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger#platform" text="Sling 資源合併"

LOCP會識別偵測到自訂套件傳送內容給 `/libs`，這是反模式（但ACL情況為例外）。

## 可能影響和風險 {#implications-and-risks}

* 在任何CFP、SP或主要AEM升級時，客戶程式碼可能會被刪除或取代。
* 有時新內容可能未正確安裝。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_guidance"
>title="實施指導"
>abstract="客戶應檢閱其自訂程式碼和套件，以識別是否有內容傳送到 /libs，並將其重構為依賴 /apps 底下的覆蓋內容，使其與 AEM as a Cloud Service 相容。請聯絡Adobe支援以尋求協助或澄清。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger#platform" text="覆蓋"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 客戶套件應將內容部署至 `/apps` 而非 `/libs`。
* 聯絡 [AEM支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html) 若您需要澄清或解決問題。
