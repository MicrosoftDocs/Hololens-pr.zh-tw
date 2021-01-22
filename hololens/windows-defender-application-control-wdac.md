---
title: Windows Defender 應用程式控制 (WDAC)
description: 概觀瞭解何者是 Windows Defender 應用程式控制項，以及如何使用它來管理 HoloLens 混合實境裝置。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 23c9a274387424e8f084a4729ee621e130820716
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284134"
---
# <span data-ttu-id="99a5b-103">Windows Defender 應用程式控制 (WDAC)</span><span class="sxs-lookup"><span data-stu-id="99a5b-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="99a5b-104">WDAC 可讓 IT 系統管理員設定其裝置，以封鎖裝置上的應用程式啟動。</span><span class="sxs-lookup"><span data-stu-id="99a5b-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="99a5b-105">這和裝置限制方法不同，例如 Kiosk 模式，使用者會以 UI 呈現，此 UI 會隱藏裝置上的應用程式，但仍可以啟動。</span><span class="sxs-lookup"><span data-stu-id="99a5b-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="99a5b-106">執行 WDAC 時，這些應用程式仍然顯示在所有應用程式清單中，但 WDAC 會停止這些 App 與程式，裝置使用者無法啟動這些 App 與程式。</span><span class="sxs-lookup"><span data-stu-id="99a5b-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="99a5b-107">裝置可指派多個 WDAC 政策。</span><span class="sxs-lookup"><span data-stu-id="99a5b-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="99a5b-108">如果在一個系統上設定了多個 WDAC 策略，則限制最多的策略會生效。</span><span class="sxs-lookup"><span data-stu-id="99a5b-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="99a5b-109">當使用者嘗試啟動由 WDAC 封鎖的應用程式時，在 HoloLens 上，不會收到無法啟動該應用程式的通知。</span><span class="sxs-lookup"><span data-stu-id="99a5b-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="99a5b-110">以下指南供使用者瞭解如何使用 WDAC 和 Windows PowerShell 來允許或封鎖 [HoloLens 2](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)裝置上的應用程式與 Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="99a5b-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="99a5b-111">當使用者使用第一個範例步驟搜尋安裝在其 Windows 10 PC 上的 App 時，可能需要嘗試幾次來縮小結果範圍。</span><span class="sxs-lookup"><span data-stu-id="99a5b-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="99a5b-112">如果您不知道套件的完整名稱，您可能需要執行幾次 Get-AppxPackage -name \*YourBestGuess\*' 才能找到它。</span><span class="sxs-lookup"><span data-stu-id="99a5b-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="99a5b-113">接著，一旦有名稱執行 '$package 1 = Get-AppxPackage -name Actual.PackageName'</span><span class="sxs-lookup"><span data-stu-id="99a5b-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="99a5b-114">例如，針對 Microsoft Edge 執行下列操作將會返回多個結果，但從該清單您可以確認您需要的全名是 Microsoft.MicrosoftEdge。</span><span class="sxs-lookup"><span data-stu-id="99a5b-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="99a5b-115">HoloLens 上的應用程式套件系列名稱</span><span class="sxs-lookup"><span data-stu-id="99a5b-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="99a5b-116">在上方連結的指南中，您可以手動編輯newPolicy.xml並新增只有在 HoloLens 上以套件系列名稱安裝之應用程式的規則。</span><span class="sxs-lookup"><span data-stu-id="99a5b-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="99a5b-117">有時候您可能會使用非桌上型電腦中要新加入至策略的應用程式。</span><span class="sxs-lookup"><span data-stu-id="99a5b-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="99a5b-118">以下是 HoloLens 2 In-Box常用和常用應用程式的清單。</span><span class="sxs-lookup"><span data-stu-id="99a5b-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="99a5b-119">應用程式名稱</span><span class="sxs-lookup"><span data-stu-id="99a5b-119">App Name</span></span>                   | <span data-ttu-id="99a5b-120">套件系列名稱</span><span class="sxs-lookup"><span data-stu-id="99a5b-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="99a5b-121">3D 檢視器</span><span class="sxs-lookup"><span data-stu-id="99a5b-121">3D Viewer</span></span>                  | <span data-ttu-id="99a5b-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="99a5b-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="99a5b-123">應用程式安裝程式</span><span class="sxs-lookup"><span data-stu-id="99a5b-123">App Installer</span></span>              | <span data-ttu-id="99a5b-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</span><span class="sxs-lookup"><span data-stu-id="99a5b-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</span></span></sup>         |
| <span data-ttu-id="99a5b-125">行事曆</span><span class="sxs-lookup"><span data-stu-id="99a5b-125">Calendar</span></span>                   | <span data-ttu-id="99a5b-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="99a5b-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="99a5b-127">相機</span><span class="sxs-lookup"><span data-stu-id="99a5b-127">Camera</span></span>                     | <span data-ttu-id="99a5b-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="99a5b-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="99a5b-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="99a5b-129">Cortana</span></span>                    | <span data-ttu-id="99a5b-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="99a5b-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="99a5b-131">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="99a5b-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="99a5b-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="99a5b-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="99a5b-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="99a5b-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="99a5b-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="99a5b-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="99a5b-135">意見反應中樞</span><span class="sxs-lookup"><span data-stu-id="99a5b-135">Feedback Hub</span></span>               | <span data-ttu-id="99a5b-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="99a5b-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="99a5b-137">檔案總管</span><span class="sxs-lookup"><span data-stu-id="99a5b-137">File Explorer</span></span>              | <span data-ttu-id="99a5b-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="99a5b-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="99a5b-139">Mail</span><span class="sxs-lookup"><span data-stu-id="99a5b-139">Mail</span></span>                       | <span data-ttu-id="99a5b-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="99a5b-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="99a5b-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="99a5b-141">Microsoft Store</span></span>            | <span data-ttu-id="99a5b-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="99a5b-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="99a5b-143">電影與電視</span><span class="sxs-lookup"><span data-stu-id="99a5b-143">Movies & TV</span></span>                | <span data-ttu-id="99a5b-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="99a5b-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="99a5b-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="99a5b-145">OneDrive</span></span>                   | <span data-ttu-id="99a5b-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="99a5b-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="99a5b-147">相片</span><span class="sxs-lookup"><span data-stu-id="99a5b-147">Photos</span></span>                     | <span data-ttu-id="99a5b-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="99a5b-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="99a5b-149">設定</span><span class="sxs-lookup"><span data-stu-id="99a5b-149">Settings</span></span>                   | <span data-ttu-id="99a5b-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="99a5b-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="99a5b-151">提示</span><span class="sxs-lookup"><span data-stu-id="99a5b-151">Tips</span></span>                       | <span data-ttu-id="99a5b-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="99a5b-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="99a5b-153">1 - 封鎖應用程式安裝程式只會封鎖應用程式安裝程式應用程式，不會封鎖從其他來源安裝的應用程式，例如 Microsoft Store 或 MDM 解決方案。</span><span class="sxs-lookup"><span data-stu-id="99a5b-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <span data-ttu-id="99a5b-154">如何尋找套件系列名稱</span><span class="sxs-lookup"><span data-stu-id="99a5b-154">How to find a Package Family Name</span></span>

