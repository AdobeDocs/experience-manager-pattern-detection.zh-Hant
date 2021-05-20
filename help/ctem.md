---
title: CTEM
description: 模式偵測器程式碼說明頁面
exl-id: cd70486c-8e21-4c31-89bf-928b80fa8772
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
>abstract="CTEM可識別AEM上已安裝的自訂元件。 提供這些資訊是為了評估最佳做法"

`CTEM` 識別AEM上已安裝的自訂範本。這些資訊是為最佳做法評估而提供的。

範本是以「cq:Template」的主要類型值來識別。 子類型與此代碼一起使用，以標識模板的類別：

* `custom.editable.template`:範本的路徑不以「/apps」開頭。
* `custom.static.template`:範本的路徑以「/apps」開頭。

## 可能的影響和風險{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_guidance"
>title="實施指南"
>abstract="最佳實務是將所有靜態範本移至可編輯的範本。 客戶可以利用現有的AEM現代化工具，將靜態範本移轉至可編輯的範本。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html" text="可編輯的範本"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/" text="AEM 現代化工具"

* 最佳實務是將所有靜態範本移至可編輯的範本。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_tools"
>title="工具和資源"
>abstract="在AEM現代化套裝的協助下，客戶可以控制頁面結構（從靜態定義到可編輯的範本）。 其目的是協助客戶從舊版功能的有限功能，轉變為強大、現代的AEM產品。 這些工具可設定、可感知配置且可擴充。 請洽詢Adobe支援以取得說明和說明"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/pages/tools/page-structure.html" text="頁面結構轉換器"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 運用[AEM現代化工具](https://opensource.adobe.com/aem-modernize-tools/)將靜態範本移轉至可編輯的範本。
* 如需可編輯範本的詳細資訊，請前往[範本](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html)。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決問題。
