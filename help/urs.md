---
title: URS
description: 模式偵測器程式碼說明頁面
translation-type: tm+mt
source-git-commit: 5a83dd8d08da974a5d775032b8dbea2593be9d15
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 0%

---


# URS {#urs}

不支援的儲存庫結構

## 背景 {#background}

`URS` 標識不支援的儲存庫結構的案例。從6.AEM4開始，已為資料庫內容的重組提供了准則。 通過明確定義產AEM品代碼和客戶代碼的層次並避免它們之間的衝突，內容將從`/etc`重組到儲存庫中的其他資料夾，遵守以下高級規則：

* 產AEM品代碼將始終放置在`/libs`中，這不能被自定義代碼覆蓋自定義代碼應放置在`/apps`、`/content`和`/conf`中。
* 強烈建議遵守這些准則作為AEMCloud Service。

子類型用於標識應解決的特定類型的儲存庫問題：
* `clientlibs.location`:參照路徑的客 `/etc` 戶端庫。
* `file.location`:安裝後 `/etc` 已修改的檔案。
* `node.location`:安裝後 `/etc` 已修改的節點。
* `workflow.location`:下面的工作流模型或啟動程式 `/etc/workflow`。
* `package.structure`:包含可變內容和不可變內容的包。

## 可能的影響和風險{#implications-and-risks}

* 依賴舊路徑的自訂程式碼可能會造成不想要的行為，並影響產品功能。
* 同時包含可變內容和不可變內容的軟體包在部署過程中可能會出現問題。

## 可能的解決方案{#solutions}

* 有關準備作為Cloud Service的指導，請參閱[Repository Restructing](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/restructuring/repository-restructuring.html)AEM。
* 另請參閱[AEM Project Structure](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html)以進一步瞭解儲存庫的可變和不可變區域。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
* 利用[Repository Modernizer](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/repo-modernizer.html#refactoring-tools)將內容和代碼分離為獨立的包，以便與為Adobe Experience Manager定義的項目結構(作為Cloud Service)相容，從而重構現有項目包。