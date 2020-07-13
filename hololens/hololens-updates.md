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
ms.date: 07/09/2020
ms.reviewer: jarrettr
manager: jarrettr
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 384d33e72effd298e1874e5723e9c418061c3287
ms.sourcegitcommit: 0d4e67d8e21d34885e0eaee08646e28426c4f641
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/10/2020
ms.locfileid: "10861906"
---
# <span data-ttu-id="a5543-103">管理 HoloLens 更新</span><span class="sxs-lookup"><span data-stu-id="a5543-103">Manage HoloLens updates</span></span>

<span data-ttu-id="a5543-104">HoloLens 使用 Windows Update 的方式與其他 Windows 10 裝置相同。</span><span class="sxs-lookup"><span data-stu-id="a5543-104">HoloLens uses Windows Update in the same manner as other Windows 10 devices.</span></span> <span data-ttu-id="a5543-105">當有可用的更新時，系統會在您下次插入裝置並聯線到網際網路時，自動下載並安裝。</span><span class="sxs-lookup"><span data-stu-id="a5543-105">When an update is available, it is automatically downloaded and installed the next time that your device is plugged in and connected to the internet.</span></span> <span data-ttu-id="a5543-106">本文說明如何管理企業或其他受管理環境中的更新。</span><span class="sxs-lookup"><span data-stu-id="a5543-106">This article describes how to manage updates in an enterprise or other managed environment.</span></span> <span data-ttu-id="a5543-107">如需如何管理個別 HoloLens 裝置更新的相關資訊，請參閱[更新 HoloLens](hololens-update-hololens.md)。</span><span class="sxs-lookup"><span data-stu-id="a5543-107">For information about how to manage updates to individual HoloLens devices, see [Update HoloLens](hololens-update-hololens.md).</span></span>

## <span data-ttu-id="a5543-108">自動管理更新</span><span class="sxs-lookup"><span data-stu-id="a5543-108">Manage updates automatically</span></span>

### <span data-ttu-id="a5543-109">使用商務用 Windows Update 來管理更新</span><span class="sxs-lookup"><span data-stu-id="a5543-109">Managing updates by using Windows Update for Business</span></span>

<span data-ttu-id="a5543-110">Windows Holographic for Business 可使用 [商務用 Windows Update](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) 來管理更新。</span><span class="sxs-lookup"><span data-stu-id="a5543-110">Windows Holographic for Business can use [Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) to manage updates.</span></span> <span data-ttu-id="a5543-111">所有 HoloLens 2 裝置都可以使用 Windows Holographic for Business。</span><span class="sxs-lookup"><span data-stu-id="a5543-111">All HoloLens 2 devices can use Windows Holographic for Business.</span></span> <span data-ttu-id="a5543-112">請確認其使用 Windows Holographic for Business 組建10.0.18362.1042 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="a5543-112">Make sure that they use Windows Holographic for Business build 10.0.18362.1042 or a later build.</span></span> <span data-ttu-id="a5543-113">如果您使用的是 HoloLens (第 1 代) 裝置，則必須[將其升級至 Windows Holographic for Business](hololens1-upgrade-enterprise.md)，以便管理其更新。</span><span class="sxs-lookup"><span data-stu-id="a5543-113">If you have HoloLens (1st gen) devices, you have to [upgrade them to Windows Holographic for Business](hololens1-upgrade-enterprise.md) in order to manage their updates.</span></span>

<span data-ttu-id="a5543-114">商務用 Windows Update 會直接將 HoloLens 裝置連線至 Windows Update 服務。</span><span class="sxs-lookup"><span data-stu-id="a5543-114">Windows Update for Business connects HoloLens devices directly to the Windows Update service.</span></span> <span data-ttu-id="a5543-115">使用商務用 Windows Update，您可以控制更新程序&mdash;的多個環節，例如哪些裝置在何時取得哪些更新。</span><span class="sxs-lookup"><span data-stu-id="a5543-115">By using Windows Update for Business, you can control multiple aspects of the update process&mdash;that is, which devices get which updates at what time.</span></span> <span data-ttu-id="a5543-116">例如，您可以階段推出更新到裝置的一個子集，以進行測試，之後再向其餘的裝置階段推出更新。</span><span class="sxs-lookup"><span data-stu-id="a5543-116">For example, you can roll out updates to a subset of devices for testing, then later roll out updates to the remaining devices.</span></span> <span data-ttu-id="a5543-117">或者，您可以針對不同類型的更新定義不同的更新排程。</span><span class="sxs-lookup"><span data-stu-id="a5543-117">Or, you can define different update schedules for different types of updates.</span></span>

