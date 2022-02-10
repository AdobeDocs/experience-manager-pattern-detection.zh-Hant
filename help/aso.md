---
title: 麻生
description: 模式檢測器代碼幫助頁
exl-id: 2ba416b7-80c1-4ec5-a6bf-d80f6d625b07
source-git-commit: ff4f798d540d52d7875e514a2edb959e64e068fb
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 4%

---

# 麻生 {#aso}

系統AEM概述

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_overview"
>title="系統AEM概述"
>abstract="ASO代碼標識有關實例的一般AEM資訊。 每個查找結果都提供特定類型系統資訊的一個值，這些值有助於您的遷移規劃和重構工作。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="AEMas a Cloud Service — 發行說明"

`ASO` 標識有關實例的一般AEM資訊。 每個查找結果都提供特定類型的系統資訊的一個值。

子類型用於標識不同類型的資訊：

* `aem.version`:版本AEM。
* `aem.product`:檢測產品(商AEM業、Forms等)的使用。
* `node.count`:某類型（頁、資產等）的近似節點計數 以及節點總數。
* `node.store`:節點儲存實現類型(SegmentNodeStore、DocumentNodeStore)及其大小。
* `data.store`:資料儲存實現類型(FileDataStore、S3DataStore、AzureDataStore)。
* `maintenance.task`:維護任務。
* `slow.query`:查詢速度慢。
* `group.membership`:組中的用戶和子組（僅限直接/聲明的成員）數。
* `cqtag.count`:CQ標籤的資產數。
* `smarttag.count`:Smart標籤的資產數。
* `ccom.version`:核心元件包的版本。
* `instance.type`:實例AEM類型（作者|發佈）。
* `unprocessed.asset.count`:未處理的資產數。

## 可能的影響和風險 {#implications-and-risks}

* 提AEM供了版本、節點計數、組成員、節點儲存、資料儲存實現類型、CQ標籤計數、智慧標籤計數、核心元件版本AEM和實例類型供參考。
* 定制應用程式可能依賴於在as a Cloud Service中不可用的產AEM品或功能。
* 使用不受支援的功能進行升級可能會導致升級失敗和應用程式無法正常工作。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_guidance"
>title="實施指南"
>abstract="通過ASO代碼公開的資訊提供了您的環境的一般資訊AEM，包括版本、產品附加模組、系統級資訊，應對as a Cloud Service中任何不受支援的產品或功能進行AEM檢查。 聯繫Adobe支援以獲得幫助和澄清。"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 不AEM建議使用不受支援的產品或功能進行升級，可能不受支援。
* 查看 [發行說明](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hant) 瞭解最新的AEMas a Cloud Service。
* 請聯繫我們 [支AEM持團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) 澄清或解決問題。
