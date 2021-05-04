---
title: URS
description: 模式偵測器程式碼說明頁面
exl-id: 05c5b664-f034-42a2-918b-07772c8d480f
translation-type: tm+mt
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 0%

---

# URS {#urs}

不支援的儲存庫結構

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urs_overview"
>title="不支援的儲存庫結構"
>abstract="URS標識不支援的儲存庫結構。 這樣可以呈現資訊，以避免產AEM品代碼和客戶代碼之間的衝突，將內容從/etc重構到儲存庫中的其他資料夾等。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/restructuring/repository-restructuring.html" text="儲存庫重組"

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

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urs_guidance"
>title="實施指南"
>abstract="最佳做法是審查代碼項目，確保它遵守項目結AEM構指導原則，並避免代碼依賴較舊／不受支援的儲存庫路徑，這些路徑可能會導致Cloud Service中不AEM希望的行為。 聯絡Adobe支援以取得說明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html" text="項AEM目結構指南"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 有關準備作為Cloud Service的指導，請參閱[Repository Restructing](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/restructuring/repository-restructuring.html)AEM。
* 另請參閱[AEM Project Structure](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html)以進一步瞭解儲存庫的可變和不可變區域。
* 請洽詢我們的[AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
* 利用[Repository Modernizer](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/repo-modernizer.html#refactoring-tools)將內容和代碼分離為獨立的包，以便與為Adobe Experience Manager定義的項目結構(作為Cloud Service)相容，從而重構現有項目包。
