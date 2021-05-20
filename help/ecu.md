---
title: ECU
description: 模式偵測器程式碼說明頁面
exl-id: fd061001-b00e-44ae-bd31-71bd2fa733cd
source-git-commit: cbd43bca20831c19eb30703cc1ec528c75f2a2ef
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 0%

---

# ECU {#ecu}

已棄用：無關的內容使用情形（以CAV取代，內容區域違規）

## 背景 {#background}

`ECU` 識別以違反內容分類規則的方式使用不同內容區域的模式。

Sling要求處理會定義資源內容（尤其是`sling:resourceType`屬性）如何用來判斷用於轉譯內容的指令碼。 （如需詳細資訊，請參閱[找到指令碼](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/the-basics.html#locating-the-script) 。） Sling也提供透過「覆蓋」和「覆寫」存取及合併資源的技術。 這些說明屬於[Sling Resource Merger](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html)和[Overlays](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html)的一部分。

為了讓客戶更安全、更輕鬆地了解`/libs`中哪些區域是安全的使用，並覆蓋`/libs`中的內容已使用「mixin」屬性分類：公開、抽象、最終和內部。 每個分類都代表內容如何為使用者、繼承或覆蓋的規則。 有關詳細說明，請參閱[可持續升級](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html)。

## 可能的影響和風險{#implications-and-risks}

* AEM升級可能會導致頁面呈現問題和其他不適當的行為。
* 安全更新無效。

## 可能的解決方案 {#solutions}

* 針對需要內容覆蓋的情況，將內容覆蓋的使用量減到最少。
* 尤其是，請避免覆寫受限內容（最終和內部分類）。
* 請考慮在AEM升級、ServicePack或CumulativeFixPack安裝後，調整`/libs`中的變更。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決問題。
