---
title: CAV
description: 模式偵測器程式碼說明頁面
translation-type: tm+mt
source-git-commit: 2391ad7851d4e6634a7bacd684b08db44a9c78e8
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 0%

---


# CAV {#cav}

內容區域違規

## 背景 {#background}

`CAV` 識別以違反內容分類規則的方式使用不同內容區域的模式。

Sling請求處理會定義資源的內容，尤其是其`sling:resourceType`屬性，用來判斷用來轉譯內容的指令碼。 （有關詳細資訊，請參閱[查找指令碼](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/the-basics.html#locating-the-script)。） Sling也提供透過「Overlays」和「Overrides」存取及合併資源的技巧。 這些描述為[Sling Resource Merger](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html)和[Overlays](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html)的一部分。

為了讓客戶更安全、更輕鬆地瞭解`/libs`的哪些區域安全使用並覆蓋`/libs`中的內容已使用「mixin」屬性分類：公開、抽象、最終和內部。 每個分類都包含內容可能是使用者、繼承或覆蓋的規則。 如需詳細說明，請參閱[可持續升級](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html)。

## 可能的影響和風險{#implications-and-risks}

* 升級可AEM能會導致頁面轉換問題和其他不想要的行為。
* 安全性更新無效。

## 可能的解決方案{#solutions}

* 將內容覆蓋的使用降到最低，以處理需要覆蓋的情況。
* 尤其是，請避免覆寫受限制的內容（最終和內部分類）。
* 考慮在升級、ServicePack或CumulativeFixPack安裝後AEM調整`/libs`的變更。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
