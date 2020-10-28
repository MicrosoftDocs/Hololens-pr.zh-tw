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
ms.openlocfilehash: dc1deb2b159d3d41b1a1f73c33f1cd44731f8e4d
ms.sourcegitcommit: 72ae5a270f869393872eac160e43076eaa35fe4c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135566"
---
# <span data-ttu-id="3c178-103">Windows Defender 應用程式控制 (WDAC)</span><span class="sxs-lookup"><span data-stu-id="3c178-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="3c178-104">WDAC 可讓 IT 系統管理員設定其裝置，以封鎖裝置上的應用程式啟動。</span><span class="sxs-lookup"><span data-stu-id="3c178-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="3c178-105">這與裝置限制的方法不同（例如 Kiosk 模式），使用者會在其中提供隱藏裝置上 app 的 UI，但仍可啟動這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="3c178-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="3c178-106">在已實現 WDAC 的情況下，應用程式仍會顯示在 [所有應用程式] 清單中，但 WDAC 會停止由裝置使用者啟動這些 app 和進程。</span><span class="sxs-lookup"><span data-stu-id="3c178-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

> [!NOTE]
> <span data-ttu-id="3c178-107">當使用者嘗試啟動由 WDAC 封鎖的應用程式時，他們將不會收到無法啟動該應用程式的通知。</span><span class="sxs-lookup"><span data-stu-id="3c178-107">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="3c178-108">以下是使用者瞭解如何在使用 [Microsoft Intune 的 HoloLens 2 裝置上使用 WDAC 和 Windows PowerShell 來允許或封鎖 app](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)的指南。</span><span class="sxs-lookup"><span data-stu-id="3c178-108">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="3c178-109">當使用者使用第一個範例搜尋安裝在 Windows 10 電腦上的應用程式時，可能需要進行幾個嘗試來縮小結果範圍。</span><span class="sxs-lookup"><span data-stu-id="3c178-109">When users search for apps installed on their Windows 10 PC using the first example step they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="3c178-110">如果您不知道套件的完整名稱，您可能需要執行數次「Add-appxpackage-name \ \* YourBestGuess \ \*」才能進行尋找。</span><span class="sxs-lookup"><span data-stu-id="3c178-110">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="3c178-111">當您的名稱為「$package 1 = Get-AppxPackage 名稱實際 PackageName "</span><span class="sxs-lookup"><span data-stu-id="3c178-111">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="3c178-112">例如，執行下列 for Edge 會傳回多個結果，但在該清單中，您可以找出您所需的完整名稱是 MicrosoftEdge。</span><span class="sxs-lookup"><span data-stu-id="3c178-112">For example running the following for Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span> 

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="3c178-113">在 HoloLens 上應用程式的套件系列名稱</span><span class="sxs-lookup"><span data-stu-id="3c178-113">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="3c178-114">在上述連結的指南中，您可以手動編輯 newPolicy.xml，以及新增只安裝在 HoloLens 及其套件系列名稱的應用程式規則。</span><span class="sxs-lookup"><span data-stu-id="3c178-114">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications which are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="3c178-115">有時候，您可能會使用的 app 不在桌上型電腦上，您想要新增至原則。</span><span class="sxs-lookup"><span data-stu-id="3c178-115">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span> 

