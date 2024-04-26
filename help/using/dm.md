---
title: DM
description: 了解模式偵測器程式碼如何識別 AEM Assets - Dynamic Media 的使用方式。
exl-id: f077df57-f2bc-4875-a7de-41251a9d7f2f
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 94%

---

# DM {#dm}

Dynamic Media

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dm_overview"
>title="Dynamic Media"
>abstract="DM 程式碼會識別 AEM Assets Dynamic Media 在目前實施中的使用方式。Dynamic Media 模式是由執行模式所偵測。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-65/content/implementing/developing/introduction/dev-guidelines-bestpractices" text="AEM 開發 - 指導方針與最佳實務"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines" text="AEM as a Cloud Service 開發指導方針"

`DM` (Dynamic Media)識別AEM Assets Dynamic Media的使用。 Dynamic Media 模式是由執行模式所偵測。

此程式碼使用子類型：

* `dynamic.media.runmode`：此子類型的關聯值 (如果提供) 是下列其中一值：
   * `dynamicmedia`：Dynamic Media - 混合模式
   * `dynamicmedia_scene7`：Dynamic Media - Scene7 模式

## 可能的影響和風險 {#implications-and-risks}

* `dynamic.media.runmode`
   * Dynamic Media 可能有相關的升級問題。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dm_guidance"
>title="實施指導"
>abstract="AEM as a Cloud Service 只支援 dynamicmedia_scene7 執行模式。請檢閱目前設定，並聯繫 Adobe 支援團隊以尋求協助與澄清。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/assets/dynamicmedia/administering-dynamic-media" text="建立 Dynamic Media"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"


* `dynamic.media.runmode`
   * 如需詳細資訊，請參閱[設定 Dynamic Media](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/assets/dynamicmedia/administering-dynamic-media)。

* 如果您需要釐清或解決問題，請聯絡 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)。
