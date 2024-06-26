---
title: FORM
description: 模式偵測器程式碼說明頁面。
exl-id: ac28760b-b0ab-4082-b7ce-730cddc4ad83
source-git-commit: 0d693e3ccadc81b59852914f115bb2fa2ea166b0
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 100%

---

# [!DNL FORMS] {#form}

[!DNL Adobe Experience Manager Forms]

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_forms_overview"
>title="FORMS"
>abstract="FORMS 程式碼會識別從 AEM (Adobe Experience Manager) Forms 移轉至 AEM Forms as a Cloud Service 相關的可能問題。請檢閱相關的可能影響和風險，並在移轉至 Cloud Service 之前解決這些問題。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-manager-pattern-detection/table-of-contents/forms#implications-and-risks" text="可能的影響和風險"

`FORMS` 會識別從 [!DNL Adobe Experience Manager Forms] 移轉至 [!DNL Adobe Experience Manager Forms]s as a [!DNL Cloud Service] 相關的可能問題。請在移轉至 [!DNL Cloud Service] 之前解決這些問題。

下列子類型可協助您識別不同類型的問題：

* `modified.feature`：這些功能、資產或 API 已針對 Cloud Service 進行了更新或修改。在移轉至 Cloud Service 之前，請執行移轉公用程式，讓這些功能和資產相容於 Cloud Service。
* `unavailable.feature`：您的環境有 Cloud Service 中無法使用或已移除的功能和資產。請勿將這類功能或資產移轉至 Cloud Service 環境。
* `unsupported.feature`：您的環境使用了一些 Cloud Service 尚未支援的功能。請勿將這類功能或資產移轉至 Cloud Service 環境。請查看每月發行說明，以了解功能可用性相關資訊。
* `unsupported.api`：您的環境有一些 Cloud Service 尚未支援的 API。在移轉至 Cloud Service 之前，請在您的程式碼中停用、取代或移除這些 API。請查看每月發行說明，以了解功能可用性相關資訊。