<span data-ttu-id="3c178-116">以下是適用于 HoloLens 2 裝置的常用和 In-Box 應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="3c178-116">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="3c178-117">應用程式名稱</span><span class="sxs-lookup"><span data-stu-id="3c178-117">App Name</span></span>                   | <span data-ttu-id="3c178-118">套件系列名稱</span><span class="sxs-lookup"><span data-stu-id="3c178-118">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="3c178-119">3D 檢視器</span><span class="sxs-lookup"><span data-stu-id="3c178-119">3D Viewer</span></span>                  | <span data-ttu-id="3c178-120">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3c178-120">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="3c178-121">應用程式安裝程式</span><span class="sxs-lookup"><span data-stu-id="3c178-121">App Installer</span></span>              | <span data-ttu-id="3c178-122">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</span><span class="sxs-lookup"><span data-stu-id="3c178-122">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</span></span></sup>         |
| <span data-ttu-id="3c178-123">行事曆</span><span class="sxs-lookup"><span data-stu-id="3c178-123">Calendar</span></span>                   | <span data-ttu-id="3c178-124">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3c178-124">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="3c178-125">相機</span><span class="sxs-lookup"><span data-stu-id="3c178-125">Camera</span></span>                     | <span data-ttu-id="3c178-126">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="3c178-126">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="3c178-127">Cortana</span><span class="sxs-lookup"><span data-stu-id="3c178-127">Cortana</span></span>                    | <span data-ttu-id="3c178-128">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3c178-128">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="3c178-129">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="3c178-129">Dynamics 365 Guides</span></span>        | <span data-ttu-id="3c178-130">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3c178-130">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="3c178-131">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="3c178-131">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="3c178-132">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3c178-132">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="3c178-133">意見反應中樞</span><span class="sxs-lookup"><span data-stu-id="3c178-133">Feedback Hub</span></span>               | <span data-ttu-id="3c178-134">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3c178-134">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="3c178-135">檔案總管</span><span class="sxs-lookup"><span data-stu-id="3c178-135">File Explorer</span></span>              | <span data-ttu-id="3c178-136">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="3c178-136">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="3c178-137">Mail</span><span class="sxs-lookup"><span data-stu-id="3c178-137">Mail</span></span>                       | <span data-ttu-id="3c178-138">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3c178-138">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="3c178-139">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="3c178-139">Microsoft Store</span></span>            | <span data-ttu-id="3c178-140">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3c178-140">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="3c178-141">電影與電視</span><span class="sxs-lookup"><span data-stu-id="3c178-141">Movies & TV</span></span>                | <span data-ttu-id="3c178-142">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3c178-142">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="3c178-143">OneDrive</span><span class="sxs-lookup"><span data-stu-id="3c178-143">OneDrive</span></span>                   | <span data-ttu-id="3c178-144">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3c178-144">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="3c178-145">相片</span><span class="sxs-lookup"><span data-stu-id="3c178-145">Photos</span></span>                     | <span data-ttu-id="3c178-146">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3c178-146">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="3c178-147">設定</span><span class="sxs-lookup"><span data-stu-id="3c178-147">Settings</span></span>                   | <span data-ttu-id="3c178-148">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="3c178-148">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="3c178-149">提示</span><span class="sxs-lookup"><span data-stu-id="3c178-149">Tips</span></span>                       | <span data-ttu-id="3c178-150">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3c178-150">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="3c178-151">1封鎖 App 安裝程式只會封鎖 App 安裝程式應用程式，而不會封鎖從其他來源（例如 Microsoft Store 或您的 MDM 解決方案）所安裝的應用程式。</span><span class="sxs-lookup"><span data-stu-id="3c178-151">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <span data-ttu-id="3c178-152">如何尋找套件系列名稱</span><span class="sxs-lookup"><span data-stu-id="3c178-152">How to find a Package Family Name</span></span>

