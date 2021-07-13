---
title: Windows Defender應用程式控制-WDAC
description: 概述什麼是 Windows Defender 應用程式控制，以及如何使用它來管理 HoloLens 的混合現實裝置。
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
ms.openlocfilehash: a27a16913873c5245f734dbe084eb2b7ed007c20
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639925"
---
# <a name="windows-defender-application-control---wdac"></a><span data-ttu-id="31291-103">Windows Defender應用程式控制-WDAC</span><span class="sxs-lookup"><span data-stu-id="31291-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="31291-104">WDAC 可讓 IT 系統管理員設定其裝置，以封鎖在裝置上啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="31291-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="31291-105">這與裝置限制的方法不同，例如 Kiosk 模式，其中使用者會看到 UI 來隱藏裝置上的應用程式，但仍可啟動。</span><span class="sxs-lookup"><span data-stu-id="31291-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="31291-106">在執行 WDAC 的同時，應用程式仍會顯示在 [所有應用程式] 清單中，但 WDAC 會停止這些應用程式和進程，使其無法由裝置使用者啟動。</span><span class="sxs-lookup"><span data-stu-id="31291-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="31291-107">可能指派一個以上的 WDAC 原則給裝置。</span><span class="sxs-lookup"><span data-stu-id="31291-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="31291-108">如果系統上設定了多個 WDAC 原則，則最嚴格的原則會生效。</span><span class="sxs-lookup"><span data-stu-id="31291-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="31291-109">當使用者嘗試啟動由 WDAC 封鎖的應用程式時，HoloLens 不會收到有關無法啟動該應用程式的通知。</span><span class="sxs-lookup"><span data-stu-id="31291-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="31291-110">下列指南可讓使用者瞭解如何[使用 WDAC 和 Windows PowerShell，在 HoloLens 2 裝置上使用 Microsoft Intune 來允許或封鎖應用程式](/mem/intune/configuration/custom-profile-hololens)。</span><span class="sxs-lookup"><span data-stu-id="31291-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="31291-111">當使用者使用第一個範例步驟搜尋安裝在其 Windows 10 電腦上的應用程式時，可能需要進行幾次嘗試縮小結果的範圍。</span><span class="sxs-lookup"><span data-stu-id="31291-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="31291-112">如果您不知道封裝的完整名稱，您可能需要執行 ' Add-appxpackage-name \* YourBestGuess \* ' 數次，才能找到它。</span><span class="sxs-lookup"><span data-stu-id="31291-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="31291-113">然後，一旦您的名稱執行 ' $package 1 = Get-AppxPackage-name PackageName '</span><span class="sxs-lookup"><span data-stu-id="31291-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="31291-114">例如，執行下列 Microsoft Edge 將會傳回一個以上的結果，但從該清單中，您可以識別出所需的完整名稱是 MicrosoftEdge。</span><span class="sxs-lookup"><span data-stu-id="31291-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a><span data-ttu-id="31291-115">HoloLens 上應用程式的套件系列名稱</span><span class="sxs-lookup"><span data-stu-id="31291-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="31291-116">在上方連結的指南中，您可以手動編輯 newPolicy.xml，並為僅安裝在 HoloLens 上的應用程式新增其套件系列名稱的規則。</span><span class="sxs-lookup"><span data-stu-id="31291-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="31291-117">有時您可以使用的應用程式不在您想要新增至原則的桌上型電腦上。</span><span class="sxs-lookup"><span data-stu-id="31291-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="31291-118">以下是 HoloLens 2 裝置常用且 In-Box 的應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="31291-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="31291-119">應用程式名稱</span><span class="sxs-lookup"><span data-stu-id="31291-119">App Name</span></span>                   | <span data-ttu-id="31291-120">套件家族名稱</span><span class="sxs-lookup"><span data-stu-id="31291-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="31291-121">3D 檢視器</span><span class="sxs-lookup"><span data-stu-id="31291-121">3D Viewer</span></span>                  | <span data-ttu-id="31291-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="31291-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="31291-123">應用程式安裝程式</span><span class="sxs-lookup"><span data-stu-id="31291-123">App Installer</span></span>              | <span data-ttu-id="31291-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="31291-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span></span>         |
| <span data-ttu-id="31291-125">Calendar</span><span class="sxs-lookup"><span data-stu-id="31291-125">Calendar</span></span>                   | <span data-ttu-id="31291-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="31291-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="31291-127">相機</span><span class="sxs-lookup"><span data-stu-id="31291-127">Camera</span></span>                     | <span data-ttu-id="31291-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="31291-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="31291-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="31291-129">Cortana</span></span>                    | <span data-ttu-id="31291-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="31291-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="31291-131">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="31291-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="31291-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="31291-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="31291-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="31291-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="31291-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="31291-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="31291-135">意見反應中樞</span><span class="sxs-lookup"><span data-stu-id="31291-135">Feedback Hub</span></span>               | <span data-ttu-id="31291-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="31291-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="31291-137">檔案總管</span><span class="sxs-lookup"><span data-stu-id="31291-137">File Explorer</span></span>              | <span data-ttu-id="31291-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="31291-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="31291-139">電子郵件</span><span class="sxs-lookup"><span data-stu-id="31291-139">Mail</span></span>                       | <span data-ttu-id="31291-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="31291-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="31291-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="31291-141">Microsoft Store</span></span>            | <span data-ttu-id="31291-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="31291-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="31291-143">電影與電視</span><span class="sxs-lookup"><span data-stu-id="31291-143">Movies & TV</span></span>                | <span data-ttu-id="31291-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="31291-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="31291-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="31291-145">OneDrive</span></span>                   | <span data-ttu-id="31291-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="31291-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="31291-147">照片</span><span class="sxs-lookup"><span data-stu-id="31291-147">Photos</span></span>                     | <span data-ttu-id="31291-148">微軟。Windows。Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="31291-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="31291-149">設定</span><span class="sxs-lookup"><span data-stu-id="31291-149">Settings</span></span>                   | <span data-ttu-id="31291-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="31291-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="31291-151">提示</span><span class="sxs-lookup"><span data-stu-id="31291-151">Tips</span></span>                       | <span data-ttu-id="31291-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="31291-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="31291-153">1-封鎖應用程式安裝程式只會封鎖應用程式安裝程式應用程式，而不會封鎖從其他來源（例如 Microsoft Store 或您的 MDM 解決方案）安裝的應用程式。</span><span class="sxs-lookup"><span data-stu-id="31291-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <a name="how-to-find-a-package-family-name"></a><span data-ttu-id="31291-154">如何尋找套件系列名稱</span><span class="sxs-lookup"><span data-stu-id="31291-154">How to find a Package Family Name</span></span>

