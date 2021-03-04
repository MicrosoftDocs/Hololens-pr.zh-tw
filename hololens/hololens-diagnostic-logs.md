---
title: 透過 HoloLens 裝置收集與使用診斷資訊
description: 瞭解如何收集、使用及保留 HoloLens 裝置中的診斷資訊。
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
ms.openlocfilehash: c8d9aa9fecff74a04e3f7cb395bffe5d239e18cf
ms.sourcegitcommit: 7791e470fc2e03bdf51b19a816d7215018772860
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "11387517"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a><span data-ttu-id="d9f54-103">透過 HoloLens 裝置收集與使用診斷資訊</span><span class="sxs-lookup"><span data-stu-id="d9f54-103">Collect and use diagnostic information from HoloLens devices</span></span>

<span data-ttu-id="d9f54-104">HoloLens 使用者和系統管理員可以選擇從 HoloLens 收集診斷資訊的四種不同方法：</span><span class="sxs-lookup"><span data-stu-id="d9f54-104">HoloLens users and administrators can choose from among four different methods to collect diagnostic information from HoloLens:</span></span>

- <span data-ttu-id="d9f54-105">意見回饋中樞應用程式</span><span class="sxs-lookup"><span data-stu-id="d9f54-105">Feedback Hub app</span></span>
- <span data-ttu-id="d9f54-106">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="d9f54-106">DiagnosticLog CSP</span></span>
- <span data-ttu-id="d9f54-107">設定 App</span><span class="sxs-lookup"><span data-stu-id="d9f54-107">Settings app</span></span>
- <span data-ttu-id="d9f54-108">離線診斷</span><span class="sxs-lookup"><span data-stu-id="d9f54-108">Offline Diagnostics</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="d9f54-109">裝置診斷記錄包含 PII (個人標識) ，例如使用者于一般作業期間啟動哪些程式或應用程式。</span><span class="sxs-lookup"><span data-stu-id="d9f54-109">Device diagnostic logs contain personally identifiable information (PII), such as about what processes or applications the user starts during typical operations.</span></span> <span data-ttu-id="d9f54-110">例如，當多個使用者共用 HoloLens 裝置 (時，使用者使用不同的 Microsoft Azure Active Directory (Azure AD) 帳戶) 而使用同一個裝置時) 診斷記錄可能會包含適用于多個使用者的 PII 資訊。</span><span class="sxs-lookup"><span data-stu-id="d9f54-110">When multiple users share a HoloLens device (for example, users sign in to the same device by using different Microsoft Azure Active Directory (Azure AD) accounts) the diagnostic logs may contain PII information that applies to multiple users.</span></span> <span data-ttu-id="d9f54-111">詳細資訊請參閱 Microsoft [隱私權聲明](https://privacy.microsoft.com/privacystatement)。</span><span class="sxs-lookup"><span data-stu-id="d9f54-111">For more information, see [Microsoft Privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

<span data-ttu-id="d9f54-112">下表比較了不同的集合方法。</span><span class="sxs-lookup"><span data-stu-id="d9f54-112">The following table compares different collection methods.</span></span> <span data-ttu-id="d9f54-113">方法名稱會連結至資料表後各節中更詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="d9f54-113">The method names link to more detailed information in the sections that follow the table.</span></span>

|<span data-ttu-id="d9f54-114">方法</span><span class="sxs-lookup"><span data-stu-id="d9f54-114">Method</span></span> |<span data-ttu-id="d9f54-115">必要條件</span><span class="sxs-lookup"><span data-stu-id="d9f54-115">Prerequisites</span></span> |<span data-ttu-id="d9f54-116">資料位置</span><span class="sxs-lookup"><span data-stu-id="d9f54-116">Data locations</span></span> |<span data-ttu-id="d9f54-117">資料存取和使用</span><span class="sxs-lookup"><span data-stu-id="d9f54-117">Data access and use</span></span> |<span data-ttu-id="d9f54-118">資料保留</span><span class="sxs-lookup"><span data-stu-id="d9f54-118">Data retention</span></span> |
| --- | --- | --- | --- | --- |
|[<span data-ttu-id="d9f54-119">意見反應中樞</span><span class="sxs-lookup"><span data-stu-id="d9f54-119">Feedback Hub</span></span>](#feedback-hub) |<span data-ttu-id="d9f54-120">網路和網際網路連接</span><span class="sxs-lookup"><span data-stu-id="d9f54-120">Network and internet connection</span></span><br /><br /><span data-ttu-id="d9f54-121">意見回饋中樞應用程式</span><span class="sxs-lookup"><span data-stu-id="d9f54-121">Feedback Hub app</span></span><br /><br /><span data-ttu-id="d9f54-122">將檔案上傳到 Microsoft 雲端的許可權</span><span class="sxs-lookup"><span data-stu-id="d9f54-122">Permission to upload files to the Microsoft cloud</span></span> |<span data-ttu-id="d9f54-123">Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="d9f54-123">Microsoft cloud</span></span><br /><br /><span data-ttu-id="d9f54-124">HoloLens 裝置 (選) </span><span class="sxs-lookup"><span data-stu-id="d9f54-124">HoloLens device (optional)</span></span> |<span data-ttu-id="d9f54-125">使用者要求協助、同意使用條款，並上傳資料</span><span class="sxs-lookup"><span data-stu-id="d9f54-125">User requests assistance, agrees to the terms of use, and uploads the data</span></span><br /><br /><span data-ttu-id="d9f54-126">Microsoft 員工會以與使用條款一致的方式查看資料</span><span class="sxs-lookup"><span data-stu-id="d9f54-126">Microsoft employees view the data, as consistent with the terms of use</span></span> |<span data-ttu-id="d9f54-127">雲端資料會保留由 NGP 新一代隱私權 (定義的) 。</span><span class="sxs-lookup"><span data-stu-id="d9f54-127">Data in the cloud is retained for the period that is defined by Next Generation Privacy (NGP).</span></span> <span data-ttu-id="d9f54-128">然後會自動刪除資料。</span><span class="sxs-lookup"><span data-stu-id="d9f54-128">Then the data is deleted automatically.</span></span><br /><br /><span data-ttu-id="d9f54-129">擁有裝置擁有者或系統管理員許可權的使用者，隨時都可以刪除裝置**上**的資料。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="d9f54-129">Data on the device can be deleted at any time by a user who has **Device owner** or **Admin** permissions.</span></span> |
|[<span data-ttu-id="d9f54-130">設定疑難排解員</span><span class="sxs-lookup"><span data-stu-id="d9f54-130">Settings Troubleshooter</span></span>](#settings-troubleshooter) |<span data-ttu-id="d9f54-131">設定 App</span><span class="sxs-lookup"><span data-stu-id="d9f54-131">Settings app</span></span> |<span data-ttu-id="d9f54-132">HoloLens 裝置</span><span class="sxs-lookup"><span data-stu-id="d9f54-132">HoloLens device</span></span><br /><br /><span data-ttu-id="d9f54-133">已連接的電腦 (選) </span><span class="sxs-lookup"><span data-stu-id="d9f54-133">Connected computer (optional)</span></span> |<span data-ttu-id="d9f54-134">除非使用者特別與其他使用者共用資料，否則使用者會儲存資料，而且只有使用者 (存取資料) 。</span><span class="sxs-lookup"><span data-stu-id="d9f54-134">The user stores the data, and only the user accesses the data (unless the user specifically shares the data with another user).</span></span> |<span data-ttu-id="d9f54-135">資料會保留在裝置上，直到使用者刪除資料。\*</span><span class="sxs-lookup"><span data-stu-id="d9f54-135">The data is retained on device until the user deletes it.\*</span></span> |
|[<span data-ttu-id="d9f54-136">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="d9f54-136">DiagnosticLog CSP</span></span>](#diagnosticlog-csp) |<span data-ttu-id="d9f54-137">網路連線</span><span class="sxs-lookup"><span data-stu-id="d9f54-137">Network connection</span></span><br /><br /><span data-ttu-id="d9f54-138">支援 DiagnosticLog CSP 的 MDM 環境</span><span class="sxs-lookup"><span data-stu-id="d9f54-138">MDM environment that supports the DiagnosticLog CSP</span></span> |<span data-ttu-id="d9f54-139">系統管理員設定儲存位置</span><span class="sxs-lookup"><span data-stu-id="d9f54-139">Administrator configures storage locations</span></span> |<span data-ttu-id="d9f54-140">在受管理的環境中，使用者隱含地同意系統管理員存取資料。</span><span class="sxs-lookup"><span data-stu-id="d9f54-140">In the managed environment, the user implicitly consents to administrator access to the data.</span></span><br /><br /><span data-ttu-id="d9f54-141">系統管理員設定存取角色和許可權。</span><span class="sxs-lookup"><span data-stu-id="d9f54-141">Administrator configures access roles and permissions.</span></span> | <span data-ttu-id="d9f54-142">資料會保留在雲端儲存空間中，而系統管理員會設定保留原則。</span><span class="sxs-lookup"><span data-stu-id="d9f54-142">Data is retained in the cloud storage and Administrator configures retention policy.</span></span> |
|[<span data-ttu-id="d9f54-143">離線診斷</span><span class="sxs-lookup"><span data-stu-id="d9f54-143">Offline diagnostics</span></span>](#offline-diagnostics) |<span data-ttu-id="d9f54-144">裝置組配置：</span><span class="sxs-lookup"><span data-stu-id="d9f54-144">Device configuration:</span></span><ul><li><span data-ttu-id="d9f54-145">已打開電源並連接到電腦</span><span class="sxs-lookup"><span data-stu-id="d9f54-145">Powered on and connected to computer</span></span></li><li><span data-ttu-id="d9f54-146">電源和音量按鈕可運作</span><span class="sxs-lookup"><span data-stu-id="d9f54-146">Power and Volume buttons functioning</span></span></li></ul> |<span data-ttu-id="d9f54-147">HoloLens 裝置</span><span class="sxs-lookup"><span data-stu-id="d9f54-147">HoloLens device</span></span><br /><br /><span data-ttu-id="d9f54-148">已連接電腦</span><span class="sxs-lookup"><span data-stu-id="d9f54-148">Connected computer</span></span> |<span data-ttu-id="d9f54-149">除非使用者特別與其他使用者共用資料，否則使用者會儲存資料，而且只有使用者 (存取資料) 。</span><span class="sxs-lookup"><span data-stu-id="d9f54-149">The user stores the data, and only the user accesses the data (unless the user specifically shares the data with another user).</span></span> |<span data-ttu-id="d9f54-150">資料會保留在裝置上，直到使用者將其刪除。</span><span class="sxs-lookup"><span data-stu-id="d9f54-150">The data is retained on device until the user deletes it.</span></span> |

- <span data-ttu-id="d9f54-151">使用者負責以負責的方式與他人共用記錄。</span><span class="sxs-lookup"><span data-stu-id="d9f54-151">End-user is responsible for sharing the logs responsibly with someone else.</span></span> <span data-ttu-id="d9f54-152">這些檔案在聯繫客戶服務和支援人員時，主要很有用。</span><span class="sxs-lookup"><span data-stu-id="d9f54-152">These files are primarily useful when contacting customer service and support.</span></span>  

## <a name="feedback-hub"></a><span data-ttu-id="d9f54-153">意見反應中樞</span><span class="sxs-lookup"><span data-stu-id="d9f54-153">Feedback Hub</span></span>

<span data-ttu-id="d9f54-154">HoloLens 使用者可以使用 Microsoft Feedback Hub 桌面應用程式將診斷資訊傳送給 Microsoft 支援服務。</span><span class="sxs-lookup"><span data-stu-id="d9f54-154">A HoloLens user can use the Microsoft Feedback Hub desktop app to send diagnostic information to Microsoft Support.</span></span> <span data-ttu-id="d9f54-155">有關詳細資料及完整指示，請參閱 [提供意見回饋](hololens-feedback.md)給我們。</span><span class="sxs-lookup"><span data-stu-id="d9f54-155">For details and complete instructions, see [Give us feedback](hololens-feedback.md).</span></span>  

> [!NOTE]  
> <span data-ttu-id="d9f54-156">**商業或企業使用者：** 如果您使用意見回饋中樞應用程式來報告與 MDM、資源配置或其他任何裝置管理層面相關的問題，請變更應用程式類別至**企業管理**  >  **裝置類別**。</span><span class="sxs-lookup"><span data-stu-id="d9f54-156">**Commercial or enterprise users:** If you use the Feedback Hub app to report a problem that relates to MDM, provisioning, or any other device management aspect, change the app category to **Enterprise Management** > **Device category**.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="d9f54-157">必要條件</span><span class="sxs-lookup"><span data-stu-id="d9f54-157">Prerequisites</span></span>

- <span data-ttu-id="d9f54-158">裝置已連接至網路。</span><span class="sxs-lookup"><span data-stu-id="d9f54-158">The device is connected to a network.</span></span>
- <span data-ttu-id="d9f54-159">意見回饋中樞應用程式可在使用者的桌上型電腦上使用，使用者可以將檔案上傳到 Microsoft 雲端。</span><span class="sxs-lookup"><span data-stu-id="d9f54-159">The Feedback Hub app is available on the user's desktop computer, and the user can upload files to the Microsoft cloud.</span></span>

### <a name="data-locations-access-and-retention"></a><span data-ttu-id="d9f54-160">資料位置、存取和保留</span><span class="sxs-lookup"><span data-stu-id="d9f54-160">Data locations, access, and retention</span></span>

<span data-ttu-id="d9f54-161">使用者同意意見回饋中樞的使用條款，即表示使用者明確同意 (定義之資料的儲存) 。</span><span class="sxs-lookup"><span data-stu-id="d9f54-161">By agreeing to the terms-of-use of the Feedback Hub, the user explicitly consents to the storage and usage of the data (as defined by that agreement).</span></span>

<span data-ttu-id="d9f54-162">意見回饋中樞提供兩個供使用者儲存診斷資訊的位置：</span><span class="sxs-lookup"><span data-stu-id="d9f54-162">The Feedback Hub provides two places for the user to store diagnostic information:</span></span>

- <span data-ttu-id="d9f54-163">**Microsoft 雲端**。</span><span class="sxs-lookup"><span data-stu-id="d9f54-163">**The Microsoft cloud**.</span></span> <span data-ttu-id="d9f54-164">使用者使用意見回饋中樞應用程式上傳的資料會儲存與新一代隱私權與 NGP (一致的天數) 需求。</span><span class="sxs-lookup"><span data-stu-id="d9f54-164">Data that the user uploads by using the Feedback Hub app is stored for the number of days that is consistent with Next Generation Privacy (NGP) requirements.</span></span> <span data-ttu-id="d9f54-165">在這期間，Microsoft 員工可以使用符合 NGP 規範的檢視器來存取訊號。</span><span class="sxs-lookup"><span data-stu-id="d9f54-165">Microsoft employees can use an NGP-compliant viewer to access the information during this period.</span></span>
   > [!NOTE]  
   > <span data-ttu-id="d9f54-166">這些需求適用于所有意見回饋中樞類別中的資料。</span><span class="sxs-lookup"><span data-stu-id="d9f54-166">These requirements apply to data in all Feedback Hub categories.</span></span>

- <span data-ttu-id="d9f54-167">**HoloLens 裝置**。</span><span class="sxs-lookup"><span data-stu-id="d9f54-167">**The HoloLens device**.</span></span> <span data-ttu-id="d9f54-168">在意見回饋中心歸檔報告時，使用者可以選取儲存在提供意見回饋時所建立之診斷和附件 **的本機複本**。</span><span class="sxs-lookup"><span data-stu-id="d9f54-168">While filing a report in Feedback Hub, the user can select **Save a local copy of diagnostics and attachments created when giving feedback**.</span></span> <span data-ttu-id="d9f54-169">如果使用者選取此選項，意見回饋中樞會儲存 HoloLens 裝置診斷資訊的一份副本。</span><span class="sxs-lookup"><span data-stu-id="d9f54-169">If the user selects this option, the Feedback Hub stores a copy of the diagnostic information on the HoloLens device.</span></span> <span data-ttu-id="d9f54-170">使用者或使用該帳戶的任何人 (HoloLens) 。</span><span class="sxs-lookup"><span data-stu-id="d9f54-170">This information remains accessible to the user (or anyone that uses that account to sign in to HoloLens).</span></span> <span data-ttu-id="d9f54-171">若要刪除此資訊， **使用者必須在裝置** 上擁有 **裝置擁有者或** 系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="d9f54-171">To delete this information, a user must have **Device owner** or **Admin** permissions on the device.</span></span> <span data-ttu-id="d9f54-172">擁有適當許可權的使用者可以登錄意見回饋中心、選取設定\*\*\*\*  >  **視圖**診斷記錄，然後刪除資訊。</span><span class="sxs-lookup"><span data-stu-id="d9f54-172">A user who has the appropriate permissions can sign in to the Feedback Hub, select **Settings** > **View diagnostics logs**, and delete the information.</span></span>

## <a name="settings-troubleshooter"></a><span data-ttu-id="d9f54-173">設定疑難排解員</span><span class="sxs-lookup"><span data-stu-id="d9f54-173">Settings Troubleshooter</span></span>

<span data-ttu-id="d9f54-174">HoloLens 使用者可以使用裝置上的設定應用程式來疑難排解問題並收集診斷資訊。</span><span class="sxs-lookup"><span data-stu-id="d9f54-174">A HoloLens user can use the Settings app on the device to troubleshoot problems and collect diagnostic information.</span></span> <span data-ttu-id="d9f54-175">若要這樣做，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d9f54-175">To do this, follow these steps:</span></span>

1. <span data-ttu-id="d9f54-176">開啟設定應用程式，然後選取更新 **&**  >  **疑難排解**頁面。</span><span class="sxs-lookup"><span data-stu-id="d9f54-176">Open the Settings app and select **Update & Security** > **Troubleshoot** page.</span></span>
1. <span data-ttu-id="d9f54-177">選取適當的區域， **然後選取開始**。</span><span class="sxs-lookup"><span data-stu-id="d9f54-177">Select the appropriate area, and select **Start**.</span></span>
1. <span data-ttu-id="d9f54-178">重現問題。</span><span class="sxs-lookup"><span data-stu-id="d9f54-178">Reproduce the issue.</span></span>
1. <span data-ttu-id="d9f54-179">重現問題之後，請返回設定， **然後選取停止**。</span><span class="sxs-lookup"><span data-stu-id="d9f54-179">After you reproduce the issue, return to Settings and then select **Stop**.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="d9f54-180">必要條件</span><span class="sxs-lookup"><span data-stu-id="d9f54-180">Prerequisites</span></span>

- <span data-ttu-id="d9f54-181">設定應用程式已安裝于裝置上，可供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="d9f54-181">The Settings app is installed on the device and is available to the user.</span></span>

### <a name="data-locations-access-and-retention"></a><span data-ttu-id="d9f54-182">資料位置、存取和保留</span><span class="sxs-lookup"><span data-stu-id="d9f54-182">Data locations, access, and retention</span></span>

<span data-ttu-id="d9f54-183">由於使用者會啟動資料收集，因此使用者隱含地同意儲存診斷資訊。</span><span class="sxs-lookup"><span data-stu-id="d9f54-183">Because the user starts the data collection, the user implicitly consents to the storage of the diagnostic information.</span></span> <span data-ttu-id="d9f54-184">只有使用者或使用者共用資料的任何人，才能存取資料。</span><span class="sxs-lookup"><span data-stu-id="d9f54-184">Only the user, or anyone with whom that the user shares the data, can access the data.</span></span>

<span data-ttu-id="d9f54-185">診斷資訊會儲存在裝置上。</span><span class="sxs-lookup"><span data-stu-id="d9f54-185">The diagnostic information is stored on the device.</span></span> <span data-ttu-id="d9f54-186">如果裝置已連接到使用者的電腦，則資訊也會位於下列檔案中的電腦上：</span><span class="sxs-lookup"><span data-stu-id="d9f54-186">If the device is connected to the user's computer, the information also resides on the computer in the following file:</span></span>

> <span data-ttu-id="d9f54-187">此電腦\\ \<*HoloLens device name*> \\內部儲存\\Documents\\Trace \<*ddmmyyhhmmss*> .etl</span><span class="sxs-lookup"><span data-stu-id="d9f54-187">This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents\\Trace\<*ddmmyyhhmmss*>.etl</span></span>

> [!NOTE]  
> <span data-ttu-id="d9f54-188">在此檔案路徑和名稱中，代表 HoloLens 裝置的名稱，並代表檔案 \<*HoloLens device name*> \<*ddmmyyhhmmss*> 的建立日期和時間。</span><span class="sxs-lookup"><span data-stu-id="d9f54-188">In this file path and name, \<*HoloLens device name*> represents the name of the HoloLens device, and \<*ddmmyyhhmmss*> represents the date and time that the file was created.</span></span>

<span data-ttu-id="d9f54-189">診斷資訊會保留在這些位置，直到使用者刪除它。</span><span class="sxs-lookup"><span data-stu-id="d9f54-189">The diagnostic information remains in these locations until the user deletes it.</span></span>

## <a name="diagnosticlog-csp"></a><span data-ttu-id="d9f54-190">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="d9f54-190">DiagnosticLog CSP</span></span>

<span data-ttu-id="d9f54-191">在行動裝置管理 (MDM) 環境中，IT 系統管理員可以使用 [DiagnosticLog ](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) 設定服務提供者 (CSP) 在已註冊的 HoloLens 裝置上設定診斷設定。</span><span class="sxs-lookup"><span data-stu-id="d9f54-191">In a Mobile Device Management (MDM) environment, the IT administrator can use the the [DiagnosticLog configuration service provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) to configure diagnostic settings on enrolled HoloLens devices.</span></span> <span data-ttu-id="d9f54-192">IT 系統管理員可以設定這些設定，以收集已註冊裝置中的記錄。</span><span class="sxs-lookup"><span data-stu-id="d9f54-192">The IT administrator can configure these settings to collect logs from enrolled devices.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="d9f54-193">必要條件</span><span class="sxs-lookup"><span data-stu-id="d9f54-193">Prerequisites</span></span>

- <span data-ttu-id="d9f54-194">裝置已連接至網路。</span><span class="sxs-lookup"><span data-stu-id="d9f54-194">The device is connected to a network.</span></span>
- <span data-ttu-id="d9f54-195">裝置是在支援 DiagnosticLog CSP 的 MDM 環境中註冊。</span><span class="sxs-lookup"><span data-stu-id="d9f54-195">The device is enrolled in an MDM environment that supports the DiagnosticLog CSP.</span></span>

### <a name="data-locations-access-and-retention"></a><span data-ttu-id="d9f54-196">資料位置、存取和保留</span><span class="sxs-lookup"><span data-stu-id="d9f54-196">Data locations, access, and retention</span></span>

<span data-ttu-id="d9f54-197">由於裝置是受管理環境的一部分，因此使用者隱含地同意以系統管理方式存取診斷資訊。</span><span class="sxs-lookup"><span data-stu-id="d9f54-197">Because the device is part of the managed environment, the user implicitly consents to administrative access to diagnostic information.</span></span>

<span data-ttu-id="d9f54-198">IT 系統管理員使用 DiagnosticLog CSP 來設定資料儲存、保留和存取策略，包括規範下列各項的政策：</span><span class="sxs-lookup"><span data-stu-id="d9f54-198">The IT administrator uses the DiagnosticLog CSP to configure the data storage, retention, and access policies, including the policies that govern the following:</span></span>

- <span data-ttu-id="d9f54-199">儲存診斷資訊的雲端基礎結構。</span><span class="sxs-lookup"><span data-stu-id="d9f54-199">The cloud infrastructure that stores the diagnostic information.</span></span>
- <span data-ttu-id="d9f54-200">診斷資訊的保留期間。</span><span class="sxs-lookup"><span data-stu-id="d9f54-200">The retention period for the diagnostic information.</span></span>
- <span data-ttu-id="d9f54-201">控制診斷資訊存取權的許可權。</span><span class="sxs-lookup"><span data-stu-id="d9f54-201">Permissions that control access to the diagnostic information.</span></span>

## <a name="offline-diagnostics"></a><span data-ttu-id="d9f54-202">離線診斷</span><span class="sxs-lookup"><span data-stu-id="d9f54-202">Offline diagnostics</span></span>
<span data-ttu-id="d9f54-203">如果裝置無法透過意見反應中樞或設定疑難排解員收集診斷，您可以手動收集診斷。</span><span class="sxs-lookup"><span data-stu-id="d9f54-203">In situations where the device is not able to collect diagnostics via Feedback Hub or the Setting Troubleshooter, you can collect diagnostics manually.</span></span> <span data-ttu-id="d9f54-204">其中一個必要情況是裝置無法連接到Wi-Fi或您無法存取上述的其他方法。</span><span class="sxs-lookup"><span data-stu-id="d9f54-204">One scenario where this is necessary is when the device cannot connect to Wi-Fi or you can't access other methods mentioned above.</span></span> <span data-ttu-id="d9f54-205">診斷會收集裝置中的當機傾卸和記錄，協助 Microsoft 支援工程師隔離問題。</span><span class="sxs-lookup"><span data-stu-id="d9f54-205">The diagnostics collect crash dumps and logs from the device that help a Microsoft support engineer isolate issues.</span></span>

<span data-ttu-id="d9f54-206">當裝置透過 USB 纜線連接到電腦後，裝置會顯示在檔案管理器中時，此功能會運作。</span><span class="sxs-lookup"><span data-stu-id="d9f54-206">This works when the device shows up in File Explorer after connecting it to a PC via a USB cable.</span></span>

> [!NOTE]
> <span data-ttu-id="d9f54-207">離線診斷的產生與管理會根據您的作業系統版本而有不同的控制方式。</span><span class="sxs-lookup"><span data-stu-id="d9f54-207">Offline Diagnostics generation and management is controlled differently depending on your OS version.</span></span> <span data-ttu-id="d9f54-208">之前它是由遙測設定控制，但現在是透過 MDM 策略直接控制。</span><span class="sxs-lookup"><span data-stu-id="d9f54-208">Previously it was controlled by the telemetry setting, but is now directly controlled via MDM policy.</span></span> <span data-ttu-id="d9f54-209">如果透過設定或 MDM 策略停用，就無法使用此機制收集診斷記錄。</span><span class="sxs-lookup"><span data-stu-id="d9f54-209">If disabled via either setting or MDM policy, then diagnostic logs cannot be collected using this mechanism.</span></span>

<span data-ttu-id="d9f54-210">Windows 全攝影[之前的行為，verison 20H2：](hololens-release-notes.md#windows-holographic-version-20h2)</span><span class="sxs-lookup"><span data-stu-id="d9f54-210">Behavior Prior to [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2):</span></span>
 - <span data-ttu-id="d9f54-211">只有當使用者執行 OOBE 或 [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) 政策值設定為 Full (Basic 是 HoloLens) 時，才能啟用離線診斷。</span><span class="sxs-lookup"><span data-stu-id="d9f54-211">Offline diagnostics is only enabled when user is either going through OOBE or [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) policy value is set to Full (Basic is default value on HoloLens).</span></span> 
- <span data-ttu-id="d9f54-212">若要停用離線診斷，請前往設定**應用程式>隱私權**頁面，**然後選取診斷**資料中的基本 **。**</span><span class="sxs-lookup"><span data-stu-id="d9f54-212">To disable Offline diagnostics, go to **Settings App > Privacy** page and select **Basic** in **Diagnostic Data**.</span></span> <span data-ttu-id="d9f54-213">在離線診斷取決於遙測設定的建立中，只會影響是否收集任何記錄。</span><span class="sxs-lookup"><span data-stu-id="d9f54-213">On builds where offline diagnostics depends on telemetry setting, it only impacts whether any logs are collected or not.</span></span> <span data-ttu-id="d9f54-214">這不會影響所收集的檔案。</span><span class="sxs-lookup"><span data-stu-id="d9f54-214">It does not impact what files are collected.</span></span>
- <span data-ttu-id="d9f54-215">如果裝置已鎖定，就不會顯示記錄。</span><span class="sxs-lookup"><span data-stu-id="d9f54-215">If device is locked then logs won't appear.</span></span>

<span data-ttu-id="d9f54-216">在 [Windows 全攝影版、verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 及更新版本上：</span><span class="sxs-lookup"><span data-stu-id="d9f54-216">On builds [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) and onwards:</span></span>
- <span data-ttu-id="d9f54-217">啟用後拉式診斷時，會由具有對應設定[MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)的特定 MDM 原則控制</span><span class="sxs-lookup"><span data-stu-id="d9f54-217">When Fallback Diagnostics is enabled will be controlled by specific MDM policy with corresponding setting [MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)</span></span>
- <span data-ttu-id="d9f54-218">如果裝置已鎖定，就不會顯示記錄。</span><span class="sxs-lookup"><span data-stu-id="d9f54-218">If device is locked then logs won't appear.</span></span>

<span data-ttu-id="d9f54-219">若要深入瞭解，請觀看這段影片。</span><span class="sxs-lookup"><span data-stu-id="d9f54-219">Watch this video to learn more.</span></span>

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

<span data-ttu-id="d9f54-220">請遵循下列步驟收集診斷：</span><span class="sxs-lookup"><span data-stu-id="d9f54-220">Follow these steps to collect diagnostics:</span></span>
1.  <span data-ttu-id="d9f54-221">使用 USB 纜線將裝置連接到您的電腦。</span><span class="sxs-lookup"><span data-stu-id="d9f54-221">Connect the device with a USB cable to your PC.</span></span>
2.  <span data-ttu-id="d9f54-222">在 PC 上的檔案檔案管理器中，流覽至 **'This PC \<hololens-device> \內部儲存空間'。**</span><span class="sxs-lookup"><span data-stu-id="d9f54-222">In File Explorer on your PC, navigate to **'This PC\<hololens-device>\Internal Storage'**.</span></span>
3.  <span data-ttu-id="d9f54-223">如果 **內部儲存** 空間資料夾沒有顯示，裝置會等待使用者進行註冊。</span><span class="sxs-lookup"><span data-stu-id="d9f54-223">If the **Internal Storage** folder does not show up, the device is waiting for a user to sign in.</span></span> <span data-ttu-id="d9f54-224">按住 POWER 按鈕 10 秒，即可在裝置上進行登錄或電源迴圈。</span><span class="sxs-lookup"><span data-stu-id="d9f54-224">Either sign-in or power cycle the device by holding the POWER button down for 10 seconds.</span></span>
4.  <span data-ttu-id="d9f54-225">同步選取並立即放開 **POWER + 音量降低** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="d9f54-225">Press and immediately release the **POWER + VOLUME DOWN** buttons together.</span></span>
5.  <span data-ttu-id="d9f54-226">請稍候裝置準備 ZIP 檔案。</span><span class="sxs-lookup"><span data-stu-id="d9f54-226">Wait a minute for the device to prepare the zip archives.</span></span> <span data-ttu-id="d9f54-227"> (產生 ZIP 檔案時，可能會顯示名為 HololensDiagnostics.temp 的暫存檔案。</span><span class="sxs-lookup"><span data-stu-id="d9f54-227">(A temporary file named HololensDiagnostics.temp may become visible while the device generates the zip archives.</span></span> <span data-ttu-id="d9f54-228">請勿存取或儲存該檔案。</span><span class="sxs-lookup"><span data-stu-id="d9f54-228">Do not access or save that file.</span></span> <span data-ttu-id="d9f54-229">程式完成時，將會由 zip archives.) </span><span class="sxs-lookup"><span data-stu-id="d9f54-229">When the process finishes it will be replaced by the zip archives.)</span></span>
6.  <span data-ttu-id="d9f54-230">重新更新檔案，然後流覽至 **"\Documents"** 資料夾。</span><span class="sxs-lookup"><span data-stu-id="d9f54-230">Refresh file explorer, and navigate to the **'\Documents'** folder.</span></span>
7.  <span data-ttu-id="d9f54-231">複製診斷 ZIP 檔案，然後與 Microsoft 支援小組共用。</span><span class="sxs-lookup"><span data-stu-id="d9f54-231">Copy the diagnostics ZIP files and share them with the Microsoft support team.</span></span>

> [!NOTE]
> <span data-ttu-id="d9f54-232">部分診斷 ZIP 檔案可能包含個人識別資訊。</span><span class="sxs-lookup"><span data-stu-id="d9f54-232">Some of the diagnostics ZIP files may contain personally identifiable information.</span></span>