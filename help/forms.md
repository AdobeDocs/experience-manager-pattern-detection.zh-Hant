---
title: Forms。
description: 模式偵測器程式碼說明頁面
translation-type: tm+mt
source-git-commit: a6ba6e93c89644160650882ecbf17028bec35068
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 0%

---


# [!DNL FORMS] {#forms}

[!DNL Adobe Experience Manager Forms]

## 背景 {#background}

`FORMS` 確定作為Cloud Service從Adobe Experience Manager Forms遷移到Adobe Experience Manager Forms的潛在問題。在移轉至Cloud Service之前解決這些問題。

下列子類型可協助您識別不同類型的問題：

* `modified.feature`:這些功能、資產或API已更新或修改以供Cloud Service。遷移到Cloud Service之前，請運行遷移實用程式以使這些功能和資產與Cloud Service相容。
* `unavailable.feature`:您的環境具有無法使用或從Cloud Service中移除的功能和資產。請勿將這些功能或資產移轉至Cloud Service環境。
* `unsupported.feature`:您的環境使用一些尚未支援的Cloud Service功能。請勿將這些功能或資產移轉至Cloud Service環境。 請留意每月的版本注意事項，以瞭解功能的可用性。
* `unsupported.api`:您的Cloud Service有部分API尚未支援。移轉至Cloud Service前，請停用、取代或移除程式碼中的這些API。 請留意每月的版本注意事項，以瞭解功能的可用性。

請參閱[可能的含義和風險](#implications-and-risks)和[可能的解決方案](#solutions)部分，瞭解有關更換和使某些功能和API與Cloud Service相容所需執行的其他操作的資訊

## 可能的影響和風險{#implications-and-risks}

在移轉至Adobe Experience Manager Forms作為Cloud Service之前，先解決以下問題。 當下列含義和風險未解決時，某些功能在Cloud Service環境中無法如預期般運作。

* 規則編輯器功能的代碼編輯器功能不可用。 (CODE_EDITOR)

* 預設情況下，電子郵件支援（SMTP埠）被禁用。 (EMAIL_SERVICE_CONFIGURATION)

* **[!UICONTROL 電子郵件PDF]**&#x200B;提交動作不可用。(EMAIL_PDF_SUBMIT_ACTION)

* 目前尚未支援以XDP為基礎的調適性表單。 (XDP_BASED_FORM)

* 提交表格時會立即叫用提交動作，而不是等待所有簽署者完成簽署。 因此，最適化表單簽名檔案(Adobe Sign合約PDF傳送給簽署者)無法提交要使用或處理的動作。 (FORM_SIGN_INTEGRATION)

* 「簽名」步驟不可用。 (SIGNATURE_STEP)

* 驗證步驟不可用。 (VERIFY_STEP)

* Forms門戶網站功能和&#x200B;**[!UICONTROL Forms門戶網站提交操作]**&#x200B;不可用。 您無法使用Forms入口網站來列出表單、儲存草稿或顯示已提交的表單。 您不能將(使用&#x200B;**[!UICONTROL Forms門戶提交操作]**)提交到適應性表單的資料發送到Forms門戶。 [!UICONTROL 目前不] 支援另 [!UICONTROL 存] 為草稿和自動儲存最適化表單功能。(FORMS._PORTAL_SUBMISSION,FORMS._PORTAL, DRAFT_AUTO_SAVE, DRAFT_SAVE)

* **[!UICONTROL 提交到Forms工作流]**&#x200B;提交操作不可用。 在AEM6.5Forms及舊版中，提交動作用於提交針對JEE工作流程和LiveCycle Workflow的適應性表單資料給舊版AEM Forms。 (LC_WORKFLOW_SUBMISSION)

* 無法使用「互動式通訊」功能。  (FP_PROFILE_INTERACTIVE_COMMUNICATIONS)。

* **[!UICONTROL 目前不]** 支援另 **[!UICONTROL 存]** 為草稿和自動儲存最適化表單功能。(DRAFT_AUTO_SAVE,DRAFT_SAVE)

* 中繼資料accordion無法使用。 (METADATA_ACCORDION_FORM_CONTAINER)

* 依預設，CAPTCHA元件現在使用Google reCAPTCHA服務來驗證CAPTCHA。 無法使用Adobe Experience Manager驗證驗證驗證驗證驗證碼的選項。 (FORMS_CAPTCHA)

## 可能的解決方案{#solutions}

* 使用移轉公用程式，將您環境上的所有規則指令碼轉換為可重複使用的函式。 您可以搭配使用可重複使用的函式和視覺化規則編輯器，以繼續取得使用規則指令碼取得的結果。 (CODE_EDITOR)

* 請與支援團隊聯繫，為您的環境啟用電子郵件（開啟SMTP埠）功能。 預設情況下，僅啟用傳出HTTP和HTTPS連接。 (EMAIL_SERVICE_CONFIGURATION)

* 使用&#x200B;**[!UICONTROL Email]**&#x200B;提交動作，而非&#x200B;**[!UICONTROL Email PDF]**。 **[!UICONTROL Email]**&#x200B;提交操作提供了發送附件和附加記錄文檔(DoR)的選項。 (EMAIL_PDF_SUBMIT_ACTION)

* 請勿將基於XDP的自適應表單遷移到Cloud Service環境。 請留意每月的版本注意事項，以瞭解功能的可用性。 (XDP_BASED_FORM)

* 已提交的資料包含簽署合約ID。 如有需要，您可以使用簽署合約ID來擷取簽署合約PDF。  (FORM_SIGN_INTEGRATION)

* 在同一視窗中，以「簽署最適化表單貼文提交」選項取代最適化表單中的「簽名」步驟。 它可協助您繼續提供[瀏覽器內簽署體驗](https://medium.com/adobetech/using-adobe-sign-to-e-sign-an-adaptive-form-heres-the-best-way-to-do-it-dc3e15f9b684)。 (SIGNATURE_STEP)

* 將現有的可調式表單移至Cloud Service環境之前，先移除驗證步驟。 (VERIFY_STEP)

* 除了&#x200B;**[!UICONTROL Forms門戶提交行動]**&#x200B;之外，別無他法。 一旦針對Cloud Service發佈了Forms門戶功能，您就可以使用此提交操作。 請留意每月的版本注意事項，以瞭解功能的可用性。 (FORMS._PORTAL_SUBMISSION,FORMS._PORTAL)

* 沒有替代的提交操作可提交至Forms工作流&#x200B;]**提交操作。**[!UICONTROL &#x200B;您可以開發自訂提交動作，將資料、附件或記錄檔案(DoR)傳送至LiveCycle程式。 (LC_WORKFLOW_SUBMISSION)

* 請勿將您的互動式通訊、信件和相關字典移轉至Cloud Service環境。 (FP_PROFILE_INTERACTIVE_COMMUNICATIONS)

* 在將最適化表單移轉至Cloud Service之前，停用最適化表單中的「另存為草稿&#x200B;]**」和「啟用自動儲存]**」選項。 **[!UICONTROL **[!UICONTROL &#x200B;在為Cloud Service發佈Forms門戶功能後，您可以啟用這些選項。 請留意每月的版本注意事項，以瞭解功能的可用性。 (DRAFT_AUTO_SAVE,DRAFT_SAVE)

* 中繼資料accordion沒有替代項目。 將表單移除，再移轉至Cloud Service。(METADATA_ACCORDION_FORM_CONTAINER)

* 使用Google reCaptcha，而非Adobe Experience Manager提供的CAPTCHA服務。 (FORMS_CAPTCHA)

請聯絡[Adobe支援](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以取得說明或解決疑慮。
