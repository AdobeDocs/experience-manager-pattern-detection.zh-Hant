---
title: ACV
description: 模式偵測器程式碼說明頁面
exl-id: 7e3c1142-c349-4bce-b8de-8e91528f80a5
source-git-commit: d61fbb28fdf91fd9b356654d5cd2d50b156398c4
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 3%

---

# ACV {#acv}

Assets Content Validator

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_overview"
>title="Assets Content Validator"
>abstract="ACV可識別資產內容中缺少的必要節點。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/home.html" text="重大變更 — Experience Manager為Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="Experience Manager作為Cloud Service — 發行說明"

`ACV`  Assets的Content Validator可識別資產內容中缺少的必要節點。這可能會導致Experience Manager為Cloud Service時無法使用某些資產功能。

子類型可用來識別不同類型的資訊，例如：

* `assets.sanity.missing.jcrcontent`:標識儲存庫中缺少必需節點的資料夾。識別存放庫中任何遺失的內容，有助於防止任何功能或使用案例損毀。

## 可能的影響和風險 {#implications-and-risks}

這可能會導致某些Assets功能失敗，而這些功能需要依賴Experience Manager作為Cloud Service中繼承的屬性。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_guidance"
>title="實施指南"
>abstract="Adobe建議檢閱內容結構，以防止依賴繼承屬性的工作流程中斷。 如需協助，請連絡客戶服務。"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 如果資料夾缺少子節點，則分析該資料夾。 如果資料夾的數量是可管理的，請手動建立節點，否則請使用指令碼。
* 請洽詢我們的[Experience Manager客戶服務團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑問。
