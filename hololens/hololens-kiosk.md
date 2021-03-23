---
title: 設定 HoloLens (第 1 代) 的 kiosk
description: 瞭解如何設定並使用資訊站設定來鎖定 HoloLens 裝置上的應用程式。
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
ms.openlocfilehash: a043b2f96bec6127d52622b4662279c777df6f8f
ms.sourcegitcommit: e1dd3d79d763d02d4fe04c82d8f49e8f9d85ee4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "11445373"
---
# <a name="set-up-hololens-as-a-kiosk"></a><span data-ttu-id="bda02-103">設定 HoloLens (第 1 代) 的 kiosk</span><span class="sxs-lookup"><span data-stu-id="bda02-103">Set up HoloLens as a kiosk</span></span>

<span data-ttu-id="bda02-104">您可以將 HoloLens 裝置設定為在資訊站模式中執行，將裝置設定為固定\*\* 用途裝置 ，也稱為資訊站。</span><span class="sxs-lookup"><span data-stu-id="bda02-104">You can configure a HoloLens device to function as a fixed-purpose device, also called a *kiosk*, by configuring the device to run in kiosk mode.</span></span> <span data-ttu-id="bda02-105">Kiosk 模式會限制 (裝置) 或使用者使用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="bda02-105">Kiosk mode limits the applications (or users) that are available on the device.</span></span> <span data-ttu-id="bda02-106">資訊站模式是一項方便的功能，可用於將 HoloLens 裝置專用於商務應用程式，或在 App 示範中使用 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="bda02-106">Kiosk mode is a convenient feature that you can use to dedicate a HoloLens device to business apps, or to use the HoloLens device in an app demo.</span></span>

