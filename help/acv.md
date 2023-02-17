---
title: ACV
description: 模式偵測器程式碼說明頁面
exl-id: 1dd1af45-aa56-48da-8582-c4330cded489
source-git-commit: 0a6b0f8f2b64bf1c966b8f282a2205f2772afe3f
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 86%

---

# ACV {#acv}

Assets 內容驗證器

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_overview"
>title="Assets 內容驗證器"
>abstract="ACV 會識別資產內容中缺少的必要節點。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/home.html" text="重大變更 - Experience Manager as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hant" text="Experience Manager as a Cloud Service - 發行說明"

`ACV` Assets 內容驗證器會識別資產內容中缺少的必要節點和違規行為。這可能會導致 Experience Manager as a Cloud Service 中的某些 Assets 功能失敗。

子類型用於識別不同類型的資訊，例如：

* `missing.jcrcontent`：識別存放庫中有缺少必要節點的檔案夾。識別存放庫中有任何缺少的內容，有助於防止任何損壞的功能或使用案例。
* `missing.original.rendition`：識別存放庫中有缺少必要原始轉譯的資產。請注意預覽 PDF 頁面不需要在 AEMaaCS 中產生子資產。因此，對於 PDF 資產，將禁止報告缺少原始轉譯的子資產。
* `metadata.descendants.violation`：識別在存放庫的資產中繼資料節點下具有超過 100 個子系的資產。
* `conflict.node`:識別/content/dam/ path下儲存庫中是否存在衝突節點。

## 可能影響和風險 {#implications-and-risks}

* 這可能會導致某些依賴 Experience Manager as a Cloud Service 繼承屬性的 Assets 功能失敗。
* AEM Assets 依賴原始轉譯的存在。如果缺少原始轉譯，Cloud Service 的資產處理將會進入迴圈。AEMaaCS 不支援產生子資產。
* 中繼資料節點下的大量子系可能會減慢載入包含違反此規則之資產的檔案夾的速度。
* 存在衝突節點可能會導致AEMas a Cloud Service擷取失敗。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_guidance"
>title="實施指導"
>abstract="Adobe 建議檢閱內容結構，以防止依賴繼承屬性的工作流程損壞。請聯絡客戶服務以尋求協助。"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 如果檔案夾缺少子節點，請分析該檔案夾。如果檔案夾數目在可控範圍內，請手動建立節點，否則請使用指令碼。
* 對於缺少原始轉譯的資產，請在移轉前重新上傳資產或予以刪除。
* 缺少子資產原始轉譯無需採取任何動作。
* 若是衝突節點，則應先解決這些節點，或者在移轉至AEM as a Cloud Service前可能需要刪除這些節點。
* 請聯繫我們的 [Experience Manager 客戶服務團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以釐清或解決問題。
