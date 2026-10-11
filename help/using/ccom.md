---
title: CCOM
description: 模式偵測器程式碼說明頁面。
exl-id: 59071538-56ec-44e7-8196-56e6525bb4b9
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
source-git-commit: baa8f6dbf24b735348ed6b27f1e885b5078859ce
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 100%
---
# CCOM {#ccom}

自訂元件

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ccom_overview"
>title="自訂元件"
>abstract="CCOM 會識別安裝在 AEM 上的自訂元件。 提供這項資訊是為了進行最佳做法評估。"

`CCOM` 會識別安裝在 AEM 上的自訂元件。 提供這項資訊是為了進行最佳做法評估。

子類型會與此代碼搭配使用，以識別元件的類別：

* `custom.core`：元件的超級類型鏈結中的某個超級類型包含 `core/wcm/components/`，這表示元件繼承自核心元件。
* `custom.foundation`：元件的超級類型鏈結中的某個超級類型包含 &quot;`core/wcm/components/`，這表示元件繼承自核心元件。
* `custom.overlay.foundation`：元件路徑包含 `wcm/foundation/components/` 或 `foundation/components/`，表示路徑會覆蓋基礎元件。
* `custom`：自訂元件不會繼承或覆蓋核心或基礎元件。

## 可能的影響和風險 {#implications-and-risks}

* 最佳實務是將自訂元件數目降至最小、使用核心元件，並透過樣式系統使用核心元件以減少技術負債。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ccom_guidance"
>title="實施指導"
>abstract="最佳做法是將自訂元件數目降至最小、使用核心元件，並透過樣式系統使用核心元件以減少技術負債。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-core-components/using/introduction" text="核心元件"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-learn/sites/page-authoring/style-system-feature-video-use#page-authoring" text="樣式系統"

* 如需核心元件的詳細資訊，請參閱[核心元件簡介](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-core-components/using/introduction)。
* 如需樣式系統的詳細資訊，請參閱[使用樣式系統](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-learn/sites/page-authoring/style-system-feature-video-use#page-authoring)。
* 請聯絡 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以釐清或解決問題。
