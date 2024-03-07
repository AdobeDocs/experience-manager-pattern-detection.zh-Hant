---
title: INS
description: 模式偵測器程式碼說明頁面
source-git-commit: e469b546a75a77e538a54de3ffc1ca385c8cf21d
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 47%

---

# INS {#ins}

無效的名稱空間

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ins_overview"
>title="無效的名稱空間"
>abstract="INS會識別AEM執行個體上的名稱空間問題"

`INS`  無效的名稱空間會識別AEM執行個體上的名稱空間問題。

子類型用於識別不同類型的資訊，例如：

* `uri`：識別AEM中的無效名稱空間URI。

## 可能影響和風險 {#implications-and-risks}

* 無法複製內容（跨階層）或複製內容(跨環境 — 透過 `/crx/packMgr` 或內容副本)。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ins_guidance"
>title="實施指導"
>abstract="請聯絡客戶服務以尋求協助。"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 根據以下條件修正名稱空間定義 [JCR規格](https://developer.adobe.com/experience-manager/reference-materials/spec/jcr/1.0/4.5_Namespaces.html). 遵循提及的步驟 [此處](https://experienceleaguecommunities.adobe.com/t5/adobe-experience-manager/how-can-i-delete-a-namespace-created-in-crx/td-p/225163)
* 請聯繫我們的 [Experience Manager 客戶服務團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以釐清或解決問題。