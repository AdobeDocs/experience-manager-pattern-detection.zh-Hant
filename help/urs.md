---
title: URS
description: 模式偵測器程式碼說明頁面
exl-id: 05c5b664-f034-42a2-918b-07772c8d480f
source-git-commit: 3e14d73acbe480dd861f492c24f67ffc37b1090d
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 0%

---

# URS {#urs}

不支援的儲存庫結構

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urs_overview"
>title="不支援的儲存庫結構"
>abstract="URS可識別不支援的儲存庫結構和節點特性。 這會顯示資訊，以避免AEM產品代碼和客戶代碼之間的衝突、從/etc重組到存放庫中的其他資料夾等。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/restructuring/repository-restructuring.html" text="存放庫重組"

## 背景 {#background}

`URS` 識別不支援的儲存庫結構和節點特性。 自AEM 6.4起，已提供重新調整存放庫內容的准則。 透過清楚定義AEM產品代碼和客戶代碼的階層，並避免兩者間產生衝突，內容會重新組織為退出 `/etc` 儲存庫中的其他資料夾，請遵循下列高階規則：

* AEM產品代碼將一律放置於 `/libs`，自訂程式碼不可覆寫。
* 自訂程式碼應放置在 `/apps`, `/content` 和 `/conf`.
* AEMas a Cloud Service不支援長節點名稱（>150位元組）。
* 強烈建議您遵循這些准則，以便AEMas a Cloud Service。

子類型用於識別應解決的特定儲存庫問題類型：
* `clientlibs.location`:參考的客戶端庫 `/etc` 路徑。
* `file.location`:檔案 `/etc` 自安裝以來已修改。
* `node.location`:底下的節點 `/etc` 自安裝以來已修改。
* `workflow.location`:工作流模型或啟動器 `/etc/workflow`.
* `package.structure`:包含可變內容和不可變內容的包。
* `node.name.length`:長度不受支援的節點名。
* `node.size`:大小不受支援的節點。

## 可能的影響和風險 {#implications-and-risks}

* 依賴較舊路徑的自訂程式碼可能會造成不適當的行為，並影響產品功能。
* 同時包含可變內容和不可變內容的軟體包在部署期間很可能導致問題。

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urs_guidance"
>title="實施指南"
>abstract="最佳實務是檢閱您的程式碼專案，確保其遵守AEM專案結構准則，並避免程式碼依賴較舊/不受支援的存放庫路徑，而這些路徑可能會造成AEMas a Cloud Service中不適當的行為。 請洽詢Adobe支援以取得說明和說明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html" text="AEM專案結構指引"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 請參閱 [存放庫重組](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/restructuring/repository-restructuring.html) 以取得準備AEMas a Cloud Service的指引。
* 另請參閱 [AEM專案結構](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html) 以進一步了解存放庫的可變和不可變區域。
* 請聯繫我們的 [AEM支援團隊](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) 以取得澄清或處理關注。
* 善用 [Repository Modernizer](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/repo-modernizer.html#refactoring-tools) 將內容和程式碼分離為獨立套件，以與為Adobe Experience Manager as a Cloud Service定義的專案結構相容，借此重新建構現有的專案套件。
