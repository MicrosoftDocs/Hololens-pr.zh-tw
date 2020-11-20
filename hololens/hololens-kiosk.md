---
title: 設定 HoloLens (第 1 代) 的 kiosk
description: 使用 kiosk 配置來鎖定 HoloLens 上的應用程式。
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f560dae725cbce8658bdf2a135c5061b5332f797
ms.sourcegitcommit: 456a88907d606f4c4532b153d5a848e214b6b8e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/19/2020
ms.locfileid: "11182004"
---
# <span data-ttu-id="cd169-103">設定 HoloLens (第 1 代) 的 kiosk</span><span class="sxs-lookup"><span data-stu-id="cd169-103">Set up HoloLens as a kiosk</span></span>

<span data-ttu-id="cd169-104">您可以將 HoloLens 裝置設定為固定用途的裝置（亦稱為 *kiosk*），方法是將裝置設定為在 kiosk 模式中執行。</span><span class="sxs-lookup"><span data-stu-id="cd169-104">You can configure a HoloLens device to function as a fixed-purpose device, also called a *kiosk*, by configuring the device to run in kiosk mode.</span></span> <span data-ttu-id="cd169-105">展臺模式會限制裝置上可用的應用程式 (或使用者) 。</span><span class="sxs-lookup"><span data-stu-id="cd169-105">Kiosk mode limits the applications (or users) that are available on the device.</span></span> <span data-ttu-id="cd169-106">Kiosk 模式是一種便利的功能，您可以用來將 HoloLens 裝置專用於商務應用程式，或在應用程式示範中使用 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="cd169-106">Kiosk mode is a convenient feature that you can use to dedicate a HoloLens device to business apps, or to use the HoloLens device in an app demo.</span></span>

