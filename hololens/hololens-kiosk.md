---
title: 設定 HoloLens (第 1 代) 的 kiosk
description: 使用 kiosk 配置來鎖定 HoloLens 上的應用程式。
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 04/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: c6b2bf3d48da642e91b8709cfdf35d03a7913ac4
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016687"
---
# <span data-ttu-id="e6f08-103">設定 HoloLens (第 1 代) 的 kiosk</span><span class="sxs-lookup"><span data-stu-id="e6f08-103">Set up HoloLens as a kiosk</span></span>

<span data-ttu-id="e6f08-104">您可以將 HoloLens 裝置設定為固定用途的裝置（亦稱為 *kiosk*），方法是將裝置設定為在 kiosk 模式中執行。</span><span class="sxs-lookup"><span data-stu-id="e6f08-104">You can configure a HoloLens device to function as a fixed-purpose device, also called a *kiosk*, by configuring the device to run in kiosk mode.</span></span> <span data-ttu-id="e6f08-105">展臺模式會限制裝置上可用的應用程式 (或使用者) 。</span><span class="sxs-lookup"><span data-stu-id="e6f08-105">Kiosk mode limits the applications (or users) that are available on the device.</span></span> <span data-ttu-id="e6f08-106">Kiosk 模式是一種便利的功能，您可以用來將 HoloLens 裝置專用於商務應用程式，或在應用程式示範中使用 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-106">Kiosk mode is a convenient feature that you can use to dedicate a HoloLens device to business apps, or to use the HoloLens device in an app demo.</span></span>

