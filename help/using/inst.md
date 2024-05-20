---
title: INST
description: 模式偵測器程式碼說明頁面。
exl-id: 9b8129d7-63d7-4975-a68b-9ba704d01532
source-git-commit: 58fdb55e1f0c067dacf6825c4076465bc8c5d821
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 99%

---

# INST {#inst}

已安裝的成品

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_overview"
>title="已安裝的成品"
>abstract="INST 會識別客戶安裝在 AEM 中的自訂和第三方套件和套件組合。報告此資訊以協助表示系統狀態的特性和升級工作的一般範圍。任何第三方套件都必須遵守 AEM as a Cloud Service 開發和封裝指導方針。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines" text="開發指導方針 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/implementing/developing/repository-structure-package" text="封裝指導方針 - AEM as a Cloud Service"

`INST` 會識別客戶安裝在 AEM 中的自訂和第三方套件和套件組合。報告此資訊以協助表示系統狀態的特性和升級工作的一般範圍。

已安裝多個套件版本時，只會報告最新版。

偵測到的套件和套件組合不一定針對 AEM as a Cloud Service 進行最佳化。任何第三方套件都應透過其建立者或 Adobe 驗證是否相容於 AEM as a Cloud Service。

子類型用於識別不同類型的資訊：

* `custom.bundle`：已安裝在 AEM 中的套件組合。
* `custom.package`：已安裝在 AEM 中的套件。

## 可能的影響和風險 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_guidance"
>title="實施指導"
>abstract="客戶無法再使用 CRX 封裝管理員來安裝第三方套件。客戶應檢閱這些已安裝且必須重組的成品，並且將這些成品最佳化以搭配 AEM as a Cloud Service 使用。向建立者或 Adobe 驗證任何第三方套件是否與 AEM as a Cloud Service 相容。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure#embeddeds" text="將子套件內嵌於容器套件"


* 無法使用 AEM as a Cloud Service 中的 CRX 封裝管理員來安裝第三方套件。
* 相依於第三方套件的應用程式可能無法如預期運作，直到正確部署可搭配 AEM as a Cloud Service 使用。
* 若未針對 AEM as a Cloud Service 進行最佳化，第三方廠商套件可能會導致不良行為。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_tools"
>title="工具和資源"
>abstract="請檢閱 WKND 舊版專案以了解如何將 INST 違規設為相容於 AEM Cloud Service。也請檢閱 GitHub 上的 INST 違規範例，以了解如何更正並將其部署於 AEM as a Cloud Service。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst" text="WKND-舊版專案"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst" text="INST 違規範例 - GitHub"

* 應使用 Cloud Manager [部署程序](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/implementing/using-cloud-manager/deploy-code#deployment-process)將第三方套件作為專案的一部分部署到 AEM。
* 請檢閱如何[將第三方套件內嵌](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure#embedding-3rd-party-packages)於 AEM as a Cloud Service 的專案。
* 第三方套件必須遵守 AEM as a Cloud Service [開發](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines)和[封裝](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/implementing/developing/repository-structure-package)指導方針。
* 請檢閱 [WKND 舊版](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst)專案，了解如何更正 [INST 違規](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst)，使其與 AEM as a Cloud Service 相容。
* 請聯絡 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以釐清或解決問題。
