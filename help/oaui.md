---
title: 奧伊
description: 模式偵測器程式碼說明頁面
exl-id: 326144d6-705a-4b2c-ac35-403fd4c2259f
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 3%

---

# 奧伊 {#oaui}

OAuth使用者例項

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_overview"
>title="OAuth使用者例項"
>abstract="OAUI程式碼可識別至少有一個與OAuth相關的設定使用者需要正確移轉的模式。 當rep:AuthorizableId節點下方有名為oauth的子節點（以/home/user-path/user-node/oauth的形式）時，系統會為使用者設定OAuth"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hant" text="AEM as aCloud Service — 發行說明"

`OAUI` 識別至少有一個與OAuth相關的已設定使用者需要正確移轉的模式。

當`rep:AuthorizableId`節點下方直接有名為`oauth`的子節點（以`/home/user-path/user-node/oauth`的形式）時，會為用戶配置OAuth。

例如：`/home/users/ims/0001/R80w6XaUCBq3jHE47xDN/oauth`。

## 可能的影響和風險{#implications-and-risks}

* 使用OAuth設定的外部使用者，在透過下列程式重新設定前，將無法登入製作/發佈執行個體。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_guidance"
>title="實施指南"
>abstract="設定了OAuth的外部使用者必須重新設定為與AEM as aCloud Service相容，才能登入製作/發佈執行個體。 AEM as aCloud Service僅針對作者、管理員和開發使用者提供IMS驗證支援，並針對發佈環境提供以SAML為基礎的整合。 請洽詢Adobe支援以取得說明和說明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/security/ims-support.html" text="IMS支援 — AEM as aCloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/personalization/user-and-group-sync-for-publish-tier.html?lang=en#integration-with-an-idp" text="SAML整合 — 發佈"

* 請連絡您的Adobe代表，討論使用者移轉的選項。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決問題。