<span data-ttu-id="3c178-153">如果應用程式不在此清單中，則使用者可以使用 Device Portal，連線至已安裝想要封鎖之 app 的 HoloLens 2，以判斷 PackageRelativeID，並從該處取得 PackageFamilyName。</span><span class="sxs-lookup"><span data-stu-id="3c178-153">If an app is not on this list then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="3c178-154">在您的 HoloLens 2 裝置上安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="3c178-154">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="3c178-155">開啟 [設定]-> 更新 & Securtiy-> 供開發人員使用，並啟用 [ **開發人員模式]** 和 [ **裝置入口網站**]。</span><span class="sxs-lookup"><span data-stu-id="3c178-155">Open Settings -> Updates & Securtiy -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="3c178-156">更多詳細資訊指示請參閱 [在這裡設定及使用 device portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="3c178-156">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="3c178-157">連接裝置入口網站之後，請流覽至 [ **視圖** ]，然後流覽至 [ **app**]。</span><span class="sxs-lookup"><span data-stu-id="3c178-157">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="3c178-158">在 [已安裝的應用程式] 面板中，使用下拉式清單來選取已安裝的應用程式。</span><span class="sxs-lookup"><span data-stu-id="3c178-158">Within the Installed Apps panel use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="3c178-159">找出 PackageRelativeID。</span><span class="sxs-lookup"><span data-stu-id="3c178-159">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="3c178-160">在！之前複製應用程式字元，這將是您的 PackageFamilyName。</span><span class="sxs-lookup"><span data-stu-id="3c178-160">Copy app characters before the !, this will be your PackageFamilyName.</span></span>

## <span data-ttu-id="3c178-161">樣本封鎖 App 安裝程式</span><span class="sxs-lookup"><span data-stu-id="3c178-161">Sample - Blocking App Installer</span></span>

<span data-ttu-id="3c178-162">舉例來說，您可能會想要封鎖 [App 安裝](app-deploy-app-installer.md) 程式 App。</span><span class="sxs-lookup"><span data-stu-id="3c178-162">As an example you may wish to block the [App Installer](app-deploy-app-installer.md) app.</span></span> <span data-ttu-id="3c178-163">我們已在這個範例中加入了一些範例程式碼。</span><span class="sxs-lookup"><span data-stu-id="3c178-163">We have included some sample code for this example.</span></span> <span data-ttu-id="3c178-164">請在 [這個範例下載這些程式碼範例](https://aka.ms/HoloLensDocs-Sample-WDAC-App-Installer)。</span><span class="sxs-lookup"><span data-stu-id="3c178-164">Please download these [code samples for this example](https://aka.ms/HoloLensDocs-Sample-WDAC-App-Installer).</span></span> <span data-ttu-id="3c178-165">在 zip 檔案中，您會看到：</span><span class="sxs-lookup"><span data-stu-id="3c178-165">In the zip file you'll find:</span></span>

| <span data-ttu-id="3c178-166">檔案</span><span class="sxs-lookup"><span data-stu-id="3c178-166">File</span></span> | <span data-ttu-id="3c178-167">用法</span><span class="sxs-lookup"><span data-stu-id="3c178-167">Use</span></span> |
|-|-|
| <span data-ttu-id="3c178-168">compiledPolicy</span><span class="sxs-lookup"><span data-stu-id="3c178-168">compiledPolicy.bin</span></span> | [<span data-ttu-id="3c178-169">在步驟9中建立，在最後步驟10中使用。</span><span class="sxs-lookup"><span data-stu-id="3c178-169">Created in Step 9, used in final Step 10.</span></span>](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) |
| <span data-ttu-id="3c178-170">mergedPolicy.xml</span><span class="sxs-lookup"><span data-stu-id="3c178-170">mergedPolicy.xml</span></span> | [<span data-ttu-id="3c178-171">在步驟6中建立。</span><span class="sxs-lookup"><span data-stu-id="3c178-171">Created in Step 6.</span></span>](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) |
| <span data-ttu-id="3c178-172">WDAC_Set syncml</span><span class="sxs-lookup"><span data-stu-id="3c178-172">WDAC_Set.syncml</span></span> | <span data-ttu-id="3c178-173">在 WDAC 中未使用，但可用於 [ENTERPRISEMODERNAPPMANAGEMENT CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp)</span><span class="sxs-lookup"><span data-stu-id="3c178-173">Not used in WDAC but can be used for for [EnterpriseModernAppManagement CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp)</span></span> |

<span data-ttu-id="3c178-174">如果您想要立即封鎖 app，在此案例中，請使用 compiledPolicy 檔案，然後跳至上述連結中的步驟10。</span><span class="sxs-lookup"><span data-stu-id="3c178-174">If you would like to try immediately blocking an app, in this case the App Installer app, then use the compiledPolicy.bin file and skip to step 10 in the link above.</span></span> <span data-ttu-id="3c178-175">這可讓您測試自訂原則，並確保群組指派與原則配置正確無誤。</span><span class="sxs-lookup"><span data-stu-id="3c178-175">This will allow you to test out the custom policy and ensure the group assignments and policy configuration is correct.</span></span> 

<span data-ttu-id="3c178-176">如果您想要將針對封鎖 App 安裝程式的 WDAC 原則與上述清單中的其他 app 結合，或任何其他應用程式，您可以使用 mergedPolicy.xml 檔案並繼續合併新的原則。</span><span class="sxs-lookup"><span data-stu-id="3c178-176">If you would like to combine the WDAC policy for blocking App Installer with other apps from the list above, or any other app, then you may use the mergedPolicy.xml file and continue to merge new policies.</span></span> <span data-ttu-id="3c178-177">如上述的 WDAC 原則所述，不需要這麼做。</span><span class="sxs-lookup"><span data-stu-id="3c178-177">As stated above WDAC policies are additive so this is not required.</span></span> 

<span data-ttu-id="3c178-178">由於 App 安裝程式 app 是透過嘗試開啟檔案來啟動，因此會出現提示。</span><span class="sxs-lookup"><span data-stu-id="3c178-178">Since the App Installer app is launched via trying to open a file will be presented with a prompt.</span></span> <span data-ttu-id="3c178-179">視 WDAC 封鎖的上述 App 所述，不會顯示已封鎖的提示，但由於使用者嘗試在其裝置上開啟檔案，因此會出現開啟檔案時的錯誤。</span><span class="sxs-lookup"><span data-stu-id="3c178-179">As stated above Apps blocked by WDAC do not present a prompt they are blocked, however since the user is attempting to open a file on their device they are presented with an error for opening the file.</span></span> 

![應用程式安裝已從 WDAC 封鎖](images\wdac-app-installer-no-launch.jpg)

<span data-ttu-id="3c178-181">如果您不想使用 WDAC，您可以選擇使用 [ENTERPRISEMODERNAPPMANAGEMENT CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp) 來移除 App 安裝程式 UX （畢竟是 app）。</span><span class="sxs-lookup"><span data-stu-id="3c178-181">If you do not wish to use WDAC, you may as an alternative use [EnterpriseModernAppManagement CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp) to remove the App Installer UX, which is an app after all.</span></span> <span data-ttu-id="3c178-182">如此一來，應用程式安裝程式 app 就會從裝置中卸載。</span><span class="sxs-lookup"><span data-stu-id="3c178-182">The result of this is that the App Installer app will be uninstalled from the device.</span></span> <span data-ttu-id="3c178-183">.appx、msix、msixbundle 及其他副檔名，以及 web 到 app 啟動的通訊協定將不會再由應用程式安裝程式來處理。</span><span class="sxs-lookup"><span data-stu-id="3c178-183">.appx, .msix, .msixbundle, and other file extensions as well as protocol for web-to-app launch will no longer be handled by the App Installer app.</span></span> <span data-ttu-id="3c178-184">使用者會收到在市集中搜尋檔案副檔名/通訊協定的程式提示，因為沒有列出該應用程式。</span><span class="sxs-lookup"><span data-stu-id="3c178-184">The user will get a prompt to search for a handler for the file extension/protocol in the store and they will not find the app because it’s not listed.</span></span>