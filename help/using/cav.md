---
title: CAV
description: 模式偵測器程式碼說明頁面。
exl-id: b2282da2-a028-4be7-914c-17dcd5d2902a
source-git-commit: 616fa84f6237893243cffc8af28c7cbe76bf32d7
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 45%

---

# CAV {#cav}

內容區域違規

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cav_overview"
>title="內容區域違規"
>abstract="CAV 程式碼會識別以違反內容分類規則的方式使用不同內容區域的模式。此違規資訊會提供覆蓋的總覽，限制在內容移至AEMas a Cloud Service後可能需要變更的內容。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger#platform" text="Sling 資源合併"

CAV會識別以違反內容分類規則的方式使用不同內容區域的模式。

Sling請求處理會定義資源的內容、其 `sling:resourceType` 屬性是用來決定轉譯內容所用的指令碼。 如需詳細資訊，請參閱[找到指令碼](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/introduction/the-basics#locating-the-script)。Sling 也透過「覆蓋」和「覆寫」提供存取和合併資源的技術。在 [Sling 資源合併](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger)和[覆蓋](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/overlays)中予以說明。

讓客戶更安全、更輕鬆地瞭解 `/libs` 可安全使用並覆蓋中的內容 `/libs` 已使用「mixin」屬性進行分類：Public、Abstract、Final和Internal。 每個分類表示如何使用、繼承或覆蓋內容的相關規則。請參閱[永續升級](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/upgrading/sustainable-upgrades)以取得詳細說明。

## 可能影響和風險 {#implications-and-risks}

* AEM 升級可能會導致頁面轉譯問題和其他不良行為。
* 安全性更新無效。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cav_guidance"
>title="實施指導"
>abstract="由CAS識別的模式，其中存在不同的內容區域違規，應進行審查。 應避免最終和內部內容分類區域。 請聯絡Adobe支援以尋求協助或澄清。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/upgrading/sustainable-upgrades" text="永續升級"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 將內容覆蓋的使用降至最小，只用於必要的案例。
* 尤其應避免覆蓋受限內容 (最終和內部分類)。
* 考慮調整來自的變更 `/libs` 在AEM升級、Service Pack或Cumulative Fix Pack安裝之後。
* 聯絡 [AEM支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html) 以澄清或解決問題。
