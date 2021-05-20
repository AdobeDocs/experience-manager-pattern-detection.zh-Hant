---
title: 呂
description: 模式偵測器程式碼說明頁面
exl-id: 742220d6-b37a-48ec-9f89-2f3f0ce6ff96
source-git-commit: 76dc944f1592118920f89c513faf456b8aa443a9
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 5%

---

# 呂 {#lui}

舊版使用者介面

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_overview"
>title="舊版使用者介面"
>abstract="LUI識別在舊版AEM和AEM中不建議或不支援的已棄用使用者介面元素的使用方式，作為Cloud Service。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="重大變更 — AEM as aCloud Service"

`LUI` 識別在舊版AEM和AEM as a Cloud Service中不建議或不支援的已棄用使用者介面元素的使用。

子類型用於識別應升級或必須升級的不同類型的使用者介面元素：

* `legacy.dialog.classic`:根據ExtJS的傳統UI對話方塊必須變更為Coral。
   * 當對話方塊名稱為「dialog」或「design_dialog」時，以及
`jcr:primaryType`屬性值或`xtype`屬性值為&quot;cq:Dialog&quot;。
* `legacy.dialog.coral2`:Coral 2對話方塊應更新為使用Coral 3。
   * 當對話方塊及其子內容節點名稱為「cq:dialog/content」時，就會偵測到此狀況。
&quot;cq:design_dialog/content&quot;、&quot;cq:dialog.coral2/content&quot;或&quot;cq:design_dialog.coral2/content&quot;
和`sling:resourceType`屬性值不包含
&quot;granite/ui/components/coral/foundation&quot;。
* `legacy.custom.component`:繼承的元 `foundation/components`件應更新為使用核心元件。
   * 當`jcr:primaryType`屬性值為&quot;cq:Component&quot;，且
      `sling:resourceSuperType` 屬性值包含「foundation/components」或
      `sling:resourceSuperType` 超類型元件鏈的屬性值包含「foundation/components」。
* `legacy.static.template`:靜態範本應升級為可編輯的範本。
   * 當`jcr:primaryType`屬性值為&quot;cq:Template&quot;時，就會偵測到此狀況。

## 可能的影響和風險{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_guidance"
>title="實施指南"
>abstract="AEM中不再提供傳統UI作為Cloud Service，而製作的標準介面為觸控式UI。 最佳實務是移動所有不支援的介面，且連結的自訂應重構為與AEM as aCloud Service相容的較新功能/功能。 客戶可善用現有的AEM現代化套裝，協助減少導入AEM Sites實作所需的心力。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/" text="AEM 現代化工具"

* AEM中不再提供傳統UI作為Cloud Service。 製作的標準介面是觸控式UI。
* 依賴舊式自訂元件可能會隨著時間增加維護成本。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_tools"
>title="工具和資源"
>abstract="透過AEM現代化套裝的協助，客戶可將傳統(ExtJS)對話方塊轉換為Coral對話方塊。 目的是協助客戶從不支援的或舊版功能，改用強大、現代的AEM產品。 這些工具可設定、可感知配置且可擴充。 此外，還可探索以一組標準化核心元件取代自訂元件，以縮短開發時間並降低應用程式的維護成本。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/pages/tools/component.html" text="元件轉換器"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html" text="核心元件"

* 運用[AEM現代化工具套裝](https://opensource.adobe.com/aem-modernize-tools/)來減少導入AEM Sites實作所需的工作。 這些工具包括：
   * 傳統(ExtJS)對話方塊至Coral對話方塊
   * 從基礎元件轉換為核心元件
   * 可編輯範本和回應式格線的靜態範本和欄控制
   * 可編輯的模板策略的設計和設計對話框
* 檢閱專案的自訂元件庫，並盡可能轉換至標準化的[核心元件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html?lang=zh-Hant)集，以縮短開發時間並降低應用程式的維護成本。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決問題。