<span data-ttu-id="bda02-107">本文提供 HoloLens 裝置所特有的資訊站組配置方面的資訊。</span><span class="sxs-lookup"><span data-stu-id="bda02-107">This article provides information about aspects of kiosk configuration that are specific to HoloLens devices.</span></span> <span data-ttu-id="bda02-108">有關不同類型的 Windows 型資訊站以及如何設定這類資訊站的一般資訊，請參閱在 Windows 桌上出版上設定資訊站和 [數位標記](https://docs.microsoft.com/windows/configuration/kiosk-methods)。</span><span class="sxs-lookup"><span data-stu-id="bda02-108">For general information about the different types of Windows-based kiosks and how to configure them, see [Configure kiosks and digital signs on Windows desktop editions](https://docs.microsoft.com/windows/configuration/kiosk-methods).</span></span>  

> [!IMPORTANT]  
> <span data-ttu-id="bda02-109">資訊站模式會決定當使用者登錄裝置時，哪些應用程式可以使用。</span><span class="sxs-lookup"><span data-stu-id="bda02-109">Kiosk mode determines which apps are available when a user signs in to the device.</span></span> <span data-ttu-id="bda02-110">不過，資訊站模式不是安全性方法。</span><span class="sxs-lookup"><span data-stu-id="bda02-110">However, kiosk mode is not a security method.</span></span> <span data-ttu-id="bda02-111">它不會停止「允許」應用程式開啟另一個不允許的應用程式。</span><span class="sxs-lookup"><span data-stu-id="bda02-111">It does not stop an "allowed" app from opening another app that is not allowed.</span></span> <span data-ttu-id="bda02-112">若要封鎖應用程式或程式開啟，請使用 WINDOWS Defender 應用程式控制 ([WDAC](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)) 建立適當的策略。</span><span class="sxs-lookup"><span data-stu-id="bda02-112">In order to block apps or processes from opening, use [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) to create appropriate policies.</span></span>
>
> <span data-ttu-id="bda02-113">深入瞭解 Microsoft 服務以為使用者提供 HoloLens 2 使用的進一級安全性，並深入瞭解狀態分隔與隔離 [- Defender 保護](security-state-separation-isolation.md#defender-protections)。</span><span class="sxs-lookup"><span data-stu-id="bda02-113">Learn more about the Microsoft services to give users an advanced level of security that HoloLens 2 uses, read more about [State separation and isolation - Defender protections](security-state-separation-isolation.md#defender-protections).</span></span> <span data-ttu-id="bda02-114">或瞭解如何使用 [WDAC 和 Windows PowerShell 來允許或封鎖 HoloLens 2](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)裝置與 Microsoft Intune 上的應用程式。</span><span class="sxs-lookup"><span data-stu-id="bda02-114">Or learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="bda02-115">您可以在單一 App 或多應用程式設定中使用資訊站模式，而且您可以使用三個程式之一來設定及部署資訊站設定。</span><span class="sxs-lookup"><span data-stu-id="bda02-115">You can use kiosk mode in either a single-app or a multi-app configuration, and you can use one of three processes to set up and deploy the kiosk configuration.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="bda02-116">刪除多應用程式組配置會移除指派的存取功能所建立的使用者鎖定設定檔。</span><span class="sxs-lookup"><span data-stu-id="bda02-116">Deleting the multi-app configuration removes the user lockdown profiles that the assigned access feature created.</span></span> <span data-ttu-id="bda02-117">不過，它不會還原所有策略變更。</span><span class="sxs-lookup"><span data-stu-id="bda02-117">However, it does not revert all the policy changes.</span></span> <span data-ttu-id="bda02-118">若要還原這些策略，您必須將裝置重設為出廠設定。</span><span class="sxs-lookup"><span data-stu-id="bda02-118">To revert these policies, you have to reset the device to the factory settings.</span></span>

## <a name="plan-the-kiosk-deployment"></a><span data-ttu-id="bda02-119">規劃資訊站部署</span><span class="sxs-lookup"><span data-stu-id="bda02-119">Plan the kiosk deployment</span></span>

<span data-ttu-id="bda02-120">規劃您的 Kiosk 時，您必須能夠回答下列問題。</span><span class="sxs-lookup"><span data-stu-id="bda02-120">When planning your Kiosk you'll need to be able to answer the following questions.</span></span> <span data-ttu-id="bda02-121">以下是閱讀此頁面時要考慮的一些決策，以及這些問題的一些考慮。</span><span class="sxs-lookup"><span data-stu-id="bda02-121">Here are some decisions to think about while reading this page and some considerations for these questions.</span></span>
1. **<span data-ttu-id="bda02-122">誰將會使用您的 Kiosk，以及他們 (使用 [) 的帳戶類型 ](hololens-identity.md) ？</span><span class="sxs-lookup"><span data-stu-id="bda02-122">Who will be using your Kiosk, and what [type of account(s)](hololens-identity.md) will they be using?</span></span>** <span data-ttu-id="bda02-123">這是您可能已經做出的決定，不應該為了您的資訊站而調整，但會影響稍後指派資訊站。</span><span class="sxs-lookup"><span data-stu-id="bda02-123">This is a decision you have likely already made and shouldn't be adjusted for the sake of your Kiosk, but will affect how the Kiosk is assigned later.</span></span>
1. **<span data-ttu-id="bda02-124">您是否需要讓每個使用者/群組擁有不同的資訊站，或某些使用者/群組未啟用資訊站？</span><span class="sxs-lookup"><span data-stu-id="bda02-124">Do you need to have either different Kiosks per user/group or a Kiosk not enabled for some?</span></span>** <span data-ttu-id="bda02-125">如果是這樣，您就會想要透過 XML 建立您的 Kiosk。</span><span class="sxs-lookup"><span data-stu-id="bda02-125">If so, you'll want to create your Kiosk via XML.</span></span> 
1. **<span data-ttu-id="bda02-126">您的 Kiosk 中有多少應用程式？</span><span class="sxs-lookup"><span data-stu-id="bda02-126">How many apps will be in your Kiosk?</span></span>** <span data-ttu-id="bda02-127">如果您擁有超過 1 個應用程式，則需要多應用程式 Kiosk。</span><span class="sxs-lookup"><span data-stu-id="bda02-127">If you have more than 1 app, you'll need a multi-app Kiosk.</span></span> 
1. **<span data-ttu-id="bda02-128">您的 Kiosk () 哪個應用程式？</span><span class="sxs-lookup"><span data-stu-id="bda02-128">Which app(s) will be in your Kiosk?</span></span>** <span data-ttu-id="bda02-129">請使用下方的 AUMID 清單來新增In-Box應用程式。</span><span class="sxs-lookup"><span data-stu-id="bda02-129">Please use our list of AUMIDs below to add any In-Box apps in addition to your own.</span></span>
1. **<span data-ttu-id="bda02-130">您打算如何部署您的 Kiosk？</span><span class="sxs-lookup"><span data-stu-id="bda02-130">How do you plan to deploy your Kiosk?</span></span>** <span data-ttu-id="bda02-131">如果您是在 MDM 中註冊裝置，我們建議您使用 MDM 部署您的 Kiosk。</span><span class="sxs-lookup"><span data-stu-id="bda02-131">If you are enrolling device in MDM then we suggest using MDM to deploy your Kiosk.</span></span> <span data-ttu-id="bda02-132">如果您不是使用 MDM，可以使用部署套件進行部署。</span><span class="sxs-lookup"><span data-stu-id="bda02-132">If you are not using MDM then deployment with Provisioning Package is available.</span></span>  

### <a name="kiosk-mode-requirements"></a><span data-ttu-id="bda02-133">資訊站模式需求</span><span class="sxs-lookup"><span data-stu-id="bda02-133">Kiosk mode requirements</span></span>

<span data-ttu-id="bda02-134">您可以將任何 HoloLens 2 裝置設定為使用資訊站模式。</span><span class="sxs-lookup"><span data-stu-id="bda02-134">You can configure any HoloLens 2 device to use kiosk mode.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bda02-135">只有在裝置有商務用 Windows Holographic 時，才能使用 Kiosk 模式。</span><span class="sxs-lookup"><span data-stu-id="bda02-135">Kiosk mode is available only if the device has Windows Holographic for Business.</span></span> <span data-ttu-id="bda02-136">所有 HoloLens 2 裝置都提供 Windows 商務用 Holographic，而且沒有其他版本。</span><span class="sxs-lookup"><span data-stu-id="bda02-136">All HoloLens 2 devices ship with Windows Holographic for Business and there are no other editions.</span></span> <span data-ttu-id="bda02-137">每個 HoloLens 2 裝置都能在方塊外執行 Kiosk 模式。</span><span class="sxs-lookup"><span data-stu-id="bda02-137">Every HoloLens 2 devices is able to run Kiosk mode out of the box.</span></span>
>
> <span data-ttu-id="bda02-138">HoloLens (第一代) 裝置必須同時升級 OS 版本和 OS 版本。</span><span class="sxs-lookup"><span data-stu-id="bda02-138">HoloLens (1st gen) devices need to be upgraded both in terms of OS build and OS edition.</span></span> <span data-ttu-id="bda02-139">以下是將 HoloLens (第一代) Windows [Holographic for Business](hololens1-upgrade-enterprise.md) 版本更新的資訊。</span><span class="sxs-lookup"><span data-stu-id="bda02-139">Here is more information on updating a HoloLens (1st gen) to [Windows Holographic for Business](hololens1-upgrade-enterprise.md) edition.</span></span> <span data-ttu-id="bda02-140">若要更新 HoloLens (第 1 代) 裝置以使用資訊站模式，您必須先確定裝置執行 Windows 10、版本 1803 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="bda02-140">To update a HoloLens (1st gen) device to use kiosk mode, you must first make sure that the device runs Windows 10, version 1803, or a later version.</span></span> <span data-ttu-id="bda02-141">如果您已經使用 Windows 裝置修復工具將 HoloLens (第 1 代) 裝置復原至其預設版本，或者如果您已安裝最新的更新，您的裝置就可以進行設定。</span><span class="sxs-lookup"><span data-stu-id="bda02-141">If you have used the Windows Device Recovery Tool to recover your HoloLens (1st gen) device to its default build, or if you have installed the most recent updates, your device is ready to configure.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="bda02-142">若要協助保護在資訊站模式中執行的裝置，請考慮新增關閉 USB 連接等功能的裝置管理政策。</span><span class="sxs-lookup"><span data-stu-id="bda02-142">To help protect devices that run in kiosk mode, consider adding device management policies that turn off features such as USB connectivity.</span></span> <span data-ttu-id="bda02-143">此外，請檢查您的更新響鈴設定，以確保在上班時間期間不會發生自動更新。</span><span class="sxs-lookup"><span data-stu-id="bda02-143">Additionally, check your update ring settings to make sure that automatic updates do not occur during business hours.</span></span>

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a><span data-ttu-id="bda02-144">決定單一應用程式資訊站或多應用程式資訊站</span><span class="sxs-lookup"><span data-stu-id="bda02-144">Decide between a single-app kiosk or a multi-app kiosk</span></span>

<span data-ttu-id="bda02-145">當使用者登錄裝置時，單一應用程式資訊站會啟動指定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="bda02-145">A single-app kiosk starts the specified app when the user signs in to the device.</span></span> <span data-ttu-id="bda02-146">已停用開始功能表，就像 Cortana 一樣。</span><span class="sxs-lookup"><span data-stu-id="bda02-146">The Start menu is disabled, as is Cortana.</span></span> <span data-ttu-id="bda02-147">HoloLens 2 裝置不會回應開始 [手勢](hololens2-basic-usage.md#start-gesture) 。</span><span class="sxs-lookup"><span data-stu-id="bda02-147">A HoloLens 2 device does not respond to the [Start](hololens2-basic-usage.md#start-gesture) gesture.</span></span> <span data-ttu-id="bda02-148">第 1 代 (HoloLens) 不會回應綻 [開手勢](hololens1-basic-usage.md) 。</span><span class="sxs-lookup"><span data-stu-id="bda02-148">A HoloLens (1st gen) device does not respond to the [bloom](hololens1-basic-usage.md) gesture.</span></span> <span data-ttu-id="bda02-149">由於只有一個應用程式可以執行，因此使用者無法放置其他應用程式。</span><span class="sxs-lookup"><span data-stu-id="bda02-149">Because only one app can run, the user cannot place other apps.</span></span>

<span data-ttu-id="bda02-150">當使用者登錄裝置時，多應用程式資訊站會顯示開始功能表。</span><span class="sxs-lookup"><span data-stu-id="bda02-150">A multi-app kiosk displays the Start menu when the user signs in to the device.</span></span> <span data-ttu-id="bda02-151">資訊站組式會決定哪些應用程式可在開始功能表上使用。</span><span class="sxs-lookup"><span data-stu-id="bda02-151">The kiosk configuration determines which apps are available on the Start menu.</span></span> <span data-ttu-id="bda02-152">您可以使用多應用程式資訊站，只向使用者呈現他們必須使用的事物，並移除他們不需要使用的事物，以為使用者提供易於理解的體驗。</span><span class="sxs-lookup"><span data-stu-id="bda02-152">You can use a multi-app kiosk to provide an easy-to-understand experience for users by presenting to them only the things that they have to use, and removing the things they don't need to use.</span></span>

<span data-ttu-id="bda02-153">下表列出不同資訊站模式中的功能。</span><span class="sxs-lookup"><span data-stu-id="bda02-153">The following table lists the feature capabilities in the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="bda02-154">[開始] 功能表</span><span class="sxs-lookup"><span data-stu-id="bda02-154">Start menu</span></span> |<span data-ttu-id="bda02-155">快速動作功能表</span><span class="sxs-lookup"><span data-stu-id="bda02-155">Quick Actions menu</span></span> |<span data-ttu-id="bda02-156">相機和視像</span><span class="sxs-lookup"><span data-stu-id="bda02-156">Camera and video</span></span> |<span data-ttu-id="bda02-157">Miracast</span><span class="sxs-lookup"><span data-stu-id="bda02-157">Miracast</span></span> |<span data-ttu-id="bda02-158">Cortana</span><span class="sxs-lookup"><span data-stu-id="bda02-158">Cortana</span></span> |<span data-ttu-id="bda02-159">內建語音命令</span><span class="sxs-lookup"><span data-stu-id="bda02-159">Built-in voice commands</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|<span data-ttu-id="bda02-160">單一應用程式資訊站</span><span class="sxs-lookup"><span data-stu-id="bda02-160">Single-app kiosk</span></span> |<span data-ttu-id="bda02-161">已停用</span><span class="sxs-lookup"><span data-stu-id="bda02-161">Disabled</span></span> |<span data-ttu-id="bda02-162">已停用</span><span class="sxs-lookup"><span data-stu-id="bda02-162">Disabled</span></span>   |<span data-ttu-id="bda02-163">已停用</span><span class="sxs-lookup"><span data-stu-id="bda02-163">Disabled</span></span> |<span data-ttu-id="bda02-164">已停用</span><span class="sxs-lookup"><span data-stu-id="bda02-164">Disabled</span></span>   |<span data-ttu-id="bda02-165">已停用</span><span class="sxs-lookup"><span data-stu-id="bda02-165">Disabled</span></span> |<span data-ttu-id="bda02-166">已啟用 <sup> 1</span><span class="sxs-lookup"><span data-stu-id="bda02-166">Enabled<sup>1</span></span></sup> |
|<span data-ttu-id="bda02-167">多個應用程式 Kiosk</span><span class="sxs-lookup"><span data-stu-id="bda02-167">Multi-app kiosk</span></span> |<span data-ttu-id="bda02-168">啟用</span><span class="sxs-lookup"><span data-stu-id="bda02-168">Enabled</span></span> |<span data-ttu-id="bda02-169">已啟用 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="bda02-169">Enabled<sup>2</span></span></sup> |<span data-ttu-id="bda02-170">可用 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="bda02-170">Available<sup>2</span></span></sup> |<span data-ttu-id="bda02-171">可用 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="bda02-171">Available<sup>2</span></span></sup> |<span data-ttu-id="bda02-172">提供 <sup> 2、3</span><span class="sxs-lookup"><span data-stu-id="bda02-172">Available<sup>2, 3</span></span></sup>  |<span data-ttu-id="bda02-173">已啟用 <sup> 1</span><span class="sxs-lookup"><span data-stu-id="bda02-173">Enabled<sup>1</span></span></sup> |

> <sup><span data-ttu-id="bda02-174">1 </sup> 與停用功能相關的語音命令無法運作。</span><span class="sxs-lookup"><span data-stu-id="bda02-174">1</sup> Voice commands that relate to disabled features do not function.</span></span>  
> <sup><span data-ttu-id="bda02-175">2 </sup> 若要瞭解如何設定這些功能，請參閱選取 [資訊站應用程式](#plan-kiosk-apps)。</span><span class="sxs-lookup"><span data-stu-id="bda02-175">2</sup> For more information about how to configure these features, see [Select kiosk apps](#plan-kiosk-apps).</span></span>  
> <sup><span data-ttu-id="bda02-176">3 </sup> 即使 Cortana 已停用，內建的語音命令也已啟用。</span><span class="sxs-lookup"><span data-stu-id="bda02-176">3</sup> Even if Cortana is disabled, the built-in voice commands are enabled.</span></span>

<span data-ttu-id="bda02-177">下表列出不同資訊站模式的使用者支援功能。</span><span class="sxs-lookup"><span data-stu-id="bda02-177">The following table lists the user support features of the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="bda02-178">支援的使用者類型</span><span class="sxs-lookup"><span data-stu-id="bda02-178">Supported user types</span></span> | <span data-ttu-id="bda02-179">自動登入</span><span class="sxs-lookup"><span data-stu-id="bda02-179">Automatic sign-in</span></span> | <span data-ttu-id="bda02-180">多個存取層級</span><span class="sxs-lookup"><span data-stu-id="bda02-180">Multiple access levels</span></span> |
| --- | --- | --- | --- |
|<span data-ttu-id="bda02-181">單一應用程式資訊站</span><span class="sxs-lookup"><span data-stu-id="bda02-181">Single-app kiosk</span></span> |<span data-ttu-id="bda02-182">Azure Active Directory (或) 帳戶的受管理服務帳戶 (MSA) 帳戶</span><span class="sxs-lookup"><span data-stu-id="bda02-182">Managed Service Account (MSA) in Azure Active Directory (Azure AD) or local account</span></span> |<span data-ttu-id="bda02-183">是</span><span class="sxs-lookup"><span data-stu-id="bda02-183">Yes</span></span> |<span data-ttu-id="bda02-184">否</span><span class="sxs-lookup"><span data-stu-id="bda02-184">No</span></span> |
|<span data-ttu-id="bda02-185">多個應用程式 Kiosk</span><span class="sxs-lookup"><span data-stu-id="bda02-185">Multi-app kiosk</span></span> |<span data-ttu-id="bda02-186">Azure AD 帳戶</span><span class="sxs-lookup"><span data-stu-id="bda02-186">Azure AD account</span></span> |<span data-ttu-id="bda02-187">否</span><span class="sxs-lookup"><span data-stu-id="bda02-187">No</span></span> |<span data-ttu-id="bda02-188">是</span><span class="sxs-lookup"><span data-stu-id="bda02-188">Yes</span></span> |

<span data-ttu-id="bda02-189">有關如何使用這些功能的範例，請參閱下表。</span><span class="sxs-lookup"><span data-stu-id="bda02-189">For examples of how to use these capabilities, see the following table.</span></span>

|<span data-ttu-id="bda02-190">使用單一應用程式資訊站：</span><span class="sxs-lookup"><span data-stu-id="bda02-190">Use a single-app kiosk for:</span></span> |<span data-ttu-id="bda02-191">使用多應用程式資訊站：</span><span class="sxs-lookup"><span data-stu-id="bda02-191">Use a multi-app kiosk for:</span></span> |
| --- | --- |
|<span data-ttu-id="bda02-192">只為新員工執行 Dynamics 365 指南的裝置。</span><span class="sxs-lookup"><span data-stu-id="bda02-192">A device that runs only a Dynamics 365 Guide for new employees.</span></span> |<span data-ttu-id="bda02-193">為一系列員工同時執行指南和遠端協助的裝置。</span><span class="sxs-lookup"><span data-stu-id="bda02-193">A device that runs both Guides and Remote Assistance for a range of employees.</span></span> |
|<span data-ttu-id="bda02-194">只執行自訂應用程式的裝置。</span><span class="sxs-lookup"><span data-stu-id="bda02-194">A device that runs only a custom app.</span></span> |<span data-ttu-id="bda02-195">適用于大多數使用者的裝置， (只執行自訂應用程式) ，但可做為特定使用者群組的標準裝置。</span><span class="sxs-lookup"><span data-stu-id="bda02-195">A device that functions as a kiosk for most users (running only a custom app), but functions as a standard device for a specific group of users.</span></span> |

### <a name="plan-kiosk-apps"></a><span data-ttu-id="bda02-196">規劃資訊站應用程式</span><span class="sxs-lookup"><span data-stu-id="bda02-196">Plan kiosk apps</span></span>

<span data-ttu-id="bda02-197">若要瞭解如何選擇資訊站應用程式的一般資訊，請參閱在資訊站模式中選擇已指派存取 [ (指南 ](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)) 。</span><span class="sxs-lookup"><span data-stu-id="bda02-197">For general information about how to choose kiosk apps, see [Guidelines for choosing an app for assigned access (kiosk mode)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app).</span></span>

<span data-ttu-id="bda02-198">如果您使用 Windows 裝置入口網站來設定單一應用程式資訊站，請在設定程式期間選取應用程式。</span><span class="sxs-lookup"><span data-stu-id="bda02-198">If you use the Windows Device Portal to configure a single-app kiosk, you select the app during the setup process.</span></span>  

<span data-ttu-id="bda02-199">如果您使用行動裝置管理 (MDM) 系統或部署套件來設定資訊站模式，請使用 [AssignedAccess ](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) configuration Service provider (CSP) 來指定應用程式。</span><span class="sxs-lookup"><span data-stu-id="bda02-199">If you use a Mobile Device Management (MDM) system or a provisioning package to configure kiosk mode, you use the [AssignedAccess Configuration Service Provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) to specify applications.</span></span> <span data-ttu-id="bda02-200">CSP 會 [使用應用程式使用者模型 ID (AUMID) 識別 ](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 應用程式。</span><span class="sxs-lookup"><span data-stu-id="bda02-200">The CSP uses [Application User Model IDs (AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) to identify applications.</span></span> <span data-ttu-id="bda02-201">下表列出一些可在多應用程式資訊站使用的方塊內應用程式的 AUMID。</span><span class="sxs-lookup"><span data-stu-id="bda02-201">The following table lists the AUMIDs of some in-box applications that you can use in a multi-app kiosk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bda02-202">資訊站模式會決定當使用者登錄裝置時，哪些應用程式可以使用。</span><span class="sxs-lookup"><span data-stu-id="bda02-202">Kiosk mode determines which apps are available when a user signs in to the device.</span></span> <span data-ttu-id="bda02-203">不過，資訊站模式不是安全性方法。</span><span class="sxs-lookup"><span data-stu-id="bda02-203">However, kiosk mode is not a security method.</span></span> <span data-ttu-id="bda02-204">它不會停止「允許」應用程式開啟另一個不允許的應用程式。</span><span class="sxs-lookup"><span data-stu-id="bda02-204">It does not stop an "allowed" app from opening another app that is not allowed.</span></span> <span data-ttu-id="bda02-205">由於我們不限制此行為，因此應用程式仍可從 Edge、檔案檔案管理器和 Microsoft Store App 啟動。</span><span class="sxs-lookup"><span data-stu-id="bda02-205">Because we do not restrict this behavior, apps can still be launched from Edge, File explorer, and the Microsoft Store apps.</span></span> <span data-ttu-id="bda02-206">如果您不希望從資訊站啟動特定應用程式，請使用 Windows Defender 應用程式控制項 [# (WDAC](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)) 建立適當的策略。</span><span class="sxs-lookup"><span data-stu-id="bda02-206">If there are specific apps you don't want launched from a Kiosk, use [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) to create appropriate policies.</span></span> 
> 
> <span data-ttu-id="bda02-207">此外，混合實境首頁無法設定為資訊站應用程式。</span><span class="sxs-lookup"><span data-stu-id="bda02-207">In addition, the Mixed Reality Home is not able to be set as a kiosk app.</span></span>

<a id="aumids"></a>

|<span data-ttu-id="bda02-208">應用程式名稱</span><span class="sxs-lookup"><span data-stu-id="bda02-208">App Name</span></span> |<span data-ttu-id="bda02-209">AUMID</span><span class="sxs-lookup"><span data-stu-id="bda02-209">AUMID</span></span> |
| --- | --- |
|<span data-ttu-id="bda02-210">3D 檢視器</span><span class="sxs-lookup"><span data-stu-id="bda02-210">3D Viewer</span></span> |<span data-ttu-id="bda02-211">Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\！Microsoft.Microsoft3DViewer</span><span class="sxs-lookup"><span data-stu-id="bda02-211">Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\!Microsoft.Microsoft3DViewer</span></span> |
|<span data-ttu-id="bda02-212">行事曆</span><span class="sxs-lookup"><span data-stu-id="bda02-212">Calendar</span></span> |<span data-ttu-id="bda02-213">microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\！microsoft.windowslive.calendar</span><span class="sxs-lookup"><span data-stu-id="bda02-213">microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\!microsoft.windowslive.calendar</span></span> |
|<span data-ttu-id="bda02-214">相機 <sup> 1、2</span><span class="sxs-lookup"><span data-stu-id="bda02-214">Camera<sup>1, 2</span></span></sup> |<span data-ttu-id="bda02-215">HoloCamera\_cw5n1h2txyewy\！HoloCamera</span><span class="sxs-lookup"><span data-stu-id="bda02-215">HoloCamera\_cw5n1h2txyewy\!HoloCamera</span></span> |
|<span data-ttu-id="bda02-216">Cortana <sup> 3</span><span class="sxs-lookup"><span data-stu-id="bda02-216">Cortana<sup>3</span></span></sup> |<span data-ttu-id="bda02-217">Microsoft.549981C3F5F10\_8wekyb3d8bbwe\！應用程式</span><span class="sxs-lookup"><span data-stu-id="bda02-217">Microsoft.549981C3F5F10\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="bda02-218">HoloLens 上的裝置選擇器 (第一代) </span><span class="sxs-lookup"><span data-stu-id="bda02-218">Device Picker on HoloLens (1st gen)</span></span> |<span data-ttu-id="bda02-219">HoloDevicesFlow\_cw5n1h2txyewy\！HoloDevicesFlow</span><span class="sxs-lookup"><span data-stu-id="bda02-219">HoloDevicesFlow\_cw5n1h2txyewy\!HoloDevicesFlow</span></span> |
|<span data-ttu-id="bda02-220">HoloLens 2 上的裝置選擇器</span><span class="sxs-lookup"><span data-stu-id="bda02-220">Device Picker on HoloLens 2</span></span> |<span data-ttu-id="bda02-221">Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\！Microsoft.Windows.DevicesFlowHost</span><span class="sxs-lookup"><span data-stu-id="bda02-221">Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\!Microsoft.Windows.DevicesFlowHost</span></span> |
|<span data-ttu-id="bda02-222">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="bda02-222">Dynamics 365 Guides</span></span> |<span data-ttu-id="bda02-223">Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\！MicrosoftGuides</span><span class="sxs-lookup"><span data-stu-id="bda02-223">Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\!MicrosoftGuides</span></span> |
|<span data-ttu-id="bda02-224">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="bda02-224">Dynamics 365 Remote Assist</span></span> |<span data-ttu-id="bda02-225">Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\！Microsoft.RemoteAssist</span><span class="sxs-lookup"><span data-stu-id="bda02-225">Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\!Microsoft.RemoteAssist</span></span> |
|<span data-ttu-id="bda02-226">意見 &nbsp; 回饋中心</span><span class="sxs-lookup"><span data-stu-id="bda02-226">Feedback&nbsp;Hub</span></span> |<span data-ttu-id="bda02-227">Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\！應用程式</span><span class="sxs-lookup"><span data-stu-id="bda02-227">Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="bda02-228">檔案總管</span><span class="sxs-lookup"><span data-stu-id="bda02-228">File Explorer</span></span> |<span data-ttu-id="bda02-229">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span><span class="sxs-lookup"><span data-stu-id="bda02-229">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span></span> |
|<span data-ttu-id="bda02-230">Mail</span><span class="sxs-lookup"><span data-stu-id="bda02-230">Mail</span></span> |<span data-ttu-id="bda02-231">microsoft.windowscommunicationsapps_8wekyb3d8bbwe！microsoft.windowslive.mail</span><span class="sxs-lookup"><span data-stu-id="bda02-231">microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail</span></span> |
|<span data-ttu-id="bda02-232">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="bda02-232">Microsoft Edge</span></span> |<span data-ttu-id="bda02-233">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE</span><span class="sxs-lookup"><span data-stu-id="bda02-233">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE</span></span> |
|<span data-ttu-id="bda02-234">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="bda02-234">Microsoft Store</span></span> |<span data-ttu-id="bda02-235">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span><span class="sxs-lookup"><span data-stu-id="bda02-235">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span></span> |
|<span data-ttu-id="bda02-236">Miracast <sup> 4</span><span class="sxs-lookup"><span data-stu-id="bda02-236">Miracast<sup>4</span></span></sup> |&nbsp; |
|<span data-ttu-id="bda02-237">電影與電視</span><span class="sxs-lookup"><span data-stu-id="bda02-237">Movies & TV</span></span> |<span data-ttu-id="bda02-238">Microsoft.ZuneVideo\_8wekyb3d8bbwe\！Microsoft.ZuneVideo</span><span class="sxs-lookup"><span data-stu-id="bda02-238">Microsoft.ZuneVideo\_8wekyb3d8bbwe\!Microsoft.ZuneVideo</span></span> |
|<span data-ttu-id="bda02-239">OneDrive</span><span class="sxs-lookup"><span data-stu-id="bda02-239">OneDrive</span></span> |<span data-ttu-id="bda02-240">microsoft.microsoftskydrive\_8wekyb3d8bbwe\！應用程式</span><span class="sxs-lookup"><span data-stu-id="bda02-240">microsoft.microsoftskydrive\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="bda02-241">相片</span><span class="sxs-lookup"><span data-stu-id="bda02-241">Photos</span></span> |<span data-ttu-id="bda02-242">Microsoft.Windows.Photos\_8wekyb3d8bbwe\！應用程式</span><span class="sxs-lookup"><span data-stu-id="bda02-242">Microsoft.Windows.Photos\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="bda02-243">設定</span><span class="sxs-lookup"><span data-stu-id="bda02-243">Settings</span></span> |<span data-ttu-id="bda02-244">HolographicSystemSettings\_cw5n1h2txyewy\！應用程式</span><span class="sxs-lookup"><span data-stu-id="bda02-244">HolographicSystemSettings\_cw5n1h2txyewy\!App</span></span> |
|<span data-ttu-id="bda02-245">提示</span><span class="sxs-lookup"><span data-stu-id="bda02-245">Tips</span></span> |<span data-ttu-id="bda02-246">Microsoft.HoloLensTips\_8wekyb3d8bbwe\！HoloLensTips</span><span class="sxs-lookup"><span data-stu-id="bda02-246">Microsoft.HoloLensTips\_8wekyb3d8bbwe\!HoloLensTips</span></span> |

> <sup><span data-ttu-id="bda02-247">1 </sup> 若要啟用相片或視像捕獲，您必須將相機應用程式啟用為資訊站應用程式。</span><span class="sxs-lookup"><span data-stu-id="bda02-247">1</sup> To enable photo or video capture, you have to enable the Camera app as a kiosk app.</span></span>  
> <sup><span data-ttu-id="bda02-248">2 </sup> 當您啟用相機應用程式時，請注意下列條件：</span><span class="sxs-lookup"><span data-stu-id="bda02-248">2</sup> When you enable the Camera app, be aware of the following conditions:</span></span>
> - <span data-ttu-id="bda02-249">快速動作功能表包含相片和視像按鈕。</span><span class="sxs-lookup"><span data-stu-id="bda02-249">The Quick Actions menu includes the Photo and Video buttons.</span></span>  
> - <span data-ttu-id="bda02-250">您也應該啟用可與圖片 (相片、郵件或 OneDrive) 應用程式。</span><span class="sxs-lookup"><span data-stu-id="bda02-250">You should also enable an app (such as Photos, Mail, or OneDrive) that can interact with or retrieve pictures.</span></span>  
>  
> <sup><span data-ttu-id="bda02-251">3 即使您未將 Cortana 啟用為資訊站應用程式，內建 </sup> 的語音命令也已啟用。</span><span class="sxs-lookup"><span data-stu-id="bda02-251">3</sup> Even if you do not enable Cortana as a kiosk app, built-in voice commands are enabled.</span></span> <span data-ttu-id="bda02-252">不過，與停用功能相關的命令沒有作用。</span><span class="sxs-lookup"><span data-stu-id="bda02-252">However, commands that are related to disabled features have no effect.</span></span>  
> <sup><span data-ttu-id="bda02-253">4 </sup> 您無法直接啟用 Miracast。</span><span class="sxs-lookup"><span data-stu-id="bda02-253">4</sup> You cannot enable Miracast directly.</span></span> <span data-ttu-id="bda02-254">若要將 Miracast 啟用為資訊站應用程式，請啟用相機 App 和裝置選擇器應用程式。</span><span class="sxs-lookup"><span data-stu-id="bda02-254">To enable Miracast as a kiosk app enable the Camera app and the Device Picker app.</span></span>

### <a name="plan-kiosk-profiles-for-users-or-groups"></a><span data-ttu-id="bda02-255">針對使用者或群組規劃資訊站設定檔</span><span class="sxs-lookup"><span data-stu-id="bda02-255">Plan kiosk profiles for users or groups</span></span>

<span data-ttu-id="bda02-256">建立 xml 檔案或使用 Intune 的 UI 設定資訊站時，您必須考慮誰將使用 Kiosk。</span><span class="sxs-lookup"><span data-stu-id="bda02-256">When either creating the xml file or using Intune’s UI to set up a Kiosk you’ll need to consider who will be user the Kiosk.</span></span> <span data-ttu-id="bda02-257">資訊站組組只能用於個別帳戶或 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="bda02-257">A Kiosk configuration can be limited to either an individual account or Azure AD groups.</span></span> 

<span data-ttu-id="bda02-258">一般來說，使用者或使用者群組會啟用資訊站。</span><span class="sxs-lookup"><span data-stu-id="bda02-258">Typically Kiosks are enabled for either a user, or user group.</span></span> <span data-ttu-id="bda02-259">不過，如果您打算撰寫自己的 XML Kiosk，則您可能會想要考慮全域指派的 Access，其中無論身分識別，都會在裝置層級上應用 Kiosk。</span><span class="sxs-lookup"><span data-stu-id="bda02-259">However if you plan on writing your own XML Kiosk, then you may want to consider Global Assigned Access, in which the Kiosk is applied at the device level regardless of Identity.</span></span> <span data-ttu-id="bda02-260">如果這項功能吸引您， [請閱讀有關全域指派的 Access Kiosks 的更多資訊。](hololens-global-assigned-access-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="bda02-260">If this appeals to you [read more about Global Assigned Access Kiosks.](hololens-global-assigned-access-kiosk.md)</span></span>

#### <a name="if-you-are-creating-an-xml-file"></a><span data-ttu-id="bda02-261">如果您要建立 XML 檔案：</span><span class="sxs-lookup"><span data-stu-id="bda02-261">If you are creating an XML file:</span></span>
-   <span data-ttu-id="bda02-262">您許多人會建立多個 Kiosk 設定檔，並將每個設定檔指派給不同的使用者/群組。</span><span class="sxs-lookup"><span data-stu-id="bda02-262">You many create multiple Kiosk profiles, and assign each to different users/groups.</span></span> <span data-ttu-id="bda02-263">例如有許多應用程式的 Azure AD 群組資訊站，以及具有多個 App 資訊站且具有單一應用程式的訪客。</span><span class="sxs-lookup"><span data-stu-id="bda02-263">Such as a Kiosk for your Azure AD Group that has many apps, and a Visitor that has a multiple app kiosk with a singular app.</span></span>
-   <span data-ttu-id="bda02-264">您的資訊站組會稱為 **設定檔識別碼** ，且具有 GUID。</span><span class="sxs-lookup"><span data-stu-id="bda02-264">Your kiosk configuration will be called a **Profile Id** and have a GUID.</span></span>
-   <span data-ttu-id="bda02-265">您可以在設定檔區段指定使用者類型，並將相同的 GUID 用於 **DefaultProfile Id，** 以指派該設定檔。</span><span class="sxs-lookup"><span data-stu-id="bda02-265">You will assign that Profile in the configs section by specifying the user type and using the same GUID for the **DefaultProfile Id**.</span></span>
- <span data-ttu-id="bda02-266">您可以建立 XML 檔案，但仍透過 MDM 套用至裝置，方法為建立自訂 OMA URI 裝置組組設定檔，然後使用 URI 值將其套用至 HoloLens 裝置群組：./Device/Vendor/MSFT/AssignedAccess/Configuration</span><span class="sxs-lookup"><span data-stu-id="bda02-266">A XML file can be created but still applied to a device via MDM by creating a custom OMA URI device configuration profile and applying it to HoloLens device group using the URI value: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a><span data-ttu-id="bda02-267">如果您要在 Intune 中建立資訊站。</span><span class="sxs-lookup"><span data-stu-id="bda02-267">If you are creating a Kiosk in Intune.</span></span>
-   <span data-ttu-id="bda02-268">每個裝置只能收到單一的 Kiosk 設定檔，否則將會造成衝突，而且不會收到任何 Kiosk 組配置。</span><span class="sxs-lookup"><span data-stu-id="bda02-268">Each device may only receive a single Kiosk profile, otherwise it will create a conflict and receive no Kiosk configurations at all.</span></span> 
    -   <span data-ttu-id="bda02-269">其他類型的設定檔和策略 ，例如與資訊站組組設定檔不相關的裝置限制，不會與資訊站組組設定檔發生衝突。</span><span class="sxs-lookup"><span data-stu-id="bda02-269">Other kinds of profiles and policies, such as device restrictions that are not related to the kiosk configuration profile, do not conflict with the kiosk configuration profile.</span></span>
-   <span data-ttu-id="bda02-270">對於屬於使用者登入類型的所有使用者，將會啟用 Kiosk，此設定會以使用者或 Azure AD 群組設定。</span><span class="sxs-lookup"><span data-stu-id="bda02-270">The Kiosk will be enabled for all users who are a part of the User logon type, this will be set with a user or Azure AD group.</span></span> 
-   <span data-ttu-id="bda02-271">設定資訊站設定及使用者登入 **類型之後 (** 可以登入 Kiosk) 且已選取應用程式的使用者，則裝置設定仍必須指派給群組。</span><span class="sxs-lookup"><span data-stu-id="bda02-271">After the Kiosk configuration is set and the **User logon type** (users who can log into the Kiosk) and the Apps are selected, the Device Configuration must still be assigned to a group.</span></span> <span data-ttu-id="bda02-272">指派的群組 () 哪些裝置收到 Kiosk 裝置組，不過，如果已啟用或未啟用 Kiosk，則不會與它們互動。</span><span class="sxs-lookup"><span data-stu-id="bda02-272">The Assigned group(s) determines which devices receive the Kiosk device configuration, however does not interact with if the Kiosk is enabled or not.</span></span> 
    - <span data-ttu-id="bda02-273">有關在 Intune 中指派組組設定檔之效果的完整討論，請參閱 [在 Microsoft Intune 中指派使用者和裝置設定檔](https://docs.microsoft.com/intune/configuration/device-profile-assign)。</span><span class="sxs-lookup"><span data-stu-id="bda02-273">For a full discussion of the effects of assigning configuration profiles in Intune, see [Assign user and device profiles in Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).</span></span>

### <a name="select-a-deployment-method"></a><span data-ttu-id="bda02-274">選取部署方法</span><span class="sxs-lookup"><span data-stu-id="bda02-274">Select a deployment method</span></span>

<span data-ttu-id="bda02-275">您可以選取下列其中一種方法來部署資訊站組配置：</span><span class="sxs-lookup"><span data-stu-id="bda02-275">You can select one of the following methods to deploy kiosk configurations:</span></span>

- [<span data-ttu-id="bda02-276">Microsoft Intune 或其他行動裝置管理 (MDM) 服務</span><span class="sxs-lookup"><span data-stu-id="bda02-276">Microsoft Intune or other mobile device management (MDM) service</span></span>](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="bda02-277">佈建套件</span><span class="sxs-lookup"><span data-stu-id="bda02-277">Provisioning package</span></span>](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="bda02-278">Windows Device Portal</span><span class="sxs-lookup"><span data-stu-id="bda02-278">Windows Device Portal</span></span>](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > <span data-ttu-id="bda02-279">由於這個方法需要在裝置上啟用開發人員模式，因此建議您只使用它進行示範。</span><span class="sxs-lookup"><span data-stu-id="bda02-279">Because this method requires that Developer Mode be enabled on the device, we recommend that you use it only for demonstrations.</span></span>

<span data-ttu-id="bda02-280">下表列出每個部署方法的功能和優點。</span><span class="sxs-lookup"><span data-stu-id="bda02-280">The following table lists the capabilities and benefits of each of the deployment methods.</span></span>

| &nbsp; |<span data-ttu-id="bda02-281">使用 Windows 裝置入口網站進行部署</span><span class="sxs-lookup"><span data-stu-id="bda02-281">Deploy by using Windows Device Portal</span></span> |<span data-ttu-id="bda02-282">使用部署套件進行部署</span><span class="sxs-lookup"><span data-stu-id="bda02-282">Deploy by using a provisioning package</span></span> |<span data-ttu-id="bda02-283">使用 MDM 部署</span><span class="sxs-lookup"><span data-stu-id="bda02-283">Deploy by using MDM</span></span> |
| --------------------------- | ------------- | -------------------- | ---- |
|<span data-ttu-id="bda02-284">部署單一應用程式資訊站</span><span class="sxs-lookup"><span data-stu-id="bda02-284">Deploy single-app kiosks</span></span>   | <span data-ttu-id="bda02-285">是</span><span class="sxs-lookup"><span data-stu-id="bda02-285">Yes</span></span>           | <span data-ttu-id="bda02-286">是</span><span class="sxs-lookup"><span data-stu-id="bda02-286">Yes</span></span>                  | <span data-ttu-id="bda02-287">是</span><span class="sxs-lookup"><span data-stu-id="bda02-287">Yes</span></span>  |
|<span data-ttu-id="bda02-288">部署多應用程式資訊站</span><span class="sxs-lookup"><span data-stu-id="bda02-288">Deploy multi-app kiosks</span></span>    | <span data-ttu-id="bda02-289">否</span><span class="sxs-lookup"><span data-stu-id="bda02-289">No</span></span>            | <span data-ttu-id="bda02-290">是</span><span class="sxs-lookup"><span data-stu-id="bda02-290">Yes</span></span>                  | <span data-ttu-id="bda02-291">是</span><span class="sxs-lookup"><span data-stu-id="bda02-291">Yes</span></span>  |
|<span data-ttu-id="bda02-292">僅部署到本地裝置</span><span class="sxs-lookup"><span data-stu-id="bda02-292">Deploy to local devices only</span></span> | <span data-ttu-id="bda02-293">是</span><span class="sxs-lookup"><span data-stu-id="bda02-293">Yes</span></span>           | <span data-ttu-id="bda02-294">是</span><span class="sxs-lookup"><span data-stu-id="bda02-294">Yes</span></span>                  | <span data-ttu-id="bda02-295">否</span><span class="sxs-lookup"><span data-stu-id="bda02-295">No</span></span>   |
|<span data-ttu-id="bda02-296">使用開發人員模式進行部署</span><span class="sxs-lookup"><span data-stu-id="bda02-296">Deploy by using Developer Mode</span></span> |<span data-ttu-id="bda02-297">必要</span><span class="sxs-lookup"><span data-stu-id="bda02-297">Required</span></span>       | <span data-ttu-id="bda02-298">不需要</span><span class="sxs-lookup"><span data-stu-id="bda02-298">Not required</span></span>            | <span data-ttu-id="bda02-299">不需要</span><span class="sxs-lookup"><span data-stu-id="bda02-299">Not required</span></span>   |
|<span data-ttu-id="bda02-300">使用 Azure Active Directory (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="bda02-300">Deploy by using Azure Active Directory (Azure AD)</span></span>  | <span data-ttu-id="bda02-301">不需要</span><span class="sxs-lookup"><span data-stu-id="bda02-301">Not required</span></span>            | <span data-ttu-id="bda02-302">不需要</span><span class="sxs-lookup"><span data-stu-id="bda02-302">Not required</span></span>                   | <span data-ttu-id="bda02-303">必要</span><span class="sxs-lookup"><span data-stu-id="bda02-303">Required</span></span>  |
|<span data-ttu-id="bda02-304">自動部署</span><span class="sxs-lookup"><span data-stu-id="bda02-304">Deploy automatically</span></span>      | <span data-ttu-id="bda02-305">否</span><span class="sxs-lookup"><span data-stu-id="bda02-305">No</span></span>            | <span data-ttu-id="bda02-306">否</span><span class="sxs-lookup"><span data-stu-id="bda02-306">No</span></span>                   | <span data-ttu-id="bda02-307">是</span><span class="sxs-lookup"><span data-stu-id="bda02-307">Yes</span></span>  |
|<span data-ttu-id="bda02-308">部署速度</span><span class="sxs-lookup"><span data-stu-id="bda02-308">Deployment speed</span></span>            | <span data-ttu-id="bda02-309">快速</span><span class="sxs-lookup"><span data-stu-id="bda02-309">Fast</span></span>       | <span data-ttu-id="bda02-310">快速</span><span class="sxs-lookup"><span data-stu-id="bda02-310">Fast</span></span>                 | <span data-ttu-id="bda02-311">慢速</span><span class="sxs-lookup"><span data-stu-id="bda02-311">Slow</span></span> |
|<span data-ttu-id="bda02-312">大規模部署</span><span class="sxs-lookup"><span data-stu-id="bda02-312">Deploy at scale</span></span> | <span data-ttu-id="bda02-313">不建議使用</span><span class="sxs-lookup"><span data-stu-id="bda02-313">Not recommended</span></span>    | <span data-ttu-id="bda02-314">建議執行</span><span class="sxs-lookup"><span data-stu-id="bda02-314">Recommended</span></span>        | <span data-ttu-id="bda02-315">建議執行</span><span class="sxs-lookup"><span data-stu-id="bda02-315">Recommended</span></span> |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a><span data-ttu-id="bda02-316">使用 Microsoft Intune 或其他 MDM 來設定單一應用程式或多應用程式資訊站</span><span class="sxs-lookup"><span data-stu-id="bda02-316">Use Microsoft Intune or other MDM to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="bda02-317">若要使用 Microsoft Intune 或其他 MDM 系統設定資訊站模式，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="bda02-317">To set up kiosk mode by using Microsoft Intune or another MDM system, follow these steps.</span></span>

1. <span data-ttu-id="bda02-318">[準備註冊裝置](#mdmenroll)。</span><span class="sxs-lookup"><span data-stu-id="bda02-318">[Prepare to enroll the devices](#mdmenroll).</span></span>
1. <span data-ttu-id="bda02-319">[建立資訊站組組設定檔](#mdmprofile)。</span><span class="sxs-lookup"><span data-stu-id="bda02-319">[Create a kiosk configuration profile](#mdmprofile).</span></span>
1. <span data-ttu-id="bda02-320">設定資訊站。</span><span class="sxs-lookup"><span data-stu-id="bda02-320">Configure the kiosk.</span></span>
   - <span data-ttu-id="bda02-321">[設定單一應用程式資訊站的設定](#mdmconfigsingle)。</span><span class="sxs-lookup"><span data-stu-id="bda02-321">[Configure the settings for a single-app kiosk](#mdmconfigsingle).</span></span>
   - <span data-ttu-id="bda02-322">[設定多應用程式資訊站的設定](#mdmconfigmulti)。</span><span class="sxs-lookup"><span data-stu-id="bda02-322">[Configure the settings for a multi-app kiosk](#mdmconfigmulti).</span></span>
1. <span data-ttu-id="bda02-323">[將資訊站組組設定檔指派給群組](#mdmassign)。</span><span class="sxs-lookup"><span data-stu-id="bda02-323">[Assign the kiosk configuration profile to a group](#mdmassign).</span></span>
1. <span data-ttu-id="bda02-324">部署裝置。</span><span class="sxs-lookup"><span data-stu-id="bda02-324">Deploy the devices.</span></span>
   - <span data-ttu-id="bda02-325">[部署單一應用程式資訊站](#mdmsingledeploy)。</span><span class="sxs-lookup"><span data-stu-id="bda02-325">[Deploy a single-app kiosk](#mdmsingledeploy).</span></span>
   - <span data-ttu-id="bda02-326">[部署多應用程式資訊站](#mdmmultideploy)。</span><span class="sxs-lookup"><span data-stu-id="bda02-326">[Deploy a multi-app kiosk](#mdmmultideploy).</span></span>

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a><span data-ttu-id="bda02-327">MDM，步驟 1 &ndash; 準備註冊裝置</span><span class="sxs-lookup"><span data-stu-id="bda02-327">MDM, step 1 &ndash; Prepare to enroll the devices</span></span>

<span data-ttu-id="bda02-328">您可以將 MDM 系統設定為在使用者第一次登錄時自動註冊 HoloLens 裝置，或讓使用者手動註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="bda02-328">You can configure your MDM system to enroll HoloLens devices automatically when the user first signs in, or have users enroll devices manually.</span></span> <span data-ttu-id="bda02-329">裝置還必須加入您的 Azure AD 網域，並指派給適當的群組。</span><span class="sxs-lookup"><span data-stu-id="bda02-329">The devices also have to be joined to your Azure AD domain, and assigned to the appropriate groups.</span></span>

<span data-ttu-id="bda02-330">若要瞭解如何註冊裝置，請參閱在 MDM 中註冊 [HoloLens](hololens-enroll-mdm.md) 和 Windows 裝置 [Intune 註冊方法](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)。</span><span class="sxs-lookup"><span data-stu-id="bda02-330">For more information about how to enroll the devices, see [Enroll HoloLens in MDM](hololens-enroll-mdm.md) and [Intune enrollment methods for Windows devices](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods).</span></span>

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a><span data-ttu-id="bda02-331">MDM，步驟 2 &ndash; 建立資訊站組組設定檔</span><span class="sxs-lookup"><span data-stu-id="bda02-331">MDM, step 2 &ndash; Create a kiosk configuration profile</span></span>

1. <span data-ttu-id="bda02-332">開啟 [Azure 入口](https://portal.azure.com/) 網站並登錄您的 Intune 系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="bda02-332">Open the [Azure](https://portal.azure.com/) portal and sign in to your Intune administrator account.</span></span>
1. <span data-ttu-id="bda02-333">選取**Microsoft Intune**  >  **裝置組調 - 設定檔**  >  **建立設定檔**。</span><span class="sxs-lookup"><span data-stu-id="bda02-333">Select **Microsoft Intune** > **Device configuration - Profiles** > **Create profile**.</span></span>
1. <span data-ttu-id="bda02-334">輸入設定檔名稱。</span><span class="sxs-lookup"><span data-stu-id="bda02-334">Enter a profile name.</span></span>
1. <span data-ttu-id="bda02-335">選取**平臺**  >  **Windows 10 及更新**版本，然後選取設定檔**類型**  > **裝置限制**。</span><span class="sxs-lookup"><span data-stu-id="bda02-335">Select **Platform** > **Windows 10 and later**, and then select **Profile type** >**Device restrictions**.</span></span>
1. <span data-ttu-id="bda02-336">選取**設定**  >  **資訊**站，然後選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bda02-336">Select **Configure** > **Kiosk**, and then select one of the following:</span></span>
   - <span data-ttu-id="bda02-337">若要建立單一應用程式資訊站，請**選取 Kiosk 模式**  >  **單一應用程式資訊站**。</span><span class="sxs-lookup"><span data-stu-id="bda02-337">To create a single-app kiosk, select **Kiosk Mode** > **Single-app kiosk**.</span></span>
   - <span data-ttu-id="bda02-338">若要建立多應用程式資訊站，請**選取 Kiosk 模式**  >  **多重應用程式資訊站**。</span><span class="sxs-lookup"><span data-stu-id="bda02-338">To create a multi-app kiosk, select **Kiosk Mode** > **Multi-app kiosk**.</span></span>
1. <span data-ttu-id="bda02-339">若要開始配置資訊站， **請選取**新增 。</span><span class="sxs-lookup"><span data-stu-id="bda02-339">To start configuring the kiosk, select **Add**.</span></span>

<span data-ttu-id="bda02-340">您的下一個步驟會視您想要的網亭類型而不同。</span><span class="sxs-lookup"><span data-stu-id="bda02-340">Your next steps differ depending on the type of kiosk that you want.</span></span> <span data-ttu-id="bda02-341">詳細資訊，請選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="bda02-341">For more information, select one of the following options:</span></span>  

- [<span data-ttu-id="bda02-342">單一應用程式資訊站</span><span class="sxs-lookup"><span data-stu-id="bda02-342">Single-app kiosk</span></span>](#mdmconfigsingle)
- [<span data-ttu-id="bda02-343">多個應用程式 Kiosk</span><span class="sxs-lookup"><span data-stu-id="bda02-343">Multi-app kiosk</span></span>](#mdmconfigmulti)

<span data-ttu-id="bda02-344">若要瞭解如何建立資訊站設定設定檔，請參閱 [Windows 10](https://docs.microsoft.com/intune/configuration/kiosk-settings)和商務用 Windows Holographic 裝置設定，以使用 Intune 作為專用資訊站執行。</span><span class="sxs-lookup"><span data-stu-id="bda02-344">For more information about how to create a kiosk configuration profile, see [Windows 10 and Windows Holographic for Business device settings to run as a dedicated kiosk using Intune](https://docs.microsoft.com/intune/configuration/kiosk-settings).</span></span>

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a><span data-ttu-id="bda02-345">MDM，步驟 3 (單一應用程式) 設定單一應用程式資訊站 &ndash;  的設定</span><span class="sxs-lookup"><span data-stu-id="bda02-345">MDM, step 3 (single-app) &ndash;  Configure the settings for a single-app kiosk</span></span>

<span data-ttu-id="bda02-346">本節摘要說明單一應用程式資訊站所需的設定。</span><span class="sxs-lookup"><span data-stu-id="bda02-346">This section summarizes the settings that a single-app kiosk requires.</span></span> <span data-ttu-id="bda02-347">有關詳細資料，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="bda02-347">For more details, see the following articles:</span></span>

- <span data-ttu-id="bda02-348">若要瞭解如何在 Intune 中設定資訊站設定設定檔，請參閱如何使用 [Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)設定 Kiosk 模式。</span><span class="sxs-lookup"><span data-stu-id="bda02-348">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="bda02-349">有關 Intune 中單一應用程式資訊站可用設定的資訊，請參閱 [單一全螢幕應用程式資訊站](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)</span><span class="sxs-lookup"><span data-stu-id="bda02-349">For more information about the available settings for single-app kiosks in Intune, see [Single full-screen app kiosks](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)</span></span>
- <span data-ttu-id="bda02-350">如需其他 MDM 服務，請參閱提供者文件中的指示。</span><span class="sxs-lookup"><span data-stu-id="bda02-350">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="bda02-351">如果您必須使用自訂 XML 設定來設定 MDM 服務中的資訊站，請建立定義資訊站設定的 [XML 檔案](#ppkioskconfig)。</span><span class="sxs-lookup"><span data-stu-id="bda02-351">If you have to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span>

1. <span data-ttu-id="bda02-352">選取**使用者登入類型**：Local 使用者帳戶，然後輸入可登入資訊站的 (裝置) 帳戶或  >  \*\* \*\*Microsoft 帳戶 (MSA) 的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="bda02-352">Select **User logon type** > **Local user account**, and then enter the user name of the local (device) account or Microsoft Account (MSA) that can sign in to the kiosk.</span></span>
   > [!NOTE]  
   > <span data-ttu-id="bda02-353">**商務用** Windows Holographic 不支援自動登入使用者帳戶類型。</span><span class="sxs-lookup"><span data-stu-id="bda02-353">**Autologon** user account types aren't supported on Windows Holographic for Business.</span></span>
1. <span data-ttu-id="bda02-354">選取**應用程式類型**  >  **Store App，** 然後從清單中選取應用程式。</span><span class="sxs-lookup"><span data-stu-id="bda02-354">Select **Application type** > **Store app**, and then select an app from the list.</span></span>

<span data-ttu-id="bda02-355">下一個步驟是 [將設定檔](#mdmassign) 指派給群組。</span><span class="sxs-lookup"><span data-stu-id="bda02-355">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a><span data-ttu-id="bda02-356">MDM、步驟 3 (應用程式) 設定多應用程式資訊站 &ndash; 的設定</span><span class="sxs-lookup"><span data-stu-id="bda02-356">MDM, step 3 (multi-app) &ndash; Configure the settings for a multi-app kiosk</span></span>

<span data-ttu-id="bda02-357">本節摘要說明多應用程式資訊站所需的設定。</span><span class="sxs-lookup"><span data-stu-id="bda02-357">This section summarizes the settings that a multi-app kiosk requires.</span></span> <span data-ttu-id="bda02-358">有關詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="bda02-358">For more detailed information, see the following articles:</span></span>

- <span data-ttu-id="bda02-359">若要瞭解如何在 Intune 中設定資訊站設定設定檔，請參閱如何使用 [Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)設定 Kiosk 模式。</span><span class="sxs-lookup"><span data-stu-id="bda02-359">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="bda02-360">有關 Intune 中多應用程式資訊站可用設定的資訊，請參閱 [多應用程式資訊站](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)</span><span class="sxs-lookup"><span data-stu-id="bda02-360">For more information about the available settings for multi-app kiosks in Intune, see [Multi-app kiosks](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)</span></span>
- <span data-ttu-id="bda02-361">如需其他 MDM 服務，請參閱提供者文件中的指示。</span><span class="sxs-lookup"><span data-stu-id="bda02-361">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="bda02-362">如果您需要使用自訂 XML 設定來設定 MDM 服務中的資訊站，請建立 [定義](#ppkioskconfig)資訊站設定的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="bda02-362">If you need to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span> <span data-ttu-id="bda02-363">如果您使用 XML 檔案，請務必包含開始 [版面配置](#start-layout-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="bda02-363">If you use an XML file, make sure to include the [Start layout](#start-layout-for-hololens).</span></span>  
- <span data-ttu-id="bda02-364">您可以選擇使用自訂的開始版面配置與 Intune 或其他 MDM 服務。</span><span class="sxs-lookup"><span data-stu-id="bda02-364">You can optionally use a custom Start layout with Intune or other MDM services.</span></span> <span data-ttu-id="bda02-365">詳細資訊，請參閱開始為 MDM ([Intune 和其他) 。](#start-layout-file-for-mdm-intune-and-others)</span><span class="sxs-lookup"><span data-stu-id="bda02-365">For more information, see [Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

1. <span data-ttu-id="bda02-366">選取**S 模式裝置中的目標 Windows 10**  >  **否**。</span><span class="sxs-lookup"><span data-stu-id="bda02-366">Select **Target Windows 10 in S mode devices** > **No**.</span></span>  
   >[!NOTE]  
   > <span data-ttu-id="bda02-367">商務用 Windows Holographic 不支援 S 模式。</span><span class="sxs-lookup"><span data-stu-id="bda02-367">S mode isn't supported on Windows Holographic for Business.</span></span>
1. <span data-ttu-id="bda02-368">選取**使用者登入類型**  >  **Azure AD 使用者或群組**或**使用者登**入類型  >  **HoloLens 訪客**，然後新增一或多個使用者群組或帳戶。</span><span class="sxs-lookup"><span data-stu-id="bda02-368">Select **User logon type** > **Azure AD user or group** or **User logon type** > **HoloLens visitor**, and then add one or more user groups or accounts.</span></span>  

   <span data-ttu-id="bda02-369">只有屬於您于使用者登入類型中指定的群組或帳戶 **的使用者** ，才能使用資訊站體驗。</span><span class="sxs-lookup"><span data-stu-id="bda02-369">Only users who belong to the groups or accounts that you specify in **User logon type** can use the kiosk experience.</span></span>

1. <span data-ttu-id="bda02-370">使用下列選項選取一或多個應用程式：</span><span class="sxs-lookup"><span data-stu-id="bda02-370">Select one or more apps by using the following options:</span></span>
   - <span data-ttu-id="bda02-371">若要新增已上傳的企業經營應用程式，請選取新增 **市** 售應用程式，然後選取您想要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="bda02-371">To add an uploaded line-of-business app, select **Add store app** and then select the app that you want.</span></span>
   - <span data-ttu-id="bda02-372">若要指定 App 的 AUMID 來新增應用程式，請選取 **AUMID** 新增，然後輸入應用程式的 AUMID。</span><span class="sxs-lookup"><span data-stu-id="bda02-372">To add an app by specifying its AUMID, select **Add by AUMID** and then enter the AUMID of the app.</span></span> [<span data-ttu-id="bda02-373">查看可用的 AUMID 清單</span><span class="sxs-lookup"><span data-stu-id="bda02-373">See the list of available AUMIDs</span></span>](#aumids)

<span data-ttu-id="bda02-374">下一個步驟是 [將設定檔](#mdmassign) 指派給群組。</span><span class="sxs-lookup"><span data-stu-id="bda02-374">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a><span data-ttu-id="bda02-375">MDM，步驟 4 &ndash; 將資訊站組組設定檔指派給群組</span><span class="sxs-lookup"><span data-stu-id="bda02-375">MDM, step 4 &ndash; Assign the kiosk configuration profile to a group</span></span>

<span data-ttu-id="bda02-376">使用 **資訊** 站設定設定檔的作業頁面來設定要部署資訊站設定的地方。</span><span class="sxs-lookup"><span data-stu-id="bda02-376">Use the **Assignments** page of the kiosk configuration profile to set where you want the kiosk configuration to deploy.</span></span> <span data-ttu-id="bda02-377">在最簡單的情況下，您將資訊站組組設定檔指派給一個群組，當裝置註冊 MDM 時，該群組會包含 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="bda02-377">In the simplest case, you assign the kiosk configuration profile to a group that will contain the HoloLens device when the device enrolls in MDM.</span></span>

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a><span data-ttu-id="bda02-378">MDM、步驟 5 (單一應用程式) &ndash; 部署單一應用程式資訊站</span><span class="sxs-lookup"><span data-stu-id="bda02-378">MDM, step 5 (single-app) &ndash; Deploy a single-app kiosk</span></span>

<span data-ttu-id="bda02-379">當您使用 MDM 系統時，您可以在 OOBE 期間在 MDM 中註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="bda02-379">When you use an MDM system, you can enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="bda02-380">OOBE 完成之後，輕鬆登錄裝置。</span><span class="sxs-lookup"><span data-stu-id="bda02-380">After OOBE finishes, signing in to the device is easy.</span></span>

<span data-ttu-id="bda02-381">在 OOBE 期間，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="bda02-381">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="bda02-382">使用您于資訊站設定檔中指定的帳號來登錄。</span><span class="sxs-lookup"><span data-stu-id="bda02-382">Sign in by using the account that you specified in the kiosk configuration profile.</span></span>
1. <span data-ttu-id="bda02-383">註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="bda02-383">Enroll the device.</span></span> <span data-ttu-id="bda02-384">請確定裝置已新加入資訊站組設定檔指派的群組中。</span><span class="sxs-lookup"><span data-stu-id="bda02-384">Make sure that the device is added to the group that the kiosk configuration profile is assigned to.</span></span>
1. <span data-ttu-id="bda02-385">請等候 OOBE 完成、儲存區 App 下載及安裝，以及要適用原則。</span><span class="sxs-lookup"><span data-stu-id="bda02-385">Wait for OOBE to finish, for the store app to download and install, and for policies to be applied.</span></span> <span data-ttu-id="bda02-386">然後重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="bda02-386">Then restart the device.</span></span>

<span data-ttu-id="bda02-387">下次您登錄裝置時，資訊站應用程式應該會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="bda02-387">The next time you sign in to the device, the kiosk app should automatically start.</span></span>

<span data-ttu-id="bda02-388">如果您此時沒看到您的資訊站組組， [請檢查作業狀態](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。</span><span class="sxs-lookup"><span data-stu-id="bda02-388">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a><span data-ttu-id="bda02-389">MDM，步驟 5 (部署多) &ndash; 應用程式資訊站</span><span class="sxs-lookup"><span data-stu-id="bda02-389">MDM, step 5 (multi-app) &ndash; Deploy a multi-app kiosk</span></span>

<span data-ttu-id="bda02-390">當您使用 MDM 系統時，您可以在 OOBE 期間將裝置加入 Azure AD 租使用者，並註冊 MDM 中的裝置。</span><span class="sxs-lookup"><span data-stu-id="bda02-390">When you use an MDM system, you can join the device to your Azure AD tenant and enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="bda02-391">如果適用，請提供註冊資訊給使用者，讓使用者在 OOBE 程式期間能夠使用。</span><span class="sxs-lookup"><span data-stu-id="bda02-391">If appropriate, provide the enrollment information to the users so that they have it available during the OOBE process.</span></span>

> [!NOTE]  
> <span data-ttu-id="bda02-392">如果您已經將資訊站組組設定檔指派給包含使用者的群組，請確定其中一個使用者帳戶是第一個要登錄裝置的帳戶。</span><span class="sxs-lookup"><span data-stu-id="bda02-392">If you have assigned the kiosk configuration profile to a group that contains users, make sure that one of those user accounts is the first account to sign in to the device.</span></span>

<span data-ttu-id="bda02-393">在 OOBE 期間，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="bda02-393">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="bda02-394">使用屬於使用者登入類型群組 **的帳戶登** 入。</span><span class="sxs-lookup"><span data-stu-id="bda02-394">Sign in by using the account that belongs to the **User logon type** group.</span></span>
1. <span data-ttu-id="bda02-395">註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="bda02-395">Enroll the device.</span></span>
1. <span data-ttu-id="bda02-396">等待任何屬於資訊站組配置設定檔的 App 下載並安裝。</span><span class="sxs-lookup"><span data-stu-id="bda02-396">Wait for any apps that are part of the kiosk configuration profile to download and install.</span></span> <span data-ttu-id="bda02-397">此外，請等候原則的適用。</span><span class="sxs-lookup"><span data-stu-id="bda02-397">Also, wait for policies to be applied.</span></span>  
1. <span data-ttu-id="bda02-398">OOBE 完成之後，您可以安裝 Microsoft Store 或並排載入的其他應用程式。</span><span class="sxs-lookup"><span data-stu-id="bda02-398">After OOBE finishes, you can install additional apps from the Microsoft store or by sideloading.</span></span> <span data-ttu-id="bda02-399">[裝置所屬](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) 群組的必填應用程式會自動安裝。</span><span class="sxs-lookup"><span data-stu-id="bda02-399">[Required apps](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) for the group that the device belongs to install automatically.</span></span>
1. <span data-ttu-id="bda02-400">安裝完成後，重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="bda02-400">After the installation finishes, restart the device.</span></span>

<span data-ttu-id="bda02-401">下次使用屬於使用者登入類型的帳戶登入裝置時，資訊站應用程式應該\*\*\*\* 會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="bda02-401">The next time you sign in to the device by using an account that belongs to the **User logon type**, the kiosk app should automatically launch.</span></span>

<span data-ttu-id="bda02-402">如果您此時沒看到您的資訊站組組， [請檢查作業狀態](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。</span><span class="sxs-lookup"><span data-stu-id="bda02-402">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a><span data-ttu-id="bda02-403">使用設定套件來設定單一應用程式或多應用程式資訊站</span><span class="sxs-lookup"><span data-stu-id="bda02-403">Use a provisioning package to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="bda02-404">若要使用設定套件來設定資訊站模式，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="bda02-404">To set up kiosk mode by using a provisioning package, follow these steps.</span></span>

1. <span data-ttu-id="bda02-405">[建立定義資訊站配置的 XML 檔案。，](#ppkioskconfig)包括開始 [版面配置](#start-layout-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="bda02-405">[Create an XML file that defines the kiosk configuration.](#ppkioskconfig), including a [Start layout](#start-layout-for-hololens).</span></span>
2. [<span data-ttu-id="bda02-406">將 XML 檔案新增到資源調配套件。</span><span class="sxs-lookup"><span data-stu-id="bda02-406">Add the XML file to a provisioning package.</span></span>](#ppconfigadd)
3. [<span data-ttu-id="bda02-407">將部署套件套用至 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="bda02-407">Apply the provisioning package to HoloLens.</span></span>](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a><span data-ttu-id="bda02-408">部署套件，步驟 1 &ndash; 建立資訊站組組 XML 檔案</span><span class="sxs-lookup"><span data-stu-id="bda02-408">Provisioning package, step 1 &ndash; Create a kiosk configuration XML file</span></span>

<span data-ttu-id="bda02-409">請 [遵循一般指示，為 Windows](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)桌面建立資訊站組組 XML 檔案，但下列專案除外：</span><span class="sxs-lookup"><span data-stu-id="bda02-409">Follow [the general instructions to create a kiosk configuration XML file for Windows desktop](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file), except for the following:</span></span>

- <span data-ttu-id="bda02-410">請勿將傳統 Windows 應用程式 (Win32) 。</span><span class="sxs-lookup"><span data-stu-id="bda02-410">Do not include Classic Windows applications (Win32).</span></span> <span data-ttu-id="bda02-411">HoloLens 不支援這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="bda02-411">HoloLens does not support these applications.</span></span>
- <span data-ttu-id="bda02-412">使用 [HoloLens](#start-layout-for-hololens) 的預留位置開始版面配置 XML。</span><span class="sxs-lookup"><span data-stu-id="bda02-412">Use the [placeholder Start layout XML](#start-layout-for-hololens) for HoloLens.</span></span>
- <span data-ttu-id="bda02-413">選擇性：新增來賓存取訊號站組</span><span class="sxs-lookup"><span data-stu-id="bda02-413">Optional: Add guest access to the kiosk configuration</span></span>

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a><span data-ttu-id="bda02-414">選擇性：新增來賓存取訊號站組</span><span class="sxs-lookup"><span data-stu-id="bda02-414">Optional: Add guest access to the kiosk configuration</span></span>

<span data-ttu-id="bda02-415">在[**XML 檔案的 Configs**](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)區段，您可以設定名為**訪客**的特殊群組，以允許來賓使用資訊站。</span><span class="sxs-lookup"><span data-stu-id="bda02-415">In the [**Configs** section of the XML file](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs), you can configure a special group named **Visitor** to allow guests to use the kiosk.</span></span> <span data-ttu-id="bda02-416">當資訊站已配置為支援 **訪客特殊群組** 時，會**新增「來賓**」選項至登錄頁面。</span><span class="sxs-lookup"><span data-stu-id="bda02-416">When the kiosk is configured to support the **Visitor** special group, a "**Guest**" option is added to the sign-in page.</span></span> <span data-ttu-id="bda02-417">**來賓**帳戶不需要密碼，當帳戶退出時，會刪除與該帳戶相關聯的任何資料。</span><span class="sxs-lookup"><span data-stu-id="bda02-417">The **Guest** account does not require a password, and any data that is associated with the account is deleted when the account signs out.</span></span>

<span data-ttu-id="bda02-418">若要啟用 **來賓帳戶** ，請新增下列程式碼片段至您的資訊站組組 XML：</span><span class="sxs-lookup"><span data-stu-id="bda02-418">To enable the **Guest** account, add the following snippet to your kiosk configuration XML:</span></span>

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a><span data-ttu-id="bda02-419">HoloLens 的預留位置開始版面配置</span><span class="sxs-lookup"><span data-stu-id="bda02-419">Placeholder Start layout for HoloLens</span></span>

<span data-ttu-id="bda02-420">如果您使用 [設定套件來](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 設定多應用程式資訊站，程式需要開始版面配置。</span><span class="sxs-lookup"><span data-stu-id="bda02-420">If you use a [provisioning package](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) to configure a multi-app kiosk, the procedure requires a Start layout.</span></span> <span data-ttu-id="bda02-421">商務用 Windows Holographic 不支援開始版面配置自訂。</span><span class="sxs-lookup"><span data-stu-id="bda02-421">Start layout customization isn't supported in Windows Holographic for Business.</span></span> <span data-ttu-id="bda02-422">因此，您必須使用預留位置開始版面配置。</span><span class="sxs-lookup"><span data-stu-id="bda02-422">Therefore, you'll have to use a placeholder Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="bda02-423">由於單一應用程式資訊站在使用者登錄時會啟動資訊站應用程式，因此它不使用開始功能表，也不需要有開始版面配置。</span><span class="sxs-lookup"><span data-stu-id="bda02-423">Because a single-app kiosk starts the kiosk app when a user signs in, it does not use a Start menu and does not have to have a Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="bda02-424">如果您使用 [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 設定多應用程式資訊站，您可以選擇使用開始版面配置。</span><span class="sxs-lookup"><span data-stu-id="bda02-424">If you use [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) to set up a multi-app kiosk, you can optionally use a Start layout.</span></span> <span data-ttu-id="bda02-425">詳細資訊，請參閱適用于 Intune 和其他應用程式之 MDM ([預留位置開始版面配置) 。](#start-layout-file-for-mdm-intune-and-others)</span><span class="sxs-lookup"><span data-stu-id="bda02-425">For more information, see [Placeholder Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

<span data-ttu-id="bda02-426">針對開始版面配置，將下列 **StartLayout 區** 段新增到資訊站置備 XML 檔案：</span><span class="sxs-lookup"><span data-stu-id="bda02-426">For the Start layout, add the following **StartLayout** section to the kiosk provisioning XML file:</span></span>

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

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a><span data-ttu-id="bda02-427">適用于 Intune 和其他使用者之 MDM (版面配置檔案) </span><span class="sxs-lookup"><span data-stu-id="bda02-427">Placeholder Start layout file for MDM (Intune and others)</span></span>

<span data-ttu-id="bda02-428">將下列範例儲存為 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="bda02-428">Save the following sample as an XML file.</span></span> <span data-ttu-id="bda02-429">當您在 Microsoft Intune 中設定多應用程式資訊站或提供資訊站設定檔 (另一個 MDM 服務中，您可以使用這個) 。</span><span class="sxs-lookup"><span data-stu-id="bda02-429">You can use this file when you configure the multi-app kiosk in Microsoft Intune (or in another MDM service that provides a kiosk profile).</span></span>

> [!NOTE]
> <span data-ttu-id="bda02-430">如果您必須使用自訂設定和完整 XML 設定來設定 MDM 服務中的資訊站，請使用部署套件的開始版面 [配置指示](#start-layout-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="bda02-430">If you have to use a custom setting and full XML configuration to set up a kiosk in your MDM service, use the [Start layout instructions for a provisioning package](#start-layout-for-hololens).</span></span>

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

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a><span data-ttu-id="bda02-431">箴。</span><span class="sxs-lookup"><span data-stu-id="bda02-431">Prov.</span></span> <span data-ttu-id="bda02-432">套件，步驟 2 &ndash; 新增資訊站組組 XML 檔案至置備套件</span><span class="sxs-lookup"><span data-stu-id="bda02-432">package, step 2 &ndash; Add the kiosk configuration XML file to a provisioning package</span></span>

1. <span data-ttu-id="bda02-433">開啟 [Windows 組組設計工具](https://www.microsoft.com/store/apps/9nblggh4tx22)。</span><span class="sxs-lookup"><span data-stu-id="bda02-433">Open [Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22).</span></span>
1. <span data-ttu-id="bda02-434">選取 **進位置備**，輸入專案的名稱，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="bda02-434">Select **Advanced provisioning**, enter a name for your project, and then select **Next**.</span></span>
1. <span data-ttu-id="bda02-435">選取 **Windows 10 全圖**，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="bda02-435">Select **Windows 10 Holographic**, and then select **Next**.</span></span>
1. <span data-ttu-id="bda02-436">選取 **完成**。</span><span class="sxs-lookup"><span data-stu-id="bda02-436">Select **Finish**.</span></span> <span data-ttu-id="bda02-437">套件的工作區就會開啟。</span><span class="sxs-lookup"><span data-stu-id="bda02-437">The workspace for your package opens.</span></span>
1. <span data-ttu-id="bda02-438">選取**執行時間設定**  >  **AssignedAccesss**  >  **MultiAppgnedAccesSettings**。</span><span class="sxs-lookup"><span data-stu-id="bda02-438">Select **Runtime settings** > **AssignedAccess** > **MultiAppAssignedAccessSettings**.</span></span>
1. <span data-ttu-id="bda02-439">在中央窗格中，選取 **流覽** 以尋找並選取您建立的資訊站組組 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="bda02-439">In the center pane, select **Browse** to locate and select the kiosk configuration XML file that you created.</span></span>

   ![Windows 設定設計工具中 MultiAppAssignedAccessSettings 欄位的螢幕擷取畫面](./images/multiappassignedaccesssettings.png)

1. <span data-ttu-id="bda02-441">**選擇性**。</span><span class="sxs-lookup"><span data-stu-id="bda02-441">**Optional**.</span></span> <span data-ttu-id="bda02-442"> (如果您想要在裝置初始設定之後套用設定套件，且資訊站裝置上已有系統管理員使用者，請略過此步驟。) 選取執行時間設定 帳戶使用者，然後建\立\*\*\** &gt;\ \*\*\** &gt;\ \*\*\** 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bda02-442">(If you want to apply the provisioning package after the initial setup of the device, and there is an admin user already available on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a user account.</span></span> <span data-ttu-id="bda02-443">提供使用者名稱和密碼，然後選取**UserGroup**  >  **系統管理員**。</span><span class="sxs-lookup"><span data-stu-id="bda02-443">Provide a user name and password, and then select **UserGroup** > **Administrators**.</span></span>  
  
     <span data-ttu-id="bda02-444">您可以使用這個帳戶來查看供應狀態和記錄。</span><span class="sxs-lookup"><span data-stu-id="bda02-444">By using this account, you can view the provisioning status and logs.</span></span>  
1. <span data-ttu-id="bda02-445">**選擇性**。</span><span class="sxs-lookup"><span data-stu-id="bda02-445">**Optional**.</span></span> <span data-ttu-id="bda02-446"> (如果您已經在資訊站裝置上擁有非系統管理員帳戶，請略過此步驟。) 選取執行時間設定 帳\戶\*\*\** 使用者，然後建立本地 &gt;\ \*\*\** &gt;\ \*\*\** 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bda02-446">(If you already have a non-admin account on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a local user account.</span></span> <span data-ttu-id="bda02-447">請確定使用者名稱與在組組 XML 中指定的帳號相同。</span><span class="sxs-lookup"><span data-stu-id="bda02-447">Make sure that the user name is the same as for the account that you specify in the configuration XML.</span></span> <span data-ttu-id="bda02-448">選取**UserGroup**  >  **標準使用者**。</span><span class="sxs-lookup"><span data-stu-id="bda02-448">Select **UserGroup** > **Standard Users**.</span></span>
1. <span data-ttu-id="bda02-449">選取**檔案**  >  **儲存**。</span><span class="sxs-lookup"><span data-stu-id="bda02-449">Select **File** > **Save**.</span></span>
1. <span data-ttu-id="bda02-450">選取**匯出**  >  **部署套件**，然後選取擁有者\*\*\*\*  >  **IT 系統管理員**。這會將此部署套件的優先順序設定為高於從其他來源套用至此裝置之設定套件的優先順序。</span><span class="sxs-lookup"><span data-stu-id="bda02-450">Select **Export** > **Provisioning package**, and then select **Owner** > **IT Admin**. This sets the precedence of this provisioning package higher than provisioning packages that are applied to this device from other sources.</span></span>
1. <span data-ttu-id="bda02-451">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="bda02-451">Select **Next**.</span></span>
1. <span data-ttu-id="bda02-452">在部署 **套件安全性頁面上** ，選取安全性選項。</span><span class="sxs-lookup"><span data-stu-id="bda02-452">On the **Provisioning package security** page, select a security option.</span></span>
   > [!IMPORTANT]  
   > <span data-ttu-id="bda02-453">如果您選取 **啟用套件簽名**，您還必須選取有效的憑證，才能用於簽署套件。</span><span class="sxs-lookup"><span data-stu-id="bda02-453">If you select **Enable package signing**, you also have to select a valid certificate to use for signing the package.</span></span> <span data-ttu-id="bda02-454">若要這麼做，請選取 **流覽** ，然後選取要用於簽署套件的憑證。</span><span class="sxs-lookup"><span data-stu-id="bda02-454">To do this, select **Browse** and select the certificate that you want to use to sign the package.</span></span>
   
   > [!CAUTION]  
   > <span data-ttu-id="bda02-455">請勿選取啟用 **套件加密**。</span><span class="sxs-lookup"><span data-stu-id="bda02-455">Do not select **Enable package encryption**.</span></span> <span data-ttu-id="bda02-456">在 HoloLens 裝置上，此設定會導致設定失敗。</span><span class="sxs-lookup"><span data-stu-id="bda02-456">On HoloLens devices, this setting causes provisioning to fail.</span></span>
1. <span data-ttu-id="bda02-457">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="bda02-457">Select **Next**.</span></span>
1. <span data-ttu-id="bda02-458">指定建置套件時，您希望其輸出位置。</span><span class="sxs-lookup"><span data-stu-id="bda02-458">Specify the output location where you want the provisioning package to go when it's built.</span></span> <span data-ttu-id="bda02-459">Windows 設定設計工具預設會使用專案資料夾做為輸出位置。</span><span class="sxs-lookup"><span data-stu-id="bda02-459">By default, Windows Configuration Designer uses the project folder as the output location.</span></span> <span data-ttu-id="bda02-460">如果您想要變更輸出位置，請選取 **流覽**。</span><span class="sxs-lookup"><span data-stu-id="bda02-460">If you want to change the output location, select **Browse**.</span></span> <span data-ttu-id="bda02-461">完成後，請選取 下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="bda02-461">When you are finished, select **Next**.</span></span>
1. <span data-ttu-id="bda02-462">選取 **建立** 以開始建立套件。</span><span class="sxs-lookup"><span data-stu-id="bda02-462">Select **Build** to start building the package.</span></span> <span data-ttu-id="bda02-463">建置佈建套件並不需要很長的時間。</span><span class="sxs-lookup"><span data-stu-id="bda02-463">The provisioning package doesn't take long to build.</span></span> <span data-ttu-id="bda02-464">建立頁面會顯示專案資訊，進度列會指出建建狀態。</span><span class="sxs-lookup"><span data-stu-id="bda02-464">The build page displays the project information, and the progress bar indicates the build status.</span></span>

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a><span data-ttu-id="bda02-465">部署套件，步驟 3 &ndash; 將部署套件套用至 HoloLens</span><span class="sxs-lookup"><span data-stu-id="bda02-465">Provisioning package, step 3 &ndash; Apply the provisioning package to HoloLens</span></span>

<span data-ttu-id="bda02-466">「使用布備套件設定 HoloLens」一文提供在下列情況下套用布備套件的詳細指示：</span><span class="sxs-lookup"><span data-stu-id="bda02-466">The "Configure HoloLens by using a provisioning package" article provides detailed instructions to apply the provisioning package under the following circumstances:</span></span>

- <span data-ttu-id="bda02-467">在設定期間，您一開始可以將設定套件套用至[HoloLens。](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)</span><span class="sxs-lookup"><span data-stu-id="bda02-467">You can initially [apply a provisioning package to HoloLens during setup](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).</span></span>

- <span data-ttu-id="bda02-468">設定之後，您也可以將設定套件套用至[HoloLens。](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)</span><span class="sxs-lookup"><span data-stu-id="bda02-468">You can also [apply a provisioning package to HoloLens after setup](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup).</span></span>

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a><span data-ttu-id="bda02-469">使用 Windows 裝置入口網站設定單一應用程式資訊站</span><span class="sxs-lookup"><span data-stu-id="bda02-469">Use the Windows Device Portal to set up a single-app kiosk</span></span>

<span data-ttu-id="bda02-470">若要使用 Windows 裝置入口網站設定資訊站模式，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="bda02-470">To set up kiosk mode by using the Windows Device Portal, follow these steps.</span></span>

1. <span data-ttu-id="bda02-471">[設定 HoloLens 裝置以使用 Windows 裝置入口網站](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)。</span><span class="sxs-lookup"><span data-stu-id="bda02-471">[Set up the HoloLens device to use the Windows Device Portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal).</span></span> <span data-ttu-id="bda02-472">Device Portal 是您 HoloLens 上的網頁伺服器，您可以從電腦上的網頁瀏覽器與它連線。</span><span class="sxs-lookup"><span data-stu-id="bda02-472">The Device Portal is a web server on your HoloLens that you can connect to from a web browser on your PC.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="bda02-473">當您將 HoloLens 設定為使用裝置入口網站時，您必須在裝置上啟用開發人員模式。</span><span class="sxs-lookup"><span data-stu-id="bda02-473">When you set up HoloLens to use the Device Portal, you have to enable Developer Mode on the device.</span></span> <span data-ttu-id="bda02-474">擁有商務用 Windows Holographic 的裝置上的開發人員模式可讓您並行載入應用程式。</span><span class="sxs-lookup"><span data-stu-id="bda02-474">Developer Mode on a device that has Windows Holographic for Business enables you to side-load apps.</span></span> <span data-ttu-id="bda02-475">不過，這項設定會讓使用者安裝尚未經過 Microsoft Store 認證的 App。</span><span class="sxs-lookup"><span data-stu-id="bda02-475">However, this setting creates a risk that a user can install apps that have not been certified by the Microsoft Store.</span></span> <span data-ttu-id="bda02-476">系統管理員可以使用策略 CSP 中的 **ApplicationManagement/Allow Developerer 解除** 鎖定設定來封鎖啟用開發人員 [模式的能力](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)。</span><span class="sxs-lookup"><span data-stu-id="bda02-476">Administrators can block the ability to enable Developer Mode by using the **ApplicationManagement/AllowDeveloper Unlock** setting in the [Policy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider).</span></span> [<span data-ttu-id="bda02-477">深入了解開發人員模式。</span><span class="sxs-lookup"><span data-stu-id="bda02-477">Learn more about Developer Mode.</span></span>](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. <span data-ttu-id="bda02-478">在電腦上，使用 [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) 或 [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)連接到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="bda02-478">On a computer, connect to the HoloLens by using [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) or [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb).</span></span>

1. <span data-ttu-id="bda02-479">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bda02-479">Do one of the following:</span></span>
   - <span data-ttu-id="bda02-480">如果您是第一次連接到 Windows 裝置入口網站，請 [建立使用者名稱和密碼](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)</span><span class="sxs-lookup"><span data-stu-id="bda02-480">If you are connecting to the Windows Device Portal for the first time, [create a user name and password](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)</span></span>
   - <span data-ttu-id="bda02-481">輸入您先前設定的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="bda02-481">Enter the user name and password that you previously set up.</span></span>

    > [!TIP]
    > <span data-ttu-id="bda02-482">如果您在瀏覽器中看到憑證有誤，請遵循[下列疑難排解步驟](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)。</span><span class="sxs-lookup"><span data-stu-id="bda02-482">If you see a certificate error in the browser, follow [these troubleshooting steps](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate).</span></span>

1. <span data-ttu-id="bda02-483">在 Windows 裝置入口網站中，選取 Kiosk **模式**。</span><span class="sxs-lookup"><span data-stu-id="bda02-483">In the Windows Device Portal, select **Kiosk Mode**.</span></span>

1. <span data-ttu-id="bda02-484">選取 **啟用資訊站模式**，選取裝置啟動時要執行的應用程式， **然後選取**儲存 。</span><span class="sxs-lookup"><span data-stu-id="bda02-484">Select **Enable Kiosk Mode**, select an app to run when the device starts, and then select **Save**.</span></span>

    ![Kiosk 模式](images/kiosk.png)
1. <span data-ttu-id="bda02-486">重新開機 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="bda02-486">Restart HoloLens.</span></span> <span data-ttu-id="bda02-487">如果您仍然開啟您的裝置入口網站頁面，您可以選取 **頁面頂端的** 重新開機。</span><span class="sxs-lookup"><span data-stu-id="bda02-487">If you still have your Device Portal page open, you can select **Restart** at the top of the page.</span></span>

> [!NOTE]
> <span data-ttu-id="bda02-488">資訊站模式可透過 Device Portal 的 REST API 設定，方法為使用一個必要的查詢字串參數 ("kioskModeEnabled" 執行 POST 到 /api/holographic/kioskmode/settings，其值為 "true" 或 "false") ，以及一個選擇性參數 ("startupApp" 且套件名稱為) 。</span><span class="sxs-lookup"><span data-stu-id="bda02-488">Kiosk Mode can be set via Device Portal’s REST API by doing a POST to /api/holographic/kioskmode/settings with one required query string parameter (“kioskModeEnabled” with a value of “true” or “false”) and one optional parameter (“startupApp” with a value of a package name).</span></span> <span data-ttu-id="bda02-489">請記住，裝置入口網站僅供開發人員使用，不應在非開發人員裝置上啟用。</span><span class="sxs-lookup"><span data-stu-id="bda02-489">Please keep in mind that Device Portal is intended for developers only and should not be enabled on non-developer devices.</span></span> <span data-ttu-id="bda02-490">REST API 可能會在未來更新/發行中變更。</span><span class="sxs-lookup"><span data-stu-id="bda02-490">The REST API is subject to change in future updates/releases.</span></span>

## <a name="more-information"></a><span data-ttu-id="bda02-491">其他資訊</span><span class="sxs-lookup"><span data-stu-id="bda02-491">More information</span></span>

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a><span data-ttu-id="bda02-492">瞭解如何使用設定套件來設定資訊站。</span><span class="sxs-lookup"><span data-stu-id="bda02-492">Watch how to configure a kiosk by using a provisioning package.</span></span>  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a><span data-ttu-id="bda02-493">全域指派存取 – 資訊站模式</span><span class="sxs-lookup"><span data-stu-id="bda02-493">Global Assigned Access – Kiosk Mode</span></span>
- <span data-ttu-id="bda02-494">啟用適用于系統層級的 Kiosk 模式的新 Kiosk 方法，減少資訊站的身分識別管理。</span><span class="sxs-lookup"><span data-stu-id="bda02-494">Reduced Identity management for Kiosk, by enabling new Kiosk method that applies Kiosk mode at the system level.</span></span>

<span data-ttu-id="bda02-495">這項新功能可讓 IT 系統管理員針對適用于系統層級的多個應用程式資訊站模式設定 HoloLens 2 裝置，與系統上的任何身分識別沒有任何關聯，並適用于所有已登錄裝置的使用者。</span><span class="sxs-lookup"><span data-stu-id="bda02-495">This new feature allows an IT Admin to configure a HoloLens 2 device for multiple app kiosk mode which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span> <span data-ttu-id="bda02-496">請參閱 [HoloLens 全域指派的 Access Kiosk](hololens-global-assigned-access-kiosk.md) 檔，以取得這項新功能的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="bda02-496">See the [HoloLens global assigned access kiosk](hololens-global-assigned-access-kiosk.md) documentation for more details on this new feature.</span></span>

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a><span data-ttu-id="bda02-497">在多應用程式資訊站模式中自動啟動應用程式</span><span class="sxs-lookup"><span data-stu-id="bda02-497">Automatic launch of an application in multiple-app kiosk mode</span></span> 
- <span data-ttu-id="bda02-498">自動應用程式啟動的專注體驗，進一步增加針對 Kiosk 模式體驗所選取的 UI 和 App 選項。</span><span class="sxs-lookup"><span data-stu-id="bda02-498">Focused experience with automatic app launch, further increasing the UI and app selections chosen for Kiosk mode experiences.</span></span>

<span data-ttu-id="bda02-499">僅適用于多應用程式資訊站模式，且只有 1 個應用程式可以使用下列已指派的 Access 組式中的反亮屬性來指定自動啟動。</span><span class="sxs-lookup"><span data-stu-id="bda02-499">Applies only to multiple-app kiosk mode and only 1 app can be designated to auto-launch using highlighted attribute below in Assigned Access configuration.</span></span> 

<span data-ttu-id="bda02-500">當使用者登錄時，應用程式會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="bda02-500">Application is automatically launched when user signs-in.</span></span> 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a><span data-ttu-id="bda02-501">處理失敗時，Kiosk 模式的行為變更</span><span class="sxs-lookup"><span data-stu-id="bda02-501">Kiosk mode behavior changes for handling of failures</span></span>
- <span data-ttu-id="bda02-502">消除 Kiosk 模式上的可用應用程式失敗，以更安全的 Kiosk 模式。</span><span class="sxs-lookup"><span data-stu-id="bda02-502">More secure Kiosk mode by eliminating available apps on Kiosk mode failures.</span></span> 

<span data-ttu-id="bda02-503">先前在套用資訊站模式中遇到失敗時，HoloLens 用來在開始功能表中顯示所有應用程式。</span><span class="sxs-lookup"><span data-stu-id="bda02-503">Earlier on encountering failures in applying kiosk mode, HoloLens used to show up all applications in start menu.</span></span> <span data-ttu-id="bda02-504">現在，在 Windows Holographic 版本 20H2 發生失敗時，在開始功能表中不會顯示任何應用程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bda02-504">Now in Windows Holographic version 20H2 in the case of failures no apps will be shown in the start menu as below:</span></span> 

![當資訊站模式失敗時，其外觀影像。](images/hololens-kiosk-failure-behavior.png )

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a><span data-ttu-id="bda02-506">為離線資訊站的 Azure AD 群組成員資格進行緩存</span><span class="sxs-lookup"><span data-stu-id="bda02-506">Cache Azure AD Group membership for offline Kiosk</span></span>
- <span data-ttu-id="bda02-507">已啟用離線資訊站，可與 Azure AD 群組一起使用最多 60 天。</span><span class="sxs-lookup"><span data-stu-id="bda02-507">Enabled Offline Kiosks to be used with Azure AD groups for up to 60 days.</span></span>

<span data-ttu-id="bda02-508">此策略會控制 Azure AD 群組成員資格緩存的天數，允許用於針對已登錄使用者的 Azure AD 群組所指定的 Access 組。</span><span class="sxs-lookup"><span data-stu-id="bda02-508">This policy controls for how many days, Azure AD group membership cache is allowed to be used for Assigned Access configurations targeting Azure AD groups for signed in user.</span></span> <span data-ttu-id="bda02-509">一旦此策略值設為大於 0，則不會使用快處理。</span><span class="sxs-lookup"><span data-stu-id="bda02-509">Once this policy value is set to value greater than 0 only then cache is used otherwise not.</span></span>  

<span data-ttu-id="bda02-510">名稱：AADGroupMembershipCacheValidityInDays URI 值：./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays</span><span class="sxs-lookup"><span data-stu-id="bda02-510">Name: AADGroupMembershipCacheValidityInDays URI value: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays</span></span>

<span data-ttu-id="bda02-511">最小值 - 0 天</span><span class="sxs-lookup"><span data-stu-id="bda02-511">Min - 0 days</span></span>  
<span data-ttu-id="bda02-512">最多 - 60 天</span><span class="sxs-lookup"><span data-stu-id="bda02-512">Max - 60 days</span></span> 

<span data-ttu-id="bda02-513">正確使用此策略的步驟：</span><span class="sxs-lookup"><span data-stu-id="bda02-513">Steps to use this policy correctly:</span></span> 
1. <span data-ttu-id="bda02-514">針對 Azure AD 群組建立定位站的裝置組組設定檔，並將其指派給 HoloLens (裝置) 。</span><span class="sxs-lookup"><span data-stu-id="bda02-514">Create a device configuration profile for kiosk targeting Azure AD groups and assign it to HoloLens device(s).</span></span> 
1. <span data-ttu-id="bda02-515">建立自訂 OMA URI 裝置設定，將此策略值設定為所需的天數 (> 0) ，並將它指派給 HoloLens () 。</span><span class="sxs-lookup"><span data-stu-id="bda02-515">Create a custom OMA URI based device configuration which sets this policy value to desired number of days (> 0) and assign it to HoloLens device(s).</span></span> 
    1. <span data-ttu-id="bda02-516">URI 值應在 OMA-URI 文字方塊中輸入為 ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays</span><span class="sxs-lookup"><span data-stu-id="bda02-516">The URI value should be entered in OMA-URI text box as ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays</span></span>
    1. <span data-ttu-id="bda02-517">該值可以介於允許的 min / max 之間。</span><span class="sxs-lookup"><span data-stu-id="bda02-517">The value can be between min / max allowed.</span></span>
1. <span data-ttu-id="bda02-518">註冊 HoloLens 裝置，並驗證這兩種配置是否套用至裝置。</span><span class="sxs-lookup"><span data-stu-id="bda02-518">Enroll HoloLens devices and verify both configurations get applied to the device.</span></span> 
1. <span data-ttu-id="bda02-519">讓 Azure AD 使用者 1 在網際網路可用時進行登錄，一旦成功確認使用者登錄和 Azure AD 群組成員資格，就會建立快入。</span><span class="sxs-lookup"><span data-stu-id="bda02-519">Let Azure AD user 1 sign-in when internet is available, once user signs-in and Azure AD group membership is confirmed successfully, cache will be created.</span></span> 
1. <span data-ttu-id="bda02-520">現在 Azure AD 使用者 1 可以將 HoloLens 離線，並用於資訊站模式，只要策略值允許 X 天。</span><span class="sxs-lookup"><span data-stu-id="bda02-520">Now Azure AD user 1 can take HoloLens offline and use it for kiosk mode as long as policy value allows for X number of days.</span></span> 
1. <span data-ttu-id="bda02-521">步驟 4 和 5 可針對任何其他 Azure AD 使用者 N 重複執行。這裡的關鍵是，任何 Azure AD 使用者都必須使用網際網路來登錄裝置，因此至少一旦我們可以判斷他們為定位於哪個 Kiosk 組配置的 Azure AD 群組成員。</span><span class="sxs-lookup"><span data-stu-id="bda02-521">Steps 4 and 5 can be repeated for any other Azure AD user N. Key point here is that any Azure AD user must sign-in to device using Internet so at least once we can determine that they are member of Azure AD group to which Kiosk configuration is targeted.</span></span> 
 
> [!NOTE]
> <span data-ttu-id="bda02-522">在 Azure AD 使用者執行步驟 4 之前，將會遇到「已中斷連接」環境中提及的失敗行為。</span><span class="sxs-lookup"><span data-stu-id="bda02-522">Until step 4 is performed for a Azure AD user will experience failure behavior mentioned in “disconnected” environments.</span></span> 


## <a name="xml-kiosk-code-samples-for-hololens"></a><span data-ttu-id="bda02-523">HoloLens 的 XML Kiosk 程式碼範例</span><span class="sxs-lookup"><span data-stu-id="bda02-523">XML Kiosk Code Samples for HoloLens</span></span>

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a><span data-ttu-id="bda02-524">以 Azure AD 群組為目標的多個應用程式資訊站模式。</span><span class="sxs-lookup"><span data-stu-id="bda02-524">Multiple app kiosk mode targeting an Azure AD group.</span></span> 
<span data-ttu-id="bda02-525">此資訊站會為 Azure AD 群組中的使用者部署一個資訊站，使用者將啟用包含 3 個 App 的 Kiosk：設定、遠端輔助和意見回饋中心。</span><span class="sxs-lookup"><span data-stu-id="bda02-525">This kiosk deploys a Kiosk that for users in the Azure AD group, they will have a Kiosk enabled that includes the 3 apps: Settings, Remote Assist, and Feedback Hub.</span></span> <span data-ttu-id="bda02-526">若要修改此範例以立即使用，請務必變更下方強調的 GUID，使其符合您自己的 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="bda02-526">To modify this sample to be used immediately, make sure to change the GUID highlighted below to match an Azure AD Group of your own.</span></span> 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a><span data-ttu-id="bda02-527">以 Azure AD 帳戶為目標的多個應用程式資訊站模式。</span><span class="sxs-lookup"><span data-stu-id="bda02-527">Multiple app kiosk mode targeting Azure AD account.</span></span>
<span data-ttu-id="bda02-528">此資訊站會為單一使用者部署 Kiosk，他們將啟用包含 3 個 App 的 Kiosk：設定、遠端輔助和意見回饋中心。</span><span class="sxs-lookup"><span data-stu-id="bda02-528">This kiosk deploys a Kiosk for a single user, they will have a Kiosk enabled that includes the 3 apps: Settings, Remote Assist, and Feedback Hub.</span></span> <span data-ttu-id="bda02-529">若要修改此範例以立即使用，請務必變更下方強調的帳戶，使其符合您自己的 Azure AD 帳戶。</span><span class="sxs-lookup"><span data-stu-id="bda02-529">To modify this sample to be used immediately, make sure to change the account highlighted below to match an Azure AD Account of your own.</span></span> 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

