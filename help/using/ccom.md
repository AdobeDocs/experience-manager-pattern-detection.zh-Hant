---
title: CCOM
description: 模式偵測器程式碼說明頁面。
exl-id: 59071538-56ec-44e7-8196-56e6525bb4b9
source-git-commit: 58fdb55e1f0c067dacf6825c4076465bc8c5d821
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 100%

---

# CCOM {#ccom}

自訂元件

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ccom_overview"
>title="自訂元件"
>abstract="CCOM 會識別安裝在 AEM 上的自訂元件。提供這項資訊是為了最佳實務評估目的。"

`CCOM` 會識別安裝在 AEM 上的自訂元件。提供這項資訊是為了最佳實務評估目的。

此程式碼使用子類型來識別元件類別：

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
>abstract="最佳實務是將自訂元件數目降至最小、使用核心元件，並透過樣式系統使用核心元件以減少技術負債。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-core-components/using/introduction" text="核心元件"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-learn/sites/page-authoring/style-system-feature-video-use#page-authoring" text="樣式系統"

* 如需核心元件的詳細資訊，請參閱[核心元件簡介](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-core-components/using/introduction)。
* 如需樣式系統的詳細資訊，請參閱[使用樣式系統](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-learn/sites/page-authoring/style-system-feature-video-use#page-authoring)。
* 請聯絡 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以釐清或解決問題。
