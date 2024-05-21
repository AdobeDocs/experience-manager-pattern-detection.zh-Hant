---
title: INS
description: 模式偵測器程式碼說明頁面。
exl-id: d89e1589-3195-4b2d-98f4-136bedaecb0b
source-git-commit: 2881b122773a8a5ad09fb9a14ae35b4a83dae20d
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 87%

---

# INS {#ins}

無效命名空間

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ins_overview"
>title="無效命名空間"
>abstract="INS 會識別 AEM 執行個體的命名空間問題"

`INS` (無效命名空間) 會識別 AEM 執行個體的命名空間問題。

子類型用於識別不同類型的資訊，例如：

* `uri`：識別 AEM 中無效的命名空間 URI。

## 可能的影響和風險 {#implications-and-risks}

* 無法複製內容 (跨層) 或複製內容 (跨 `env`，透過 `/crx/packMgr` 或內容複製)。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ins_guidance"
>title="實施指導"
>abstract="請聯絡客戶服務以尋求協助。"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 根據以下說明修正名稱空間定義： [JCR規格](https://developer.adobe.com/experience-manager/reference-materials/spec/jcr/1.0/4.5_Namespaces.html). 請依照上述步驟操作 [此處](https://experienceleaguecommunities.adobe.com/t5/adobe-experience-manager/how-can-i-delete-a-namespace-created-in-crx/td-p/225163)
* 請聯絡 [Experience Manager 客戶服務團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以釐清或解決問題。
