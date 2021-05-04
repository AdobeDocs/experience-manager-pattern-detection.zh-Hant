---
title: 奧伊
description: 模式偵測器程式碼說明頁面
exl-id: 326144d6-705a-4b2c-ac35-403fd4c2259f
translation-type: tm+mt
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 3%

---

# OAUI {#oaui}

OAuth使用者例項

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_overview"
>title="OAuth使用者例項"
>abstract="OAUI程式碼可識別模式，其中至少有一個與OAuth相關的設定使用者需要正確移轉。 當rep:AuthorizableId節點下方有名為oauth的子節點時，/home/user-path/user-node/oauth格式會為使用者設定OAuth"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hant" text="作AEM為Cloud Service-發行說明"

`OAUI` 識別至少有一個與OAuth相關且需要正確移轉的設定使用者的模式。

當`rep:AuthorizableId`節點下方有名為`oauth`的子節點時，以`/home/user-path/user-node/oauth`的形式為用戶配置OAuth。

例如：`/home/users/ims/0001/R80w6XaUCBq3jHE47xDN/oauth`。

## 可能的影響和風險{#implications-and-risks}

* 使用OAuth設定的外部使用者，在依下列程式重新設定之前，將無法登入作者／發佈例項。

## 可能的解決方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_guidance"
>title="實施指南"
>abstract="使用OAuth設定的外部使用者在重新設定為與Cloud Service相容之前，將無法登入作者／發佈例AEM項。 作AEM為Cloud Service，僅提供作者、管理員和開發使用者的IMS驗證支援，以及發佈環境的SAML整合。 聯絡Adobe支援以取得說明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/security/ims-support.html" text="IMS支援-AEM做為Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/personalization/user-and-group-sync-for-publish-tier.html?lang=en#integration-with-an-idp" text="SAML整合——發佈"

* 請洽詢您的Adobe代表，以討論使用者移轉的選項。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
