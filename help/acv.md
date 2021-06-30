---
title: ACV
description: 模式偵測器程式碼說明頁面
exl-id: 7e3c1142-c349-4bce-b8de-8e91528f80a5
source-git-commit: 57e33b97aba253bad62cf95dcca9ef6885d263e6
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 0%

---

# ACV {#acv}

Assets Content Validator

## 背景 {#background}

>[!INFO]
>id=&quot;aemcloud_bpa_acv_overview&quot;
>title=&quot;Assets Content Validator&quot;
>abstract=&quot;ACV可識別資產內容中缺少的強制節點。&quot;
>additional-url=&quot;https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/home.html&quot; text=&quot;重大變更 — Experience Manager為Cloud Service&quot;
>additional-url=&quot;https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html&quot; text=&quot;Experience Manager作為Cloud Service — 發行說明&quot;

`ACV`  Assets的Content Validator可識別資產內容中缺少的必要節點。這可能會導致Experience Manager為Cloud Service時無法使用某些資產功能。

子類型可用來識別不同類型的資訊，例如：

* `assets.sanity.missing.jcrcontent`:標識儲存庫中缺少必需節點的資料夾。識別存放庫中任何遺失的內容，有助於防止任何功能或使用案例損毀。

## 可能的影響和風險 {#implications-and-risks}

這可能會導致某些Assets功能失敗，而這些功能需要依賴Experience Manager作為Cloud Service中繼承的屬性。

## 可能的解決方案 {#solutions}

>[!INFO]
>id=&quot;aemcloud_bpa_acv_guidation&quot;
>title=&quot;實作指引&quot;
>abstract=&quot;Adobe建議檢閱內容結構，以防止依賴繼承屬性的工作流程中斷。 如需協助，請連絡客戶服務」。
>additional-url=&quot;https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html&quot; text=&quot;Experience Cloud支援&quot;

* 如果資料夾缺少子節點，則分析該資料夾。 如果資料夾的數量是可管理的，請手動建立節點，否則請使用指令碼。
* 請洽詢我們的[Experience Manager客戶服務團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑問。
