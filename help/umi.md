---
title: UMI
description: 模式偵測器程式碼說明頁面
translation-type: tm+mt
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 0%

---


# UMI {#umi}

升級配置錯誤問題

## 背景 {#background}

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

* 請勿更改或刪除上述四個配置。
* 如果配置已更改，則應將其恢復為預期值。 這些值在`UMI`消息中指示。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
