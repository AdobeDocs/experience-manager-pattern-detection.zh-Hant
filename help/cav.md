---
title: CAV
description: 模式偵測器程式碼說明頁面
exl-id: b2282da2-a028-4be7-914c-17dcd5d2902a
translation-type: tm+mt
source-git-commit: 1966a3e83ab6b2247d9f1095c8965eac399e3b6e
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 0%

---

# CAV {#cav}

內容區域違規

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cav_overview"
>title="內容區域違規"
>abstract="CAV程式碼會識別使用不同內容區域的方式違反內容分類規則的模式。 此違規將提供覆蓋、受限制內容的概述，一旦我們移至Cloud Service，這些內容可能AEM需要變更。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html#platform" text="Sling Resource Merger"

`CAV` 識別以違反內容分類規則的方式使用不同內容區域的模式。

Sling請求處理會定義資源的內容，尤其是其`sling:resourceType`屬性，用來判斷用來轉譯內容的指令碼。 如需詳細資訊，請參閱[尋找指令碼](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/the-basics.html#locating-the-script)。 Sling也提供透過「Overlays」和「Overrides」存取及合併資源的技巧。 這些描述為[Sling Resource Merger](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html)和[Overlays](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html)的一部分。

為了讓客戶更安全、更輕鬆地瞭解`/libs`的哪些區域安全使用並覆蓋`/libs`中的內容已使用「mixin」屬性分類：公開、抽象、最終和內部。 每個分類都包含內容可能是使用者、繼承或覆蓋的規則。 如需詳細說明，請參閱[可持續升級](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html)。

## 可能的影響和風險{#implications-and-risks}

* 升級可AEM能會導致頁面轉換問題和其他不想要的行為。
* 安全性更新無效。

## 可能的解決方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cav_guidance"
>title="實施指南"
>abstract="應查看以CAS標識的存在不同內容區域違規的模式。 應避免最終和內部內容分類區域。 聯絡Adobe支援以取得說明。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html" text="可持續升級"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 將內容覆蓋的使用降到最低，以處理需要覆蓋的情況。
* 尤其是，請避免覆寫受限制的內容（最終和內部分類）。
* 考慮在升級、ServicePack或CumulativeFixPack安裝後AEM調整`/libs`的變更。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