<span data-ttu-id="e6f08-107">本文提供有關 HoloLens 裝置專用之 kiosk 設定的各個方面的資訊。</span><span class="sxs-lookup"><span data-stu-id="e6f08-107">This article provides information about aspects of kiosk configuration that are specific to HoloLens devices.</span></span> <span data-ttu-id="e6f08-108">如需不同類型的 Windows 網亭以及如何進行設定的一般資訊，請參閱 [在 windows 桌上出版上設定網亭和數位簽章](https://docs.microsoft.com/windows/configuration/kiosk-methods)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-108">For general information about the different types of Windows-based kiosks and how to configure them, see [Configure kiosks and digital signs on Windows desktop editions](https://docs.microsoft.com/windows/configuration/kiosk-methods).</span></span>  

> [!IMPORTANT]  
> <span data-ttu-id="e6f08-109">Kiosk 模式決定使用者登入裝置時可使用哪些 app。</span><span class="sxs-lookup"><span data-stu-id="e6f08-109">Kiosk mode determines which apps are available when a user signs in to the device.</span></span> <span data-ttu-id="e6f08-110">不過，kiosk 模式不是安全性方法。</span><span class="sxs-lookup"><span data-stu-id="e6f08-110">However, kiosk mode is not a security method.</span></span> <span data-ttu-id="e6f08-111">它不會停止「允許」 app，無法開啟其他不允許的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e6f08-111">It does not stop an "allowed" app from opening another app that is not allowed.</span></span> <span data-ttu-id="e6f08-112">為了封鎖 app 或進程的開啟，請使用 [Windows Defender 應用程式控制項 (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) 來建立適當的原則。</span><span class="sxs-lookup"><span data-stu-id="e6f08-112">In order to block apps or processes from opening, use [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) to create appropriate policies.</span></span>
>
> <span data-ttu-id="e6f08-113">深入瞭解 Microsoft 服務，為使用者提供 HoloLens 2 所使用的高級安全等級，進一步瞭解 [狀態分隔與隔離資訊保護](security-state-separation-isolation.md#defender-protections)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-113">Learn more about the Microsoft services to give users an advanced level of security that HoloLens 2 uses, read more about [State separation and isolation - Defender protections](security-state-separation-isolation.md#defender-protections).</span></span> <span data-ttu-id="e6f08-114">或者，瞭解如何 [使用 WDAC 和 Windows PowerShell，透過 Microsoft Intune 在 HoloLens 2 裝置上允許或封鎖 app](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-114">Or learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="e6f08-115">您可以在單一 app 或多重應用程式設定中使用 kiosk 模式，而且您可以使用三個進程中的其中一個來設定和部署展臺設定。</span><span class="sxs-lookup"><span data-stu-id="e6f08-115">You can use kiosk mode in either a single-app or a multi-app configuration, and you can use one of three processes to set up and deploy the kiosk configuration.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="e6f08-116">刪除多重應用程式設定，會移除指派的存取功能所建立的使用者鎖定設定檔。</span><span class="sxs-lookup"><span data-stu-id="e6f08-116">Deleting the multi-app configuration removes the user lockdown profiles that the assigned access feature created.</span></span> <span data-ttu-id="e6f08-117">不過，它不會復原所有原則變更。</span><span class="sxs-lookup"><span data-stu-id="e6f08-117">However, it does not revert all the policy changes.</span></span> <span data-ttu-id="e6f08-118">若要復原這些原則，您必須將裝置重設成出廠設定。</span><span class="sxs-lookup"><span data-stu-id="e6f08-118">To revert these policies, you have to reset the device to the factory settings.</span></span>

## <span data-ttu-id="e6f08-119">規劃展臺部署</span><span class="sxs-lookup"><span data-stu-id="e6f08-119">Plan the kiosk deployment</span></span>

### <span data-ttu-id="e6f08-120">展臺模式需求</span><span class="sxs-lookup"><span data-stu-id="e6f08-120">Kiosk mode requirements</span></span>

<span data-ttu-id="e6f08-121">您可以將任何 HoloLens 2 裝置設定為使用 kiosk 模式。</span><span class="sxs-lookup"><span data-stu-id="e6f08-121">You can configure any HoloLens 2 device to use kiosk mode.</span></span>

<span data-ttu-id="e6f08-122">若要將 HoloLens (1 gen) 裝置設定為使用 kiosk 模式，您必須先確定裝置執行的是 Windows 10 版本1803或更新版本。</span><span class="sxs-lookup"><span data-stu-id="e6f08-122">To configure a HoloLens (1st gen) device to use kiosk mode, you must first make sure that the device runs Windows 10, version 1803, or a later version.</span></span> <span data-ttu-id="e6f08-123">如果您已使用 Windows 裝置恢復工具將 HoloLens (1 gen) 裝置復原為預設組建，或者如果您已安裝最新的更新，則您的裝置已準備好進行設定。</span><span class="sxs-lookup"><span data-stu-id="e6f08-123">If you have used the Windows Device Recovery Tool to recover your HoloLens (1st gen) device to its default build, or if you have installed the most recent updates, your device is ready to configure.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="e6f08-124">若要協助保護在 kiosk 模式下執行的裝置，請考慮新增裝置管理原則，以關閉 USB 連線等功能。</span><span class="sxs-lookup"><span data-stu-id="e6f08-124">To help protect devices that run in kiosk mode, consider adding device management policies that turn off features such as USB connectivity.</span></span> <span data-ttu-id="e6f08-125">此外，請檢查您的 [更新鈴聲] 設定，以確定在上班時間期間不會進行自動更新。</span><span class="sxs-lookup"><span data-stu-id="e6f08-125">Additionally, check your update ring settings to make sure that automatic updates do not occur during business hours.</span></span>

### <span data-ttu-id="e6f08-126">在單一應用程式亭或多重應用程式亭之間進行決定</span><span class="sxs-lookup"><span data-stu-id="e6f08-126">Decide between a single-app kiosk or a multi-app kiosk</span></span>

<span data-ttu-id="e6f08-127">當使用者登入裝置時，單一 app 展臺會啟動指定的 app。</span><span class="sxs-lookup"><span data-stu-id="e6f08-127">A single-app kiosk starts the specified app when the user signs in to the device.</span></span> <span data-ttu-id="e6f08-128">[開始] 功能表停用，就像是 Cortana 一樣。</span><span class="sxs-lookup"><span data-stu-id="e6f08-128">The Start menu is disabled, as is Cortana.</span></span> <span data-ttu-id="e6f08-129">HoloLens 2 裝置沒有回應 [開始](hololens2-basic-usage.md#start-gesture) 手勢。</span><span class="sxs-lookup"><span data-stu-id="e6f08-129">A HoloLens 2 device does not respond to the [Start](hololens2-basic-usage.md#start-gesture) gesture.</span></span> <span data-ttu-id="e6f08-130">HoloLens (1 gen) 裝置不會回應 [bloom](hololens1-basic-usage.md) 手勢。</span><span class="sxs-lookup"><span data-stu-id="e6f08-130">A HoloLens (1st gen) device does not respond to the [bloom](hololens1-basic-usage.md) gesture.</span></span> <span data-ttu-id="e6f08-131">因為只有一個 app 可以執行，所以使用者無法放置其他應用程式。</span><span class="sxs-lookup"><span data-stu-id="e6f08-131">Because only one app can run, the user cannot place other apps.</span></span>

<span data-ttu-id="e6f08-132">多個應用程式站會在使用者登入裝置時顯示 [開始] 功能表。</span><span class="sxs-lookup"><span data-stu-id="e6f08-132">A multi-app kiosk displays the Start menu when the user signs in to the device.</span></span> <span data-ttu-id="e6f08-133">展臺設定會決定在 [開始] 功能表上可用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e6f08-133">The kiosk configuration determines which apps are available on the Start menu.</span></span> <span data-ttu-id="e6f08-134">您可以使用多重應用程式亭，透過只向他們提供他們所需使用的專案，並移除不需要使用的專案，來為使用者提供易於理解的體驗。</span><span class="sxs-lookup"><span data-stu-id="e6f08-134">You can use a multi-app kiosk to provide an easy-to-understand experience for users by presenting to them only the things that they have to use, and removing the things they don't need to use.</span></span>

<span data-ttu-id="e6f08-135">下表列出不同資訊亭模式中的功能功能。</span><span class="sxs-lookup"><span data-stu-id="e6f08-135">The following table lists the feature capabilities in the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="e6f08-136">[開始] 功能表</span><span class="sxs-lookup"><span data-stu-id="e6f08-136">Start menu</span></span> |<span data-ttu-id="e6f08-137">[快速動作] 功能表</span><span class="sxs-lookup"><span data-stu-id="e6f08-137">Quick Actions menu</span></span> |<span data-ttu-id="e6f08-138">相機和影片</span><span class="sxs-lookup"><span data-stu-id="e6f08-138">Camera and video</span></span> |<span data-ttu-id="e6f08-139">Miracast</span><span class="sxs-lookup"><span data-stu-id="e6f08-139">Miracast</span></span> |<span data-ttu-id="e6f08-140">Cortana</span><span class="sxs-lookup"><span data-stu-id="e6f08-140">Cortana</span></span> |<span data-ttu-id="e6f08-141">內建語音命令</span><span class="sxs-lookup"><span data-stu-id="e6f08-141">Built-in voice commands</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|<span data-ttu-id="e6f08-142">單一應用程式資訊站</span><span class="sxs-lookup"><span data-stu-id="e6f08-142">Single-app kiosk</span></span> |<span data-ttu-id="e6f08-143">已停用</span><span class="sxs-lookup"><span data-stu-id="e6f08-143">Disabled</span></span> |<span data-ttu-id="e6f08-144">已停用</span><span class="sxs-lookup"><span data-stu-id="e6f08-144">Disabled</span></span>   |<span data-ttu-id="e6f08-145">已停用</span><span class="sxs-lookup"><span data-stu-id="e6f08-145">Disabled</span></span> |<span data-ttu-id="e6f08-146">已停用</span><span class="sxs-lookup"><span data-stu-id="e6f08-146">Disabled</span></span>   |<span data-ttu-id="e6f08-147">已停用</span><span class="sxs-lookup"><span data-stu-id="e6f08-147">Disabled</span></span> |<span data-ttu-id="e6f08-148">已啟用 <sup> 1</span><span class="sxs-lookup"><span data-stu-id="e6f08-148">Enabled<sup>1</span></span></sup> |
|<span data-ttu-id="e6f08-149">多應用程式亭</span><span class="sxs-lookup"><span data-stu-id="e6f08-149">Multi-app kiosk</span></span> |<span data-ttu-id="e6f08-150">啟用</span><span class="sxs-lookup"><span data-stu-id="e6f08-150">Enabled</span></span> |<span data-ttu-id="e6f08-151">已啟用 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="e6f08-151">Enabled<sup>2</span></span></sup> |<span data-ttu-id="e6f08-152">可用 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="e6f08-152">Available<sup>2</span></span></sup> |<span data-ttu-id="e6f08-153">可用 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="e6f08-153">Available<sup>2</span></span></sup> |<span data-ttu-id="e6f08-154">可用 <sup> 2、3</span><span class="sxs-lookup"><span data-stu-id="e6f08-154">Available<sup>2, 3</span></span></sup>  |<span data-ttu-id="e6f08-155">已啟用 <sup> 1</span><span class="sxs-lookup"><span data-stu-id="e6f08-155">Enabled<sup>1</span></span></sup> |

> <sup><span data-ttu-id="e6f08-156">1與 </sup> 停用功能相關的語音命令無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="e6f08-156">1</sup> Voice commands that relate to disabled features do not function.</span></span>  
> <sup><span data-ttu-id="e6f08-157">2 </sup> 如需如何設定這些功能的詳細資訊，請參閱 [選取 kiosk app](#plan-kiosk-apps)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-157">2</sup> For more information about how to configure these features, see [Select kiosk apps](#plan-kiosk-apps).</span></span>  
> <sup><span data-ttu-id="e6f08-158">3 </sup> 即使已停用 Cortana，仍會啟用內建語音命令。</span><span class="sxs-lookup"><span data-stu-id="e6f08-158">3</sup> Even if Cortana is disabled, the built-in voice commands are enabled.</span></span>

<span data-ttu-id="e6f08-159">下表列出不同 kiosk 模式的使用者支援功能。</span><span class="sxs-lookup"><span data-stu-id="e6f08-159">The following table lists the user support features of the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="e6f08-160">支援的使用者類型</span><span class="sxs-lookup"><span data-stu-id="e6f08-160">Supported user types</span></span> | <span data-ttu-id="e6f08-161">自動登入</span><span class="sxs-lookup"><span data-stu-id="e6f08-161">Automatic sign-in</span></span> | <span data-ttu-id="e6f08-162">多個存取層級</span><span class="sxs-lookup"><span data-stu-id="e6f08-162">Multiple access levels</span></span> |
| --- | --- | --- | --- |
|<span data-ttu-id="e6f08-163">單一應用程式資訊站</span><span class="sxs-lookup"><span data-stu-id="e6f08-163">Single-app kiosk</span></span> |<span data-ttu-id="e6f08-164">受管理的服務帳戶 (Azure Active Directory (AAD) 或本機帳戶中的 MSA) </span><span class="sxs-lookup"><span data-stu-id="e6f08-164">Managed Service Account (MSA) in Azure Active Directory (AAD) or local account</span></span> |<span data-ttu-id="e6f08-165">是</span><span class="sxs-lookup"><span data-stu-id="e6f08-165">Yes</span></span> |<span data-ttu-id="e6f08-166">否</span><span class="sxs-lookup"><span data-stu-id="e6f08-166">No</span></span> |
|<span data-ttu-id="e6f08-167">多應用程式亭</span><span class="sxs-lookup"><span data-stu-id="e6f08-167">Multi-app kiosk</span></span> |<span data-ttu-id="e6f08-168">AAD 帳戶</span><span class="sxs-lookup"><span data-stu-id="e6f08-168">AAD account</span></span> |<span data-ttu-id="e6f08-169">否</span><span class="sxs-lookup"><span data-stu-id="e6f08-169">No</span></span> |<span data-ttu-id="e6f08-170">是</span><span class="sxs-lookup"><span data-stu-id="e6f08-170">Yes</span></span> |

<span data-ttu-id="e6f08-171">如需如何使用這些功能的範例，請參閱下表。</span><span class="sxs-lookup"><span data-stu-id="e6f08-171">For examples of how to use these capabilities, see the following table.</span></span>

|<span data-ttu-id="e6f08-172">使用單一應用程式亭進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="e6f08-172">Use a single-app kiosk for:</span></span> |<span data-ttu-id="e6f08-173">使用多應用程式亭進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="e6f08-173">Use a multi-app kiosk for:</span></span> |
| --- | --- |
|<span data-ttu-id="e6f08-174">一種裝置，只對新的員工執行 Dynamics 365 指南。</span><span class="sxs-lookup"><span data-stu-id="e6f08-174">A device that runs only a Dynamics 365 Guide for new employees.</span></span> |<span data-ttu-id="e6f08-175">為一系列員工執行輔助線和遠端協助的裝置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-175">A device that runs both Guides and Remote Assistance for a range of employees.</span></span> |
|<span data-ttu-id="e6f08-176">只執行自訂應用程式的裝置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-176">A device that runs only a custom app.</span></span> |<span data-ttu-id="e6f08-177">在 (只執行自訂應用程式) 的裝置，但作為特定使用者群組的標準裝置的功能。</span><span class="sxs-lookup"><span data-stu-id="e6f08-177">A device that functions as a kiosk for most users (running only a custom app), but functions as a standard device for a specific group of users.</span></span> |

### <span data-ttu-id="e6f08-178">規劃展臺應用程式</span><span class="sxs-lookup"><span data-stu-id="e6f08-178">Plan kiosk apps</span></span>

<span data-ttu-id="e6f08-179">如需如何選擇 kiosk app 的一般資訊，請參閱在 [ (kiosk 模式] 中選擇指派存取權的原則) ](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-179">For general information about how to choose kiosk apps, see [Guidelines for choosing an app for assigned access (kiosk mode)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app).</span></span>

<span data-ttu-id="e6f08-180">如果您使用 Windows Device Portal 來設定單一應用程式亭，您可以在安裝程式期間選取 app。</span><span class="sxs-lookup"><span data-stu-id="e6f08-180">If you use the Windows Device Portal to configure a single-app kiosk, you select the app during the setup process.</span></span>  

<span data-ttu-id="e6f08-181">如果您使用行動裝置管理 (MDM) 系統或預配套件來設定 kiosk 模式，您可以使用 [AssignedAccess 配置服務提供者 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) 來指定應用程式。</span><span class="sxs-lookup"><span data-stu-id="e6f08-181">If you use a Mobile Device Management (MDM) system or a provisioning package to configure kiosk mode, you use the [AssignedAccess Configuration Service Provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) to specify applications.</span></span> <span data-ttu-id="e6f08-182">CSP 會使用 [應用程式使用者模型識別碼 (aumid) ](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 來識別應用程式。</span><span class="sxs-lookup"><span data-stu-id="e6f08-182">The CSP uses [Application User Model IDs (AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) to identify applications.</span></span> <span data-ttu-id="e6f08-183">下表列出一些您可以在多應用程式亭中使用的 Aumid 應用程式。</span><span class="sxs-lookup"><span data-stu-id="e6f08-183">The following table lists the AUMIDs of some in-box applications that you can use in a multi-app kiosk.</span></span>

> [!CAUTION]
> <span data-ttu-id="e6f08-184">您無法選取 [Shell] app 做為展臺 app。</span><span class="sxs-lookup"><span data-stu-id="e6f08-184">You cannot select the Shell app as a kiosk app.</span></span> <span data-ttu-id="e6f08-185">此外，我們建議您 **不要選取 [** microsoft Edge]、[microsoft Store] 或 [檔案資源管理器] 做為展臺 app。</span><span class="sxs-lookup"><span data-stu-id="e6f08-185">Addition, we recommend that you do **not** select Microsoft Edge, Microsoft Store, or File Explorer as a kiosk app.</span></span>  

<a id="aumids"></a>

|<span data-ttu-id="e6f08-186">應用程式名稱</span><span class="sxs-lookup"><span data-stu-id="e6f08-186">App Name</span></span> |<span data-ttu-id="e6f08-187">AUMID</span><span class="sxs-lookup"><span data-stu-id="e6f08-187">AUMID</span></span> |
| --- | --- |
|<span data-ttu-id="e6f08-188">3D 檢視器</span><span class="sxs-lookup"><span data-stu-id="e6f08-188">3D Viewer</span></span> |<span data-ttu-id="e6f08-189">Microsoft3DViewer _8wekyb3d8bbwe \！Microsoft3DViewer</span><span class="sxs-lookup"><span data-stu-id="e6f08-189">Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\!Microsoft.Microsoft3DViewer</span></span> |
|<span data-ttu-id="e6f08-190">行事曆</span><span class="sxs-lookup"><span data-stu-id="e6f08-190">Calendar</span></span> |<span data-ttu-id="e6f08-191">windowscommunicationsapps \ _8wekyb3d8bbwe \！ windowslive。</span><span class="sxs-lookup"><span data-stu-id="e6f08-191">microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\!microsoft.windowslive.calendar</span></span> |
|<span data-ttu-id="e6f08-192">相機 <sup> 1、2</span><span class="sxs-lookup"><span data-stu-id="e6f08-192">Camera<sup>1, 2</span></span></sup> |<span data-ttu-id="e6f08-193">HoloCamera \ _cw5n1h2txyewy \！HoloCamera</span><span class="sxs-lookup"><span data-stu-id="e6f08-193">HoloCamera\_cw5n1h2txyewy\!HoloCamera</span></span> |
|<span data-ttu-id="e6f08-194">Cortana <sup> 3</span><span class="sxs-lookup"><span data-stu-id="e6f08-194">Cortana<sup>3</span></span></sup> |<span data-ttu-id="e6f08-195">549981C3F5F10 _8wekyb3d8bbwe \！適用</span><span class="sxs-lookup"><span data-stu-id="e6f08-195">Microsoft.549981C3F5F10\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="e6f08-196">HoloLens 上的 Device 拾器 (1 gen) </span><span class="sxs-lookup"><span data-stu-id="e6f08-196">Device Picker on HoloLens (1st gen)</span></span> |<span data-ttu-id="e6f08-197">HoloDevicesFlow \ _cw5n1h2txyewy \！HoloDevicesFlow</span><span class="sxs-lookup"><span data-stu-id="e6f08-197">HoloDevicesFlow\_cw5n1h2txyewy\!HoloDevicesFlow</span></span> |
|<span data-ttu-id="e6f08-198">HoloLens 2 上的裝置選擇器</span><span class="sxs-lookup"><span data-stu-id="e6f08-198">Device Picker on HoloLens 2</span></span> |<span data-ttu-id="e6f08-199">DevicesFlowHost \ _cw5n1h2txyewy \！DevicesFlowHost</span><span class="sxs-lookup"><span data-stu-id="e6f08-199">Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\!Microsoft.Windows.DevicesFlowHost</span></span> |
|<span data-ttu-id="e6f08-200">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="e6f08-200">Dynamics 365 Guides</span></span> |<span data-ttu-id="e6f08-201">Dynamics365 _8wekyb3d8bbwe \！MicrosoftGuides</span><span class="sxs-lookup"><span data-stu-id="e6f08-201">Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\!MicrosoftGuides</span></span> |
|<span data-ttu-id="e6f08-202">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="e6f08-202">Dynamics 365 Remote Assist</span></span> |<span data-ttu-id="e6f08-203">MicrosoftRemoteAssist _8wekyb3d8bbwe \！RemoteAssist</span><span class="sxs-lookup"><span data-stu-id="e6f08-203">Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\!Microsoft.RemoteAssist</span></span> |
|<span data-ttu-id="e6f08-204">意見反應 &nbsp; 中樞</span><span class="sxs-lookup"><span data-stu-id="e6f08-204">Feedback&nbsp;Hub</span></span> |<span data-ttu-id="e6f08-205">WindowsFeedbackHub _8wekyb3d8bbwe \！適用</span><span class="sxs-lookup"><span data-stu-id="e6f08-205">Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="e6f08-206">檔案總管</span><span class="sxs-lookup"><span data-stu-id="e6f08-206">File Explorer</span></span> |<span data-ttu-id="e6f08-207">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span><span class="sxs-lookup"><span data-stu-id="e6f08-207">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span></span> |
|<span data-ttu-id="e6f08-208">Mail</span><span class="sxs-lookup"><span data-stu-id="e6f08-208">Mail</span></span> |<span data-ttu-id="e6f08-209">windowscommunicationsapps_8wekyb3d8bbwe！ windowslive！</span><span class="sxs-lookup"><span data-stu-id="e6f08-209">microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail</span></span> |
|<span data-ttu-id="e6f08-210">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="e6f08-210">Microsoft Store</span></span> |<span data-ttu-id="e6f08-211">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span><span class="sxs-lookup"><span data-stu-id="e6f08-211">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span></span> |
|<span data-ttu-id="e6f08-212">Miracast <sup> 4</span><span class="sxs-lookup"><span data-stu-id="e6f08-212">Miracast<sup>4</span></span></sup> |&nbsp; |
|<span data-ttu-id="e6f08-213">電影與電視</span><span class="sxs-lookup"><span data-stu-id="e6f08-213">Movies & TV</span></span> |<span data-ttu-id="e6f08-214">ZuneVideo _8wekyb3d8bbwe \！ZuneVideo</span><span class="sxs-lookup"><span data-stu-id="e6f08-214">Microsoft.ZuneVideo\_8wekyb3d8bbwe\!Microsoft.ZuneVideo</span></span> |
|<span data-ttu-id="e6f08-215">OneDrive</span><span class="sxs-lookup"><span data-stu-id="e6f08-215">OneDrive</span></span> |<span data-ttu-id="e6f08-216">microsoftskydrive _8wekyb3d8bbwe \！適用</span><span class="sxs-lookup"><span data-stu-id="e6f08-216">microsoft.microsoftskydrive\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="e6f08-217">相片</span><span class="sxs-lookup"><span data-stu-id="e6f08-217">Photos</span></span> |<span data-ttu-id="e6f08-218">您的 _8wekyb3d8bbwe \！適用</span><span class="sxs-lookup"><span data-stu-id="e6f08-218">Microsoft.Windows.Photos\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="e6f08-219">設定</span><span class="sxs-lookup"><span data-stu-id="e6f08-219">Settings</span></span> |<span data-ttu-id="e6f08-220">HolographicSystemSettings \ _cw5n1h2txyewy \！適用</span><span class="sxs-lookup"><span data-stu-id="e6f08-220">HolographicSystemSettings\_cw5n1h2txyewy\!App</span></span> |
|<span data-ttu-id="e6f08-221">提示</span><span class="sxs-lookup"><span data-stu-id="e6f08-221">Tips</span></span> |<span data-ttu-id="e6f08-222">HoloLensTips _8wekyb3d8bbwe \！HoloLensTips</span><span class="sxs-lookup"><span data-stu-id="e6f08-222">Microsoft.HoloLensTips\_8wekyb3d8bbwe\!HoloLensTips</span></span> |

> <sup><span data-ttu-id="e6f08-223">1 </sup> 若要啟用相片或影片捕獲，您必須啟用攝影機 app 作為 kiosk app。</span><span class="sxs-lookup"><span data-stu-id="e6f08-223">1</sup> To enable photo or video capture, you have to enable the Camera app as a kiosk app.</span></span>  
> <sup><span data-ttu-id="e6f08-224">2 </sup> 當您啟用攝像頭 app 時，請注意下列情況：</span><span class="sxs-lookup"><span data-stu-id="e6f08-224">2</sup> When you enable the Camera app, be aware of the following conditions:</span></span>
> - <span data-ttu-id="e6f08-225">[快速動作] 功能表包括 [相片] 和 [影片] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="e6f08-225">The Quick Actions menu includes the Photo and Video buttons.</span></span>  
> - <span data-ttu-id="e6f08-226">您也應該啟用可與圖片互動或取得圖片的 app (例如相片、郵件或 OneDrive) 。</span><span class="sxs-lookup"><span data-stu-id="e6f08-226">You should also enable an app (such as Photos, Mail, or OneDrive) that can interact with or retrieve pictures.</span></span>  
>  
> <sup><span data-ttu-id="e6f08-227">3 </sup> 即使您未啟用 Cortana 作為 kiosk app，也會啟用內建語音命令。</span><span class="sxs-lookup"><span data-stu-id="e6f08-227">3</sup> Even if you do not enable Cortana as a kiosk app, built-in voice commands are enabled.</span></span> <span data-ttu-id="e6f08-228">不過，與停用功能相關的命令不會產生任何效果。</span><span class="sxs-lookup"><span data-stu-id="e6f08-228">However, commands that are related to disabled features have no effect.</span></span>  
> <sup><span data-ttu-id="e6f08-229">4 </sup> 您無法直接啟用 Miracast。</span><span class="sxs-lookup"><span data-stu-id="e6f08-229">4</sup> You cannot enable Miracast directly.</span></span> <span data-ttu-id="e6f08-230">若要啟用 Miracast 作為 kiosk app，請啟用相機 app 和裝置選擇器應用程式。</span><span class="sxs-lookup"><span data-stu-id="e6f08-230">To enable Miracast as a kiosk app enable the Camera app and the Device Picker app.</span></span>

### <span data-ttu-id="e6f08-231">規劃使用者和裝置群組</span><span class="sxs-lookup"><span data-stu-id="e6f08-231">Plan user and device groups</span></span>

<span data-ttu-id="e6f08-232">在 MDM 環境中，您可以使用群組來管理裝置設定和使用者存取。</span><span class="sxs-lookup"><span data-stu-id="e6f08-232">In an MDM environment, you use groups to manage device configurations and user access.</span></span> 

<span data-ttu-id="e6f08-233">Kiosk 配置設定檔包括 [ **使用者登入類型** ] 設定。</span><span class="sxs-lookup"><span data-stu-id="e6f08-233">The kiosk configuration profile includes the **User logon type** setting.</span></span> <span data-ttu-id="e6f08-234">**使用者登入類型** 會識別使用者 (或群組，其中包含哪些使用者可以使用您所新增的應用程式) 。</span><span class="sxs-lookup"><span data-stu-id="e6f08-234">**User logon type** identifies the user (or group that contains the users) who can use the app or apps that you add.</span></span> <span data-ttu-id="e6f08-235">如果使用者使用未包含在設定檔中的帳戶登入，該使用者就無法在展臺上使用 app。</span><span class="sxs-lookup"><span data-stu-id="e6f08-235">If a user signs in by using an account that is not included in the configuration profile, that user cannot use apps on the kiosk.</span></span>  

> [!NOTE]  
> <span data-ttu-id="e6f08-236">單一 app 展臺的 **使用者登入類型** 會指定單一使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="e6f08-236">The **User logon type** of a single-app kiosk specifies a single user account.</span></span> <span data-ttu-id="e6f08-237">這是在其中執行 kiosk 的使用者內容。</span><span class="sxs-lookup"><span data-stu-id="e6f08-237">This is the user context under which the kiosk runs.</span></span> <span data-ttu-id="e6f08-238">多應用程式亭的 **使用者登入類型** 可以指定一個或多個可以使用 kiosk 的使用者帳戶或群組。</span><span class="sxs-lookup"><span data-stu-id="e6f08-238">The **User logon type** of a multi-app kiosk can specify one or more user accounts or groups that can use the kiosk.</span></span>

<span data-ttu-id="e6f08-239">您必須先將 kiosk 配置設定檔 *指派* 給包含裝置的群組，或是可以登入裝置的使用者，才能將其部署到裝置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-239">Before you can deploy the kiosk configuration to a device, you have to *assign* the kiosk configuration profile to a group that contains the device or a user who can sign in to the device.</span></span> <span data-ttu-id="e6f08-240">這個設定會產生如下所示的行為。</span><span class="sxs-lookup"><span data-stu-id="e6f08-240">This setting produces behavior such as the following.</span></span>

- <span data-ttu-id="e6f08-241">如果裝置是指派群組的成員，則在任何使用者第一次登入裝置時，kiosk 設定就會部署到該裝置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-241">If the device is a member of the assigned group, the kiosk configuration deploys to the device the first time that any user signs in on the device.</span></span>  
- <span data-ttu-id="e6f08-242">如果裝置不是指派群組的成員，但屬於該群組成員的使用者登入，kiosk 設定會在該時間部署到裝置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-242">If the device is not a member of the assigned group, but a user who is a member of that group signs in, the kiosk configuration deploys to the device at that time.</span></span>

<span data-ttu-id="e6f08-243">如需在 Intune 中指派設定檔的效果的完整討論，請參閱 [在 Microsoft Intune 中指派使用者和裝置設定檔](https://docs.microsoft.com/intune/configuration/device-profile-assign)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-243">For a full discussion of the effects of assigning configuration profiles in Intune, see [Assign user and device profiles in Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).</span></span>

> [!NOTE]  
> <span data-ttu-id="e6f08-244">下列範例說明多重 app 網亭。</span><span class="sxs-lookup"><span data-stu-id="e6f08-244">The following examples describe multi-app kiosks.</span></span> <span data-ttu-id="e6f08-245">單一 app 網亭的行為方式與此類似，但只有一個使用者帳戶能取得 kiosk 體驗。</span><span class="sxs-lookup"><span data-stu-id="e6f08-245">Single-app kiosks behave in a similar manner, but only one user account gets the kiosk experience.</span></span>

**<span data-ttu-id="e6f08-246">範例 1</span><span class="sxs-lookup"><span data-stu-id="e6f08-246">Example 1</span></span>**

<span data-ttu-id="e6f08-247">您針對裝置和使用者使用單一群組 (群組 1) 。</span><span class="sxs-lookup"><span data-stu-id="e6f08-247">You use a single group (Group 1) for both devices and users.</span></span> <span data-ttu-id="e6f08-248">一個裝置和使用者 A、B 和 C 都是這個群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e6f08-248">One device and users A, B, and C are members of this group.</span></span> <span data-ttu-id="e6f08-249">您可以設定展臺設定檔，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e6f08-249">You configure the kiosk configuration profile as follows:</span></span>  

- <span data-ttu-id="e6f08-250">**使用者登入類型**：群組1</span><span class="sxs-lookup"><span data-stu-id="e6f08-250">**User logon type**: Group 1</span></span>
- <span data-ttu-id="e6f08-251">**已指派的群組**：群組1</span><span class="sxs-lookup"><span data-stu-id="e6f08-251">**Assigned group**: Group 1</span></span>

<span data-ttu-id="e6f08-252">不論哪個使用者先登入裝置 (並透過全新的體驗（或 OOBE) ），kiosk 配置也會部署到裝置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-252">Regardless of which user signs on to the device first (and goes through the Out-of-Box Experience, or OOBE), the kiosk configuration deploys to the device.</span></span> <span data-ttu-id="e6f08-253">使用者 A、B 和 C 都可以登入裝置並取得展臺體驗。</span><span class="sxs-lookup"><span data-stu-id="e6f08-253">Users A, B, and C can all sign in to the device and get the kiosk experience.</span></span>

**<span data-ttu-id="e6f08-254">範例 2</span><span class="sxs-lookup"><span data-stu-id="e6f08-254">Example 2</span></span>**

<span data-ttu-id="e6f08-255">您會將裝置合約給需要不同資訊站體驗的兩個不同轉銷商。</span><span class="sxs-lookup"><span data-stu-id="e6f08-255">You contract out devices to two different vendors who need different kiosk experiences.</span></span> <span data-ttu-id="e6f08-256">兩個廠商都有使用者，而且您想讓所有使用者都能存取其自己的供應商和其他廠商的展臺。</span><span class="sxs-lookup"><span data-stu-id="e6f08-256">Both vendors have users, and you want all the users to have access to kiosks from both their own vendor and the other vendor.</span></span> <span data-ttu-id="e6f08-257">您可以按照下列步驟設定群組：</span><span class="sxs-lookup"><span data-stu-id="e6f08-257">You configure groups as follows:</span></span>

- <span data-ttu-id="e6f08-258">裝置群組1：</span><span class="sxs-lookup"><span data-stu-id="e6f08-258">Device Group 1:</span></span>
  - <span data-ttu-id="e6f08-259">裝置 1 (供應商 1) </span><span class="sxs-lookup"><span data-stu-id="e6f08-259">Device 1 (Vendor 1)</span></span>
  - <span data-ttu-id="e6f08-260">裝置 2 (供應商 1) </span><span class="sxs-lookup"><span data-stu-id="e6f08-260">Device 2 (Vendor 1)</span></span>

- <span data-ttu-id="e6f08-261">裝置群組2：</span><span class="sxs-lookup"><span data-stu-id="e6f08-261">Device Group 2:</span></span>
  - <span data-ttu-id="e6f08-262">裝置 3 (供應商 2) </span><span class="sxs-lookup"><span data-stu-id="e6f08-262">Device 3 (Vendor 2)</span></span>
  - <span data-ttu-id="e6f08-263">裝置 4 (供應商 2) </span><span class="sxs-lookup"><span data-stu-id="e6f08-263">Device 4 (Vendor 2)</span></span>

- <span data-ttu-id="e6f08-264">[使用者] 群組：</span><span class="sxs-lookup"><span data-stu-id="e6f08-264">User Group:</span></span>
  - <span data-ttu-id="e6f08-265">使用者 A (供應商 1) </span><span class="sxs-lookup"><span data-stu-id="e6f08-265">User A (Vendor 1)</span></span>
  - <span data-ttu-id="e6f08-266">使用者 B (供應商 2) </span><span class="sxs-lookup"><span data-stu-id="e6f08-266">User B (Vendor 2)</span></span>

<span data-ttu-id="e6f08-267">您建立兩個具備下列設定的 kiosk 設定檔：</span><span class="sxs-lookup"><span data-stu-id="e6f08-267">You create two kiosk configuration profiles that have the following settings:</span></span>

- <span data-ttu-id="e6f08-268">展臺設定檔1：</span><span class="sxs-lookup"><span data-stu-id="e6f08-268">Kiosk Profile 1:</span></span>
   - <span data-ttu-id="e6f08-269">**使用者登入類型**：使用者群組</span><span class="sxs-lookup"><span data-stu-id="e6f08-269">**User logon type**: User Group</span></span>
   - <span data-ttu-id="e6f08-270">**已指派的群組**：裝置群組1</span><span class="sxs-lookup"><span data-stu-id="e6f08-270">**Assigned group**: Device Group 1</span></span>

- <span data-ttu-id="e6f08-271">展臺設定檔2：</span><span class="sxs-lookup"><span data-stu-id="e6f08-271">Kiosk Profile 2:</span></span>
   - <span data-ttu-id="e6f08-272">**使用者登入類型**：使用者群組</span><span class="sxs-lookup"><span data-stu-id="e6f08-272">**User logon type**: User Group</span></span>
   - <span data-ttu-id="e6f08-273">**已指派的群組**：裝置群組2</span><span class="sxs-lookup"><span data-stu-id="e6f08-273">**Assigned group**: Device Group 2</span></span>

<span data-ttu-id="e6f08-274">這些設定會產生下列結果：</span><span class="sxs-lookup"><span data-stu-id="e6f08-274">These configurations produce the following results:</span></span>

- <span data-ttu-id="e6f08-275">當任何使用者登入 [裝置 1] 或 [裝置 2] 時，Intune 都會將 Kiosk 設定檔1部署到該裝置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-275">When any user signs in to Device 1 or Device 2, Intune deploys Kiosk Profile 1 to that device.</span></span>
- <span data-ttu-id="e6f08-276">當任何使用者登入 [裝置 3] 或 [裝置 4] 時，Intune 都會將 Kiosk 設定檔2部署到該裝置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-276">When any user signs in to Device 3 or Device 4, Intune deploys Kiosk Profile 2 to that device.</span></span>
- <span data-ttu-id="e6f08-277">使用者 A 和使用者 B 可以登入四個裝置中的任何一種。</span><span class="sxs-lookup"><span data-stu-id="e6f08-277">User A and user B can sign in to any of the four devices.</span></span> <span data-ttu-id="e6f08-278">如果他們登入 [裝置 1] 或 [裝置 2]，就會看到 [廠商1資訊] 的體驗。</span><span class="sxs-lookup"><span data-stu-id="e6f08-278">If they sign in to Device 1 or Device 2, they see the Vendor 1 kiosk experience.</span></span> <span data-ttu-id="e6f08-279">如果他們登入 [裝置 3] 或 [裝置 4]，就會看到 [廠商 2] 的 kiosk 體驗。</span><span class="sxs-lookup"><span data-stu-id="e6f08-279">If they sign in to Device 3 or Device 4, they see the Vendor 2 kiosk experience.</span></span>

#### <span data-ttu-id="e6f08-280">設定檔衝突</span><span class="sxs-lookup"><span data-stu-id="e6f08-280">Profile conflicts</span></span>

<span data-ttu-id="e6f08-281">如果有兩個或多個展臺配置設定檔針對相同的裝置，就會發生衝突。</span><span class="sxs-lookup"><span data-stu-id="e6f08-281">If two or more kiosk configuration profiles target the same device, they conflict.</span></span> <span data-ttu-id="e6f08-282">如果是 Intune 管理的裝置，則 Intune 不會套用任何衝突的設定檔。</span><span class="sxs-lookup"><span data-stu-id="e6f08-282">In the case of Intune-managed devices, Intune does not apply any of the conflicting profiles.</span></span>

<span data-ttu-id="e6f08-283">其他類型的設定檔與原則，例如與 kiosk 配置設定檔無關的裝置限制，請勿與 kiosk 設定設定檔發生衝突。</span><span class="sxs-lookup"><span data-stu-id="e6f08-283">Other kinds of profiles and policies, such as device restrictions that are not related to the kiosk configuration profile, do not conflict with the kiosk configuration profile.</span></span>

### <span data-ttu-id="e6f08-284">選取部署方法</span><span class="sxs-lookup"><span data-stu-id="e6f08-284">Select a deployment method</span></span>

<span data-ttu-id="e6f08-285">您可以選取下列其中一種方法來部署展臺配置：</span><span class="sxs-lookup"><span data-stu-id="e6f08-285">You can select one of the following methods to deploy kiosk configurations:</span></span>

- [<span data-ttu-id="e6f08-286"> (MDM) 服務的 Microsoft Intune 或其他行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="e6f08-286">Microsoft Intune or other mobile device management (MDM) service</span></span>](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="e6f08-287">佈建套件</span><span class="sxs-lookup"><span data-stu-id="e6f08-287">Provisioning package</span></span>](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="e6f08-288">Windows Device Portal</span><span class="sxs-lookup"><span data-stu-id="e6f08-288">Windows Device Portal</span></span>](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > <span data-ttu-id="e6f08-289">由於這個方法需要在裝置上啟用開發人員模式，因此我們建議您僅將它用於示範。</span><span class="sxs-lookup"><span data-stu-id="e6f08-289">Because this method requires that Developer Mode be enabled on the device, we recommend that you use it only for demonstrations.</span></span>

<span data-ttu-id="e6f08-290">下表列出每個部署方法的功能和優點。</span><span class="sxs-lookup"><span data-stu-id="e6f08-290">The following table lists the capabilities and benefits of each of the deployment methods.</span></span>

| &nbsp; |<span data-ttu-id="e6f08-291">使用 Windows Device Portal 進行部署</span><span class="sxs-lookup"><span data-stu-id="e6f08-291">Deploy by using Windows Device Portal</span></span> |<span data-ttu-id="e6f08-292">使用預配套件進行部署</span><span class="sxs-lookup"><span data-stu-id="e6f08-292">Deploy by using a provisioning package</span></span> |<span data-ttu-id="e6f08-293">使用 MDM 部署</span><span class="sxs-lookup"><span data-stu-id="e6f08-293">Deploy by using MDM</span></span> |
| --------------------------- | ------------- | -------------------- | ---- |
|<span data-ttu-id="e6f08-294">部署單一 app 網亭</span><span class="sxs-lookup"><span data-stu-id="e6f08-294">Deploy single-app kiosks</span></span>   | <span data-ttu-id="e6f08-295">是</span><span class="sxs-lookup"><span data-stu-id="e6f08-295">Yes</span></span>           | <span data-ttu-id="e6f08-296">是</span><span class="sxs-lookup"><span data-stu-id="e6f08-296">Yes</span></span>                  | <span data-ttu-id="e6f08-297">是</span><span class="sxs-lookup"><span data-stu-id="e6f08-297">Yes</span></span>  |
|<span data-ttu-id="e6f08-298">部署多應用程式亭</span><span class="sxs-lookup"><span data-stu-id="e6f08-298">Deploy multi-app kiosks</span></span>    | <span data-ttu-id="e6f08-299">否</span><span class="sxs-lookup"><span data-stu-id="e6f08-299">No</span></span>            | <span data-ttu-id="e6f08-300">是</span><span class="sxs-lookup"><span data-stu-id="e6f08-300">Yes</span></span>                  | <span data-ttu-id="e6f08-301">是</span><span class="sxs-lookup"><span data-stu-id="e6f08-301">Yes</span></span>  |
|<span data-ttu-id="e6f08-302">僅部署到本機裝置</span><span class="sxs-lookup"><span data-stu-id="e6f08-302">Deploy to local devices only</span></span> | <span data-ttu-id="e6f08-303">是</span><span class="sxs-lookup"><span data-stu-id="e6f08-303">Yes</span></span>           | <span data-ttu-id="e6f08-304">是</span><span class="sxs-lookup"><span data-stu-id="e6f08-304">Yes</span></span>                  | <span data-ttu-id="e6f08-305">否</span><span class="sxs-lookup"><span data-stu-id="e6f08-305">No</span></span>   |
|<span data-ttu-id="e6f08-306">使用開發人員模式進行部署</span><span class="sxs-lookup"><span data-stu-id="e6f08-306">Deploy by using Developer Mode</span></span> |<span data-ttu-id="e6f08-307">必要</span><span class="sxs-lookup"><span data-stu-id="e6f08-307">Required</span></span>       | <span data-ttu-id="e6f08-308">不需要</span><span class="sxs-lookup"><span data-stu-id="e6f08-308">Not required</span></span>            | <span data-ttu-id="e6f08-309">不需要</span><span class="sxs-lookup"><span data-stu-id="e6f08-309">Not required</span></span>   |
|<span data-ttu-id="e6f08-310">使用 Azure Active Directory (AAD) 進行部署</span><span class="sxs-lookup"><span data-stu-id="e6f08-310">Deploy by using Azure Active Directory (AAD)</span></span>  | <span data-ttu-id="e6f08-311">不需要</span><span class="sxs-lookup"><span data-stu-id="e6f08-311">Not required</span></span>            | <span data-ttu-id="e6f08-312">不需要</span><span class="sxs-lookup"><span data-stu-id="e6f08-312">Not required</span></span>                   | <span data-ttu-id="e6f08-313">必要</span><span class="sxs-lookup"><span data-stu-id="e6f08-313">Required</span></span>  |
|<span data-ttu-id="e6f08-314">自動部署</span><span class="sxs-lookup"><span data-stu-id="e6f08-314">Deploy automatically</span></span>      | <span data-ttu-id="e6f08-315">否</span><span class="sxs-lookup"><span data-stu-id="e6f08-315">No</span></span>            | <span data-ttu-id="e6f08-316">否</span><span class="sxs-lookup"><span data-stu-id="e6f08-316">No</span></span>                   | <span data-ttu-id="e6f08-317">是</span><span class="sxs-lookup"><span data-stu-id="e6f08-317">Yes</span></span>  |
|<span data-ttu-id="e6f08-318">部署速度</span><span class="sxs-lookup"><span data-stu-id="e6f08-318">Deployment speed</span></span>            | <span data-ttu-id="e6f08-319">高</span><span class="sxs-lookup"><span data-stu-id="e6f08-319">Fastest</span></span>       | <span data-ttu-id="e6f08-320">快速</span><span class="sxs-lookup"><span data-stu-id="e6f08-320">Fast</span></span>                 | <span data-ttu-id="e6f08-321">慢速</span><span class="sxs-lookup"><span data-stu-id="e6f08-321">Slow</span></span> |
|<span data-ttu-id="e6f08-322">在縮放時部署</span><span class="sxs-lookup"><span data-stu-id="e6f08-322">Deploy at scale</span></span> | <span data-ttu-id="e6f08-323">不建議使用</span><span class="sxs-lookup"><span data-stu-id="e6f08-323">Not recommended</span></span>    | <span data-ttu-id="e6f08-324">不建議使用</span><span class="sxs-lookup"><span data-stu-id="e6f08-324">Not recommended</span></span>        | <span data-ttu-id="e6f08-325">建議執行</span><span class="sxs-lookup"><span data-stu-id="e6f08-325">Recommended</span></span> |

## <span data-ttu-id="e6f08-326">使用 Microsoft Intune 或其他 MDM 設定單一 app 或多重應用程式亭</span><span class="sxs-lookup"><span data-stu-id="e6f08-326">Use Microsoft Intune or other MDM to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="e6f08-327">若要使用 Microsoft Intune 或其他 MDM 系統來設定 kiosk 模式，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="e6f08-327">To set up kiosk mode by using Microsoft Intune or another MDM system, follow these steps.</span></span>

1. <span data-ttu-id="e6f08-328">[準備註冊裝置](#mdmenroll)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-328">[Prepare to enroll the devices](#mdmenroll).</span></span>
1. <span data-ttu-id="e6f08-329">[建立展臺設定檔](#mdmprofile)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-329">[Create a kiosk configuration profile](#mdmprofile).</span></span>
1. <span data-ttu-id="e6f08-330">設定 kiosk。</span><span class="sxs-lookup"><span data-stu-id="e6f08-330">Configure the kiosk.</span></span>
   - <span data-ttu-id="e6f08-331">[設定單一 app 展臺的設定](#mdmconfigsingle)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-331">[Configure the settings for a single-app kiosk](#mdmconfigsingle).</span></span>
   - <span data-ttu-id="e6f08-332">[設定多應用程式資訊站的設定](#mdmconfigmulti)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-332">[Configure the settings for a multi-app kiosk](#mdmconfigmulti).</span></span>
1. <span data-ttu-id="e6f08-333">[將 kiosk 配置設定檔指派給群組](#mdmassign)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-333">[Assign the kiosk configuration profile to a group](#mdmassign).</span></span>
1. <span data-ttu-id="e6f08-334">部署裝置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-334">Deploy the devices.</span></span>
   - <span data-ttu-id="e6f08-335">[部署單一應用程式亭](#mdmsingledeploy)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-335">[Deploy a single-app kiosk](#mdmsingledeploy).</span></span>
   - <span data-ttu-id="e6f08-336">[部署多應用程式亭](#mdmmultideploy)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-336">[Deploy a multi-app kiosk](#mdmmultideploy).</span></span>

### <a id="mdmenroll"></a><span data-ttu-id="e6f08-337">MDM，步驟 1 &ndash; 準備註冊裝置</span><span class="sxs-lookup"><span data-stu-id="e6f08-337">MDM, step 1 &ndash; Prepare to enroll the devices</span></span>

<span data-ttu-id="e6f08-338">您可以設定您的 MDM 系統在使用者第一次登入時自動登記 HoloLens 裝置，或讓使用者手動註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-338">You can configure your MDM system to enroll HoloLens devices automatically when the user first signs in, or have users enroll devices manually.</span></span> <span data-ttu-id="e6f08-339">裝置也必須加入到 Azure AD 網域，並指派給適當的群組。</span><span class="sxs-lookup"><span data-stu-id="e6f08-339">The devices also have to be joined to your Azure AD domain, and assigned to the appropriate groups.</span></span>

<span data-ttu-id="e6f08-340">如需有關如何註冊裝置的詳細資訊，請參閱在[Windows 裝置的 MDM 和 Intune 註冊方法](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)[中註冊 HoloLens](hololens-enroll-mdm.md) 。</span><span class="sxs-lookup"><span data-stu-id="e6f08-340">For more information about how to enroll the devices, see [Enroll HoloLens in MDM](hololens-enroll-mdm.md) and [Intune enrollment methods for Windows devices](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods).</span></span>

### <a id="mdmprofile"></a><span data-ttu-id="e6f08-341">MDM，步驟 2 &ndash; 建立 kiosk 配置設定檔</span><span class="sxs-lookup"><span data-stu-id="e6f08-341">MDM, step 2 &ndash; Create a kiosk configuration profile</span></span>

1. <span data-ttu-id="e6f08-342">開啟 [Azure](https://portal.azure.com/) 入口網站，並登入您的 Intune 系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="e6f08-342">Open the [Azure](https://portal.azure.com/) portal and sign in to your Intune administrator account.</span></span>
1. <span data-ttu-id="e6f08-343">選取 [ **Microsoft Intune**裝置設定]-[設定檔]  >  **Device configuration - Profiles**  >  **建立設定檔**。</span><span class="sxs-lookup"><span data-stu-id="e6f08-343">Select **Microsoft Intune** > **Device configuration - Profiles** > **Create profile**.</span></span>
1. <span data-ttu-id="e6f08-344">輸入設定檔名稱。</span><span class="sxs-lookup"><span data-stu-id="e6f08-344">Enter a profile name.</span></span>
1. <span data-ttu-id="e6f08-345">選取 [**平臺**  >  **Windows 10 及更新版本**]，然後選取 [**配置檔案類型**  > **裝置限制**]。</span><span class="sxs-lookup"><span data-stu-id="e6f08-345">Select **Platform** > **Windows 10 and later**, and then select **Profile type** >**Device restrictions**.</span></span>
1. <span data-ttu-id="e6f08-346">選取 [**設定**  >  **Kiosk**]，然後選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="e6f08-346">Select **Configure** > **Kiosk**, and then select one of the following:</span></span>
   - <span data-ttu-id="e6f08-347">若要建立單一應用程式亭，請選取 [**展臺模式**  >  **單一應用程式亭**]。</span><span class="sxs-lookup"><span data-stu-id="e6f08-347">To create a single-app kiosk, select **Kiosk Mode** > **Single-app kiosk**.</span></span>
   - <span data-ttu-id="e6f08-348">若要建立多重應用程式亭，請選取 [**展臺模式**  >  **多重應用程式資訊站**]。</span><span class="sxs-lookup"><span data-stu-id="e6f08-348">To create a multi-app kiosk, select **Kiosk Mode** > **Multi-app kiosk**.</span></span>
1. <span data-ttu-id="e6f08-349">若要開始配置資訊亭，請選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="e6f08-349">To start configuring the kiosk, select **Add**.</span></span>

<span data-ttu-id="e6f08-350">根據您想要的展臺類型，後續步驟會有所不同。</span><span class="sxs-lookup"><span data-stu-id="e6f08-350">Your next steps differ depending on the type of kiosk that you want.</span></span> <span data-ttu-id="e6f08-351">如需詳細資訊，請選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="e6f08-351">For more information, select one of the following options:</span></span>  

- [<span data-ttu-id="e6f08-352">單一應用程式資訊站</span><span class="sxs-lookup"><span data-stu-id="e6f08-352">Single-app kiosk</span></span>](#mdmconfigsingle)
- [<span data-ttu-id="e6f08-353">多應用程式亭</span><span class="sxs-lookup"><span data-stu-id="e6f08-353">Multi-app kiosk</span></span>](#mdmconfigmulti)

<span data-ttu-id="e6f08-354">如需如何建立 kiosk 配置設定檔的詳細資訊，請參閱 [windows 10 和 Windows 全息企業版裝置設定，以使用 Intune 作為專用的展臺執行](https://docs.microsoft.com/intune/configuration/kiosk-settings)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-354">For more information about how to create a kiosk configuration profile, see [Windows 10 and Windows Holographic for Business device settings to run as a dedicated kiosk using Intune](https://docs.microsoft.com/intune/configuration/kiosk-settings).</span></span>

### <a id="mdmconfigsingle"></a><span data-ttu-id="e6f08-355">MDM、步驟 3 (單 app) &ndash;  設定單一 app 展臺的設定</span><span class="sxs-lookup"><span data-stu-id="e6f08-355">MDM, step 3 (single-app) &ndash;  Configure the settings for a single-app kiosk</span></span>

<span data-ttu-id="e6f08-356">本節摘要說明單一 app 展臺所需的設定。</span><span class="sxs-lookup"><span data-stu-id="e6f08-356">This section summarizes the settings that a single-app kiosk requires.</span></span> <span data-ttu-id="e6f08-357">如需詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="e6f08-357">For more details, see the following articles:</span></span>

- <span data-ttu-id="e6f08-358">如需如何在 Intune 中設定 kiosk 設定檔的相關資訊，請參閱 [如何使用 Microsoft Intune 設定 Kiosk 模式](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-358">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="e6f08-359">如需 Intune 中單一 app 亭可用設定的詳細資訊，請參閱 [單一全螢幕 app 網亭](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)</span><span class="sxs-lookup"><span data-stu-id="e6f08-359">For more information about the available settings for single-app kiosks in Intune, see [Single full-screen app kiosks](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)</span></span>
- <span data-ttu-id="e6f08-360">如需其他 MDM 服務，請參閱提供者文件中的指示。</span><span class="sxs-lookup"><span data-stu-id="e6f08-360">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="e6f08-361">如果您必須在 MDM 服務中使用自訂 XML 配置來設定展臺，請 [建立定義 kiosk 配置的 XML](#ppkioskconfig)檔案。</span><span class="sxs-lookup"><span data-stu-id="e6f08-361">If you have to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span>

1. <span data-ttu-id="e6f08-362">選取 [**使用者登**  >  入類型（**本機使用者帳戶**）]，然後輸入本機 (裝置) 帳戶或 Microsoft 帳戶的使用者名稱，即可登入資訊站 (MSA) 。</span><span class="sxs-lookup"><span data-stu-id="e6f08-362">Select **User logon type** > **Local user account**, and then enter the user name of the local (device) account or Microsoft Account (MSA) that can sign in to the kiosk.</span></span>
   > [!NOTE]  
   > <span data-ttu-id="e6f08-363">Windows 全息企業版不支援**自動登入**使用者帳戶類型。</span><span class="sxs-lookup"><span data-stu-id="e6f08-363">**Autologon** user account types aren't supported on Windows Holographic for Business.</span></span>
1. <span data-ttu-id="e6f08-364">選取 [**應用程式類型**  >  **存儲應用**程式]，然後從清單中選取一個應用程式。</span><span class="sxs-lookup"><span data-stu-id="e6f08-364">Select **Application type** > **Store app**, and then select an app from the list.</span></span>

<span data-ttu-id="e6f08-365">下一步是將設定檔 [指派](#mdmassign) 給群組。</span><span class="sxs-lookup"><span data-stu-id="e6f08-365">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a id="mdmconfigmulti"></a><span data-ttu-id="e6f08-366">MDM、步驟 3 (多重 app) &ndash; 設定多應用程式資訊站的設定</span><span class="sxs-lookup"><span data-stu-id="e6f08-366">MDM, step 3 (multi-app) &ndash; Configure the settings for a multi-app kiosk</span></span>

<span data-ttu-id="e6f08-367">本節摘要說明多應用程式亭所需的設定。</span><span class="sxs-lookup"><span data-stu-id="e6f08-367">This section summarizes the settings that a multi-app kiosk requires.</span></span> <span data-ttu-id="e6f08-368">如需詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="e6f08-368">For more detailed information, see the following articles:</span></span>

- <span data-ttu-id="e6f08-369">如需如何在 Intune 中設定 kiosk 設定檔的相關資訊，請參閱 [如何使用 Microsoft Intune 設定 Kiosk 模式](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-369">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="e6f08-370">如需 Intune 中多個 app 網亭可用設定的詳細資訊，請參閱 [多重 app 網亭](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)</span><span class="sxs-lookup"><span data-stu-id="e6f08-370">For more information about the available settings for multi-app kiosks in Intune, see [Multi-app kiosks](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)</span></span>
- <span data-ttu-id="e6f08-371">如需其他 MDM 服務，請參閱提供者文件中的指示。</span><span class="sxs-lookup"><span data-stu-id="e6f08-371">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="e6f08-372">如果您需要在 MDM 服務中使用自訂 XML 設定來設定展臺，請 [建立定義 kiosk 配置的 XML](#ppkioskconfig)檔案。</span><span class="sxs-lookup"><span data-stu-id="e6f08-372">If you need to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span> <span data-ttu-id="e6f08-373">如果您使用 XML 檔案，請務必包含 [「開始」版面](#start-layout-for-hololens)配置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-373">If you use an XML file, make sure to include the [Start layout](#start-layout-for-hololens).</span></span>  
- <span data-ttu-id="e6f08-374">您也可以選擇在 Intune 或其他 MDM 服務中使用自訂開始配置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-374">You can optionally use a custom Start layout with Intune or other MDM services.</span></span> <span data-ttu-id="e6f08-375">如需詳細資訊，請參閱 [ (Intune 的 [啟動版面配置檔案] 和其他) ](#start-layout-file-for-mdm-intune-and-others)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-375">For more information, see [Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

1. <span data-ttu-id="e6f08-376">選取 [**在 S 模式裝置中以 Windows 10 為目標]**  >  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="e6f08-376">Select **Target Windows 10 in S mode devices** > **No**.</span></span>  
   >[!NOTE]  
   > <span data-ttu-id="e6f08-377">在商務用 Windows 全息版中不支援 S 模式。</span><span class="sxs-lookup"><span data-stu-id="e6f08-377">S mode isn't supported on Windows Holographic for Business.</span></span>
1. <span data-ttu-id="e6f08-378">選取 [**使用者登入類型**  >  **Azure AD 使用者或群組**或**使用者登入類型**  >  **HoloLens 訪客**]，然後新增一個或多個使用者群組或帳戶。</span><span class="sxs-lookup"><span data-stu-id="e6f08-378">Select **User logon type** > **Azure AD user or group** or **User logon type** > **HoloLens visitor**, and then add one or more user groups or accounts.</span></span>  

   <span data-ttu-id="e6f08-379">只有屬於您在 [ **使用者登入類型** ] 中指定之群組或帳戶的使用者，才能使用 kiosk 體驗。</span><span class="sxs-lookup"><span data-stu-id="e6f08-379">Only users who belong to the groups or accounts that you specify in **User logon type** can use the kiosk experience.</span></span>

1. <span data-ttu-id="e6f08-380">使用下列選項選取一或多個應用程式：</span><span class="sxs-lookup"><span data-stu-id="e6f08-380">Select one or more apps by using the following options:</span></span>
   - <span data-ttu-id="e6f08-381">若要新增已上傳的商務用應用程式，請選取 [ **新增 store app** ]，然後選取您要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e6f08-381">To add an uploaded line-of-business app, select **Add store app** and then select the app that you want.</span></span>
   - <span data-ttu-id="e6f08-382">若要新增應用程式，請指定其 AUMID，選取 [ **由 AUMID 新增** ]，然後輸入 APP 的 AUMID。</span><span class="sxs-lookup"><span data-stu-id="e6f08-382">To add an app by specifying its AUMID, select **Add by AUMID** and then enter the AUMID of the app.</span></span> [<span data-ttu-id="e6f08-383">請參閱可用的 Aumid 清單</span><span class="sxs-lookup"><span data-stu-id="e6f08-383">See the list of available AUMIDs</span></span>](#aumids)

<span data-ttu-id="e6f08-384">下一步是將設定檔 [指派](#mdmassign) 給群組。</span><span class="sxs-lookup"><span data-stu-id="e6f08-384">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a id="mdmassign"></a><span data-ttu-id="e6f08-385">MDM，步驟 4 &ndash; 將 kiosk 配置設定檔指派給群組</span><span class="sxs-lookup"><span data-stu-id="e6f08-385">MDM, step 4 &ndash; Assign the kiosk configuration profile to a group</span></span>

<span data-ttu-id="e6f08-386">使用 kiosk 配置設定檔的 [ **作業** ] 頁面，設定您想要的 kiosk 配置部署位置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-386">Use the **Assignments** page of the kiosk configuration profile to set where you want the kiosk configuration to deploy.</span></span> <span data-ttu-id="e6f08-387">在最簡單的情況下，您會將 kiosk 配置設定檔指派給將裝置在 MDM 中註冊時將包含 HoloLens 裝置的群組。</span><span class="sxs-lookup"><span data-stu-id="e6f08-387">In the simplest case, you assign the kiosk configuration profile to a group that will contain the HoloLens device when the device enrolls in MDM.</span></span>

### <a id="mdmsingledeploy"></a><span data-ttu-id="e6f08-388">MDM、步驟 5 (單一 app) &ndash; 部署單一應用程式亭</span><span class="sxs-lookup"><span data-stu-id="e6f08-388">MDM, step 5 (single-app) &ndash; Deploy a single-app kiosk</span></span>

<span data-ttu-id="e6f08-389">當您使用 MDM 系統時，您可以在 OOBE 期間在 MDM 中註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-389">When you use an MDM system, you can enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="e6f08-390">在 OOBE 完成之後，登入裝置很簡單。</span><span class="sxs-lookup"><span data-stu-id="e6f08-390">After OOBE finishes, signing in to the device is easy.</span></span>

<span data-ttu-id="e6f08-391">在 OOBE 期間，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e6f08-391">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="e6f08-392">使用您在 kiosk 配置設定檔中指定的帳號登入。</span><span class="sxs-lookup"><span data-stu-id="e6f08-392">Sign in by using the account that you specified in the kiosk configuration profile.</span></span>
1. <span data-ttu-id="e6f08-393">註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-393">Enroll the device.</span></span> <span data-ttu-id="e6f08-394">確認裝置已新增到指派給它的群組。</span><span class="sxs-lookup"><span data-stu-id="e6f08-394">Make sure that the device is added to the group that the kiosk configuration profile is assigned to.</span></span>
1. <span data-ttu-id="e6f08-395">等待 OOBE 完成，針對要下載並安裝的 microsoft store 應用程式，以及要套用的原則。</span><span class="sxs-lookup"><span data-stu-id="e6f08-395">Wait for OOBE to finish, for the store app to download and install, and for policies to be applied.</span></span> <span data-ttu-id="e6f08-396">然後重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-396">Then restart the device.</span></span>

<span data-ttu-id="e6f08-397">下次登入裝置時，kiosk app 就會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="e6f08-397">The next time you sign in to the device, the kiosk app should automatically start.</span></span>

<span data-ttu-id="e6f08-398">如果此時沒有看到您的展臺設定，請 [檢查作業狀態](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-398">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

### <a id="mdmmultideploy"></a><span data-ttu-id="e6f08-399">MDM、步驟 5 (多重 app) &ndash; 部署多應用程式亭</span><span class="sxs-lookup"><span data-stu-id="e6f08-399">MDM, step 5 (multi-app) &ndash; Deploy a multi-app kiosk</span></span>

<span data-ttu-id="e6f08-400">當您使用 MDM 系統時，您可以將裝置加入到 Azure AD 租使用者，並在 OOBE 期間在 MDM 中註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-400">When you use an MDM system, you can join the device to your Azure AD tenant and enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="e6f08-401">如有需要，請將註冊資訊提供給使用者，讓他們可以在 OOBE 程式中使用。</span><span class="sxs-lookup"><span data-stu-id="e6f08-401">If appropriate, provide the enrollment information to the users so that they have it available during the OOBE process.</span></span>

> [!NOTE]  
> <span data-ttu-id="e6f08-402">如果您已將 kiosk 配置設定檔指派給包含使用者的群組，請確認其中一個使用者帳戶是第一個登入裝置的帳戶。</span><span class="sxs-lookup"><span data-stu-id="e6f08-402">If you have assigned the kiosk configuration profile to a group that contains users, make sure that one of those user accounts is the first account to sign in to the device.</span></span>

<span data-ttu-id="e6f08-403">在 OOBE 期間，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e6f08-403">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="e6f08-404">使用屬於 [ **使用者登入類型** ] 群組的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="e6f08-404">Sign in by using the account that belongs to the **User logon type** group.</span></span>
1. <span data-ttu-id="e6f08-405">註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-405">Enroll the device.</span></span>
1. <span data-ttu-id="e6f08-406">等待任何屬於 kiosk 配置設定檔的 app 下載並安裝。</span><span class="sxs-lookup"><span data-stu-id="e6f08-406">Wait for any apps that are part of the kiosk configuration profile to download and install.</span></span> <span data-ttu-id="e6f08-407">此外，請等待應用原則。</span><span class="sxs-lookup"><span data-stu-id="e6f08-407">Also, wait for policies to be applied.</span></span>  
1. <span data-ttu-id="e6f08-408">在 OOBE 完成之後，您可以從 Microsoft 網上商店或邊載安裝其他 app。</span><span class="sxs-lookup"><span data-stu-id="e6f08-408">After OOBE finishes, you can install additional apps from the Microsoft store or by sideloading.</span></span> <span data-ttu-id="e6f08-409">裝置所歸屬的群組自動安裝[所需的應用程式](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-409">[Required apps](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) for the group that the device belongs to install automatically.</span></span>
1. <span data-ttu-id="e6f08-410">安裝完成後，請重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-410">After the installation finishes, restart the device.</span></span>

<span data-ttu-id="e6f08-411">下次您使用屬於 **使用者登入類型**的帳戶登入裝置時，kiosk app 應該會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="e6f08-411">The next time you sign in to the device by using an account that belongs to the **User logon type**, the kiosk app should automatically launch.</span></span>

<span data-ttu-id="e6f08-412">如果此時沒有看到您的展臺設定，請 [檢查作業狀態](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-412">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

## <span data-ttu-id="e6f08-413">使用預配套件來設定單一 app 或多重應用程式亭</span><span class="sxs-lookup"><span data-stu-id="e6f08-413">Use a provisioning package to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="e6f08-414">若要使用預配套件設定 kiosk 模式，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="e6f08-414">To set up kiosk mode by using a provisioning package, follow these steps.</span></span>

1. <span data-ttu-id="e6f08-415">[建立定義 kiosk](#ppkioskconfig)設定的 XML 檔案，包括 [開始版面](#start-layout-for-hololens)配置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-415">[Create an XML file that defines the kiosk configuration.](#ppkioskconfig), including a [Start layout](#start-layout-for-hololens).</span></span>
2. [<span data-ttu-id="e6f08-416">將 XML 檔案新增至預配套件。</span><span class="sxs-lookup"><span data-stu-id="e6f08-416">Add the XML file to a provisioning package.</span></span>](#ppconfigadd)
3. [<span data-ttu-id="e6f08-417">將預配套件套用至 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="e6f08-417">Apply the provisioning package to HoloLens.</span></span>](#ppapply)

### <a id="ppkioskconfig"></a><span data-ttu-id="e6f08-418">預配套件，步驟 1 &ndash; 建立 kiosk 配置 XML 檔案</span><span class="sxs-lookup"><span data-stu-id="e6f08-418">Provisioning package, step 1 &ndash; Create a kiosk configuration XML file</span></span>

<span data-ttu-id="e6f08-419">依照 [一般指示，為 Windows 桌面建立 kiosk 配置 XML](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)檔案，除了下列情況：</span><span class="sxs-lookup"><span data-stu-id="e6f08-419">Follow [the general instructions to create a kiosk configuration XML file for Windows desktop](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file), except for the following:</span></span>

- <span data-ttu-id="e6f08-420">請勿在 Win32) 中加入傳統的 Windows 應用程式 (。</span><span class="sxs-lookup"><span data-stu-id="e6f08-420">Do not include Classic Windows applications (Win32).</span></span> <span data-ttu-id="e6f08-421">HoloLens 不支援這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="e6f08-421">HoloLens does not support these applications.</span></span>
- <span data-ttu-id="e6f08-422">使用適用于 HoloLens 的 [預留位置開始版面配置 XML](#start-layout-for-hololens) 。</span><span class="sxs-lookup"><span data-stu-id="e6f08-422">Use the [placeholder Start layout XML](#start-layout-for-hololens) for HoloLens.</span></span>
- <span data-ttu-id="e6f08-423">選用：新增來賓對 kiosk 設定的存取權</span><span class="sxs-lookup"><span data-stu-id="e6f08-423">Optional: Add guest access to the kiosk configuration</span></span>

#### <a id="ppkioskguest"></a><span data-ttu-id="e6f08-424">選用：新增來賓對 kiosk 設定的存取權</span><span class="sxs-lookup"><span data-stu-id="e6f08-424">Optional: Add guest access to the kiosk configuration</span></span>

<span data-ttu-id="e6f08-425">在 XML 檔案的 [配置] [ **Configs**區段](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)中，您可以將名為「**訪客**」的特殊群組設定為允許來賓使用資訊站。</span><span class="sxs-lookup"><span data-stu-id="e6f08-425">In the [**Configs** section of the XML file](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs), you can configure a special group named **Visitor** to allow guests to use the kiosk.</span></span> <span data-ttu-id="e6f08-426">如果將 kiosk 設定為支援 **「訪客特殊」** 群組，則會在登入頁面中新增「**來賓**」選項。</span><span class="sxs-lookup"><span data-stu-id="e6f08-426">When the kiosk is configured to support the **Visitor** special group, a "**Guest**" option is added to the sign-in page.</span></span> <span data-ttu-id="e6f08-427">**來賓**帳戶不需要密碼，而且與該帳戶相關聯的任何資料都會在帳戶登出時刪除。</span><span class="sxs-lookup"><span data-stu-id="e6f08-427">The **Guest** account does not require a password, and any data that is associated with the account is deleted when the account signs out.</span></span>

<span data-ttu-id="e6f08-428">若要啟用 **來賓** 帳戶，請將下列程式碼片段新增至您的 KIOSK 配置 XML：</span><span class="sxs-lookup"><span data-stu-id="e6f08-428">To enable the **Guest** account, add the following snippet to your kiosk configuration XML:</span></span>

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a><span data-ttu-id="e6f08-429">HoloLens 的預留位置開始時間版面配置</span><span class="sxs-lookup"><span data-stu-id="e6f08-429">Placeholder Start layout for HoloLens</span></span>

<span data-ttu-id="e6f08-430">如果您使用 [預配套件](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 來設定多應用程式資訊站，程式需要開始版面配置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-430">If you use a [provisioning package](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) to configure a multi-app kiosk, the procedure requires a Start layout.</span></span> <span data-ttu-id="e6f08-431">在商務用 Windows 全息版中不支援開始進行版面配置自訂。</span><span class="sxs-lookup"><span data-stu-id="e6f08-431">Start layout customization isn't supported in Windows Holographic for Business.</span></span> <span data-ttu-id="e6f08-432">因此，您必須使用預留位置 [開始] 版面配置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-432">Therefore, you'll have to use a placeholder Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="e6f08-433">因為單一 app 展臺會在使用者登入時啟動展臺應用程式，所以它不會使用 [開始] 功能表，也不需要開始進行版面配置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-433">Because a single-app kiosk starts the kiosk app when a user signs in, it does not use a Start menu and does not have to have a Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="e6f08-434">如果您使用 [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 來設定多個 app 的展臺，您可以選擇使用 [開始] 版面配置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-434">If you use [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) to set up a multi-app kiosk, you can optionally use a Start layout.</span></span> <span data-ttu-id="e6f08-435">如需詳細資訊，請參閱 [MDM (Intune 的 [預留位置啟動版面 ](#start-layout-file-for-mdm-intune-and-others)配置] 檔案，以及其他) 。</span><span class="sxs-lookup"><span data-stu-id="e6f08-435">For more information, see [Placeholder Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

<span data-ttu-id="e6f08-436">在 [開始] 版面配置中，將下列 **StartLayout** 區段新增至 KIOSK 提供 XML 檔案：</span><span class="sxs-lookup"><span data-stu-id="e6f08-436">For the Start layout, add the following **StartLayout** section to the kiosk provisioning XML file:</span></span>

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

#### <a id="start-layout-file-for-mdm-intune-and-others"></a><span data-ttu-id="e6f08-437">MDM (Intune 和其他人的預留位置啟動版面配置檔案) </span><span class="sxs-lookup"><span data-stu-id="e6f08-437">Placeholder Start layout file for MDM (Intune and others)</span></span>

<span data-ttu-id="e6f08-438">將下列範例儲存為 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="e6f08-438">Save the following sample as an XML file.</span></span> <span data-ttu-id="e6f08-439">您可以在 Microsoft (Intune 中設定多應用程式亭，或在提供 kiosk 設定檔的另一個 MDM 服務中，使用這個檔案) 。</span><span class="sxs-lookup"><span data-stu-id="e6f08-439">You can use this file when you configure the multi-app kiosk in Microsoft Intune (or in another MDM service that provides a kiosk profile).</span></span>

> [!NOTE]
> <span data-ttu-id="e6f08-440">如果您必須使用自訂設定及完整的 XML 配置來設定 MDM 服務中的展臺，請使用 [提供套件的開始配置指示](#start-layout-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-440">If you have to use a custom setting and full XML configuration to set up a kiosk in your MDM service, use the [Start layout instructions for a provisioning package](#start-layout-for-hololens).</span></span>

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

### <a id="ppconfigadd"></a><span data-ttu-id="e6f08-441">Prov.</span><span class="sxs-lookup"><span data-stu-id="e6f08-441">Prov.</span></span> <span data-ttu-id="e6f08-442">套件，步驟 2 &ndash; 將 kiosk 配置 XML 檔案新增至置備套件</span><span class="sxs-lookup"><span data-stu-id="e6f08-442">package, step 2 &ndash; Add the kiosk configuration XML file to a provisioning package</span></span>

1. <span data-ttu-id="e6f08-443">開啟 [Windows 配置設計](https://www.microsoft.com/store/apps/9nblggh4tx22)工具。</span><span class="sxs-lookup"><span data-stu-id="e6f08-443">Open [Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22).</span></span>
1. <span data-ttu-id="e6f08-444">選取 [ **高級提供**]，輸入您專案的名稱，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e6f08-444">Select **Advanced provisioning**, enter a name for your project, and then select **Next**.</span></span>
1. <span data-ttu-id="e6f08-445">選取 [ **Windows 10 全息**版]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e6f08-445">Select **Windows 10 Holographic**, and then select **Next**.</span></span>
1. <span data-ttu-id="e6f08-446">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="e6f08-446">Select **Finish**.</span></span> <span data-ttu-id="e6f08-447">套件的工作區就會開啟。</span><span class="sxs-lookup"><span data-stu-id="e6f08-447">The workspace for your package opens.</span></span>
1. <span data-ttu-id="e6f08-448">選取 [**執行時間設定**]  >  **AssignedAccess**[  >  **MultiAppAssignedAccessSettings**]。</span><span class="sxs-lookup"><span data-stu-id="e6f08-448">Select **Runtime settings** > **AssignedAccess** > **MultiAppAssignedAccessSettings**.</span></span>
1. <span data-ttu-id="e6f08-449">在中央窗格中，選取 **[流覽]** 以找出並選取您所建立的 KIOSK 配置 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="e6f08-449">In the center pane, select **Browse** to locate and select the kiosk configuration XML file that you created.</span></span>

   ![Windows 設定設計工具中 MultiAppAssignedAccessSettings 欄位的螢幕擷取畫面](./images/multiappassignedaccesssettings.png)

1. <span data-ttu-id="e6f08-451">**選用**。</span><span class="sxs-lookup"><span data-stu-id="e6f08-451">**Optional**.</span></span> <span data-ttu-id="e6f08-452"> (如果您想要在裝置的初始設定之後套用預配套件，且展臺裝置上已提供系統管理員使用者，請跳過此步驟。 ) 選取 [ **執行時間設定** &gt; **帳戶** &gt; **使用者**]，然後建立使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="e6f08-452">(If you want to apply the provisioning package after the initial setup of the device, and there is an admin user already available on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a user account.</span></span> <span data-ttu-id="e6f08-453">提供使用者名稱和密碼，然後選取 [ **UserGroup**系統  >  **管理員**]。</span><span class="sxs-lookup"><span data-stu-id="e6f08-453">Provide a user name and password, and then select **UserGroup** > **Administrators**.</span></span>  
  
     <span data-ttu-id="e6f08-454">您可以使用此帳戶來查看 [預配狀態與記錄]。</span><span class="sxs-lookup"><span data-stu-id="e6f08-454">By using this account, you can view the provisioning status and logs.</span></span>  
1. <span data-ttu-id="e6f08-455">**選用**。</span><span class="sxs-lookup"><span data-stu-id="e6f08-455">**Optional**.</span></span> <span data-ttu-id="e6f08-456"> (如果您在展臺裝置上已有非系統管理員帳戶，請跳過此步驟。 ) 選取 [ **執行時間設定** &gt; **帳戶** &gt; **使用者**]，然後建立本機使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="e6f08-456">(If you already have a non-admin account on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a local user account.</span></span> <span data-ttu-id="e6f08-457">請確定使用者名稱與您在配置 XML 中指定的帳號相同。</span><span class="sxs-lookup"><span data-stu-id="e6f08-457">Make sure that the user name is the same as for the account that you specify in the configuration XML.</span></span> <span data-ttu-id="e6f08-458">選取 [ **UserGroup**  >  **標準使用者**]。</span><span class="sxs-lookup"><span data-stu-id="e6f08-458">Select **UserGroup** > **Standard Users**.</span></span>
1. <span data-ttu-id="e6f08-459">選取 **[**  >  **儲存**檔案]。</span><span class="sxs-lookup"><span data-stu-id="e6f08-459">Select **File** > **Save**.</span></span>
1. <span data-ttu-id="e6f08-460">選取 [**匯出**  >  **預配套件**]，然後選取 [**擁有**者  >  **IT 系統管理員**]。這會將這個預配套件的優先順序設為高於從其他來源套用至此裝置的預配套件。</span><span class="sxs-lookup"><span data-stu-id="e6f08-460">Select **Export** > **Provisioning package**, and then select **Owner** > **IT Admin**. This sets the precedence of this provisioning package higher than provisioning packages that are applied to this device from other sources.</span></span>
1. <span data-ttu-id="e6f08-461">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="e6f08-461">Select **Next**.</span></span>
1. <span data-ttu-id="e6f08-462">在 [ **預配套件安全性** ] 頁面上，選取安全性選項。</span><span class="sxs-lookup"><span data-stu-id="e6f08-462">On the **Provisioning package security** page, select a security option.</span></span>
   > [!IMPORTANT]  
   > <span data-ttu-id="e6f08-463">如果您選取 [ **啟用套件簽署**]，您也必須選取要用來簽署套件的有效憑證。</span><span class="sxs-lookup"><span data-stu-id="e6f08-463">If you select **Enable package signing**, you also have to select a valid certificate to use for signing the package.</span></span> <span data-ttu-id="e6f08-464">若要這樣做，請選取 **[流覽]** ，然後選取您要用來簽署套件的憑證。</span><span class="sxs-lookup"><span data-stu-id="e6f08-464">To do this, select **Browse** and select the certificate that you want to use to sign the package.</span></span>
   
   > [!CAUTION]  
   > <span data-ttu-id="e6f08-465">請勿選取 [ **啟用套件加密**]。</span><span class="sxs-lookup"><span data-stu-id="e6f08-465">Do not select **Enable package encryption**.</span></span> <span data-ttu-id="e6f08-466">在 HoloLens 裝置上，此設定會導致置備失敗。</span><span class="sxs-lookup"><span data-stu-id="e6f08-466">On HoloLens devices, this setting causes provisioning to fail.</span></span>
1. <span data-ttu-id="e6f08-467">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="e6f08-467">Select **Next**.</span></span>
1. <span data-ttu-id="e6f08-468">指定要在建立預配套件時所要執行的輸出位置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-468">Specify the output location where you want the provisioning package to go when it's built.</span></span> <span data-ttu-id="e6f08-469">Windows 設定設計工具預設會使用專案資料夾做為輸出位置。</span><span class="sxs-lookup"><span data-stu-id="e6f08-469">By default, Windows Configuration Designer uses the project folder as the output location.</span></span> <span data-ttu-id="e6f08-470">如果您想要變更輸出位置，請選取 **[流覽]**。</span><span class="sxs-lookup"><span data-stu-id="e6f08-470">If you want to change the output location, select **Browse**.</span></span> <span data-ttu-id="e6f08-471">完成後，請選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e6f08-471">When you are finished, select **Next**.</span></span>
1. <span data-ttu-id="e6f08-472">選取 [ **組建** ]，開始建立套件。</span><span class="sxs-lookup"><span data-stu-id="e6f08-472">Select **Build** to start building the package.</span></span> <span data-ttu-id="e6f08-473">建置佈建套件並不需要很長的時間。</span><span class="sxs-lookup"><span data-stu-id="e6f08-473">The provisioning package doesn't take long to build.</span></span> <span data-ttu-id="e6f08-474">[建立] 頁面會顯示專案資訊，且進度列會指出組建狀態。</span><span class="sxs-lookup"><span data-stu-id="e6f08-474">The build page displays the project information, and the progress bar indicates the build status.</span></span>

### <a id="ppapply"></a><span data-ttu-id="e6f08-475">預配套件，步驟3會 &ndash; 將預配套件套用至 HoloLens</span><span class="sxs-lookup"><span data-stu-id="e6f08-475">Provisioning package, step 3 &ndash; Apply the provisioning package to HoloLens</span></span>

<span data-ttu-id="e6f08-476">「使用預配套件設定 HoloLens」一文提供在下列情況下套用預配套件的詳細指示：</span><span class="sxs-lookup"><span data-stu-id="e6f08-476">The "Configure HoloLens by using a provisioning package" article provides detailed instructions to apply the provisioning package under the following circumstances:</span></span>

- <span data-ttu-id="e6f08-477">您最初可以 [在安裝期間將預配套件套用到 HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-477">You can initially [apply a provisioning package to HoloLens during setup](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).</span></span>

- <span data-ttu-id="e6f08-478">您也可以 [在安裝完成後將預配套件套用至 HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-478">You can also [apply a provisioning package to HoloLens after setup](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup).</span></span>

## <span data-ttu-id="e6f08-479">使用 Windows Device Portal 設定單一應用程式亭</span><span class="sxs-lookup"><span data-stu-id="e6f08-479">Use the Windows Device Portal to set up a single-app kiosk</span></span>

<span data-ttu-id="e6f08-480">若要使用 Windows Device Portal 設定 kiosk 模式，請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="e6f08-480">To set up kiosk mode by using the Windows Device Portal, follow these steps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6f08-481">[展臺模式] 只有在裝置已安裝 [Windows 全息企業](hololens1-upgrade-enterprise.md) 版時才能使用。</span><span class="sxs-lookup"><span data-stu-id="e6f08-481">Kiosk mode is available only if the device has [Windows Holographic for Business](hololens1-upgrade-enterprise.md) installed.</span></span>

1. <span data-ttu-id="e6f08-482">[設定 HoloLens 裝置以使用 Windows Device Portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-482">[Set up the HoloLens device to use the Windows Device Portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal).</span></span> <span data-ttu-id="e6f08-483">Device Portal 是您 HoloLens 上的網頁伺服器，您可以從電腦上的網頁瀏覽器與它連線。</span><span class="sxs-lookup"><span data-stu-id="e6f08-483">The Device Portal is a web server on your HoloLens that you can connect to from a web browser on your PC.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="e6f08-484">當您將 HoloLens 設定為使用 Device Portal 時，必須在裝置上啟用 [開發人員模式]。</span><span class="sxs-lookup"><span data-stu-id="e6f08-484">When you set up HoloLens to use the Device Portal, you have to enable Developer Mode on the device.</span></span> <span data-ttu-id="e6f08-485">Windows 全息版裝置上的開發人員模式可讓您使用側載入 app。</span><span class="sxs-lookup"><span data-stu-id="e6f08-485">Developer Mode on a device that has Windows Holographic for Business enables you to side-load apps.</span></span> <span data-ttu-id="e6f08-486">不過，此設定會建立使用者可安裝未透過 Microsoft Store 認證之 app 的風險。</span><span class="sxs-lookup"><span data-stu-id="e6f08-486">However, this setting creates a risk that a user can install apps that have not been certified by the Microsoft Store.</span></span> <span data-ttu-id="e6f08-487">系統管理員可以使用[原則 CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)中的**ApplicationManagement/AllowDeveloper 解除鎖定**設定，來封鎖啟用開發人員模式的功能。</span><span class="sxs-lookup"><span data-stu-id="e6f08-487">Administrators can block the ability to enable Developer Mode by using the **ApplicationManagement/AllowDeveloper Unlock** setting in the [Policy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider).</span></span> [<span data-ttu-id="e6f08-488">深入了解開發人員模式。</span><span class="sxs-lookup"><span data-stu-id="e6f08-488">Learn more about Developer Mode.</span></span>](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. <span data-ttu-id="e6f08-489">在電腦上，使用 [wi-fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) 或 [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)連接至 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="e6f08-489">On a computer, connect to the HoloLens by using [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) or [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb).</span></span>

1. <span data-ttu-id="e6f08-490">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="e6f08-490">Do one of the following:</span></span>
   - <span data-ttu-id="e6f08-491">如果您是第一次連線到 Windows Device Portal，請 [建立使用者名稱和密碼](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)</span><span class="sxs-lookup"><span data-stu-id="e6f08-491">If you are connecting to the Windows Device Portal for the first time, [create a user name and password](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)</span></span>
   - <span data-ttu-id="e6f08-492">輸入您先前設定的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="e6f08-492">Enter the user name and password that you previously set up.</span></span>

    > [!TIP]
    > <span data-ttu-id="e6f08-493">如果您在瀏覽器中看到憑證有誤，請遵循[下列疑難排解步驟](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)。</span><span class="sxs-lookup"><span data-stu-id="e6f08-493">If you see a certificate error in the browser, follow [these troubleshooting steps](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate).</span></span>

1. <span data-ttu-id="e6f08-494">在 Windows Device Portal 中，選取 [ **展臺模式]**。</span><span class="sxs-lookup"><span data-stu-id="e6f08-494">In the Windows Device Portal, select **Kiosk Mode**.</span></span>

1. <span data-ttu-id="e6f08-495">選取 [ **啟用 Kiosk 模式]**，選取裝置啟動時要執行的應用程式，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="e6f08-495">Select **Enable Kiosk Mode**, select an app to run when the device starts, and then select **Save**.</span></span>

    ![Kiosk 模式](images/kiosk.png)
1. <span data-ttu-id="e6f08-497">重新開機 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="e6f08-497">Restart HoloLens.</span></span> <span data-ttu-id="e6f08-498">如果您仍開啟了 [裝置入口網站] 頁面，您可以選取頁面頂端的 [ **重新開機** ]。</span><span class="sxs-lookup"><span data-stu-id="e6f08-498">If you still have your Device Portal page open, you can select **Restart** at the top of the page.</span></span>

## <span data-ttu-id="e6f08-499">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="e6f08-499">More information</span></span>

<span data-ttu-id="e6f08-500">瞭解如何使用預配套件來設定展臺。</span><span class="sxs-lookup"><span data-stu-id="e6f08-500">Watch how to configure a kiosk by using a provisioning package.</span></span>  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]
