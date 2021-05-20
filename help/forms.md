---
title: 表單
description: 模式偵測器程式碼說明頁面
exl-id: ac28760b-b0ab-4082-b7ce-730cddc4ad83
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '1228'
ht-degree: 0%

---

# [!DNL FORMS] {#form}

[!DNL Adobe Experience Manager Forms]

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_forms_overview"
>title="Forms。"
>abstract="Forms。程式碼可識別從Adobe Experience Manager Forms移轉至Adobe Experience Manager Forms做為Cloud Service的潛在問題。 在移轉至Cloud Service之前，先審查可能的影響和相關風險，並解決這些問題。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-pattern-detection/table-of-contents/forms.html#implications-and-risks" text="可能的影響和風險"

`FORMS` 識別從移轉至的 [!DNL Adobe Experience Manager Forms] 潛 [!DNL Adobe Experience Manager Form]在問 [!DNL Cloud Service]題。在移轉至[!DNL Cloud Service]之前解決這些問題。

下列子類型可協助您識別不同類型的問題：

* `modified.feature`:這些功能、資產或API已更新或修改，以供Cloud Service。移轉至Cloud Service之前，請執行移轉公用程式，讓這些功能和資產與Cloud Service相容。
* `unavailable.feature`:您的環境有無法使用或從Cloud Service中移除的功能和資產。請勿將這類功能或資產移轉至Cloud Service環境。
* `unsupported.feature`:您的環境使用一些Cloud Service尚未支援的功能。請勿將這類功能或資產移轉至Cloud Service環境。 如需功能可用性的相關資訊，請參閱每月發行說明。
* `unsupported.api`:您的Cloud Service有部分API但尚不支援。移轉至Cloud Service之前，請停用、取代或從程式碼中移除這些API。 如需功能可用性的相關資訊，請參閱每月發行說明。

