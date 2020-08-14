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
ms.openlocfilehash: f5c45477ab33064afe30e275f8b0003bc6022eac
ms.sourcegitcommit: bdbaed42dd9ecbd0ed9517de2e98a0465f584c1d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "10929849"
---
# <span data-ttu-id="30f40-103">設定 HoloLens (第 1 代) 的 kiosk</span><span class="sxs-lookup"><span data-stu-id="30f40-103">Set up HoloLens as a kiosk</span></span>

<span data-ttu-id="30f40-104">您可以將 HoloLens 裝置設定為固定用途的裝置（亦稱為 *kiosk*），方法是將裝置設定為在 kiosk 模式中執行。</span><span class="sxs-lookup"><span data-stu-id="30f40-104">You can configure a HoloLens device to function as a fixed-purpose device, also called a *kiosk*, by configuring the device to run in kiosk mode.</span></span> <span data-ttu-id="30f40-105">展臺模式會限制裝置上可用的應用程式 (或使用者) 。</span><span class="sxs-lookup"><span data-stu-id="30f40-105">Kiosk mode limits the applications (or users) that are available on the device.</span></span> <span data-ttu-id="30f40-106">Kiosk 模式是一種便利的功能，您可以用來將 HoloLens 裝置專用於商務應用程式，或在應用程式示範中使用 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="30f40-106">Kiosk mode is a convenient feature that you can use to dedicate a HoloLens device to business apps, or to use the HoloLens device in an app demo.</span></span>

