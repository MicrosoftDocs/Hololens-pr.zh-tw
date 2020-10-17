---
title: 透過 HoloLens 裝置收集與使用診斷資訊
description: 透過 HoloLens 裝置收集與使用診斷資訊
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
ms.openlocfilehash: e1302a3d482648b1ebbf7fee71ceec3ca4261d23
ms.sourcegitcommit: 87d503434339fc6c9b41aa9473e35ddfde845cac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "11120144"
---
# <span data-ttu-id="70e62-103">透過 HoloLens 裝置收集與使用診斷資訊</span><span class="sxs-lookup"><span data-stu-id="70e62-103">Collect and use diagnostic information from HoloLens devices</span></span>

<span data-ttu-id="70e62-104">HoloLens 使用者與系統管理員可以從四種不同的方法中選擇，從 HoloLens 收集診斷資訊：</span><span class="sxs-lookup"><span data-stu-id="70e62-104">HoloLens users and administrators can choose from among four different methods to collect diagnostic information from HoloLens:</span></span>

- <span data-ttu-id="70e62-105">意見反應中心應用程式</span><span class="sxs-lookup"><span data-stu-id="70e62-105">Feedback Hub app</span></span>
- <span data-ttu-id="70e62-106">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="70e62-106">DiagnosticLog CSP</span></span>
- <span data-ttu-id="70e62-107">設定 App</span><span class="sxs-lookup"><span data-stu-id="70e62-107">Settings app</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="70e62-108">裝置診斷記錄包含個人可識別資訊 (PII) ，例如使用者在一般作業中啟動哪些程式或應用程式。</span><span class="sxs-lookup"><span data-stu-id="70e62-108">Device diagnostic logs contain personally identifiable information (PII), such as about what processes or applications the user starts during typical operations.</span></span> <span data-ttu-id="70e62-109">如果有多個使用者共用 HoloLens 裝置 (例如，使用者使用不同的 Microsoft Azure Active Directory 登入相同的裝置 (AAD) 帳戶) 診斷記錄可能包含適用于多個使用者的 PII 資訊。</span><span class="sxs-lookup"><span data-stu-id="70e62-109">When multiple users share a HoloLens device (for example, users sign in to the same device by using different Microsoft Azure Active Directory (AAD) accounts) the diagnostic logs may contain PII information that applies to multiple users.</span></span> <span data-ttu-id="70e62-110">如需詳細資訊，請參閱 [Microsoft 隱私權聲明](https://privacy.microsoft.com/privacystatement)。</span><span class="sxs-lookup"><span data-stu-id="70e62-110">For more information, see [Microsoft Privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

<span data-ttu-id="70e62-111">下表比較三個集合方法。</span><span class="sxs-lookup"><span data-stu-id="70e62-111">The following table compares the three collection methods.</span></span> <span data-ttu-id="70e62-112">在表格後面的章節中，方法名稱連結至更詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="70e62-112">The method names link to more detailed information in the sections that follow the table.</span></span>

|<span data-ttu-id="70e62-113">方法</span><span class="sxs-lookup"><span data-stu-id="70e62-113">Method</span></span> |<span data-ttu-id="70e62-114">必要條件</span><span class="sxs-lookup"><span data-stu-id="70e62-114">Prerequisites</span></span> |<span data-ttu-id="70e62-115">資料位置</span><span class="sxs-lookup"><span data-stu-id="70e62-115">Data locations</span></span> |<span data-ttu-id="70e62-116">資料存取及使用</span><span class="sxs-lookup"><span data-stu-id="70e62-116">Data access and use</span></span> |<span data-ttu-id="70e62-117">資料保留</span><span class="sxs-lookup"><span data-stu-id="70e62-117">Data retention</span></span> |
| --- | --- | --- | --- | --- |
|[<span data-ttu-id="70e62-118">意見反應中樞</span><span class="sxs-lookup"><span data-stu-id="70e62-118">Feedback Hub</span></span>](#feedback-hub) |<span data-ttu-id="70e62-119">網路和網際網路連線</span><span class="sxs-lookup"><span data-stu-id="70e62-119">Network and internet connection</span></span><br /><br /><span data-ttu-id="70e62-120">意見反應中心應用程式</span><span class="sxs-lookup"><span data-stu-id="70e62-120">Feedback Hub app</span></span><br /><br /><span data-ttu-id="70e62-121">將檔案上傳到 Microsoft 雲端的許可權</span><span class="sxs-lookup"><span data-stu-id="70e62-121">Permission to upload files to the Microsoft cloud</span></span> |<span data-ttu-id="70e62-122">Microsoft 雲端</span><span class="sxs-lookup"><span data-stu-id="70e62-122">Microsoft cloud</span></span><br /><br /><span data-ttu-id="70e62-123">HoloLens 裝置 (選用) </span><span class="sxs-lookup"><span data-stu-id="70e62-123">HoloLens device (optional)</span></span> |<span data-ttu-id="70e62-124">使用者要求協助、同意使用條款及上傳資料</span><span class="sxs-lookup"><span data-stu-id="70e62-124">User requests assistance, agrees to the terms of use, and uploads the data</span></span><br /><br /><span data-ttu-id="70e62-125">Microsoft 員工會以與使用條款相符的方式來查看資料</span><span class="sxs-lookup"><span data-stu-id="70e62-125">Microsoft employees view the data, as consistent with the terms of use</span></span> |<span data-ttu-id="70e62-126">雲端中的資料會在下一代隱私權 (NGP) 所定義的期間保留。</span><span class="sxs-lookup"><span data-stu-id="70e62-126">Data in the cloud is retained for the period that is defined by Next Generation Privacy (NGP).</span></span> <span data-ttu-id="70e62-127">然後，系統會自動刪除該資料。</span><span class="sxs-lookup"><span data-stu-id="70e62-127">Then the data is deleted automatically.</span></span><br /><br /><span data-ttu-id="70e62-128">裝置上的資料可隨時由擁有 **裝置擁有** 者或系統 **管理員** 許可權的使用者刪除。</span><span class="sxs-lookup"><span data-stu-id="70e62-128">Data on the device can be deleted at any time by a user who has **Device owner** or **Admin** permissions.</span></span> |
|[<span data-ttu-id="70e62-129">[設定] 疑難排解</span><span class="sxs-lookup"><span data-stu-id="70e62-129">Settings Troubleshooter</span></span>](#settings-troubleshooter) |<span data-ttu-id="70e62-130">設定 App</span><span class="sxs-lookup"><span data-stu-id="70e62-130">Settings app</span></span> |<span data-ttu-id="70e62-131">HoloLens 裝置</span><span class="sxs-lookup"><span data-stu-id="70e62-131">HoloLens device</span></span><br /><br /><span data-ttu-id="70e62-132">已連接的電腦 (選用) </span><span class="sxs-lookup"><span data-stu-id="70e62-132">Connected computer (optional)</span></span> |<span data-ttu-id="70e62-133">使用者會儲存資料，除非使用者明確與其他使用者共用資料，否則只有使用者存取資料 () 。</span><span class="sxs-lookup"><span data-stu-id="70e62-133">The user stores the data, and only the user accesses the data (unless the user specifically shares the data with another user).</span></span> |<span data-ttu-id="70e62-134">資料會保留，直到使用者刪除為止。</span><span class="sxs-lookup"><span data-stu-id="70e62-134">The data is retained until the user deletes it.\*</span></span> |
|[<span data-ttu-id="70e62-135">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="70e62-135">DiagnosticLog CSP</span></span>](#diagnosticlog-csp) |<span data-ttu-id="70e62-136">網路連線</span><span class="sxs-lookup"><span data-stu-id="70e62-136">Network connection</span></span><br /><br /><span data-ttu-id="70e62-137">支援 DiagnosticLog CSP 的 MDM 環境</span><span class="sxs-lookup"><span data-stu-id="70e62-137">MDM environment that supports the DiagnosticLog CSP</span></span> |<span data-ttu-id="70e62-138">系統管理員設定儲存位置</span><span class="sxs-lookup"><span data-stu-id="70e62-138">Administrator configures storage locations</span></span> |<span data-ttu-id="70e62-139">在受管理的環境中，使用者隱含地同意資料的管理員存取權。</span><span class="sxs-lookup"><span data-stu-id="70e62-139">In the managed environment, the user implicitly consents to administrator access to the data.</span></span><br /><br /><span data-ttu-id="70e62-140">系統管理員設定存取角色和許可權。</span><span class="sxs-lookup"><span data-stu-id="70e62-140">Administrator configures access roles and permissions.</span></span> | <span data-ttu-id="70e62-141">系統管理員配置保留原則。</span><span class="sxs-lookup"><span data-stu-id="70e62-141">Administrator configures retention policy.</span></span> |
|[<span data-ttu-id="70e62-142">離線診斷</span><span class="sxs-lookup"><span data-stu-id="70e62-142">Offline diagnostics</span></span>](#offline-diagnostics) |<span data-ttu-id="70e62-143">裝置配置：</span><span class="sxs-lookup"><span data-stu-id="70e62-143">Device configuration:</span></span><ul><li><span data-ttu-id="70e62-144">已電源開啟並已連線至電腦</span><span class="sxs-lookup"><span data-stu-id="70e62-144">Powered on and connected to computer</span></span></li><li><span data-ttu-id="70e62-145">[電源] 和 [音量] 按鈕正常運作</span><span class="sxs-lookup"><span data-stu-id="70e62-145">Power and Volume buttons functioning</span></span></li></ul> |<span data-ttu-id="70e62-146">HoloLens 裝置</span><span class="sxs-lookup"><span data-stu-id="70e62-146">HoloLens device</span></span><br /><br /><span data-ttu-id="70e62-147">已連接的電腦</span><span class="sxs-lookup"><span data-stu-id="70e62-147">Connected computer</span></span> |<span data-ttu-id="70e62-148">使用者會儲存資料，除非使用者明確與其他使用者共用資料，否則只有使用者存取資料 () 。</span><span class="sxs-lookup"><span data-stu-id="70e62-148">The user stores the data, and only the user accesses the data (unless the user specifically shares the data with another user).</span></span> |<span data-ttu-id="70e62-149">資料會保留，直到使用者刪除為止。</span><span class="sxs-lookup"><span data-stu-id="70e62-149">The data is retained until the user deletes it.</span></span> | 


-   <span data-ttu-id="70e62-150">最終使用者負責與其他人共用記錄。</span><span class="sxs-lookup"><span data-stu-id="70e62-150">End-user is responsible for sharing the logs responsibly with someone else.</span></span> <span data-ttu-id="70e62-151">這些檔案在與客戶服務和支援人員聯繫時主要很有用。</span><span class="sxs-lookup"><span data-stu-id="70e62-151">These files are primarily useful when contacting customer service and support.</span></span>  

## <span data-ttu-id="70e62-152">意見反應中樞</span><span class="sxs-lookup"><span data-stu-id="70e62-152">Feedback Hub</span></span>

<span data-ttu-id="70e62-153">HoloLens 使用者可以使用 Microsoft 意見中心桌面應用程式，傳送診斷資訊給 Microsoft 支援。</span><span class="sxs-lookup"><span data-stu-id="70e62-153">A HoloLens user can use the Microsoft Feedback Hub desktop app to send diagnostic information to Microsoft Support.</span></span> <span data-ttu-id="70e62-154">如需詳細資訊及完整指示，請參閱 [向我們提供意見](hololens-feedback.md)反應。</span><span class="sxs-lookup"><span data-stu-id="70e62-154">For details and complete instructions, see [Give us feedback](hololens-feedback.md).</span></span>  

> [!NOTE]  
> <span data-ttu-id="70e62-155">**商業或企業使用者：** 如果您使用意見反應中樞 app 來報告與 MDM、提供或任何其他裝置管理功能相關的問題，請將應用程式類別變更為 [**企業管理**  >  **裝置] 類別**。</span><span class="sxs-lookup"><span data-stu-id="70e62-155">**Commercial or enterprise users:** If you use the Feedback Hub app to report a problem that relates to MDM, provisioning, or any other device management aspect, change the app category to **Enterprise Management** > **Device category**.</span></span>

### <span data-ttu-id="70e62-156">必要條件</span><span class="sxs-lookup"><span data-stu-id="70e62-156">Prerequisites</span></span>

- <span data-ttu-id="70e62-157">裝置已連線至網路。</span><span class="sxs-lookup"><span data-stu-id="70e62-157">The device is connected to a network.</span></span>
- <span data-ttu-id="70e62-158">您可以在使用者的桌上型電腦上使用「意見反應中樞」 app，使用者可以將檔案上傳到 Microsoft 雲端。</span><span class="sxs-lookup"><span data-stu-id="70e62-158">The Feedback Hub app is available on the user's desktop computer, and the user can upload files to the Microsoft cloud.</span></span>

### <span data-ttu-id="70e62-159">資料位置、存取和保留</span><span class="sxs-lookup"><span data-stu-id="70e62-159">Data locations, access, and retention</span></span>

<span data-ttu-id="70e62-160">透過同意意見反應中樞的使用條款，使用者就能明確地同意資料 (的儲存與使用狀況，如該合約) 所定義。</span><span class="sxs-lookup"><span data-stu-id="70e62-160">By agreeing to the terms-of-use of the Feedback Hub, the user explicitly consents to the storage and usage of the data (as defined by that agreement).</span></span>

<span data-ttu-id="70e62-161">意見反應中心提供兩個位置供使用者儲存診斷資訊：</span><span class="sxs-lookup"><span data-stu-id="70e62-161">The Feedback Hub provides two places for the user to store diagnostic information:</span></span>

- <span data-ttu-id="70e62-162">**Microsoft 雲端**。</span><span class="sxs-lookup"><span data-stu-id="70e62-162">**The Microsoft cloud**.</span></span> <span data-ttu-id="70e62-163">使用者使用「意見反應中樞」 app 上傳的資料，會儲存在與下一代隱私權 (NGP) 需求相符的天數。</span><span class="sxs-lookup"><span data-stu-id="70e62-163">Data that the user uploads by using the Feedback Hub app is stored for the number of days that is consistent with Next Generation Privacy (NGP) requirements.</span></span> <span data-ttu-id="70e62-164">Microsoft 員工可以使用 NGP 相容的檢視器，在此期間存取訊號。</span><span class="sxs-lookup"><span data-stu-id="70e62-164">Microsoft employees can use an NGP-compliant viewer to access the information during this period.</span></span>
   > [!NOTE]  
   > <span data-ttu-id="70e62-165">這些需求適用于所有意見反應中樞類別中的資料。</span><span class="sxs-lookup"><span data-stu-id="70e62-165">These requirements apply to data in all Feedback Hub categories.</span></span>

- <span data-ttu-id="70e62-166">**HoloLens 裝置**。</span><span class="sxs-lookup"><span data-stu-id="70e62-166">**The HoloLens device**.</span></span> <span data-ttu-id="70e62-167">當您在意見反應中樞中歸檔報表時，使用者可以選取 [ **儲存在提供意見反應時建立的診斷與附件的本機複本**]。</span><span class="sxs-lookup"><span data-stu-id="70e62-167">While filing a report in Feedback Hub, the user can select **Save a local copy of diagnostics and attachments created when giving feedback**.</span></span> <span data-ttu-id="70e62-168">如果使用者選取此選項，意見反應中心就會儲存 HoloLens 裝置上的診斷資訊複本。</span><span class="sxs-lookup"><span data-stu-id="70e62-168">If the user selects this option, the Feedback Hub stores a copy of the diagnostic information on the HoloLens device.</span></span> <span data-ttu-id="70e62-169">使用者 (或任何使用該帳戶登入 HoloLens) 的人，就能繼續存取此資訊。</span><span class="sxs-lookup"><span data-stu-id="70e62-169">This information remains accessible to the user (or anyone that uses that account to sign in to HoloLens).</span></span> <span data-ttu-id="70e62-170">若要刪除此資訊，使用者必須擁有裝置的 **裝置擁有** 者或系統 **管理員** 許可權。</span><span class="sxs-lookup"><span data-stu-id="70e62-170">To delete this information, a user must have **Device owner** or **Admin** permissions on the device.</span></span> <span data-ttu-id="70e62-171">具有適當許可權的使用者可以登入意見反應中樞，選取 [**設定**] [  >  **查看診斷記錄**]，然後刪除資訊。</span><span class="sxs-lookup"><span data-stu-id="70e62-171">A user who has the appropriate permissions can sign in to the Feedback Hub, select **Settings** > **View diagnostics logs**, and delete the information.</span></span>

## <span data-ttu-id="70e62-172">[設定] 疑難排解</span><span class="sxs-lookup"><span data-stu-id="70e62-172">Settings Troubleshooter</span></span>

<span data-ttu-id="70e62-173">HoloLens 使用者可以使用裝置上的 [設定] 應用程式來疑難排解問題，並收集診斷資訊。</span><span class="sxs-lookup"><span data-stu-id="70e62-173">A HoloLens user can use the Settings app on the device to troubleshoot problems and collect diagnostic information.</span></span> <span data-ttu-id="70e62-174">若要這樣做，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="70e62-174">To do this, follow these steps:</span></span>

1. <span data-ttu-id="70e62-175">開啟 [設定] 應用程式，然後選取 [**更新 & 安全性**  >  **疑難排解**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="70e62-175">Open the Settings app and select **Update & Security** > **Troubleshoot** page.</span></span>
1. <span data-ttu-id="70e62-176">選取適當的區域，然後選取 [ **開始**]。</span><span class="sxs-lookup"><span data-stu-id="70e62-176">Select the appropriate area, and select **Start**.</span></span>
1. <span data-ttu-id="70e62-177">再現問題。</span><span class="sxs-lookup"><span data-stu-id="70e62-177">Reproduce the issue.</span></span>
1. <span data-ttu-id="70e62-178">再現問題之後，請返回 [設定]，然後選取 [ **停止**]。</span><span class="sxs-lookup"><span data-stu-id="70e62-178">After you reproduce the issue, return to Settings and then select **Stop**.</span></span>

### <span data-ttu-id="70e62-179">必要條件</span><span class="sxs-lookup"><span data-stu-id="70e62-179">Prerequisites</span></span>

- <span data-ttu-id="70e62-180">[設定] 應用程式已安裝在裝置上，且可供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="70e62-180">The Settings app is installed on the device and is available to the user.</span></span>

### <span data-ttu-id="70e62-181">資料位置、存取和保留</span><span class="sxs-lookup"><span data-stu-id="70e62-181">Data locations, access, and retention</span></span>

<span data-ttu-id="70e62-182">因為使用者會啟動資料收集，所以使用者會隱式同意診斷資訊的儲存。</span><span class="sxs-lookup"><span data-stu-id="70e62-182">Because the user starts the data collection, the user implicitly consents to the storage of the diagnostic information.</span></span> <span data-ttu-id="70e62-183">只有使用者，或使用者共用資料的任何人都可以存取資料。</span><span class="sxs-lookup"><span data-stu-id="70e62-183">Only the user, or anyone with whom that the user shares the data, can access the data.</span></span>

<span data-ttu-id="70e62-184">診斷資訊會儲存在裝置上。</span><span class="sxs-lookup"><span data-stu-id="70e62-184">The diagnostic information is stored on the device.</span></span> <span data-ttu-id="70e62-185">如果裝置已連線至使用者的電腦，資訊也會存放在電腦上的下列檔案中：</span><span class="sxs-lookup"><span data-stu-id="70e62-185">If the device is connected to the user's computer, the information also resides on the computer in the following file:</span></span>

> <span data-ttu-id="70e62-186">此 PC\\ \<*HoloLens device name*> \\Internal Storage\\Documents\\Trace \<*ddmmyyhhmmss*></span><span class="sxs-lookup"><span data-stu-id="70e62-186">This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents\\Trace\<*ddmmyyhhmmss*>.etl</span></span>

> [!NOTE]  
> <span data-ttu-id="70e62-187">在此檔案路徑和名稱中， \<*HoloLens device name*> 代表 HoloLens 裝置的名稱，並代表該檔案的 \<*ddmmyyhhmmss*> 建立日期和時間。</span><span class="sxs-lookup"><span data-stu-id="70e62-187">In this file path and name, \<*HoloLens device name*> represents the name of the HoloLens device, and \<*ddmmyyhhmmss*> represents the date and time that the file was created.</span></span>

<span data-ttu-id="70e62-188">診斷資訊會保留在這些位置，直到使用者將其刪除為止。</span><span class="sxs-lookup"><span data-stu-id="70e62-188">The diagnostic information remains in these locations until the user deletes it.</span></span>

## <span data-ttu-id="70e62-189">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="70e62-189">DiagnosticLog CSP</span></span>

<span data-ttu-id="70e62-190">在行動裝置管理 (MDM) 環境中，IT 系統管理員可以使用 [DiagnosticLog 配置服務提供者 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) 來設定登記的 HoloLens 裝置上的診斷設定。</span><span class="sxs-lookup"><span data-stu-id="70e62-190">In a Mobile Device Management (MDM) environment, the IT administrator can use the the [DiagnosticLog configuration service provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) to configure diagnostic settings on enrolled HoloLens devices.</span></span> <span data-ttu-id="70e62-191">IT 管理員可以設定這些設定，從已註冊的裝置收集記錄。</span><span class="sxs-lookup"><span data-stu-id="70e62-191">The IT administrator can configure these settings to collect logs from enrolled devices.</span></span>

### <span data-ttu-id="70e62-192">必要條件</span><span class="sxs-lookup"><span data-stu-id="70e62-192">Prerequisites</span></span>

- <span data-ttu-id="70e62-193">裝置已連線至網路。</span><span class="sxs-lookup"><span data-stu-id="70e62-193">The device is connected to a network.</span></span>
- <span data-ttu-id="70e62-194">裝置已在支援 DiagnosticLog CSP 的 MDM 環境中註冊。</span><span class="sxs-lookup"><span data-stu-id="70e62-194">The device is enrolled in an MDM environment that supports the DiagnosticLog CSP.</span></span>

### <span data-ttu-id="70e62-195">資料位置、存取和保留</span><span class="sxs-lookup"><span data-stu-id="70e62-195">Data locations, access, and retention</span></span>

<span data-ttu-id="70e62-196">因為裝置是受管理環境的一部分，所以使用者隱含同意診斷資訊的管理存取權。</span><span class="sxs-lookup"><span data-stu-id="70e62-196">Because the device is part of the managed environment, the user implicitly consents to administrative access to diagnostic information.</span></span>

<span data-ttu-id="70e62-197">IT 系統管理員使用 DiagnosticLog CSP 來設定資料儲存、保留及存取原則，包括控制下列專案的原則：</span><span class="sxs-lookup"><span data-stu-id="70e62-197">The IT administrator uses the DiagnosticLog CSP to configure the data storage, retention, and access policies, including the policies that govern the following:</span></span>

- <span data-ttu-id="70e62-198">儲存診斷資訊的雲端基礎結構。</span><span class="sxs-lookup"><span data-stu-id="70e62-198">The cloud infrastructure that stores the diagnostic information.</span></span>
- <span data-ttu-id="70e62-199">診斷資訊的保留期間。</span><span class="sxs-lookup"><span data-stu-id="70e62-199">The retention period for the diagnostic information.</span></span>
- <span data-ttu-id="70e62-200">控制診斷資訊存取權的許可權。</span><span class="sxs-lookup"><span data-stu-id="70e62-200">Permissions that control access to the diagnostic information.</span></span>

## <span data-ttu-id="70e62-201">離線診斷</span><span class="sxs-lookup"><span data-stu-id="70e62-201">Offline diagnostics</span></span>
<span data-ttu-id="70e62-202">在裝置無法透過意見反應中樞或設定疑難排解工具收集診斷的情況下，您可以手動收集診斷。</span><span class="sxs-lookup"><span data-stu-id="70e62-202">In situations where the device is not able to collect diagnostics via Feedback Hub or the Setting Troubleshooter, you can collect diagnostics manually.</span></span> <span data-ttu-id="70e62-203">需要這麼做的一種情況是裝置無法連線到 Wi-fi。</span><span class="sxs-lookup"><span data-stu-id="70e62-203">One scenario where this is necessary is when the device cannot connect to Wi-Fi.</span></span> <span data-ttu-id="70e62-204">診斷程式會從裝置收集損毀轉儲與記錄，以協助 Microsoft 支援工程師隔離問題。</span><span class="sxs-lookup"><span data-stu-id="70e62-204">The diagnostics collect crash dumps and logs from the device that help a Microsoft support engineer isolate issues.</span></span>

<span data-ttu-id="70e62-205">當裝置透過 USB 纜線連線到電腦之後，在檔案資源管理器中顯示時，就能正常運作。</span><span class="sxs-lookup"><span data-stu-id="70e62-205">This works when the device shows up in File Explorer after connecting it to a PC via a USB cable.</span></span> 

> [!NOTE]
> <span data-ttu-id="70e62-206">只有在使用者使用 OOBE 或 [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) 原則時，才會啟用 [離線診斷] 設定為 [完整 (在 Hololens) 上為預設值。</span><span class="sxs-lookup"><span data-stu-id="70e62-206">Offline diagnostics is only enabled when user is either going through OOBE or [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) policy value is set to Full (Basic is default value on Hololens).</span></span> 

<span data-ttu-id="70e62-207">如果裝置已鎖定，則不會顯示記錄。</span><span class="sxs-lookup"><span data-stu-id="70e62-207">If device is locked then logs won't appear.</span></span> <span data-ttu-id="70e62-208">若要停用離線診斷，請移至 [**設定] App > 隱私權**] 頁面，然後選取 [在**診斷資料**中**基本**]</span><span class="sxs-lookup"><span data-stu-id="70e62-208">To disable Offline diagnostics, go to **Settings App > Privacy** page and select **Basic** in **Diagnostic Data**.</span></span> <span data-ttu-id="70e62-209">在離線診斷依賴遙測設定的組建上，它只會影響是否收集任何記錄。</span><span class="sxs-lookup"><span data-stu-id="70e62-209">On builds where offline diagnostics depends on telemetry setting, it only impacts whether any logs are collected or not.</span></span> <span data-ttu-id="70e62-210">它不會影響收集的檔案。</span><span class="sxs-lookup"><span data-stu-id="70e62-210">It does not impact what files are collected.</span></span>

<span data-ttu-id="70e62-211">觀看這段影片以深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="70e62-211">Watch this video to learn more.</span></span> 

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

<span data-ttu-id="70e62-212">請依照下列步驟來收集診斷資訊：</span><span class="sxs-lookup"><span data-stu-id="70e62-212">Follow these steps to collect diagnostics:</span></span>
1.  <span data-ttu-id="70e62-213">將裝置與 USB 纜線連接至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="70e62-213">Connect the device with a USB cable to your PC.</span></span>
2.  <span data-ttu-id="70e62-214">在您電腦上的檔案資源管理器中，流覽至「 **這台電腦 \<hololens-device> \Internal 儲存空間**」。</span><span class="sxs-lookup"><span data-stu-id="70e62-214">In File Explorer on your PC, navigate to **'This PC\<hololens-device>\Internal Storage'**.</span></span>
3.  <span data-ttu-id="70e62-215">如果未顯示 **內部儲存** 資料夾，表示裝置正在等待使用者登入。</span><span class="sxs-lookup"><span data-stu-id="70e62-215">If the **Internal Storage** folder does not show up, the device is waiting for a user to sign in.</span></span> <span data-ttu-id="70e62-216">您可以登入或關閉裝置，只要按住電源按鈕10秒。</span><span class="sxs-lookup"><span data-stu-id="70e62-216">Either sign-in or power cycle the device by holding the POWER button down for 10 seconds.</span></span>
4.  <span data-ttu-id="70e62-217">按下，然後立即放開 [ **電源 + 音量** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="70e62-217">Press and immediately release the **POWER + VOLUME DOWN** buttons together.</span></span>
5.  <span data-ttu-id="70e62-218">稍等一分鐘，讓裝置準備 zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="70e62-218">Wait a minute for the device to prepare the zip archives.</span></span> <span data-ttu-id="70e62-219"> (名為 HololensDiagnostics 的臨時檔案在裝置產生 zip 存檔時可能會顯示。</span><span class="sxs-lookup"><span data-stu-id="70e62-219">(A temporary file named HololensDiagnostics.temp may become visible while the device generates the zip archives.</span></span> <span data-ttu-id="70e62-220">請勿存取或儲存該檔案。</span><span class="sxs-lookup"><span data-stu-id="70e62-220">Do not access or save that file.</span></span> <span data-ttu-id="70e62-221">程式完成後，zip 存檔就會取代該進程。 ) </span><span class="sxs-lookup"><span data-stu-id="70e62-221">When the process finishes it will be replaced by the zip archives.)</span></span>
6.  <span data-ttu-id="70e62-222">重新整理檔資源管理器，然後流覽至 [ **\ 檔** ] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="70e62-222">Refresh file explorer, and navigate to the **'\Documents'** folder.</span></span>
7.  <span data-ttu-id="70e62-223">複製診斷程式 ZIP 檔案，並與 Microsoft 支援小組共用。</span><span class="sxs-lookup"><span data-stu-id="70e62-223">Copy the diagnostics ZIP files and share them with the Microsoft support team.</span></span>

> [!NOTE]
> <span data-ttu-id="70e62-224">某些診斷 ZIP 檔案可能包含個人可識別的資訊。</span><span class="sxs-lookup"><span data-stu-id="70e62-224">Some of the diagnostics ZIP files may contain personally identifiable information.</span></span>



