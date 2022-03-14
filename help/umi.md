---
title: UMI
description: 模式偵測器程式碼說明頁面
exl-id: 04efa760-61f5-4690-8b4e-89fa756c5b64
source-git-commit: e72ddc20578f8ca736da198e626478816e7ca641
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 83%

---

# 海 {#umi}

升級設定錯誤問題

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_overview"
>title="升級設定錯誤問題"
>abstract="UMI 會識別某些 OSGi 設定的修改，這些修改在升級時可能會造成問題，包括升級失敗或降低功能。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="重大變更 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hant" text="AEM as a Cloud Service - 發行說明"

`UMI` 會識別某些 OSGi 設定的修改，這些修改在升級時可能會造成問題，包括升級失敗或降低功能。

會檢查下列設定是否修改：
* `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName`
* `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`
* `org.apache.sling.engine.impl.auth.SlingAuthenticator`
* `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory`
* `com.day.cq.commons.impl.ExternalizerImpl`

## 可能影響和風險 {#implications-and-risks}

* 變更或移除設定可能會造成下列錯誤：
   * 升級可能會變得停滯 (例如遺失的 `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName` 出現在 `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids` 中)。
   * 升級後授權問題可能隨之而來 (`org.apache.sling.engine.impl.auth.SlingAuthenticator`)。
   * 某些功能可能無法如預期運作。例如變更 `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory` 可能會導致 JSP 檔案未編譯，最終結果是失去功能。
   * 外部化器配置的值 `com.day.cq.commons.impl.ExternalizerImpl` 由雲管理器as a Cloud Service中的環境變數AEM設定。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_guidance"
>title="實施指導"
>abstract="最佳實務是檢閱目前的設定並還原上述設定的任何變更，以避免任何未來升級問題。請聯繫 Adobe 支援以尋求協助與澄清。"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 請勿變更或移除上述四個設定。
* 如果已經變更設定，應將其還原為預期值。這些值顯示在 `UMI` 訊息中。
* 對於 `com.day.cq.commons.impl.ExternalizerImpl`請參閱 [文檔](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developer-tools/externalizer.html?lang=en) 用於在as a Cloud Service中使用雲管理器環境變數設定外部AEM化器配置。
* 請聯繫我們的 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以澄清或解決問題。
