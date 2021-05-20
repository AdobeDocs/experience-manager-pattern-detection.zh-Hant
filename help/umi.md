---
title: UMI
description: 模式偵測器程式碼說明頁面
exl-id: 04efa760-61f5-4690-8b4e-89fa756c5b64
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
>abstract="UMI識別對某些OSGi設定的修改，這些修改在升級時會造成問題，包括升級失敗或功能減少。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="重大變更 — AEM as aCloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hant" text="AEM as aCloud Service — 發行說明"

`UMI` 識別對某些OSGi設定所做的修改，這些修改在升級時會造成問題，包括升級失敗或功能降低。

系統會檢查下列設定以進行修改：
* `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName`
* `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`
* `org.apache.sling.engine.impl.auth.SlingAuthenticator`
* `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory`

## 可能的影響和風險{#implications-and-risks}

* 更改或刪除配置可能導致以下問題：
   * 升級可能卡住（例如`org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName`遺失，但存在於`org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`中）。
   * 升級後可能會出現授權問題(`org.apache.sling.engine.impl.auth.SlingAuthenticator`)。
   * 某些功能可能無法如預期般運作。 例如，更改`org.apache.sling.scripting.java.impl.JavaScriptEngineFactory`可能會導致某些JSP檔案無法編譯，最終導致功能丟失。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_guidance"
>title="實施指南"
>abstract="最佳實務是檢閱您目前的設定，並回復對上述設定所做的任何變更，以避免未來發生任何升級問題。 請洽詢Adobe支援以取得說明和說明"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 請勿變更或移除上述四項設定。
* 如果設定已變更，則應將其還原為其預期值。 這些值在`UMI`消息中指示。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決問題。
