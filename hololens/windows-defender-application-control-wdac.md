---
title: Windows Defender 應用程式控制-WDAC
description: 瞭解 WDAC 是什麼，以及如何使用它來管理 HoloLens 裝置。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d1147b202d3b575fa1f2dd20f620005c786ea9fc
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016766"
---
# <span data-ttu-id="1ed43-103">Windows Defender 應用程式控制-WDAC</span><span class="sxs-lookup"><span data-stu-id="1ed43-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="1ed43-104">WDAC 可讓 IT 系統管理員設定其裝置，以封鎖裝置上的應用程式啟動。</span><span class="sxs-lookup"><span data-stu-id="1ed43-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="1ed43-105">這與裝置限制的方法不同（例如 Kiosk 模式），使用者會在其中提供隱藏裝置上 app 的 UI，但仍可啟動這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="1ed43-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="1ed43-106">在已實現 WDAC 的情況下，應用程式仍會顯示在 [所有應用程式] 清單中，但 WDAC 會停止由裝置使用者啟動這些 app 和進程。</span><span class="sxs-lookup"><span data-stu-id="1ed43-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

> [!NOTE]
> <span data-ttu-id="1ed43-107">當使用者嘗試啟動由 WDAC 封鎖的應用程式時，他們將不會收到無法啟動該應用程式的通知。</span><span class="sxs-lookup"><span data-stu-id="1ed43-107">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="1ed43-108">以下是使用者瞭解如何在使用 [Microsoft Intune 的 HoloLens 2 裝置上使用 WDAC 和 Windows PowerShell 來允許或封鎖 app](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)的指南。</span><span class="sxs-lookup"><span data-stu-id="1ed43-108">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="1ed43-109">當使用者使用第一個範例搜尋安裝在 Windows 10 電腦上的應用程式時，可能需要進行幾個嘗試來縮小結果範圍。</span><span class="sxs-lookup"><span data-stu-id="1ed43-109">When users search for apps installed on their Windows 10 PC using the first example step they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="1ed43-110">如果您不知道套件的完整名稱，您可能需要執行數次「Add-appxpackage-name \ \* YourBestGuess \ \*」才能進行尋找。</span><span class="sxs-lookup"><span data-stu-id="1ed43-110">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="1ed43-111">接著，當您的名稱為「$package 1 = Add-appxpackage-name PackageName '</span><span class="sxs-lookup"><span data-stu-id="1ed43-111">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="1ed43-112">例如，執行下列 for Edge 會傳回多個結果，但在該清單中，您可以找出您所需的完整名稱是 MicrosoftEdge。</span><span class="sxs-lookup"><span data-stu-id="1ed43-112">For example running the following for Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span> 

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="1ed43-113">在 HoloLens 上應用程式的套件系列名稱</span><span class="sxs-lookup"><span data-stu-id="1ed43-113">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="1ed43-114">在上述連結的指南中，您可以手動編輯 newPolicy.xml，以及新增只安裝在 HoloLens 及其套件系列名稱的應用程式規則。</span><span class="sxs-lookup"><span data-stu-id="1ed43-114">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications which are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="1ed43-115">有時候，您可能會使用的 app 不在桌上型電腦上，您想要新增至原則。</span><span class="sxs-lookup"><span data-stu-id="1ed43-115">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span> 

