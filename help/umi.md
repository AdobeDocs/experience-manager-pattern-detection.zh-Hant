---
title: UMI
description: 模式偵測器程式碼說明頁面
exl-id: 04efa760-61f5-4690-8b4e-89fa756c5b64
translation-type: tm+mt
source-git-commit: 76dc944f1592118920f89c513faf456b8aa443a9
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 3%

---

# UMI {#umi}

升級配置錯誤問題

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_overview"
>title="升級配置錯誤問題"
>abstract="UMI可識別對某些OSGi配置的修改，這些修改在升級時將導致問題，包括升級失敗或功能減少。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="顯著變AEM更——作為Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hant" text="作AEM為Cloud Service-發行說明"

`UMI` 標識對某些OSGi配置的修改，這些修改在升級時將導致問題，包括升級失敗或功能減少。

將檢查以下配置以進行修改：
* `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName`
* `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`
* `org.apache.sling.engine.impl.auth.SlingAuthenticator`
* `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory`

## 可能的影響和風險{#implications-and-risks}

* 更改或刪除配置可能導致以下問題：
   * 升級可能會卡住（例如`org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName`遺失，但`org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`中顯示）。
   * 升級後可能會發生授權問題(`org.apache.sling.engine.impl.auth.SlingAuthenticator`)。
   * 某些功能可能無法如預期般運作。 例如，更改`org.apache.sling.scripting.java.impl.JavaScriptEngineFactory`可能會導致某些JSP檔案無法編譯，最終導致功能丟失。

## 可能的解決方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_guidance"
>title="實施指南"
>abstract="最佳做法是檢查您當前的配置並回復對上述配置所做的任何更改，以避免將來出現任何升級問題。 聯絡Adobe支援以取得說明"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 請勿更改或刪除上述四個配置。
* 如果配置已更改，則應將其恢復為預期值。 這些值在`UMI`消息中指示。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