<span data-ttu-id="30f40-107">本文提供有關 HoloLens 裝置專用之 kiosk 設定的各個方面的資訊。</span><span class="sxs-lookup"><span data-stu-id="30f40-107">This article provides information about aspects of kiosk configuration that are specific to HoloLens devices.</span></span> <span data-ttu-id="30f40-108">如需不同類型的 Windows 網亭以及如何進行設定的一般資訊，請參閱 [在 windows 桌上出版上設定網亭和數位簽章](https://docs.microsoft.com/windows/configuration/kiosk-methods)。</span><span class="sxs-lookup"><span data-stu-id="30f40-108">For general information about the different types of Windows-based kiosks and how to configure them, see [Configure kiosks and digital signs on Windows desktop editions](https://docs.microsoft.com/windows/configuration/kiosk-methods).</span></span>  

> [!IMPORTANT]  
> <span data-ttu-id="30f40-109">Kiosk 模式決定使用者登入裝置時可使用哪些 app。</span><span class="sxs-lookup"><span data-stu-id="30f40-109">Kiosk mode determines which apps are available when a user signs in to the device.</span></span> <span data-ttu-id="30f40-110">不過，kiosk 模式不是安全性方法。</span><span class="sxs-lookup"><span data-stu-id="30f40-110">However, kiosk mode is not a security method.</span></span> <span data-ttu-id="30f40-111">它不會停止「允許」 app，無法開啟其他不允許的應用程式。</span><span class="sxs-lookup"><span data-stu-id="30f40-111">It does not stop an "allowed" app from opening another app that is not allowed.</span></span> <span data-ttu-id="30f40-112">為了封鎖 app 或進程的開啟，請使用 [Windows Defender 應用程式控制項 (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) 來建立適當的原則。</span><span class="sxs-lookup"><span data-stu-id="30f40-112">In order to block apps or processes from opening, use [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) to create appropriate policies.</span></span>  

<span data-ttu-id="30f40-113">您可以在單一 app 或多重應用程式設定中使用 kiosk 模式，而且您可以使用三個進程中的其中一個來設定和部署展臺設定。</span><span class="sxs-lookup"><span data-stu-id="30f40-113">You can use kiosk mode in either a single-app or a multi-app configuration, and you can use one of three processes to set up and deploy the kiosk configuration.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="30f40-114">刪除多重應用程式設定，會移除指派的存取功能所建立的使用者鎖定設定檔。</span><span class="sxs-lookup"><span data-stu-id="30f40-114">Deleting the multi-app configuration removes the user lockdown profiles that the assigned access feature created.</span></span> <span data-ttu-id="30f40-115">不過，它不會復原所有原則變更。</span><span class="sxs-lookup"><span data-stu-id="30f40-115">However, it does not revert all the policy changes.</span></span> <span data-ttu-id="30f40-116">若要復原這些原則，您必須將裝置重設成出廠設定。</span><span class="sxs-lookup"><span data-stu-id="30f40-116">To revert these policies, you have to reset the device to the factory settings.</span></span>

## <span data-ttu-id="30f40-117">規劃展臺部署</span><span class="sxs-lookup"><span data-stu-id="30f40-117">Plan the kiosk deployment</span></span>

### <span data-ttu-id="30f40-118">展臺模式需求</span><span class="sxs-lookup"><span data-stu-id="30f40-118">Kiosk mode requirements</span></span>

<span data-ttu-id="30f40-119">您可以將任何 HoloLens 2 裝置設定為使用 kiosk 模式。</span><span class="sxs-lookup"><span data-stu-id="30f40-119">You can configure any HoloLens 2 device to use kiosk mode.</span></span>

<span data-ttu-id="30f40-120">若要將 HoloLens (1 gen) 裝置設定為使用 kiosk 模式，您必須先確定裝置執行的是 Windows 10 版本1803或更新版本。</span><span class="sxs-lookup"><span data-stu-id="30f40-120">To configure a HoloLens (1st gen) device to use kiosk mode, you must first make sure that the device runs Windows 10, version 1803, or a later version.</span></span> <span data-ttu-id="30f40-121">如果您已使用 Windows 裝置恢復工具將 HoloLens (1 gen) 裝置復原為預設組建，或者如果您已安裝最新的更新，則您的裝置已準備好進行設定。</span><span class="sxs-lookup"><span data-stu-id="30f40-121">If you have used the Windows Device Recovery Tool to recover your HoloLens (1st gen) device to its default build, or if you have installed the most recent updates, your device is ready to configure.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="30f40-122">若要協助保護在 kiosk 模式下執行的裝置，請考慮新增裝置管理原則，以關閉 USB 連線等功能。</span><span class="sxs-lookup"><span data-stu-id="30f40-122">To help protect devices that run in kiosk mode, consider adding device management policies that turn off features such as USB connectivity.</span></span> <span data-ttu-id="30f40-123">此外，請檢查您的 [更新鈴聲] 設定，以確定在上班時間期間不會進行自動更新。</span><span class="sxs-lookup"><span data-stu-id="30f40-123">Additionally, check your update ring settings to make sure that automatic updates do not occur during business hours.</span></span>

### <span data-ttu-id="30f40-124">在單一應用程式亭或多重應用程式亭之間進行決定</span><span class="sxs-lookup"><span data-stu-id="30f40-124">Decide between a single-app kiosk or a multi-app kiosk</span></span>

<span data-ttu-id="30f40-125">當使用者登入裝置時，單一 app 展臺會啟動指定的 app。</span><span class="sxs-lookup"><span data-stu-id="30f40-125">A single-app kiosk starts the specified app when the user signs in to the device.</span></span> <span data-ttu-id="30f40-126">[開始] 功能表停用，就像是 Cortana 一樣。</span><span class="sxs-lookup"><span data-stu-id="30f40-126">The Start menu is disabled, as is Cortana.</span></span> <span data-ttu-id="30f40-127">HoloLens 2 裝置沒有回應 [開始](hololens2-basic-usage.md#start-gesture) 手勢。</span><span class="sxs-lookup"><span data-stu-id="30f40-127">A HoloLens 2 device does not respond to the [Start](hololens2-basic-usage.md#start-gesture) gesture.</span></span> <span data-ttu-id="30f40-128">HoloLens (1 gen) 裝置不會回應 [bloom](hololens1-basic-usage.md) 手勢。</span><span class="sxs-lookup"><span data-stu-id="30f40-128">A HoloLens (1st gen) device does not respond to the [bloom](hololens1-basic-usage.md) gesture.</span></span> <span data-ttu-id="30f40-129">因為只有一個 app 可以執行，所以使用者無法放置其他應用程式。</span><span class="sxs-lookup"><span data-stu-id="30f40-129">Because only one app can run, the user cannot place other apps.</span></span>

<span data-ttu-id="30f40-130">多個應用程式站會在使用者登入裝置時顯示 [開始] 功能表。</span><span class="sxs-lookup"><span data-stu-id="30f40-130">A multi-app kiosk displays the Start menu when the user signs in to the device.</span></span> <span data-ttu-id="30f40-131">展臺設定會決定在 [開始] 功能表上可用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="30f40-131">The kiosk configuration determines which apps are available on the Start menu.</span></span> <span data-ttu-id="30f40-132">您可以使用多重應用程式亭，透過只向他們提供他們所需使用的專案，並移除不需要使用的專案，來為使用者提供易於理解的體驗。</span><span class="sxs-lookup"><span data-stu-id="30f40-132">You can use a multi-app kiosk to provide an easy-to-understand experience for users by presenting to them only the things that they have to use, and removing the things they don't need to use.</span></span>

<span data-ttu-id="30f40-133">下表列出不同資訊亭模式中的功能功能。</span><span class="sxs-lookup"><span data-stu-id="30f40-133">The following table lists the feature capabilities in the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="30f40-134">[開始] 功能表</span><span class="sxs-lookup"><span data-stu-id="30f40-134">Start menu</span></span> |<span data-ttu-id="30f40-135">[快速動作] 功能表</span><span class="sxs-lookup"><span data-stu-id="30f40-135">Quick Actions menu</span></span> |<span data-ttu-id="30f40-136">相機和影片</span><span class="sxs-lookup"><span data-stu-id="30f40-136">Camera and video</span></span> |<span data-ttu-id="30f40-137">Miracast</span><span class="sxs-lookup"><span data-stu-id="30f40-137">Miracast</span></span> |<span data-ttu-id="30f40-138">Cortana</span><span class="sxs-lookup"><span data-stu-id="30f40-138">Cortana</span></span> |<span data-ttu-id="30f40-139">內建語音命令</span><span class="sxs-lookup"><span data-stu-id="30f40-139">Built-in voice commands</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|<span data-ttu-id="30f40-140">單一應用程式資訊站</span><span class="sxs-lookup"><span data-stu-id="30f40-140">Single-app kiosk</span></span> |<span data-ttu-id="30f40-141">已停用</span><span class="sxs-lookup"><span data-stu-id="30f40-141">Disabled</span></span> |<span data-ttu-id="30f40-142">已停用</span><span class="sxs-lookup"><span data-stu-id="30f40-142">Disabled</span></span>   |<span data-ttu-id="30f40-143">已停用</span><span class="sxs-lookup"><span data-stu-id="30f40-143">Disabled</span></span> |<span data-ttu-id="30f40-144">已停用</span><span class="sxs-lookup"><span data-stu-id="30f40-144">Disabled</span></span>   |<span data-ttu-id="30f40-145">已停用</span><span class="sxs-lookup"><span data-stu-id="30f40-145">Disabled</span></span> |<span data-ttu-id="30f40-146">已啟用 <sup> 1</span><span class="sxs-lookup"><span data-stu-id="30f40-146">Enabled<sup>1</span></span></sup> |
|<span data-ttu-id="30f40-147">多應用程式亭</span><span class="sxs-lookup"><span data-stu-id="30f40-147">Multi-app kiosk</span></span> |<span data-ttu-id="30f40-148">啟用</span><span class="sxs-lookup"><span data-stu-id="30f40-148">Enabled</span></span> |<span data-ttu-id="30f40-149">已啟用 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="30f40-149">Enabled<sup>2</span></span></sup> |<span data-ttu-id="30f40-150">可用 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="30f40-150">Available<sup>2</span></span></sup> |<span data-ttu-id="30f40-151">可用 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="30f40-151">Available<sup>2</span></span></sup> |<span data-ttu-id="30f40-152">可用 <sup> 2、3</span><span class="sxs-lookup"><span data-stu-id="30f40-152">Available<sup>2, 3</span></span></sup>  |<span data-ttu-id="30f40-153">已啟用 <sup> 1</span><span class="sxs-lookup"><span data-stu-id="30f40-153">Enabled<sup>1</span></span></sup> |

> <sup><span data-ttu-id="30f40-154">1與 </sup> 停用功能相關的語音命令無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="30f40-154">1</sup> Voice commands that relate to disabled features do not function.</span></span>  
> <sup><span data-ttu-id="30f40-155">2 </sup> 如需如何設定這些功能的詳細資訊，請參閱 [選取 kiosk app](#plan-kiosk-apps)。</span><span class="sxs-lookup"><span data-stu-id="30f40-155">2</sup> For more information about how to configure these features, see [Select kiosk apps](#plan-kiosk-apps).</span></span>  
> <sup><span data-ttu-id="30f40-156">3 </sup> 即使已停用 Cortana，仍會啟用內建語音命令。</span><span class="sxs-lookup"><span data-stu-id="30f40-156">3</sup> Even if Cortana is disabled, the built-in voice commands are enabled.</span></span>

<span data-ttu-id="30f40-157">下表列出不同 kiosk 模式的使用者支援功能。</span><span class="sxs-lookup"><span data-stu-id="30f40-157">The following table lists the user support features of the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="30f40-158">支援的使用者類型</span><span class="sxs-lookup"><span data-stu-id="30f40-158">Supported user types</span></span> | <span data-ttu-id="30f40-159">自動登入</span><span class="sxs-lookup"><span data-stu-id="30f40-159">Automatic sign-in</span></span> | <span data-ttu-id="30f40-160">多個存取層級</span><span class="sxs-lookup"><span data-stu-id="30f40-160">Multiple access levels</span></span> |
| --- | --- | --- | --- |
|<span data-ttu-id="30f40-161">單一應用程式資訊站</span><span class="sxs-lookup"><span data-stu-id="30f40-161">Single-app kiosk</span></span> |<span data-ttu-id="30f40-162">受管理的服務帳戶 (Azure Active Directory (AAD) 或本機帳戶中的 MSA) </span><span class="sxs-lookup"><span data-stu-id="30f40-162">Managed Service Account (MSA) in Azure Active Directory (AAD) or local account</span></span> |<span data-ttu-id="30f40-163">是</span><span class="sxs-lookup"><span data-stu-id="30f40-163">Yes</span></span> |<span data-ttu-id="30f40-164">否</span><span class="sxs-lookup"><span data-stu-id="30f40-164">No</span></span> |
|<span data-ttu-id="30f40-165">多應用程式亭</span><span class="sxs-lookup"><span data-stu-id="30f40-165">Multi-app kiosk</span></span> |<span data-ttu-id="30f40-166">AAD 帳戶</span><span class="sxs-lookup"><span data-stu-id="30f40-166">AAD account</span></span> |<span data-ttu-id="30f40-167">否</span><span class="sxs-lookup"><span data-stu-id="30f40-167">No</span></span> |<span data-ttu-id="30f40-168">是</span><span class="sxs-lookup"><span data-stu-id="30f40-168">Yes</span></span> |

<span data-ttu-id="30f40-169">如需如何使用這些功能的範例，請參閱下表。</span><span class="sxs-lookup"><span data-stu-id="30f40-169">For examples of how to use these capabilities, see the following table.</span></span>

|<span data-ttu-id="30f40-170">使用單一應用程式亭進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="30f40-170">Use a single-app kiosk for:</span></span> |<span data-ttu-id="30f40-171">使用多應用程式亭進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="30f40-171">Use a multi-app kiosk for:</span></span> |
| --- | --- |
|<span data-ttu-id="30f40-172">一種裝置，只對新的員工執行 Dynamics 365 指南。</span><span class="sxs-lookup"><span data-stu-id="30f40-172">A device that runs only a Dynamics 365 Guide for new employees.</span></span> |<span data-ttu-id="30f40-173">為一系列員工執行輔助線和遠端協助的裝置。</span><span class="sxs-lookup"><span data-stu-id="30f40-173">A device that runs both Guides and Remote Assistance for a range of employees.</span></span> |
|<span data-ttu-id="30f40-174">只執行自訂應用程式的裝置。</span><span class="sxs-lookup"><span data-stu-id="30f40-174">A device that runs only a custom app.</span></span> |<span data-ttu-id="30f40-175">在 (只執行自訂應用程式) 的裝置，但作為特定使用者群組的標準裝置的功能。</span><span class="sxs-lookup"><span data-stu-id="30f40-175">A device that functions as a kiosk for most users (running only a custom app), but functions as a standard device for a specific group of users.</span></span> |

### <span data-ttu-id="30f40-176">規劃展臺應用程式</span><span class="sxs-lookup"><span data-stu-id="30f40-176">Plan kiosk apps</span></span>

<span data-ttu-id="30f40-177">如需如何選擇 kiosk app 的一般資訊，請參閱在 [ (kiosk 模式] 中選擇指派存取權的原則) ](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)。</span><span class="sxs-lookup"><span data-stu-id="30f40-177">For general information about how to choose kiosk apps, see [Guidelines for choosing an app for assigned access (kiosk mode)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app).</span></span>

<span data-ttu-id="30f40-178">如果您使用 Windows Device Portal 來設定單一應用程式亭，您可以在安裝程式期間選取 app。</span><span class="sxs-lookup"><span data-stu-id="30f40-178">If you use the Windows Device Portal to configure a single-app kiosk, you select the app during the setup process.</span></span>  

<span data-ttu-id="30f40-179">如果您使用行動裝置管理 (MDM) 系統或預配套件來設定 kiosk 模式，您可以使用 [AssignedAccess 配置服務提供者 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) 來指定應用程式。</span><span class="sxs-lookup"><span data-stu-id="30f40-179">If you use a Mobile Device Management (MDM) system or a provisioning package to configure kiosk mode, you use the [AssignedAccess Configuration Service Provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) to specify applications.</span></span> <span data-ttu-id="30f40-180">CSP 會使用 [應用程式使用者模型識別碼 (aumid) ](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 來識別應用程式。</span><span class="sxs-lookup"><span data-stu-id="30f40-180">The CSP uses [Application User Model IDs (AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) to identify applications.</span></span> <span data-ttu-id="30f40-181">下表列出一些您可以在多應用程式亭中使用的 Aumid 應用程式。</span><span class="sxs-lookup"><span data-stu-id="30f40-181">The following table lists the AUMIDs of some in-box applications that you can use in a multi-app kiosk.</span></span>

> [!CAUTION]
> <span data-ttu-id="30f40-182">您無法選取 [Shell] app 做為展臺 app。</span><span class="sxs-lookup"><span data-stu-id="30f40-182">You cannot select the Shell app as a kiosk app.</span></span> <span data-ttu-id="30f40-183">此外，我們建議您 **不要選取 [** microsoft Edge]、[microsoft Store] 或 [檔案資源管理器] 做為展臺 app。</span><span class="sxs-lookup"><span data-stu-id="30f40-183">Addition, we recommend that you do **not** select Microsoft Edge, Microsoft Store, or File Explorer as a kiosk app.</span></span>  

<a id="aumids"></a>

|<span data-ttu-id="30f40-184">應用程式名稱</span><span class="sxs-lookup"><span data-stu-id="30f40-184">App Name</span></span> |<span data-ttu-id="30f40-185">AUMID</span><span class="sxs-lookup"><span data-stu-id="30f40-185">AUMID</span></span> |
| --- | --- |
|<span data-ttu-id="30f40-186">3D 檢視器</span><span class="sxs-lookup"><span data-stu-id="30f40-186">3D Viewer</span></span> |<span data-ttu-id="30f40-187">Microsoft3DViewer _8wekyb3d8bbwe \！Microsoft3DViewer</span><span class="sxs-lookup"><span data-stu-id="30f40-187">Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\!Microsoft.Microsoft3DViewer</span></span> |
|<span data-ttu-id="30f40-188">行事曆</span><span class="sxs-lookup"><span data-stu-id="30f40-188">Calendar</span></span> |<span data-ttu-id="30f40-189">windowscommunicationsapps \ _8wekyb3d8bbwe \！ windowslive。</span><span class="sxs-lookup"><span data-stu-id="30f40-189">microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\!microsoft.windowslive.calendar</span></span> |
|<span data-ttu-id="30f40-190">相機 <sup> 1、2</span><span class="sxs-lookup"><span data-stu-id="30f40-190">Camera<sup>1, 2</span></span></sup> |<span data-ttu-id="30f40-191">HoloCamera \ _cw5n1h2txyewy \！HoloCamera</span><span class="sxs-lookup"><span data-stu-id="30f40-191">HoloCamera\_cw5n1h2txyewy\!HoloCamera</span></span> |
|<span data-ttu-id="30f40-192">Cortana <sup> 3</span><span class="sxs-lookup"><span data-stu-id="30f40-192">Cortana<sup>3</span></span></sup> |<span data-ttu-id="30f40-193">549981C3F5F10 _8wekyb3d8bbwe \！適用</span><span class="sxs-lookup"><span data-stu-id="30f40-193">Microsoft.549981C3F5F10\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="30f40-194">HoloLens 上的 Device 拾器 (1 gen) </span><span class="sxs-lookup"><span data-stu-id="30f40-194">Device Picker on HoloLens (1st gen)</span></span> |<span data-ttu-id="30f40-195">HoloDevicesFlow \ _cw5n1h2txyewy \！HoloDevicesFlow</span><span class="sxs-lookup"><span data-stu-id="30f40-195">HoloDevicesFlow\_cw5n1h2txyewy\!HoloDevicesFlow</span></span> |
|<span data-ttu-id="30f40-196">HoloLens 2 上的裝置選擇器</span><span class="sxs-lookup"><span data-stu-id="30f40-196">Device Picker on HoloLens 2</span></span> |<span data-ttu-id="30f40-197">DevicesFlowHost \ _cw5n1h2txyewy \！DevicesFlowHost</span><span class="sxs-lookup"><span data-stu-id="30f40-197">Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\!Microsoft.Windows.DevicesFlowHost</span></span> |
|<span data-ttu-id="30f40-198">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="30f40-198">Dynamics 365 Guides</span></span> |<span data-ttu-id="30f40-199">Dynamics365 _8wekyb3d8bbwe \！MicrosoftGuides</span><span class="sxs-lookup"><span data-stu-id="30f40-199">Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\!MicrosoftGuides</span></span> |
|<span data-ttu-id="30f40-200">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="30f40-200">Dynamics 365 Remote Assist</span></span> |<span data-ttu-id="30f40-201">MicrosoftRemoteAssist _8wekyb3d8bbwe \！RemoteAssist</span><span class="sxs-lookup"><span data-stu-id="30f40-201">Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\!Microsoft.RemoteAssist</span></span> |
|<span data-ttu-id="30f40-202">意見反應 &nbsp; 中樞</span><span class="sxs-lookup"><span data-stu-id="30f40-202">Feedback&nbsp;Hub</span></span> |<span data-ttu-id="30f40-203">WindowsFeedbackHub _8wekyb3d8bbwe \！適用</span><span class="sxs-lookup"><span data-stu-id="30f40-203">Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="30f40-204">檔案總管</span><span class="sxs-lookup"><span data-stu-id="30f40-204">File Explorer</span></span> |<span data-ttu-id="30f40-205">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span><span class="sxs-lookup"><span data-stu-id="30f40-205">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span></span> |
|<span data-ttu-id="30f40-206">郵件</span><span class="sxs-lookup"><span data-stu-id="30f40-206">Mail</span></span> |<span data-ttu-id="30f40-207">windowscommunicationsapps_8wekyb3d8bbwe！ windowslive！</span><span class="sxs-lookup"><span data-stu-id="30f40-207">microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail</span></span> |
|<span data-ttu-id="30f40-208">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="30f40-208">Microsoft Store</span></span> |<span data-ttu-id="30f40-209">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span><span class="sxs-lookup"><span data-stu-id="30f40-209">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span></span> |
|<span data-ttu-id="30f40-210">Miracast <sup> 4</span><span class="sxs-lookup"><span data-stu-id="30f40-210">Miracast<sup>4</span></span></sup> |&nbsp; |
|<span data-ttu-id="30f40-211">電影與電視</span><span class="sxs-lookup"><span data-stu-id="30f40-211">Movies & TV</span></span> |<span data-ttu-id="30f40-212">ZuneVideo _8wekyb3d8bbwe \！ZuneVideo</span><span class="sxs-lookup"><span data-stu-id="30f40-212">Microsoft.ZuneVideo\_8wekyb3d8bbwe\!Microsoft.ZuneVideo</span></span> |
|<span data-ttu-id="30f40-213">OneDrive</span><span class="sxs-lookup"><span data-stu-id="30f40-213">OneDrive</span></span> |<span data-ttu-id="30f40-214">microsoftskydrive _8wekyb3d8bbwe \！適用</span><span class="sxs-lookup"><span data-stu-id="30f40-214">microsoft.microsoftskydrive\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="30f40-215">相片</span><span class="sxs-lookup"><span data-stu-id="30f40-215">Photos</span></span> |<span data-ttu-id="30f40-216">您的 _8wekyb3d8bbwe \！適用</span><span class="sxs-lookup"><span data-stu-id="30f40-216">Microsoft.Windows.Photos\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="30f40-217">設定</span><span class="sxs-lookup"><span data-stu-id="30f40-217">Settings</span></span> |<span data-ttu-id="30f40-218">HolographicSystemSettings \ _cw5n1h2txyewy \！適用</span><span class="sxs-lookup"><span data-stu-id="30f40-218">HolographicSystemSettings\_cw5n1h2txyewy\!App</span></span> |
|<span data-ttu-id="30f40-219">提示</span><span class="sxs-lookup"><span data-stu-id="30f40-219">Tips</span></span> |<span data-ttu-id="30f40-220">HoloLensTips _8wekyb3d8bbwe \！HoloLensTips</span><span class="sxs-lookup"><span data-stu-id="30f40-220">Microsoft.HoloLensTips\_8wekyb3d8bbwe\!HoloLensTips</span></span> |

> <sup><span data-ttu-id="30f40-221">1 </sup> 若要啟用相片或影片捕獲，您必須啟用攝影機 app 作為 kiosk app。</span><span class="sxs-lookup"><span data-stu-id="30f40-221">1</sup> To enable photo or video capture, you have to enable the Camera app as a kiosk app.</span></span>  
> <sup><span data-ttu-id="30f40-222">2 </sup> 當您啟用攝像頭 app 時，請注意下列情況：</span><span class="sxs-lookup"><span data-stu-id="30f40-222">2</sup> When you enable the Camera app, be aware of the following conditions:</span></span>
> - <span data-ttu-id="30f40-223">[快速動作] 功能表包括 [相片] 和 [影片] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="30f40-223">The Quick Actions menu includes the Photo and Video buttons.</span></span>  
> - <span data-ttu-id="30f40-224">您也應該啟用可與圖片互動或取得圖片的 app (例如相片、郵件或 OneDrive) 。</span><span class="sxs-lookup"><span data-stu-id="30f40-224">You should also enable an app (such as Photos, Mail, or OneDrive) that can interact with or retrieve pictures.</span></span>  
>  
> <sup><span data-ttu-id="30f40-225">3 </sup> 即使您未啟用 Cortana 作為 kiosk app，也會啟用內建語音命令。</span><span class="sxs-lookup"><span data-stu-id="30f40-225">3</sup> Even if you do not enable Cortana as a kiosk app, built-in voice commands are enabled.</span></span> <span data-ttu-id="30f40-226">不過，與停用功能相關的命令不會產生任何效果。</span><span class="sxs-lookup"><span data-stu-id="30f40-226">However, commands that are related to disabled features have no effect.</span></span>  
> <sup><span data-ttu-id="30f40-227">4 </sup> 您無法直接啟用 Miracast。</span><span class="sxs-lookup"><span data-stu-id="30f40-227">4</sup> You cannot enable Miracast directly.</span></span> <span data-ttu-id="30f40-228">若要啟用 Miracast 作為 kiosk app，請啟用相機 app 和裝置選擇器應用程式。</span><span class="sxs-lookup"><span data-stu-id="30f40-228">To enable Miracast as a kiosk app enable the Camera app and the Device Picker app.</span></span>

### <span data-ttu-id="30f40-229">規劃使用者和裝置群組</span><span class="sxs-lookup"><span data-stu-id="30f40-229">Plan user and device groups</span></span>

<span data-ttu-id="30f40-230">在 MDM 環境中，您可以使用群組來管理裝置設定和使用者存取。</span><span class="sxs-lookup"><span data-stu-id="30f40-230">In an MDM environment, you use groups to manage device configurations and user access.</span></span> 

<span data-ttu-id="30f40-231">Kiosk 配置設定檔包括 [ **使用者登入類型** ] 設定。</span><span class="sxs-lookup"><span data-stu-id="30f40-231">The kiosk configuration profile includes the **User logon type** setting.</span></span> <span data-ttu-id="30f40-232">**使用者登入類型** 會識別使用者 (或群組，其中包含哪些使用者可以使用您所新增的應用程式) 。</span><span class="sxs-lookup"><span data-stu-id="30f40-232">**User logon type** identifies the user (or group that contains the users) who can use the app or apps that you add.</span></span> <span data-ttu-id="30f40-233">如果使用者使用未包含在設定檔中的帳戶登入，該使用者就無法在展臺上使用 app。</span><span class="sxs-lookup"><span data-stu-id="30f40-233">If a user signs in by using an account that is not included in the configuration profile, that user cannot use apps on the kiosk.</span></span>  

> [!NOTE]  
> <span data-ttu-id="30f40-234">單一 app 展臺的 **使用者登入類型** 會指定單一使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="30f40-234">The **User logon type** of a single-app kiosk specifies a single user account.</span></span> <span data-ttu-id="30f40-235">這是在其中執行 kiosk 的使用者內容。</span><span class="sxs-lookup"><span data-stu-id="30f40-235">This is the user context under which the kiosk runs.</span></span> <span data-ttu-id="30f40-236">多應用程式亭的 **使用者登入類型** 可以指定一個或多個可以使用 kiosk 的使用者帳戶或群組。</span><span class="sxs-lookup"><span data-stu-id="30f40-236">The **User logon type** of a multi-app kiosk can specify one or more user accounts or groups that can use the kiosk.</span></span>

<span data-ttu-id="30f40-237">您必須先將 kiosk 配置設定檔 *指派* 給包含裝置的群組，或是可以登入裝置的使用者，才能將其部署到裝置。</span><span class="sxs-lookup"><span data-stu-id="30f40-237">Before you can deploy the kiosk configuration to a device, you have to *assign* the kiosk configuration profile to a group that contains the device or a user who can sign in to the device.</span></span> <span data-ttu-id="30f40-238">這個設定會產生如下所示的行為。</span><span class="sxs-lookup"><span data-stu-id="30f40-238">This setting produces behavior such as the following.</span></span>

- <span data-ttu-id="30f40-239">如果裝置是指派群組的成員，則在任何使用者第一次登入裝置時，kiosk 設定就會部署到該裝置。</span><span class="sxs-lookup"><span data-stu-id="30f40-239">If the device is a member of the assigned group, the kiosk configuration deploys to the device the first time that any user signs in on the device.</span></span>  
- <span data-ttu-id="30f40-240">如果裝置不是指派群組的成員，但屬於該群組成員的使用者登入，kiosk 設定會在該時間部署到裝置。</span><span class="sxs-lookup"><span data-stu-id="30f40-240">If the device is not a member of the assigned group, but a user who is a member of that group signs in, the kiosk configuration deploys to the device at that time.</span></span>

<span data-ttu-id="30f40-241">如需在 Intune 中指派設定檔的效果的完整討論，請參閱 [在 Microsoft Intune 中指派使用者和裝置設定檔](https://docs.microsoft.com/intune/configuration/device-profile-assign)。</span><span class="sxs-lookup"><span data-stu-id="30f40-241">For a full discussion of the effects of assigning configuration profiles in Intune, see [Assign user and device profiles in Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).</span></span>

> [!NOTE]  
> <span data-ttu-id="30f40-242">下列範例說明多重 app 網亭。</span><span class="sxs-lookup"><span data-stu-id="30f40-242">The following examples describe multi-app kiosks.</span></span> <span data-ttu-id="30f40-243">單一 app 網亭的行為方式與此類似，但只有一個使用者帳戶能取得 kiosk 體驗。</span><span class="sxs-lookup"><span data-stu-id="30f40-243">Single-app kiosks behave in a similar manner, but only one user account gets the kiosk experience.</span></span>

**<span data-ttu-id="30f40-244">範例 1</span><span class="sxs-lookup"><span data-stu-id="30f40-244">Example 1</span></span>**

<span data-ttu-id="30f40-245">您針對裝置和使用者使用單一群組 (群組 1) 。</span><span class="sxs-lookup"><span data-stu-id="30f40-245">You use a single group (Group 1) for both devices and users.</span></span> <span data-ttu-id="30f40-246">一個裝置和使用者 A、B 和 C 都是這個群組的成員。</span><span class="sxs-lookup"><span data-stu-id="30f40-246">One device and users A, B, and C are members of this group.</span></span> <span data-ttu-id="30f40-247">您可以設定展臺設定檔，如下所示：</span><span class="sxs-lookup"><span data-stu-id="30f40-247">You configure the kiosk configuration profile as follows:</span></span>  

- <span data-ttu-id="30f40-248">**使用者登入類型**：群組1</span><span class="sxs-lookup"><span data-stu-id="30f40-248">**User logon type**: Group 1</span></span>
- <span data-ttu-id="30f40-249">**已指派的群組**：群組1</span><span class="sxs-lookup"><span data-stu-id="30f40-249">**Assigned group**: Group 1</span></span>

<span data-ttu-id="30f40-250">不論哪個使用者先登入裝置 (並透過全新的體驗（或 OOBE) ），kiosk 配置也會部署到裝置。</span><span class="sxs-lookup"><span data-stu-id="30f40-250">Regardless of which user signs on to the device first (and goes through the Out-of-Box Experience, or OOBE), the kiosk configuration deploys to the device.</span></span> <span data-ttu-id="30f40-251">使用者 A、B 和 C 都可以登入裝置並取得展臺體驗。</span><span class="sxs-lookup"><span data-stu-id="30f40-251">Users A, B, and C can all sign in to the device and get the kiosk experience.</span></span>

**<span data-ttu-id="30f40-252">範例 2</span><span class="sxs-lookup"><span data-stu-id="30f40-252">Example 2</span></span>**

<span data-ttu-id="30f40-253">您會將裝置合約給需要不同資訊站體驗的兩個不同轉銷商。</span><span class="sxs-lookup"><span data-stu-id="30f40-253">You contract out devices to two different vendors who need different kiosk experiences.</span></span> <span data-ttu-id="30f40-254">兩個廠商都有使用者，而且您想讓所有使用者都能存取其自己的供應商和其他廠商的展臺。</span><span class="sxs-lookup"><span data-stu-id="30f40-254">Both vendors have users, and you want all the users to have access to kiosks from both their own vendor and the other vendor.</span></span> <span data-ttu-id="30f40-255">您可以按照下列步驟設定群組：</span><span class="sxs-lookup"><span data-stu-id="30f40-255">You configure groups as follows:</span></span>

- <span data-ttu-id="30f40-256">裝置群組1：</span><span class="sxs-lookup"><span data-stu-id="30f40-256">Device Group 1:</span></span>
  - <span data-ttu-id="30f40-257">裝置 1 (供應商 1) </span><span class="sxs-lookup"><span data-stu-id="30f40-257">Device 1 (Vendor 1)</span></span>
  - <span data-ttu-id="30f40-258">裝置 2 (供應商 1) </span><span class="sxs-lookup"><span data-stu-id="30f40-258">Device 2 (Vendor 1)</span></span>

- <span data-ttu-id="30f40-259">裝置群組2：</span><span class="sxs-lookup"><span data-stu-id="30f40-259">Device Group 2:</span></span>
  - <span data-ttu-id="30f40-260">裝置 3 (供應商 2) </span><span class="sxs-lookup"><span data-stu-id="30f40-260">Device 3 (Vendor 2)</span></span>
  - <span data-ttu-id="30f40-261">裝置 4 (供應商 2) </span><span class="sxs-lookup"><span data-stu-id="30f40-261">Device 4 (Vendor 2)</span></span>

- <span data-ttu-id="30f40-262">[使用者] 群組：</span><span class="sxs-lookup"><span data-stu-id="30f40-262">User Group:</span></span>
  - <span data-ttu-id="30f40-263">使用者 A (供應商 1) </span><span class="sxs-lookup"><span data-stu-id="30f40-263">User A (Vendor 1)</span></span>
  - <span data-ttu-id="30f40-264">使用者 B (供應商 2) </span><span class="sxs-lookup"><span data-stu-id="30f40-264">User B (Vendor 2)</span></span>

<span data-ttu-id="30f40-265">您建立兩個具備下列設定的 kiosk 設定檔：</span><span class="sxs-lookup"><span data-stu-id="30f40-265">You create two kiosk configuration profiles that have the following settings:</span></span>

- <span data-ttu-id="30f40-266">展臺設定檔1：</span><span class="sxs-lookup"><span data-stu-id="30f40-266">Kiosk Profile 1:</span></span>
   - <span data-ttu-id="30f40-267">**使用者登入類型**：使用者群組</span><span class="sxs-lookup"><span data-stu-id="30f40-267">**User logon type**: User Group</span></span>
   - <span data-ttu-id="30f40-268">**已指派的群組**：裝置群組1</span><span class="sxs-lookup"><span data-stu-id="30f40-268">**Assigned group**: Device Group 1</span></span>

- <span data-ttu-id="30f40-269">展臺設定檔2：</span><span class="sxs-lookup"><span data-stu-id="30f40-269">Kiosk Profile 2:</span></span>
   - <span data-ttu-id="30f40-270">**使用者登入類型**：使用者群組</span><span class="sxs-lookup"><span data-stu-id="30f40-270">**User logon type**: User Group</span></span>
   - <span data-ttu-id="30f40-271">**已指派的群組**：裝置群組2</span><span class="sxs-lookup"><span data-stu-id="30f40-271">**Assigned group**: Device Group 2</span></span>

<span data-ttu-id="30f40-272">這些設定會產生下列結果：</span><span class="sxs-lookup"><span data-stu-id="30f40-272">These configurations produce the following results:</span></span>

- <span data-ttu-id="30f40-273">當任何使用者登入 [裝置 1] 或 [裝置 2] 時，Intune 都會將 Kiosk 設定檔1部署到該裝置。</span><span class="sxs-lookup"><span data-stu-id="30f40-273">When any user signs in to Device 1 or Device 2, Intune deploys Kiosk Profile 1 to that device.</span></span>
- <span data-ttu-id="30f40-274">當任何使用者登入 [裝置 3] 或 [裝置 4] 時，Intune 都會將 Kiosk 設定檔2部署到該裝置。</span><span class="sxs-lookup"><span data-stu-id="30f40-274">When any user signs in to Device 3 or Device 4, Intune deploys Kiosk Profile 2 to that device.</span></span>
- <span data-ttu-id="30f40-275">使用者 A 和使用者 B 可以登入四個裝置中的任何一種。</span><span class="sxs-lookup"><span data-stu-id="30f40-275">User A and user B can sign in to any of the four devices.</span></span> <span data-ttu-id="30f40-276">如果他們登入 [裝置 1] 或 [裝置 2]，就會看到 [廠商1資訊] 的體驗。</span><span class="sxs-lookup"><span data-stu-id="30f40-276">If they sign in to Device 1 or Device 2, they see the Vendor 1 kiosk experience.</span></span> <span data-ttu-id="30f40-277">如果他們登入 [裝置 3] 或 [裝置 4]，就會看到 [廠商 2] 的 kiosk 體驗。</span><span class="sxs-lookup"><span data-stu-id="30f40-277">If they sign in to Device 3 or Device 4, they see the Vendor 2 kiosk experience.</span></span>

#### <span data-ttu-id="30f40-278">設定檔衝突</span><span class="sxs-lookup"><span data-stu-id="30f40-278">Profile conflicts</span></span>

<span data-ttu-id="30f40-279">如果有兩個或多個展臺配置設定檔針對相同的裝置，就會發生衝突。</span><span class="sxs-lookup"><span data-stu-id="30f40-279">If two or more kiosk configuration profiles target the same device, they conflict.</span></span> <span data-ttu-id="30f40-280">如果是 Intune 管理的裝置，則 Intune 不會套用任何衝突的設定檔。</span><span class="sxs-lookup"><span data-stu-id="30f40-280">In the case of Intune-managed devices, Intune does not apply any of the conflicting profiles.</span></span>

<span data-ttu-id="30f40-281">其他類型的設定檔與原則，例如與 kiosk 配置設定檔無關的裝置限制，請勿與 kiosk 設定設定檔發生衝突。</span><span class="sxs-lookup"><span data-stu-id="30f40-281">Other kinds of profiles and policies, such as device restrictions that are not related to the kiosk configuration profile, do not conflict with the kiosk configuration profile.</span></span>

### <span data-ttu-id="30f40-282">選取部署方法</span><span class="sxs-lookup"><span data-stu-id="30f40-282">Select a deployment method</span></span>

<span data-ttu-id="30f40-283">您可以選取下列其中一種方法來部署展臺配置：</span><span class="sxs-lookup"><span data-stu-id="30f40-283">You can select one of the following methods to deploy kiosk configurations:</span></span>

- [<span data-ttu-id="30f40-284"> (MDM) 服務的 Microsoft Intune 或其他行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="30f40-284">Microsoft Intune or other mobile device management (MDM) service</span></span>](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="30f40-285">佈建套件</span><span class="sxs-lookup"><span data-stu-id="30f40-285">Provisioning package</span></span>](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="30f40-286">Windows Device Portal</span><span class="sxs-lookup"><span data-stu-id="30f40-286">Windows Device Portal</span></span>](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > <span data-ttu-id="30f40-287">由於這個方法需要在裝置上啟用開發人員模式，因此我們建議您僅將它用於示範。</span><span class="sxs-lookup"><span data-stu-id="30f40-287">Because this method requires that Developer Mode be enabled on the device, we recommend that you use it only for demonstrations.</span></span>

<span data-ttu-id="30f40-288">下表列出每個部署方法的功能和優點。</span><span class="sxs-lookup"><span data-stu-id="30f40-288">The following table lists the capabilities and benefits of each of the deployment methods.</span></span>

| &nbsp; |<span data-ttu-id="30f40-289">使用 Windows Device Portal 進行部署</span><span class="sxs-lookup"><span data-stu-id="30f40-289">Deploy by using Windows Device Portal</span></span> |<span data-ttu-id="30f40-290">使用預配套件進行部署</span><span class="sxs-lookup"><span data-stu-id="30f40-290">Deploy by using a provisioning package</span></span> |<span data-ttu-id="30f40-291">使用 MDM 部署</span><span class="sxs-lookup"><span data-stu-id="30f40-291">Deploy by using MDM</span></span> |
| --------------------------- | ------------- | -------------------- | ---- |
|<span data-ttu-id="30f40-292">部署單一 app 網亭</span><span class="sxs-lookup"><span data-stu-id="30f40-292">Deploy single-app kiosks</span></span>   | <span data-ttu-id="30f40-293">是</span><span class="sxs-lookup"><span data-stu-id="30f40-293">Yes</span></span>           | <span data-ttu-id="30f40-294">是</span><span class="sxs-lookup"><span data-stu-id="30f40-294">Yes</span></span>                  | <span data-ttu-id="30f40-295">是</span><span class="sxs-lookup"><span data-stu-id="30f40-295">Yes</span></span>  |
|<span data-ttu-id="30f40-296">部署多應用程式亭</span><span class="sxs-lookup"><span data-stu-id="30f40-296">Deploy multi-app kiosks</span></span>    | <span data-ttu-id="30f40-297">否</span><span class="sxs-lookup"><span data-stu-id="30f40-297">No</span></span>            | <span data-ttu-id="30f40-298">是</span><span class="sxs-lookup"><span data-stu-id="30f40-298">Yes</span></span>                  | <span data-ttu-id="30f40-299">是</span><span class="sxs-lookup"><span data-stu-id="30f40-299">Yes</span></span>  |
|<span data-ttu-id="30f40-300">僅部署到本機裝置</span><span class="sxs-lookup"><span data-stu-id="30f40-300">Deploy to local devices only</span></span> | <span data-ttu-id="30f40-301">是</span><span class="sxs-lookup"><span data-stu-id="30f40-301">Yes</span></span>           | <span data-ttu-id="30f40-302">是</span><span class="sxs-lookup"><span data-stu-id="30f40-302">Yes</span></span>                  | <span data-ttu-id="30f40-303">否</span><span class="sxs-lookup"><span data-stu-id="30f40-303">No</span></span>   |
|<span data-ttu-id="30f40-304">使用開發人員模式進行部署</span><span class="sxs-lookup"><span data-stu-id="30f40-304">Deploy by using Developer Mode</span></span> |<span data-ttu-id="30f40-305">必要</span><span class="sxs-lookup"><span data-stu-id="30f40-305">Required</span></span>       | <span data-ttu-id="30f40-306">不需要</span><span class="sxs-lookup"><span data-stu-id="30f40-306">Not required</span></span>            | <span data-ttu-id="30f40-307">不需要</span><span class="sxs-lookup"><span data-stu-id="30f40-307">Not required</span></span>   |
|<span data-ttu-id="30f40-308">使用 Azure Active Directory (AAD) 進行部署</span><span class="sxs-lookup"><span data-stu-id="30f40-308">Deploy by using Azure Active Directory (AAD)</span></span>  | <span data-ttu-id="30f40-309">不需要</span><span class="sxs-lookup"><span data-stu-id="30f40-309">Not required</span></span>            | <span data-ttu-id="30f40-310">不需要</span><span class="sxs-lookup"><span data-stu-id="30f40-310">Not required</span></span>                   | <span data-ttu-id="30f40-311">必要</span><span class="sxs-lookup"><span data-stu-id="30f40-311">Required</span></span>  |
|<span data-ttu-id="30f40-312">自動部署</span><span class="sxs-lookup"><span data-stu-id="30f40-312">Deploy automatically</span></span>      | <span data-ttu-id="30f40-313">否</span><span class="sxs-lookup"><span data-stu-id="30f40-313">No</span></span>            | <span data-ttu-id="30f40-314">否</span><span class="sxs-lookup"><span data-stu-id="30f40-314">No</span></span>                   | <span data-ttu-id="30f40-315">是</span><span class="sxs-lookup"><span data-stu-id="30f40-315">Yes</span></span>  |
|<span data-ttu-id="30f40-316">部署速度</span><span class="sxs-lookup"><span data-stu-id="30f40-316">Deployment speed</span></span>            | <span data-ttu-id="30f40-317">高</span><span class="sxs-lookup"><span data-stu-id="30f40-317">Fastest</span></span>       | <span data-ttu-id="30f40-318">快速</span><span class="sxs-lookup"><span data-stu-id="30f40-318">Fast</span></span>                 | <span data-ttu-id="30f40-319">慢速</span><span class="sxs-lookup"><span data-stu-id="30f40-319">Slow</span></span> |
|<span data-ttu-id="30f40-320">在縮放時部署</span><span class="sxs-lookup"><span data-stu-id="30f40-320">Deploy at scale</span></span> | <span data-ttu-id="30f40-321">不建議使用</span><span class="sxs-lookup"><span data-stu-id="30f40-321">Not recommended</span></span>    | <span data-ttu-id="30f40-322">不建議使用</span><span class="sxs-lookup"><span data-stu-id="30f40-322">Not recommended</span></span>        | <span data-ttu-id="30f40-323">建議執行</span><span class="sxs-lookup"><span data-stu-id="30f40-323">Recommended</span></span> |

## <span data-ttu-id="30f40-324">使用 Microsoft Intune 或其他 MDM 設定單一 app 或多重應用程式亭</span><span class="sxs-lookup"><span data-stu-id="30f40-324">Use Microsoft Intune or other MDM to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="30f40-325">若要使用 Microsoft Intune 或其他 MDM 系統來設定 kiosk 模式，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="30f40-325">To set up kiosk mode by using Microsoft Intune or another MDM system, follow these steps.</span></span>

1. <span data-ttu-id="30f40-326">[準備註冊裝置](#mdmenroll)。</span><span class="sxs-lookup"><span data-stu-id="30f40-326">[Prepare to enroll the devices](#mdmenroll).</span></span>
1. <span data-ttu-id="30f40-327">[建立展臺設定檔](#mdmprofile)。</span><span class="sxs-lookup"><span data-stu-id="30f40-327">[Create a kiosk configuration profile](#mdmprofile).</span></span>
1. <span data-ttu-id="30f40-328">設定 kiosk。</span><span class="sxs-lookup"><span data-stu-id="30f40-328">Configure the kiosk.</span></span>
   - <span data-ttu-id="30f40-329">[設定單一 app 展臺的設定](#mdmconfigsingle)。</span><span class="sxs-lookup"><span data-stu-id="30f40-329">[Configure the settings for a single-app kiosk](#mdmconfigsingle).</span></span>
   - <span data-ttu-id="30f40-330">[設定多應用程式資訊站的設定](#mdmconfigmulti)。</span><span class="sxs-lookup"><span data-stu-id="30f40-330">[Configure the settings for a multi-app kiosk](#mdmconfigmulti).</span></span>
1. <span data-ttu-id="30f40-331">[將 kiosk 配置設定檔指派給群組](#mdmassign)。</span><span class="sxs-lookup"><span data-stu-id="30f40-331">[Assign the kiosk configuration profile to a group](#mdmassign).</span></span>
1. <span data-ttu-id="30f40-332">部署裝置。</span><span class="sxs-lookup"><span data-stu-id="30f40-332">Deploy the devices.</span></span>
   - <span data-ttu-id="30f40-333">[部署單一應用程式亭](#mdmsingledeploy)。</span><span class="sxs-lookup"><span data-stu-id="30f40-333">[Deploy a single-app kiosk](#mdmsingledeploy).</span></span>
   - <span data-ttu-id="30f40-334">[部署多應用程式亭](#mdmmultideploy)。</span><span class="sxs-lookup"><span data-stu-id="30f40-334">[Deploy a multi-app kiosk](#mdmmultideploy).</span></span>

### <a id="mdmenroll"></a><span data-ttu-id="30f40-335">MDM，步驟 1 &ndash; 準備註冊裝置</span><span class="sxs-lookup"><span data-stu-id="30f40-335">MDM, step 1 &ndash; Prepare to enroll the devices</span></span>

<span data-ttu-id="30f40-336">您可以設定您的 MDM 系統在使用者第一次登入時自動登記 HoloLens 裝置，或讓使用者手動註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="30f40-336">You can configure your MDM system to enroll HoloLens devices automatically when the user first signs in, or have users enroll devices manually.</span></span> <span data-ttu-id="30f40-337">裝置也必須加入到 Azure AD 網域，並指派給適當的群組。</span><span class="sxs-lookup"><span data-stu-id="30f40-337">The devices also have to be joined to your Azure AD domain, and assigned to the appropriate groups.</span></span>

<span data-ttu-id="30f40-338">如需有關如何註冊裝置的詳細資訊，請參閱在[Windows 裝置的 MDM 和 Intune 註冊方法](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)[中註冊 HoloLens](hololens-enroll-mdm.md) 。</span><span class="sxs-lookup"><span data-stu-id="30f40-338">For more information about how to enroll the devices, see [Enroll HoloLens in MDM](hololens-enroll-mdm.md) and [Intune enrollment methods for Windows devices](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods).</span></span>

### <a id="mdmprofile"></a><span data-ttu-id="30f40-339">MDM，步驟 2 &ndash; 建立 kiosk 配置設定檔</span><span class="sxs-lookup"><span data-stu-id="30f40-339">MDM, step 2 &ndash; Create a kiosk configuration profile</span></span>

1. <span data-ttu-id="30f40-340">開啟 [Azure](https://portal.azure.com/) 入口網站，並登入您的 Intune 系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="30f40-340">Open the [Azure](https://portal.azure.com/) portal and sign in to your Intune administrator account.</span></span>
1. <span data-ttu-id="30f40-341">選取 [ **Microsoft Intune**裝置設定]-[設定檔]  >  **Device configuration - Profiles**  >  **建立設定檔**。</span><span class="sxs-lookup"><span data-stu-id="30f40-341">Select **Microsoft Intune** > **Device configuration - Profiles** > **Create profile**.</span></span>
1. <span data-ttu-id="30f40-342">輸入設定檔名稱。</span><span class="sxs-lookup"><span data-stu-id="30f40-342">Enter a profile name.</span></span>
1. <span data-ttu-id="30f40-343">選取 [**平臺**  >  **Windows 10 及更新版本**]，然後選取 [**配置檔案類型**  > **裝置限制**]。</span><span class="sxs-lookup"><span data-stu-id="30f40-343">Select **Platform** > **Windows 10 and later**, and then select **Profile type** >**Device restrictions**.</span></span>
1. <span data-ttu-id="30f40-344">選取 [**設定**  >  **Kiosk**]，然後選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="30f40-344">Select **Configure** > **Kiosk**, and then select one of the following:</span></span>
   - <span data-ttu-id="30f40-345">若要建立單一應用程式亭，請選取 [**展臺模式**  >  **單一應用程式亭**]。</span><span class="sxs-lookup"><span data-stu-id="30f40-345">To create a single-app kiosk, select **Kiosk Mode** > **Single-app kiosk**.</span></span>
   - <span data-ttu-id="30f40-346">若要建立多重應用程式亭，請選取 [**展臺模式**  >  **多重應用程式資訊站**]。</span><span class="sxs-lookup"><span data-stu-id="30f40-346">To create a multi-app kiosk, select **Kiosk Mode** > **Multi-app kiosk**.</span></span>
1. <span data-ttu-id="30f40-347">若要開始配置資訊亭，請選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="30f40-347">To start configuring the kiosk, select **Add**.</span></span>

<span data-ttu-id="30f40-348">根據您想要的展臺類型，後續步驟會有所不同。</span><span class="sxs-lookup"><span data-stu-id="30f40-348">Your next steps differ depending on the type of kiosk that you want.</span></span> <span data-ttu-id="30f40-349">如需詳細資訊，請選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="30f40-349">For more information, select one of the following options:</span></span>  

- [<span data-ttu-id="30f40-350">單一應用程式資訊站</span><span class="sxs-lookup"><span data-stu-id="30f40-350">Single-app kiosk</span></span>](#mdmconfigsingle)
- [<span data-ttu-id="30f40-351">多應用程式亭</span><span class="sxs-lookup"><span data-stu-id="30f40-351">Multi-app kiosk</span></span>](#mdmconfigmulti)

<span data-ttu-id="30f40-352">如需如何建立 kiosk 配置設定檔的詳細資訊，請參閱 [windows 10 和 Windows 全息企業版裝置設定，以使用 Intune 作為專用的展臺執行](https://docs.microsoft.com/intune/configuration/kiosk-settings)。</span><span class="sxs-lookup"><span data-stu-id="30f40-352">For more information about how to create a kiosk configuration profile, see [Windows 10 and Windows Holographic for Business device settings to run as a dedicated kiosk using Intune](https://docs.microsoft.com/intune/configuration/kiosk-settings).</span></span>

### <a id="mdmconfigsingle"></a><span data-ttu-id="30f40-353">MDM、步驟 3 (單 app) &ndash;  設定單一 app 展臺的設定</span><span class="sxs-lookup"><span data-stu-id="30f40-353">MDM, step 3 (single-app) &ndash;  Configure the settings for a single-app kiosk</span></span>

<span data-ttu-id="30f40-354">本節摘要說明單一 app 展臺所需的設定。</span><span class="sxs-lookup"><span data-stu-id="30f40-354">This section summarizes the settings that a single-app kiosk requires.</span></span> <span data-ttu-id="30f40-355">如需詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="30f40-355">For more details, see the following articles:</span></span>

- <span data-ttu-id="30f40-356">如需如何在 Intune 中設定 kiosk 設定檔的相關資訊，請參閱 [如何使用 Microsoft Intune 設定 Kiosk 模式](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="30f40-356">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="30f40-357">如需 Intune 中單一 app 亭可用設定的詳細資訊，請參閱 [單一全螢幕 app 網亭](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)</span><span class="sxs-lookup"><span data-stu-id="30f40-357">For more information about the available settings for single-app kiosks in Intune, see [Single full-screen app kiosks](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)</span></span>
- <span data-ttu-id="30f40-358">如需其他 MDM 服務，請參閱提供者文件中的指示。</span><span class="sxs-lookup"><span data-stu-id="30f40-358">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="30f40-359">如果您必須在 MDM 服務中使用自訂 XML 配置來設定展臺，請 [建立定義 kiosk 配置的 XML](#ppkioskconfig)檔案。</span><span class="sxs-lookup"><span data-stu-id="30f40-359">If you have to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span>

1. <span data-ttu-id="30f40-360">選取 [**使用者登**  >  入類型（**本機使用者帳戶**）]，然後輸入本機 (裝置) 帳戶或 Microsoft 帳戶的使用者名稱，即可登入資訊站 (MSA) 。</span><span class="sxs-lookup"><span data-stu-id="30f40-360">Select **User logon type** > **Local user account**, and then enter the user name of the local (device) account or Microsoft Account (MSA) that can sign in to the kiosk.</span></span>
   > [!NOTE]  
   > <span data-ttu-id="30f40-361">Windows 全息企業版不支援**自動登入**使用者帳戶類型。</span><span class="sxs-lookup"><span data-stu-id="30f40-361">**Autologon** user account types aren't supported on Windows Holographic for Business.</span></span>
1. <span data-ttu-id="30f40-362">選取 [**應用程式類型**  >  **存儲應用**程式]，然後從清單中選取一個應用程式。</span><span class="sxs-lookup"><span data-stu-id="30f40-362">Select **Application type** > **Store app**, and then select an app from the list.</span></span>

<span data-ttu-id="30f40-363">下一步是將設定檔 [指派](#mdmassign) 給群組。</span><span class="sxs-lookup"><span data-stu-id="30f40-363">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a id="mdmconfigmulti"></a><span data-ttu-id="30f40-364">MDM、步驟 3 (多重 app) &ndash; 設定多應用程式資訊站的設定</span><span class="sxs-lookup"><span data-stu-id="30f40-364">MDM, step 3 (multi-app) &ndash; Configure the settings for a multi-app kiosk</span></span>

<span data-ttu-id="30f40-365">本節摘要說明多應用程式亭所需的設定。</span><span class="sxs-lookup"><span data-stu-id="30f40-365">This section summarizes the settings that a multi-app kiosk requires.</span></span> <span data-ttu-id="30f40-366">如需詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="30f40-366">For more detailed information, see the following articles:</span></span>

- <span data-ttu-id="30f40-367">如需如何在 Intune 中設定 kiosk 設定檔的相關資訊，請參閱 [如何使用 Microsoft Intune 設定 Kiosk 模式](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="30f40-367">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="30f40-368">如需 Intune 中多個 app 網亭可用設定的詳細資訊，請參閱 [多重 app 網亭](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)</span><span class="sxs-lookup"><span data-stu-id="30f40-368">For more information about the available settings for multi-app kiosks in Intune, see [Multi-app kiosks](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)</span></span>
- <span data-ttu-id="30f40-369">如需其他 MDM 服務，請參閱提供者文件中的指示。</span><span class="sxs-lookup"><span data-stu-id="30f40-369">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="30f40-370">如果您需要在 MDM 服務中使用自訂 XML 設定來設定展臺，請 [建立定義 kiosk 配置的 XML](#ppkioskconfig)檔案。</span><span class="sxs-lookup"><span data-stu-id="30f40-370">If you need to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span> <span data-ttu-id="30f40-371">如果您使用 XML 檔案，請務必包含 [「開始」版面](#start-layout-for-hololens)配置。</span><span class="sxs-lookup"><span data-stu-id="30f40-371">If you use an XML file, make sure to include the [Start layout](#start-layout-for-hololens).</span></span>  
- <span data-ttu-id="30f40-372">您也可以選擇在 Intune 或其他 MDM 服務中使用自訂開始配置。</span><span class="sxs-lookup"><span data-stu-id="30f40-372">You can optionally use a custom Start layout with Intune or other MDM services.</span></span> <span data-ttu-id="30f40-373">如需詳細資訊，請參閱 [ (Intune 的 [啟動版面配置檔案] 和其他) ](#start-layout-file-for-mdm-intune-and-others)。</span><span class="sxs-lookup"><span data-stu-id="30f40-373">For more information, see [Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

1. <span data-ttu-id="30f40-374">選取 [**在 S 模式裝置中以 Windows 10 為目標]**  >  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="30f40-374">Select **Target Windows 10 in S mode devices** > **No**.</span></span>  
   >[!NOTE]  
   > <span data-ttu-id="30f40-375">在商務用 Windows 全息版中不支援 S 模式。</span><span class="sxs-lookup"><span data-stu-id="30f40-375">S mode isn't supported on Windows Holographic for Business.</span></span>
1. <span data-ttu-id="30f40-376">選取 [**使用者登入類型**  >  **Azure AD 使用者或群組**或**使用者登入類型**  >  **HoloLens 訪客**]，然後新增一個或多個使用者群組或帳戶。</span><span class="sxs-lookup"><span data-stu-id="30f40-376">Select **User logon type** > **Azure AD user or group** or **User logon type** > **HoloLens visitor**, and then add one or more user groups or accounts.</span></span>  

   <span data-ttu-id="30f40-377">只有屬於您在 [ **使用者登入類型** ] 中指定之群組或帳戶的使用者，才能使用 kiosk 體驗。</span><span class="sxs-lookup"><span data-stu-id="30f40-377">Only users who belong to the groups or accounts that you specify in **User logon type** can use the kiosk experience.</span></span>

1. <span data-ttu-id="30f40-378">使用下列選項選取一或多個應用程式：</span><span class="sxs-lookup"><span data-stu-id="30f40-378">Select one or more apps by using the following options:</span></span>
   - <span data-ttu-id="30f40-379">若要新增已上傳的商務用應用程式，請選取 [ **新增 store app** ]，然後選取您要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="30f40-379">To add an uploaded line-of-business app, select **Add store app** and then select the app that you want.</span></span>
   - <span data-ttu-id="30f40-380">若要新增應用程式，請指定其 AUMID，選取 [ **由 AUMID 新增** ]，然後輸入 APP 的 AUMID。</span><span class="sxs-lookup"><span data-stu-id="30f40-380">To add an app by specifying its AUMID, select **Add by AUMID** and then enter the AUMID of the app.</span></span> [<span data-ttu-id="30f40-381">請參閱可用的 Aumid 清單</span><span class="sxs-lookup"><span data-stu-id="30f40-381">See the list of available AUMIDs</span></span>](#aumids)

<span data-ttu-id="30f40-382">下一步是將設定檔 [指派](#mdmassign) 給群組。</span><span class="sxs-lookup"><span data-stu-id="30f40-382">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a id="mdmassign"></a><span data-ttu-id="30f40-383">MDM，步驟 4 &ndash; 將 kiosk 配置設定檔指派給群組</span><span class="sxs-lookup"><span data-stu-id="30f40-383">MDM, step 4 &ndash; Assign the kiosk configuration profile to a group</span></span>

<span data-ttu-id="30f40-384">使用 kiosk 配置設定檔的 [ **作業** ] 頁面，設定您想要的 kiosk 配置部署位置。</span><span class="sxs-lookup"><span data-stu-id="30f40-384">Use the **Assignments** page of the kiosk configuration profile to set where you want the kiosk configuration to deploy.</span></span> <span data-ttu-id="30f40-385">在最簡單的情況下，您會將 kiosk 配置設定檔指派給將裝置在 MDM 中註冊時將包含 HoloLens 裝置的群組。</span><span class="sxs-lookup"><span data-stu-id="30f40-385">In the simplest case, you assign the kiosk configuration profile to a group that will contain the HoloLens device when the device enrolls in MDM.</span></span>

### <a id="mdmsingledeploy"></a><span data-ttu-id="30f40-386">MDM、步驟 5 (單一 app) &ndash; 部署單一應用程式亭</span><span class="sxs-lookup"><span data-stu-id="30f40-386">MDM, step 5 (single-app) &ndash; Deploy a single-app kiosk</span></span>

<span data-ttu-id="30f40-387">當您使用 MDM 系統時，您可以在 OOBE 期間在 MDM 中註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="30f40-387">When you use an MDM system, you can enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="30f40-388">在 OOBE 完成之後，登入裝置很簡單。</span><span class="sxs-lookup"><span data-stu-id="30f40-388">After OOBE finishes, signing in to the device is easy.</span></span>

<span data-ttu-id="30f40-389">在 OOBE 期間，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="30f40-389">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="30f40-390">使用您在 kiosk 配置設定檔中指定的帳號登入。</span><span class="sxs-lookup"><span data-stu-id="30f40-390">Sign in by using the account that you specified in the kiosk configuration profile.</span></span>
1. <span data-ttu-id="30f40-391">註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="30f40-391">Enroll the device.</span></span> <span data-ttu-id="30f40-392">確認裝置已新增到指派給它的群組。</span><span class="sxs-lookup"><span data-stu-id="30f40-392">Make sure that the device is added to the group that the kiosk configuration profile is assigned to.</span></span>
1. <span data-ttu-id="30f40-393">等待 OOBE 完成，針對要下載並安裝的 microsoft store 應用程式，以及要套用的原則。</span><span class="sxs-lookup"><span data-stu-id="30f40-393">Wait for OOBE to finish, for the store app to download and install, and for policies to be applied.</span></span> <span data-ttu-id="30f40-394">然後重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="30f40-394">Then restart the device.</span></span>

<span data-ttu-id="30f40-395">下次登入裝置時，kiosk app 就會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="30f40-395">The next time you sign in to the device, the kiosk app should automatically start.</span></span>

<span data-ttu-id="30f40-396">如果此時沒有看到您的展臺設定，請 [檢查作業狀態](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。</span><span class="sxs-lookup"><span data-stu-id="30f40-396">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

### <a id="mdmmultideploy"></a><span data-ttu-id="30f40-397">MDM、步驟 5 (多重 app) &ndash; 部署多應用程式亭</span><span class="sxs-lookup"><span data-stu-id="30f40-397">MDM, step 5 (multi-app) &ndash; Deploy a multi-app kiosk</span></span>

<span data-ttu-id="30f40-398">當您使用 MDM 系統時，您可以將裝置加入到 Azure AD 租使用者，並在 OOBE 期間在 MDM 中註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="30f40-398">When you use an MDM system, you can join the device to your Azure AD tenant and enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="30f40-399">如有需要，請將註冊資訊提供給使用者，讓他們可以在 OOBE 程式中使用。</span><span class="sxs-lookup"><span data-stu-id="30f40-399">If appropriate, provide the enrollment information to the users so that they have it available during the OOBE process.</span></span>

> [!NOTE]  
> <span data-ttu-id="30f40-400">如果您已將 kiosk 配置設定檔指派給包含使用者的群組，請確認其中一個使用者帳戶是第一個登入裝置的帳戶。</span><span class="sxs-lookup"><span data-stu-id="30f40-400">If you have assigned the kiosk configuration profile to a group that contains users, make sure that one of those user accounts is the first account to sign in to the device.</span></span>

<span data-ttu-id="30f40-401">在 OOBE 期間，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="30f40-401">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="30f40-402">使用屬於 [ **使用者登入類型** ] 群組的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="30f40-402">Sign in by using the account that belongs to the **User logon type** group.</span></span>
1. <span data-ttu-id="30f40-403">註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="30f40-403">Enroll the device.</span></span>
1. <span data-ttu-id="30f40-404">等待任何屬於 kiosk 配置設定檔的 app 下載並安裝。</span><span class="sxs-lookup"><span data-stu-id="30f40-404">Wait for any apps that are part of the kiosk configuration profile to download and install.</span></span> <span data-ttu-id="30f40-405">此外，請等待應用原則。</span><span class="sxs-lookup"><span data-stu-id="30f40-405">Also, wait for policies to be applied.</span></span>  
1. <span data-ttu-id="30f40-406">在 OOBE 完成之後，您可以從 Microsoft 網上商店或邊載安裝其他 app。</span><span class="sxs-lookup"><span data-stu-id="30f40-406">After OOBE finishes, you can install additional apps from the Microsoft store or by sideloading.</span></span> <span data-ttu-id="30f40-407">裝置所歸屬的群組自動安裝[所需的應用程式](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)。</span><span class="sxs-lookup"><span data-stu-id="30f40-407">[Required apps](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) for the group that the device belongs to install automatically.</span></span>
1. <span data-ttu-id="30f40-408">安裝完成後，請重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="30f40-408">After the installation finishes, restart the device.</span></span>

<span data-ttu-id="30f40-409">下次您使用屬於 **使用者登入類型**的帳戶登入裝置時，kiosk app 應該會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="30f40-409">The next time you sign in to the device by using an account that belongs to the **User logon type**, the kiosk app should automatically launch.</span></span>

<span data-ttu-id="30f40-410">如果此時沒有看到您的展臺設定，請 [檢查作業狀態](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。</span><span class="sxs-lookup"><span data-stu-id="30f40-410">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

## <span data-ttu-id="30f40-411">使用預配套件來設定單一 app 或多重應用程式亭</span><span class="sxs-lookup"><span data-stu-id="30f40-411">Use a provisioning package to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="30f40-412">若要使用預配套件設定 kiosk 模式，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="30f40-412">To set up kiosk mode by using a provisioning package, follow these steps.</span></span>

1. <span data-ttu-id="30f40-413">[建立定義 kiosk](#ppkioskconfig)設定的 XML 檔案，包括 [開始版面](#start-layout-for-hololens)配置。</span><span class="sxs-lookup"><span data-stu-id="30f40-413">[Create an XML file that defines the kiosk configuration.](#ppkioskconfig), including a [Start layout](#start-layout-for-hololens).</span></span>
2. [<span data-ttu-id="30f40-414">將 XML 檔案新增至預配套件。</span><span class="sxs-lookup"><span data-stu-id="30f40-414">Add the XML file to a provisioning package.</span></span>](#ppconfigadd)
3. [<span data-ttu-id="30f40-415">將預配套件套用至 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="30f40-415">Apply the provisioning package to HoloLens.</span></span>](#ppapply)

### <a id="ppkioskconfig"></a><span data-ttu-id="30f40-416">預配套件，步驟 1 &ndash; 建立 kiosk 配置 XML 檔案</span><span class="sxs-lookup"><span data-stu-id="30f40-416">Provisioning package, step 1 &ndash; Create a kiosk configuration XML file</span></span>

<span data-ttu-id="30f40-417">依照 [一般指示，為 Windows 桌面建立 kiosk 配置 XML](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)檔案，除了下列情況：</span><span class="sxs-lookup"><span data-stu-id="30f40-417">Follow [the general instructions to create a kiosk configuration XML file for Windows desktop](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file), except for the following:</span></span>

- <span data-ttu-id="30f40-418">請勿在 Win32) 中加入傳統的 Windows 應用程式 (。</span><span class="sxs-lookup"><span data-stu-id="30f40-418">Do not include Classic Windows applications (Win32).</span></span> <span data-ttu-id="30f40-419">HoloLens 不支援這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="30f40-419">HoloLens does not support these applications.</span></span>
- <span data-ttu-id="30f40-420">使用適用于 HoloLens 的 [預留位置開始版面配置 XML](#start-layout-for-hololens) 。</span><span class="sxs-lookup"><span data-stu-id="30f40-420">Use the [placeholder Start layout XML](#start-layout-for-hololens) for HoloLens.</span></span>
- <span data-ttu-id="30f40-421">選用：新增來賓對 kiosk 設定的存取權</span><span class="sxs-lookup"><span data-stu-id="30f40-421">Optional: Add guest access to the kiosk configuration</span></span>

#### <a id="ppkioskguest"></a><span data-ttu-id="30f40-422">選用：新增來賓對 kiosk 設定的存取權</span><span class="sxs-lookup"><span data-stu-id="30f40-422">Optional: Add guest access to the kiosk configuration</span></span>

<span data-ttu-id="30f40-423">在 XML 檔案的 [配置] [ **Configs**區段](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)中，您可以將名為「**訪客**」的特殊群組設定為允許來賓使用資訊站。</span><span class="sxs-lookup"><span data-stu-id="30f40-423">In the [**Configs** section of the XML file](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs), you can configure a special group named **Visitor** to allow guests to use the kiosk.</span></span> <span data-ttu-id="30f40-424">如果將 kiosk 設定為支援 **「訪客特殊」** 群組，則會在登入頁面中新增「**來賓**」選項。</span><span class="sxs-lookup"><span data-stu-id="30f40-424">When the kiosk is configured to support the **Visitor** special group, a "**Guest**" option is added to the sign-in page.</span></span> <span data-ttu-id="30f40-425">**來賓**帳戶不需要密碼，而且與該帳戶相關聯的任何資料都會在帳戶登出時刪除。</span><span class="sxs-lookup"><span data-stu-id="30f40-425">The **Guest** account does not require a password, and any data that is associated with the account is deleted when the account signs out.</span></span>

<span data-ttu-id="30f40-426">若要啟用 **來賓** 帳戶，請將下列程式碼片段新增至您的 KIOSK 配置 XML：</span><span class="sxs-lookup"><span data-stu-id="30f40-426">To enable the **Guest** account, add the following snippet to your kiosk configuration XML:</span></span>

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a><span data-ttu-id="30f40-427">HoloLens 的預留位置開始時間版面配置</span><span class="sxs-lookup"><span data-stu-id="30f40-427">Placeholder Start layout for HoloLens</span></span>

<span data-ttu-id="30f40-428">如果您使用 [預配套件](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 來設定多應用程式資訊站，程式需要開始版面配置。</span><span class="sxs-lookup"><span data-stu-id="30f40-428">If you use a [provisioning package](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) to configure a multi-app kiosk, the procedure requires a Start layout.</span></span> <span data-ttu-id="30f40-429">在商務用 Windows 全息版中不支援開始進行版面配置自訂。</span><span class="sxs-lookup"><span data-stu-id="30f40-429">Start layout customization isn't supported in Windows Holographic for Business.</span></span> <span data-ttu-id="30f40-430">因此，您必須使用預留位置 [開始] 版面配置。</span><span class="sxs-lookup"><span data-stu-id="30f40-430">Therefore, you'll have to use a placeholder Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="30f40-431">因為單一 app 展臺會在使用者登入時啟動展臺應用程式，所以它不會使用 [開始] 功能表，也不需要開始進行版面配置。</span><span class="sxs-lookup"><span data-stu-id="30f40-431">Because a single-app kiosk starts the kiosk app when a user signs in, it does not use a Start menu and does not have to have a Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="30f40-432">如果您使用 [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 來設定多個 app 的展臺，您可以選擇使用 [開始] 版面配置。</span><span class="sxs-lookup"><span data-stu-id="30f40-432">If you use [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) to set up a multi-app kiosk, you can optionally use a Start layout.</span></span> <span data-ttu-id="30f40-433">如需詳細資訊，請參閱 [MDM (Intune 的 [預留位置啟動版面 ](#start-layout-file-for-mdm-intune-and-others)配置] 檔案，以及其他) 。</span><span class="sxs-lookup"><span data-stu-id="30f40-433">For more information, see [Placeholder Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

<span data-ttu-id="30f40-434">在 [開始] 版面配置中，將下列 **StartLayout** 區段新增至 KIOSK 提供 XML 檔案：</span><span class="sxs-lookup"><span data-stu-id="30f40-434">For the Start layout, add the following **StartLayout** section to the kiosk provisioning XML file:</span></span>

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

#### <a id="start-layout-file-for-mdm-intune-and-others"></a><span data-ttu-id="30f40-435">MDM (Intune 和其他人的預留位置啟動版面配置檔案) </span><span class="sxs-lookup"><span data-stu-id="30f40-435">Placeholder Start layout file for MDM (Intune and others)</span></span>

<span data-ttu-id="30f40-436">將下列範例儲存為 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="30f40-436">Save the following sample as an XML file.</span></span> <span data-ttu-id="30f40-437">您可以在 Microsoft (Intune 中設定多應用程式亭，或在提供 kiosk 設定檔的另一個 MDM 服務中，使用這個檔案) 。</span><span class="sxs-lookup"><span data-stu-id="30f40-437">You can use this file when you configure the multi-app kiosk in Microsoft Intune (or in another MDM service that provides a kiosk profile).</span></span>

> [!NOTE]
> <span data-ttu-id="30f40-438">如果您必須使用自訂設定及完整的 XML 配置來設定 MDM 服務中的展臺，請使用 [提供套件的開始配置指示](#start-layout-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="30f40-438">If you have to use a custom setting and full XML configuration to set up a kiosk in your MDM service, use the [Start layout instructions for a provisioning package](#start-layout-for-hololens).</span></span>

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

### <a id="ppconfigadd"></a><span data-ttu-id="30f40-439">Prov.</span><span class="sxs-lookup"><span data-stu-id="30f40-439">Prov.</span></span> <span data-ttu-id="30f40-440">套件，步驟 2 &ndash; 將 kiosk 配置 XML 檔案新增至置備套件</span><span class="sxs-lookup"><span data-stu-id="30f40-440">package, step 2 &ndash; Add the kiosk configuration XML file to a provisioning package</span></span>

1. <span data-ttu-id="30f40-441">開啟 [Windows 配置設計](https://www.microsoft.com/store/apps/9nblggh4tx22)工具。</span><span class="sxs-lookup"><span data-stu-id="30f40-441">Open [Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22).</span></span>
1. <span data-ttu-id="30f40-442">選取 [ **高級提供**]，輸入您專案的名稱，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="30f40-442">Select **Advanced provisioning**, enter a name for your project, and then select **Next**.</span></span>
1. <span data-ttu-id="30f40-443">選取 [ **Windows 10 全息**版]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="30f40-443">Select **Windows 10 Holographic**, and then select **Next**.</span></span>
1. <span data-ttu-id="30f40-444">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="30f40-444">Select **Finish**.</span></span> <span data-ttu-id="30f40-445">套件的工作區就會開啟。</span><span class="sxs-lookup"><span data-stu-id="30f40-445">The workspace for your package opens.</span></span>
1. <span data-ttu-id="30f40-446">選取 [**執行時間設定**]  >  **AssignedAccess**[  >  **MultiAppAssignedAccessSettings**]。</span><span class="sxs-lookup"><span data-stu-id="30f40-446">Select **Runtime settings** > **AssignedAccess** > **MultiAppAssignedAccessSettings**.</span></span>
1. <span data-ttu-id="30f40-447">在中央窗格中，選取 **[流覽]** 以找出並選取您所建立的 KIOSK 配置 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="30f40-447">In the center pane, select **Browse** to locate and select the kiosk configuration XML file that you created.</span></span>

   ![Windows 設定設計工具中 MultiAppAssignedAccessSettings 欄位的螢幕擷取畫面](./images/multiappassignedaccesssettings.png)

1. <span data-ttu-id="30f40-449">**選用**。</span><span class="sxs-lookup"><span data-stu-id="30f40-449">**Optional**.</span></span> <span data-ttu-id="30f40-450"> (如果您想要在裝置的初始設定之後套用預配套件，且展臺裝置上已提供系統管理員使用者，請跳過此步驟。 ) 選取 [ **執行時間設定** &gt; **帳戶** &gt; **使用者**]，然後建立使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="30f40-450">(If you want to apply the provisioning package after the initial setup of the device, and there is an admin user already available on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a user account.</span></span> <span data-ttu-id="30f40-451">提供使用者名稱和密碼，然後選取 [ **UserGroup**系統  >  **管理員**]。</span><span class="sxs-lookup"><span data-stu-id="30f40-451">Provide a user name and password, and then select **UserGroup** > **Administrators**.</span></span>  
  
     <span data-ttu-id="30f40-452">您可以使用此帳戶來查看 [預配狀態與記錄]。</span><span class="sxs-lookup"><span data-stu-id="30f40-452">By using this account, you can view the provisioning status and logs.</span></span>  
1. <span data-ttu-id="30f40-453">**選用**。</span><span class="sxs-lookup"><span data-stu-id="30f40-453">**Optional**.</span></span> <span data-ttu-id="30f40-454"> (如果您在展臺裝置上已有非系統管理員帳戶，請跳過此步驟。 ) 選取 [ **執行時間設定** &gt; **帳戶** &gt; **使用者**]，然後建立本機使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="30f40-454">(If you already have a non-admin account on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a local user account.</span></span> <span data-ttu-id="30f40-455">請確定使用者名稱與您在配置 XML 中指定的帳號相同。</span><span class="sxs-lookup"><span data-stu-id="30f40-455">Make sure that the user name is the same as for the account that you specify in the configuration XML.</span></span> <span data-ttu-id="30f40-456">選取 [ **UserGroup**  >  **標準使用者**]。</span><span class="sxs-lookup"><span data-stu-id="30f40-456">Select **UserGroup** > **Standard Users**.</span></span>
1. <span data-ttu-id="30f40-457">選取 **[**  >  **儲存**檔案]。</span><span class="sxs-lookup"><span data-stu-id="30f40-457">Select **File** > **Save**.</span></span>
1. <span data-ttu-id="30f40-458">選取 [**匯出**  >  **預配套件**]，然後選取 [**擁有**者  >  **IT 系統管理員**]。這會將這個預配套件的優先順序設為高於從其他來源套用至此裝置的預配套件。</span><span class="sxs-lookup"><span data-stu-id="30f40-458">Select **Export** > **Provisioning package**, and then select **Owner** > **IT Admin**. This sets the precedence of this provisioning package higher than provisioning packages that are applied to this device from other sources.</span></span>
1. <span data-ttu-id="30f40-459">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="30f40-459">Select **Next**.</span></span>
1. <span data-ttu-id="30f40-460">在 [ **預配套件安全性** ] 頁面上，選取安全性選項。</span><span class="sxs-lookup"><span data-stu-id="30f40-460">On the **Provisioning package security** page, select a security option.</span></span>
   > [!IMPORTANT]  
   > <span data-ttu-id="30f40-461">如果您選取 [ **啟用套件簽署**]，您也必須選取要用來簽署套件的有效憑證。</span><span class="sxs-lookup"><span data-stu-id="30f40-461">If you select **Enable package signing**, you also have to select a valid certificate to use for signing the package.</span></span> <span data-ttu-id="30f40-462">若要這樣做，請選取 **[流覽]** ，然後選取您要用來簽署套件的憑證。</span><span class="sxs-lookup"><span data-stu-id="30f40-462">To do this, select **Browse** and select the certificate that you want to use to sign the package.</span></span>
   
   > [!CAUTION]  
   > <span data-ttu-id="30f40-463">請勿選取 [ **啟用套件加密**]。</span><span class="sxs-lookup"><span data-stu-id="30f40-463">Do not select **Enable package encryption**.</span></span> <span data-ttu-id="30f40-464">在 HoloLens 裝置上，此設定會導致置備失敗。</span><span class="sxs-lookup"><span data-stu-id="30f40-464">On HoloLens devices, this setting causes provisioning to fail.</span></span>
1. <span data-ttu-id="30f40-465">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="30f40-465">Select **Next**.</span></span>
1. <span data-ttu-id="30f40-466">指定要在建立預配套件時所要執行的輸出位置。</span><span class="sxs-lookup"><span data-stu-id="30f40-466">Specify the output location where you want the provisioning package to go when it's built.</span></span> <span data-ttu-id="30f40-467">Windows 設定設計工具預設會使用專案資料夾做為輸出位置。</span><span class="sxs-lookup"><span data-stu-id="30f40-467">By default, Windows Configuration Designer uses the project folder as the output location.</span></span> <span data-ttu-id="30f40-468">如果您想要變更輸出位置，請選取 **[流覽]**。</span><span class="sxs-lookup"><span data-stu-id="30f40-468">If you want to change the output location, select **Browse**.</span></span> <span data-ttu-id="30f40-469">完成後，請選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="30f40-469">When you are finished, select **Next**.</span></span>
1. <span data-ttu-id="30f40-470">選取 [ **組建** ]，開始建立套件。</span><span class="sxs-lookup"><span data-stu-id="30f40-470">Select **Build** to start building the package.</span></span> <span data-ttu-id="30f40-471">建置佈建套件並不需要很長的時間。</span><span class="sxs-lookup"><span data-stu-id="30f40-471">The provisioning package doesn't take long to build.</span></span> <span data-ttu-id="30f40-472">[建立] 頁面會顯示專案資訊，且進度列會指出組建狀態。</span><span class="sxs-lookup"><span data-stu-id="30f40-472">The build page displays the project information, and the progress bar indicates the build status.</span></span>

### <a id="ppapply"></a><span data-ttu-id="30f40-473">預配套件，步驟3會 &ndash; 將預配套件套用至 HoloLens</span><span class="sxs-lookup"><span data-stu-id="30f40-473">Provisioning package, step 3 &ndash; Apply the provisioning package to HoloLens</span></span>

<span data-ttu-id="30f40-474">「使用預配套件設定 HoloLens」一文提供在下列情況下套用預配套件的詳細指示：</span><span class="sxs-lookup"><span data-stu-id="30f40-474">The "Configure HoloLens by using a provisioning package" article provides detailed instructions to apply the provisioning package under the following circumstances:</span></span>

- <span data-ttu-id="30f40-475">您最初可以 [在安裝期間將預配套件套用到 HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。</span><span class="sxs-lookup"><span data-stu-id="30f40-475">You can initially [apply a provisioning package to HoloLens during setup](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).</span></span>

- <span data-ttu-id="30f40-476">您也可以 [在安裝完成後將預配套件套用至 HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)。</span><span class="sxs-lookup"><span data-stu-id="30f40-476">You can also [apply a provisioning package to HoloLens after setup](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup).</span></span>

## <span data-ttu-id="30f40-477">使用 Windows Device Portal 設定單一應用程式亭</span><span class="sxs-lookup"><span data-stu-id="30f40-477">Use the Windows Device Portal to set up a single-app kiosk</span></span>

<span data-ttu-id="30f40-478">若要使用 Windows Device Portal 設定 kiosk 模式，請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="30f40-478">To set up kiosk mode by using the Windows Device Portal, follow these steps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="30f40-479">[展臺模式] 只有在裝置已安裝 [Windows 全息企業](hololens1-upgrade-enterprise.md) 版時才能使用。</span><span class="sxs-lookup"><span data-stu-id="30f40-479">Kiosk mode is available only if the device has [Windows Holographic for Business](hololens1-upgrade-enterprise.md) installed.</span></span>

1. <span data-ttu-id="30f40-480">[設定 HoloLens 裝置以使用 Windows Device Portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)。</span><span class="sxs-lookup"><span data-stu-id="30f40-480">[Set up the HoloLens device to use the Windows Device Portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal).</span></span> <span data-ttu-id="30f40-481">Device Portal 是您 HoloLens 上的網頁伺服器，您可以從電腦上的網頁瀏覽器與它連線。</span><span class="sxs-lookup"><span data-stu-id="30f40-481">The Device Portal is a web server on your HoloLens that you can connect to from a web browser on your PC.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="30f40-482">當您將 HoloLens 設定為使用 Device Portal 時，必須在裝置上啟用 [開發人員模式]。</span><span class="sxs-lookup"><span data-stu-id="30f40-482">When you set up HoloLens to use the Device Portal, you have to enable Developer Mode on the device.</span></span> <span data-ttu-id="30f40-483">Windows 全息版裝置上的開發人員模式可讓您使用側載入 app。</span><span class="sxs-lookup"><span data-stu-id="30f40-483">Developer Mode on a device that has Windows Holographic for Business enables you to side-load apps.</span></span> <span data-ttu-id="30f40-484">不過，此設定會建立使用者可安裝未透過 Microsoft Store 認證之 app 的風險。</span><span class="sxs-lookup"><span data-stu-id="30f40-484">However, this setting creates a risk that a user can install apps that have not been certified by the Microsoft Store.</span></span> <span data-ttu-id="30f40-485">系統管理員可以使用[原則 CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)中的**ApplicationManagement/AllowDeveloper 解除鎖定**設定，來封鎖啟用開發人員模式的功能。</span><span class="sxs-lookup"><span data-stu-id="30f40-485">Administrators can block the ability to enable Developer Mode by using the **ApplicationManagement/AllowDeveloper Unlock** setting in the [Policy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider).</span></span> [<span data-ttu-id="30f40-486">深入了解開發人員模式。</span><span class="sxs-lookup"><span data-stu-id="30f40-486">Learn more about Developer Mode.</span></span>](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. <span data-ttu-id="30f40-487">在電腦上，使用 [wi-fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) 或 [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)連接至 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="30f40-487">On a computer, connect to the HoloLens by using [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) or [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb).</span></span>

1. <span data-ttu-id="30f40-488">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="30f40-488">Do one of the following:</span></span>
   - <span data-ttu-id="30f40-489">如果您是第一次連線到 Windows Device Portal，請 [建立使用者名稱和密碼](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)</span><span class="sxs-lookup"><span data-stu-id="30f40-489">If you are connecting to the Windows Device Portal for the first time, [create a user name and password](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)</span></span>
   - <span data-ttu-id="30f40-490">輸入您先前設定的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="30f40-490">Enter the user name and password that you previously set up.</span></span>

    > [!TIP]
    > <span data-ttu-id="30f40-491">如果您在瀏覽器中看到憑證有誤，請遵循[下列疑難排解步驟](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)。</span><span class="sxs-lookup"><span data-stu-id="30f40-491">If you see a certificate error in the browser, follow [these troubleshooting steps](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate).</span></span>

1. <span data-ttu-id="30f40-492">在 Windows Device Portal 中，選取 [ **展臺模式]**。</span><span class="sxs-lookup"><span data-stu-id="30f40-492">In the Windows Device Portal, select **Kiosk Mode**.</span></span>

1. <span data-ttu-id="30f40-493">選取 [ **啟用 Kiosk 模式]**，選取裝置啟動時要執行的應用程式，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="30f40-493">Select **Enable Kiosk Mode**, select an app to run when the device starts, and then select **Save**.</span></span>

    ![Kiosk 模式](images/kiosk.png)
1. <span data-ttu-id="30f40-495">重新開機 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="30f40-495">Restart HoloLens.</span></span> <span data-ttu-id="30f40-496">如果您仍開啟了 [裝置入口網站] 頁面，您可以選取頁面頂端的 [ **重新開機** ]。</span><span class="sxs-lookup"><span data-stu-id="30f40-496">If you still have your Device Portal page open, you can select **Restart** at the top of the page.</span></span>

## <span data-ttu-id="30f40-497">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="30f40-497">More information</span></span>

<span data-ttu-id="30f40-498">瞭解如何使用預配套件來設定展臺。</span><span class="sxs-lookup"><span data-stu-id="30f40-498">Watch how to configure a kiosk by using a provisioning package.</span></span>  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]
