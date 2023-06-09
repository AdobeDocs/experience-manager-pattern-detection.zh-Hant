---
title: LUI
description: 模式偵測器程式碼說明頁面
exl-id: 742220d6-b37a-48ec-9f89-2f3f0ce6ff96
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: tm+mt
source-wordcount: '783'
ht-degree: 100%

---

# LUI {#lui}

舊版使用者介面

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_overview"
>title="舊版使用者介面"
>abstract="LUI 會識別 AEM 更新版本和 AEM as a Cloud Service 中不建議或不支援之已棄用使用者介面元素的使用。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="重大變更 - AEM as a Cloud Service"

`LUI` 會識別 AEM 更新版本和 AEM as a Cloud Service 中不建議或不支援之已棄用使用者介面元素的使用。

子類型用於識別應該或必須升級的不同使用者介面元素類型：

* `legacy.dialog.classic`：基於 ExtJS 的 Classic UI 對話框必須變更為 Coral。
   * 當對話框名稱是 &quot;dialog&quot; 或 &quot;design_dialog&quot;，並在
`jcr:primaryType` 屬性值或 `xtype` 屬性值是 &quot;cq:Dialog&quot; 時偵測到它。
* `legacy.dialog.coral2`：Coral 2 對話框應更新為使用 Coral 3。
   * 當對話框及其子內容節點名稱是 &quot;cq:dialog/content&quot;、
&quot;cq:design_dialog/content&quot;、&quot;cq:dialog.coral2/content&quot; 或 &quot;cq:design_dialog.coral2/content&quot;，
而且 `sling:resourceType` 屬性值不包含
&quot;granite/ui/components/coral/foundation&quot; 時偵測到它。
* `legacy.custom.component`：從 `foundation/components` 繼承而來的元件應更新為使用核心元件。
   * 當 `jcr:primaryType` 屬性值是 &quot;cq:Component&quot;，而且
     `sling:resourceSuperType` 屬性值包含 &quot;foundation/components&quot;，或者超級類型元件鏈結的任何
     `sling:resourceSuperType` 屬性值包含 &quot;foundation/components&quot; 時偵測到它。
* `legacy.static.template`：靜態範本應升級為可編輯的範本。
   * 當 `jcr:primaryType` 屬性值是 &quot;cq:Template&quot; 時偵測到它。
* `content.fragment.template`：內容片段範本應建立片段模型，以取代片段範本。
   * 內容片段範本可以在以下位置找到：
      * 現成可用的內容片段範本儲存於 `/libs/settings/dam/cfm/templates`
      * 它們可以在 `/apps/settings/dam/cfm/templates` 或 `/conf/.../settings/dam/cfm/templates`(... = 全域或 &quot;租用戶&quot;) 中重疊
* `translation.dictionary`：I18n 字典存在於 /apps 下方。
   * /apps 在執行階段不可變，且 translator.html 已無法在 AEM as a Cloud Service 中使用。

## 可能影響和風險 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_guidance"
>title="實施指導"
>abstract="Classic UI 無法再用於 AEM as a Cloud Service，標準製作介面是已啟用觸控的 UI。最佳實務是移動所有不支援的介面，而且應將連結自訂重構為相容於 AEM as a Cloud Service 的較新特性/功能。客戶可以善用現有的 AEM 現代化套件，協助減少 AEM Sites 實施現代化所需的工作。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/" text="AEM 現代化工具"

* Classic UI 無法再用於 AEM as a Cloud Service。標準製作介面是已啟用觸控的 UI。
* 依賴舊版自訂元件可能會隨著時間增加維護成本。
* 內容片段範本已為 AEM 6.3 中的內容片段模型取代。將基於舊版範本的內容片段遷移至 AEM as a Cloud Service 時，這些片段雖然仍保有功能性，但無法根據舊版範本建立新的片段。也無法使用 AEM GraphQL 提供這些片段，而這需要讓內容片段模型作為結構描述使用。
* /apps 在執行階段不可變，且 translator.html 已無法在 AEM as a Cloud Service 中使用。因此 I18n 字典必須透過 CI/CD 管道來自於 Git。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_tools"
>title="工具和資源"
>abstract="借助 AEM 現代化套件，客戶可以將 Classic(ExtJS) 對話框轉換為 Coral 對話框。目的是協助客戶從不支援或舊版功能轉換為強大現代的 AEM 供應項目。這些是可設定的、可感知設定和可擴充的工具。 此外，請嘗試將自訂元件取代為標準核心元件集，以加快開發時間並降低應用程式維護成本。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/pages/component/about.html" text="元件轉換器"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html?lang=zh-Hant" text="核心元件"

* 善用 [AEM 現代化工具套件](https://opensource.adobe.com/aem-modernize-tools/)，以減少 AEM Sites 實施現代化所需的工作。這些工具包含下列轉換：
   * 從 Classic (ExtJS) 對話框轉換為 Coral 對話框
   * 從基礎元件轉換為核心元件
   * 從靜態範本和資料行控制轉換為可編輯的範本與回應式格線
   * 從設計與設計對話框轉換為可編輯的範本原則
* 請檢閱專案的自訂元件程式庫，並轉變為標準[核心元件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html?lang=zh-Hant)集 (如有可能)，以加快開發時間並降低應用程式維護成本。
* 建議使用與舊版範本相等的功能建立內容片段模型，並將這些模型用於內容片段建立作業。如需詳細資訊，請參閱[內容片段模型](https://experienceleague.adobe.com/docs/experience-manager-65/assets/content-fragments/content-fragments-models.html?lang=zh-Hant)。
* I18n 字典必須透過 CI/CD 管道來自於 Git。[文件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes.html?lang=zh-Hant#apps-libs-immutable)
* 請聯繫我們的 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以澄清或解決問題。
