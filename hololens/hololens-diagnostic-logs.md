---
title: 收集和使用 HoloLens 裝置的診斷資訊
description: 瞭解如何收集、使用及保留 HoloLens 裝置的診斷資訊。
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/15/2020
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.custom:
- CI 115131
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: c1d5205d4faa4384600c489167c9581de8e4b62c
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397839"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a><span data-ttu-id="ab19b-103">收集和使用 HoloLens 裝置的診斷資訊</span><span class="sxs-lookup"><span data-stu-id="ab19b-103">Collect and use diagnostic information from HoloLens devices</span></span>

<span data-ttu-id="ab19b-104">HoloLens 使用者和系統管理員可以從四種不同的方法中進行選擇，以收集 HoloLens 的診斷資訊：</span><span class="sxs-lookup"><span data-stu-id="ab19b-104">HoloLens users and administrators can choose from among four different methods to collect diagnostic information from HoloLens:</span></span>

- <span data-ttu-id="ab19b-105">意見反應中樞應用程式</span><span class="sxs-lookup"><span data-stu-id="ab19b-105">Feedback Hub app</span></span>
- <span data-ttu-id="ab19b-106">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="ab19b-106">DiagnosticLog CSP</span></span>
- <span data-ttu-id="ab19b-107">設定 App</span><span class="sxs-lookup"><span data-stu-id="ab19b-107">Settings app</span></span>
- <span data-ttu-id="ab19b-108">離線診斷</span><span class="sxs-lookup"><span data-stu-id="ab19b-108">Offline Diagnostics</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="ab19b-109">裝置診斷記錄包含個人識別資訊 (PII) ，例如使用者在一般作業期間啟動的進程或應用程式。</span><span class="sxs-lookup"><span data-stu-id="ab19b-109">Device diagnostic logs contain personally identifiable information (PII), such as about what processes or applications the user starts during typical operations.</span></span> <span data-ttu-id="ab19b-110">如果有多個使用者共用 HoloLens 裝置 (例如，使用者使用不同的 Microsoft Azure Active Directory (Azure AD) 帳戶登入相同的裝置，) 診斷記錄可能包含適用于多個使用者的 PII 資訊。</span><span class="sxs-lookup"><span data-stu-id="ab19b-110">When multiple users share a HoloLens device (for example, users sign in to the same device by using different Microsoft Azure Active Directory (Azure AD) accounts) the diagnostic logs may contain PII information that applies to multiple users.</span></span> <span data-ttu-id="ab19b-111">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://privacy.microsoft.com/privacystatement)。</span><span class="sxs-lookup"><span data-stu-id="ab19b-111">For more information, see [Microsoft Privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

<span data-ttu-id="ab19b-112">下表比較不同的收集方法。</span><span class="sxs-lookup"><span data-stu-id="ab19b-112">The following table compares different collection methods.</span></span> <span data-ttu-id="ab19b-113">方法名稱會連結至資料表後面各節中的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ab19b-113">The method names link to more detailed information in the sections that follow the table.</span></span>

