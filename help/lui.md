---
title: 呂
description: 模式偵測器程式碼說明頁面
translation-type: tm+mt
source-git-commit: a2c7137dd5cb2479bc0c6134d3afa58111049a68
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 4%

---


# LUI {#lui}

舊版使用者介面

## 背景 {#background}

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

* Classic UI已不再提供AEM為Cloud Service。 製作的標準介面是可觸控的UI。
* 依賴舊式自訂元件可能會隨著時間增加維護成本。

## 可能的解決方案{#solutions}

* 運用[Meduration Tools suiteAEM](https://opensource.adobe.com/aem-modernize-tools/)來減少AEM Sites實作最新化所需的工作。 這些工具包括：
   * Coral對話方塊的傳統(ExtJS)對話方塊
   * 從基礎元件轉換為核心元件
   * 可編輯範本和回應式格線的靜態範本和欄位控制
   * 可編輯範本原則的設計與設計對話方塊
* 檢視專案的自訂元件庫，並盡可能轉換至標準化的[核心元件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html?lang=zh-Hant)集，以加速開發時間並降低應用程式的維護成本。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
