---
title: UMI
description: 模式偵測器程式碼說明頁面。
exl-id: 04efa760-61f5-4690-8b4e-89fa756c5b64
source-git-commit: 0d693e3ccadc81b59852914f115bb2fa2ea166b0
workflow-type: ht
source-wordcount: '352'
ht-degree: 100%

---

# UMI {#umi}

升級設定錯誤問題

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_overview"
>title="升級設定錯誤問題"
>abstract="UMI 會識別某些 OSGi 設定的修改，這些修改在升級時會造成問題，包括升級失敗或降低功能。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes" text="重大變更 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="AEM as a Cloud Service - 發行說明"

`UMI` 會識別某些 OSGi 設定的修改，這些修改在升級時會造成問題，包括升級失敗或降低功能。

會檢查下列設定是否修改：

* `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName`
* `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`
* `org.apache.sling.engine.impl.auth.SlingAuthenticator`
* `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory`
* `com.day.cq.commons.impl.ExternalizerImpl`
* `org.apache.sling.commons.log.LogManager.factory.config`：確認自訂記錄器的 `org.apache.sling.commons.log.file` 屬性是否指向 `logs/error.log` 檔案以外的內容。

## 可能的影響和風險 {#implications-and-risks}

* 變更或移除設定可能會造成以下錯誤：
   * 升級可能會變得停滯 (例如遺失的 `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName` 出現在 `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids` 中)。
   * 升級後授權問題可能隨之而來 (`org.apache.sling.engine.impl.auth.SlingAuthenticator`)。
   * 某些功能可能無法如預期運作。例如變更 `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory` 可能會導致 JSP 檔案未編譯，最終結果是失去功能。
   * 外部器設定 `com.day.cq.commons.impl.ExternalizerImpl` 的值是透過 AEM as a Cloud Service 中的 Cloud Manager 環境變數所設定。
   * AEM as a Cloud Service 不支援自訂記錄檔。無法從 AEM as a Cloud Service 存取寫入自訂命名記錄的記錄。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_guidance"
>title="實施指導"
>abstract="最佳做法是檢閱目前的設定並還原上述設定的任何變更，以避免任何未來升級問題。請聯絡 Adobe 支援人員，取得協助或說明。"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 請勿變更或移除上述四個設定。
   * 如有下列違規行為：\
     「遺失 OSGi 設定『`xyz-configuration`』的必要屬性：『[property-1,property-2...]』」。\
     請確認這些刪除是否合法，因為這些 OSGI 設定是 OOTB，而且可能從未透過 OSGi 設定管理員進行修改/儲存。
* 如果已經變更設定，應將其還原為預期值。這些值顯示在 `UMI` 訊息中。
* 對於 `com.day.cq.commons.impl.ExternalizerImpl`，請參閱[文件](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/implementing/developer-tools/externalizer)以了解如何使用 AEM as a Cloud Service 中的 Cloud Manager 環境變數來進行外部器設定。
* 如果是 `org.apache.sling.commons.log.LogManager.factory.config`，變更 OSGI 設定以將自訂記錄器傳送到 `logs/error.log` 檔案。請參閱[文件](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/logs)以重新指向 `logs/error.log` 檔案。
* 請聯絡 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以釐清或解決問題。