> [!NOTE]  
> <span data-ttu-id="a5543-118">針對 HoloLens 裝置，您可以自動管理功能更新 (每年發行兩次) 和品質更新 (按月或按需發行，包括重大安全性更新)。</span><span class="sxs-lookup"><span data-stu-id="a5543-118">For HoloLens devices, you can automatically manage feature updates (released two times a year) and quality updates (released monthly or as required, including critical security updates).</span></span> <span data-ttu-id="a5543-119">如需更新類型的詳細資訊，請參閱[商務用 Windows Update 所管理的更新類型](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)。</span><span class="sxs-lookup"><span data-stu-id="a5543-119">For more information about update types, see [Types of updates managed by Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).</span></span>

<span data-ttu-id="a5543-120">您可以使用行動裝置管理 (MDM) 解決方案 (例如 Microsoft Intune) 中的原則，來設定 HoloLens 的商務用 Windows Update 設定。</span><span class="sxs-lookup"><span data-stu-id="a5543-120">You can configure Windows Update for Business settings for HoloLens by using policies in a Mobile Device Management (MDM) solution such as Microsoft Intune.</span></span>

### <span data-ttu-id="a5543-121">使用 Microsoft Intune 來管理商務用 Windows Update</span><span class="sxs-lookup"><span data-stu-id="a5543-121">Managing Windows Update for Business by using Microsoft Intune</span></span>

