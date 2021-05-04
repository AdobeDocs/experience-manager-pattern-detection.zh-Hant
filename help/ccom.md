---
title: CCOM
description: 模式偵測器程式碼說明頁面
exl-id: 59071538-56ec-44e7-8196-56e6525bb4b9
translation-type: tm+mt
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 6%

---

# CCOM {#ccom}

自訂元件

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ccom_overview"
>title="自訂元件"
>abstract="CCOM識別已安裝的自訂元件AEM。 提供此資訊的目的是評估最佳做法"

`CCOM` 標識已安裝在上的自定義組AEM件。提供此資訊的目的是評估最佳實務。

子類型與此代碼一起使用，用於標識元件的類別：

* `custom.core`:元件的超類型鏈中的超類型包含&quot;core/wcm/components/&quot;，表示它繼承自核心元件。
* `custom.foundation`:元件的超類型鏈中的超類型包含&quot;core/wcm/components/&quot;，表示它繼承自核心元件。
* `custom.overlay.foundation`:元件路徑包含&quot;wcm/foundation/components/&quot;或&quot;foundation/components/&quot;，表示它覆蓋了基礎元件。
* `custom`:自訂元件不會繼承或覆蓋核心或基礎元件。

## 可能的影響和風險{#implications-and-risks}

* 最佳實務是將自訂元件的數量減到最少、運用核心元件，並搭配Style System使用核心元件以降低技術負擔。

## 可能的解決方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ccom_guidance"
>title="實施指南"
>abstract="最佳實務是將自訂元件的數量減到最少、運用核心元件，並搭配Style System使用核心元件以降低技術負擔。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html" text="核心元件"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/style-system-feature-video-use.html?lang=en#page-authoring" text="樣式系統"

* 有關核心元件的詳細資訊，請參閱[核心元件簡介](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html?lang=zh-Hant)。
* 有關樣式系統的更多資訊，請訪問[使用樣式系統](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/style-system-feature-video-use.html?lang=en#page-authoring)。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