<span data-ttu-id="31291-155">如果應用程式不在此清單中，則使用者可能會使用裝置入口網站，連接到已安裝要封鎖之應用程式的 HoloLens 2，以判斷 PackageRelativeID 以及從中取得 PackageFamilyName。</span><span class="sxs-lookup"><span data-stu-id="31291-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="31291-156">在 HoloLens 2 裝置上安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="31291-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="31291-157">開啟適用于開發人員的設定 > 更新 & 安全性 >，並啟用 **開發人員模式**，然後再啟用 **裝置入口網站**。</span><span class="sxs-lookup"><span data-stu-id="31291-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="31291-158">如需更多詳細資訊 [，請參閱這裡的設定和使用裝置入口網站](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="31291-158">More more details instructions read more about [setup and use of device portal here](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="31291-159">裝置入口網站連線之後，請流覽至 **Views** 然後再流覽至 [ **應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="31291-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="31291-160">在 [已安裝的應用程式] 面板中，使用下拉式清單來選取已安裝的應用程式。</span><span class="sxs-lookup"><span data-stu-id="31291-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="31291-161">找出 PackageRelativeID。</span><span class="sxs-lookup"><span data-stu-id="31291-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="31291-162">將應用程式字元複製到！之前，這些字元將會是您的 PackageFamilyName。</span><span class="sxs-lookup"><span data-stu-id="31291-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


