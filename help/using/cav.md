---
title: CAV
description: 模式偵測器程式碼說明頁面
exl-id: b2282da2-a028-4be7-914c-17dcd5d2902a
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: ht
source-wordcount: '366'
ht-degree: 100%

---

# CAV {#cav}

內容區域違規

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cav_overview"
>title="內容區域違規"
>abstract="CAV 程式碼會識別以違反內容分類規則的方式使用不同內容區域的模式。此違規資訊提供覆蓋的總覽，在我們移至 AEM as a Cloud Service 之後，這些受限內容可能需要變更。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html#platform" text="Sling 資源合併"

`CAV` 會識別以違反內容分類規則的方式使用不同內容區域的模式。

Sling 請求處理會定義如何將資源的內容 (尤其是其 `sling:resourceType` 屬性) 用於決定轉譯內容時所用的指令碼。如需詳細資訊，請參閱[找到指令碼](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/the-basics.html#locating-the-script)。Sling 也透過「覆蓋」和「覆寫」提供存取和合併資源的技術。在 [Sling 資源合併](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html)和[覆蓋](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html)中予以說明。

為了讓客戶更安全輕鬆地了解 `/libs` 的哪些區域可安全使用和覆蓋，`/libs` 中的內容已經透過 &quot;mixin&quot; 屬性進行分類：公用、抽象、最終和內部。每個分類表示如何使用、繼承或覆蓋內容的相關規則。請參閱[永續升級](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html)以取得詳細說明。

## 可能影響和風險 {#implications-and-risks}

* AEM 升級可能會導致頁面轉譯問題和其他不良行為。
* 安全性更新無效。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cav_guidance"
>title="實施指導"
>abstract="應檢閱 CAS 所識別存在不同內容區域違規的模式。應避免最終和內部內容分類區域。請聯繫 Adobe 支援以尋求協助與澄清。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html" text="永續升級"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 將內容覆蓋的使用降至最小，只用於必要的案例。
* 尤其應避免覆蓋受限內容 (最終和內部分類)。
* 請考慮在 AEM 升級、ServicePack 或 CumulativeFixPack 安裝之後調整來自 `/libs` 的變更。
* 請聯繫我們的 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以澄清或解決問題。
