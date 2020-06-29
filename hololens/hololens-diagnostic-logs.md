---
title: 從 HoloLens 裝置收集及使用診斷資訊
description: ''
author: Teresa-Motiv
ms.author: v-tea
ms.date: 03/23/2020
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
ms.openlocfilehash: f11128c66845f0e062a006855fd75ca66ffc4e5e
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828402"
---
# <span data-ttu-id="8ff19-102">從 HoloLens 裝置收集及使用診斷資訊</span><span class="sxs-lookup"><span data-stu-id="8ff19-102">Collect and use diagnostic information from HoloLens devices</span></span>

<span data-ttu-id="8ff19-103">HoloLens 使用者與系統管理員可以從四種不同的方法中選擇，從 HoloLens 收集診斷資訊：</span><span class="sxs-lookup"><span data-stu-id="8ff19-103">HoloLens users and administrators can choose from among four different methods to collect diagnostic information from HoloLens:</span></span>

- <span data-ttu-id="8ff19-104">意見反應中心應用程式</span><span class="sxs-lookup"><span data-stu-id="8ff19-104">Feedback Hub app</span></span>
- <span data-ttu-id="8ff19-105">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="8ff19-105">DiagnosticLog CSP</span></span>
- <span data-ttu-id="8ff19-106">設定 App</span><span class="sxs-lookup"><span data-stu-id="8ff19-106">Settings app</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="8ff19-107">裝置診斷記錄包含個人身分識別資訊（PII），例如使用者在一般作業期間啟動哪些程式或應用程式。</span><span class="sxs-lookup"><span data-stu-id="8ff19-107">Device diagnostic logs contain personally identifiable information (PII), such as about what processes or applications the user starts during typical operations.</span></span> <span data-ttu-id="8ff19-108">當多個使用者共用一個 HoloLens 裝置時（例如，使用者使用不同的 Microsoft Azure Active Directory （AAD）帳戶登入相同的裝置），診斷記錄可能會包含適用于多個使用者的 PII 資訊。</span><span class="sxs-lookup"><span data-stu-id="8ff19-108">When multiple users share a HoloLens device (for example, users sign in to the same device by using different Microsoft Azure Active Directory (AAD) accounts) the diagnostic logs may contain PII information that applies to multiple users.</span></span> <span data-ttu-id="8ff19-109">如需詳細資訊，請參閱[Microsoft 隱私權聲明](https://privacy.microsoft.com/privacystatement)。</span><span class="sxs-lookup"><span data-stu-id="8ff19-109">For more information, see [Microsoft Privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

<span data-ttu-id="8ff19-110">下表比較三個集合方法。</span><span class="sxs-lookup"><span data-stu-id="8ff19-110">The following table compares the three collection methods.</span></span> <span data-ttu-id="8ff19-111">在表格後面的章節中，方法名稱連結至更詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="8ff19-111">The method names link to more detailed information in the sections that follow the table.</span></span>

|<span data-ttu-id="8ff19-112">方法</span><span class="sxs-lookup"><span data-stu-id="8ff19-112">Method</span></span> |<span data-ttu-id="8ff19-113">必要條件</span><span class="sxs-lookup"><span data-stu-id="8ff19-113">Prerequisites</span></span> |<span data-ttu-id="8ff19-114">資料位置</span><span class="sxs-lookup"><span data-stu-id="8ff19-114">Data locations</span></span> |<span data-ttu-id="8ff19-115">資料存取及使用</span><span class="sxs-lookup"><span data-stu-id="8ff19-115">Data access and use</span></span> |<span data-ttu-id="8ff19-116">資料保留</span><span class="sxs-lookup"><span data-stu-id="8ff19-116">Data retention</span></span> |
| --- | --- | --- | --- | --- |
|[<span data-ttu-id="8ff19-117">意見反應中樞</span><span class="sxs-lookup"><span data-stu-id="8ff19-117">Feedback Hub</span></span>](#feedback-hub) |<span data-ttu-id="8ff19-118">網路和網際網路連線</span><span class="sxs-lookup"><span data-stu-id="8ff19-118">Network and internet connection</span></span><br /><br /><span data-ttu-id="8ff19-119">意見反應中心應用程式</span><span class="sxs-lookup"><span data-stu-id="8ff19-119">Feedback Hub app</span></span><br /><br /><span data-ttu-id="8ff19-120">將檔案上傳到 Microsoft 雲端的許可權</span><span class="sxs-lookup"><span data-stu-id="8ff19-120">Permission to upload files to the Microsoft cloud</span></span> |<span data-ttu-id="8ff19-121">Microsoft 雲端</span><span class="sxs-lookup"><span data-stu-id="8ff19-121">Microsoft cloud</span></span><br /><br /><span data-ttu-id="8ff19-122">HoloLens 裝置（選用）</span><span class="sxs-lookup"><span data-stu-id="8ff19-122">HoloLens device (optional)</span></span> |<span data-ttu-id="8ff19-123">使用者要求協助、同意使用條款及上傳資料</span><span class="sxs-lookup"><span data-stu-id="8ff19-123">User requests assistance, agrees to the terms of use, and uploads the data</span></span><br /><br /><span data-ttu-id="8ff19-124">Microsoft 員工會以與使用條款相符的方式來查看資料</span><span class="sxs-lookup"><span data-stu-id="8ff19-124">Microsoft employees view the data, as consistent with the terms of use</span></span> |<span data-ttu-id="8ff19-125">雲端中的資料會針對 [新一代隱私權（NGP）] 定義的期間保留。</span><span class="sxs-lookup"><span data-stu-id="8ff19-125">Data in the cloud is retained for the period that is defined by Next Generation Privacy (NGP).</span></span> <span data-ttu-id="8ff19-126">然後，系統會自動刪除該資料。</span><span class="sxs-lookup"><span data-stu-id="8ff19-126">Then the data is deleted automatically.</span></span><br /><br /><span data-ttu-id="8ff19-127">裝置上的資料可隨時由擁有**裝置擁有**者或系統**管理員**許可權的使用者刪除。</span><span class="sxs-lookup"><span data-stu-id="8ff19-127">Data on the device can be deleted at any time by a user who has **Device owner** or **Admin** permissions.</span></span> |
|[<span data-ttu-id="8ff19-128">[設定] 疑難排解</span><span class="sxs-lookup"><span data-stu-id="8ff19-128">Settings Troubleshooter</span></span>](#settings-troubleshooter) |<span data-ttu-id="8ff19-129">設定 App</span><span class="sxs-lookup"><span data-stu-id="8ff19-129">Settings app</span></span> |<span data-ttu-id="8ff19-130">HoloLens 裝置</span><span class="sxs-lookup"><span data-stu-id="8ff19-130">HoloLens device</span></span><br /><br /><span data-ttu-id="8ff19-131">已連接的電腦（選用）</span><span class="sxs-lookup"><span data-stu-id="8ff19-131">Connected computer (optional)</span></span> |<span data-ttu-id="8ff19-132">使用者會儲存資料，而且只有使用者才存取資料（除非使用者特別與其他使用者共用資料）。</span><span class="sxs-lookup"><span data-stu-id="8ff19-132">The user stores the data, and only the user accesses the data (unless the user specifically shares the data with another user).</span></span> |<span data-ttu-id="8ff19-133">資料會保留，直到使用者刪除為止。</span><span class="sxs-lookup"><span data-stu-id="8ff19-133">The data is retained until the user deletes it.\*</span></span> |
|[<span data-ttu-id="8ff19-134">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="8ff19-134">DiagnosticLog CSP</span></span>](#diagnosticlog-csp) |<span data-ttu-id="8ff19-135">網路連線</span><span class="sxs-lookup"><span data-stu-id="8ff19-135">Network connection</span></span><br /><br /><span data-ttu-id="8ff19-136">支援 DiagnosticLog CSP 的 MDM 環境</span><span class="sxs-lookup"><span data-stu-id="8ff19-136">MDM environment that supports the DiagnosticLog CSP</span></span> |<span data-ttu-id="8ff19-137">系統管理員設定儲存位置</span><span class="sxs-lookup"><span data-stu-id="8ff19-137">Administrator configures storage locations</span></span> |<span data-ttu-id="8ff19-138">在受管理的環境中，使用者隱含地同意資料的管理員存取權。</span><span class="sxs-lookup"><span data-stu-id="8ff19-138">In the managed environment, the user implicitly consents to administrator access to the data.</span></span><br /><br /><span data-ttu-id="8ff19-139">系統管理員設定存取角色和許可權。</span><span class="sxs-lookup"><span data-stu-id="8ff19-139">Administrator configures access roles and permissions.</span></span> | <span data-ttu-id="8ff19-140">系統管理員配置保留原則。</span><span class="sxs-lookup"><span data-stu-id="8ff19-140">Administrator configures retention policy.</span></span> |


-   <span data-ttu-id="8ff19-141">最終使用者負責與其他人共用記錄。</span><span class="sxs-lookup"><span data-stu-id="8ff19-141">End-user is responsible for sharing the logs responsibly with someone else.</span></span> <span data-ttu-id="8ff19-142">這些檔案在與客戶服務和支援人員聯繫時主要很有用。</span><span class="sxs-lookup"><span data-stu-id="8ff19-142">These files are primarily useful when contacting customer service and support.</span></span>  

## <span data-ttu-id="8ff19-143">意見反應中樞</span><span class="sxs-lookup"><span data-stu-id="8ff19-143">Feedback Hub</span></span>

<span data-ttu-id="8ff19-144">HoloLens 使用者可以使用 Microsoft 意見中心桌面應用程式，傳送診斷資訊給 Microsoft 支援。</span><span class="sxs-lookup"><span data-stu-id="8ff19-144">A HoloLens user can use the Microsoft Feedback Hub desktop app to send diagnostic information to Microsoft Support.</span></span> <span data-ttu-id="8ff19-145">如需詳細資訊及完整指示，請參閱[向我們提供意見](hololens-feedback.md)反應。</span><span class="sxs-lookup"><span data-stu-id="8ff19-145">For details and complete instructions, see [Give us feedback](hololens-feedback.md).</span></span>  

> [!NOTE]  
> <span data-ttu-id="8ff19-146">**商業或企業使用者：** 如果您使用意見反應中樞 app 來報告與 MDM、提供或任何其他裝置管理功能相關的問題，請將應用程式類別變更為 [**企業管理**  >  **裝置] 類別**。</span><span class="sxs-lookup"><span data-stu-id="8ff19-146">**Commercial or enterprise users:** If you use the Feedback Hub app to report a problem that relates to MDM, provisioning, or any other device management aspect, change the app category to **Enterprise Management** > **Device category**.</span></span>

### <span data-ttu-id="8ff19-147">必要條件</span><span class="sxs-lookup"><span data-stu-id="8ff19-147">Prerequisites</span></span>

- <span data-ttu-id="8ff19-148">裝置已連線至網路。</span><span class="sxs-lookup"><span data-stu-id="8ff19-148">The device is connected to a network.</span></span>
- <span data-ttu-id="8ff19-149">您可以在使用者的桌上型電腦上使用「意見反應中樞」 app，使用者可以將檔案上傳到 Microsoft 雲端。</span><span class="sxs-lookup"><span data-stu-id="8ff19-149">The Feedback Hub app is available on the user's desktop computer, and the user can upload files to the Microsoft cloud.</span></span>

### <span data-ttu-id="8ff19-150">資料位置、存取和保留</span><span class="sxs-lookup"><span data-stu-id="8ff19-150">Data locations, access, and retention</span></span>

<span data-ttu-id="8ff19-151">透過同意意見反應中樞的使用條款，使用者就能明確同意資料的儲存及使用量（如該協定所定義）。</span><span class="sxs-lookup"><span data-stu-id="8ff19-151">By agreeing to the terms-of-use of the Feedback Hub, the user explicitly consents to the storage and usage of the data (as defined by that agreement).</span></span>

<span data-ttu-id="8ff19-152">意見反應中心提供兩個位置供使用者儲存診斷資訊：</span><span class="sxs-lookup"><span data-stu-id="8ff19-152">The Feedback Hub provides two places for the user to store diagnostic information:</span></span>

- <span data-ttu-id="8ff19-153">**Microsoft 雲端**。</span><span class="sxs-lookup"><span data-stu-id="8ff19-153">**The Microsoft cloud**.</span></span> <span data-ttu-id="8ff19-154">使用者使用「意見反應中心」 app 上傳的資料，會儲存為符合下一代隱私權（NGP）需求的天數。</span><span class="sxs-lookup"><span data-stu-id="8ff19-154">Data that the user uploads by using the Feedback Hub app is stored for the number of days that is consistent with Next Generation Privacy (NGP) requirements.</span></span> <span data-ttu-id="8ff19-155">Microsoft 員工可以使用 NGP 相容的檢視器，在此期間存取訊號。</span><span class="sxs-lookup"><span data-stu-id="8ff19-155">Microsoft employees can use an NGP-compliant viewer to access the information during this period.</span></span>
   > [!NOTE]  
   > <span data-ttu-id="8ff19-156">這些需求適用于所有意見反應中樞類別中的資料。</span><span class="sxs-lookup"><span data-stu-id="8ff19-156">These requirements apply to data in all Feedback Hub categories.</span></span>

- <span data-ttu-id="8ff19-157">**HoloLens 裝置**。</span><span class="sxs-lookup"><span data-stu-id="8ff19-157">**The HoloLens device**.</span></span> <span data-ttu-id="8ff19-158">當您在意見反應中樞中歸檔報表時，使用者可以選取 [**儲存在提供意見反應時建立的診斷與附件的本機複本**]。</span><span class="sxs-lookup"><span data-stu-id="8ff19-158">While filing a report in Feedback Hub, the user can select **Save a local copy of diagnostics and attachments created when giving feedback**.</span></span> <span data-ttu-id="8ff19-159">如果使用者選取此選項，意見反應中心就會儲存 HoloLens 裝置上的診斷資訊複本。</span><span class="sxs-lookup"><span data-stu-id="8ff19-159">If the user selects this option, the Feedback Hub stores a copy of the diagnostic information on the HoloLens device.</span></span> <span data-ttu-id="8ff19-160">使用者仍可存取此資訊（或使用該帳戶登入 HoloLens 的任何人）。</span><span class="sxs-lookup"><span data-stu-id="8ff19-160">This information remains accessible to the user (or anyone that uses that account to sign in to HoloLens).</span></span> <span data-ttu-id="8ff19-161">若要刪除此資訊，使用者必須擁有裝置的**裝置擁有**者或系統**管理員**許可權。</span><span class="sxs-lookup"><span data-stu-id="8ff19-161">To delete this information, a user must have **Device owner** or **Admin** permissions on the device.</span></span> <span data-ttu-id="8ff19-162">具有適當許可權的使用者可以登入意見反應中樞，選取 [**設定**] [  >  **查看診斷記錄**]，然後刪除資訊。</span><span class="sxs-lookup"><span data-stu-id="8ff19-162">A user who has the appropriate permissions can sign in to the Feedback Hub, select **Settings** > **View diagnostics logs**, and delete the information.</span></span>

## <span data-ttu-id="8ff19-163">[設定] 疑難排解</span><span class="sxs-lookup"><span data-stu-id="8ff19-163">Settings Troubleshooter</span></span>

<span data-ttu-id="8ff19-164">HoloLens 使用者可以使用裝置上的 [設定] 應用程式來疑難排解問題，並收集診斷資訊。</span><span class="sxs-lookup"><span data-stu-id="8ff19-164">A HoloLens user can use the Settings app on the device to troubleshoot problems and collect diagnostic information.</span></span> <span data-ttu-id="8ff19-165">若要這樣做，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="8ff19-165">To do this, follow these steps:</span></span>

1. <span data-ttu-id="8ff19-166">開啟 [設定] 應用程式，然後選取 [**更新 & 安全性**  >  **疑難排解**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="8ff19-166">Open the Settings app and select **Update & Security** > **Troubleshoot** page.</span></span>
1. <span data-ttu-id="8ff19-167">選取適當的區域，然後選取 [**開始**]。</span><span class="sxs-lookup"><span data-stu-id="8ff19-167">Select the appropriate area, and select **Start**.</span></span>
1. <span data-ttu-id="8ff19-168">再現問題。</span><span class="sxs-lookup"><span data-stu-id="8ff19-168">Reproduce the issue.</span></span>
1. <span data-ttu-id="8ff19-169">再現問題之後，請返回 [設定]，然後選取 [**停止**]。</span><span class="sxs-lookup"><span data-stu-id="8ff19-169">After you reproduce the issue, return to Settings and then select **Stop**.</span></span>

### <span data-ttu-id="8ff19-170">必要條件</span><span class="sxs-lookup"><span data-stu-id="8ff19-170">Prerequisites</span></span>

- <span data-ttu-id="8ff19-171">[設定] 應用程式已安裝在裝置上，且可供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="8ff19-171">The Settings app is installed on the device and is available to the user.</span></span>

### <span data-ttu-id="8ff19-172">資料位置、存取和保留</span><span class="sxs-lookup"><span data-stu-id="8ff19-172">Data locations, access, and retention</span></span>

<span data-ttu-id="8ff19-173">因為使用者會啟動資料收集，所以使用者會隱式同意診斷資訊的儲存。</span><span class="sxs-lookup"><span data-stu-id="8ff19-173">Because the user starts the data collection, the user implicitly consents to the storage of the diagnostic information.</span></span> <span data-ttu-id="8ff19-174">只有使用者，或使用者共用資料的任何人都可以存取資料。</span><span class="sxs-lookup"><span data-stu-id="8ff19-174">Only the user, or anyone with whom that the user shares the data, can access the data.</span></span>

<span data-ttu-id="8ff19-175">診斷資訊會儲存在裝置上。</span><span class="sxs-lookup"><span data-stu-id="8ff19-175">The diagnostic information is stored on the device.</span></span> <span data-ttu-id="8ff19-176">如果裝置已連線至使用者的電腦，資訊也會存放在電腦上的下列檔案中：</span><span class="sxs-lookup"><span data-stu-id="8ff19-176">If the device is connected to the user's computer, the information also resides on the computer in the following file:</span></span>

> <span data-ttu-id="8ff19-177">此 PC\\ \<*HoloLens device name*> \\Internal Storage\\Documents\\Trace \<*ddmmyyhhmmss*></span><span class="sxs-lookup"><span data-stu-id="8ff19-177">This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents\\Trace\<*ddmmyyhhmmss*>.etl</span></span>

> [!NOTE]  
> <span data-ttu-id="8ff19-178">在此檔案路徑和名稱中， \<*HoloLens device name*> 代表 HoloLens 裝置的名稱，並代表該檔案的 \<*ddmmyyhhmmss*> 建立日期和時間。</span><span class="sxs-lookup"><span data-stu-id="8ff19-178">In this file path and name, \<*HoloLens device name*> represents the name of the HoloLens device, and \<*ddmmyyhhmmss*> represents the date and time that the file was created.</span></span>

<span data-ttu-id="8ff19-179">診斷資訊會保留在這些位置，直到使用者將其刪除為止。</span><span class="sxs-lookup"><span data-stu-id="8ff19-179">The diagnostic information remains in these locations until the user deletes it.</span></span>

## <span data-ttu-id="8ff19-180">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="8ff19-180">DiagnosticLog CSP</span></span>

<span data-ttu-id="8ff19-181">在行動裝置管理（MDM）環境中，IT 系統管理員可以使用[DiagnosticLog configuration services 提供者（CSP）](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp)來設定登記的 HoloLens 裝置上的診斷設定。</span><span class="sxs-lookup"><span data-stu-id="8ff19-181">In a Mobile Device Management (MDM) environment, the IT administrator can use the the [DiagnosticLog configuration service provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) to configure diagnostic settings on enrolled HoloLens devices.</span></span> <span data-ttu-id="8ff19-182">IT 管理員可以設定這些設定，從已註冊的裝置收集記錄。</span><span class="sxs-lookup"><span data-stu-id="8ff19-182">The IT administrator can configure these settings to collect logs from enrolled devices.</span></span>

### <span data-ttu-id="8ff19-183">必要條件</span><span class="sxs-lookup"><span data-stu-id="8ff19-183">Prerequisites</span></span>

- <span data-ttu-id="8ff19-184">裝置已連線至網路。</span><span class="sxs-lookup"><span data-stu-id="8ff19-184">The device is connected to a network.</span></span>
- <span data-ttu-id="8ff19-185">裝置已在支援 DiagnosticLog CSP 的 MDM 環境中註冊。</span><span class="sxs-lookup"><span data-stu-id="8ff19-185">The device is enrolled in an MDM environment that supports the DiagnosticLog CSP.</span></span>

### <span data-ttu-id="8ff19-186">資料位置、存取和保留</span><span class="sxs-lookup"><span data-stu-id="8ff19-186">Data locations, access, and retention</span></span>

<span data-ttu-id="8ff19-187">因為裝置是受管理環境的一部分，所以使用者隱含同意診斷資訊的管理存取權。</span><span class="sxs-lookup"><span data-stu-id="8ff19-187">Because the device is part of the managed environment, the user implicitly consents to administrative access to diagnostic information.</span></span>

<span data-ttu-id="8ff19-188">IT 系統管理員使用 DiagnosticLog CSP 來設定資料儲存、保留及存取原則，包括控制下列專案的原則：</span><span class="sxs-lookup"><span data-stu-id="8ff19-188">The IT administrator uses the DiagnosticLog CSP to configure the data storage, retention, and access policies, including the policies that govern the following:</span></span>

- <span data-ttu-id="8ff19-189">儲存診斷資訊的雲端基礎結構。</span><span class="sxs-lookup"><span data-stu-id="8ff19-189">The cloud infrastructure that stores the diagnostic information.</span></span>
- <span data-ttu-id="8ff19-190">診斷資訊的保留期間。</span><span class="sxs-lookup"><span data-stu-id="8ff19-190">The retention period for the diagnostic information.</span></span>
- <span data-ttu-id="8ff19-191">控制診斷資訊存取權的許可權。</span><span class="sxs-lookup"><span data-stu-id="8ff19-191">Permissions that control access to the diagnostic information.</span></span>


