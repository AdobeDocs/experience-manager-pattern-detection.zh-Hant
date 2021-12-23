---
title: ACV
description: 模式偵測器程式碼說明頁面
exl-id: 1dd1af45-aa56-48da-8582-c4330cded489
source-git-commit: 301aef7e53e94eb5941691450b3f1192408f2c6b
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 2%

---

# ACV {#acv}

Assets Content Validator

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_overview"
>title="Assets Content Validator"
>abstract="ACV可識別資產內容中缺少的必要節點。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/home.html" text="重大變更 — Experience Manageras a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hant" text="Experience Manageras a Cloud Service — 發行說明"

`ACV`  Assets的Content Validator可識別資產內容中缺少的必要節點。 這可能會導致某些Assets功能在Experience Manageras a Cloud Service上失敗。

子類型可用來識別不同類型的資訊，例如：

* `missing.jcrcontent`:標識儲存庫中缺少必需節點的資料夾。 識別存放庫中任何遺失的內容，有助於防止任何功能或使用案例損毀。
* `missing.original.rendition`:識別存放庫中缺少強制原始轉譯的資產。

## 可能的影響和風險 {#implications-and-risks}

* 這可能會導致某些Assets功能失敗，而這些功能須仰賴Experience Manageras a Cloud Service中的繼承屬性。
* AEM Assets取決於原始轉譯的存在。 如果原始轉譯遺失，Cloud Service中的資產處理會進入回圈。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_guidance"
>title="實施指南"
>abstract="Adobe建議檢閱內容結構，以防止依賴繼承屬性的工作流程中斷。 請聯絡客戶服務以取得協助。"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 如果資料夾缺少子節點，則分析該資料夾。 如果資料夾的數量是可管理的，請手動建立節點，否則請使用指令碼。
* 針對遺失原始轉譯的資產，請重新上傳資產或在移轉前將其刪除。
* 聯繫我們的 [Experience Manager客戶服務團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) 以取得澄清或處理關注。
