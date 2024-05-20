---
title: LUI
description: 模式偵測器程式碼說明頁面。
exl-id: 742220d6-b37a-48ec-9f89-2f3f0ce6ff96
source-git-commit: 58fdb55e1f0c067dacf6825c4076465bc8c5d821
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 49%

---

# LUI {#lui}

舊版使用者介面

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_overview"
>title="舊版使用者介面"
>abstract="LUI會識別已棄用使用者介面元素的使用。 這些元素在更新版本的AEM和AEMas a Cloud Service中不建議或不支援。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes" text="重大變更 - AEM as a Cloud Service"

`LUI`  會識別已棄用使用者介面元素的使用。 較新版本的AEM和AEMas a Cloud Service中不建議或不支援這些元素。

子類型用於識別應該或必須升級的不同使用者介面元素類型：

* `legacy.dialog.classic`：基於ExtJS的Classic UI對話方塊必須變更為Coral。
   * 當對話方塊名稱是 `dialog` 或 `design_dialog` 而且當 `jcr:primaryType` 屬性值或 `xtype` 屬性值是 `cq:Dialog`.
* `legacy.dialog.coral2`： `Coral 2` 對話方塊應更新為使用 `Coral 3`。
   * 當對話方塊及其子內容節點名稱為
      * `cq:dialog/content`，
      * `cq:design_dialog/content`，
      * `cq:dialog.coral2/content`，
      * 或 `cq:design_dialog.coral2/content`
和 `sling:resourceType` 屬性值不包含 `granite/ui/components/coral/foundation`.
* `legacy.custom.component`：從 `foundation/components` 繼承而來的元件應更新為使用核心元件。
   * 此子型別偵測於 `jcr:primaryType` 屬性值是 `cq:Component` 和
     `sling:resourceSuperType` 屬性值包含&quot;foundation / components&quot;。 或者超級類型元件鏈結的任何
     `sling:resourceSuperType` 屬性值包含&quot;foundation / components&quot;時偵測到它。
* `legacy.static.template`：靜態範本應升級為可編輯的範本。
   * 此子型別偵測於 `jcr:primaryType` 屬性值是 `cq:Template`.
* `content.fragment.template`：內容片段範本應建立片段模型，以取代片段範本。
   * 內容片段範本可以在以下位置找到：
      * 現成可用的內容片段範本儲存於 `/libs/settings/dam/cfm/templates`
      * 它們可以在 `/apps/settings/dam/cfm/templates` 或 `/conf/.../settings/dam/cfm/templates`(... = 全域或 &quot;租用戶&quot;) 中重疊
* `translation.dictionary`： `I18n` 字典出現於 `/apps`.
   * `/apps` 在執行階段不可變，且translator.html將無法再用於AEM as a cloud service。

## 可能的影響和風險 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_guidance"
>title="實施指導"
>abstract="Classic UI 無法再用於 AEM as a Cloud Service，標準製作介面是已啟用觸控的 UI。最佳實務是移動所有不支援的介面，而且應將連結的自訂重構為相容於AEMas a Cloud Service的較新功能。 客戶可以使用現有的 AEM 現代化套件，協助減少 AEM Sites 實施現代化所需的工作。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/" text="AEM 現代化工具"

* Classic UI 無法再用於 AEM as a Cloud Service。標準製作介面是已啟用觸控的 UI。
* 依賴舊版自訂元件可能會隨著時間增加維護成本。
* 內容片段範本取代AEM 6.3中的內容片段模型。將基於舊版範本的內容片段遷移到AEMas a Cloud Service時，這些片段雖然仍保有功能性，但無法根據舊版範本建立片段。 也無法使用AEM GraphQL提供這些片段，而這需要內容片段模型作為結構描述。
* /apps 在執行階段不可變，且 translator.html 已無法在 AEM as a Cloud Service 中使用。因此， `I18n` 字典必須透過CI / CD管道來自Git。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_tools"
>title="工具和資源"
>abstract="借助 AEM 現代化套件，客戶可以將 Classic(ExtJS) 對話框轉換為 Coral 對話框。目的是協助客戶從不支援或舊版功能轉換為強大現代的 AEM 供應項目。這些是可設定的、可感知設定和可擴充的工具。此外，請嘗試將自訂元件取代為標準核心元件集，以加快開發時間並降低應用程式維護成本。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/pages/component/about.html" text="元件轉換器"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-core-components/using/introduction" text="核心元件"

* 若要減少因應現代化AEM Sites實作所需的工作量，請使用 [AEM現代化工具套裝](https://opensource.adobe.com/aem-modernize-tools/). 這些工具包含下列轉換：
   * 從 Classic (ExtJS) 對話框轉換為 Coral 對話框
   * 從基礎元件轉換為核心元件
   * 從靜態範本和欄控制轉換為可編輯範本和回應式格線
   * 從設計與設計對話方塊轉換為可編輯的範本原則
* 請檢閱專案的自訂元件程式庫，並轉變為標準[核心元件](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-core-components/using/introduction)集 (如有可能)，以加快開發時間並降低應用程式維護成本。
* 使用與舊版範本相等的功能建立內容片段模型，並將這些模型用於日後的內容片段建立。 如需更多詳細資訊，請參閱[內容片段模型](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-65/content/assets/content-fragments/content-fragments-models)。
* `I18n` 字典必須透過CI / CD管道來自Git。 [文件](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes#apps-libs-immutable)
* 請聯絡 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以釐清或解決問題。
