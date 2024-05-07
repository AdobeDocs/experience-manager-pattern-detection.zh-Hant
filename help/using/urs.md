---
title: URS
description: 模式偵測器程式碼說明頁面。
exl-id: 05c5b664-f034-42a2-918b-07772c8d480f
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: ht
source-wordcount: '377'
ht-degree: 100%

---

# URS {#urs}

不支援的存放庫結構

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urs_overview"
>title="不支援的存放庫結構"
>abstract="URS 會識別不支援的存放庫結構和節點特性案例。這會顯示下列相關資訊：避免 AEM 產品程式碼和客戶程式碼之間的衝突、/etc 中的內容重組到存放庫的其他檔案夾等等。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-65/content/implementing/deploying/restructuring/repository-restructuring" text="存放庫重組"

## 背景 {#background}

`URS` 會識別不支援的存放庫結構和節點特性案例。自 AEM 6.4 起已經提供存放庫內容重組的指導方針。透過明確界定 AEM 產品程式碼和客戶程式碼的階層，避免兩者之間的衝突，`/etc` 中的內容會重組到存放庫的其他檔案夾，遵守下列高階規則：

* AEM 產品程式碼永遠都會放在 `/libs` 中，自訂程式碼不可予以覆寫。
* 自訂程式碼應放在 `/apps`、`/content` 和 `/conf` 中。
* 對於 AEM as a Cloud Service，強烈建議遵循這些指導方針。

子類型用於識別應解決的特定存放庫問題類型：

* `clientlibs.location`：依路徑參考 `/etc` 的用戶端程式庫。
* `file.location`：`/etc` 下的檔案在安裝後已修改。
* `node.location`：`/etc` 下的節點在安裝後已修改。
* `workflow.location`：`/etc/workflow` 下的工作流程模型或啟動器。
* `package.structure`：包含可變和不可變內容的套件。
* `node.size`：大小不受支援的節點。

## 可能的影響和風險 {#implications-and-risks}

* 依賴較舊路徑的自訂程式碼可能會導致不良行為並影響產品功能。
* 包含可變和不可變內容的套件在部署期間可能會造成問題。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urs_guidance"
>title="實施指導"
>abstract="最佳實務是檢閱您的程式碼專案。確保它遵守 AEM 專案結構準則，避免依賴較舊/不受支援之存放庫路徑的程式碼 (這可能會在 AEM as a Cloud Service 中導致不良行為)。請聯絡 Adobe 支援人員，取得協助或說明。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure" text="AEM 專案結構指導方針"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 請參閱[存放庫重組](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-65/content/implementing/deploying/restructuring/repository-restructuring)以取得為 AEM as a Cloud Service 做準備的指導。
* 也請參閱 [AEM 專案結構](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure)以進一步了解存放庫的可變和不可變區域。
* 請聯絡 [AEM 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以釐清或解決問題。
* 使用 [Repository Modernizer](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/repo-modernizer#refactoring-tools) 將內容和程式碼分割為獨立套件，以與 Adobe Experience Manager as a Cloud Service 定義的專案結構相容，藉此重組現有的專案套件。
