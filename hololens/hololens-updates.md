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
ms.date: 10/13/2020
ms.reviewer: jarrettr
manager: jarrettr
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 3a2246296c5ab8aa86dfaa419ed02aa5a961dbfc
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163135"
---
# <span data-ttu-id="ab83e-103">管理 HoloLens 更新</span><span class="sxs-lookup"><span data-stu-id="ab83e-103">Manage HoloLens updates</span></span>

<span data-ttu-id="ab83e-104">HoloLens 使用 Windows Update 的方式與其他 Windows 10 裝置相同。</span><span class="sxs-lookup"><span data-stu-id="ab83e-104">HoloLens uses Windows Update in the same manner as other Windows 10 devices.</span></span> <span data-ttu-id="ab83e-105">當有可用的更新時，系統會在您下次插入裝置並聯線到網際網路時，自動下載並安裝。</span><span class="sxs-lookup"><span data-stu-id="ab83e-105">When an update is available, it is automatically downloaded and installed the next time that your device is plugged in and connected to the internet.</span></span> <span data-ttu-id="ab83e-106">本文說明如何管理企業或其他受管理環境中的更新。</span><span class="sxs-lookup"><span data-stu-id="ab83e-106">This article describes how to manage updates in an enterprise or other managed environment.</span></span> <span data-ttu-id="ab83e-107">如需如何管理個別 HoloLens 裝置更新的相關資訊，請參閱[更新 HoloLens](hololens-update-hololens.md)。</span><span class="sxs-lookup"><span data-stu-id="ab83e-107">For information about how to manage updates to individual HoloLens devices, see [Update HoloLens](hololens-update-hololens.md).</span></span>

## <span data-ttu-id="ab83e-108">自動管理更新</span><span class="sxs-lookup"><span data-stu-id="ab83e-108">Manage updates automatically</span></span>

### <span data-ttu-id="ab83e-109">使用商務用 Windows Update 來管理更新</span><span class="sxs-lookup"><span data-stu-id="ab83e-109">Managing updates by using Windows Update for Business</span></span>

<span data-ttu-id="ab83e-110">Windows Holographic for Business 可使用 [商務用 Windows Update](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) 來管理更新。</span><span class="sxs-lookup"><span data-stu-id="ab83e-110">Windows Holographic for Business can use [Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) to manage updates.</span></span> <span data-ttu-id="ab83e-111">所有 HoloLens 2 裝置都可以使用 Windows Holographic for Business。</span><span class="sxs-lookup"><span data-stu-id="ab83e-111">All HoloLens 2 devices can use Windows Holographic for Business.</span></span> <span data-ttu-id="ab83e-112">請確認其使用 Windows Holographic for Business 組建10.0.18362.1042 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="ab83e-112">Make sure that they use Windows Holographic for Business build 10.0.18362.1042 or a later build.</span></span> <span data-ttu-id="ab83e-113">如果您使用的是 HoloLens (第 1 代) 裝置，則必須[將其升級至 Windows Holographic for Business](hololens1-upgrade-enterprise.md)，以便管理其更新。</span><span class="sxs-lookup"><span data-stu-id="ab83e-113">If you have HoloLens (1st gen) devices, you have to [upgrade them to Windows Holographic for Business](hololens1-upgrade-enterprise.md) in order to manage their updates.</span></span>

<span data-ttu-id="ab83e-114">商務用 Windows Update 會直接將 HoloLens 裝置連線至 Windows Update 服務。</span><span class="sxs-lookup"><span data-stu-id="ab83e-114">Windows Update for Business connects HoloLens devices directly to the Windows Update service.</span></span> <span data-ttu-id="ab83e-115">使用商務用 Windows Update，您可以控制更新程序&mdash;的多個環節，例如哪些裝置在何時取得哪些更新。</span><span class="sxs-lookup"><span data-stu-id="ab83e-115">By using Windows Update for Business, you can control multiple aspects of the update process&mdash;that is, which devices get which updates at what time.</span></span> <span data-ttu-id="ab83e-116">例如，您可以階段推出更新到裝置的一個子集，以進行測試，之後再向其餘的裝置階段推出更新。</span><span class="sxs-lookup"><span data-stu-id="ab83e-116">For example, you can roll out updates to a subset of devices for testing, then later roll out updates to the remaining devices.</span></span> <span data-ttu-id="ab83e-117">或者，您可以針對不同類型的更新定義不同的更新排程。</span><span class="sxs-lookup"><span data-stu-id="ab83e-117">Or, you can define different update schedules for different types of updates.</span></span>

> [!NOTE]  
> <span data-ttu-id="ab83e-118">針對 HoloLens 裝置，您可以自動管理功能更新 (每年發行兩次) 和品質更新 (按月或按需發行，包括重大安全性更新)。</span><span class="sxs-lookup"><span data-stu-id="ab83e-118">For HoloLens devices, you can automatically manage feature updates (released two times a year) and quality updates (released monthly or as required, including critical security updates).</span></span> <span data-ttu-id="ab83e-119">如需更新類型的詳細資訊，請參閱[商務用 Windows Update 所管理的更新類型](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)。</span><span class="sxs-lookup"><span data-stu-id="ab83e-119">For more information about update types, see [Types of updates managed by Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).</span></span>

<span data-ttu-id="ab83e-120">您可以使用行動裝置管理 (MDM) 解決方案 (例如 Microsoft Intune) 中的原則，來設定 HoloLens 的商務用 Windows Update 設定。</span><span class="sxs-lookup"><span data-stu-id="ab83e-120">You can configure Windows Update for Business settings for HoloLens by using policies in a Mobile Device Management (MDM) solution such as Microsoft Intune.</span></span>

