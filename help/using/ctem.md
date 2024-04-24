---
title: CTEM
description: 模式偵測器程式碼說明頁面。
exl-id: cd70486c-8e21-4c31-89bf-928b80fa8772
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 68%

---

# CTEM {#ctem}

自訂範本

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_overview"
>title="自訂範本"
>abstract="CTEM 會識別 AEM 上已安裝的自訂元件。提供這項資訊是為了最佳實務評估目的。"

`CTEM`  會識別AEM上已安裝的自訂範本。 提供這項資訊是為了最佳實務評估目的。

範本由的主要型別值識別 `cq:Template`. 此程式碼使用子類型來識別範本類別：

* `custom.editable.template`：範本的路徑開頭不是 &quot;/apps&quot;。
* `custom.static.template`：範本的路徑開頭是 &quot;/apps&quot;。

## 可能影響和風險 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_guidance"
>title="實施指導"
>abstract="最佳實務是將所有靜態範本移至可編輯的範本。客戶可以使用現有的AEM現代化工具，將靜態範本移轉至可編輯的範本。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/templates/templates" text="可編輯的範本"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/" text="AEM 現代化工具"

* 最佳實務是將所有靜態範本移至可編輯的範本。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_tools"
>title="工具和資源"
>abstract="借助 AEM 現代化套件，客戶可以操縱頁面結構，從靜態範本移至可編輯的範本。目的是協助客戶從功能有限的舊版功能轉換為強大現代的 AEM 供應項目。這些工具可設定、可感知設定且可擴充。 請聯絡Adobe支援以尋求協助或澄清。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/pages/structure/about.html" text="頁面結構轉換器"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 使用 [AEM現代化工具](https://opensource.adobe.com/aem-modernize-tools/) 將靜態範本移轉至可編輯的範本。
* 如需可編輯範本的詳細資訊，請參閱[範本](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/templates/templates)。
* 聯絡 [AEM支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html) 以澄清或解決問題。
