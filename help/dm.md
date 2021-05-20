---
title: DM
description: 模式偵測器程式碼說明頁面
exl-id: f077df57-f2bc-4875-a7de-41251a9d7f2f
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 7%

---

# DM {#dm}

Dynamic Media

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dm_overview"
>title="Dynamic Media"
>abstract="DM程式碼可識別您目前實作中AEM Assets Dynamic Media的使用情形。 Dynamic Media模式由執行模式偵測。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html" text="AEM開發 — 准則和最佳作法"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html" text="AEM as a Cloud Service 開發方針"

`DM` 識別AEM Assets Dynamic Media的使用情形。Dynamic Media模式由執行模式偵測。

子類型與此代碼一起使用：

* `dynamic.media.runmode`:如果提供了此子類型的關聯值，則其為：
   * `dynamicmedia`:Dynamic Media — 混合模式
   * `dynamicmedia_scene7`:Dynamic Media - Scene 7模式

## 可能的影響和風險{#implications-and-risks}

* `dynamic.media.runmode`
   * 可能會有與Dynamic Media相關的升級問題。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dm_guidance"
>title="實施指南"
>abstract="AEM as aCloud Service僅支援dynamicmedia_scene7 runmode。 請檢閱目前設定，並聯絡Adobe支援團隊以取得說明和說明。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/administering-dynamic-media.html" text="建立 Dynamic Media"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"


* `dynamic.media.runmode`
   * 如需詳細資訊，請參閱[設定Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/administering-dynamic-media.html)。

* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決問題。
