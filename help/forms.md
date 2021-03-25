---
title: 表單
description: 模式偵測器程式碼說明頁面
translation-type: tm+mt
source-git-commit: 9a02482d023ce1a6cbbff24b8e6509c91ddd2a6b
workflow-type: tm+mt
source-wordcount: '1136'
ht-degree: 0%

---


# [!DNL FORMS] {#form}

[!DNL Adobe Experience Manager Forms]

## 背景 {#background}

`FORMS` 識別與從遷移到遷移 [!DNL Adobe Experience Manager Forms] 的 [!DNL Adobe Experience Manager Form]潛在問題 [!DNL Cloud Service]。移轉至[!DNL Cloud Service]之前，請先解決這些問題。

下列子類型可協助您識別不同類型的問題：

* `modified.feature`:這些功能、資產或API已更新或修改以供Cloud Service。遷移到Cloud Service之前，請運行遷移實用程式以使這些功能和資產與Cloud Service相容。
* `unavailable.feature`:您的環境具有無法使用或從Cloud Service中移除的功能和資產。請勿將這些功能或資產移轉至Cloud Service環境。
* `unsupported.feature`:您的環境使用一些尚未支援的Cloud Service功能。請勿將這些功能或資產移轉至Cloud Service環境。 如需功能可用性的詳細資訊，請參閱每月發行說明。
* `unsupported.api`:您的Cloud Service有部分API尚未支援。移轉至Cloud Service前，請停用、取代或移除程式碼中的這些API。 如需功能可用性的詳細資訊，請參閱每月發行說明。

