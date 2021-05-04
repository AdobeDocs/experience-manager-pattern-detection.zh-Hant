---
title: 呂
description: 模式偵測器程式碼說明頁面
exl-id: 742220d6-b37a-48ec-9f89-2f3f0ce6ff96
translation-type: tm+mt
source-git-commit: 76dc944f1592118920f89c513faf456b8aa443a9
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 5%

---

# LUI {#lui}

舊版使用者介面

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_overview"
>title="舊版使用者介面"
>abstract="LUI將不建議使用或不支援的過時使用者介面元素用AEM作AEMCloud Service。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="顯著變AEM更——作為Cloud Service"

`LUI` 識別在舊版和舊版中不建議或不支援的已過時使用者介面元AEM素的AEM使用方式。

子類型用於標識應該或必須升級的不同類型的用戶介面元素：

* `legacy.dialog.classic`:基於ExtJS的傳統UI對話方塊必須變更為Coral。
   * 當對話方塊名稱為&quot;dialog&quot;或&quot;design_dialog&quot;時，以及
`jcr:primaryType`屬性值或`xtype`屬性值為&quot;cq:Dialog&quot;。
* `legacy.dialog.coral2`:Coral 2對話方塊，應更新為使用Coral 3。
   * 當對話框及其子內容節點名稱為&quot;cq:dialog/content&quot;時，會偵測到此問題，
&quot;cq:design_dialog/content&quot;、&quot;cq:dialog.coral2/content&quot;或&quot;cq:design_dialog.coral2/content&quot;
和`sling:resourceType`屬性值不包含
&quot;granite/ui/components/coral/foundation&quot;。
* `legacy.custom.component`:繼承的元 `foundation/components`件應更新為使用核心元件。
   * 當`jcr:primaryType`屬性值為&quot;cq:Component&quot;且
      `sling:resourceSuperType` 屬性值包含「foundation/components」或
      `sling:resourceSuperType` 超類型元件鏈的屬性值包含&quot;foundation/components&quot;。
* `legacy.static.template`:靜態範本，應升級為可編輯的範本。
   * 當`jcr:primaryType`屬性值為&quot;cq:Template&quot;時，就會偵測到此問題。

## 可能的影響和風險{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_guidance"
>title="實施指南"
>abstract="Classic UI已不再以Cloud ServiceAEM形式提供，而製作的標準介面是可觸控的UI。 最佳實務是將所有不支援的介面和連結的自訂項目，重新分解為與Cloud Service相容的較新AEM功能／功能。 客戶可以利用現AEM有的Meduration Suite來協助減少AEM Sites實作現代化所需的工作。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/" text="AEM 現代化工具"

* Classic UI已不再提供AEM為Cloud Service。 製作的標準介面是可觸控的UI。
* 依賴舊式自訂元件可能會隨著時間增加維護成本。

## 可能的解決方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_tools"
>title="工具與資源"
>abstract="借助Meduration Suite，客AEM戶可將Classic(ExtJS)對話方塊轉換為Coral Dialog。 其目的是協助客戶從不受支援或舊有的功能，轉向強穩、現代化的AEM產品。 這些工具具備可設定性、可感知組態和可擴充性。 此外，探索使用一套標準化核心元件來取代自訂元件，以加速開發時間並降低應用程式的維護成本。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/pages/tools/component.html" text="元件轉換器"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html" text="核心元件"

* 運用[Meduration Tools suiteAEM](https://opensource.adobe.com/aem-modernize-tools/)來減少AEM Sites實作最新化所需的工作。 這些工具包括：
   * Coral對話方塊的傳統(ExtJS)對話方塊
   * 從基礎元件轉換為核心元件
   * 可編輯範本和回應式格線的靜態範本和欄位控制
   * 可編輯範本原則的設計與設計對話方塊
* 檢視專案的自訂元件庫，並盡可能轉換至標準化的[核心元件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html?lang=zh-Hant)集，以加速開發時間並降低應用程式的維護成本。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