|<span data-ttu-id="ab19b-114">方法</span><span class="sxs-lookup"><span data-stu-id="ab19b-114">Method</span></span> |<span data-ttu-id="ab19b-115">必要條件</span><span class="sxs-lookup"><span data-stu-id="ab19b-115">Prerequisites</span></span> |<span data-ttu-id="ab19b-116">資料地點</span><span class="sxs-lookup"><span data-stu-id="ab19b-116">Data locations</span></span> |<span data-ttu-id="ab19b-117">資料存取和使用</span><span class="sxs-lookup"><span data-stu-id="ab19b-117">Data access and use</span></span> |<span data-ttu-id="ab19b-118">資料保留</span><span class="sxs-lookup"><span data-stu-id="ab19b-118">Data retention</span></span> |
| --- | --- | --- | --- | --- |
|[<span data-ttu-id="ab19b-119">意見反應中樞</span><span class="sxs-lookup"><span data-stu-id="ab19b-119">Feedback Hub</span></span>](#feedback-hub) |<span data-ttu-id="ab19b-120">網路和網際網路連接</span><span class="sxs-lookup"><span data-stu-id="ab19b-120">Network and internet connection</span></span><br /><br /><span data-ttu-id="ab19b-121">意見反應中樞應用程式</span><span class="sxs-lookup"><span data-stu-id="ab19b-121">Feedback Hub app</span></span><br /><br /><span data-ttu-id="ab19b-122">將檔案上傳至 Microsoft 雲端的許可權</span><span class="sxs-lookup"><span data-stu-id="ab19b-122">Permission to upload files to the Microsoft cloud</span></span> |<span data-ttu-id="ab19b-123">Microsoft 雲端</span><span class="sxs-lookup"><span data-stu-id="ab19b-123">Microsoft cloud</span></span><br /><br /><span data-ttu-id="ab19b-124">HoloLens 裝置 (選用) </span><span class="sxs-lookup"><span data-stu-id="ab19b-124">HoloLens device (optional)</span></span> |<span data-ttu-id="ab19b-125">使用者要求協助、同意使用條款及上傳資料</span><span class="sxs-lookup"><span data-stu-id="ab19b-125">User requests assistance, agrees to the terms of use, and uploads the data</span></span><br /><br /><span data-ttu-id="ab19b-126">Microsoft 員工會看到資料，與使用條款一致</span><span class="sxs-lookup"><span data-stu-id="ab19b-126">Microsoft employees view the data, as consistent with the terms of use</span></span> |<span data-ttu-id="ab19b-127">雲端中的資料會保留在下一代隱私權 (NGP) 所定義的期間內。</span><span class="sxs-lookup"><span data-stu-id="ab19b-127">Data in the cloud is retained for the period that is defined by Next Generation Privacy (NGP).</span></span> <span data-ttu-id="ab19b-128">然後會自動刪除資料。</span><span class="sxs-lookup"><span data-stu-id="ab19b-128">Then the data is deleted automatically.</span></span><br /><br /><span data-ttu-id="ab19b-129">具有 **裝置擁有** 者或系統 **管理員** 許可權的使用者可以隨時刪除裝置上的資料。</span><span class="sxs-lookup"><span data-stu-id="ab19b-129">Data on the device can be deleted at any time by a user who has **Device owner** or **Admin** permissions.</span></span> |
|[<span data-ttu-id="ab19b-130">設定疑難排解員</span><span class="sxs-lookup"><span data-stu-id="ab19b-130">Settings Troubleshooter</span></span>](#settings-troubleshooter) |<span data-ttu-id="ab19b-131">設定 App</span><span class="sxs-lookup"><span data-stu-id="ab19b-131">Settings app</span></span> |<span data-ttu-id="ab19b-132">HoloLens 裝置</span><span class="sxs-lookup"><span data-stu-id="ab19b-132">HoloLens device</span></span><br /><br /><span data-ttu-id="ab19b-133">連接的電腦 (選用) </span><span class="sxs-lookup"><span data-stu-id="ab19b-133">Connected computer (optional)</span></span> |<span data-ttu-id="ab19b-134">使用者會儲存資料，而且只有使用者會 (存取資料，除非使用者與其他使用者) 明確共用資料。</span><span class="sxs-lookup"><span data-stu-id="ab19b-134">The user stores the data, and only the user accesses the data (unless the user specifically shares the data with another user).</span></span> |<span data-ttu-id="ab19b-135">資料會保留在裝置上，直到使用者刪除為止。 \*</span><span class="sxs-lookup"><span data-stu-id="ab19b-135">The data is retained on device until the user deletes it.\*</span></span> |
|[<span data-ttu-id="ab19b-136">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="ab19b-136">DiagnosticLog CSP</span></span>](#diagnosticlog-csp) |<span data-ttu-id="ab19b-137">網路連線</span><span class="sxs-lookup"><span data-stu-id="ab19b-137">Network connection</span></span><br /><br /><span data-ttu-id="ab19b-138">支援 DiagnosticLog CSP 的 MDM 環境</span><span class="sxs-lookup"><span data-stu-id="ab19b-138">MDM environment that supports the DiagnosticLog CSP</span></span> |<span data-ttu-id="ab19b-139">系統管理員設定儲存位置</span><span class="sxs-lookup"><span data-stu-id="ab19b-139">Administrator configures storage locations</span></span> |<span data-ttu-id="ab19b-140">在受管理的環境中，使用者會以隱含的方式同意資料的系統管理員存取權。</span><span class="sxs-lookup"><span data-stu-id="ab19b-140">In the managed environment, the user implicitly consents to administrator access to the data.</span></span><br /><br /><span data-ttu-id="ab19b-141">系統管理員設定存取角色和許可權。</span><span class="sxs-lookup"><span data-stu-id="ab19b-141">Administrator configures access roles and permissions.</span></span> | <span data-ttu-id="ab19b-142">資料會保留在雲端儲存體中，而且系統管理員會設定保留原則。</span><span class="sxs-lookup"><span data-stu-id="ab19b-142">Data is retained in the cloud storage and Administrator configures retention policy.</span></span> |
|[<span data-ttu-id="ab19b-143">離線診斷</span><span class="sxs-lookup"><span data-stu-id="ab19b-143">Offline diagnostics</span></span>](#offline-diagnostics) |<span data-ttu-id="ab19b-144">裝置設定：</span><span class="sxs-lookup"><span data-stu-id="ab19b-144">Device configuration:</span></span><ul><li><span data-ttu-id="ab19b-145">開啟電源並連接到電腦</span><span class="sxs-lookup"><span data-stu-id="ab19b-145">Powered on and connected to computer</span></span></li><li><span data-ttu-id="ab19b-146">電源和音量按鈕正常運作</span><span class="sxs-lookup"><span data-stu-id="ab19b-146">Power and Volume buttons functioning</span></span></li></ul> |<span data-ttu-id="ab19b-147">HoloLens 裝置</span><span class="sxs-lookup"><span data-stu-id="ab19b-147">HoloLens device</span></span><br /><br /><span data-ttu-id="ab19b-148">連接的電腦</span><span class="sxs-lookup"><span data-stu-id="ab19b-148">Connected computer</span></span> |<span data-ttu-id="ab19b-149">使用者會儲存資料，而且只有使用者會 (存取資料，除非使用者與其他使用者) 明確共用資料。</span><span class="sxs-lookup"><span data-stu-id="ab19b-149">The user stores the data, and only the user accesses the data (unless the user specifically shares the data with another user).</span></span> |<span data-ttu-id="ab19b-150">資料會保留在裝置上，直到使用者刪除為止。</span><span class="sxs-lookup"><span data-stu-id="ab19b-150">The data is retained on device until the user deletes it.</span></span> |

* <span data-ttu-id="ab19b-151">終端使用者負責以負責任的方式與他人共用記錄。</span><span class="sxs-lookup"><span data-stu-id="ab19b-151">End-user is responsible for sharing the logs responsibly with someone else.</span></span> <span data-ttu-id="ab19b-152">這些檔案在聯繫客戶服務和支援時，主要很有用。</span><span class="sxs-lookup"><span data-stu-id="ab19b-152">These files are primarily useful when contacting customer service and support.</span></span>  

## <a name="feedback-hub"></a><span data-ttu-id="ab19b-153">意見反應中樞</span><span class="sxs-lookup"><span data-stu-id="ab19b-153">Feedback Hub</span></span>

<span data-ttu-id="ab19b-154">HoloLens 使用者可以使用 Microsoft 意見反應中樞 desktop 應用程式，將診斷資訊傳送至 Microsoft 支援服務。</span><span class="sxs-lookup"><span data-stu-id="ab19b-154">A HoloLens user can use the Microsoft Feedback Hub desktop app to send diagnostic information to Microsoft Support.</span></span> <span data-ttu-id="ab19b-155">如需詳細資訊和完整指示，請參閱 [提供給我們意見](hololens-feedback.md)反應。</span><span class="sxs-lookup"><span data-stu-id="ab19b-155">For details and complete instructions, see [Give us feedback](hololens-feedback.md).</span></span>  

> [!NOTE]  
> <span data-ttu-id="ab19b-156">**商業或企業使用者：** 如果您使用意見反應中樞應用程式來報告與 MDM、布建或任何其他裝置管理方面相關的問題，請將應用程式類別變更為 **企業管理**  >  **裝置類別**。</span><span class="sxs-lookup"><span data-stu-id="ab19b-156">**Commercial or enterprise users:** If you use the Feedback Hub app to report a problem that relates to MDM, provisioning, or any other device management aspect, change the app category to **Enterprise Management** > **Device category**.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="ab19b-157">為了提供修正問題的最佳可能資料，強烈建議您將裝置遙測設定為 **選擇性**。</span><span class="sxs-lookup"><span data-stu-id="ab19b-157">To provide the best possible data for fixing issues, we highly recommend that you set your device telemetry to **Optional**.</span></span> <span data-ttu-id="ab19b-158">您可以在 (OOBE) 的全新體驗期間，或使用 [ **設定** ] 應用程式來設定此值。</span><span class="sxs-lookup"><span data-stu-id="ab19b-158">You can set this value during the Out-of-Box-Experience (OOBE), or by using the **Settings** app.</span></span> <span data-ttu-id="ab19b-159">若要使用設定來完成這項操作，請選取 [ **開始 > 設定] > [> 應用程式診斷 >**]。</span><span class="sxs-lookup"><span data-stu-id="ab19b-159">To do this by using Settings, select **Start > Settings > Privacy > App Diagnostics > On**.</span></span>
### <a name="prerequisites"></a><span data-ttu-id="ab19b-160">必要條件</span><span class="sxs-lookup"><span data-stu-id="ab19b-160">Prerequisites</span></span>

- <span data-ttu-id="ab19b-161">裝置已連線到網路。</span><span class="sxs-lookup"><span data-stu-id="ab19b-161">The device is connected to a network.</span></span>
- <span data-ttu-id="ab19b-162">意見反應中樞的應用程式可在使用者的桌上型電腦上取得，而使用者可將檔案上傳至 Microsoft 雲端。</span><span class="sxs-lookup"><span data-stu-id="ab19b-162">The Feedback Hub app is available on the user's desktop computer, and the user can upload files to the Microsoft cloud.</span></span>

### <a name="data-locations-access-and-retention"></a><span data-ttu-id="ab19b-163">資料位置、存取和保留期</span><span class="sxs-lookup"><span data-stu-id="ab19b-163">Data locations, access, and retention</span></span>

<span data-ttu-id="ab19b-164">藉由同意意見反應中樞的使用規定，使用者會明確同意至資料 (的儲存和使用方式，如該合約) 所定義。</span><span class="sxs-lookup"><span data-stu-id="ab19b-164">By agreeing to the terms-of-use of the Feedback Hub, the user explicitly consents to the storage and usage of the data (as defined by that agreement).</span></span>

<span data-ttu-id="ab19b-165">意見反應中樞提供兩個位置讓使用者儲存診斷資訊：</span><span class="sxs-lookup"><span data-stu-id="ab19b-165">The Feedback Hub provides two places for the user to store diagnostic information:</span></span>

- <span data-ttu-id="ab19b-166">**Microsoft 雲端**。</span><span class="sxs-lookup"><span data-stu-id="ab19b-166">**The Microsoft cloud**.</span></span> <span data-ttu-id="ab19b-167">使用者使用意見反應中樞應用程式上傳的資料會儲存在與下一代隱私權一致 (NGP) 需求的天數內。</span><span class="sxs-lookup"><span data-stu-id="ab19b-167">Data that the user uploads by using the Feedback Hub app is stored for the number of days that is consistent with Next Generation Privacy (NGP) requirements.</span></span> <span data-ttu-id="ab19b-168">Microsoft 員工可以使用 NGP 相容的檢視器來存取這段期間的資訊。</span><span class="sxs-lookup"><span data-stu-id="ab19b-168">Microsoft employees can use an NGP-compliant viewer to access the information during this period.</span></span>

   > [!NOTE]  
   > <span data-ttu-id="ab19b-169">這些需求適用于所有意見反應中樞類別中的資料。</span><span class="sxs-lookup"><span data-stu-id="ab19b-169">These requirements apply to data in all Feedback Hub categories.</span></span>

- <span data-ttu-id="ab19b-170">**HoloLens 裝置**。</span><span class="sxs-lookup"><span data-stu-id="ab19b-170">**The HoloLens device**.</span></span> <span data-ttu-id="ab19b-171">當意見反應中樞中的報表時，使用者可以選取 [ **儲存診斷的本機複本，以及提供意見反應時所建立的附件**]。</span><span class="sxs-lookup"><span data-stu-id="ab19b-171">While filing a report in Feedback Hub, the user can select **Save a local copy of diagnostics and attachments created when giving feedback**.</span></span> <span data-ttu-id="ab19b-172">如果使用者選取這個選項，意見反應中樞會在 HoloLens 裝置上儲存一份診斷資訊。</span><span class="sxs-lookup"><span data-stu-id="ab19b-172">If the user selects this option, the Feedback Hub stores a copy of the diagnostic information on the HoloLens device.</span></span> <span data-ttu-id="ab19b-173">此資訊仍可供使用者 (或使用該帳戶登入 HoloLens) 的任何人存取。</span><span class="sxs-lookup"><span data-stu-id="ab19b-173">This information remains accessible to the user (or anyone that uses that account to sign in to HoloLens).</span></span> <span data-ttu-id="ab19b-174">若要刪除此資訊，使用者必須擁有裝置的 **裝置擁有** 者或系統 **管理員** 許可權。</span><span class="sxs-lookup"><span data-stu-id="ab19b-174">To delete this information, a user must have **Device owner** or **Admin** permissions on the device.</span></span> <span data-ttu-id="ab19b-175">具有適當許可權的使用者可以登入意見反應中樞、選取 [**設定**]  >  **視圖診斷記錄**，以及刪除資訊。</span><span class="sxs-lookup"><span data-stu-id="ab19b-175">A user who has the appropriate permissions can sign in to the Feedback Hub, select **Settings** > **View diagnostics logs**, and delete the information.</span></span>

## <a name="settings-troubleshooter"></a><span data-ttu-id="ab19b-176">設定疑難排解員</span><span class="sxs-lookup"><span data-stu-id="ab19b-176">Settings Troubleshooter</span></span>

<span data-ttu-id="ab19b-177">HoloLens 使用者可以使用裝置上的 [ **設定** ] 應用程式，針對問題進行疑難排解，並收集診斷資訊。</span><span class="sxs-lookup"><span data-stu-id="ab19b-177">A HoloLens user can use the **Settings** app on the device to troubleshoot problems and collect diagnostic information.</span></span> <span data-ttu-id="ab19b-178">若要這樣做，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ab19b-178">To do this, follow these steps:</span></span>

1. <span data-ttu-id="ab19b-179">開啟 [設定] 應用程式，然後選取 [**更新 & 安全性**  >  **疑難排解**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="ab19b-179">Open the Settings app and select **Update & Security** > **Troubleshoot** page.</span></span>
1. <span data-ttu-id="ab19b-180">選取適當的區域，然後選取 [ **開始**]。</span><span class="sxs-lookup"><span data-stu-id="ab19b-180">Select the appropriate area, and select **Start**.</span></span>
1. <span data-ttu-id="ab19b-181">重現問題。</span><span class="sxs-lookup"><span data-stu-id="ab19b-181">Reproduce the issue.</span></span>
1. <span data-ttu-id="ab19b-182">重現問題之後，請返回 [設定]，然後選取 [ **停止**]。</span><span class="sxs-lookup"><span data-stu-id="ab19b-182">After you reproduce the issue, return to Settings and then select **Stop**.</span></span>

<span data-ttu-id="ab19b-183">使用者也可以從 [ **設定** ] 應用程式設定回溯診斷的行為。</span><span class="sxs-lookup"><span data-stu-id="ab19b-183">A user can also configure the behavior of Fallback Diagnostics from the **Settings** app.</span></span> <span data-ttu-id="ab19b-184">流覽至 [ **隱私權-> 疑難排解** ] 頁面，以設定此設定。</span><span class="sxs-lookup"><span data-stu-id="ab19b-184">Navigate to **Privacy -> Troubleshooting** page to configure this setting.</span></span>
> [!NOTE]
> <span data-ttu-id="ab19b-185">如果裝置已設定 MDM 原則，使用者將無法覆寫該行為。</span><span class="sxs-lookup"><span data-stu-id="ab19b-185">If there is MDM policy configured for the device, user will not be able to override that behavior.</span></span>

### <a name="os-update-troubleshooter"></a><span data-ttu-id="ab19b-186">作業系統更新疑難排解員</span><span class="sxs-lookup"><span data-stu-id="ab19b-186">OS Update Troubleshooter</span></span>
<span data-ttu-id="ab19b-187">組建 Windows 全像 [21H1 版 ](hololens-release-notes.md#windows-holographic-version-21h1) 和更新版本：</span><span class="sxs-lookup"><span data-stu-id="ab19b-187">On builds [Windows Holographic, version 21H1 ](hololens-release-notes.md#windows-holographic-version-21h1) and onwards:</span></span>
- <span data-ttu-id="ab19b-188">除了「設定」應用程式內的先前疑難排解工具之外，還新增了新的疑難排解員，新增了新的「設定」應用程式以進行 OS 更新。</span><span class="sxs-lookup"><span data-stu-id="ab19b-188">In addition to the previous troubleshooters within the Settings app, a new troubleshooter has been added with the addition of the new Settings app for OS Updates.</span></span> <span data-ttu-id="ab19b-189">流覽至 [ **設定]-> 更新 & 安全性-> 疑難排解-> Windows Update** ，然後選取 [ **啟動**]。</span><span class="sxs-lookup"><span data-stu-id="ab19b-189">Navigate to **Settings -> Update & Security -> Troubleshoot -> Windows Update** and select **Start**.</span></span> <span data-ttu-id="ab19b-190">這可讓您在使用作業系統更新重現問題時收集追蹤，以協助您更妥善地針對 IT 或支援進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="ab19b-190">This allows you to collect traces while reproducing your issue with OS Updates to assist better in troubleshooting with your IT or support.</span></span>
### <a name="prerequisites"></a><span data-ttu-id="ab19b-191">必要條件</span><span class="sxs-lookup"><span data-stu-id="ab19b-191">Prerequisites</span></span>

- <span data-ttu-id="ab19b-192">[ **設定** ] 應用程式會安裝在裝置上，並可供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="ab19b-192">The **Settings** app is installed on the device and is available to the user.</span></span>

### <a name="data-locations-access-and-retention"></a><span data-ttu-id="ab19b-193">資料位置、存取和保留期</span><span class="sxs-lookup"><span data-stu-id="ab19b-193">Data locations, access, and retention</span></span>

<span data-ttu-id="ab19b-194">由於使用者會啟動資料收集，因此使用者會隱含地同意到診斷資訊的儲存區。</span><span class="sxs-lookup"><span data-stu-id="ab19b-194">Because the user starts the data collection, the user implicitly consents to the storage of the diagnostic information.</span></span> <span data-ttu-id="ab19b-195">只有使用者或使用者共用資料的任何人，都可以存取資料。</span><span class="sxs-lookup"><span data-stu-id="ab19b-195">Only the user, or anyone with whom that the user shares the data, can access the data.</span></span>

<span data-ttu-id="ab19b-196">診斷資訊會儲存在裝置上。</span><span class="sxs-lookup"><span data-stu-id="ab19b-196">The diagnostic information is stored on the device.</span></span> <span data-ttu-id="ab19b-197">如果裝置已連線到使用者的電腦，該資訊也會位於電腦上的下列檔案中：</span><span class="sxs-lookup"><span data-stu-id="ab19b-197">If the device is connected to the user's computer, the information also resides on the computer in the following file:</span></span>

> <span data-ttu-id="ab19b-198">這部電腦的 \\ \<*HoloLens device name*> \\ 內部儲存體 \\ 檔 \\ 追蹤 \<*ddmmyyhhmmss*> .etl</span><span class="sxs-lookup"><span data-stu-id="ab19b-198">This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents\\Trace\<*ddmmyyhhmmss*>.etl</span></span>

> [!NOTE]  
> <span data-ttu-id="ab19b-199">在此檔案路徑和名稱中， \<*HoloLens device name*> 代表 HoloLens 裝置的名稱，並 \<*ddmmyyhhmmss*> 代表建立檔案的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="ab19b-199">In this file path and name, \<*HoloLens device name*> represents the name of the HoloLens device, and \<*ddmmyyhhmmss*> represents the date and time that the file was created.</span></span>

<span data-ttu-id="ab19b-200">診斷資訊會保留在這些位置，直到使用者刪除為止。</span><span class="sxs-lookup"><span data-stu-id="ab19b-200">The diagnostic information remains in these locations until the user deletes it.</span></span>

## <a name="diagnosticlog-csp"></a><span data-ttu-id="ab19b-201">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="ab19b-201">DiagnosticLog CSP</span></span>

<span data-ttu-id="ab19b-202">在行動裝置管理 (MDM) 環境中，IT 系統管理員可以使用 DiagnosticLog 設定 [服務提供者 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) 來設定已註冊 HoloLens 裝置上的診斷設定。</span><span class="sxs-lookup"><span data-stu-id="ab19b-202">In a Mobile Device Management (MDM) environment, the IT administrator can use the the [DiagnosticLog configuration service provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) to configure diagnostic settings on enrolled HoloLens devices.</span></span> <span data-ttu-id="ab19b-203">IT 系統管理員可以設定這些設定，從已註冊的裝置收集記錄。</span><span class="sxs-lookup"><span data-stu-id="ab19b-203">The IT administrator can configure these settings to collect logs from enrolled devices.</span></span>

<span data-ttu-id="ab19b-204">查看更多：</span><span class="sxs-lookup"><span data-stu-id="ab19b-204">See more:</span></span>
- [<span data-ttu-id="ab19b-205">從 Windows 裝置收集診斷</span><span class="sxs-lookup"><span data-stu-id="ab19b-205">Collect diagnostics from a Windows device</span></span>](https://docs.microsoft.com/mem/intune/remote-actions/collect-diagnostics)
- [<span data-ttu-id="ab19b-206">Intune 公開預覽版-Windows 10 裝置診斷</span><span class="sxs-lookup"><span data-stu-id="ab19b-206">Intune Public Preview - Windows 10 Device diagnostics</span></span>](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a><span data-ttu-id="ab19b-207">必要條件</span><span class="sxs-lookup"><span data-stu-id="ab19b-207">Prerequisites</span></span>

- <span data-ttu-id="ab19b-208">裝置已連線到網路。</span><span class="sxs-lookup"><span data-stu-id="ab19b-208">The device is connected to a network.</span></span>
- <span data-ttu-id="ab19b-209">裝置會在支援 DiagnosticLog CSP 的 MDM 環境中註冊。</span><span class="sxs-lookup"><span data-stu-id="ab19b-209">The device is enrolled in an MDM environment that supports the DiagnosticLog CSP.</span></span>

### <a name="data-locations-access-and-retention"></a><span data-ttu-id="ab19b-210">資料位置、存取和保留期</span><span class="sxs-lookup"><span data-stu-id="ab19b-210">Data locations, access, and retention</span></span>

<span data-ttu-id="ab19b-211">由於裝置是受管理環境的一部分，因此使用者會以隱含的方式同意診斷資訊的系統管理存取權。</span><span class="sxs-lookup"><span data-stu-id="ab19b-211">Because the device is part of the managed environment, the user implicitly consents to administrative access to diagnostic information.</span></span>

<span data-ttu-id="ab19b-212">IT 系統管理員會使用 DiagnosticLog CSP 來設定資料儲存、保留和存取原則，包括管理下列各項的原則：</span><span class="sxs-lookup"><span data-stu-id="ab19b-212">The IT administrator uses the DiagnosticLog CSP to configure the data storage, retention, and access policies, including the policies that govern the following:</span></span>

- <span data-ttu-id="ab19b-213">儲存診斷資訊的雲端基礎結構。</span><span class="sxs-lookup"><span data-stu-id="ab19b-213">The cloud infrastructure that stores the diagnostic information.</span></span>
- <span data-ttu-id="ab19b-214">診斷資訊的保留期限。</span><span class="sxs-lookup"><span data-stu-id="ab19b-214">The retention period for the diagnostic information.</span></span>
- <span data-ttu-id="ab19b-215">控制診斷資訊存取權的許可權。</span><span class="sxs-lookup"><span data-stu-id="ab19b-215">Permissions that control access to the diagnostic information.</span></span>

## <a name="offline-diagnostics"></a><span data-ttu-id="ab19b-216">離線診斷</span><span class="sxs-lookup"><span data-stu-id="ab19b-216">Offline diagnostics</span></span>
<span data-ttu-id="ab19b-217">在裝置無法透過意見反應中樞或設定疑難排解員收集診斷的情況下，您可以手動收集診斷資訊。</span><span class="sxs-lookup"><span data-stu-id="ab19b-217">In situations where the device is not able to collect diagnostics via Feedback Hub or the Settings Troubleshooter, you can collect diagnostics manually.</span></span> <span data-ttu-id="ab19b-218">其中一個必要的案例是裝置無法連線到 Wi-Fi，或您無法存取上述的其他方法。</span><span class="sxs-lookup"><span data-stu-id="ab19b-218">One scenario where this is necessary is when the device cannot connect to Wi-Fi or you can't access other methods mentioned above.</span></span> <span data-ttu-id="ab19b-219">診斷會從裝置收集損毀傾印和記錄，以協助 Microsoft 支援工程師找出問題。</span><span class="sxs-lookup"><span data-stu-id="ab19b-219">The diagnostics collect crash dumps and logs from the device that help a Microsoft support engineer isolate issues.</span></span>

<span data-ttu-id="ab19b-220">當裝置透過 USB 纜線將裝置連接到電腦之後，就會出現在檔案總管中。</span><span class="sxs-lookup"><span data-stu-id="ab19b-220">This works when the device shows up in File Explorer after connecting it to a PC via a USB cable.</span></span>

> [!NOTE]
> <span data-ttu-id="ab19b-221">離線診斷產生和管理會依您的作業系統版本而有不同的控制。</span><span class="sxs-lookup"><span data-stu-id="ab19b-221">Offline Diagnostics generation and management is controlled differently depending on your OS version.</span></span> <span data-ttu-id="ab19b-222">之前是由遙測設定所控制，但現在已透過 MDM 原則直接控制。</span><span class="sxs-lookup"><span data-stu-id="ab19b-222">Previously it was controlled by the telemetry setting, but is now directly controlled via MDM policy.</span></span> <span data-ttu-id="ab19b-223">如果透過設定或 MDM 原則停用，則無法使用此機制來收集診斷記錄。</span><span class="sxs-lookup"><span data-stu-id="ab19b-223">If disabled via either setting or MDM policy, then diagnostic logs cannot be collected using this mechanism.</span></span>

<span data-ttu-id="ab19b-224">Windows 全像 [版本20H2 之前的](hololens-release-notes.md#windows-holographic-version-20h2)行為：</span><span class="sxs-lookup"><span data-stu-id="ab19b-224">Behavior prior to [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2):</span></span>
 - <span data-ttu-id="ab19b-225">只有當使用者要通過 OOBE 或 [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) 原則值設定為 Full 時，才會啟用離線診斷， (Basic 是 HoloLens) 上的預設值。</span><span class="sxs-lookup"><span data-stu-id="ab19b-225">Offline diagnostics is only enabled when user is either going through OOBE or [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) policy value is set to Full (Basic is default value on HoloLens).</span></span> 
- <span data-ttu-id="ab19b-226">若要停用離線診斷，請移至 [**設定] 應用程式 > 隱私權**] 頁面，然後選取 [**診斷資料** 中的 **基本**</span><span class="sxs-lookup"><span data-stu-id="ab19b-226">To disable Offline diagnostics, go to **Settings App > Privacy** page and select **Basic** in **Diagnostic Data**.</span></span> <span data-ttu-id="ab19b-227">在離線診斷相依于遙測設定的組建上，它只會影響是否收集任何記錄。</span><span class="sxs-lookup"><span data-stu-id="ab19b-227">On builds where offline diagnostics depends on telemetry setting, it only impacts whether any logs are collected or not.</span></span> <span data-ttu-id="ab19b-228">它不會影響收集的檔案。</span><span class="sxs-lookup"><span data-stu-id="ab19b-228">It does not impact what files are collected.</span></span>
- <span data-ttu-id="ab19b-229">如果裝置已鎖定，則不會出現記錄。</span><span class="sxs-lookup"><span data-stu-id="ab19b-229">If device is locked then logs won't appear.</span></span>

<span data-ttu-id="ab19b-230">組建 Windows 全像 [20H2 版](hololens-release-notes.md#windows-holographic-version-20h2) 和更新版本：</span><span class="sxs-lookup"><span data-stu-id="ab19b-230">On builds [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) and onwards:</span></span>
- <span data-ttu-id="ab19b-231">啟用 Fallback 診斷之後，將會由具有對應設定[MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)的特定 MDM 原則控制</span><span class="sxs-lookup"><span data-stu-id="ab19b-231">When Fallback Diagnostics is enabled will be controlled by specific MDM policy with corresponding setting [MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)</span></span>
- <span data-ttu-id="ab19b-232">如果裝置已鎖定，則不會出現記錄。</span><span class="sxs-lookup"><span data-stu-id="ab19b-232">If device is locked then logs won't appear.</span></span>

<span data-ttu-id="ab19b-233">觀看這段影片以深入了解。</span><span class="sxs-lookup"><span data-stu-id="ab19b-233">Watch this video to learn more.</span></span>

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

<span data-ttu-id="ab19b-234">請遵循下列步驟來收集診斷：</span><span class="sxs-lookup"><span data-stu-id="ab19b-234">Follow these steps to collect diagnostics:</span></span>
1.  <span data-ttu-id="ab19b-235">使用 USB 纜線將裝置連接到您的電腦。</span><span class="sxs-lookup"><span data-stu-id="ab19b-235">Connect the device with a USB cable to your PC.</span></span>
2.  <span data-ttu-id="ab19b-236">在電腦的檔案總管中，流覽至 [ **此電腦 \<hololens-device> \Internal 儲存體**]。</span><span class="sxs-lookup"><span data-stu-id="ab19b-236">In File Explorer on your PC, navigate to **'This PC\<hololens-device>\Internal Storage'**.</span></span>
3.  <span data-ttu-id="ab19b-237">如果未顯示 **內部儲存體** 資料夾，裝置會等待使用者登入。</span><span class="sxs-lookup"><span data-stu-id="ab19b-237">If the **Internal Storage** folder does not show up, the device is waiting for a user to sign in.</span></span> <span data-ttu-id="ab19b-238">只要按住電源按鈕10秒，即可登入或重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="ab19b-238">Either sign-in or power cycle the device by holding the POWER button down for 10 seconds.</span></span>
4.  <span data-ttu-id="ab19b-239">按下並立即放開 **電源 + 音量** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="ab19b-239">Press and immediately release the **Power + Volume Down** buttons together.</span></span>
5.  <span data-ttu-id="ab19b-240">等候一分鐘，讓裝置準備 zip 封存。</span><span class="sxs-lookup"><span data-stu-id="ab19b-240">Wait a minute for the device to prepare the zip archives.</span></span> <span data-ttu-id="ab19b-241"> (一個名為 HololensDiagnostics 的暫存檔案，在裝置產生 zip 封存時可能會顯示出來。</span><span class="sxs-lookup"><span data-stu-id="ab19b-241">(A temporary file named HololensDiagnostics.temp may become visible while the device generates the zip archives.</span></span> <span data-ttu-id="ab19b-242">請勿存取或儲存該檔案。</span><span class="sxs-lookup"><span data-stu-id="ab19b-242">Do not access or save that file.</span></span> <span data-ttu-id="ab19b-243">當程式完成時，zip 封存將會取代它。 ) </span><span class="sxs-lookup"><span data-stu-id="ab19b-243">When the process finishes it will be replaced by the zip archives.)</span></span>
6.  <span data-ttu-id="ab19b-244">重新整理 [檔案瀏覽器]，然後流覽至 **' \Documents '** 資料夾。</span><span class="sxs-lookup"><span data-stu-id="ab19b-244">Refresh file explorer, and navigate to the **'\Documents'** folder.</span></span>
7.  <span data-ttu-id="ab19b-245">複製診斷 ZIP 檔案，並與 Microsoft 支援小組分享。</span><span class="sxs-lookup"><span data-stu-id="ab19b-245">Copy the diagnostics ZIP files and share them with the Microsoft support team.</span></span>

> [!NOTE]
> <span data-ttu-id="ab19b-246">某些診斷 ZIP 檔案可能包含 PII。</span><span class="sxs-lookup"><span data-stu-id="ab19b-246">Some of the diagnostics ZIP files may contain PII.</span></span>