<span data-ttu-id="a5543-122">如需如何使用 Intune 來設定商務用 Windows Update 的詳細討論，請參閱[在 Intune 中管理 Windows 10 軟體更新](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="a5543-122">For a detailed discussion about how to use Intune to configure Windows Update for Business, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="a5543-123">有關 HoloLens 支援的特定 Intune 功能的更多資訊，請參閱 [HoloLens 支援的 Intune 更新管理功能](#intune-update-management-functions-that-hololens-supports)。</span><span class="sxs-lookup"><span data-stu-id="a5543-123">For more information about the specific Intune functionality that HoloLens supports, see [Intune update management functions that HoloLens supports](#intune-update-management-functions-that-hololens-supports).</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="a5543-124">Intune 提供管理更新的兩種原則類型： *Windows 10 更新通道*和 *Windows 10 版功能更新*。</span><span class="sxs-lookup"><span data-stu-id="a5543-124">Intune provides two policy types for managing updates: *Windows 10 update ring* and *Windows 10 feature update*.</span></span> <span data-ttu-id="a5543-125">Windows 10 功能更新原則類型目前處於公開預覽狀態，且不支援 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="a5543-125">The Windows 10 feature update policy type is in public preview at this time and is not supported for HoloLens.</span></span>
>  
> <span data-ttu-id="a5543-126">您可以使用 Windows 10 更新通道原則來管理 HoloLens 2 更新。</span><span class="sxs-lookup"><span data-stu-id="a5543-126">You can use Windows 10 update ring policies to manage HoloLens 2 updates.</span></span>

### <span data-ttu-id="a5543-127">設定 HoloLens 2 或 HoloLens (第 1 代) 的更新原則</span><span class="sxs-lookup"><span data-stu-id="a5543-127">Configure update policies for HoloLens 2 or HoloLens (1st gen)</span></span>

<span data-ttu-id="a5543-128">本節將說明可用來管理 HoloLens 2 或 HoloLens (第 1 代) 更新的原則。</span><span class="sxs-lookup"><span data-stu-id="a5543-128">This section describes the policies that you can use to manage updates for either HoloLens 2 or HoloLens (1st gen).</span></span> <span data-ttu-id="a5543-129">如需有關針對 HoloLens 2 所提供功能的詳細資訊，請參閱[計畫及設定 HoloLens 2 的更新階段推出](#plan-and-configure-update-rollouts-for-hololens-2)。</span><span class="sxs-lookup"><span data-stu-id="a5543-129">For more information about the functionality that is available for HoloLens 2, see [Plan and configure update rollouts for HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).</span></span>

<span data-ttu-id="a5543-130">[原則 CSP - 更新](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update)會定義設定商務用 Windows Update 的原則。</span><span class="sxs-lookup"><span data-stu-id="a5543-130">[Policy CSP - Update](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) defines the policies that configure Windows Update for Business.</span></span>

> [!NOTE]  
> <span data-ttu-id="a5543-131">如需特定版本 HoloLens 支援的特定原則設定服務提供者 (CSP) 清單，請參閱 [HoloLens 裝置支援的原則 CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)。</span><span class="sxs-lookup"><span data-stu-id="a5543-131">For a list of specific policy configuration service providers (CSPs) that are supported by specific editions of HoloLens, see [Policy CSPs supported by HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices).</span></span>

#### <span data-ttu-id="a5543-132">設定自動檢查更新</span><span class="sxs-lookup"><span data-stu-id="a5543-132">Configure automatic checks for updates</span></span>

<span data-ttu-id="a5543-133">您可以使用 **Update/AllowAutoUpdate** 原則來管理自動更新行為，例如掃描、下載及安裝更新。</span><span class="sxs-lookup"><span data-stu-id="a5543-133">You can use the **Update/AllowAutoUpdate** policy to manage automatic update behavior, such as scanning, downloading, and installing updates.</span></span> <span data-ttu-id="a5543-134">如需此原則可用設定的詳細資訊，請參閱 [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)。</span><span class="sxs-lookup"><span data-stu-id="a5543-134">For more information about the available settings for this policy, see [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).</span></span>

> [!NOTE]  
> <span data-ttu-id="a5543-135">在 Microsoft Intune 中，您可以使用**自動更新行為** 來變更此原則。</span><span class="sxs-lookup"><span data-stu-id="a5543-135">In Microsoft Intune, you can use **Automatic Update Behavior** to change this policy.</span></span> <span data-ttu-id="a5543-136">如需詳細資訊，請參閱[管理 Intune 中的 Windows 10 軟體更新](https://docs.microsoft.com/intune/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="a5543-136">For more information, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span></span>

#### <span data-ttu-id="a5543-137">設定更新排程</span><span class="sxs-lookup"><span data-stu-id="a5543-137">Configure an update schedule</span></span>

<span data-ttu-id="a5543-138">若要設定套用更新的方式和時間，請使用下列原則：</span><span class="sxs-lookup"><span data-stu-id="a5543-138">To configure how and when updates are applied, use the following policies:</span></span>

- [<span data-ttu-id="a5543-139">Update/ScheduledInstallDay</span><span class="sxs-lookup"><span data-stu-id="a5543-139">Update/ScheduledInstallDay</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - <span data-ttu-id="a5543-140">值：**0** – **7** (0 = 每天、1 = 星期日、7 = 星期六) </span><span class="sxs-lookup"><span data-stu-id="a5543-140">Values: **0**–**7** (0 = every day, 1 = Sunday, 7 = Saturday)</span></span>
  - <span data-ttu-id="a5543-141">預設值：**0** (每天)</span><span class="sxs-lookup"><span data-stu-id="a5543-141">Default value: **0** (every day)</span></span>
- [<span data-ttu-id="a5543-142">Update/ScheduledInstallTime</span><span class="sxs-lookup"><span data-stu-id="a5543-142">Update/ScheduledInstallTime</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - <span data-ttu-id="a5543-143">值：0–23 (0 = 午夜，23 = 下午 11 點) </span><span class="sxs-lookup"><span data-stu-id="a5543-143">Values: 0–23 (0 = midnight, 23 = 11 PM)</span></span>
  - <span data-ttu-id="a5543-144">預設值：下午 3 點</span><span class="sxs-lookup"><span data-stu-id="a5543-144">Default value: 3 PM</span></span>

#### <span data-ttu-id="a5543-145">僅限執行 Windows 10 版本1607 的裝置</span><span class="sxs-lookup"><span data-stu-id="a5543-145">For devices that run Windows 10, version 1607 only</span></span>

<span data-ttu-id="a5543-146">您可以使用下列更新原則將裝置設定為從 Windows Server Update Services (WSUS) 取得更新，而非從 Windows Update：</span><span class="sxs-lookup"><span data-stu-id="a5543-146">You can use the following update policies to configure devices to get updates from Windows Server Update Service (WSUS), instead of from Windows Update:</span></span>

- [<span data-ttu-id="a5543-147">Update/AllowUpdateService</span><span class="sxs-lookup"><span data-stu-id="a5543-147">Update/AllowUpdateService</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [<span data-ttu-id="a5543-148">Update/RequireUpdateApproval</span><span class="sxs-lookup"><span data-stu-id="a5543-148">Update/RequireUpdateApproval</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [<span data-ttu-id="a5543-149">Update/UpdateServiceUrl</span><span class="sxs-lookup"><span data-stu-id="a5543-149">Update/UpdateServiceUrl</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <span data-ttu-id="a5543-150">規劃和設定 HoloLens 2 的更新階段性推出</span><span class="sxs-lookup"><span data-stu-id="a5543-150">Plan and configure update rollouts for HoloLens 2</span></span>

<span data-ttu-id="a5543-151">HoloLens 2 比 HoloLens (第 1 代) 支援更多更新自動化功能。</span><span class="sxs-lookup"><span data-stu-id="a5543-151">HoloLens 2 supports more update automation features than HoloLens (1st gen) does.</span></span> <span data-ttu-id="a5543-152">如果您使用 Microsoft Intune 來管理商務用 Windows Update 原則，則尤其如此。</span><span class="sxs-lookup"><span data-stu-id="a5543-152">This is especially true if you use Microsoft Intune to manage Windows Update for Business policies.</span></span> <span data-ttu-id="a5543-153">這些功能可讓您更輕鬆地在組織中規劃和實施更新階段性推出。</span><span class="sxs-lookup"><span data-stu-id="a5543-153">These features make it easier for you to plan and implement update rollouts across your organization.</span></span>

#### <span data-ttu-id="a5543-154">規劃更新策略</span><span class="sxs-lookup"><span data-stu-id="a5543-154">Plan the update strategy</span></span>

<span data-ttu-id="a5543-155">商務用 Windows Update 有支援延遲原則。</span><span class="sxs-lookup"><span data-stu-id="a5543-155">Windows Updates for Business supports deferral policies.</span></span> <span data-ttu-id="a5543-156">Microsoft 發行更新之後，您可以使用延遲原則，來定義在裝置上安裝該更新之前要等待多久。</span><span class="sxs-lookup"><span data-stu-id="a5543-156">After Microsoft releases an update, you can use a deferral policy to define how long to wait before installing that update on devices.</span></span> <span data-ttu-id="a5543-157">將裝置的子集 (又稱為*更新通道*) 與不同的延遲原則相關聯，您就可以協調貴組織的更新階段性推出策略。</span><span class="sxs-lookup"><span data-stu-id="a5543-157">By associating subsets of your devices (also known as *update rings*) with different deferral policies, you can coordinate an update rollout strategy for your organization.</span></span>

<span data-ttu-id="a5543-158">例如假設組織擁有1,000 個裝置，且必須以五波更新裝置。</span><span class="sxs-lookup"><span data-stu-id="a5543-158">For example, consider an organization that has 1,000 devices, and has to update the devices in five waves.</span></span> <span data-ttu-id="a5543-159">組織可以建立五個更新通道，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="a5543-159">The organization can create five update rings, as shown in the following table.</span></span>

|<span data-ttu-id="a5543-160">群組</span><span class="sxs-lookup"><span data-stu-id="a5543-160">Group</span></span> |<span data-ttu-id="a5543-161">裝置數量</span><span class="sxs-lookup"><span data-stu-id="a5543-161">Number of devices</span></span> |<span data-ttu-id="a5543-162">延遲 (天) </span><span class="sxs-lookup"><span data-stu-id="a5543-162">Deferral (days)</span></span> |
| ---| :---: | :---: |
|<span data-ttu-id="a5543-163">群組 1 (IT 員工)</span><span class="sxs-lookup"><span data-stu-id="a5543-163">Grp 1 (IT staff)</span></span> |<span data-ttu-id="a5543-164">5</span><span class="sxs-lookup"><span data-stu-id="a5543-164">5</span></span> |<span data-ttu-id="a5543-165">0</span><span class="sxs-lookup"><span data-stu-id="a5543-165">0</span></span> |
|<span data-ttu-id="a5543-166">群組 2 (早期採用者)</span><span class="sxs-lookup"><span data-stu-id="a5543-166">Grp 2 (early adopters)</span></span> |<span data-ttu-id="a5543-167">50</span><span class="sxs-lookup"><span data-stu-id="a5543-167">50</span></span> |<span data-ttu-id="a5543-168">60</span><span class="sxs-lookup"><span data-stu-id="a5543-168">60</span></span> |
|<span data-ttu-id="a5543-169">群組 3 (主要 1)</span><span class="sxs-lookup"><span data-stu-id="a5543-169">Grp 3 (main 1)</span></span> |<span data-ttu-id="a5543-170">250</span><span class="sxs-lookup"><span data-stu-id="a5543-170">250</span></span> |<span data-ttu-id="a5543-171">120</span><span class="sxs-lookup"><span data-stu-id="a5543-171">120</span></span> |
|<span data-ttu-id="a5543-172">群組 4 (主要 2)</span><span class="sxs-lookup"><span data-stu-id="a5543-172">Grp 4 (main 2)</span></span> |<span data-ttu-id="a5543-173">300</span><span class="sxs-lookup"><span data-stu-id="a5543-173">300</span></span> |<span data-ttu-id="a5543-174">150</span><span class="sxs-lookup"><span data-stu-id="a5543-174">150</span></span> |
|<span data-ttu-id="a5543-175">群組 5 (主要 3)</span><span class="sxs-lookup"><span data-stu-id="a5543-175">Grp 5 (main 3)</span></span> |<span data-ttu-id="a5543-176">395</span><span class="sxs-lookup"><span data-stu-id="a5543-176">395</span></span> |<span data-ttu-id="a5543-177">180</span><span class="sxs-lookup"><span data-stu-id="a5543-177">180</span></span> |

<span data-ttu-id="a5543-178">以下是一段時間之後，階段推出在整個組織的進展方式。</span><span class="sxs-lookup"><span data-stu-id="a5543-178">Here's how the rollout progresses over time to the whole organization.</span></span>

![部署更新的時間表](./images/hololens-updates-timeline.png)

#### <span data-ttu-id="a5543-180">設定更新延遲原則</span><span class="sxs-lookup"><span data-stu-id="a5543-180">Configure an update deferral policy</span></span>

<span data-ttu-id="a5543-181">延遲原則是指定更新可用的日期，以及更新提供給裝置使用的日期之間的天數。</span><span class="sxs-lookup"><span data-stu-id="a5543-181">A deferral policy specifies the number of days between the date on which an update becomes available and the date on which the update is offered to a device.</span></span>

<span data-ttu-id="a5543-182">您可以設定不同的延遲來進行功能更新和品質更新。</span><span class="sxs-lookup"><span data-stu-id="a5543-182">You can configure different deferrals for feature updates and quality updates.</span></span> <span data-ttu-id="a5543-183">下表列出每一類型使用的特定原則和每個類別的最大延遲。</span><span class="sxs-lookup"><span data-stu-id="a5543-183">The following table lists the specific policies to use for each type, and the maximum deferral for each.</span></span>

|<span data-ttu-id="a5543-184">類別</span><span class="sxs-lookup"><span data-stu-id="a5543-184">Category</span></span> |<span data-ttu-id="a5543-185">原則</span><span class="sxs-lookup"><span data-stu-id="a5543-185">Policy</span></span> |<span data-ttu-id="a5543-186">延遲上限</span><span class="sxs-lookup"><span data-stu-id="a5543-186">Maximum deferral</span></span> |
| --- | --- | --- |
|<span data-ttu-id="a5543-187">功能更新</span><span class="sxs-lookup"><span data-stu-id="a5543-187">Feature updates</span></span> |<span data-ttu-id="a5543-188">DeferFeatureUpdatesPeriodInDays</span><span class="sxs-lookup"><span data-stu-id="a5543-188">DeferFeatureUpdatesPeriodInDays</span></span> |<span data-ttu-id="a5543-189">365 天</span><span class="sxs-lookup"><span data-stu-id="a5543-189">365 days</span></span> |
|<span data-ttu-id="a5543-190">品質更新</span><span class="sxs-lookup"><span data-stu-id="a5543-190">Quality updates</span></span> |<span data-ttu-id="a5543-191">DeferQualityUpdatesPeriodInDays</span><span class="sxs-lookup"><span data-stu-id="a5543-191">DeferQualityUpdatesPeriodInDays</span></span> |<span data-ttu-id="a5543-192">30 天</span><span class="sxs-lookup"><span data-stu-id="a5543-192">30 days</span></span> |

#### <span data-ttu-id="a5543-193">HoloLens 支援的 Intune 更新管理功能</span><span class="sxs-lookup"><span data-stu-id="a5543-193">Intune update management functions that HoloLens supports</span></span>

<span data-ttu-id="a5543-194">您可以使用下列 Intune 更新管理功能來管理 HoloLens 更新。</span><span class="sxs-lookup"><span data-stu-id="a5543-194">You can use the following Intune update management functions to manage updates for HoloLens.</span></span>

- <span data-ttu-id="a5543-195">**建立**和**指派**：這些函數會將 Windows 10 更新通道新增到更新通道清單中。</span><span class="sxs-lookup"><span data-stu-id="a5543-195">**Create** and **Assign**: These functions add a Windows 10 update ring to the list of update rings.</span></span> <span data-ttu-id="a5543-196">如需詳細資訊，請參閱[建立並指派更新通道](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)。</span><span class="sxs-lookup"><span data-stu-id="a5543-196">For more information, see [Create and assign update rings](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).</span></span>

- <span data-ttu-id="a5543-197">**暫停**：如果在部署功能或品質更新時遇到問題，您可以暫停更新 35 天 (從指定日期開始)。</span><span class="sxs-lookup"><span data-stu-id="a5543-197">**Pause**: If you encounter a problem when you deploy a feature or quality update, you can pause the update for 35 days (starting from a specified date).</span></span> <span data-ttu-id="a5543-198">當您解決或緩解問題之前，暫停會防止其他裝置安裝更新。</span><span class="sxs-lookup"><span data-stu-id="a5543-198">This pause prevents other devices from installing the update until you resolve or mitigate the problem.</span></span> <span data-ttu-id="a5543-199">如果您暫停功能更新，系統仍會提供品質更新，以確保其保持安全。</span><span class="sxs-lookup"><span data-stu-id="a5543-199">If you pause a feature update, quality updates are still offered to devices to make sure that they stay secure.</span></span> <span data-ttu-id="a5543-200">當更新類型暫停時，該通道的 [概觀] 窗格會顯示該更新類型繼續前剩餘的天數。</span><span class="sxs-lookup"><span data-stu-id="a5543-200">When an update type is paused, the Overview pane for that ring displays how many days remain before that update type resumes.</span></span> <span data-ttu-id="a5543-201">經過指定時間後，暫停會自動到期，而更新程式會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="a5543-201">After the specified time has passed, the pause automatically expires, and the update process resumes.</span></span>

  <span data-ttu-id="a5543-202">當更新通道暫停時，您可以選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="a5543-202">While the update ring is paused, you can select either of the following options:</span></span>

  - <span data-ttu-id="a5543-203">**延長**：將更新類型的暫停時間延長 35天。</span><span class="sxs-lookup"><span data-stu-id="a5543-203">**Extend**: Extend the pause period for an update type for 35 days.</span></span>
  - <span data-ttu-id="a5543-204">**繼續**：將該通道的更新還原為使用中的作業。</span><span class="sxs-lookup"><span data-stu-id="a5543-204">**Resume**: Restore updates for that ring to active operation.</span></span> <span data-ttu-id="a5543-205">您可以視需要再次暫停更新通道。</span><span class="sxs-lookup"><span data-stu-id="a5543-205">You can pause the update ring again, if it is necessary.</span></span>

  > [!NOTE]  
  > <span data-ttu-id="a5543-206">HoloLens 2 裝置不支援更新通道的 [解除安裝]\*\*\*\* 作業。</span><span class="sxs-lookup"><span data-stu-id="a5543-206">The **Uninstall** operation for update rings is not supported for HoloLens 2 devices.</span></span>

## <span data-ttu-id="a5543-207">手動檢查更新</span><span class="sxs-lookup"><span data-stu-id="a5543-207">Manually check for updates</span></span>

<span data-ttu-id="a5543-208">雖然 HoloLens 會定期檢查系統更新，但有時候您可能會想手動檢查。</span><span class="sxs-lookup"><span data-stu-id="a5543-208">Although HoloLens periodically checks for system updates, there may be circumstances in which you want to manually check.</span></span>

<span data-ttu-id="a5543-209">若要手動檢查更新，請移至 [設定]\*\*\*\*  >  [更新 & 安全性]\*\*\*\*  >  [檢查更新]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a5543-209">To manually check for updates, go to **Settings** > **Update & Security** > **Check for updates**.</span></span> <span data-ttu-id="a5543-210">如果 [設定] 應用程式指出您的裝置為最新狀態，表示已擁有目前可用的所有更新。</span><span class="sxs-lookup"><span data-stu-id="a5543-210">If the Settings app indicates that your device is up to date, you have all the updates that are currently available.</span></span>

## <span data-ttu-id="a5543-211">手動復原更新</span><span class="sxs-lookup"><span data-stu-id="a5543-211">Manually roll back an update</span></span>

<span data-ttu-id="a5543-212">在某些情況下，您可能會想還原到舊版的 HoloLens 軟體。</span><span class="sxs-lookup"><span data-stu-id="a5543-212">In some cases, you might want to revert to a previous version of the HoloLens software.</span></span> <span data-ttu-id="a5543-213">執行此作業的程序取決於您使用的是 HoloLens 2 或 HoloLens (第 1 代)。</span><span class="sxs-lookup"><span data-stu-id="a5543-213">The process for doing this depends on whether you are using HoloLens 2 or HoloLens (1st gen).</span></span>

### <span data-ttu-id="a5543-214">還原為先前版本 (HoloLens 2)</span><span class="sxs-lookup"><span data-stu-id="a5543-214">Revert to a previous version (HoloLens 2)</span></span>

<span data-ttu-id="a5543-215">您可以使用 [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 將您的 HoloLens 重設為較舊的版本，以復原更新並返回舊版的 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="a5543-215">You can roll back updates and return to a previous version of HoloLens 2 by using the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="a5543-216">還原為較舊的版本會刪除您的個人檔案和設定。</span><span class="sxs-lookup"><span data-stu-id="a5543-216">Reverting to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="a5543-217">若要還原為先前版本的 HoloLens 2，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a5543-217">To revert to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="a5543-218">請確認您沒有任何手機或 Windows 裝置插入電腦。</span><span class="sxs-lookup"><span data-stu-id="a5543-218">Make sure that you don't have any phones or Windows devices plugged in to your computer.</span></span>
1. <span data-ttu-id="a5543-219">在您的電腦上，從 Microsoft Store下載 [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)。</span><span class="sxs-lookup"><span data-stu-id="a5543-219">On your computer, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="a5543-220">下載[最新的 HoloLens 2 發行版本](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="a5543-220">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="a5543-221">下載完成後，請開啟**檔案總管** > [下載]\*\*\*\*，以滑鼠右鍵按一下您剛下載的壓縮 (.zip) 資料夾，然後選取 [解壓全部]\*\*\*\* > [解壓縮]\*\*\*\* 來展開檔案。</span><span class="sxs-lookup"><span data-stu-id="a5543-221">After these downloads finish, open **File explorer** > **Downloads**, right-click the compressed (.zip) folder that you just downloaded, and then select **Extract all** > **Extract** to expand the file.</span></span>
1. <span data-ttu-id="a5543-222">使用 USB-A 轉 USB-C 纜線將您的 HoloLens 裝置連線至電腦。</span><span class="sxs-lookup"><span data-stu-id="a5543-222">Use a USB-A to USB-C cable to connect your HoloLens device to your computer.</span></span> <span data-ttu-id="a5543-223">(即使您過去一直是使用其他纜線來連接 HoloLens，以上仍是最適合的纜線)。</span><span class="sxs-lookup"><span data-stu-id="a5543-223">Even if you've been using other cables to connect your HoloLens, this kind of cable works best.</span></span>
1. <span data-ttu-id="a5543-224">Advanced Recovery Companion 會自動偵測您的 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="a5543-224">The Advanced Recovery Companion automatically detects your HoloLens device.</span></span> <span data-ttu-id="a5543-225">選取 [Microsoft HoloLens]\*\*\*\* 動態磚。</span><span class="sxs-lookup"><span data-stu-id="a5543-225">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="a5543-226">在下一個畫面中，選取 [手動套件選取]\*\*\*\*，然後開啟先前展開的資料夾。</span><span class="sxs-lookup"><span data-stu-id="a5543-226">On the next screen, select **Manual package selection**, and then open the folder that you previously expanded.</span></span>
1. <span data-ttu-id="a5543-227">選取安裝 (.ffu) 檔案。</span><span class="sxs-lookup"><span data-stu-id="a5543-227">Select the installation (.ffu) file.</span></span>
1. <span data-ttu-id="a5543-228">選取 [安裝軟體]\*\*\*\*，然後依照指示進行。</span><span class="sxs-lookup"><span data-stu-id="a5543-228">Select **Install software**, and then follow the instructions.</span></span>

### <span data-ttu-id="a5543-229">還原為先前版本 (HoloLens (第1代))</span><span class="sxs-lookup"><span data-stu-id="a5543-229">Revert to a previous version (HoloLens (1st gen))</span></span>

<span data-ttu-id="a5543-230">您可以使用 [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) 將您的 HoloLens 重設為較舊的版本，以便復原更新並返回舊版 HoloLens (第 1 代)。</span><span class="sxs-lookup"><span data-stu-id="a5543-230">You can roll back updates and return to a previous version of HoloLens (1st gen) by using the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="a5543-231">還原為較舊的 HoloLens 版本會刪除您的個人檔案和設定。</span><span class="sxs-lookup"><span data-stu-id="a5543-231">Reverting to an earlier HoloLens version deletes your personal files and settings.</span></span>

<span data-ttu-id="a5543-232">若要還原為先前版本 HoloLens (第1代) ，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a5543-232">To revert to a previous version of HoloLens (1st gen), follow these steps:</span></span>

1. <span data-ttu-id="a5543-233">請確認您沒有任何手機或 Windows 裝置插入電腦。</span><span class="sxs-lookup"><span data-stu-id="a5543-233">Make sure that you don't have any phones or Windows devices plugged into your computer.</span></span>
1. <span data-ttu-id="a5543-234">在您的電腦上，下載 [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)。</span><span class="sxs-lookup"><span data-stu-id="a5543-234">On your computer, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="a5543-235">下載 [HoloLens 年度更新版復原套件](https://aka.ms/hololensrecovery)。</span><span class="sxs-lookup"><span data-stu-id="a5543-235">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="a5543-236">下載完成後，請開啟**檔案總管** > [下載]\*\*\*\*，以滑鼠右鍵按一下您剛下載的壓縮 (.zip) 資料夾，然後選取 [解壓全部]\*\*\*\* > [解壓縮]\*\*\*\* 來展開檔案。</span><span class="sxs-lookup"><span data-stu-id="a5543-236">After the downloads finish, open **File explorer** > **Downloads**, right-click the compressed (.zip) folder that you just downloaded, and then select **Extract all** > **Extract** to expand the file.</span></span>
1. <span data-ttu-id="a5543-237">使用隨附於 HoloLens 裝置的 micro-USB 纜線，將您的 HoloLens 裝置連線至電腦。</span><span class="sxs-lookup"><span data-stu-id="a5543-237">Use the micro-USB cable that was provided together with your HoloLens device to connect your HoloLens device to your computer.</span></span> <span data-ttu-id="a5543-238">即使您已使用其他纜線來連接 HoloLens 裝置，這仍是最適合的纜線。</span><span class="sxs-lookup"><span data-stu-id="a5543-238">Even if you've been using other cables to connect your HoloLens device, this one works best.</span></span>
1. <span data-ttu-id="a5543-239">WDRT 會自動偵測您的 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="a5543-239">The WDRT automatically detects your HoloLens device.</span></span> <span data-ttu-id="a5543-240">選取 [Microsoft HoloLens]\*\*\*\* 動態磚。</span><span class="sxs-lookup"><span data-stu-id="a5543-240">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="a5543-241">在下一個畫面中，選取 [手動套件選取]\*\*\*\*，然後開啟先前展開的資料夾。</span><span class="sxs-lookup"><span data-stu-id="a5543-241">On the next screen, select **Manual package selection**, and then open the folder that you previously expanded.</span></span>
1. <span data-ttu-id="a5543-242">選取安裝 (.ffu) 檔案。</span><span class="sxs-lookup"><span data-stu-id="a5543-242">Select the installation (.ffu) file.</span></span>
1. <span data-ttu-id="a5543-243">選取 [安裝軟體]\*\*\*\*，然後依照指示進行。</span><span class="sxs-lookup"><span data-stu-id="a5543-243">Select **Install software**, and then follow the instructions.</span></span>

**<span data-ttu-id="a5543-244">如果 WDRT 不會偵測您的裝置</span><span class="sxs-lookup"><span data-stu-id="a5543-244">If WDRT doesn't detect your device</span></span>**

<span data-ttu-id="a5543-245">如果 WDRT 不會偵測您的 HoloLens 裝置，請嘗試重新啟動電腦。</span><span class="sxs-lookup"><span data-stu-id="a5543-245">If WDRT doesn't detect your HoloLens device, try restarting your computer.</span></span> <span data-ttu-id="a5543-246">如果仍然無法解決問題，請選取 [沒有偵測到我的裝置]\*\*\*\*，選取 **Microsoft HoloLens**，然後按照指示進行。</span><span class="sxs-lookup"><span data-stu-id="a5543-246">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="a5543-247">相關文章</span><span class="sxs-lookup"><span data-stu-id="a5543-247">Related articles</span></span>

- [<span data-ttu-id="a5543-248">HoloLens 2 版本資訊</span><span class="sxs-lookup"><span data-stu-id="a5543-248">HoloLens 2 release notes</span></span>](https://docs.microsoft.com/hololens/hololens-release-notes)
- [<span data-ttu-id="a5543-249">什麼是商務用 Windows Update?</span><span class="sxs-lookup"><span data-stu-id="a5543-249">What is Windows Update for Business?</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [<span data-ttu-id="a5543-250">指派裝置到維護通道進行 Windows 10 更新</span><span class="sxs-lookup"><span data-stu-id="a5543-250">Assign devices to servicing channels for Windows 10 updates</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [<span data-ttu-id="a5543-251">在 Intune 中管理 Windows 10 軟體更新</span><span class="sxs-lookup"><span data-stu-id="a5543-251">Manage Windows 10 software updates in Intune</span></span>](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
