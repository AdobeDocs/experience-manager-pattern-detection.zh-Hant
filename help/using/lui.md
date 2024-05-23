---
title: LUI
description: 模式偵測器程式碼說明頁面。
exl-id: 742220d6-b37a-48ec-9f89-2f3f0ce6ff96
source-git-commit: 58fdb55e1f0c067dacf6825c4076465bc8c5d821
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 100%

---

# LUI {#lui}

舊版使用者介面

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_overview"
>title="舊版使用者介面"
>abstract="LUI 會識別已棄用的使用者介面元素的使用。在較高版本的 AEM 和 AEM as a Cloud Service 中不建議或不支援這些元素。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes" text="重大變更 - AEM as a Cloud Service"

`LUI` 會識別已棄用的使用者介面元素的使用。在較高版本的 AEM 和 AEM as a Cloud Service 中不建議或不支援這些元素。

子類型用於識別應該或必須升級的不同使用者介面元素類型：

* `legacy.dialog.classic`：基於 ExtJS 的 Classic UI 對話框必須變更為 Coral。
   * 當對話框名稱是 `dialog` 或 `design_dialog`，並在
 `jcr:primaryType` 屬性值或`xtype`  屬性值是 `cq:Dialog` 時，會偵測到子類型。
* `legacy.dialog.coral2`： `Coral 2` 對話方塊應更新為使用 `Coral 3`。
   * 當對話方塊及其子內容節點名稱為
      * `cq:dialog/content`、
      * `cq:design_dialog/content`、
      * `cq:dialog.coral2/content`、
      * 或 `cq:design_dialog.coral2/content`
且 `sling:resourceType` 屬性值不包含 `granite/ui/components/coral/foundation` 時，會偵測到子類型。
* `legacy.custom.component`：從 `foundation/components` 繼承而來的元件應更新為使用核心元件。
   * 當 `jcr:primaryType` 屬性值是 `cq:Component`，而且
     `sling:resourceSuperType` 屬性值包含「foundation / components」時，會偵測到子類型。或者超級類型元件鏈結的任何
     `sling:resourceSuperType` 屬性值包含
「foundation / components」時，會偵測到子類型。
* `legacy.static.template`：靜態範本應升級為可編輯的範本。
   * 當 `jcr:primaryType` 屬性值是 `cq:Template` 時會偵測到子類型。
* `content.fragment.template`：內容片段範本應建立片段模型，以取代片段範本。
   * 內容片段範本可以在以下位置找到：
      * 現成可用的內容片段範本儲存於 `/libs/settings/dam/cfm/templates`
      * 它們可以在 `/apps/settings/dam/cfm/templates` 或 `/conf/.../settings/dam/cfm/templates`(... = 全域或 &quot;租用戶&quot;) 中重疊
* `translation.dictionary`：`I18n` 字典存在於 `/apps` 下方。
   * `/apps` 在執行階段不可變，且 translator.html 已無法在 AEM as a Cloud Service 中使用。

## 可能的影響和風險 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_guidance"
>title="實施指導"
>abstract="Classic UI 無法再用於 AEM as a Cloud Service，標準製作介面是已啟用觸控的 UI。最佳實務是移動所有不支援的介面，而且應將連結自訂重構為相容於 AEM as a Cloud Service 的較新特性和功能。客戶可以使用現有的 AEM 現代化套件，協助減少 AEM Sites 實施現代化所需的工作。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/" text="AEM 現代化工具"

* Classic UI 無法再用於 AEM as a Cloud Service。標準製作介面是已啟用觸控的 UI。
* 依賴舊版自訂元件可能會隨著時間增加維護成本。
* 內容片段範本已為 AEM 6.3 中的內容片段模型取代。將基於舊版範本的內容片段遷移至 AEM as a Cloud Service 時，這些片段雖然仍保有功能性，但無法根據舊版範本建立片段。也無法使用 AEM GraphQL 提供這些片段，而這需要讓內容片段模型作為結構描述使用。
* /apps 在執行階段不可變，且 translator.html 已無法在 AEM as a Cloud Service 中使用。因此，`I18n` 字典必須透過 CI / CD 管道從 Git 取得。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_tools"
>title="工具和資源"
>abstract="借助 AEM 現代化套件，客戶可以將 Classic(ExtJS) 對話框轉換為 Coral 對話框。目的是協助客戶從不支援或舊版功能轉換為強大現代的 AEM 供應項目。這些是可設定的、可感知設定和可擴充的工具。此外，請嘗試將自訂元件取代為標準核心元件集，以加快開發時間並降低應用程式維護成本。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/pages/component/about.html" text="元件轉換器"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-core-components/using/introduction" text="核心元件"

* 要減少 AEM Sites 實施現代化所需的工作，使用 [AEM 現代化工具套件](https://opensource.adobe.com/aem-modernize-tools/)。這些工具包含下列轉換：
   * 從 Classic (ExtJS) 對話框轉換為 Coral 對話框
   * 從基礎元件轉換為核心元件
   * 從靜態範本和資料行控制轉換為可編輯的範本與回應式格線
   * 從設計與設計對話框轉換為可編輯的範本原則
* 請檢閱專案的自訂元件程式庫，並轉變為標準[核心元件](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-core-components/using/introduction)集 (如有可能)，以加快開發時間並降低應用程式維護成本。
* 建立具有與舊範本相同功能的內容片段模型，並在將來使用這些模型建立內容片段。如需更多詳細資訊，請參閱[內容片段模型](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-65/content/assets/content-fragments/content-fragments-models)。
* `I18n` 字典必須透過 CI / CD 管道從 Git 取得。[文件](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes#apps-libs-immutable)
* 請聯絡 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以釐清或解決問題。