<span data-ttu-id="99a5b-155">如果清單中沒有應用程式，則使用者可能會使用裝置入口網站，連接至已安裝要封鎖之應用程式的 HoloLens 2，以判斷 PackageRelativeID，並在那裡取得 PackageFamilyName。</span><span class="sxs-lookup"><span data-stu-id="99a5b-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="99a5b-156">在您的 HoloLens 2 裝置上安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="99a5b-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="99a5b-157">開啟設定 ->更新&安全性 ->開發人員，並啟用 **開發人員模式** ，然後 **啟用裝置入口網站**。</span><span class="sxs-lookup"><span data-stu-id="99a5b-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="99a5b-158">在此閱讀更多有關裝置入口網站 [設定及使用的詳細資訊指示](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="99a5b-158">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="99a5b-159">一旦連接裝置入口網站，請流覽至流覽至流覽 **視圖** ，然後流覽 **至應用程式**。</span><span class="sxs-lookup"><span data-stu-id="99a5b-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="99a5b-160">在安裝的應用程式面板中，使用下拉式清單選取已安裝的應用程式。</span><span class="sxs-lookup"><span data-stu-id="99a5b-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="99a5b-161">找到 PackageRelativeID。</span><span class="sxs-lookup"><span data-stu-id="99a5b-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="99a5b-162">在 ！之前複製 App 字元，這些字元就會是您的 PackageFamilyName。</span><span class="sxs-lookup"><span data-stu-id="99a5b-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