請參閱[可能的影響和風險](#implications-and-risks)和[可能的解決方案](#solutions)小節，以了解讓一些功能和 API 相容於 Cloud Service 的取代和其他必要動作相關資訊。

## 可能的影響和風險 {#implications-and-risks}

請在移轉至 [!DNL Adobe Experience Manager Forms as a Cloud Service] 之前解決下列問題。未解決下列影響和風險時，部分功能在 Cloud Service 環境中無法如預期運作。

* 規則編輯器功能的程式碼編輯器功能無法使用。(CODE_EDITOR)

* 電子郵件支援 (SMTP 連接埠) 預設為停用。(EMAIL_SERVICE_CONFIGURATION)

* **[!UICONTROL 電子郵件 PDF]** 提交動作無法使用。(EMAIL_PDF_SUBMIT_ACTION)

* 不支援 XFA 型最適化表單。(XFA_BASED_FORM, XDP_BASED_FORM)

* 在表單提交時就會立即叫用提交動作，而不會等候所有簽署者完成簽署。因此傳送給簽署者的 Adobe Sign 合約 PDF 不可供提交動作使用或處理。(FORM_SIGN_INTEGRATION)

* 簽名步驟無法使用。(SIGNATURE_STEP)

* 驗證步驟無法使用。(VERIFY_STEP)

* **[!UICONTROL 提交至 Forms Workflow]** 提交動作無法使用。在 AEM 6.5 Forms 和舊版，提交動作用於將最適化表單資料提交至舊版 AEM Forms on JEE Workflow 和 LiveCycle Workflow。(LC_WORKFLOW_SUBMISSION)

* 互動式通訊功能無法使用。(FP_PROFILE_INTERACTIVE_COMMUNICATIONS)。

* 中繼資料 Accordion 無法使用。(METADATA_ACCORDION_FORM_CONTAINER)

* 驗證碼元件現在預設會使用 Google reCAPTCHA 服務來進行驗證碼驗證。使用 Adobe Experience Manager 進行驗證碼驗證的選項已棄用。(FORMS_CAPTCHA)

* [!DNL AEM Forms] 應用程式不可用於 [!DNL Cloud Services]。(AEM_FORMS_APP)

* [文件服務](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-65/content/forms/install-aem-forms/osgi-installation/install-configure-document-services#deployment-topology)步驟不可用於 AEM Workflow。(WORKFLOW_DOCSERVICES)

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_forms_guidance"
>title="實施指導"
>abstract="透過 FORMS 程式碼公開的資訊，會提供讓一些功能和 API 相容於 Cloud Service 的取代和其他必要動作相關指導。請聯絡 Adobe 支援人員，取得協助或說明。"
>additional-url="https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支援"

* 使用移轉公用程式，將環境中的所有規則指令碼轉換為可重複使用的函數。您可以在視覺規則編輯器中使用可重複使用的函數，繼續取得與規則指令碼相同的結果。(CODE_EDITOR)

* 請聯絡支援團隊，為您的環境啟用電子郵件 (開啟 SMTP 連接埠) 功能。預設只會啟用傳出 HTTP 和 HTTPS 連線。(EMAIL_SERVICE_CONFIGURATION, Email step)

* 請使用&#x200B;**[!UICONTROL 電子郵件]**&#x200B;提交動作而非&#x200B;**[!UICONTROL 電子郵件 PDF]**。**[!UICONTROL 電子郵件]**&#x200B;提交動作會提供傳送附件和將記錄文件 (DoR) 附加於電子郵件的選項。(EMAIL_PDF_SUBMIT_ACTION)

* 提交的資料包含 Adobe Sign 合約 ID。必要時，您可以使用 Sign 合約 ID 來擷取 Sign 合約 PDF。(FORM_SIGN_INTEGRATION)

* 從現有的最適化表單移除簽名步驟。設定最適化表單以使用[瀏覽器內簽名體驗](https://blog.developer.adobe.com/using-adobe-sign-to-e-sign-an-adaptive-form-heres-the-best-way-to-do-it-dc3e15f9b684)。它會顯示 Adobe Sign 合約，以便在提交最適化表單時於瀏覽器中簽署合約。瀏覽器內簽名體驗有助於提供更快的簽名體驗，為簽署者節省寶貴時間。(SIGNATURE_STEP)

* 將調適型表單移至 [!DNL Cloud Service] 環境之前，請從現有的調適型表單移除驗證步驟。(VERIFY_STEP)

* 您可以編輯現有的調適型表單，以使用[提交至 REST 端點](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-submit-actions-and-metadata-submission/configuring-submit-actions#submit-to-rest-endpoint)、[傳送電子郵件](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-submit-actions-and-metadata-submission/configuring-submit-actions#send-email)、[使用表單資料模型提交](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-submit-actions-and-metadata-submission/configuring-submit-actions#submit-using-form-data-model)和[叫用 AEM 工作流程](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-submit-actions-and-metadata-submission/configuring-submit-actions#invoke-an-aem-workflow)提交動作。

* 您可以開發 AEM 工作流程，並編輯現有的調適型表單，以使用 [AEM 工作流程](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-submit-actions-and-metadata-submission/configuring-submit-actions#invoke-an-aem-workflow)提交動作將資料傳送至 AEM 工作流程，而不使用&#x200B;**[!UICONTROL 提交至 Forms Workflow]** 提交動作。您可以開發自訂提交動作，將資料、附件或記錄文件 (DoR) 傳送至 LiveCycle 程序，而不使用[!UICONTROL 提交至 Forms Workflow]。(LC_WORKFLOW_SUBMISSION)

* 請查看每月發行說明，以了解互動式通訊功能可用性相關資訊。請勿將互動式通訊、郵件和相關字典移轉至 Cloud Service 環境 (該功能尚不可使用)。(FP_PROFILE_INTERACTIVE_COMMUNICATIONS)

* 中繼資料 Accordion 沒有替代項目。將表單移轉至 Cloud Service 之前，請將它從表單中移除。(METADATA_ACCORDION_FORM_CONTAINER)

* 請使用 Google reCAPTCHA 服務，而不使用 Adobe Experience Manager 所提供的驗證碼服務。(FORMS_CAPTCHA)

* 請勿移轉使用文件服務工作流程步驟的 AEM 工作流程模型。此外，如果調適型表單將使用者資料傳送至使用文件服務工作流程步驟的工作流程模型，請勿移轉或更新這些調適型表單，或在移轉表單之前先將 `Submit Action` 變更為[支援的提交動作](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-submit-actions-and-metadata-submission/configuring-submit-actions)。(WORKFLOW_DOCSERVICES)

* 最適化表單提供回應式設計。這些表單會根據基礎裝置變更外觀、設計和互動。您可以在行動裝置上繼續使用最適化表單。請查看每月發行說明，以了解 [!DNL AEM Forms] 應用程式可用性相關資訊。(AEM_FORMS_APP)

* 未提供開箱即用的 XFA 型最適化表單支援。如果您打算使用 XFA 型最適化表單，請聯絡 Adobe 支援並附上使用案例和特定要求的詳細資料。(XFA_BASED_FORM, XDP_BASED_FORM)

請聯絡 [Adobe 支援團隊](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)以釐清或解決問題。
