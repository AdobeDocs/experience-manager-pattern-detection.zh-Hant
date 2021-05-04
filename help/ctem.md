---
title: CTEM
description: 模式偵測器程式碼說明頁面
exl-id: cd70486c-8e21-4c31-89bf-928b80fa8772
translation-type: tm+mt
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 5%

---

# CTEM {#ctem}

自訂範本

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_overview"
>title="自訂範本"
>abstract="CTEM識別已安裝的自訂元AEM件。 提供此資訊的目的是評估最佳做法"

`CTEM` 標識已安裝在上的自定義模AEM板。提供此資訊的目的是評估最佳實務。

範本由主要類型值&quot;cq:Template&quot;來識別。 子類型與此代碼一起使用，用於標識模板的類別：

* `custom.editable.template`:範本的路徑不以「/apps」開頭。
* `custom.static.template`:範本的路徑以&quot;/apps&quot;開頭。

## 可能的影響和風險{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_guidance"
>title="實施指南"
>abstract="最佳實務是將所有靜態範本移至可編輯的範本。 客戶可運用現有的AEM現代化工具將靜態範本移轉至可編輯的範本。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html" text="可編輯的範本"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/" text="AEM 現代化工具"

* 最佳實務是將所有靜態範本移至可編輯的範本。

## 可能的解決方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_tools"
>title="工具與資源"
>abstract="借助Meduration Suite,AEM客戶可以控制頁面結構（從靜態定義到可編輯範本）。 其目的在於協助客戶從舊式功能的有限功能，轉向強大、現代化的AEM產品。 這些工具具備可設定性、可感知組態和可擴充性。 聯絡Adobe支援以取得說明"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/pages/tools/page-structure.html" text="頁面結構轉換器"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 利用[現代化工AEM具](https://opensource.adobe.com/aem-modernize-tools/)將靜態範本移轉至可編輯範本。
* 有關可編輯模板的詳細資訊，請訪問[Templates](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html)。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
