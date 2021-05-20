---
title: CCOM
description: 模式偵測器程式碼說明頁面
exl-id: 59071538-56ec-44e7-8196-56e6525bb4b9
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
>abstract="CCOM可識別AEM上已安裝的自訂元件。 提供這些資訊是為了評估最佳做法"

`CCOM` 識別AEM上已安裝的自訂元件。這些資訊是為最佳做法評估而提供的。

子類型與此代碼一起使用，以標識元件的類別：

* `custom.core`:元件的超類型鏈中的超類型包含「core/wcm/components/」，表示它繼承自核心元件。
* `custom.foundation`:元件的超類型鏈中的超類型包含「core/wcm/components/」，表示它繼承自核心元件。
* `custom.overlay.foundation`:元件路徑包含「wcm/foundation/components/」或「foundation/components/」，表示它覆蓋了基礎元件。
* `custom`:自訂元件不會繼承或覆蓋核心或基礎元件。

## 可能的影響和風險{#implications-and-risks}

* 最佳實務是將自訂元件的數量減到最少、運用核心元件，以及搭配樣式系統使用核心元件以減少技術負擔。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ccom_guidance"
>title="實施指南"
>abstract="最佳實務是將自訂元件的數量減到最少、運用核心元件，以及搭配樣式系統使用核心元件以減少技術負擔。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html" text="核心元件"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/style-system-feature-video-use.html?lang=en#page-authoring" text="樣式系統"

* 如需核心元件的詳細資訊，請參閱[核心元件簡介](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html?lang=zh-Hant)。
* 在[使用樣式系統](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/style-system-feature-video-use.html?lang=en#page-authoring)中查找有關樣式系統的詳細資訊。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決問題。
