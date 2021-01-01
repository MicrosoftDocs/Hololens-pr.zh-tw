---
title: Windows Defender 應用程式控制 (WDAC)
description: 瞭解 WDAC 是什麼，以及如何使用它來管理 HoloLens 裝置。
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
ms.openlocfilehash: d337f9856eaeac433524d7bb8b60e9a24e264b80
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252644"
---
# <span data-ttu-id="5f9bd-103">Windows Defender 應用程式控制 (WDAC)</span><span class="sxs-lookup"><span data-stu-id="5f9bd-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="5f9bd-104">WDAC 可讓 IT 系統管理員設定其裝置，以封鎖裝置上的應用程式啟動。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="5f9bd-105">這與裝置限制的方法不同（例如 Kiosk 模式），使用者會在其中提供隱藏裝置上 app 的 UI，但仍可啟動這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="5f9bd-106">在已實現 WDAC 的情況下，應用程式仍會顯示在 [所有應用程式] 清單中，但 WDAC 會停止由裝置使用者啟動這些 app 和進程。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="5f9bd-107">可能會為裝置指派一個以上的 WDAC 原則。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="5f9bd-108">如果在系統上設定多個 WDAC 原則，則限制性較強的規則就會生效。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="5f9bd-109">當使用者嘗試啟動由 WDAC 封鎖的應用程式時，他們將不會收到無法啟動該應用程式的通知。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="5f9bd-110">以下是使用者瞭解如何在使用 [Microsoft Intune 的 HoloLens 2 裝置上使用 WDAC 和 Windows PowerShell 來允許或封鎖 app](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)的指南。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="5f9bd-111">當使用者使用第一個範例步驟搜尋安裝在 Windows 10 電腦上的應用程式時，可能需要進行幾個嘗試來縮小結果範圍。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="5f9bd-112">如果您不知道套件的完整名稱，您可能需要執行數次「Add-appxpackage-name \ \* YourBestGuess \ \*」才能進行尋找。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="5f9bd-113">當您的名稱為「$package 1 = Get-AppxPackage 名稱實際 PackageName "</span><span class="sxs-lookup"><span data-stu-id="5f9bd-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="5f9bd-114">例如，執行下列 Microsoft Edge 會傳回一個以上的結果，但在該清單中，您可以找出您所需的完整名稱是 MicrosoftEdge。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="5f9bd-115">在 HoloLens 上應用程式的套件系列名稱</span><span class="sxs-lookup"><span data-stu-id="5f9bd-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="5f9bd-116">在上述連結的指南中，您可以手動編輯 newPolicy.xml，以及新增僅在 HoloLens 上使用其套件系列名稱安裝之應用程式的規則。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="5f9bd-117">有時候，您可能會使用的 app 不在桌上型電腦上，您想要新增至原則。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="5f9bd-118">以下是適用于 HoloLens 2 裝置的常用和 In-Box 應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="5f9bd-119">應用程式名稱</span><span class="sxs-lookup"><span data-stu-id="5f9bd-119">App Name</span></span>                   | <span data-ttu-id="5f9bd-120">套件系列名稱</span><span class="sxs-lookup"><span data-stu-id="5f9bd-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="5f9bd-121">3D 檢視器</span><span class="sxs-lookup"><span data-stu-id="5f9bd-121">3D Viewer</span></span>                  | <span data-ttu-id="5f9bd-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5f9bd-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="5f9bd-123">應用程式安裝程式</span><span class="sxs-lookup"><span data-stu-id="5f9bd-123">App Installer</span></span>              | <span data-ttu-id="5f9bd-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</span><span class="sxs-lookup"><span data-stu-id="5f9bd-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</span></span></sup>         |
| <span data-ttu-id="5f9bd-125">行事曆</span><span class="sxs-lookup"><span data-stu-id="5f9bd-125">Calendar</span></span>                   | <span data-ttu-id="5f9bd-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5f9bd-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="5f9bd-127">相機</span><span class="sxs-lookup"><span data-stu-id="5f9bd-127">Camera</span></span>                     | <span data-ttu-id="5f9bd-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="5f9bd-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="5f9bd-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="5f9bd-129">Cortana</span></span>                    | <span data-ttu-id="5f9bd-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5f9bd-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="5f9bd-131">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="5f9bd-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="5f9bd-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5f9bd-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="5f9bd-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="5f9bd-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="5f9bd-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5f9bd-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="5f9bd-135">意見反應中樞</span><span class="sxs-lookup"><span data-stu-id="5f9bd-135">Feedback Hub</span></span>               | <span data-ttu-id="5f9bd-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5f9bd-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="5f9bd-137">檔案總管</span><span class="sxs-lookup"><span data-stu-id="5f9bd-137">File Explorer</span></span>              | <span data-ttu-id="5f9bd-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="5f9bd-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="5f9bd-139">Mail</span><span class="sxs-lookup"><span data-stu-id="5f9bd-139">Mail</span></span>                       | <span data-ttu-id="5f9bd-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5f9bd-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="5f9bd-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="5f9bd-141">Microsoft Store</span></span>            | <span data-ttu-id="5f9bd-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5f9bd-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="5f9bd-143">電影與電視</span><span class="sxs-lookup"><span data-stu-id="5f9bd-143">Movies & TV</span></span>                | <span data-ttu-id="5f9bd-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5f9bd-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="5f9bd-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="5f9bd-145">OneDrive</span></span>                   | <span data-ttu-id="5f9bd-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5f9bd-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="5f9bd-147">相片</span><span class="sxs-lookup"><span data-stu-id="5f9bd-147">Photos</span></span>                     | <span data-ttu-id="5f9bd-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5f9bd-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="5f9bd-149">設定</span><span class="sxs-lookup"><span data-stu-id="5f9bd-149">Settings</span></span>                   | <span data-ttu-id="5f9bd-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="5f9bd-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="5f9bd-151">提示</span><span class="sxs-lookup"><span data-stu-id="5f9bd-151">Tips</span></span>                       | <span data-ttu-id="5f9bd-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="5f9bd-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="5f9bd-153">1封鎖 App 安裝程式只會封鎖 App 安裝程式應用程式，而不會封鎖從其他來源（例如 Microsoft Store 或您的 MDM 解決方案）所安裝的應用程式。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <span data-ttu-id="5f9bd-154">如何尋找套件系列名稱</span><span class="sxs-lookup"><span data-stu-id="5f9bd-154">How to find a Package Family Name</span></span>

<span data-ttu-id="5f9bd-155">如果應用程式不在此清單中，則使用者可以使用裝置入口網站，連線到已安裝想要封鎖之 app 的 HoloLens 2，以判斷 PackageRelativeID，並從該處取得 PackageFamilyName。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="5f9bd-156">在您的 HoloLens 2 裝置上安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="5f9bd-157">開啟 [設定]-> 更新 & 安全性-> 開發人員，然後啟用 [ **開發人員模式]** 和 [ **裝置入口網站**]。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="5f9bd-158">更多詳細資訊指示請參閱 [在這裡設定及使用 device portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-158">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="5f9bd-159">連接裝置入口網站之後，請流覽至 [ **視圖** ]，然後流覽至 [ **app**]。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="5f9bd-160">在 [已安裝的應用程式] 面板中，使用下拉式清單來選取已安裝的應用程式。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="5f9bd-161">找出 PackageRelativeID。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="5f9bd-162">在！之前複製應用程式字元，這些字元將是您的 PackageFamilyName。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