請參閱[可能的含義和風險](#implications-and-risks)和[可能的解決方案](#solutions)部分，瞭解有關更換和使某些功能和API與Cloud Service相容所需執行的其他操作的資訊

## 可能的影響和風險{#implications-and-risks}

移轉至[!DNL Adobe Experience Manager Forms as a Cloud Service]之前，請解決下列問題。 當下列含義和風險未解決時，某些功能在Cloud Service環境中無法如預期般運作。

* 規則編輯器功能的代碼編輯器功能不可用。 (CODE_EDITOR)

* 預設情況下，電子郵件支援（SMTP埠）被禁用。 (EMAIL_SERVICE_CONFIGURATION)

* **[!UICONTROL 電子郵件PDF]**&#x200B;提交動作不可用。(EMAIL_PDF_SUBMIT_ACTION)

* 尚未支援基於XFA的自適應Forms。 (XFA_BASED_FORM、XDP_BASED_FORM)

* 表單提交時會立即叫用「提交動作」，而不是等待所有簽署者完成簽署。 因此，傳送給簽署者的Adobe Sign合約PDF不適用於「提交動作」使用或處理。 (FORM_SIGN_INTEGRATION)

* 「簽名」步驟不可用。 (SIGNATURE_STEP)

* 驗證步驟不可用。 (VERIFY_STEP)

* 尚未提供Forms門戶功能和&#x200B;**[!UICONTROL Forms門戶提交操作]**。 (FORMS._PORTAL_SUBMISSION,FORMS._PORTAL, DRAFT_AUTO_SAVE, DRAFT_SAVE)

* **[!UICONTROL 提交至Forms Workflow]**&#x200B;提交操作不可用。 在[!DNL AEM 6.5 Forms]和舊版中，「提交動作」可用來將最適化表單資料提交至舊版[!DNL AEM Forms on JEE]工作流程和LiveCycle Workflow。 (LC_WORKFLOW_SUBMISSION)

* 無法使用「互動式通訊」功能。  (FP_PROFILE_INTERACTIVE_COMMUNICATIONS)。

* **[!UICONTROL 目前不]** 支援另 **[!UICONTROL 存]** 為草稿和自動儲存最適化表單功能。(DRAFT_AUTO_SAVE,DRAFT_SAVE)

* 中繼資料accordion無法使用。 (METADATA_ACCORDION_FORM_CONTAINER)

* 依預設，CAPTCHA元件現在使用Google reCAPTCHA服務來驗證CAPTCHA。 不建議使用Adobe Experience Manager驗證CAPTCHA的選項。 (FORMS_CAPTCHA)

* [!DNL AEM Forms] 應用程式無法 [!DNL Cloud Services]使用。(AEM_FORMS._APP)

* [「工](https://experienceleague.adobe.com/docs/experience-manager-65/forms/install-aem-forms/osgi-installation/install-configure-document-services.html?lang=en#deployment-topology) 作流程」中不提供「檔案服務」AEM步驟。(WORKFLOW_DOCSERVICES)

## 可能的解決方案{#solutions}

* 使用移轉公用程式，將您環境上的所有規則指令碼轉換為可重複使用的函式。 您可以搭配使用可重複使用的函式和視覺化規則編輯器，以繼續取得使用規則指令碼取得的結果。 (CODE_EDITOR)

* 請與支援團隊聯繫，為您的環境啟用電子郵件（開啟SMTP埠）功能。 預設情況下，僅啟用傳出HTTP和HTTPS連接。 （EMAIL_SERVICE_CONFIGURATION，電子郵件步驟）

* 使用&#x200B;**[!UICONTROL Email]** Submit Action而非&#x200B;**[!UICONTROL Email PDF]**。 **[!UICONTROL Email]** Submit Action（電子郵件提交操作）提供了發送附件和附加記錄文檔(DoR)的選項。 (EMAIL_PDF_SUBMIT_ACTION)

* 已提交的資料包含Adobe Sign合約ID。 如有需要，您可以使用簽署合約ID來擷取簽署合約PDF。  (FORM_SIGN_INTEGRATION)

* 從現有的最適化表單移除簽名步驟。 設定您的最適化表單，使用[瀏覽器內簽署體驗](https://medium.com/adobetech/using-adobe-sign-to-e-sign-an-adaptive-form-heres-the-best-way-to-do-it-dc3e15f9b684)。 它顯示Adobe Sign同意在瀏覽器內簽署提交最適化表單的協定。 瀏覽器內簽署體驗有助於提供更快速的簽署體驗，並為簽署者節省時間。 (SIGNATURE_STEP)

* 在將這些表單移動到[!DNL Cloud Service]環境之前，請先從現有的自適應Forms中刪除驗證步驟。 (VERIFY_STEP)

* 修改您現有的自適應表單，使用[提交到REST端點](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#submit-to-rest-endpoint)、[發送電子郵件](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#send-email)、[使用表單資料模型](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#submit-using-form-data-model)和[調用工作流](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#invoke-an-aem-workflow)提交操作。 Forms門戶網站和Forms門戶網站提交操作尚未推出。 如需功能可用性的詳細資訊，請參閱每月發行說明。 (FORMS._PORTAL_SUBMISSION,FORMS._PORTAL)

* 您可以開發AEM「工作流」並修改現有的最適化表單，以使用[AEM Workflow](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#invoke-an-aem-workflow) Submit Action將資料傳送至AEMWorkflow，而不使用&#x200B;**[!UICONTROL Submit toForms Workflow]** Submit Action。 您可以開發自訂「提交動作」，將資料、附件或記錄檔案(DoR)傳送至LiveCycle程式，而不是使用「提交至Forms Workflow」[!UICONTROL 。 ](LC_WORKFLOW_SUBMISSION)

* 如需互動式通訊功能可用性的詳細資訊，請參閱每月發行說明。 在功能不可用之前，請勿將您的互動式通訊、信件和相關字典移轉至Cloud Service環境。 (FP_PROFILE_INTERACTIVE_COMMUNICATIONS)

* 在將草稿&#x200B;]**和**[!UICONTROL &#x200B;自動保存&#x200B;]**選項遷移到Cloud Service之前，請禁用自適應Forms中的**[!UICONTROL &#x200B;另存為草稿和啟用自動保存選項。 在為Cloud Service發佈Forms門戶功能後，您可以啟用這些選項。 如需功能可用性的詳細資訊，請參閱每月發行說明。 (DRAFT_AUTO_SAVE,DRAFT_SAVE)

* 中繼資料accordion沒有替代項目。 將表單移除，再移轉至Cloud Service。(METADATA_ACCORDION_FORM_CONTAINER)

* 使用Google reCaptcha，而非Adobe Experience Manager提供的CAPTCHA服務。 (FORMS_CAPTCHA)

* 適應性Forms提供自適應設計。 這些表單會根據基礎裝置改變外觀、設計和互動功能。 您可以繼續在行動裝置上使用Adaptive Jovan。 如需[!DNL AEM Forms]應用程式可用性的詳細資訊，請參閱每月發行說明。 (AEM_FORMS._APP)

* 請勿移轉使用「文AEM件服務工作流程」步驟的「工作流程」模型。 此外，在遷移表單之前，請勿遷移或更新將用戶資料發送到使用「文檔服務」工作流步驟的「工作流模型」的Adaptive Forms，或將「提交操作」更改為[支援的](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html)。 (WORKFLOW_DOCSERVICES)

* 不提供對基於XFA的自適應Forms的支援。 如果您打算使用基於XFA的Adaptive Forms，請與Adobe支援部門聯繫，以瞭解您的使用案例和具體要求。((XFA_BASED_FORM、XDP_BASED_FORM)

請聯絡[Adobe支援](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