<span data-ttu-id="cd169-107">本文提供有關 HoloLens 裝置專用之 kiosk 設定的各個方面的資訊。</span><span class="sxs-lookup"><span data-stu-id="cd169-107">This article provides information about aspects of kiosk configuration that are specific to HoloLens devices.</span></span> <span data-ttu-id="cd169-108">如需不同類型的 Windows 網亭以及如何進行設定的一般資訊，請參閱 [在 windows 桌上出版上設定網亭和數位簽章](https://docs.microsoft.com/windows/configuration/kiosk-methods)。</span><span class="sxs-lookup"><span data-stu-id="cd169-108">For general information about the different types of Windows-based kiosks and how to configure them, see [Configure kiosks and digital signs on Windows desktop editions](https://docs.microsoft.com/windows/configuration/kiosk-methods).</span></span>  

> [!IMPORTANT]  
> <span data-ttu-id="cd169-109">Kiosk 模式決定使用者登入裝置時可使用哪些 app。</span><span class="sxs-lookup"><span data-stu-id="cd169-109">Kiosk mode determines which apps are available when a user signs in to the device.</span></span> <span data-ttu-id="cd169-110">不過，kiosk 模式不是安全性方法。</span><span class="sxs-lookup"><span data-stu-id="cd169-110">However, kiosk mode is not a security method.</span></span> <span data-ttu-id="cd169-111">它不會停止「允許」 app，無法開啟其他不允許的應用程式。</span><span class="sxs-lookup"><span data-stu-id="cd169-111">It does not stop an "allowed" app from opening another app that is not allowed.</span></span> <span data-ttu-id="cd169-112">為了封鎖 app 或進程的開啟，請使用 [Windows Defender 應用程式控制項 (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) 來建立適當的原則。</span><span class="sxs-lookup"><span data-stu-id="cd169-112">In order to block apps or processes from opening, use [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) to create appropriate policies.</span></span>
>
> <span data-ttu-id="cd169-113">深入瞭解 Microsoft 服務，為使用者提供 HoloLens 2 所使用的高級安全等級，進一步瞭解 [狀態分隔與隔離資訊保護](security-state-separation-isolation.md#defender-protections)。</span><span class="sxs-lookup"><span data-stu-id="cd169-113">Learn more about the Microsoft services to give users an advanced level of security that HoloLens 2 uses, read more about [State separation and isolation - Defender protections](security-state-separation-isolation.md#defender-protections).</span></span> <span data-ttu-id="cd169-114">或者，瞭解如何 [使用 WDAC 和 Windows PowerShell，透過 Microsoft Intune 在 HoloLens 2 裝置上允許或封鎖 app](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)。</span><span class="sxs-lookup"><span data-stu-id="cd169-114">Or learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="cd169-115">您可以在單一 app 或多重應用程式設定中使用 kiosk 模式，而且您可以使用三個進程中的其中一個來設定和部署展臺設定。</span><span class="sxs-lookup"><span data-stu-id="cd169-115">You can use kiosk mode in either a single-app or a multi-app configuration, and you can use one of three processes to set up and deploy the kiosk configuration.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="cd169-116">刪除多重應用程式設定，會移除指派的存取功能所建立的使用者鎖定設定檔。</span><span class="sxs-lookup"><span data-stu-id="cd169-116">Deleting the multi-app configuration removes the user lockdown profiles that the assigned access feature created.</span></span> <span data-ttu-id="cd169-117">不過，它不會復原所有原則變更。</span><span class="sxs-lookup"><span data-stu-id="cd169-117">However, it does not revert all the policy changes.</span></span> <span data-ttu-id="cd169-118">若要復原這些原則，您必須將裝置重設成出廠設定。</span><span class="sxs-lookup"><span data-stu-id="cd169-118">To revert these policies, you have to reset the device to the factory settings.</span></span>

## <span data-ttu-id="cd169-119">規劃展臺部署</span><span class="sxs-lookup"><span data-stu-id="cd169-119">Plan the kiosk deployment</span></span>

<span data-ttu-id="cd169-120">規劃您的展臺時，您必須能夠回答下列問題。</span><span class="sxs-lookup"><span data-stu-id="cd169-120">When planning your Kiosk you'll need to be able to answer the following questions.</span></span> <span data-ttu-id="cd169-121">以下是閱讀此頁面時要考慮的一些決策，以及這些問題的一些考慮。</span><span class="sxs-lookup"><span data-stu-id="cd169-121">Here are some decisions to think about while reading this page and some considerations for these questions.</span></span>
1. **<span data-ttu-id="cd169-122">誰會使用您的資訊站，以及他們要使用哪 [種類型的帳戶 (s) ](hololens-identity.md) ？</span><span class="sxs-lookup"><span data-stu-id="cd169-122">Who will be using your Kiosk, and what [type of account(s)](hololens-identity.md) will they be using?</span></span>** <span data-ttu-id="cd169-123">這是您可能已進行的決定，而且不應該針對您的資訊亭進行調整，但會影響資訊亭的指派方式。</span><span class="sxs-lookup"><span data-stu-id="cd169-123">This is a decision you have likely already made and shouldn't be adjusted for the sake of your Kiosk, but will affect how the Kiosk is assigned later.</span></span>
1. **<span data-ttu-id="cd169-124">您是否需要針對每個使用者/群組或無法啟用某個資訊的展臺使用不同的網亭？</span><span class="sxs-lookup"><span data-stu-id="cd169-124">Do you need to have either different Kiosks per user/group or a Kiosk not enabled for some?</span></span>** <span data-ttu-id="cd169-125">如果是這樣，您會想透過 XML 建立您的展臺。</span><span class="sxs-lookup"><span data-stu-id="cd169-125">If so, you'll want to create your Kiosk via XML.</span></span> 
1. **<span data-ttu-id="cd169-126">您的展臺中會有多少應用程式？</span><span class="sxs-lookup"><span data-stu-id="cd169-126">How many apps will be in your Kiosk?</span></span>** <span data-ttu-id="cd169-127">如果您的應用程式多於1個，您需要多個應用程式亭。</span><span class="sxs-lookup"><span data-stu-id="cd169-127">If you have more than 1 app, you'll need a multi-app Kiosk.</span></span> 
1. **<span data-ttu-id="cd169-128">您的展臺中 (s) 應用程式？</span><span class="sxs-lookup"><span data-stu-id="cd169-128">Which app(s) will be in your Kiosk?</span></span>** <span data-ttu-id="cd169-129">除了您自己之外，請使用以下 Aumid 清單來新增任何 In-Box 應用程式。</span><span class="sxs-lookup"><span data-stu-id="cd169-129">Please use our list of AUMIDs below to add any In-Box apps in addition to your own.</span></span>
1. **<span data-ttu-id="cd169-130">您要如何規劃如何部署您的展臺？</span><span class="sxs-lookup"><span data-stu-id="cd169-130">How do you plan to deploy your Kiosk?</span></span>** <span data-ttu-id="cd169-131">如果您是在 MDM 中註冊裝置，則建議您使用 MDM 來部署您的展臺。</span><span class="sxs-lookup"><span data-stu-id="cd169-131">If you are enrolling device in MDM then we suggest using MDM to deploy your Kiosk.</span></span> <span data-ttu-id="cd169-132">如果您不是使用 MDM，就可以使用 [配套件] 進行部署。</span><span class="sxs-lookup"><span data-stu-id="cd169-132">If you are not using MDM then deployment with Provisioning Package is available.</span></span>  

### <span data-ttu-id="cd169-133">展臺模式需求</span><span class="sxs-lookup"><span data-stu-id="cd169-133">Kiosk mode requirements</span></span>

<span data-ttu-id="cd169-134">您可以將任何 HoloLens 2 裝置設定為使用 kiosk 模式。</span><span class="sxs-lookup"><span data-stu-id="cd169-134">You can configure any HoloLens 2 device to use kiosk mode.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd169-135">[展臺模式] 只有在裝置有 Windows 全息企業版時才能使用。</span><span class="sxs-lookup"><span data-stu-id="cd169-135">Kiosk mode is available only if the device has Windows Holographic for Business.</span></span> <span data-ttu-id="cd169-136">所有的 HoloLens 2 裝置都隨附 Windows 全息版，沒有其他版本。</span><span class="sxs-lookup"><span data-stu-id="cd169-136">All HoloLens 2 devices ship with Windows Holographic for Business and there are no other editions.</span></span> <span data-ttu-id="cd169-137">每個 HoloLens 2 裝置都能從盒中執行 Kiosk 模式。</span><span class="sxs-lookup"><span data-stu-id="cd169-137">Every HoloLens 2 devices is able to run Kiosk mode out of the box.</span></span>
>
> <span data-ttu-id="cd169-138">HoloLens (1 gen) 裝置必須以作業系統組建和 OS 版本進行升級。</span><span class="sxs-lookup"><span data-stu-id="cd169-138">HoloLens (1st gen) devices need to be upgraded both in terms of OS build and OS edition.</span></span> <span data-ttu-id="cd169-139">以下是將 HoloLens (1 gen) 更新為 [Windows 全息](hololens1-upgrade-enterprise.md) 版版本的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="cd169-139">Here is more information on updating a HoloLens (1st gen) to [Windows Holographic for Business](hololens1-upgrade-enterprise.md) edition.</span></span> <span data-ttu-id="cd169-140">若要將 HoloLens (1 gen) 裝置更新為使用 kiosk 模式，您必須先確定裝置執行的是 Windows 10 版本1803或更新版本。</span><span class="sxs-lookup"><span data-stu-id="cd169-140">To update a HoloLens (1st gen) device to use kiosk mode, you must first make sure that the device runs Windows 10, version 1803, or a later version.</span></span> <span data-ttu-id="cd169-141">如果您已使用 Windows 裝置恢復工具將 HoloLens (1 gen) 裝置復原為預設組建，或者如果您已安裝最新的更新，則您的裝置已準備好進行設定。</span><span class="sxs-lookup"><span data-stu-id="cd169-141">If you have used the Windows Device Recovery Tool to recover your HoloLens (1st gen) device to its default build, or if you have installed the most recent updates, your device is ready to configure.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="cd169-142">若要協助保護在 kiosk 模式下執行的裝置，請考慮新增裝置管理原則，以關閉 USB 連線等功能。</span><span class="sxs-lookup"><span data-stu-id="cd169-142">To help protect devices that run in kiosk mode, consider adding device management policies that turn off features such as USB connectivity.</span></span> <span data-ttu-id="cd169-143">此外，請檢查您的 [更新鈴聲] 設定，以確定在上班時間期間不會進行自動更新。</span><span class="sxs-lookup"><span data-stu-id="cd169-143">Additionally, check your update ring settings to make sure that automatic updates do not occur during business hours.</span></span>

### <span data-ttu-id="cd169-144">在單一應用程式亭或多重應用程式亭之間進行決定</span><span class="sxs-lookup"><span data-stu-id="cd169-144">Decide between a single-app kiosk or a multi-app kiosk</span></span>

<span data-ttu-id="cd169-145">當使用者登入裝置時，單一 app 展臺會啟動指定的 app。</span><span class="sxs-lookup"><span data-stu-id="cd169-145">A single-app kiosk starts the specified app when the user signs in to the device.</span></span> <span data-ttu-id="cd169-146">[開始] 功能表停用，就像是 Cortana 一樣。</span><span class="sxs-lookup"><span data-stu-id="cd169-146">The Start menu is disabled, as is Cortana.</span></span> <span data-ttu-id="cd169-147">HoloLens 2 裝置沒有回應 [開始](hololens2-basic-usage.md#start-gesture) 手勢。</span><span class="sxs-lookup"><span data-stu-id="cd169-147">A HoloLens 2 device does not respond to the [Start](hololens2-basic-usage.md#start-gesture) gesture.</span></span> <span data-ttu-id="cd169-148">HoloLens (1 gen) 裝置不會回應 [bloom](hololens1-basic-usage.md) 手勢。</span><span class="sxs-lookup"><span data-stu-id="cd169-148">A HoloLens (1st gen) device does not respond to the [bloom](hololens1-basic-usage.md) gesture.</span></span> <span data-ttu-id="cd169-149">因為只有一個 app 可以執行，所以使用者無法放置其他應用程式。</span><span class="sxs-lookup"><span data-stu-id="cd169-149">Because only one app can run, the user cannot place other apps.</span></span>

<span data-ttu-id="cd169-150">多個應用程式站會在使用者登入裝置時顯示 [開始] 功能表。</span><span class="sxs-lookup"><span data-stu-id="cd169-150">A multi-app kiosk displays the Start menu when the user signs in to the device.</span></span> <span data-ttu-id="cd169-151">展臺設定會決定在 [開始] 功能表上可用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="cd169-151">The kiosk configuration determines which apps are available on the Start menu.</span></span> <span data-ttu-id="cd169-152">您可以使用多重應用程式亭，透過只向他們提供他們所需使用的專案，並移除不需要使用的專案，來為使用者提供易於理解的體驗。</span><span class="sxs-lookup"><span data-stu-id="cd169-152">You can use a multi-app kiosk to provide an easy-to-understand experience for users by presenting to them only the things that they have to use, and removing the things they don't need to use.</span></span>

<span data-ttu-id="cd169-153">下表列出不同資訊亭模式中的功能功能。</span><span class="sxs-lookup"><span data-stu-id="cd169-153">The following table lists the feature capabilities in the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="cd169-154">[開始] 功能表</span><span class="sxs-lookup"><span data-stu-id="cd169-154">Start menu</span></span> |<span data-ttu-id="cd169-155">[快速動作] 功能表</span><span class="sxs-lookup"><span data-stu-id="cd169-155">Quick Actions menu</span></span> |<span data-ttu-id="cd169-156">相機和影片</span><span class="sxs-lookup"><span data-stu-id="cd169-156">Camera and video</span></span> |<span data-ttu-id="cd169-157">Miracast</span><span class="sxs-lookup"><span data-stu-id="cd169-157">Miracast</span></span> |<span data-ttu-id="cd169-158">Cortana</span><span class="sxs-lookup"><span data-stu-id="cd169-158">Cortana</span></span> |<span data-ttu-id="cd169-159">內建語音命令</span><span class="sxs-lookup"><span data-stu-id="cd169-159">Built-in voice commands</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|<span data-ttu-id="cd169-160">單一應用程式資訊站</span><span class="sxs-lookup"><span data-stu-id="cd169-160">Single-app kiosk</span></span> |<span data-ttu-id="cd169-161">已停用</span><span class="sxs-lookup"><span data-stu-id="cd169-161">Disabled</span></span> |<span data-ttu-id="cd169-162">已停用</span><span class="sxs-lookup"><span data-stu-id="cd169-162">Disabled</span></span>   |<span data-ttu-id="cd169-163">已停用</span><span class="sxs-lookup"><span data-stu-id="cd169-163">Disabled</span></span> |<span data-ttu-id="cd169-164">已停用</span><span class="sxs-lookup"><span data-stu-id="cd169-164">Disabled</span></span>   |<span data-ttu-id="cd169-165">已停用</span><span class="sxs-lookup"><span data-stu-id="cd169-165">Disabled</span></span> |<span data-ttu-id="cd169-166">已啟用 <sup> 1</span><span class="sxs-lookup"><span data-stu-id="cd169-166">Enabled<sup>1</span></span></sup> |
|<span data-ttu-id="cd169-167">多個應用程式 Kiosk</span><span class="sxs-lookup"><span data-stu-id="cd169-167">Multi-app kiosk</span></span> |<span data-ttu-id="cd169-168">啟用</span><span class="sxs-lookup"><span data-stu-id="cd169-168">Enabled</span></span> |<span data-ttu-id="cd169-169">已啟用 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="cd169-169">Enabled<sup>2</span></span></sup> |<span data-ttu-id="cd169-170">可用 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="cd169-170">Available<sup>2</span></span></sup> |<span data-ttu-id="cd169-171">可用 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="cd169-171">Available<sup>2</span></span></sup> |<span data-ttu-id="cd169-172">可用 <sup> 2、3</span><span class="sxs-lookup"><span data-stu-id="cd169-172">Available<sup>2, 3</span></span></sup>  |<span data-ttu-id="cd169-173">已啟用 <sup> 1</span><span class="sxs-lookup"><span data-stu-id="cd169-173">Enabled<sup>1</span></span></sup> |

> <sup><span data-ttu-id="cd169-174">1與 </sup> 停用功能相關的語音命令無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="cd169-174">1</sup> Voice commands that relate to disabled features do not function.</span></span>  
> <sup><span data-ttu-id="cd169-175">2 </sup> 如需如何設定這些功能的詳細資訊，請參閱 [選取 kiosk app](#plan-kiosk-apps)。</span><span class="sxs-lookup"><span data-stu-id="cd169-175">2</sup> For more information about how to configure these features, see [Select kiosk apps](#plan-kiosk-apps).</span></span>  
> <sup><span data-ttu-id="cd169-176">3 </sup> 即使已停用 Cortana，仍會啟用內建語音命令。</span><span class="sxs-lookup"><span data-stu-id="cd169-176">3</sup> Even if Cortana is disabled, the built-in voice commands are enabled.</span></span>

<span data-ttu-id="cd169-177">下表列出不同 kiosk 模式的使用者支援功能。</span><span class="sxs-lookup"><span data-stu-id="cd169-177">The following table lists the user support features of the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="cd169-178">支援的使用者類型</span><span class="sxs-lookup"><span data-stu-id="cd169-178">Supported user types</span></span> | <span data-ttu-id="cd169-179">自動登入</span><span class="sxs-lookup"><span data-stu-id="cd169-179">Automatic sign-in</span></span> | <span data-ttu-id="cd169-180">多個存取層級</span><span class="sxs-lookup"><span data-stu-id="cd169-180">Multiple access levels</span></span> |
| --- | --- | --- | --- |
|<span data-ttu-id="cd169-181">單一應用程式資訊站</span><span class="sxs-lookup"><span data-stu-id="cd169-181">Single-app kiosk</span></span> |<span data-ttu-id="cd169-182">受管理的服務帳戶 (Azure Active Directory (AAD) 或本機帳戶中的 MSA) </span><span class="sxs-lookup"><span data-stu-id="cd169-182">Managed Service Account (MSA) in Azure Active Directory (AAD) or local account</span></span> |<span data-ttu-id="cd169-183">是</span><span class="sxs-lookup"><span data-stu-id="cd169-183">Yes</span></span> |<span data-ttu-id="cd169-184">否</span><span class="sxs-lookup"><span data-stu-id="cd169-184">No</span></span> |
|<span data-ttu-id="cd169-185">多個應用程式 Kiosk</span><span class="sxs-lookup"><span data-stu-id="cd169-185">Multi-app kiosk</span></span> |<span data-ttu-id="cd169-186">AAD 帳戶</span><span class="sxs-lookup"><span data-stu-id="cd169-186">AAD account</span></span> |<span data-ttu-id="cd169-187">否</span><span class="sxs-lookup"><span data-stu-id="cd169-187">No</span></span> |<span data-ttu-id="cd169-188">是</span><span class="sxs-lookup"><span data-stu-id="cd169-188">Yes</span></span> |

<span data-ttu-id="cd169-189">如需如何使用這些功能的範例，請參閱下表。</span><span class="sxs-lookup"><span data-stu-id="cd169-189">For examples of how to use these capabilities, see the following table.</span></span>

|<span data-ttu-id="cd169-190">使用單一應用程式亭進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="cd169-190">Use a single-app kiosk for:</span></span> |<span data-ttu-id="cd169-191">使用多應用程式亭進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="cd169-191">Use a multi-app kiosk for:</span></span> |
| --- | --- |
|<span data-ttu-id="cd169-192">一種裝置，只對新的員工執行 Dynamics 365 指南。</span><span class="sxs-lookup"><span data-stu-id="cd169-192">A device that runs only a Dynamics 365 Guide for new employees.</span></span> |<span data-ttu-id="cd169-193">為一系列員工執行輔助線和遠端協助的裝置。</span><span class="sxs-lookup"><span data-stu-id="cd169-193">A device that runs both Guides and Remote Assistance for a range of employees.</span></span> |
|<span data-ttu-id="cd169-194">只執行自訂應用程式的裝置。</span><span class="sxs-lookup"><span data-stu-id="cd169-194">A device that runs only a custom app.</span></span> |<span data-ttu-id="cd169-195">在 (只執行自訂應用程式) 的裝置，但作為特定使用者群組的標準裝置的功能。</span><span class="sxs-lookup"><span data-stu-id="cd169-195">A device that functions as a kiosk for most users (running only a custom app), but functions as a standard device for a specific group of users.</span></span> |

### <span data-ttu-id="cd169-196">規劃展臺應用程式</span><span class="sxs-lookup"><span data-stu-id="cd169-196">Plan kiosk apps</span></span>

<span data-ttu-id="cd169-197">如需如何選擇 kiosk app 的一般資訊，請參閱在 [ (kiosk 模式] 中選擇指派存取權的原則) ](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)。</span><span class="sxs-lookup"><span data-stu-id="cd169-197">For general information about how to choose kiosk apps, see [Guidelines for choosing an app for assigned access (kiosk mode)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app).</span></span>

<span data-ttu-id="cd169-198">如果您使用 Windows Device Portal 來設定單一應用程式亭，您可以在安裝程式期間選取 app。</span><span class="sxs-lookup"><span data-stu-id="cd169-198">If you use the Windows Device Portal to configure a single-app kiosk, you select the app during the setup process.</span></span>  

<span data-ttu-id="cd169-199">如果您使用行動裝置管理 (MDM) 系統或預配套件來設定 kiosk 模式，您可以使用 [AssignedAccess 配置服務提供者 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) 來指定應用程式。</span><span class="sxs-lookup"><span data-stu-id="cd169-199">If you use a Mobile Device Management (MDM) system or a provisioning package to configure kiosk mode, you use the [AssignedAccess Configuration Service Provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) to specify applications.</span></span> <span data-ttu-id="cd169-200">CSP 會使用 [應用程式使用者模型識別碼 (aumid) ](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 來識別應用程式。</span><span class="sxs-lookup"><span data-stu-id="cd169-200">The CSP uses [Application User Model IDs (AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) to identify applications.</span></span> <span data-ttu-id="cd169-201">下表列出一些您可以在多應用程式亭中使用的 Aumid 應用程式。</span><span class="sxs-lookup"><span data-stu-id="cd169-201">The following table lists the AUMIDs of some in-box applications that you can use in a multi-app kiosk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd169-202">Kiosk 模式決定使用者登入裝置時可使用哪些 app。</span><span class="sxs-lookup"><span data-stu-id="cd169-202">Kiosk mode determines which apps are available when a user signs in to the device.</span></span> <span data-ttu-id="cd169-203">不過，kiosk 模式不是安全性方法。</span><span class="sxs-lookup"><span data-stu-id="cd169-203">However, kiosk mode is not a security method.</span></span> <span data-ttu-id="cd169-204">它不會停止「允許」 app，無法開啟其他不允許的應用程式。</span><span class="sxs-lookup"><span data-stu-id="cd169-204">It does not stop an "allowed" app from opening another app that is not allowed.</span></span> <span data-ttu-id="cd169-205">因為我們不限制此行為，所以仍可從 Edge、檔案資源管理器以及 Microsoft Store 應用程式啟動 app。</span><span class="sxs-lookup"><span data-stu-id="cd169-205">Because we do not restrict this behavior, apps can still be launched from Edge, File explorer, and the Microsoft Store apps.</span></span> <span data-ttu-id="cd169-206">如果您不想從展臺啟動特定的 app，請使用 [Windows Defender 應用程式控制項 (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) 來建立適當的原則。</span><span class="sxs-lookup"><span data-stu-id="cd169-206">If there are specific apps you don't want launched from a Kiosk, use [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) to create appropriate policies.</span></span> 
> 
> <span data-ttu-id="cd169-207">此外，混合式現實家用版無法設定為 kiosk app。</span><span class="sxs-lookup"><span data-stu-id="cd169-207">In addition, the Mixed Reality Home is not able to be set as a kiosk app.</span></span>

<a id="aumids"></a>

|<span data-ttu-id="cd169-208">應用程式名稱</span><span class="sxs-lookup"><span data-stu-id="cd169-208">App Name</span></span> |<span data-ttu-id="cd169-209">AUMID</span><span class="sxs-lookup"><span data-stu-id="cd169-209">AUMID</span></span> |
| --- | --- |
|<span data-ttu-id="cd169-210">3D 檢視器</span><span class="sxs-lookup"><span data-stu-id="cd169-210">3D Viewer</span></span> |<span data-ttu-id="cd169-211">Microsoft3DViewer _8wekyb3d8bbwe \！Microsoft3DViewer</span><span class="sxs-lookup"><span data-stu-id="cd169-211">Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\!Microsoft.Microsoft3DViewer</span></span> |
|<span data-ttu-id="cd169-212">行事曆</span><span class="sxs-lookup"><span data-stu-id="cd169-212">Calendar</span></span> |<span data-ttu-id="cd169-213">windowscommunicationsapps \ _8wekyb3d8bbwe \！ windowslive。</span><span class="sxs-lookup"><span data-stu-id="cd169-213">microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\!microsoft.windowslive.calendar</span></span> |
|<span data-ttu-id="cd169-214">相機 <sup> 1、2</span><span class="sxs-lookup"><span data-stu-id="cd169-214">Camera<sup>1, 2</span></span></sup> |<span data-ttu-id="cd169-215">HoloCamera \ _cw5n1h2txyewy \！HoloCamera</span><span class="sxs-lookup"><span data-stu-id="cd169-215">HoloCamera\_cw5n1h2txyewy\!HoloCamera</span></span> |
|<span data-ttu-id="cd169-216">Cortana <sup> 3</span><span class="sxs-lookup"><span data-stu-id="cd169-216">Cortana<sup>3</span></span></sup> |<span data-ttu-id="cd169-217">549981C3F5F10 _8wekyb3d8bbwe \！適用</span><span class="sxs-lookup"><span data-stu-id="cd169-217">Microsoft.549981C3F5F10\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="cd169-218">HoloLens 上的 Device 拾器 (1 gen) </span><span class="sxs-lookup"><span data-stu-id="cd169-218">Device Picker on HoloLens (1st gen)</span></span> |<span data-ttu-id="cd169-219">HoloDevicesFlow \ _cw5n1h2txyewy \！HoloDevicesFlow</span><span class="sxs-lookup"><span data-stu-id="cd169-219">HoloDevicesFlow\_cw5n1h2txyewy\!HoloDevicesFlow</span></span> |
|<span data-ttu-id="cd169-220">HoloLens 2 上的裝置選擇器</span><span class="sxs-lookup"><span data-stu-id="cd169-220">Device Picker on HoloLens 2</span></span> |<span data-ttu-id="cd169-221">DevicesFlowHost \ _cw5n1h2txyewy \！DevicesFlowHost</span><span class="sxs-lookup"><span data-stu-id="cd169-221">Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\!Microsoft.Windows.DevicesFlowHost</span></span> |
|<span data-ttu-id="cd169-222">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="cd169-222">Dynamics 365 Guides</span></span> |<span data-ttu-id="cd169-223">Dynamics365 _8wekyb3d8bbwe \！MicrosoftGuides</span><span class="sxs-lookup"><span data-stu-id="cd169-223">Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\!MicrosoftGuides</span></span> |
|<span data-ttu-id="cd169-224">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="cd169-224">Dynamics 365 Remote Assist</span></span> |<span data-ttu-id="cd169-225">MicrosoftRemoteAssist _8wekyb3d8bbwe \！RemoteAssist</span><span class="sxs-lookup"><span data-stu-id="cd169-225">Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\!Microsoft.RemoteAssist</span></span> |
|<span data-ttu-id="cd169-226">意見反應 &nbsp; 中樞</span><span class="sxs-lookup"><span data-stu-id="cd169-226">Feedback&nbsp;Hub</span></span> |<span data-ttu-id="cd169-227">WindowsFeedbackHub _8wekyb3d8bbwe \！適用</span><span class="sxs-lookup"><span data-stu-id="cd169-227">Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="cd169-228">檔案總管</span><span class="sxs-lookup"><span data-stu-id="cd169-228">File Explorer</span></span> |<span data-ttu-id="cd169-229">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span><span class="sxs-lookup"><span data-stu-id="cd169-229">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span></span> |
|<span data-ttu-id="cd169-230">Mail</span><span class="sxs-lookup"><span data-stu-id="cd169-230">Mail</span></span> |<span data-ttu-id="cd169-231">microsoft.windowscommunicationsapps_8wekyb3d8bbwe！ windowslive</span><span class="sxs-lookup"><span data-stu-id="cd169-231">microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail</span></span> |
|<span data-ttu-id="cd169-232">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="cd169-232">Microsoft Store</span></span> |<span data-ttu-id="cd169-233">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span><span class="sxs-lookup"><span data-stu-id="cd169-233">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span></span> |
|<span data-ttu-id="cd169-234">Miracast <sup> 4</span><span class="sxs-lookup"><span data-stu-id="cd169-234">Miracast<sup>4</span></span></sup> |&nbsp; |
|<span data-ttu-id="cd169-235">電影與電視</span><span class="sxs-lookup"><span data-stu-id="cd169-235">Movies & TV</span></span> |<span data-ttu-id="cd169-236">ZuneVideo _8wekyb3d8bbwe \！ZuneVideo</span><span class="sxs-lookup"><span data-stu-id="cd169-236">Microsoft.ZuneVideo\_8wekyb3d8bbwe\!Microsoft.ZuneVideo</span></span> |
|<span data-ttu-id="cd169-237">OneDrive</span><span class="sxs-lookup"><span data-stu-id="cd169-237">OneDrive</span></span> |<span data-ttu-id="cd169-238">microsoftskydrive _8wekyb3d8bbwe \！適用</span><span class="sxs-lookup"><span data-stu-id="cd169-238">microsoft.microsoftskydrive\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="cd169-239">相片</span><span class="sxs-lookup"><span data-stu-id="cd169-239">Photos</span></span> |<span data-ttu-id="cd169-240">您的 _8wekyb3d8bbwe \！適用</span><span class="sxs-lookup"><span data-stu-id="cd169-240">Microsoft.Windows.Photos\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="cd169-241">設定</span><span class="sxs-lookup"><span data-stu-id="cd169-241">Settings</span></span> |<span data-ttu-id="cd169-242">HolographicSystemSettings \ _cw5n1h2txyewy \！適用</span><span class="sxs-lookup"><span data-stu-id="cd169-242">HolographicSystemSettings\_cw5n1h2txyewy\!App</span></span> |
|<span data-ttu-id="cd169-243">提示</span><span class="sxs-lookup"><span data-stu-id="cd169-243">Tips</span></span> |<span data-ttu-id="cd169-244">HoloLensTips _8wekyb3d8bbwe \！HoloLensTips</span><span class="sxs-lookup"><span data-stu-id="cd169-244">Microsoft.HoloLensTips\_8wekyb3d8bbwe\!HoloLensTips</span></span> |

> <sup><span data-ttu-id="cd169-245">1 </sup> 若要啟用相片或影片捕獲，您必須啟用攝影機 app 作為 kiosk app。</span><span class="sxs-lookup"><span data-stu-id="cd169-245">1</sup> To enable photo or video capture, you have to enable the Camera app as a kiosk app.</span></span>  
> <sup><span data-ttu-id="cd169-246">2 </sup> 當您啟用攝像頭 app 時，請注意下列情況：</span><span class="sxs-lookup"><span data-stu-id="cd169-246">2</sup> When you enable the Camera app, be aware of the following conditions:</span></span>
> - <span data-ttu-id="cd169-247">[快速動作] 功能表包括 [相片] 和 [影片] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="cd169-247">The Quick Actions menu includes the Photo and Video buttons.</span></span>  
> - <span data-ttu-id="cd169-248">您也應該啟用可與圖片互動或取得圖片的 app (例如相片、郵件或 OneDrive) 。</span><span class="sxs-lookup"><span data-stu-id="cd169-248">You should also enable an app (such as Photos, Mail, or OneDrive) that can interact with or retrieve pictures.</span></span>  
>  
> <sup><span data-ttu-id="cd169-249">3 </sup> 即使您未啟用 Cortana 作為 kiosk app，也會啟用內建語音命令。</span><span class="sxs-lookup"><span data-stu-id="cd169-249">3</sup> Even if you do not enable Cortana as a kiosk app, built-in voice commands are enabled.</span></span> <span data-ttu-id="cd169-250">不過，與停用功能相關的命令不會產生任何效果。</span><span class="sxs-lookup"><span data-stu-id="cd169-250">However, commands that are related to disabled features have no effect.</span></span>  
> <sup><span data-ttu-id="cd169-251">4 </sup> 您無法直接啟用 Miracast。</span><span class="sxs-lookup"><span data-stu-id="cd169-251">4</sup> You cannot enable Miracast directly.</span></span> <span data-ttu-id="cd169-252">若要啟用 Miracast 作為 kiosk app，請啟用相機 app 和裝置選擇器應用程式。</span><span class="sxs-lookup"><span data-stu-id="cd169-252">To enable Miracast as a kiosk app enable the Camera app and the Device Picker app.</span></span>

### <span data-ttu-id="cd169-253">為使用者或群組規劃 kiosk 設定檔</span><span class="sxs-lookup"><span data-stu-id="cd169-253">Plan kiosk profiles for users or groups</span></span>

<span data-ttu-id="cd169-254">當您建立 xml 檔案，或使用 Intune 的 UI 來設定展臺時，您必須考慮誰將是該資訊站的使用者。</span><span class="sxs-lookup"><span data-stu-id="cd169-254">When either creating the xml file or using Intune’s UI to set up a Kiosk you’ll need to consider who will be user the Kiosk.</span></span> <span data-ttu-id="cd169-255">展臺配置可以限制為個別帳戶或 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="cd169-255">A Kiosk configuration can be limited to either an individual account or Azure AD groups.</span></span> 

<span data-ttu-id="cd169-256">通常會為使用者或使用者群組啟用展臺。</span><span class="sxs-lookup"><span data-stu-id="cd169-256">Typically Kiosks are enabled for either a user, or user group.</span></span> <span data-ttu-id="cd169-257">不過，如果您打算撰寫自己的 XML 資訊亭，您可能會想要考慮全域指派的存取權，而不論身分識別，都能在裝置層級套用展臺。</span><span class="sxs-lookup"><span data-stu-id="cd169-257">However if you plan on writing your own XML Kiosk, then you may want to consider Global Assigned Access, in which the Kiosk is applied at the device level regardless of Identity.</span></span> <span data-ttu-id="cd169-258">如果您想瞭解 [有關全域指派的 Access 網亭的詳細資訊，請參閱。](hololens-global-assigned-access-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="cd169-258">If this appeals to you [read more about Global Assigned Access Kiosks.](hololens-global-assigned-access-kiosk.md)</span></span>

#### <span data-ttu-id="cd169-259">如果您要建立 XML 檔案：</span><span class="sxs-lookup"><span data-stu-id="cd169-259">If you are creating an XML file:</span></span>
-   <span data-ttu-id="cd169-260">您有許多 [建立多個展臺設定檔]，並指派給不同的使用者/群組。</span><span class="sxs-lookup"><span data-stu-id="cd169-260">You many create multiple Kiosk profiles, and assign each to different users/groups.</span></span> <span data-ttu-id="cd169-261">例如，有許多應用程式的 AAD 群組的 Kiosk，以及具有多個 app 展臺的訪客（具有單一 app）。</span><span class="sxs-lookup"><span data-stu-id="cd169-261">Such as a Kiosk for your AAD Group that has many apps, and a Visitor that has a multiple app kiosk with a singular app.</span></span>
-   <span data-ttu-id="cd169-262">您的 kiosk 配置將稱為 **設定檔識別碼** ，且具有 GUID。</span><span class="sxs-lookup"><span data-stu-id="cd169-262">Your kiosk configuration will be called a **Profile Id** and have a GUID.</span></span>
-   <span data-ttu-id="cd169-263">您將會在 [配置] 區段中指派該設定檔，方法是指定使用者類型並對 **DefaultProfile 識別碼**使用相同的 GUID。</span><span class="sxs-lookup"><span data-stu-id="cd169-263">You will assign that Profile in the configs section by specifying the user type and using the same GUID for the **DefaultProfile Id**.</span></span>
- <span data-ttu-id="cd169-264">您可以建立自訂的 OMA URI 裝置設定檔，並將其套用至 HoloLens 裝置群組（使用 URI 值：/Device/Vendor/MSFT/AssignedAccess/Configuration），以建立 XML 檔案，但仍透過 MDM 將它套用到裝置</span><span class="sxs-lookup"><span data-stu-id="cd169-264">A XML file can be created but still applied to a device via MDM by creating a custom OMA URI device configuration profile and applying it to HoloLens device group using the URI value: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>

#### <span data-ttu-id="cd169-265">如果您是在 Intune 中建立展臺。</span><span class="sxs-lookup"><span data-stu-id="cd169-265">If you are creating a Kiosk in Intune.</span></span>
-   <span data-ttu-id="cd169-266">每個裝置可能只會收到單一展臺設定檔，否則會產生衝突，並根本不接收任何展臺設定。</span><span class="sxs-lookup"><span data-stu-id="cd169-266">Each device may only receive a single Kiosk profile, otherwise it will create a conflict and receive no Kiosk configurations at all.</span></span> 
    -   <span data-ttu-id="cd169-267">其他類型的設定檔與原則，例如與 kiosk 配置設定檔無關的裝置限制，請勿與 kiosk 設定設定檔發生衝突。</span><span class="sxs-lookup"><span data-stu-id="cd169-267">Other kinds of profiles and policies, such as device restrictions that are not related to the kiosk configuration profile, do not conflict with the kiosk configuration profile.</span></span>
-   <span data-ttu-id="cd169-268">系統會針對屬於使用者登入類型的所有使用者啟用 Kiosk，這將會與使用者或 AAD 群組設定。</span><span class="sxs-lookup"><span data-stu-id="cd169-268">The Kiosk will be enabled for all users who are a part of the User logon type, this will be set with a user or AAD group.</span></span> 
-   <span data-ttu-id="cd169-269">設定 Kiosk 設定之後， **使用者登入類型** (可以登入 Kiosk 的使用者) 且已選取這些應用程式，則仍必須將裝置設定指派給群組。</span><span class="sxs-lookup"><span data-stu-id="cd169-269">After the Kiosk configuration is set and the **User logon type** (users who can log into the Kiosk) and the Apps are selected, the Device Configuration must still be assigned to a group.</span></span> <span data-ttu-id="cd169-270">指派的群組 (s) 決定哪些裝置會收到 Kiosk 裝置設定，但在啟用資訊亭時不會與之互動。</span><span class="sxs-lookup"><span data-stu-id="cd169-270">The Assigned group(s) determines which devices receive the Kiosk device configuration, however does not interact with if the Kiosk is enabled or not.</span></span> 
    - <span data-ttu-id="cd169-271">如需在 Intune 中指派設定檔的效果的完整討論，請參閱 [在 Microsoft Intune 中指派使用者和裝置設定檔](https://docs.microsoft.com/intune/configuration/device-profile-assign)。</span><span class="sxs-lookup"><span data-stu-id="cd169-271">For a full discussion of the effects of assigning configuration profiles in Intune, see [Assign user and device profiles in Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).</span></span>

### <span data-ttu-id="cd169-272">選取部署方法</span><span class="sxs-lookup"><span data-stu-id="cd169-272">Select a deployment method</span></span>

<span data-ttu-id="cd169-273">您可以選取下列其中一種方法來部署展臺配置：</span><span class="sxs-lookup"><span data-stu-id="cd169-273">You can select one of the following methods to deploy kiosk configurations:</span></span>

- [<span data-ttu-id="cd169-274"> (MDM) 服務的 Microsoft Intune 或其他行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="cd169-274">Microsoft Intune or other mobile device management (MDM) service</span></span>](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="cd169-275">佈建套件</span><span class="sxs-lookup"><span data-stu-id="cd169-275">Provisioning package</span></span>](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="cd169-276">Windows Device Portal</span><span class="sxs-lookup"><span data-stu-id="cd169-276">Windows Device Portal</span></span>](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > <span data-ttu-id="cd169-277">由於這個方法需要在裝置上啟用開發人員模式，因此我們建議您僅將它用於示範。</span><span class="sxs-lookup"><span data-stu-id="cd169-277">Because this method requires that Developer Mode be enabled on the device, we recommend that you use it only for demonstrations.</span></span>

<span data-ttu-id="cd169-278">下表列出每個部署方法的功能和優點。</span><span class="sxs-lookup"><span data-stu-id="cd169-278">The following table lists the capabilities and benefits of each of the deployment methods.</span></span>

| &nbsp; |<span data-ttu-id="cd169-279">使用 Windows Device Portal 進行部署</span><span class="sxs-lookup"><span data-stu-id="cd169-279">Deploy by using Windows Device Portal</span></span> |<span data-ttu-id="cd169-280">使用預配套件進行部署</span><span class="sxs-lookup"><span data-stu-id="cd169-280">Deploy by using a provisioning package</span></span> |<span data-ttu-id="cd169-281">使用 MDM 部署</span><span class="sxs-lookup"><span data-stu-id="cd169-281">Deploy by using MDM</span></span> |
| --------------------------- | ------------- | -------------------- | ---- |
|<span data-ttu-id="cd169-282">部署單一 app 網亭</span><span class="sxs-lookup"><span data-stu-id="cd169-282">Deploy single-app kiosks</span></span>   | <span data-ttu-id="cd169-283">是</span><span class="sxs-lookup"><span data-stu-id="cd169-283">Yes</span></span>           | <span data-ttu-id="cd169-284">是</span><span class="sxs-lookup"><span data-stu-id="cd169-284">Yes</span></span>                  | <span data-ttu-id="cd169-285">是</span><span class="sxs-lookup"><span data-stu-id="cd169-285">Yes</span></span>  |
|<span data-ttu-id="cd169-286">部署多應用程式亭</span><span class="sxs-lookup"><span data-stu-id="cd169-286">Deploy multi-app kiosks</span></span>    | <span data-ttu-id="cd169-287">否</span><span class="sxs-lookup"><span data-stu-id="cd169-287">No</span></span>            | <span data-ttu-id="cd169-288">是</span><span class="sxs-lookup"><span data-stu-id="cd169-288">Yes</span></span>                  | <span data-ttu-id="cd169-289">是</span><span class="sxs-lookup"><span data-stu-id="cd169-289">Yes</span></span>  |
|<span data-ttu-id="cd169-290">僅部署到本機裝置</span><span class="sxs-lookup"><span data-stu-id="cd169-290">Deploy to local devices only</span></span> | <span data-ttu-id="cd169-291">是</span><span class="sxs-lookup"><span data-stu-id="cd169-291">Yes</span></span>           | <span data-ttu-id="cd169-292">是</span><span class="sxs-lookup"><span data-stu-id="cd169-292">Yes</span></span>                  | <span data-ttu-id="cd169-293">否</span><span class="sxs-lookup"><span data-stu-id="cd169-293">No</span></span>   |
|<span data-ttu-id="cd169-294">使用開發人員模式進行部署</span><span class="sxs-lookup"><span data-stu-id="cd169-294">Deploy by using Developer Mode</span></span> |<span data-ttu-id="cd169-295">必要</span><span class="sxs-lookup"><span data-stu-id="cd169-295">Required</span></span>       | <span data-ttu-id="cd169-296">不需要</span><span class="sxs-lookup"><span data-stu-id="cd169-296">Not required</span></span>            | <span data-ttu-id="cd169-297">不需要</span><span class="sxs-lookup"><span data-stu-id="cd169-297">Not required</span></span>   |
|<span data-ttu-id="cd169-298">使用 Azure Active Directory (AAD) 進行部署</span><span class="sxs-lookup"><span data-stu-id="cd169-298">Deploy by using Azure Active Directory (AAD)</span></span>  | <span data-ttu-id="cd169-299">不需要</span><span class="sxs-lookup"><span data-stu-id="cd169-299">Not required</span></span>            | <span data-ttu-id="cd169-300">不需要</span><span class="sxs-lookup"><span data-stu-id="cd169-300">Not required</span></span>                   | <span data-ttu-id="cd169-301">必要</span><span class="sxs-lookup"><span data-stu-id="cd169-301">Required</span></span>  |
|<span data-ttu-id="cd169-302">自動部署</span><span class="sxs-lookup"><span data-stu-id="cd169-302">Deploy automatically</span></span>      | <span data-ttu-id="cd169-303">否</span><span class="sxs-lookup"><span data-stu-id="cd169-303">No</span></span>            | <span data-ttu-id="cd169-304">否</span><span class="sxs-lookup"><span data-stu-id="cd169-304">No</span></span>                   | <span data-ttu-id="cd169-305">是</span><span class="sxs-lookup"><span data-stu-id="cd169-305">Yes</span></span>  |
|<span data-ttu-id="cd169-306">部署速度</span><span class="sxs-lookup"><span data-stu-id="cd169-306">Deployment speed</span></span>            | <span data-ttu-id="cd169-307">快速</span><span class="sxs-lookup"><span data-stu-id="cd169-307">Fast</span></span>       | <span data-ttu-id="cd169-308">快速</span><span class="sxs-lookup"><span data-stu-id="cd169-308">Fast</span></span>                 | <span data-ttu-id="cd169-309">慢速</span><span class="sxs-lookup"><span data-stu-id="cd169-309">Slow</span></span> |
|<span data-ttu-id="cd169-310">在縮放時部署</span><span class="sxs-lookup"><span data-stu-id="cd169-310">Deploy at scale</span></span> | <span data-ttu-id="cd169-311">不建議使用</span><span class="sxs-lookup"><span data-stu-id="cd169-311">Not recommended</span></span>    | <span data-ttu-id="cd169-312">建議執行</span><span class="sxs-lookup"><span data-stu-id="cd169-312">Recommended</span></span>        | <span data-ttu-id="cd169-313">建議執行</span><span class="sxs-lookup"><span data-stu-id="cd169-313">Recommended</span></span> |

## <span data-ttu-id="cd169-314">使用 Microsoft Intune 或其他 MDM 設定單一 app 或多重應用程式亭</span><span class="sxs-lookup"><span data-stu-id="cd169-314">Use Microsoft Intune or other MDM to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="cd169-315">若要使用 Microsoft Intune 或其他 MDM 系統來設定 kiosk 模式，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="cd169-315">To set up kiosk mode by using Microsoft Intune or another MDM system, follow these steps.</span></span>

1. <span data-ttu-id="cd169-316">[準備註冊裝置](#mdmenroll)。</span><span class="sxs-lookup"><span data-stu-id="cd169-316">[Prepare to enroll the devices](#mdmenroll).</span></span>
1. <span data-ttu-id="cd169-317">[建立展臺設定檔](#mdmprofile)。</span><span class="sxs-lookup"><span data-stu-id="cd169-317">[Create a kiosk configuration profile](#mdmprofile).</span></span>
1. <span data-ttu-id="cd169-318">設定 kiosk。</span><span class="sxs-lookup"><span data-stu-id="cd169-318">Configure the kiosk.</span></span>
   - <span data-ttu-id="cd169-319">[設定單一 app 展臺的設定](#mdmconfigsingle)。</span><span class="sxs-lookup"><span data-stu-id="cd169-319">[Configure the settings for a single-app kiosk](#mdmconfigsingle).</span></span>
   - <span data-ttu-id="cd169-320">[設定多應用程式資訊站的設定](#mdmconfigmulti)。</span><span class="sxs-lookup"><span data-stu-id="cd169-320">[Configure the settings for a multi-app kiosk](#mdmconfigmulti).</span></span>
1. <span data-ttu-id="cd169-321">[將 kiosk 配置設定檔指派給群組](#mdmassign)。</span><span class="sxs-lookup"><span data-stu-id="cd169-321">[Assign the kiosk configuration profile to a group](#mdmassign).</span></span>
1. <span data-ttu-id="cd169-322">部署裝置。</span><span class="sxs-lookup"><span data-stu-id="cd169-322">Deploy the devices.</span></span>
   - <span data-ttu-id="cd169-323">[部署單一應用程式亭](#mdmsingledeploy)。</span><span class="sxs-lookup"><span data-stu-id="cd169-323">[Deploy a single-app kiosk](#mdmsingledeploy).</span></span>
   - <span data-ttu-id="cd169-324">[部署多應用程式亭](#mdmmultideploy)。</span><span class="sxs-lookup"><span data-stu-id="cd169-324">[Deploy a multi-app kiosk](#mdmmultideploy).</span></span>

### <a id="mdmenroll"></a><span data-ttu-id="cd169-325">MDM，步驟 1 &ndash; 準備註冊裝置</span><span class="sxs-lookup"><span data-stu-id="cd169-325">MDM, step 1 &ndash; Prepare to enroll the devices</span></span>

<span data-ttu-id="cd169-326">您可以設定您的 MDM 系統在使用者第一次登入時自動登記 HoloLens 裝置，或讓使用者手動註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="cd169-326">You can configure your MDM system to enroll HoloLens devices automatically when the user first signs in, or have users enroll devices manually.</span></span> <span data-ttu-id="cd169-327">裝置也必須加入到 Azure AD 網域，並指派給適當的群組。</span><span class="sxs-lookup"><span data-stu-id="cd169-327">The devices also have to be joined to your Azure AD domain, and assigned to the appropriate groups.</span></span>

<span data-ttu-id="cd169-328">如需有關如何註冊裝置的詳細資訊，請參閱在[Windows 裝置的 MDM 和 Intune 註冊方法](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)[中註冊 HoloLens](hololens-enroll-mdm.md) 。</span><span class="sxs-lookup"><span data-stu-id="cd169-328">For more information about how to enroll the devices, see [Enroll HoloLens in MDM](hololens-enroll-mdm.md) and [Intune enrollment methods for Windows devices](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods).</span></span>

### <a id="mdmprofile"></a><span data-ttu-id="cd169-329">MDM，步驟 2 &ndash; 建立 kiosk 配置設定檔</span><span class="sxs-lookup"><span data-stu-id="cd169-329">MDM, step 2 &ndash; Create a kiosk configuration profile</span></span>

1. <span data-ttu-id="cd169-330">開啟 [Azure](https://portal.azure.com/) 入口網站，並登入您的 Intune 系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="cd169-330">Open the [Azure](https://portal.azure.com/) portal and sign in to your Intune administrator account.</span></span>
1. <span data-ttu-id="cd169-331">選取 [ **Microsoft Intune**裝置設定]-[設定檔]  >  **Device configuration - Profiles**  >  **建立設定檔**。</span><span class="sxs-lookup"><span data-stu-id="cd169-331">Select **Microsoft Intune** > **Device configuration - Profiles** > **Create profile**.</span></span>
1. <span data-ttu-id="cd169-332">輸入設定檔名稱。</span><span class="sxs-lookup"><span data-stu-id="cd169-332">Enter a profile name.</span></span>
1. <span data-ttu-id="cd169-333">選取 [**平臺**  >  **Windows 10 及更新版本**]，然後選取 [**配置檔案類型**  > **裝置限制**]。</span><span class="sxs-lookup"><span data-stu-id="cd169-333">Select **Platform** > **Windows 10 and later**, and then select **Profile type** >**Device restrictions**.</span></span>
1. <span data-ttu-id="cd169-334">選取 [**設定**  >  **Kiosk**]，然後選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="cd169-334">Select **Configure** > **Kiosk**, and then select one of the following:</span></span>
   - <span data-ttu-id="cd169-335">若要建立單一應用程式亭，請選取 [**展臺模式**  >  **單一應用程式亭**]。</span><span class="sxs-lookup"><span data-stu-id="cd169-335">To create a single-app kiosk, select **Kiosk Mode** > **Single-app kiosk**.</span></span>
   - <span data-ttu-id="cd169-336">若要建立多重應用程式亭，請選取 [**展臺模式**  >  **多重應用程式資訊站**]。</span><span class="sxs-lookup"><span data-stu-id="cd169-336">To create a multi-app kiosk, select **Kiosk Mode** > **Multi-app kiosk**.</span></span>
1. <span data-ttu-id="cd169-337">若要開始配置資訊亭，請選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="cd169-337">To start configuring the kiosk, select **Add**.</span></span>

<span data-ttu-id="cd169-338">根據您想要的展臺類型，後續步驟會有所不同。</span><span class="sxs-lookup"><span data-stu-id="cd169-338">Your next steps differ depending on the type of kiosk that you want.</span></span> <span data-ttu-id="cd169-339">如需詳細資訊，請選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="cd169-339">For more information, select one of the following options:</span></span>  

- [<span data-ttu-id="cd169-340">單一應用程式資訊站</span><span class="sxs-lookup"><span data-stu-id="cd169-340">Single-app kiosk</span></span>](#mdmconfigsingle)
- [<span data-ttu-id="cd169-341">多個應用程式 Kiosk</span><span class="sxs-lookup"><span data-stu-id="cd169-341">Multi-app kiosk</span></span>](#mdmconfigmulti)

<span data-ttu-id="cd169-342">如需如何建立 kiosk 配置設定檔的詳細資訊，請參閱 [windows 10 和 Windows 全息企業版裝置設定，以使用 Intune 作為專用的展臺執行](https://docs.microsoft.com/intune/configuration/kiosk-settings)。</span><span class="sxs-lookup"><span data-stu-id="cd169-342">For more information about how to create a kiosk configuration profile, see [Windows 10 and Windows Holographic for Business device settings to run as a dedicated kiosk using Intune](https://docs.microsoft.com/intune/configuration/kiosk-settings).</span></span>

### <a id="mdmconfigsingle"></a><span data-ttu-id="cd169-343">MDM、步驟 3 (單 app) &ndash;  設定單一 app 展臺的設定</span><span class="sxs-lookup"><span data-stu-id="cd169-343">MDM, step 3 (single-app) &ndash;  Configure the settings for a single-app kiosk</span></span>

<span data-ttu-id="cd169-344">本節摘要說明單一 app 展臺所需的設定。</span><span class="sxs-lookup"><span data-stu-id="cd169-344">This section summarizes the settings that a single-app kiosk requires.</span></span> <span data-ttu-id="cd169-345">如需詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="cd169-345">For more details, see the following articles:</span></span>

- <span data-ttu-id="cd169-346">如需如何在 Intune 中設定 kiosk 設定檔的相關資訊，請參閱 [如何使用 Microsoft Intune 設定 Kiosk 模式](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="cd169-346">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="cd169-347">如需 Intune 中單一 app 亭可用設定的詳細資訊，請參閱 [單一全螢幕 app 網亭](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)</span><span class="sxs-lookup"><span data-stu-id="cd169-347">For more information about the available settings for single-app kiosks in Intune, see [Single full-screen app kiosks](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)</span></span>
- <span data-ttu-id="cd169-348">如需其他 MDM 服務，請參閱提供者文件中的指示。</span><span class="sxs-lookup"><span data-stu-id="cd169-348">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="cd169-349">如果您必須在 MDM 服務中使用自訂 XML 配置來設定展臺，請 [建立定義 kiosk 配置的 XML](#ppkioskconfig)檔案。</span><span class="sxs-lookup"><span data-stu-id="cd169-349">If you have to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span>

1. <span data-ttu-id="cd169-350">選取 [**使用者登**  >  入類型（**本機使用者帳戶**）]，然後輸入本機 (裝置) 帳戶或 Microsoft 帳戶的使用者名稱，即可登入資訊站 (MSA) 。</span><span class="sxs-lookup"><span data-stu-id="cd169-350">Select **User logon type** > **Local user account**, and then enter the user name of the local (device) account or Microsoft Account (MSA) that can sign in to the kiosk.</span></span>
   > [!NOTE]  
   > <span data-ttu-id="cd169-351">Windows 全息企業版不支援**自動登入**使用者帳戶類型。</span><span class="sxs-lookup"><span data-stu-id="cd169-351">**Autologon** user account types aren't supported on Windows Holographic for Business.</span></span>
1. <span data-ttu-id="cd169-352">選取 [**應用程式類型**  >  **存儲應用**程式]，然後從清單中選取一個應用程式。</span><span class="sxs-lookup"><span data-stu-id="cd169-352">Select **Application type** > **Store app**, and then select an app from the list.</span></span>

<span data-ttu-id="cd169-353">下一步是將設定檔 [指派](#mdmassign) 給群組。</span><span class="sxs-lookup"><span data-stu-id="cd169-353">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a id="mdmconfigmulti"></a><span data-ttu-id="cd169-354">MDM、步驟 3 (多重 app) &ndash; 設定多應用程式資訊站的設定</span><span class="sxs-lookup"><span data-stu-id="cd169-354">MDM, step 3 (multi-app) &ndash; Configure the settings for a multi-app kiosk</span></span>

<span data-ttu-id="cd169-355">本節摘要說明多應用程式亭所需的設定。</span><span class="sxs-lookup"><span data-stu-id="cd169-355">This section summarizes the settings that a multi-app kiosk requires.</span></span> <span data-ttu-id="cd169-356">如需詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="cd169-356">For more detailed information, see the following articles:</span></span>

- <span data-ttu-id="cd169-357">如需如何在 Intune 中設定 kiosk 設定檔的相關資訊，請參閱 [如何使用 Microsoft Intune 設定 Kiosk 模式](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="cd169-357">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="cd169-358">如需 Intune 中多個 app 網亭可用設定的詳細資訊，請參閱 [多重 app 網亭](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)</span><span class="sxs-lookup"><span data-stu-id="cd169-358">For more information about the available settings for multi-app kiosks in Intune, see [Multi-app kiosks](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)</span></span>
- <span data-ttu-id="cd169-359">如需其他 MDM 服務，請參閱提供者文件中的指示。</span><span class="sxs-lookup"><span data-stu-id="cd169-359">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="cd169-360">如果您需要在 MDM 服務中使用自訂 XML 設定來設定展臺，請 [建立定義 kiosk 配置的 XML](#ppkioskconfig)檔案。</span><span class="sxs-lookup"><span data-stu-id="cd169-360">If you need to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span> <span data-ttu-id="cd169-361">如果您使用 XML 檔案，請務必包含 [「開始」版面](#start-layout-for-hololens)配置。</span><span class="sxs-lookup"><span data-stu-id="cd169-361">If you use an XML file, make sure to include the [Start layout](#start-layout-for-hololens).</span></span>  
- <span data-ttu-id="cd169-362">您也可以選擇在 Intune 或其他 MDM 服務中使用自訂開始配置。</span><span class="sxs-lookup"><span data-stu-id="cd169-362">You can optionally use a custom Start layout with Intune or other MDM services.</span></span> <span data-ttu-id="cd169-363">如需詳細資訊，請參閱 [ (Intune 的 [啟動版面配置檔案] 和其他) ](#start-layout-file-for-mdm-intune-and-others)。</span><span class="sxs-lookup"><span data-stu-id="cd169-363">For more information, see [Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

1. <span data-ttu-id="cd169-364">選取 [**在 S 模式裝置中以 Windows 10 為目標]**  >  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="cd169-364">Select **Target Windows 10 in S mode devices** > **No**.</span></span>  
   >[!NOTE]  
   > <span data-ttu-id="cd169-365">在商務用 Windows 全息版中不支援 S 模式。</span><span class="sxs-lookup"><span data-stu-id="cd169-365">S mode isn't supported on Windows Holographic for Business.</span></span>
1. <span data-ttu-id="cd169-366">選取 [**使用者登入類型**  >  **Azure AD 使用者或群組**或**使用者登入類型**  >  **HoloLens 訪客**]，然後新增一個或多個使用者群組或帳戶。</span><span class="sxs-lookup"><span data-stu-id="cd169-366">Select **User logon type** > **Azure AD user or group** or **User logon type** > **HoloLens visitor**, and then add one or more user groups or accounts.</span></span>  

   <span data-ttu-id="cd169-367">只有屬於您在 [ **使用者登入類型** ] 中指定之群組或帳戶的使用者，才能使用 kiosk 體驗。</span><span class="sxs-lookup"><span data-stu-id="cd169-367">Only users who belong to the groups or accounts that you specify in **User logon type** can use the kiosk experience.</span></span>

1. <span data-ttu-id="cd169-368">使用下列選項選取一或多個應用程式：</span><span class="sxs-lookup"><span data-stu-id="cd169-368">Select one or more apps by using the following options:</span></span>
   - <span data-ttu-id="cd169-369">若要新增已上傳的商務用應用程式，請選取 [ **新增 store app** ]，然後選取您要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="cd169-369">To add an uploaded line-of-business app, select **Add store app** and then select the app that you want.</span></span>
   - <span data-ttu-id="cd169-370">若要新增應用程式，請指定其 AUMID，選取 [ **由 AUMID 新增** ]，然後輸入 APP 的 AUMID。</span><span class="sxs-lookup"><span data-stu-id="cd169-370">To add an app by specifying its AUMID, select **Add by AUMID** and then enter the AUMID of the app.</span></span> [<span data-ttu-id="cd169-371">請參閱可用的 Aumid 清單</span><span class="sxs-lookup"><span data-stu-id="cd169-371">See the list of available AUMIDs</span></span>](#aumids)

<span data-ttu-id="cd169-372">下一步是將設定檔 [指派](#mdmassign) 給群組。</span><span class="sxs-lookup"><span data-stu-id="cd169-372">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a id="mdmassign"></a><span data-ttu-id="cd169-373">MDM，步驟 4 &ndash; 將 kiosk 配置設定檔指派給群組</span><span class="sxs-lookup"><span data-stu-id="cd169-373">MDM, step 4 &ndash; Assign the kiosk configuration profile to a group</span></span>

<span data-ttu-id="cd169-374">使用 kiosk 配置設定檔的 [ **作業** ] 頁面，設定您想要的 kiosk 配置部署位置。</span><span class="sxs-lookup"><span data-stu-id="cd169-374">Use the **Assignments** page of the kiosk configuration profile to set where you want the kiosk configuration to deploy.</span></span> <span data-ttu-id="cd169-375">在最簡單的情況下，您會將 kiosk 配置設定檔指派給將裝置在 MDM 中註冊時將包含 HoloLens 裝置的群組。</span><span class="sxs-lookup"><span data-stu-id="cd169-375">In the simplest case, you assign the kiosk configuration profile to a group that will contain the HoloLens device when the device enrolls in MDM.</span></span>

### <a id="mdmsingledeploy"></a><span data-ttu-id="cd169-376">MDM、步驟 5 (單一 app) &ndash; 部署單一應用程式亭</span><span class="sxs-lookup"><span data-stu-id="cd169-376">MDM, step 5 (single-app) &ndash; Deploy a single-app kiosk</span></span>

<span data-ttu-id="cd169-377">當您使用 MDM 系統時，您可以在 OOBE 期間在 MDM 中註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="cd169-377">When you use an MDM system, you can enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="cd169-378">在 OOBE 完成之後，登入裝置很簡單。</span><span class="sxs-lookup"><span data-stu-id="cd169-378">After OOBE finishes, signing in to the device is easy.</span></span>

<span data-ttu-id="cd169-379">在 OOBE 期間，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="cd169-379">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="cd169-380">使用您在 kiosk 配置設定檔中指定的帳號登入。</span><span class="sxs-lookup"><span data-stu-id="cd169-380">Sign in by using the account that you specified in the kiosk configuration profile.</span></span>
1. <span data-ttu-id="cd169-381">註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="cd169-381">Enroll the device.</span></span> <span data-ttu-id="cd169-382">確認裝置已新增到指派給它的群組。</span><span class="sxs-lookup"><span data-stu-id="cd169-382">Make sure that the device is added to the group that the kiosk configuration profile is assigned to.</span></span>
1. <span data-ttu-id="cd169-383">等待 OOBE 完成，針對要下載並安裝的 microsoft store 應用程式，以及要套用的原則。</span><span class="sxs-lookup"><span data-stu-id="cd169-383">Wait for OOBE to finish, for the store app to download and install, and for policies to be applied.</span></span> <span data-ttu-id="cd169-384">然後重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="cd169-384">Then restart the device.</span></span>

<span data-ttu-id="cd169-385">下次登入裝置時，kiosk app 就會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="cd169-385">The next time you sign in to the device, the kiosk app should automatically start.</span></span>

<span data-ttu-id="cd169-386">如果此時沒有看到您的展臺設定，請 [檢查作業狀態](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。</span><span class="sxs-lookup"><span data-stu-id="cd169-386">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

### <a id="mdmmultideploy"></a><span data-ttu-id="cd169-387">MDM、步驟 5 (多重 app) &ndash; 部署多應用程式亭</span><span class="sxs-lookup"><span data-stu-id="cd169-387">MDM, step 5 (multi-app) &ndash; Deploy a multi-app kiosk</span></span>

<span data-ttu-id="cd169-388">當您使用 MDM 系統時，您可以將裝置加入到 Azure AD 租使用者，並在 OOBE 期間在 MDM 中註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="cd169-388">When you use an MDM system, you can join the device to your Azure AD tenant and enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="cd169-389">如有需要，請將註冊資訊提供給使用者，讓他們可以在 OOBE 程式中使用。</span><span class="sxs-lookup"><span data-stu-id="cd169-389">If appropriate, provide the enrollment information to the users so that they have it available during the OOBE process.</span></span>

> [!NOTE]  
> <span data-ttu-id="cd169-390">如果您已將 kiosk 配置設定檔指派給包含使用者的群組，請確認其中一個使用者帳戶是第一個登入裝置的帳戶。</span><span class="sxs-lookup"><span data-stu-id="cd169-390">If you have assigned the kiosk configuration profile to a group that contains users, make sure that one of those user accounts is the first account to sign in to the device.</span></span>

<span data-ttu-id="cd169-391">在 OOBE 期間，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="cd169-391">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="cd169-392">使用屬於 [ **使用者登入類型** ] 群組的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="cd169-392">Sign in by using the account that belongs to the **User logon type** group.</span></span>
1. <span data-ttu-id="cd169-393">註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="cd169-393">Enroll the device.</span></span>
1. <span data-ttu-id="cd169-394">等待任何屬於 kiosk 配置設定檔的 app 下載並安裝。</span><span class="sxs-lookup"><span data-stu-id="cd169-394">Wait for any apps that are part of the kiosk configuration profile to download and install.</span></span> <span data-ttu-id="cd169-395">此外，請等待應用原則。</span><span class="sxs-lookup"><span data-stu-id="cd169-395">Also, wait for policies to be applied.</span></span>  
1. <span data-ttu-id="cd169-396">在 OOBE 完成之後，您可以從 Microsoft 網上商店或邊載安裝其他 app。</span><span class="sxs-lookup"><span data-stu-id="cd169-396">After OOBE finishes, you can install additional apps from the Microsoft store or by sideloading.</span></span> <span data-ttu-id="cd169-397">裝置所歸屬的群組自動安裝[所需的應用程式](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)。</span><span class="sxs-lookup"><span data-stu-id="cd169-397">[Required apps](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) for the group that the device belongs to install automatically.</span></span>
1. <span data-ttu-id="cd169-398">安裝完成後，請重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="cd169-398">After the installation finishes, restart the device.</span></span>

<span data-ttu-id="cd169-399">下次您使用屬於 **使用者登入類型**的帳戶登入裝置時，kiosk app 應該會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="cd169-399">The next time you sign in to the device by using an account that belongs to the **User logon type**, the kiosk app should automatically launch.</span></span>

<span data-ttu-id="cd169-400">如果此時沒有看到您的展臺設定，請 [檢查作業狀態](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。</span><span class="sxs-lookup"><span data-stu-id="cd169-400">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

## <span data-ttu-id="cd169-401">使用預配套件來設定單一 app 或多重應用程式亭</span><span class="sxs-lookup"><span data-stu-id="cd169-401">Use a provisioning package to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="cd169-402">若要使用預配套件設定 kiosk 模式，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="cd169-402">To set up kiosk mode by using a provisioning package, follow these steps.</span></span>

1. <span data-ttu-id="cd169-403">[建立定義 kiosk](#ppkioskconfig)設定的 XML 檔案，包括 [開始版面](#start-layout-for-hololens)配置。</span><span class="sxs-lookup"><span data-stu-id="cd169-403">[Create an XML file that defines the kiosk configuration.](#ppkioskconfig), including a [Start layout](#start-layout-for-hololens).</span></span>
2. [<span data-ttu-id="cd169-404">將 XML 檔案新增至預配套件。</span><span class="sxs-lookup"><span data-stu-id="cd169-404">Add the XML file to a provisioning package.</span></span>](#ppconfigadd)
3. [<span data-ttu-id="cd169-405">將預配套件套用至 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="cd169-405">Apply the provisioning package to HoloLens.</span></span>](#ppapply)

### <a id="ppkioskconfig"></a><span data-ttu-id="cd169-406">預配套件，步驟 1 &ndash; 建立 kiosk 配置 XML 檔案</span><span class="sxs-lookup"><span data-stu-id="cd169-406">Provisioning package, step 1 &ndash; Create a kiosk configuration XML file</span></span>

<span data-ttu-id="cd169-407">依照 [一般指示，為 Windows 桌面建立 kiosk 配置 XML](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)檔案，除了下列情況：</span><span class="sxs-lookup"><span data-stu-id="cd169-407">Follow [the general instructions to create a kiosk configuration XML file for Windows desktop](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file), except for the following:</span></span>

- <span data-ttu-id="cd169-408">請勿在 Win32) 中加入傳統的 Windows 應用程式 (。</span><span class="sxs-lookup"><span data-stu-id="cd169-408">Do not include Classic Windows applications (Win32).</span></span> <span data-ttu-id="cd169-409">HoloLens 不支援這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="cd169-409">HoloLens does not support these applications.</span></span>
- <span data-ttu-id="cd169-410">使用適用于 HoloLens 的 [預留位置開始版面配置 XML](#start-layout-for-hololens) 。</span><span class="sxs-lookup"><span data-stu-id="cd169-410">Use the [placeholder Start layout XML](#start-layout-for-hololens) for HoloLens.</span></span>
- <span data-ttu-id="cd169-411">選用：新增來賓對 kiosk 設定的存取權</span><span class="sxs-lookup"><span data-stu-id="cd169-411">Optional: Add guest access to the kiosk configuration</span></span>

#### <a id="ppkioskguest"></a><span data-ttu-id="cd169-412">選用：新增來賓對 kiosk 設定的存取權</span><span class="sxs-lookup"><span data-stu-id="cd169-412">Optional: Add guest access to the kiosk configuration</span></span>

<span data-ttu-id="cd169-413">在 XML 檔案的 [配置] [ **Configs**區段](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)中，您可以將名為「**訪客**」的特殊群組設定為允許來賓使用資訊站。</span><span class="sxs-lookup"><span data-stu-id="cd169-413">In the [**Configs** section of the XML file](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs), you can configure a special group named **Visitor** to allow guests to use the kiosk.</span></span> <span data-ttu-id="cd169-414">如果將 kiosk 設定為支援 **「訪客特殊」** 群組，則會在登入頁面中新增「**來賓**」選項。</span><span class="sxs-lookup"><span data-stu-id="cd169-414">When the kiosk is configured to support the **Visitor** special group, a "**Guest**" option is added to the sign-in page.</span></span> <span data-ttu-id="cd169-415">**來賓**帳戶不需要密碼，而且與該帳戶相關聯的任何資料都會在帳戶登出時刪除。</span><span class="sxs-lookup"><span data-stu-id="cd169-415">The **Guest** account does not require a password, and any data that is associated with the account is deleted when the account signs out.</span></span>

<span data-ttu-id="cd169-416">若要啟用 **來賓** 帳戶，請將下列程式碼片段新增至您的 KIOSK 配置 XML：</span><span class="sxs-lookup"><span data-stu-id="cd169-416">To enable the **Guest** account, add the following snippet to your kiosk configuration XML:</span></span>

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a><span data-ttu-id="cd169-417">HoloLens 的預留位置開始時間版面配置</span><span class="sxs-lookup"><span data-stu-id="cd169-417">Placeholder Start layout for HoloLens</span></span>

<span data-ttu-id="cd169-418">如果您使用 [預配套件](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 來設定多應用程式資訊站，程式需要開始版面配置。</span><span class="sxs-lookup"><span data-stu-id="cd169-418">If you use a [provisioning package](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) to configure a multi-app kiosk, the procedure requires a Start layout.</span></span> <span data-ttu-id="cd169-419">在商務用 Windows 全息版中不支援開始進行版面配置自訂。</span><span class="sxs-lookup"><span data-stu-id="cd169-419">Start layout customization isn't supported in Windows Holographic for Business.</span></span> <span data-ttu-id="cd169-420">因此，您必須使用預留位置 [開始] 版面配置。</span><span class="sxs-lookup"><span data-stu-id="cd169-420">Therefore, you'll have to use a placeholder Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="cd169-421">因為單一 app 展臺會在使用者登入時啟動展臺應用程式，所以它不會使用 [開始] 功能表，也不需要開始進行版面配置。</span><span class="sxs-lookup"><span data-stu-id="cd169-421">Because a single-app kiosk starts the kiosk app when a user signs in, it does not use a Start menu and does not have to have a Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="cd169-422">如果您使用 [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 來設定多個 app 的展臺，您可以選擇使用 [開始] 版面配置。</span><span class="sxs-lookup"><span data-stu-id="cd169-422">If you use [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) to set up a multi-app kiosk, you can optionally use a Start layout.</span></span> <span data-ttu-id="cd169-423">如需詳細資訊，請參閱 [MDM (Intune 的 [預留位置啟動版面 ](#start-layout-file-for-mdm-intune-and-others)配置] 檔案，以及其他) 。</span><span class="sxs-lookup"><span data-stu-id="cd169-423">For more information, see [Placeholder Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

<span data-ttu-id="cd169-424">在 [開始] 版面配置中，將下列 **StartLayout** 區段新增至 KIOSK 提供 XML 檔案：</span><span class="sxs-lookup"><span data-stu-id="cd169-424">For the Start layout, add the following **StartLayout** section to the kiosk provisioning XML file:</span></span>

```xml
<!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
            <StartLayout>
                <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
                      <LayoutOptions StartTileGroupCellWidth="6" />
                      <DefaultLayoutOverride>
                        <StartLayoutCollection>
                          <defaultlayout:StartLayout GroupCellWidth="6">
                            <start:Group Name="">
                              <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
                            </start:Group>
                          </defaultlayout:StartLayout>
                        </StartLayoutCollection>
                      </DefaultLayoutOverride>
                    </LayoutModificationTemplate>
                ]]>
            </StartLayout>
            <!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
```

#### <a id="start-layout-file-for-mdm-intune-and-others"></a><span data-ttu-id="cd169-425">MDM (Intune 和其他人的預留位置啟動版面配置檔案) </span><span class="sxs-lookup"><span data-stu-id="cd169-425">Placeholder Start layout file for MDM (Intune and others)</span></span>

<span data-ttu-id="cd169-426">將下列範例儲存為 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="cd169-426">Save the following sample as an XML file.</span></span> <span data-ttu-id="cd169-427">您可以在 Microsoft (Intune 中設定多應用程式亭，或在提供 kiosk 設定檔的另一個 MDM 服務中，使用這個檔案) 。</span><span class="sxs-lookup"><span data-stu-id="cd169-427">You can use this file when you configure the multi-app kiosk in Microsoft Intune (or in another MDM service that provides a kiosk profile).</span></span>

> [!NOTE]
> <span data-ttu-id="cd169-428">如果您必須使用自訂設定及完整的 XML 配置來設定 MDM 服務中的展臺，請使用 [提供套件的開始配置指示](#start-layout-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="cd169-428">If you have to use a custom setting and full XML configuration to set up a kiosk in your MDM service, use the [Start layout instructions for a provisioning package](#start-layout-for-hololens).</span></span>

```xml
<LayoutModificationTemplate
    xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"
    xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout"
    xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout"
    Version="1">
  <RequiredStartGroupsCollection>
    <RequiredStartGroups>
      <AppendGroup Name="">
        <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
      </AppendGroup>
    </RequiredStartGroups>
  </RequiredStartGroupsCollection>
 </LayoutModificationTemplate>
```

### <a id="ppconfigadd"></a><span data-ttu-id="cd169-429">Prov.</span><span class="sxs-lookup"><span data-stu-id="cd169-429">Prov.</span></span> <span data-ttu-id="cd169-430">套件，步驟 2 &ndash; 將 kiosk 配置 XML 檔案新增至置備套件</span><span class="sxs-lookup"><span data-stu-id="cd169-430">package, step 2 &ndash; Add the kiosk configuration XML file to a provisioning package</span></span>

1. <span data-ttu-id="cd169-431">開啟 [Windows 配置設計](https://www.microsoft.com/store/apps/9nblggh4tx22)工具。</span><span class="sxs-lookup"><span data-stu-id="cd169-431">Open [Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22).</span></span>
1. <span data-ttu-id="cd169-432">選取 [ **高級提供**]，輸入您專案的名稱，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cd169-432">Select **Advanced provisioning**, enter a name for your project, and then select **Next**.</span></span>
1. <span data-ttu-id="cd169-433">選取 [ **Windows 10 全息**版]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cd169-433">Select **Windows 10 Holographic**, and then select **Next**.</span></span>
1. <span data-ttu-id="cd169-434">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="cd169-434">Select **Finish**.</span></span> <span data-ttu-id="cd169-435">套件的工作區就會開啟。</span><span class="sxs-lookup"><span data-stu-id="cd169-435">The workspace for your package opens.</span></span>
1. <span data-ttu-id="cd169-436">選取 [**執行時間設定**]  >  **AssignedAccess**[  >  **MultiAppAssignedAccessSettings**]。</span><span class="sxs-lookup"><span data-stu-id="cd169-436">Select **Runtime settings** > **AssignedAccess** > **MultiAppAssignedAccessSettings**.</span></span>
1. <span data-ttu-id="cd169-437">在中央窗格中，選取 **[流覽]** 以找出並選取您所建立的 KIOSK 配置 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="cd169-437">In the center pane, select **Browse** to locate and select the kiosk configuration XML file that you created.</span></span>

   ![Windows 設定設計工具中 MultiAppAssignedAccessSettings 欄位的螢幕擷取畫面](./images/multiappassignedaccesssettings.png)

1. <span data-ttu-id="cd169-439">**選用**。</span><span class="sxs-lookup"><span data-stu-id="cd169-439">**Optional**.</span></span> <span data-ttu-id="cd169-440"> (如果您想要在裝置的初始設定之後套用預配套件，且展臺裝置上已提供系統管理員使用者，請跳過此步驟。 ) 選取 [ **執行時間設定** &gt; **帳戶** &gt; **使用者**]，然後建立使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="cd169-440">(If you want to apply the provisioning package after the initial setup of the device, and there is an admin user already available on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a user account.</span></span> <span data-ttu-id="cd169-441">提供使用者名稱和密碼，然後選取 [ **UserGroup**系統  >  **管理員**]。</span><span class="sxs-lookup"><span data-stu-id="cd169-441">Provide a user name and password, and then select **UserGroup** > **Administrators**.</span></span>  
  
     <span data-ttu-id="cd169-442">您可以使用此帳戶來查看 [預配狀態與記錄]。</span><span class="sxs-lookup"><span data-stu-id="cd169-442">By using this account, you can view the provisioning status and logs.</span></span>  
1. <span data-ttu-id="cd169-443">**選用**。</span><span class="sxs-lookup"><span data-stu-id="cd169-443">**Optional**.</span></span> <span data-ttu-id="cd169-444"> (如果您在展臺裝置上已有非系統管理員帳戶，請跳過此步驟。 ) 選取 [ **執行時間設定** &gt; **帳戶** &gt; **使用者**]，然後建立本機使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="cd169-444">(If you already have a non-admin account on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a local user account.</span></span> <span data-ttu-id="cd169-445">請確定使用者名稱與您在配置 XML 中指定的帳號相同。</span><span class="sxs-lookup"><span data-stu-id="cd169-445">Make sure that the user name is the same as for the account that you specify in the configuration XML.</span></span> <span data-ttu-id="cd169-446">選取 [ **UserGroup**  >  **標準使用者**]。</span><span class="sxs-lookup"><span data-stu-id="cd169-446">Select **UserGroup** > **Standard Users**.</span></span>
1. <span data-ttu-id="cd169-447">選取 **[**  >  **儲存**檔案]。</span><span class="sxs-lookup"><span data-stu-id="cd169-447">Select **File** > **Save**.</span></span>
1. <span data-ttu-id="cd169-448">選取 [**匯出**  >  **預配套件**]，然後選取 [**擁有**者  >  **IT 系統管理員**]。這會將這個預配套件的優先順序設為高於從其他來源套用至此裝置的預配套件。</span><span class="sxs-lookup"><span data-stu-id="cd169-448">Select **Export** > **Provisioning package**, and then select **Owner** > **IT Admin**. This sets the precedence of this provisioning package higher than provisioning packages that are applied to this device from other sources.</span></span>
1. <span data-ttu-id="cd169-449">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="cd169-449">Select **Next**.</span></span>
1. <span data-ttu-id="cd169-450">在 [ **預配套件安全性** ] 頁面上，選取安全性選項。</span><span class="sxs-lookup"><span data-stu-id="cd169-450">On the **Provisioning package security** page, select a security option.</span></span>
   > [!IMPORTANT]  
   > <span data-ttu-id="cd169-451">如果您選取 [ **啟用套件簽署**]，您也必須選取要用來簽署套件的有效憑證。</span><span class="sxs-lookup"><span data-stu-id="cd169-451">If you select **Enable package signing**, you also have to select a valid certificate to use for signing the package.</span></span> <span data-ttu-id="cd169-452">若要這樣做，請選取 **[流覽]** ，然後選取您要用來簽署套件的憑證。</span><span class="sxs-lookup"><span data-stu-id="cd169-452">To do this, select **Browse** and select the certificate that you want to use to sign the package.</span></span>
   
   > [!CAUTION]  
   > <span data-ttu-id="cd169-453">請勿選取 [ **啟用套件加密**]。</span><span class="sxs-lookup"><span data-stu-id="cd169-453">Do not select **Enable package encryption**.</span></span> <span data-ttu-id="cd169-454">在 HoloLens 裝置上，此設定會導致置備失敗。</span><span class="sxs-lookup"><span data-stu-id="cd169-454">On HoloLens devices, this setting causes provisioning to fail.</span></span>
1. <span data-ttu-id="cd169-455">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="cd169-455">Select **Next**.</span></span>
1. <span data-ttu-id="cd169-456">指定要在建立預配套件時所要執行的輸出位置。</span><span class="sxs-lookup"><span data-stu-id="cd169-456">Specify the output location where you want the provisioning package to go when it's built.</span></span> <span data-ttu-id="cd169-457">Windows 設定設計工具預設會使用專案資料夾做為輸出位置。</span><span class="sxs-lookup"><span data-stu-id="cd169-457">By default, Windows Configuration Designer uses the project folder as the output location.</span></span> <span data-ttu-id="cd169-458">如果您想要變更輸出位置，請選取 **[流覽]**。</span><span class="sxs-lookup"><span data-stu-id="cd169-458">If you want to change the output location, select **Browse**.</span></span> <span data-ttu-id="cd169-459">完成後，請選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cd169-459">When you are finished, select **Next**.</span></span>
1. <span data-ttu-id="cd169-460">選取 [ **組建** ]，開始建立套件。</span><span class="sxs-lookup"><span data-stu-id="cd169-460">Select **Build** to start building the package.</span></span> <span data-ttu-id="cd169-461">建置佈建套件並不需要很長的時間。</span><span class="sxs-lookup"><span data-stu-id="cd169-461">The provisioning package doesn't take long to build.</span></span> <span data-ttu-id="cd169-462">[建立] 頁面會顯示專案資訊，且進度列會指出組建狀態。</span><span class="sxs-lookup"><span data-stu-id="cd169-462">The build page displays the project information, and the progress bar indicates the build status.</span></span>

### <a id="ppapply"></a><span data-ttu-id="cd169-463">預配套件，步驟3會 &ndash; 將預配套件套用至 HoloLens</span><span class="sxs-lookup"><span data-stu-id="cd169-463">Provisioning package, step 3 &ndash; Apply the provisioning package to HoloLens</span></span>

<span data-ttu-id="cd169-464">「使用預配套件設定 HoloLens」一文提供在下列情況下套用預配套件的詳細指示：</span><span class="sxs-lookup"><span data-stu-id="cd169-464">The "Configure HoloLens by using a provisioning package" article provides detailed instructions to apply the provisioning package under the following circumstances:</span></span>

- <span data-ttu-id="cd169-465">您最初可以 [在安裝期間將預配套件套用到 HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。</span><span class="sxs-lookup"><span data-stu-id="cd169-465">You can initially [apply a provisioning package to HoloLens during setup](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).</span></span>

- <span data-ttu-id="cd169-466">您也可以 [在安裝完成後將預配套件套用至 HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)。</span><span class="sxs-lookup"><span data-stu-id="cd169-466">You can also [apply a provisioning package to HoloLens after setup](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup).</span></span>

## <span data-ttu-id="cd169-467">使用 Windows Device Portal 設定單一應用程式亭</span><span class="sxs-lookup"><span data-stu-id="cd169-467">Use the Windows Device Portal to set up a single-app kiosk</span></span>

<span data-ttu-id="cd169-468">若要使用 Windows Device Portal 設定 kiosk 模式，請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="cd169-468">To set up kiosk mode by using the Windows Device Portal, follow these steps.</span></span>

1. <span data-ttu-id="cd169-469">[設定 HoloLens 裝置以使用 Windows Device Portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)。</span><span class="sxs-lookup"><span data-stu-id="cd169-469">[Set up the HoloLens device to use the Windows Device Portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal).</span></span> <span data-ttu-id="cd169-470">Device Portal 是您 HoloLens 上的網頁伺服器，您可以從電腦上的網頁瀏覽器與它連線。</span><span class="sxs-lookup"><span data-stu-id="cd169-470">The Device Portal is a web server on your HoloLens that you can connect to from a web browser on your PC.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="cd169-471">當您將 HoloLens 設定為使用 Device Portal 時，必須在裝置上啟用 [開發人員模式]。</span><span class="sxs-lookup"><span data-stu-id="cd169-471">When you set up HoloLens to use the Device Portal, you have to enable Developer Mode on the device.</span></span> <span data-ttu-id="cd169-472">Windows 全息版裝置上的開發人員模式可讓您使用側載入 app。</span><span class="sxs-lookup"><span data-stu-id="cd169-472">Developer Mode on a device that has Windows Holographic for Business enables you to side-load apps.</span></span> <span data-ttu-id="cd169-473">不過，此設定會建立使用者可安裝未透過 Microsoft Store 認證之 app 的風險。</span><span class="sxs-lookup"><span data-stu-id="cd169-473">However, this setting creates a risk that a user can install apps that have not been certified by the Microsoft Store.</span></span> <span data-ttu-id="cd169-474">系統管理員可以使用[原則 CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)中的**ApplicationManagement/AllowDeveloper 解除鎖定**設定，來封鎖啟用開發人員模式的功能。</span><span class="sxs-lookup"><span data-stu-id="cd169-474">Administrators can block the ability to enable Developer Mode by using the **ApplicationManagement/AllowDeveloper Unlock** setting in the [Policy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider).</span></span> [<span data-ttu-id="cd169-475">深入了解開發人員模式。</span><span class="sxs-lookup"><span data-stu-id="cd169-475">Learn more about Developer Mode.</span></span>](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. <span data-ttu-id="cd169-476">在電腦上，使用 [wi-fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) 或 [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)連接至 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="cd169-476">On a computer, connect to the HoloLens by using [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) or [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb).</span></span>

1. <span data-ttu-id="cd169-477">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="cd169-477">Do one of the following:</span></span>
   - <span data-ttu-id="cd169-478">如果您是第一次連線到 Windows Device Portal，請 [建立使用者名稱和密碼](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)</span><span class="sxs-lookup"><span data-stu-id="cd169-478">If you are connecting to the Windows Device Portal for the first time, [create a user name and password](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)</span></span>
   - <span data-ttu-id="cd169-479">輸入您先前設定的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="cd169-479">Enter the user name and password that you previously set up.</span></span>

    > [!TIP]
    > <span data-ttu-id="cd169-480">如果您在瀏覽器中看到憑證有誤，請遵循[下列疑難排解步驟](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)。</span><span class="sxs-lookup"><span data-stu-id="cd169-480">If you see a certificate error in the browser, follow [these troubleshooting steps](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate).</span></span>

1. <span data-ttu-id="cd169-481">在 Windows Device Portal 中，選取 [ **展臺模式]**。</span><span class="sxs-lookup"><span data-stu-id="cd169-481">In the Windows Device Portal, select **Kiosk Mode**.</span></span>

1. <span data-ttu-id="cd169-482">選取 [ **啟用 Kiosk 模式]**，選取裝置啟動時要執行的應用程式，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="cd169-482">Select **Enable Kiosk Mode**, select an app to run when the device starts, and then select **Save**.</span></span>

    ![Kiosk 模式](images/kiosk.png)
1. <span data-ttu-id="cd169-484">重新開機 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="cd169-484">Restart HoloLens.</span></span> <span data-ttu-id="cd169-485">如果您仍開啟了 [裝置入口網站] 頁面，您可以選取頁面頂端的 [ **重新開機** ]。</span><span class="sxs-lookup"><span data-stu-id="cd169-485">If you still have your Device Portal page open, you can select **Restart** at the top of the page.</span></span>

> [!NOTE]
> <span data-ttu-id="cd169-486">您可以透過裝置入口網站的 REST API 來設定 Kiosk 模式，方法是使用一個所需的查詢字串參數 ( "kioskModeEnabled"，其中其中一個值為 "true" 或 "false" ) ，而其中一個選擇性參數 ( "startupApp" 與套件名稱) 的值。</span><span class="sxs-lookup"><span data-stu-id="cd169-486">Kiosk Mode can be set via Device Portal’s REST API by doing a POST to /api/holographic/kioskmode/settings with one required query string parameter (“kioskModeEnabled” with a value of “true” or “false”) and one optional parameter (“startupApp” with a value of a package name).</span></span> <span data-ttu-id="cd169-487">請記住，Device Portal 僅適用于開發人員，不應在非開發人員裝置上啟用。</span><span class="sxs-lookup"><span data-stu-id="cd169-487">Please keep in mind that Device Portal is intended for developers only and should not be enabled on non-developer devices.</span></span> <span data-ttu-id="cd169-488">REST API 在未來的更新/發行中可能會變更。</span><span class="sxs-lookup"><span data-stu-id="cd169-488">The REST API is subject to change in future updates/releases.</span></span>

## <span data-ttu-id="cd169-489">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="cd169-489">More information</span></span>

### <span data-ttu-id="cd169-490">瞭解如何使用預配套件來設定展臺。</span><span class="sxs-lookup"><span data-stu-id="cd169-490">Watch how to configure a kiosk by using a provisioning package.</span></span>  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <span data-ttu-id="cd169-491">全域指派的存取-Kiosk 模式</span><span class="sxs-lookup"><span data-stu-id="cd169-491">Global Assigned Access – Kiosk Mode</span></span>
- <span data-ttu-id="cd169-492">透過啟用在系統層級套用 Kiosk 模式的新型 Kiosk 方法，減少了資訊站的身分識別管理。</span><span class="sxs-lookup"><span data-stu-id="cd169-492">Reduced Identity management for Kiosk, by enabling new Kiosk method that applies Kiosk mode at the system level.</span></span>

<span data-ttu-id="cd169-493">這項新功能可讓 IT 系統管理員針對在系統層級適用的多個 app kiosk 模式設定 HoloLens 2 裝置，且與登入裝置的每個人都有關聯的資訊。</span><span class="sxs-lookup"><span data-stu-id="cd169-493">This new feature allows an IT Admin to configure a HoloLens 2 device for multiple app kiosk mode which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span> <span data-ttu-id="cd169-494">請在 [此深入瞭解](hololens-global-assigned-access-kiosk.md)這項新功能。</span><span class="sxs-lookup"><span data-stu-id="cd169-494">Read about this new feature in detail [here](hololens-global-assigned-access-kiosk.md).</span></span>

### <span data-ttu-id="cd169-495">在多應用程式亭模式中自動啟動應用程式</span><span class="sxs-lookup"><span data-stu-id="cd169-495">Automatic launch of an application in multiple-app kiosk mode</span></span> 
- <span data-ttu-id="cd169-496">自動應用程式啟動的焦點體驗，進一步增加針對 Kiosk 模式體驗所選擇的 UI 和 app 選項。</span><span class="sxs-lookup"><span data-stu-id="cd169-496">Focused experience with automatic app launch, further increasing the UI and app selections chosen for Kiosk mode experiences.</span></span>

<span data-ttu-id="cd169-497">僅適用于多應用程式亭模式，且只有1個 app 可以使用 [指派的存取設定] 底下的 [醒目提示] 屬性來自動啟動。</span><span class="sxs-lookup"><span data-stu-id="cd169-497">Applies only to multiple-app kiosk mode and only 1 app can be designated to auto-launch using highlighted attribute below in Assigned Access configuration.</span></span> 

<span data-ttu-id="cd169-498">應用程式會在使用者登入時自動啟動。</span><span class="sxs-lookup"><span data-stu-id="cd169-498">Application is automatically launched when user signs-in.</span></span> 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <span data-ttu-id="cd169-499">管理失敗處理的 Kiosk 模式行為變更</span><span class="sxs-lookup"><span data-stu-id="cd169-499">Kiosk mode behavior changes for handling of failures</span></span>
- <span data-ttu-id="cd169-500">在 Kiosk 模式失敗中消除可用的應用程式，以獲得更安全的 Kiosk 模式。</span><span class="sxs-lookup"><span data-stu-id="cd169-500">More secure Kiosk mode by eliminating available apps on Kiosk mode failures.</span></span> 

<span data-ttu-id="cd169-501">舊版在套用 kiosk 模式時遇到失敗，HoloLens 用來顯示 [開始] 功能表中的所有應用程式。</span><span class="sxs-lookup"><span data-stu-id="cd169-501">Earlier on encountering failures in applying kiosk mode, HoloLens used to show up all applications in start menu.</span></span> <span data-ttu-id="cd169-502">現在在 Windows 全息版20H2 的情況下，[開始] 功能表中將不會顯示任何應用程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cd169-502">Now in Windows Holographic version 20H2 in the case of failures no apps will be shown in the start menu as below:</span></span> 

![[展臺模式] 在失敗時的外觀影像。](images/hololens-kiosk-failure-behavior.png )

### <span data-ttu-id="cd169-504">為離線資訊站快取 AAD 群組成員資格</span><span class="sxs-lookup"><span data-stu-id="cd169-504">Cache AAD Group membership for offline Kiosk</span></span>
- <span data-ttu-id="cd169-505">已啟用離線亭，以使用 AAD 群組，最多可達60天。</span><span class="sxs-lookup"><span data-stu-id="cd169-505">Enabled Offline Kiosks to be used with AAD groups for up to 60 days.</span></span>

<span data-ttu-id="cd169-506">此原則控制的天數是，您可以使用 AAD 群組成員資格快取來指派針對已登入使用者的 AAD 群組指派的存取設定。</span><span class="sxs-lookup"><span data-stu-id="cd169-506">This policy controls for how many days, AAD group membership cache is allowed to be used for Assigned Access configurations targeting AAD groups for signed in user.</span></span> <span data-ttu-id="cd169-507">只要將此原則值設為大於0的值，就不會再使用 cache。</span><span class="sxs-lookup"><span data-stu-id="cd169-507">Once this policy value is set to value greater than 0 only then cache is used otherwise not.</span></span>  

<span data-ttu-id="cd169-508">Name （名稱）： AADGroupMembershipCacheValidityInDays URI 值：./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays</span><span class="sxs-lookup"><span data-stu-id="cd169-508">Name: AADGroupMembershipCacheValidityInDays URI value: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays</span></span>

<span data-ttu-id="cd169-509">最小值-0 天</span><span class="sxs-lookup"><span data-stu-id="cd169-509">Min - 0 days</span></span>  
<span data-ttu-id="cd169-510">最大值-60 天</span><span class="sxs-lookup"><span data-stu-id="cd169-510">Max - 60 days</span></span> 

<span data-ttu-id="cd169-511">正確使用此原則的步驟如下：</span><span class="sxs-lookup"><span data-stu-id="cd169-511">Steps to use this policy correctly:</span></span> 
1. <span data-ttu-id="cd169-512">針對使用 AAD 群組的展臺建立裝置配置設定檔，並將它指派給 HoloLens 裝置 (s) 。</span><span class="sxs-lookup"><span data-stu-id="cd169-512">Create a device configuration profile for kiosk targeting AAD groups and assign it to HoloLens device(s).</span></span> 
1. <span data-ttu-id="cd169-513">建立自訂 OMA URI 的裝置設定，將此原則值設為所需的天數 ( # A0 0) 並將它指派給 HoloLens 裝置 (s) 。</span><span class="sxs-lookup"><span data-stu-id="cd169-513">Create a custom OMA URI based device configuration which sets this policy value to desired number of days (> 0) and assign it to HoloLens device(s).</span></span> 
    1. <span data-ttu-id="cd169-514">URI 值應該在 OMA URI 文字方塊中輸入/Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays。</span><span class="sxs-lookup"><span data-stu-id="cd169-514">The URI value should be entered in OMA-URI text box as ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays</span></span>
    1. <span data-ttu-id="cd169-515">這個值可以介於 min/max （允許）之間。</span><span class="sxs-lookup"><span data-stu-id="cd169-515">The value can be between min / max allowed.</span></span>
1. <span data-ttu-id="cd169-516">註冊 HoloLens 裝置並確認這兩個設定都已套用到裝置。</span><span class="sxs-lookup"><span data-stu-id="cd169-516">Enroll HoloLens devices and verify both configurations get applied to the device.</span></span> 
1. <span data-ttu-id="cd169-517">讓 AAD 使用者1登入當網際網路可供使用時，一旦使用者登入和 AAD 群組成員資格已成功確認，就會建立快取。</span><span class="sxs-lookup"><span data-stu-id="cd169-517">Let AAD user 1 sign-in when internet is available, once user signs-in and AAD group membership is confirmed successfully, cache will be created.</span></span> 
1. <span data-ttu-id="cd169-518">現在 AAD 使用者1可以讓 HoloLens 離線，並在 kiosk 模式使用它，只要策略值允許 X 個天數。</span><span class="sxs-lookup"><span data-stu-id="cd169-518">Now AAD user 1 can take HoloLens offline and use it for kiosk mode as long as policy value allows for X number of days.</span></span> 
1. <span data-ttu-id="cd169-519">步驟4和5可針對任何其他 AAD 使用者 N 進行重複。以下是任何 AAD 使用者都必須使用網際網路登入到裝置，所以至少我們可以判斷他們是對哪些使用者配置目標的 AAD 群組成員。</span><span class="sxs-lookup"><span data-stu-id="cd169-519">Steps 4 and 5 can be repeated for any other AAD user N. Key point here is that any AAD user must sign-in to device using Internet so at least once we can determine that they are member of AAD group to which Kiosk configuration is targeted.</span></span> 
 
> [!NOTE]
> <span data-ttu-id="cd169-520">除非 AAD 使用者執行步驟4，否則會在「中斷連接」的環境中遇到失敗的行為。</span><span class="sxs-lookup"><span data-stu-id="cd169-520">Until step 4 is performed for a AAD user will experience failure behavior mentioned in “disconnected” environments.</span></span> 


## <span data-ttu-id="cd169-521">適用于 HoloLens 的 XML Kiosk 程式碼範例</span><span class="sxs-lookup"><span data-stu-id="cd169-521">XML Kiosk Code Samples for HoloLens</span></span>

### <span data-ttu-id="cd169-522">針對 AAD 群組的多個 app kiosk 模式。</span><span class="sxs-lookup"><span data-stu-id="cd169-522">Multiple app kiosk mode targeting an AAD group.</span></span> 
<span data-ttu-id="cd169-523">此展臺會針對 AAD 群組中的使用者部署一個資訊站，他們將會啟用一個包含3個應用程式的展臺： [設定]、[遠端協助] 和 [意見反應中心]。</span><span class="sxs-lookup"><span data-stu-id="cd169-523">This kiosk deploys a Kiosk that for users in the AAD group, they will have a Kiosk enabled that includes the 3 apps: Settings, Remote Assist, and Feedback Hub.</span></span> <span data-ttu-id="cd169-524">若要將這個範例修改成立即使用，請務必變更以下醒目提示的 GUID，以符合您自己的 AAD 群組。</span><span class="sxs-lookup"><span data-stu-id="cd169-524">To modify this sample to be used immediately, make sure to change the GUID highlighted below to match an AAD Group of your own.</span></span> 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <span data-ttu-id="cd169-525">以 AAD 帳戶為目標的多個 app kiosk 模式。</span><span class="sxs-lookup"><span data-stu-id="cd169-525">Multiple app kiosk mode targeting AAD account.</span></span>
<span data-ttu-id="cd169-526">此展臺會為單一使用者部署資訊站，他們將會啟用一個包含3個應用程式的展臺： [設定]、[遠端協助] 和 [意見反應中心]。</span><span class="sxs-lookup"><span data-stu-id="cd169-526">This kiosk deploys a Kiosk for a single user, they will have a Kiosk enabled that includes the 3 apps: Settings, Remote Assist, and Feedback Hub.</span></span> <span data-ttu-id="cd169-527">若要將這個範例修改成立即使用，請務必變更下列的帳戶，以符合您自己的 AAD 帳戶。</span><span class="sxs-lookup"><span data-stu-id="cd169-527">To modify this sample to be used immediately, make sure to change the account highlighted below to match an AAD Account of your own.</span></span> 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