請參閱[可能的影響和風險](#implications-and-risks)和[可能的解決方案](#solutions)部分，以了解有關替換和使某些功能和API與Cloud Service相容所需的其他操作的資訊

## 可能的影響和風險{#implications-and-risks}

移轉至[!DNL Adobe Experience Manager Forms as a Cloud Service]之前，請先解決下列問題。 當未解決下列含意和風險時，某些功能在Cloud Service環境中無法如預期般運作。

* 規則編輯器功能的代碼編輯器功能無法使用。 (CODE_EDITOR)

* 預設情況下禁用電子郵件支援（SMTP埠）。 (EMAIL_SERVICE_CONFIGURATION)

* 無法使用&#x200B;**[!UICONTROL 電子郵件PDF]**&#x200B;提交動作。(EMAIL_PDF_SUBMIT_ACTION)

* 尚不支援以XFA為基礎的適用性Forms。 (XFA_BASED_FORM、XDP_BASED_FORM)

* 提交表單時會立即叫用「提交動作」，而非等待所有簽署者完成簽署。 因此，傳送給簽署者的Adobe Sign合約PDF無法供「提交動作」使用或處理。 (FORM_SIGN_INTEGRATION)

* 「簽名」步驟不可用。 (SIGNATURE_STEP)

* 驗證步驟不可用。 (VERIFY_STEP)

* 尚未提供Forms Portal功能和&#x200B;**[!UICONTROL Forms Portal提交動作]**。 (FORMS._PORTAL_SUBMISSION、FORMS._PORTAL、DRAFT_AUTO_SAVE、DRAFT_SAVE)

* **[!UICONTROL 提交至Forms Workflow]**&#x200B;提交操作不可用。 在[!DNL AEM 6.5 Forms]及舊版中，「提交動作」可用來將最適化表單資料提交至舊版[!DNL AEM Forms on JEE]工作流程和LiveCycle Workflow。 (LC_WORKFLOW_SUBMISSION)

* 無法使用互動式通信功能。  (FP_PROFILE_INTERACTIVE_COMMUNICATIONS)。

* **[!UICONTROL 另存為草]** 稿和自 **[!UICONTROL 動]** 儲存最適化表單功能目前不受支援。(DRAFT_AUTO_SAVE, DRAFT_SAVE)

* 中繼資料折疊式功能表無法使用。 (METADATA_ACCORDION_FORM_CONTAINER)

* 現在，CAPTCHA元件預設會使用Google reCAPTCHA服務來驗證CAPTCHA。 不建議使用Adobe Experience Manager來驗證驗證驗證碼。 (FORMS._CAPTCHA)

* [!DNL AEM Forms] 應用程式無法 [!DNL Cloud Services]使用。(AEM_FORMS._APP)

* [檔案](https://experienceleague.adobe.com/docs/experience-manager-65/forms/install-aem-forms/osgi-installation/install-configure-document-services.html?lang=en#deployment-topology) 服務步驟在AEM工作流程中無法使用。(WORKFLOW_DOCSERVICES)

## 可能的解決方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_forms_guidance"
>title="實施指南"
>abstract="通過FORMS公開的資訊。代碼可提供替換和使某些功能和API與Cloud Service相容所需的其他操作的指導。 請洽詢Adobe支援以取得說明和說明"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支援"

* 使用遷移實用程式將環境中的所有規則指令碼轉換為可重複使用的函式。 您可以使用可重複使用的函式搭配可視化規則編輯器來繼續取得使用規則指令碼取得的結果。 (CODE_EDITOR)

* 請連絡支援團隊，為您的環境啟用電子郵件（開啟SMTP埠）功能。 預設情況下，僅啟用傳出的HTTP和HTTPS連線。 （EMAIL_SERVICE_CONFIGURATION，電子郵件步驟）

* 使用&#x200B;**[!UICONTROL Email]**&#x200B;提交動作，而非&#x200B;**[!UICONTROL Email PDF]**。 **[!UICONTROL Email]** Submit Action提供了發送附件和附加記錄文檔(DoR)和電子郵件的選項。 (EMAIL_PDF_SUBMIT_ACTION)

* 已提交的資料包含Adobe Sign合約ID。 您可以視需要使用簽署協定ID來擷取簽署協定PDF。  (FORM_SIGN_INTEGRATION)

* 從現有的適用性表單中移除「簽章」步驟。 設定最適化表單以使用[瀏覽器內簽署體驗](https://medium.com/adobetech/using-adobe-sign-to-e-sign-an-adaptive-form-heres-the-best-way-to-do-it-dc3e15f9b684)。 它會顯示Adobe Sign同意在提交最適化表單的瀏覽器中籤署合約。 瀏覽器內簽署體驗有助於提供更快速的簽署體驗，並為簽署者節省時間。 (SIGNATURE_STEP)

* 將表單移至[!DNL Cloud Service]環境之前，請先移除現有適用性Forms中的驗證步驟。 (VERIFY_STEP)

* 修改您現有的最適化表單，使用[提交至REST端點](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#submit-to-rest-endpoint)、[傳送電子郵件](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#send-email)、[使用表單資料模型](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#submit-using-form-data-model)提交，以及[叫用AEM工作流程](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#invoke-an-aem-workflow)提交動作。 Forms Portal和Forms Portal提交動作尚未推出。 如需功能可用性的相關資訊，請參閱每月發行說明。 (FORMS._PORTAL_SUBMISSION, FORMS._PORTAL)

* 您可以開發AEM Workflow並修改現有的最適化表單，以使用[AEM Workflow](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#invoke-an-aem-workflow)提交動作將資料傳送至AEM Workflow，而非使用&#x200B;**[!UICONTROL 提交至Forms Workflow]**&#x200B;提交動作。 您可以開發自定義「提交操作」，將資料、附件或記錄文檔(DoR)發送到LiveCycle進程，而不是使用[!UICONTROL 提交到Forms Workflow]。 (LC_WORKFLOW_SUBMISSION)

* 如需互動式通訊功能可用性的詳細資訊，請參閱每月發行說明。 在功能無法使用之前，請勿將互動式通訊、信函和相關字典移轉至Cloud Service環境。 (FP_PROFILE_INTERACTIVE_COMMUNICATIONS)

* 在移轉至Cloud Service之前，停用適用性Forms中的&#x200B;**[!UICONTROL 另存為草稿]**&#x200B;和&#x200B;**[!UICONTROL 啟用自動儲存]**&#x200B;選項。 為Cloud Service發行Forms Portal功能後，您就可以啟用這些選項。 如需功能可用性的相關資訊，請參閱每月發行說明。 (DRAFT_AUTO_SAVE, DRAFT_SAVE)

* 中繼資料折疊式功能表沒有取代。 將表單移除，再移轉至Cloud Service。(METADATA_ACCORDION_FORM_CONTAINER)

* 使用Google reCaptcha，而非Adobe Experience Manager提供的CAPTCHA服務。 (FORMS._CAPTCHA)

* 適用性Forms提供回應式設計。 這些表單會根據基礎裝置改變外觀、設計和互動功能。 您可以在行動裝置上繼續使用適用性Forms。 如需[!DNL AEM Forms]應用程式可用性的詳細資訊，請參閱每月發行說明。 (AEM_FORMS._APP)

* 請勿移轉使用「檔案服務工作流程」步驟的AEM工作流程模型。 此外，請勿移轉或更新將使用者資料傳送至使用「檔案服務工作流程」步驟的「工作流程模型」的Adaptive Forms，或在移轉表單前將「提交動作」變更為[支援的一個](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html)。 (WORKFLOW_DOCSERVICES)

* 不提供以XFA為基礎的適用性Forms的立即可用支援。 如果您想使用XFA型適用性Forms，請聯絡Adobe支援，提供您使用案例和特定需求的詳細資訊。(XFA_BASED_FORM、XDP_BASED_FORM)

請洽詢[Adobe支援](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑問。
