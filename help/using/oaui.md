---
title: OAUI
description: 模式偵測器程式碼說明頁面。
exl-id: 326144d6-705a-4b2c-ac35-403fd4c2259f
source-git-commit: b77a168fc8c075e8e41149a38df4d83fd2504a14
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 100%

---

# OAUI {#oaui}

OAuth 使用者執行個體

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_overview"
>title="OAuth 使用者執行個體"
>abstract="OAUI 程式碼會識別至少有一個 OAuth 相關設定使用者需要正確移轉的模式。當 rep:AuthorizableId 節點底下有一個名為 OAuth 的子節點 (採用 /home/user-path/user-node/oauth 的格式)，就會設定使用者的 OAuth。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="AEM as a Cloud Service - 發行說明"

`OAUI` 會識別至少有一個 OAuth 相關設定使用者需要正確移轉的模式。

當 `rep:AuthorizableId` 節點底下有一個名為 `oauth` 的子節點 (採用 `/home/user-path/user-node/oauth` 的格式)，就會設定使用者的 OAuth。

範例是：`/home/users/ims/0001/R80w6XaUCBq3jHE47xDN/oauth`。

## 可能的影響和風險 {#implications-and-risks}

* 使用 OAuth 設定的外部使用者無法登入製作/發佈執行個體，直到使用下列程序重新設定。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_guidance"
>title="實施指導"
>abstract="使用 OAuth 設定的外部使用者無法登入製作/發佈執行個體，直到將其重新設定為與 AEM as a Cloud Service 相容。AEM as a Cloud Service 只為作者、管理和開發使用者提供 IMS 驗證支援，並為發佈環境提供 SAML 型整合。請聯絡 Adobe 支援人員，取得協助或說明。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/security/ims-support" text="IMS 支援 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/sites/authoring/personalization/user-and-group-sync-for-publish-tier#integration-with-an-idp" text="SAML 整合 - 發佈"

* 如果您必須討論使用者移轉選項，請聯絡您的 Adobe 代表。
* 請聯絡 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以釐清或解決問題。