<span data-ttu-id="1ed43-116">以下是適用于 HoloLens 2 裝置的 [常用] 與 [主機殼中] app 清單。</span><span class="sxs-lookup"><span data-stu-id="1ed43-116">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="1ed43-117">應用程式名稱</span><span class="sxs-lookup"><span data-stu-id="1ed43-117">App Name</span></span>                   | <span data-ttu-id="1ed43-118">套件系列名稱</span><span class="sxs-lookup"><span data-stu-id="1ed43-118">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="1ed43-119">3D 檢視器</span><span class="sxs-lookup"><span data-stu-id="1ed43-119">3D Viewer</span></span>                  | <span data-ttu-id="1ed43-120">Microsoft. Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ed43-120">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="1ed43-121">行事曆</span><span class="sxs-lookup"><span data-stu-id="1ed43-121">Calendar</span></span>                   | <span data-ttu-id="1ed43-122">microsoft. windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ed43-122">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="1ed43-123">相機</span><span class="sxs-lookup"><span data-stu-id="1ed43-123">Camera</span></span>                     | <span data-ttu-id="1ed43-124">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="1ed43-124">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="1ed43-125">Cortana</span><span class="sxs-lookup"><span data-stu-id="1ed43-125">Cortana</span></span>                    | <span data-ttu-id="1ed43-126">Microsoft. 549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ed43-126">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="1ed43-127">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="1ed43-127">Dynamics 365 Guides</span></span>        | <span data-ttu-id="1ed43-128">Dynamics365 Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ed43-128">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="1ed43-129">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="1ed43-129">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="1ed43-130">Microsoft. MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ed43-130">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="1ed43-131">意見反應中樞</span><span class="sxs-lookup"><span data-stu-id="1ed43-131">Feedback Hub</span></span>               | <span data-ttu-id="1ed43-132">Microsoft. WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ed43-132">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="1ed43-133">檔案總管</span><span class="sxs-lookup"><span data-stu-id="1ed43-133">File Explorer</span></span>              | <span data-ttu-id="1ed43-134">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="1ed43-134">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="1ed43-135">Mail</span><span class="sxs-lookup"><span data-stu-id="1ed43-135">Mail</span></span>                       | <span data-ttu-id="1ed43-136">microsoft. windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ed43-136">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="1ed43-137">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="1ed43-137">Microsoft Store</span></span>            | <span data-ttu-id="1ed43-138">Microsoft. WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ed43-138">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="1ed43-139">電影與電視</span><span class="sxs-lookup"><span data-stu-id="1ed43-139">Movies & TV</span></span>                | <span data-ttu-id="1ed43-140">Microsoft. ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ed43-140">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="1ed43-141">OneDrive</span><span class="sxs-lookup"><span data-stu-id="1ed43-141">OneDrive</span></span>                   | <span data-ttu-id="1ed43-142">microsoft. microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ed43-142">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="1ed43-143">相片</span><span class="sxs-lookup"><span data-stu-id="1ed43-143">Photos</span></span>                     | <span data-ttu-id="1ed43-144">Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ed43-144">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="1ed43-145">設定</span><span class="sxs-lookup"><span data-stu-id="1ed43-145">Settings</span></span>                   | <span data-ttu-id="1ed43-146">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="1ed43-146">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="1ed43-147">提示</span><span class="sxs-lookup"><span data-stu-id="1ed43-147">Tips</span></span>                       | <span data-ttu-id="1ed43-148">Microsoft. HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ed43-148">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

<span data-ttu-id="1ed43-149">如果應用程式不在此清單中，則使用者可以使用 Device Portal，連線至已安裝想要封鎖之 app 的 HoloLens 2，以判斷 PackageRelativeID，並從該處取得 PackageFamilyName。</span><span class="sxs-lookup"><span data-stu-id="1ed43-149">If an app is not on this list then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="1ed43-150">在您的 HoloLens 2 裝置上安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="1ed43-150">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="1ed43-151">開啟 [設定]-> 更新 & Securtiy-> 供開發人員使用，並啟用 [ **開發人員模式]** 和 [ **裝置入口網站**]。</span><span class="sxs-lookup"><span data-stu-id="1ed43-151">Open Settings -> Updates & Securtiy -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="1ed43-152">更多詳細資訊指示請參閱 [在這裡設定及使用 device portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="1ed43-152">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="1ed43-153">連接裝置入口網站之後，請流覽至 [ **視圖** ]，然後流覽至 [ **app**]。</span><span class="sxs-lookup"><span data-stu-id="1ed43-153">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="1ed43-154">在 [已安裝的應用程式] 面板中，使用下拉式清單來選取已安裝的應用程式。</span><span class="sxs-lookup"><span data-stu-id="1ed43-154">Within the Installed Apps panel use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="1ed43-155">找出 PackageRelativeID。</span><span class="sxs-lookup"><span data-stu-id="1ed43-155">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="1ed43-156">在！之前複製應用程式字元，這將是您的 PackageFamilyName。</span><span class="sxs-lookup"><span data-stu-id="1ed43-156">Copy app characters before the !, this will be your PackageFamilyName.</span></span>