### <span data-ttu-id="ab83e-121">使用 Microsoft Intune 來管理商務用 Windows Update</span><span class="sxs-lookup"><span data-stu-id="ab83e-121">Managing Windows Update for Business by using Microsoft Intune</span></span>

<span data-ttu-id="ab83e-122">如需如何使用 Intune 來設定商務用 Windows Update 的詳細討論，請參閱[在 Intune 中管理 Windows 10 軟體更新](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="ab83e-122">For a detailed discussion about how to use Intune to configure Windows Update for Business, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="ab83e-123">有關 HoloLens 支援的特定 Intune 功能的更多資訊，請參閱 [HoloLens 支援的 Intune 更新管理功能](#intune-update-management-functions-that-hololens-supports)。</span><span class="sxs-lookup"><span data-stu-id="ab83e-123">For more information about the specific Intune functionality that HoloLens supports, see [Intune update management functions that HoloLens supports](#intune-update-management-functions-that-hololens-supports).</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="ab83e-124">Intune 提供管理更新的兩種原則類型： *Windows 10 更新通道*和 *Windows 10 版功能更新*。</span><span class="sxs-lookup"><span data-stu-id="ab83e-124">Intune provides two policy types for managing updates: *Windows 10 update ring* and *Windows 10 feature update*.</span></span> <span data-ttu-id="ab83e-125">Windows 10 功能更新原則類型目前處於公開預覽狀態，且不支援 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="ab83e-125">The Windows 10 feature update policy type is in public preview at this time and is not supported for HoloLens.</span></span>
>  
> <span data-ttu-id="ab83e-126">您可以使用 Windows 10 更新通道原則來管理 HoloLens 2 更新。</span><span class="sxs-lookup"><span data-stu-id="ab83e-126">You can use Windows 10 update ring policies to manage HoloLens 2 updates.</span></span>

### <span data-ttu-id="ab83e-127">設定 HoloLens 2 或 HoloLens (第 1 代) 的更新原則</span><span class="sxs-lookup"><span data-stu-id="ab83e-127">Configure update policies for HoloLens 2 or HoloLens (1st gen)</span></span>

<span data-ttu-id="ab83e-128">本節將說明可用來管理 HoloLens 2 或 HoloLens (第 1 代) 更新的原則。</span><span class="sxs-lookup"><span data-stu-id="ab83e-128">This section describes the policies that you can use to manage updates for either HoloLens 2 or HoloLens (1st gen).</span></span> <span data-ttu-id="ab83e-129">如需有關針對 HoloLens 2 所提供功能的詳細資訊，請參閱[計畫及設定 HoloLens 2 的更新階段推出](#plan-and-configure-update-rollouts-for-hololens-2)。</span><span class="sxs-lookup"><span data-stu-id="ab83e-129">For more information about the functionality that is available for HoloLens 2, see [Plan and configure update rollouts for HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).</span></span>

<span data-ttu-id="ab83e-130">[原則 CSP - 更新](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update)會定義設定商務用 Windows Update 的原則。</span><span class="sxs-lookup"><span data-stu-id="ab83e-130">[Policy CSP - Update](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) defines the policies that configure Windows Update for Business.</span></span>

> [!NOTE]  
> <span data-ttu-id="ab83e-131">如需特定版本 HoloLens 支援的特定原則設定服務提供者 (CSP) 清單，請參閱 [HoloLens 裝置支援的原則 CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)。</span><span class="sxs-lookup"><span data-stu-id="ab83e-131">For a list of specific policy configuration service providers (CSPs) that are supported by specific editions of HoloLens, see [Policy CSPs supported by HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices).</span></span>

#### <span data-ttu-id="ab83e-132">設定自動檢查更新</span><span class="sxs-lookup"><span data-stu-id="ab83e-132">Configure automatic checks for updates</span></span>

<span data-ttu-id="ab83e-133">您可以使用 **Update/AllowAutoUpdate** 原則來管理自動更新行為，例如掃描、下載及安裝更新。</span><span class="sxs-lookup"><span data-stu-id="ab83e-133">You can use the **Update/AllowAutoUpdate** policy to manage automatic update behavior, such as scanning, downloading, and installing updates.</span></span> <span data-ttu-id="ab83e-134">如需此原則可用設定的詳細資訊，請參閱 [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)。</span><span class="sxs-lookup"><span data-stu-id="ab83e-134">For more information about the available settings for this policy, see [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).</span></span>

> [!NOTE]  
> <span data-ttu-id="ab83e-135">在 Microsoft Intune 中，您可以使用**自動更新行為** 來變更此原則。</span><span class="sxs-lookup"><span data-stu-id="ab83e-135">In Microsoft Intune, you can use **Automatic Update Behavior** to change this policy.</span></span> <span data-ttu-id="ab83e-136">如需詳細資訊，請參閱[管理 Intune 中的 Windows 10 軟體更新](https://docs.microsoft.com/intune/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="ab83e-136">For more information, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span></span>

#### <span data-ttu-id="ab83e-137">設定更新排程</span><span class="sxs-lookup"><span data-stu-id="ab83e-137">Configure an update schedule</span></span>

<span data-ttu-id="ab83e-138">若要設定套用更新的方式和時間，請使用下列原則：</span><span class="sxs-lookup"><span data-stu-id="ab83e-138">To configure how and when updates are applied, use the following policies:</span></span>

- [<span data-ttu-id="ab83e-139">Update/ScheduledInstallDay</span><span class="sxs-lookup"><span data-stu-id="ab83e-139">Update/ScheduledInstallDay</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - <span data-ttu-id="ab83e-140">值：**0** – **7** (0 = 每天、1 = 星期日、7 = 星期六) </span><span class="sxs-lookup"><span data-stu-id="ab83e-140">Values: **0**–**7** (0 = every day, 1 = Sunday, 7 = Saturday)</span></span>
  - <span data-ttu-id="ab83e-141">預設值：**0** (每天)</span><span class="sxs-lookup"><span data-stu-id="ab83e-141">Default value: **0** (every day)</span></span>
- [<span data-ttu-id="ab83e-142">Update/ScheduledInstallTime</span><span class="sxs-lookup"><span data-stu-id="ab83e-142">Update/ScheduledInstallTime</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - <span data-ttu-id="ab83e-143">值：0–23 (0 = 午夜，23 = 下午 11 點) </span><span class="sxs-lookup"><span data-stu-id="ab83e-143">Values: 0–23 (0 = midnight, 23 = 11 PM)</span></span>
  - <span data-ttu-id="ab83e-144">預設值：下午 3 點</span><span class="sxs-lookup"><span data-stu-id="ab83e-144">Default value: 3 PM</span></span>

#### <span data-ttu-id="ab83e-145">設定使用時間</span><span class="sxs-lookup"><span data-stu-id="ab83e-145">Configure active hours</span></span>
<span data-ttu-id="ab83e-146">從 [Windows 全像攝影版，版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 開始，IT 系統管理員可以指定 HoloLens 2 裝置的使用時間範圍。</span><span class="sxs-lookup"><span data-stu-id="ab83e-146">Starting with [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) an IT Admin can specify the active hours range for HoloLens 2 devices.</span></span>

<span data-ttu-id="ab83e-147">[使用時間] 會識別您預期裝置處於使用中的一段時間。</span><span class="sxs-lookup"><span data-stu-id="ab83e-147">Active hours identify the period of time when you expect the device to be in use.</span></span> <span data-ttu-id="ab83e-148">更新之後的自動重新啟動會在使用時間之外發生。</span><span class="sxs-lookup"><span data-stu-id="ab83e-148">Automatic restarts after an update will occur outside of the active hours.</span></span> <span data-ttu-id="ab83e-149">指定的範圍將會從使用時間的開始時間來計算。</span><span class="sxs-lookup"><span data-stu-id="ab83e-149">The specified range will be counted from the active hours start time.</span></span> <span data-ttu-id="ab83e-150">您可以如,[使用時間設定 MDM](https://docs.microsoft.com/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm) 中所述來使用 MDM。</span><span class="sxs-lookup"><span data-stu-id="ab83e-150">You can use MDM, as described in [Configuring active hours with MDM](https://docs.microsoft.com/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm).</span></span> <span data-ttu-id="ab83e-151">MDM 使用 Policy CSP 中的 Update/ActiveHoursStart and Update/ActiveHoursEnd 和 Update/ActiveHoursMaxRange 設定來設定使用時間。</span><span class="sxs-lookup"><span data-stu-id="ab83e-151">MDM uses the Update/ActiveHoursStart and Update/ActiveHoursEnd and Update/ActiveHoursMaxRange settings in the Policy CSP to configure active hours.</span></span>

-   <span data-ttu-id="ab83e-152">[Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend) - 此值設定結束時間。</span><span class="sxs-lookup"><span data-stu-id="ab83e-152">[Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend) - This value sets the end time.</span></span> <span data-ttu-id="ab83e-153">從開始時間起最多 12 小時。</span><span class="sxs-lookup"><span data-stu-id="ab83e-153">There is a 12 hour maximum from start time.</span></span>
    -   <span data-ttu-id="ab83e-154">支援的值為 0-23，其中 0 為上午 12 點，1 為上午 1 點，依此類推。</span><span class="sxs-lookup"><span data-stu-id="ab83e-154">Supported values are 0-23, where 0 is 12 AM, 1 is 1 AM, etc.</span></span>
    -   <span data-ttu-id="ab83e-155">預設值為 17 (下午 5 點)。</span><span class="sxs-lookup"><span data-stu-id="ab83e-155">The default is 17 (5 PM).</span></span>
-   <span data-ttu-id="ab83e-156">[Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) - 此值設定從開始時間起的最大使用時間 (小時) 數。</span><span class="sxs-lookup"><span data-stu-id="ab83e-156">[Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) - This value sets max number of active hours from start time.</span></span>
    -   <span data-ttu-id="ab83e-157">支援的值為 8-18。</span><span class="sxs-lookup"><span data-stu-id="ab83e-157">Supported values are 8-18.</span></span>
    -   <span data-ttu-id="ab83e-158">預設值為 18 (小時)。</span><span class="sxs-lookup"><span data-stu-id="ab83e-158">The default value is 18 (hours).</span></span>
-   <span data-ttu-id="ab83e-159">[Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart) - 此值設定開始時間。</span><span class="sxs-lookup"><span data-stu-id="ab83e-159">[Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart) - This value sets the start time.</span></span> <span data-ttu-id="ab83e-160">從結束時間起最多 12 小時。</span><span class="sxs-lookup"><span data-stu-id="ab83e-160">There is a 12 hour maximum from end time.</span></span>
    -   <span data-ttu-id="ab83e-161">支援的值為 0-23，其中 0 為上午 12 點，1 為上午 1 點，依此類推。</span><span class="sxs-lookup"><span data-stu-id="ab83e-161">Supported values are 0-23, where 0 is 12 AM, 1 is 1 AM, etc.</span></span>
    -   <span data-ttu-id="ab83e-162">預設值為 8 (上午8點)。</span><span class="sxs-lookup"><span data-stu-id="ab83e-162">The default value is 8 (8 AM).</span></span>

#### <span data-ttu-id="ab83e-163">僅限執行 Windows 10 版本1607 的裝置</span><span class="sxs-lookup"><span data-stu-id="ab83e-163">For devices that run Windows 10, version 1607 only</span></span>

<span data-ttu-id="ab83e-164">您可以使用下列更新原則將裝置設定為從 Windows Server Update Services (WSUS) 取得更新，而非從 Windows Update：</span><span class="sxs-lookup"><span data-stu-id="ab83e-164">You can use the following update policies to configure devices to get updates from Windows Server Update Service (WSUS), instead of from Windows Update:</span></span>

- [<span data-ttu-id="ab83e-165">Update/AllowUpdateService</span><span class="sxs-lookup"><span data-stu-id="ab83e-165">Update/AllowUpdateService</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [<span data-ttu-id="ab83e-166">Update/RequireUpdateApproval</span><span class="sxs-lookup"><span data-stu-id="ab83e-166">Update/RequireUpdateApproval</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [<span data-ttu-id="ab83e-167">Update/UpdateServiceUrl</span><span class="sxs-lookup"><span data-stu-id="ab83e-167">Update/UpdateServiceUrl</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <span data-ttu-id="ab83e-168">規劃和設定 HoloLens 2 的更新階段性推出</span><span class="sxs-lookup"><span data-stu-id="ab83e-168">Plan and configure update rollouts for HoloLens 2</span></span>

<span data-ttu-id="ab83e-169">HoloLens 2 比 HoloLens (第 1 代) 支援更多更新自動化功能。</span><span class="sxs-lookup"><span data-stu-id="ab83e-169">HoloLens 2 supports more update automation features than HoloLens (1st gen) does.</span></span> <span data-ttu-id="ab83e-170">如果您使用 Microsoft Intune 來管理商務用 Windows Update 原則，則尤其如此。</span><span class="sxs-lookup"><span data-stu-id="ab83e-170">This is especially true if you use Microsoft Intune to manage Windows Update for Business policies.</span></span> <span data-ttu-id="ab83e-171">這些功能可讓您更輕鬆地在組織中規劃和實施更新階段性推出。</span><span class="sxs-lookup"><span data-stu-id="ab83e-171">These features make it easier for you to plan and implement update rollouts across your organization.</span></span>

#### <span data-ttu-id="ab83e-172">規劃更新策略</span><span class="sxs-lookup"><span data-stu-id="ab83e-172">Plan the update strategy</span></span>

<span data-ttu-id="ab83e-173">商務用 Windows Update 有支援延遲原則。</span><span class="sxs-lookup"><span data-stu-id="ab83e-173">Windows Updates for Business supports deferral policies.</span></span> <span data-ttu-id="ab83e-174">Microsoft 發行更新之後，您可以使用延遲原則，來定義在裝置上安裝該更新之前要等待多久。</span><span class="sxs-lookup"><span data-stu-id="ab83e-174">After Microsoft releases an update, you can use a deferral policy to define how long to wait before installing that update on devices.</span></span> <span data-ttu-id="ab83e-175">將裝置的子集 (又稱為*更新通道*) 與不同的延遲原則相關聯，您就可以協調貴組織的更新階段性推出策略。</span><span class="sxs-lookup"><span data-stu-id="ab83e-175">By associating subsets of your devices (also known as *update rings*) with different deferral policies, you can coordinate an update rollout strategy for your organization.</span></span>

<span data-ttu-id="ab83e-176">例如假設組織擁有1,000 個裝置，且必須以五波更新裝置。</span><span class="sxs-lookup"><span data-stu-id="ab83e-176">For example, consider an organization that has 1,000 devices, and has to update the devices in five waves.</span></span> <span data-ttu-id="ab83e-177">組織可以建立五個更新通道，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="ab83e-177">The organization can create five update rings, as shown in the following table.</span></span>

|<span data-ttu-id="ab83e-178">群組</span><span class="sxs-lookup"><span data-stu-id="ab83e-178">Group</span></span> |<span data-ttu-id="ab83e-179">裝置數量</span><span class="sxs-lookup"><span data-stu-id="ab83e-179">Number of devices</span></span> |<span data-ttu-id="ab83e-180">延遲 (天) </span><span class="sxs-lookup"><span data-stu-id="ab83e-180">Deferral (days)</span></span> |
| ---| :---: | :---: |
|<span data-ttu-id="ab83e-181">群組 1 (IT 員工)</span><span class="sxs-lookup"><span data-stu-id="ab83e-181">Grp 1 (IT staff)</span></span> |<span data-ttu-id="ab83e-182">5</span><span class="sxs-lookup"><span data-stu-id="ab83e-182">5</span></span> |<span data-ttu-id="ab83e-183">0</span><span class="sxs-lookup"><span data-stu-id="ab83e-183">0</span></span> |
|<span data-ttu-id="ab83e-184">群組 2 (早期採用者)</span><span class="sxs-lookup"><span data-stu-id="ab83e-184">Grp 2 (early adopters)</span></span> |<span data-ttu-id="ab83e-185">50</span><span class="sxs-lookup"><span data-stu-id="ab83e-185">50</span></span> |<span data-ttu-id="ab83e-186">60</span><span class="sxs-lookup"><span data-stu-id="ab83e-186">60</span></span> |
|<span data-ttu-id="ab83e-187">群組 3 (主要 1)</span><span class="sxs-lookup"><span data-stu-id="ab83e-187">Grp 3 (main 1)</span></span> |<span data-ttu-id="ab83e-188">250</span><span class="sxs-lookup"><span data-stu-id="ab83e-188">250</span></span> |<span data-ttu-id="ab83e-189">120</span><span class="sxs-lookup"><span data-stu-id="ab83e-189">120</span></span> |
|<span data-ttu-id="ab83e-190">群組 4 (主要 2)</span><span class="sxs-lookup"><span data-stu-id="ab83e-190">Grp 4 (main 2)</span></span> |<span data-ttu-id="ab83e-191">300</span><span class="sxs-lookup"><span data-stu-id="ab83e-191">300</span></span> |<span data-ttu-id="ab83e-192">150</span><span class="sxs-lookup"><span data-stu-id="ab83e-192">150</span></span> |
|<span data-ttu-id="ab83e-193">群組 5 (主要 3)</span><span class="sxs-lookup"><span data-stu-id="ab83e-193">Grp 5 (main 3)</span></span> |<span data-ttu-id="ab83e-194">395</span><span class="sxs-lookup"><span data-stu-id="ab83e-194">395</span></span> |<span data-ttu-id="ab83e-195">180</span><span class="sxs-lookup"><span data-stu-id="ab83e-195">180</span></span> |

<span data-ttu-id="ab83e-196">以下是一段時間之後，階段推出在整個組織的進展方式。</span><span class="sxs-lookup"><span data-stu-id="ab83e-196">Here's how the rollout progresses over time to the whole organization.</span></span>

![部署更新的時間表](./images/hololens-updates-timeline.png)

#### <span data-ttu-id="ab83e-198">設定更新延遲原則</span><span class="sxs-lookup"><span data-stu-id="ab83e-198">Configure an update deferral policy</span></span>

<span data-ttu-id="ab83e-199">延遲原則是指定更新可用的日期，以及更新提供給裝置使用的日期之間的天數。</span><span class="sxs-lookup"><span data-stu-id="ab83e-199">A deferral policy specifies the number of days between the date on which an update becomes available and the date on which the update is offered to a device.</span></span>

<span data-ttu-id="ab83e-200">您可以設定不同的延遲來進行功能更新和品質更新。</span><span class="sxs-lookup"><span data-stu-id="ab83e-200">You can configure different deferrals for feature updates and quality updates.</span></span> <span data-ttu-id="ab83e-201">下表列出每一類型使用的特定原則和每個類別的最大延遲。</span><span class="sxs-lookup"><span data-stu-id="ab83e-201">The following table lists the specific policies to use for each type, and the maximum deferral for each.</span></span>

|<span data-ttu-id="ab83e-202">類別</span><span class="sxs-lookup"><span data-stu-id="ab83e-202">Category</span></span> |<span data-ttu-id="ab83e-203">原則</span><span class="sxs-lookup"><span data-stu-id="ab83e-203">Policy</span></span> |<span data-ttu-id="ab83e-204">延遲上限</span><span class="sxs-lookup"><span data-stu-id="ab83e-204">Maximum deferral</span></span> |
| --- | --- | --- |
|<span data-ttu-id="ab83e-205">功能更新</span><span class="sxs-lookup"><span data-stu-id="ab83e-205">Feature updates</span></span> |<span data-ttu-id="ab83e-206">DeferFeatureUpdatesPeriodInDays</span><span class="sxs-lookup"><span data-stu-id="ab83e-206">DeferFeatureUpdatesPeriodInDays</span></span> |<span data-ttu-id="ab83e-207">365 天</span><span class="sxs-lookup"><span data-stu-id="ab83e-207">365 days</span></span> |
|<span data-ttu-id="ab83e-208">品質更新</span><span class="sxs-lookup"><span data-stu-id="ab83e-208">Quality updates</span></span> |<span data-ttu-id="ab83e-209">DeferQualityUpdatesPeriodInDays</span><span class="sxs-lookup"><span data-stu-id="ab83e-209">DeferQualityUpdatesPeriodInDays</span></span> |<span data-ttu-id="ab83e-210">30 天</span><span class="sxs-lookup"><span data-stu-id="ab83e-210">30 days</span></span> |

#### <span data-ttu-id="ab83e-211">透過裝置暫停更新</span><span class="sxs-lookup"><span data-stu-id="ab83e-211">Pause Updates via Device</span></span>

<span data-ttu-id="ab83e-212">如果使用者沒有 MDM 的存取權，他們可以在 [2004 版或更高版本的 Windows 全像攝影版](hololens-release-notes.md#windows-holographic-version-2004)的 HoloLens 2 裝置上手動暫停更新 35 天。</span><span class="sxs-lookup"><span data-stu-id="ab83e-212">If a user does not have access to MDM they can indivually Pause updates for up to 35 days manually on a HoloLens 2 device on build [Windows Holographic, version 2004](hololens-release-notes.md#windows-holographic-version-2004) or later.</span></span> <span data-ttu-id="ab83e-213">用戶可以透過瀏覽至 **[設定] -> [更新與安全性] -> [進階選項]** 向下捲動以**暫停更新**，並選擇暫停更新的日期。</span><span class="sxs-lookup"><span data-stu-id="ab83e-213">Users can reach this setting by navigating to **Settings -> Update & Security -> Advanced options** scroll down to **Pause updates** and select the date until which they will pause updates.</span></span> <span data-ttu-id="ab83e-214">一旦使用者達到暫停限制，裝置將需要取得新的更新，因為它們可以再次暫停。</span><span class="sxs-lookup"><span data-stu-id="ab83e-214">Once a user reached the pause limit, the device will need to get new updates because they can pause again.</span></span> 

<span data-ttu-id="ab83e-215">從 [20H2 版 Windows 全像攝影版](hololens-release-notes.md#windows-holographic-version-20h2)開始，這個暫停更新功能可以為 Hololens 2 裝置管理。</span><span class="sxs-lookup"><span data-stu-id="ab83e-215">Starting with [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2), this pause updates fuction can be managed for HoloLens 2 devices.</span></span> 
- <span data-ttu-id="ab83e-216">[Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)。</span><span class="sxs-lookup"><span data-stu-id="ab83e-216">[Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).</span></span>
    - <span data-ttu-id="ab83e-217">0 (預設值)：已啟用。</span><span class="sxs-lookup"><span data-stu-id="ab83e-217">0 (default) – Enabled</span></span>
    - <span data-ttu-id="ab83e-218">1 – 已停用。</span><span class="sxs-lookup"><span data-stu-id="ab83e-218">1 – Disabled</span></span>

#### <span data-ttu-id="ab83e-219">HoloLens 支援的 Intune 更新管理功能</span><span class="sxs-lookup"><span data-stu-id="ab83e-219">Intune update management functions that HoloLens supports</span></span>

<span data-ttu-id="ab83e-220">您可以使用下列 Intune 更新管理功能來管理 HoloLens 更新。</span><span class="sxs-lookup"><span data-stu-id="ab83e-220">You can use the following Intune update management functions to manage updates for HoloLens.</span></span>

- <span data-ttu-id="ab83e-221">**建立**和**指派**：這些函數會將 Windows 10 更新通道新增到更新通道清單中。</span><span class="sxs-lookup"><span data-stu-id="ab83e-221">**Create** and **Assign**: These functions add a Windows 10 update ring to the list of update rings.</span></span> <span data-ttu-id="ab83e-222">如需詳細資訊，請參閱[建立並指派更新通道](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)。</span><span class="sxs-lookup"><span data-stu-id="ab83e-222">For more information, see [Create and assign update rings](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).</span></span>

- <span data-ttu-id="ab83e-223">**暫停**：如果在部署功能或品質更新時遇到問題，您可以暫停更新 35 天 (從指定日期開始)。</span><span class="sxs-lookup"><span data-stu-id="ab83e-223">**Pause**: If you encounter a problem when you deploy a feature or quality update, you can pause the update for 35 days (starting from a specified date).</span></span> <span data-ttu-id="ab83e-224">當您解決或緩解問題之前，暫停會防止其他裝置安裝更新。</span><span class="sxs-lookup"><span data-stu-id="ab83e-224">This pause prevents other devices from installing the update until you resolve or mitigate the problem.</span></span> <span data-ttu-id="ab83e-225">如果您暫停功能更新，系統仍會提供品質更新，以確保其保持安全。</span><span class="sxs-lookup"><span data-stu-id="ab83e-225">If you pause a feature update, quality updates are still offered to devices to make sure that they stay secure.</span></span> <span data-ttu-id="ab83e-226">當更新類型暫停時，該通道的 [概觀] 窗格會顯示該更新類型繼續前剩餘的天數。</span><span class="sxs-lookup"><span data-stu-id="ab83e-226">When an update type is paused, the Overview pane for that ring displays how many days remain before that update type resumes.</span></span> <span data-ttu-id="ab83e-227">經過指定時間後，暫停會自動到期，而更新程式會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="ab83e-227">After the specified time has passed, the pause automatically expires, and the update process resumes.</span></span>

  <span data-ttu-id="ab83e-228">當更新通道暫停時，您可以選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="ab83e-228">While the update ring is paused, you can select either of the following options:</span></span>

  - <span data-ttu-id="ab83e-229">**延長**：將更新類型的暫停時間延長 35天。</span><span class="sxs-lookup"><span data-stu-id="ab83e-229">**Extend**: Extend the pause period for an update type for 35 days.</span></span>
  - <span data-ttu-id="ab83e-230">**繼續**：將該通道的更新還原為使用中的作業。</span><span class="sxs-lookup"><span data-stu-id="ab83e-230">**Resume**: Restore updates for that ring to active operation.</span></span> <span data-ttu-id="ab83e-231">您可以視需要再次暫停更新通道。</span><span class="sxs-lookup"><span data-stu-id="ab83e-231">You can pause the update ring again, if it is necessary.</span></span>

  > [!NOTE]  
  > <span data-ttu-id="ab83e-232">HoloLens 2 裝置不支援更新通道的 [解除安裝]\*\*\*\* 作業。</span><span class="sxs-lookup"><span data-stu-id="ab83e-232">The **Uninstall** operation for update rings is not supported for HoloLens 2 devices.</span></span>

## <span data-ttu-id="ab83e-233">手動檢查更新</span><span class="sxs-lookup"><span data-stu-id="ab83e-233">Manually check for updates</span></span>

<span data-ttu-id="ab83e-234">雖然 HoloLens 會定期檢查系統更新，但有時候您可能會想手動檢查。</span><span class="sxs-lookup"><span data-stu-id="ab83e-234">Although HoloLens periodically checks for system updates, there may be circumstances in which you want to manually check.</span></span>

<span data-ttu-id="ab83e-235">若要手動檢查更新，請移至 [設定]\*\*\*\*  >  [更新 & 安全性]\*\*\*\*  >  [檢查更新]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab83e-235">To manually check for updates, go to **Settings** > **Update & Security** > **Check for updates**.</span></span> <span data-ttu-id="ab83e-236">如果 [設定] 應用程式指出您的裝置為最新狀態，表示已擁有目前可用的所有更新。</span><span class="sxs-lookup"><span data-stu-id="ab83e-236">If the Settings app indicates that your device is up to date, you have all the updates that are currently available.</span></span>

## <span data-ttu-id="ab83e-237">手動復原更新</span><span class="sxs-lookup"><span data-stu-id="ab83e-237">Manually roll back an update</span></span>

<span data-ttu-id="ab83e-238">在某些情況下，您可能會想還原到舊版的 HoloLens 軟體。</span><span class="sxs-lookup"><span data-stu-id="ab83e-238">In some cases, you might want to revert to a previous version of the HoloLens software.</span></span> <span data-ttu-id="ab83e-239">執行此作業的程序取決於您使用的是 HoloLens 2 或 HoloLens (第 1 代)。</span><span class="sxs-lookup"><span data-stu-id="ab83e-239">The process for doing this depends on whether you are using HoloLens 2 or HoloLens (1st gen).</span></span>

### <span data-ttu-id="ab83e-240">還原為先前版本 (HoloLens 2)</span><span class="sxs-lookup"><span data-stu-id="ab83e-240">Revert to a previous version (HoloLens 2)</span></span>

<span data-ttu-id="ab83e-241">您可以使用 [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 將您的 HoloLens 重設為較舊的版本，以復原更新並返回舊版的 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="ab83e-241">You can roll back updates and return to a previous version of HoloLens 2 by using the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="ab83e-242">還原為較舊的版本會刪除您的個人檔案和設定。</span><span class="sxs-lookup"><span data-stu-id="ab83e-242">Reverting to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="ab83e-243">若要還原為先前版本的 HoloLens 2，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ab83e-243">To revert to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="ab83e-244">請確認您沒有任何手機或 Windows 裝置插入電腦。</span><span class="sxs-lookup"><span data-stu-id="ab83e-244">Make sure that you don't have any phones or Windows devices plugged in to your computer.</span></span>
1. <span data-ttu-id="ab83e-245">在您的電腦上，從 Microsoft Store下載 [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)。</span><span class="sxs-lookup"><span data-stu-id="ab83e-245">On your computer, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="ab83e-246">下載[最新的 HoloLens 2 發行版本](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="ab83e-246">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="ab83e-247">下載完成後，請開啟**檔案總管** > [下載]\*\*\*\*，以滑鼠右鍵按一下您剛下載的壓縮 (.zip) 資料夾，然後選取 [解壓全部]\*\*\*\* > [解壓縮]\*\*\*\* 來展開檔案。</span><span class="sxs-lookup"><span data-stu-id="ab83e-247">After these downloads finish, open **File explorer** > **Downloads**, right-click the compressed (.zip) folder that you just downloaded, and then select **Extract all** > **Extract** to expand the file.</span></span>
1. <span data-ttu-id="ab83e-248">使用 USB-A 轉 USB-C 纜線將您的 HoloLens 裝置連線至電腦。</span><span class="sxs-lookup"><span data-stu-id="ab83e-248">Use a USB-A to USB-C cable to connect your HoloLens device to your computer.</span></span> <span data-ttu-id="ab83e-249">(即使您過去一直是使用其他纜線來連接 HoloLens，以上仍是最適合的纜線)。</span><span class="sxs-lookup"><span data-stu-id="ab83e-249">Even if you've been using other cables to connect your HoloLens, this kind of cable works best.</span></span>
1. <span data-ttu-id="ab83e-250">Advanced Recovery Companion 會自動偵測您的 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="ab83e-250">The Advanced Recovery Companion automatically detects your HoloLens device.</span></span> <span data-ttu-id="ab83e-251">選取 [Microsoft HoloLens]\*\*\*\* 動態磚。</span><span class="sxs-lookup"><span data-stu-id="ab83e-251">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="ab83e-252">在下一個畫面中，選取 [手動套件選取]\*\*\*\*，然後開啟先前展開的資料夾。</span><span class="sxs-lookup"><span data-stu-id="ab83e-252">On the next screen, select **Manual package selection**, and then open the folder that you previously expanded.</span></span>
1. <span data-ttu-id="ab83e-253">選取安裝 (.ffu) 檔案。</span><span class="sxs-lookup"><span data-stu-id="ab83e-253">Select the installation (.ffu) file.</span></span>
1. <span data-ttu-id="ab83e-254">選取 [安裝軟體]\*\*\*\*，然後依照指示進行。</span><span class="sxs-lookup"><span data-stu-id="ab83e-254">Select **Install software**, and then follow the instructions.</span></span>

### <span data-ttu-id="ab83e-255">還原為先前版本 (HoloLens (第1代))</span><span class="sxs-lookup"><span data-stu-id="ab83e-255">Revert to a previous version (HoloLens (1st gen))</span></span>

<span data-ttu-id="ab83e-256">您可以使用 [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) 將您的 HoloLens 重設為較舊的版本，以便復原更新並返回舊版 HoloLens (第 1 代)。</span><span class="sxs-lookup"><span data-stu-id="ab83e-256">You can roll back updates and return to a previous version of HoloLens (1st gen) by using the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="ab83e-257">還原為較舊的 HoloLens 版本會刪除您的個人檔案和設定。</span><span class="sxs-lookup"><span data-stu-id="ab83e-257">Reverting to an earlier HoloLens version deletes your personal files and settings.</span></span>

<span data-ttu-id="ab83e-258">若要還原為先前版本 HoloLens (第1代) ，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ab83e-258">To revert to a previous version of HoloLens (1st gen), follow these steps:</span></span>

1. <span data-ttu-id="ab83e-259">請確認您沒有任何手機或 Windows 裝置插入電腦。</span><span class="sxs-lookup"><span data-stu-id="ab83e-259">Make sure that you don't have any phones or Windows devices plugged into your computer.</span></span>
1. <span data-ttu-id="ab83e-260">在您的電腦上，下載 [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)。</span><span class="sxs-lookup"><span data-stu-id="ab83e-260">On your computer, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="ab83e-261">下載 [HoloLens 年度更新版復原套件](https://aka.ms/hololensrecovery)。</span><span class="sxs-lookup"><span data-stu-id="ab83e-261">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="ab83e-262">下載完成後，請開啟**檔案總管** > [下載]\*\*\*\*，以滑鼠右鍵按一下您剛下載的壓縮 (.zip) 資料夾，然後選取 [解壓全部]\*\*\*\* > [解壓縮]\*\*\*\* 來展開檔案。</span><span class="sxs-lookup"><span data-stu-id="ab83e-262">After the downloads finish, open **File explorer** > **Downloads**, right-click the compressed (.zip) folder that you just downloaded, and then select **Extract all** > **Extract** to expand the file.</span></span>
1. <span data-ttu-id="ab83e-263">使用隨附於 HoloLens 裝置的 micro-USB 纜線，將您的 HoloLens 裝置連線至電腦。</span><span class="sxs-lookup"><span data-stu-id="ab83e-263">Use the micro-USB cable that was provided together with your HoloLens device to connect your HoloLens device to your computer.</span></span> <span data-ttu-id="ab83e-264">即使您已使用其他纜線來連接 HoloLens 裝置，這仍是最適合的纜線。</span><span class="sxs-lookup"><span data-stu-id="ab83e-264">Even if you've been using other cables to connect your HoloLens device, this one works best.</span></span>
1. <span data-ttu-id="ab83e-265">WDRT 會自動偵測您的 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="ab83e-265">The WDRT automatically detects your HoloLens device.</span></span> <span data-ttu-id="ab83e-266">選取 [Microsoft HoloLens]\*\*\*\* 動態磚。</span><span class="sxs-lookup"><span data-stu-id="ab83e-266">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="ab83e-267">在下一個畫面中，選取 [手動套件選取]\*\*\*\*，然後開啟先前展開的資料夾。</span><span class="sxs-lookup"><span data-stu-id="ab83e-267">On the next screen, select **Manual package selection**, and then open the folder that you previously expanded.</span></span>
1. <span data-ttu-id="ab83e-268">選取安裝 (.ffu) 檔案。</span><span class="sxs-lookup"><span data-stu-id="ab83e-268">Select the installation (.ffu) file.</span></span>
1. <span data-ttu-id="ab83e-269">選取 [安裝軟體]\*\*\*\*，然後依照指示進行。</span><span class="sxs-lookup"><span data-stu-id="ab83e-269">Select **Install software**, and then follow the instructions.</span></span>

**<span data-ttu-id="ab83e-270">如果 WDRT 不會偵測您的裝置</span><span class="sxs-lookup"><span data-stu-id="ab83e-270">If WDRT doesn't detect your device</span></span>**

<span data-ttu-id="ab83e-271">如果 WDRT 不會偵測您的 HoloLens 裝置，請嘗試重新啟動電腦。</span><span class="sxs-lookup"><span data-stu-id="ab83e-271">If WDRT doesn't detect your HoloLens device, try restarting your computer.</span></span> <span data-ttu-id="ab83e-272">如果仍然無法解決問題，請選取 [沒有偵測到我的裝置]\*\*\*\*，選取 **Microsoft HoloLens**，然後按照指示進行。</span><span class="sxs-lookup"><span data-stu-id="ab83e-272">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="ab83e-273">相關文章</span><span class="sxs-lookup"><span data-stu-id="ab83e-273">Related articles</span></span>

- [<span data-ttu-id="ab83e-274">HoloLens 2 版本資訊</span><span class="sxs-lookup"><span data-stu-id="ab83e-274">HoloLens 2 release notes</span></span>](https://docs.microsoft.com/hololens/hololens-release-notes)
- [<span data-ttu-id="ab83e-275">什麼是商務用 Windows Update?</span><span class="sxs-lookup"><span data-stu-id="ab83e-275">What is Windows Update for Business?</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [<span data-ttu-id="ab83e-276">指派裝置到維護通道進行 Windows 10 更新</span><span class="sxs-lookup"><span data-stu-id="ab83e-276">Assign devices to servicing channels for Windows 10 updates</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [<span data-ttu-id="ab83e-277">在 Intune 中管理 Windows 10 軟體更新</span><span class="sxs-lookup"><span data-stu-id="ab83e-277">Manage Windows 10 software updates in Intune</span></span>](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
