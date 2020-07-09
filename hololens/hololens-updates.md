---
title: 管理 HoloLens 更新
description: 系統管理員可以使用行動裝置管理來管理 HoloLens 裝置更新。
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 03/24/2020
ms.reviewer: jarrettr
manager: jarrettr
ms.custom:
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: f8d0c788756b0a24ac8a26b8258b267483f1a890
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857751"
---
# <span data-ttu-id="0623f-103">管理 HoloLens 更新</span><span class="sxs-lookup"><span data-stu-id="0623f-103">Manage HoloLens Updates</span></span>

<span data-ttu-id="0623f-104">HoloLens 使用 Windows Update 的方式與其他 Windows 10 裝置相同。</span><span class="sxs-lookup"><span data-stu-id="0623f-104">HoloLens uses Windows Update in the same manner as other Windows 10 devices.</span></span> <span data-ttu-id="0623f-105">當有可用的更新時，系統會在您下次插入裝置並聯線到網際網路時，自動下載並安裝。</span><span class="sxs-lookup"><span data-stu-id="0623f-105">When an update is available, it is automatically downloaded and installed the next time that your device is plugged in and connected to the internet.</span></span> <span data-ttu-id="0623f-106">本文說明如何管理企業或其他受管理環境中的更新。</span><span class="sxs-lookup"><span data-stu-id="0623f-106">This article describes how to manage updates in an enterprise or other managed environment.</span></span> <span data-ttu-id="0623f-107">如需管理個別 HoloLens 裝置更新的相關資訊，請參閱[更新 HoloLens](hololens-update-hololens.md)。</span><span class="sxs-lookup"><span data-stu-id="0623f-107">For information about managing updates to individual HoloLens devices, see [Update HoloLens](hololens-update-hololens.md).</span></span>

## <span data-ttu-id="0623f-108">自動管理更新</span><span class="sxs-lookup"><span data-stu-id="0623f-108">Manage updates automatically</span></span>

<span data-ttu-id="0623f-109">Windows Holographic for Business 可使用 [商務用 Windows Update](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) 來管理更新。</span><span class="sxs-lookup"><span data-stu-id="0623f-109">Windows Holographic for Business can use [Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) to manage updates.</span></span> <span data-ttu-id="0623f-110">所有 HoloLens 2 裝置都可以使用 Windows Holographic for Business。</span><span class="sxs-lookup"><span data-stu-id="0623f-110">All HoloLens 2 devices can use Windows Holographic for Business.</span></span> <span data-ttu-id="0623f-111">請確認其使用 Windows Holographic for Business 組建10.0.18362.1042 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="0623f-111">Make sure that they use Windows Holographic for Business build 10.0.18362.1042 or a later build.</span></span> <span data-ttu-id="0623f-112">如果您使用的是 HoloLens (第 1 代) 裝置，您必須[升級至 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 來管理其更新。</span><span class="sxs-lookup"><span data-stu-id="0623f-112">If you have HoloLens (1st gen) devices, you have to [upgrade them to Windows Holographic for Business](hololens1-upgrade-enterprise.md) to manage their updates.</span></span>

<span data-ttu-id="0623f-113">商務用 Windows Update 會直接將 HoloLens 裝置連線至 Windows Update 服務。</span><span class="sxs-lookup"><span data-stu-id="0623f-113">Windows Update for Business connects HoloLens devices directly to the Windows Update service.</span></span> <span data-ttu-id="0623f-114">使用商務用 Windows Update，您可以控制更新程序&mdash;的多個環節，例如哪些裝置在何時取得哪些更新。</span><span class="sxs-lookup"><span data-stu-id="0623f-114">By using Windows Update for Business, you can control multiple aspects of the update process&mdash;that is, which devices get which updates at what time.</span></span> <span data-ttu-id="0623f-115">例如，您可以將更新階段性推出到裝置的一子集，以便進行測試，然後在日後階段性推出其餘裝置的更新。</span><span class="sxs-lookup"><span data-stu-id="0623f-115">For example, you can roll out updates to a subset of devices for testing, then roll out updates to the remaining devices at a later date.</span></span> <span data-ttu-id="0623f-116">或者，您可以針對不同類型的更新定義不同的更新排程。</span><span class="sxs-lookup"><span data-stu-id="0623f-116">Or, you can define different update schedules for different types of updates.</span></span>

> [!NOTE]  
> <span data-ttu-id="0623f-117">針對 HoloLens 裝置，您可以自動管理功能更新 (每年發行兩次) 和品質更新 (按月或按需發行，包括重要的安全性更新)。</span><span class="sxs-lookup"><span data-stu-id="0623f-117">For HoloLens devices, you can automatically manage feature updates (released twice a year) and quality updates (released monthly or as required, including critical security updates).</span></span> <span data-ttu-id="0623f-118">如需更新類型的詳細資訊，請參閱[商務用 Windows Update 所管理的更新類型](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)。</span><span class="sxs-lookup"><span data-stu-id="0623f-118">For more information about update types, see [Types of updates managed by Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).</span></span>

<span data-ttu-id="0623f-119">您可以使用行動裝置管理 (MDM) 解決方案 (例如 Microsoft Intune) 中的原則，來設定 HoloLens 的商務用 Windows Update 設定。</span><span class="sxs-lookup"><span data-stu-id="0623f-119">You can configure Windows Update for Business settings for HoloLens by using policies in a Mobile Device Management (MDM) solution such as Microsoft Intune.</span></span>

<span data-ttu-id="0623f-120">如需如何使用 Intune 來設定商務用 Windows Update 的詳細討論，請參閱[在 Intune 中管理 Windows 10 軟體更新](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="0623f-120">For a detailed discussion about how to use Intune to configure Windows Update for Business, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure).</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="0623f-121">Intune 提供管理更新的兩種原則類型：*Windows 10 更新通道*和 *Windows 10 功能更新*。</span><span class="sxs-lookup"><span data-stu-id="0623f-121">Intune provides two policy types for managing updates: *Windows 10 update ring* and *Windows 10 feature updates*.</span></span> <span data-ttu-id="0623f-122">Windows 10 功能更新原則類型目前處於公開預覽狀態，且不支援 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="0623f-122">The Windows 10 feature update policy type is in public preview at this time and is not supported for HoloLens.</span></span>
>  
> <span data-ttu-id="0623f-123">您可以使用 Windows 10 更新通道原則來管理 HoloLens 2 更新。</span><span class="sxs-lookup"><span data-stu-id="0623f-123">You can use Windows 10 update ring policies to manage HoloLens 2 updates.</span></span>

### <span data-ttu-id="0623f-124">設定 HoloLens 2 或 HoloLens (第 1 代) 的更新原則</span><span class="sxs-lookup"><span data-stu-id="0623f-124">Configure update policies for HoloLens 2 or HoloLens (1st gen)</span></span>

<span data-ttu-id="0623f-125">本節將說明可用來管理 HoloLens 2 或 HoloLens (第 1 代) 更新的原則。</span><span class="sxs-lookup"><span data-stu-id="0623f-125">This section describes the policies that you can use to manage updates for either HoloLens 2 or HoloLens (1st gen).</span></span> <span data-ttu-id="0623f-126">如需有關 HoloLens 2 所提供的額外功能之詳細資訊，請參閱[規劃並設定 HoloLens 2 的更新階段性推出](#plan-and-configure-update-rollouts-for-hololens-2)。</span><span class="sxs-lookup"><span data-stu-id="0623f-126">For information about additional functionality that is available for HoloLens 2, see [Plan and configure update rollouts for HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).</span></span>

<span data-ttu-id="0623f-127">[原則配置服務提供者 (CSP)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) 會定義設定商務用 Windows Update 的原則。</span><span class="sxs-lookup"><span data-stu-id="0623f-127">The [Policy configuration service provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) defines the policies that configure Windows Update for Business.</span></span>

> [!NOTE]  
> <span data-ttu-id="0623f-128">如需特定版本的 HoloLens 所支援的特定原則之詳細資訊，請參閱 [HoloLens 裝置支援的原則](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-hololens-devices)。</span><span class="sxs-lookup"><span data-stu-id="0623f-128">For details about specific policies that are supported by specific editions of HoloLens, see [Policies supported by HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-hololens-devices).</span></span>

#### <span data-ttu-id="0623f-129">設定自動檢查更新</span><span class="sxs-lookup"><span data-stu-id="0623f-129">Configure automatic checks for updates</span></span>

<span data-ttu-id="0623f-130">您可以使用 **Update/AllowAutoUpdate** 原則來管理自動更新行為，例如掃描、下載及安裝更新。</span><span class="sxs-lookup"><span data-stu-id="0623f-130">You can use the **Update/AllowAutoUpdate** policy to manage automatic update behavior, such as scanning, downloading, and installing updates.</span></span>

<span data-ttu-id="0623f-131">此原則支援下列值：</span><span class="sxs-lookup"><span data-stu-id="0623f-131">This policy supports the following values:</span></span>

- <span data-ttu-id="0623f-132">**0** - 當有可供下載且適用於裝置的更新時，通知使用者。</span><span class="sxs-lookup"><span data-stu-id="0623f-132">**0** - Notify the user when there is an update that is ready to download that applies to the device.</span></span>
- <span data-ttu-id="0623f-133">**1** - 自動安裝更新，然後通知使用者排程重新啟動裝置。</span><span class="sxs-lookup"><span data-stu-id="0623f-133">**1** - Automatically install the update, and then notify the user to schedule a device restart.</span></span>  
- <span data-ttu-id="0623f-134">**2** - 自動安裝更新，然後重新啟動裝置。</span><span class="sxs-lookup"><span data-stu-id="0623f-134">**2** - Automatically install the update, and then restart the device.</span></span> <span data-ttu-id="0623f-135">這是建議值，且是此原則的預設值。</span><span class="sxs-lookup"><span data-stu-id="0623f-135">This is the recommended value, and it is the default value for this policy.</span></span>  

- <span data-ttu-id="0623f-136">**3** - 自動安裝更新，然後在指定時間重新啟動。</span><span class="sxs-lookup"><span data-stu-id="0623f-136">**3** - Automatically install the update, and then restart at a specified time.</span></span> <span data-ttu-id="0623f-137">指定安裝日期和時間。</span><span class="sxs-lookup"><span data-stu-id="0623f-137">Specify the installation day and time.</span></span> <span data-ttu-id="0623f-138">如果未指定日期和時間，則預設值為每天淩晨 3 點</span><span class="sxs-lookup"><span data-stu-id="0623f-138">If no day and time are specified, the default is daily at 3 A.M.</span></span>  

- <span data-ttu-id="0623f-139">**4** - 自動安裝更新，然後重新啟動裝置。</span><span class="sxs-lookup"><span data-stu-id="0623f-139">**4** - Automatically install the update, and then restart the device.</span></span> <span data-ttu-id="0623f-140">此選項也會將 [設定] 頁面設定為唯讀。</span><span class="sxs-lookup"><span data-stu-id="0623f-140">This option also sets the Settings page to read-only.</span></span>

- <span data-ttu-id="0623f-141">**5**。關閉自動更新。</span><span class="sxs-lookup"><span data-stu-id="0623f-141">**5** - Turn off automatic updates.</span></span>

<span data-ttu-id="0623f-142">如需此原則的可用設定詳細資料，請參閱 [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)。</span><span class="sxs-lookup"><span data-stu-id="0623f-142">For more details about the available settings for this policy, see [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).</span></span>

> [!NOTE]  
> <span data-ttu-id="0623f-143">在 Microsoft Intune 中，您可以使用**自動更新行為** 來變更此原則。</span><span class="sxs-lookup"><span data-stu-id="0623f-143">In Microsoft Intune, you can use **Automatic Update Behavior** to change this policy.</span></span> <span data-ttu-id="0623f-144">如需詳細資訊，請參閱[在 Microsoft Intune 中管理軟體更新](https://docs.microsoft.com/intune/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="0623f-144">For more information, see [Manage software updates in Microsoft Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span></span>

#### <span data-ttu-id="0623f-145">設定更新排程</span><span class="sxs-lookup"><span data-stu-id="0623f-145">Configure an update schedule</span></span>

<span data-ttu-id="0623f-146">若要設定套用更新的方式和時間，請使用下列原則：</span><span class="sxs-lookup"><span data-stu-id="0623f-146">To configure how and when updates are applied, use the following policies:</span></span>

- <span data-ttu-id="0623f-147">[Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)。</span><span class="sxs-lookup"><span data-stu-id="0623f-147">[Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday).</span></span>  
   - <span data-ttu-id="0623f-148">值：**0** – **7** (0 = 每天、1 = 星期日、7 = 星期六) </span><span class="sxs-lookup"><span data-stu-id="0623f-148">Values: **0**–**7** (0 = every day, 1 = Sunday, 7 = Saturday)</span></span>
   - <span data-ttu-id="0623f-149">預設值：**0** (每天)</span><span class="sxs-lookup"><span data-stu-id="0623f-149">Default value: **0** (every day)</span></span>
- <span data-ttu-id="0623f-150">[Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)。</span><span class="sxs-lookup"><span data-stu-id="0623f-150">[Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime).</span></span>
   - <span data-ttu-id="0623f-151">值：0 – 23 (0 = 午夜，23 = 下午 11 點) </span><span class="sxs-lookup"><span data-stu-id="0623f-151">Values: 0–23 (0 = midnight, 23 = 11 P.M.)</span></span>
   - <span data-ttu-id="0623f-152">預設值：下午 3 點</span><span class="sxs-lookup"><span data-stu-id="0623f-152">Default value: 3 P.M.</span></span>

#### <span data-ttu-id="0623f-153">僅限執行 Windows 10 版本1607 的裝置</span><span class="sxs-lookup"><span data-stu-id="0623f-153">For devices that run Windows 10, version 1607 only</span></span>

<span data-ttu-id="0623f-154">您可以使用下列更新原則將裝置設定為從 Windows Server Update Services (WSUS) 取得更新，而非 Windows Update：</span><span class="sxs-lookup"><span data-stu-id="0623f-154">You can use the following update policies to configure devices to get updates from the Windows Server Update Service (WSUS), instead of Windows Update:</span></span>

- [<span data-ttu-id="0623f-155">Update/AllowUpdateService</span><span class="sxs-lookup"><span data-stu-id="0623f-155">Update/AllowUpdateService</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [<span data-ttu-id="0623f-156">Update/RequireUpdateApproval</span><span class="sxs-lookup"><span data-stu-id="0623f-156">Update/RequireUpdateApproval</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [<span data-ttu-id="0623f-157">Update/UpdateServiceUrl</span><span class="sxs-lookup"><span data-stu-id="0623f-157">Update/UpdateServiceUrl</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <span data-ttu-id="0623f-158">規劃和設定 HoloLens 2 的更新階段性推出</span><span class="sxs-lookup"><span data-stu-id="0623f-158">Plan and configure update rollouts for HoloLens 2</span></span>

<span data-ttu-id="0623f-159">HoloLens 2 比 HoloLens (第 1 代) 支援更多更新自動化功能。</span><span class="sxs-lookup"><span data-stu-id="0623f-159">HoloLens 2 supports more update automation features than HoloLens (1st gen).</span></span> <span data-ttu-id="0623f-160">如果您使用 Microsoft Intune 來管理商務用 Windows Update 原則，則尤其如此。</span><span class="sxs-lookup"><span data-stu-id="0623f-160">this is especially true if you use Microsoft Intune to manage Windows Update for Business policy.</span></span> <span data-ttu-id="0623f-161">這些功能可讓您更輕鬆地在組織中規劃和實施更新階段性推出。</span><span class="sxs-lookup"><span data-stu-id="0623f-161">These features make it easier for you to plan and implement update rollouts across your organization.</span></span>

#### <span data-ttu-id="0623f-162">規劃更新策略</span><span class="sxs-lookup"><span data-stu-id="0623f-162">Plan the update strategy</span></span>

<span data-ttu-id="0623f-163">商務用 Windows Update 有支援延遲原則。</span><span class="sxs-lookup"><span data-stu-id="0623f-163">Windows Updates for Business supports deferral policies.</span></span> <span data-ttu-id="0623f-164">Microsoft 發行更新之後，您可以使用延遲原則，來定義在裝置上安裝該更新之前要等待多久。</span><span class="sxs-lookup"><span data-stu-id="0623f-164">After Microsoft releases an update, you can use a deferral policy to define how long to wait before installing that update on devices.</span></span> <span data-ttu-id="0623f-165">將裝置的子集 (稱為*更新通道*) 與不同的延遲原則相關聯，您就可以協調貴組織的更新階段性推出策略。</span><span class="sxs-lookup"><span data-stu-id="0623f-165">By associating subsets of your devices (referred to as *update rings*) with different deferral policies, you can coordinate an update rollout strategy for your organization.</span></span>

<span data-ttu-id="0623f-166">例如，假設組織中有 1000 部裝置，且必須透過五種方法來更新。</span><span class="sxs-lookup"><span data-stu-id="0623f-166">For example, consider an organization that has 1,000 devices and has to update them in five ways.</span></span> <span data-ttu-id="0623f-167">組織可以建立五個更新通道，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="0623f-167">The organization can create five update rings, as shown in the following table.</span></span>

|<span data-ttu-id="0623f-168">群組</span><span class="sxs-lookup"><span data-stu-id="0623f-168">Group</span></span> |<span data-ttu-id="0623f-169">裝置數量</span><span class="sxs-lookup"><span data-stu-id="0623f-169">Number of devices</span></span> |<span data-ttu-id="0623f-170">延遲 (天) </span><span class="sxs-lookup"><span data-stu-id="0623f-170">Deferral (days)</span></span> |
| ---| :---: | :---: |
|<span data-ttu-id="0623f-171">群組 1 (IT 員工)</span><span class="sxs-lookup"><span data-stu-id="0623f-171">Grp 1 (IT staff)</span></span> |<span data-ttu-id="0623f-172">5</span><span class="sxs-lookup"><span data-stu-id="0623f-172">5</span></span> |<span data-ttu-id="0623f-173">0</span><span class="sxs-lookup"><span data-stu-id="0623f-173">0</span></span> |
|<span data-ttu-id="0623f-174">群組 2 (早期採用者)</span><span class="sxs-lookup"><span data-stu-id="0623f-174">Grp 2 (early adopters)</span></span> |<span data-ttu-id="0623f-175">50</span><span class="sxs-lookup"><span data-stu-id="0623f-175">50</span></span> |<span data-ttu-id="0623f-176">60</span><span class="sxs-lookup"><span data-stu-id="0623f-176">60</span></span> |
|<span data-ttu-id="0623f-177">群組 3 (主要 1)</span><span class="sxs-lookup"><span data-stu-id="0623f-177">Grp 3 (main 1)</span></span> |<span data-ttu-id="0623f-178">250</span><span class="sxs-lookup"><span data-stu-id="0623f-178">250</span></span> |<span data-ttu-id="0623f-179">120</span><span class="sxs-lookup"><span data-stu-id="0623f-179">120</span></span> |
|<span data-ttu-id="0623f-180">群組 4 (主要 2)</span><span class="sxs-lookup"><span data-stu-id="0623f-180">Grp 4 (main 2)</span></span> |<span data-ttu-id="0623f-181">300</span><span class="sxs-lookup"><span data-stu-id="0623f-181">300</span></span> |<span data-ttu-id="0623f-182">150</span><span class="sxs-lookup"><span data-stu-id="0623f-182">150</span></span> |
|<span data-ttu-id="0623f-183">群組 5 (主要 3)</span><span class="sxs-lookup"><span data-stu-id="0623f-183">Grp 5 (main 3)</span></span> |<span data-ttu-id="0623f-184">395</span><span class="sxs-lookup"><span data-stu-id="0623f-184">395</span></span> |<span data-ttu-id="0623f-185">180</span><span class="sxs-lookup"><span data-stu-id="0623f-185">180</span></span> |

<span data-ttu-id="0623f-186">以下是一段時間之後，階段性推出在整個組織的進展方式。</span><span class="sxs-lookup"><span data-stu-id="0623f-186">Here's how the rollout progresses over time to the entire organization.</span></span>

![部署更新的時間表](./images/hololens-updates-timeline.png)

#### <span data-ttu-id="0623f-188">設定更新延遲原則</span><span class="sxs-lookup"><span data-stu-id="0623f-188">Configure an update deferral policy</span></span>

<span data-ttu-id="0623f-189">延遲原則會指定更新可用的日期和裝置的提議更新日期之間的天數。</span><span class="sxs-lookup"><span data-stu-id="0623f-189">A deferral policy specifies the number of days between the date that an update becomes available and the date that the update is offered to a device.</span></span>

<span data-ttu-id="0623f-190">您可以設定不同的延遲來進行功能更新和品質更新。</span><span class="sxs-lookup"><span data-stu-id="0623f-190">You can configure different deferrals for feature updates and quality updates.</span></span> <span data-ttu-id="0623f-191">下表列出每一類型使用的特定原則，以及每個類別的最大延遲。</span><span class="sxs-lookup"><span data-stu-id="0623f-191">The following table lists the specific policies to use for each type, as well as the maximum deferral for each.</span></span>

|<span data-ttu-id="0623f-192">類別</span><span class="sxs-lookup"><span data-stu-id="0623f-192">Category</span></span> |<span data-ttu-id="0623f-193">原則</span><span class="sxs-lookup"><span data-stu-id="0623f-193">Policy</span></span> |<span data-ttu-id="0623f-194">延遲上限</span><span class="sxs-lookup"><span data-stu-id="0623f-194">Maximum deferral</span></span> |
| --- | --- | --- |
|<span data-ttu-id="0623f-195">功能更新</span><span class="sxs-lookup"><span data-stu-id="0623f-195">Feature updates</span></span> |<span data-ttu-id="0623f-196">DeferFeatureUpdatesPeriodInDays</span><span class="sxs-lookup"><span data-stu-id="0623f-196">DeferFeatureUpdatesPeriodInDays</span></span> |<span data-ttu-id="0623f-197">365 天</span><span class="sxs-lookup"><span data-stu-id="0623f-197">365 days</span></span> |
|<span data-ttu-id="0623f-198">品質更新</span><span class="sxs-lookup"><span data-stu-id="0623f-198">Quality updates</span></span> |<span data-ttu-id="0623f-199">DeferQualityUpdatesPeriodInDays</span><span class="sxs-lookup"><span data-stu-id="0623f-199">DeferQualityUpdatesPeriodInDays</span></span> |<span data-ttu-id="0623f-200">30 天</span><span class="sxs-lookup"><span data-stu-id="0623f-200">30 days</span></span> |

####  <span data-ttu-id="0623f-201">範例：使用 Intune 管理更新</span><span class="sxs-lookup"><span data-stu-id="0623f-201">Examples: Using Intune to manage updates</span></span>

**<span data-ttu-id="0623f-202">範例 1：建立並指派更新通道</span><span class="sxs-lookup"><span data-stu-id="0623f-202">Example 1: Create and assign an update ring</span></span>**

<span data-ttu-id="0623f-203">如需此範例的詳細資訊，請參閱[建立並指派更新通道](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)。</span><span class="sxs-lookup"><span data-stu-id="0623f-203">For a more detailed version of this example, see [Create and assign update rings](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).</span></span>

1. <span data-ttu-id="0623f-204">登入 [Microsoft 端點管理員系統管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，然後巡覽至您的 Intune 設定檔。</span><span class="sxs-lookup"><span data-stu-id="0623f-204">Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431), and navigate to your Intune profiles.</span></span>
1. <span data-ttu-id="0623f-205">選取 [軟體更新]\*\*\*\*  >  **Windows 10 更新通道**  >  [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0623f-205">Select **Software Updates** > **Windows 10 update rings** > **Create**.</span></span>
1. <span data-ttu-id="0623f-206">在 [基本]\*\*\*\* 底下指定名稱和描述 (選用) ，然後選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0623f-206">Under **Basics**, specify a name and a description (optional), and then select **Next**.</span></span>
1. <span data-ttu-id="0623f-207">在 [更新通道設定]\*\*\*\* 底下，針對 [服務通道]\*\*\*\* ，選取 [半年通道]\*\*\*\*，然後將 [功能更新延遲期]\*\*\*\* 變更為 **120**。</span><span class="sxs-lookup"><span data-stu-id="0623f-207">Under **Update ring settings**, for **Servicing channel**, select **Semi-Annual Channel**, and then change **Feature update deferral period** to **120**.</span></span> <span data-ttu-id="0623f-208">然後選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0623f-208">Then, select **Next**.</span></span>
1. <span data-ttu-id="0623f-209">在 [作業]\*\*\*\* 底下，選取 [+選取要包含的群組]\*\*\*\*，然後將更新通道指派給一或多個群組。</span><span class="sxs-lookup"><span data-stu-id="0623f-209">Under **Assignments**, select **+ Select groups to include**, and then assign the update ring to one or more groups.</span></span> <span data-ttu-id="0623f-210">使用 [+選取要排除的群組]\*\*\*\*，以便微調作業。</span><span class="sxs-lookup"><span data-stu-id="0623f-210">Use **+ Select groups to exclude** to fine-tune the assignments.</span></span> <span data-ttu-id="0623f-211">然後選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0623f-211">Then, select **Next**.</span></span>
1. <span data-ttu-id="0623f-212">在 [檢閱 + 建立]\*\*\*\* 底下，檢閱設定。</span><span class="sxs-lookup"><span data-stu-id="0623f-212">Under **Review + create**, review the settings.</span></span> <span data-ttu-id="0623f-213">當您準備好要儲存更新通道設定時，請選取 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0623f-213">When you're ready to save the update ring configuration, select **Create**.</span></span>

<span data-ttu-id="0623f-214">更新通道清單現在包含新的 Windows 10 更新通道。</span><span class="sxs-lookup"><span data-stu-id="0623f-214">The list of update rings now includes the new Windows 10 update ring.</span></span>

**<span data-ttu-id="0623f-215">範例 2：暫停更新通道</span><span class="sxs-lookup"><span data-stu-id="0623f-215">Example 2: Pause an update ring</span></span>**

<span data-ttu-id="0623f-216">如果您在部署功能或品質更新時遇到問題，您可以暫停更新 35 天 (從指定日期開始)。</span><span class="sxs-lookup"><span data-stu-id="0623f-216">If you encounter a problem when you deploy a feature or quality update, you can pause the update for 35 days (starting from a specified date).</span></span> <span data-ttu-id="0623f-217">當您解決或緩解問題之前，暫停會防止其他裝置安裝更新。</span><span class="sxs-lookup"><span data-stu-id="0623f-217">This pause prevents other devices from installing the update until you resolve or mitigate the issue.</span></span> <span data-ttu-id="0623f-218">如果您暫停功能更新，系統仍會提供品質更新，以確保其保持安全。</span><span class="sxs-lookup"><span data-stu-id="0623f-218">If you pause a feature update, quality updates are still offered to devices to make sure that they stay secure.</span></span> <span data-ttu-id="0623f-219">經過指定時間後，暫停會自動過期。</span><span class="sxs-lookup"><span data-stu-id="0623f-219">After the specified time has passed, the pause automatically expires.</span></span> <span data-ttu-id="0623f-220">屆時，更新程式會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="0623f-220">At that point, the update process resumes.</span></span>

<span data-ttu-id="0623f-221">若要暫停 Intune 更新通道，請按照下列步驟操作：</span><span class="sxs-lookup"><span data-stu-id="0623f-221">To pause an update ring in Intune, follow these steps:</span></span>

1. <span data-ttu-id="0623f-222">在更新通道的概觀頁面中，選取 [暫停]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0623f-222">On the overview page for the update ring, select **Pause**.</span></span>
1. <span data-ttu-id="0623f-223">選取要暫停的更新類型 ([功能]\*\*\*\* 或 [品質]\*\*\*\*) ，然後選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0623f-223">Select the type of update (**Feature** or **Quality**) to pause, and then select **OK**.</span></span>

<span data-ttu-id="0623f-224">當更新類型暫停時，該通道的 [概觀] 窗格會顯示該更新類型繼續前剩餘的天數。</span><span class="sxs-lookup"><span data-stu-id="0623f-224">When an update type is paused, the Overview pane for that ring displays how many days remain before that update type resumes.</span></span>

<span data-ttu-id="0623f-225">當更新通道暫停時，您可以選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="0623f-225">While the update ring is paused, you can select either of the following options:</span></span>

- <span data-ttu-id="0623f-226">若要延長一更新類型的暫停期 35 天，請選取 [延伸]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0623f-226">To extend the pause period for an update type for 35 days, select **Extend**.</span></span>
- <span data-ttu-id="0623f-227">若要將該通道的更新還原為使用中的作業，請選取 [繼續]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0623f-227">To restore updates for that ring to active operation, select **Resume**.</span></span> <span data-ttu-id="0623f-228">如果需要，您可以再次暫停更新通道。</span><span class="sxs-lookup"><span data-stu-id="0623f-228">You can pause the update ring again if it is necessary.</span></span>

> [!NOTE]  
> <span data-ttu-id="0623f-229">HoloLens 2 裝置不支援更新通道的 [解除安裝]\*\*\*\* 作業。</span><span class="sxs-lookup"><span data-stu-id="0623f-229">The **Uninstall** operation for update rings is not supported for HoloLens 2 devices.</span></span>

## <span data-ttu-id="0623f-230">手動檢查更新</span><span class="sxs-lookup"><span data-stu-id="0623f-230">Manually check for updates</span></span>

<span data-ttu-id="0623f-231">雖然 HoloLens 會定期檢查系統更新，讓您不必進行手動檢查，但有時候您可能會想手動檢查。</span><span class="sxs-lookup"><span data-stu-id="0623f-231">Although HoloLens periodically checks for system updates so that you don't have to, there may be circumstances in which you want to manually check.</span></span>

<span data-ttu-id="0623f-232">若要手動檢查更新，請移至 [設定]\*\*\*\*  >  [更新 & 安全性]\*\*\*\*  >  [檢查更新]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0623f-232">To manually check for updates, go to **Settings** > **Update & Security** > **Check for updates**.</span></span> <span data-ttu-id="0623f-233">如果 [設定] 應用程式指出您的裝置為最新狀態，表示已擁有目前可用的所有更新。</span><span class="sxs-lookup"><span data-stu-id="0623f-233">If the Settings app indicates that your device is up to date, you have all the updates that are currently available.</span></span>

## <span data-ttu-id="0623f-234">手動還原更新</span><span class="sxs-lookup"><span data-stu-id="0623f-234">Manually revert an update</span></span>

<span data-ttu-id="0623f-235">在某些情況下，您可能會想還原到舊版的 HoloLens 軟體。</span><span class="sxs-lookup"><span data-stu-id="0623f-235">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="0623f-236">執行此作業的程序取決於您使用的是 HoloLens 2 或 HoloLens (第 1 代)。</span><span class="sxs-lookup"><span data-stu-id="0623f-236">The process for doing this depends on whether you are using HoloLens 2 or HoloLens (1st gen).</span></span>

### <span data-ttu-id="0623f-237">返回先前的版本 (HoloLens 2) </span><span class="sxs-lookup"><span data-stu-id="0623f-237">Go back to a previous version (HoloLens 2)</span></span>

<span data-ttu-id="0623f-238">您可以使用 Advanced Recovery Companion 將您的 HoloLens 重設為較舊的版本，以復原更新並返回舊版的 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="0623f-238">You can roll back updates and return to a previous version of HoloLens 2 by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="0623f-239">還原為較舊的版本會刪除您的個人檔案和設定。</span><span class="sxs-lookup"><span data-stu-id="0623f-239">Reverting to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="0623f-240">若要返回先前版本的 HoloLens 2，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="0623f-240">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="0623f-241">請確認您沒有任何手機或 Windows 裝置插入電腦。</span><span class="sxs-lookup"><span data-stu-id="0623f-241">Make sure that you don't have any phones or Windows devices plugged in to your computer.</span></span>
1. <span data-ttu-id="0623f-242">在您的電腦上，從 Microsoft Store下載 [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)。</span><span class="sxs-lookup"><span data-stu-id="0623f-242">On your computer, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="0623f-243">下載[最新的 HoloLens 2 發行版本](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="0623f-243">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="0623f-244">當您完成這些下載時，請開啟 [檔案總管]\*\*\*\*  >  [下載]\*\*\*\*，以滑鼠右鍵按一下您剛下載的壓縮 (zipped) 資料夾，然後選取 [全部解壓縮]\*\*\*\*  >  [解壓縮]\*\*\*\* 以展開檔案。</span><span class="sxs-lookup"><span data-stu-id="0623f-244">When you have finished these downloads, open **File explorer** > **Downloads**, right-click the compressed (zipped) folder that you just downloaded, and then select **Extract all** > **Extract** to expand the file.</span></span>
1. <span data-ttu-id="0623f-245">使用 USB-A 轉 USB-C 纜線將您的 HoloLens 裝置連線至電腦。</span><span class="sxs-lookup"><span data-stu-id="0623f-245">Use a USB-A to USB-C cable to connect your HoloLens device to your computer.</span></span> <span data-ttu-id="0623f-246">(即使您過去一直是使用其他纜線來連接 HoloLens，以上仍是最適合的纜線)。</span><span class="sxs-lookup"><span data-stu-id="0623f-246">Even if you've been using other cables to connect your HoloLens, this kind of cable works best.</span></span>
1. <span data-ttu-id="0623f-247">Advanced Recovery Companion 會自動偵測您的 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="0623f-247">The Advanced Recovery Companion automatically detects your HoloLens device.</span></span> <span data-ttu-id="0623f-248">選取 [Microsoft HoloLens]\*\*\*\* 動態磚。</span><span class="sxs-lookup"><span data-stu-id="0623f-248">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="0623f-249">在下一個畫面中，選取 [手動套件選取]\*\*\*\*，然後開啟先前展開的資料夾。</span><span class="sxs-lookup"><span data-stu-id="0623f-249">On the next screen, select **Manual package selection**, and then open the folder that you previously expanded.</span></span> 
1. <span data-ttu-id="0623f-250">選取安裝檔案 (副檔名為 ffu 的檔案) 。</span><span class="sxs-lookup"><span data-stu-id="0623f-250">Select the installation file (the file that has an .ffu extension).</span></span>
1. <span data-ttu-id="0623f-251">選取 [安裝軟體]\*\*\*\*，然後依照指示進行。</span><span class="sxs-lookup"><span data-stu-id="0623f-251">Select **Install software**, and then follow the instructions.</span></span>

### <span data-ttu-id="0623f-252">返回先前的版本 (HoloLens (第 1 代)) </span><span class="sxs-lookup"><span data-stu-id="0623f-252">Go back to a previous version (HoloLens (1st gen))</span></span>

<span data-ttu-id="0623f-253">您可以使用 Windows Device Recovery Tool 將您的 HoloLens 重設為較舊的版本，以便復原更新並返回舊版 HoloLens (第 1 代)。</span><span class="sxs-lookup"><span data-stu-id="0623f-253">You can roll back updates and return to a previous version of HoloLens (1st gen) by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="0623f-254">還原為較舊的版本會刪除您的個人檔案和設定。</span><span class="sxs-lookup"><span data-stu-id="0623f-254">Reverting to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="0623f-255">若要回到舊版 HoloLens (第 1 代) ，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="0623f-255">To go back to a previous version of HoloLens (1st gen), follow these steps:</span></span>

1. <span data-ttu-id="0623f-256">請確認您沒有任何手機或 Windows 裝置插入電腦。</span><span class="sxs-lookup"><span data-stu-id="0623f-256">Make sure that you don't have any phones or Windows devices plugged in to your computer.</span></span>
1. <span data-ttu-id="0623f-257">在您的電腦上，下載 [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)。</span><span class="sxs-lookup"><span data-stu-id="0623f-257">On your computer, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="0623f-258">下載 [HoloLens 年度更新版復原套件](https://aka.ms/hololensrecovery)。</span><span class="sxs-lookup"><span data-stu-id="0623f-258">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="0623f-259">下載完成後，請開啟**檔案總管**  >  [下載]\*\*\*\*，以滑鼠右鍵按一下您剛下載的壓縮 (zipped) 資料夾，然後選取 [解壓全部]\*\*\*\*  >  [解壓縮]\*\*\*\* 來展開檔案。</span><span class="sxs-lookup"><span data-stu-id="0623f-259">After the downloads finish, open **File explorer** > **Downloads**, right-click the compressed (zipped) folder that you just downloaded, and then select **Extract all** > **Extract** to expand the file.</span></span>
1. <span data-ttu-id="0623f-260">使用隨附於 HoloLens 裝置的 micro-USB 纜線，將您的 HoloLens 裝置連線至電腦。</span><span class="sxs-lookup"><span data-stu-id="0623f-260">Use the micro-USB cable that was provided together with your HoloLens device to connect your HoloLens device to your computer.</span></span> <span data-ttu-id="0623f-261">即使您已使用其他纜線來連接 HoloLens 裝置，這仍是最適合的纜線。</span><span class="sxs-lookup"><span data-stu-id="0623f-261">Even if you've been using other cables to connect your HoloLens device, this one works best.</span></span>
1. <span data-ttu-id="0623f-262">WDRT 會自動偵測您的 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="0623f-262">The WDRT automatically detects your HoloLens device.</span></span> <span data-ttu-id="0623f-263">選取 [Microsoft HoloLens]\*\*\*\* 動態磚。</span><span class="sxs-lookup"><span data-stu-id="0623f-263">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="0623f-264">在下一個畫面中，選取 [手動套件選取]\*\*\*\*，然後開啟先前展開的資料夾。</span><span class="sxs-lookup"><span data-stu-id="0623f-264">On the next screen, select **Manual package selection**, and then open the folder that you previously expanded.</span></span> 
1. <span data-ttu-id="0623f-265">選取安裝檔案 (副檔名為 ffu 的檔案) 。</span><span class="sxs-lookup"><span data-stu-id="0623f-265">Select the installation file (the file that has an .ffu extension).</span></span>
1. <span data-ttu-id="0623f-266">選取 [安裝軟體]\*\*\*\*，然後依照指示進行。</span><span class="sxs-lookup"><span data-stu-id="0623f-266">Select **Install software**, and then follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="0623f-267">如果 WDRT 不會偵測您的 HoloLens 裝置，請嘗試重新啟動電腦。</span><span class="sxs-lookup"><span data-stu-id="0623f-267">If the WDRT doesn't detect your HoloLens device, try restarting your computer.</span></span> <span data-ttu-id="0623f-268">如果仍然無法解決問題，請選取 [沒有偵測到我的裝置]\*\*\*\*，選取 **Microsoft HoloLens**，然後按照指示進行。</span><span class="sxs-lookup"><span data-stu-id="0623f-268">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="0623f-269">相關文章</span><span class="sxs-lookup"><span data-stu-id="0623f-269">Related articles</span></span>

- [<span data-ttu-id="0623f-270">使用商務用 Windows Update 來部署更新</span><span class="sxs-lookup"><span data-stu-id="0623f-270">Deploy updates using Windows Update for Business</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [<span data-ttu-id="0623f-271">指派裝置到維護通道進行 Windows 10 更新</span><span class="sxs-lookup"><span data-stu-id="0623f-271">Assign devices to servicing channels for Windows 10 updates</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [<span data-ttu-id="0623f-272">在 Intune 中管理 Windows 10 軟體更新</span><span class="sxs-lookup"><span data-stu-id="0623f-272">Manage Windows 10 software updates in Intune</span></span>](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
