---
title: 如何透過 HoloLens 2 App 安裝程式載入並安裝應用程式
description: 透過 UI 進行投影片載入和安裝應用程式
keywords: app 管理、app、hololens、app 安裝程式
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 10/26/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 415733bb2809b7ae2808edc097423f8928910c57
ms.sourcegitcommit: c4fd9a87bb7c728c73418f95a1b15dd93b0af7c6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "11150914"
---
# <span data-ttu-id="d8323-104">透過 App 安裝程式在 HoloLens 2 上安裝應用程式</span><span class="sxs-lookup"><span data-stu-id="d8323-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8323-105">此功能目前僅適用于 Windows 測試人員組建 19041.1377 + 中的 avalible。</span><span class="sxs-lookup"><span data-stu-id="d8323-105">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="d8323-106">[深入瞭解如何在 Windows 測試人員組建中註冊](hololens-insider.md)。</span><span class="sxs-lookup"><span data-stu-id="d8323-106">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

<span data-ttu-id="d8323-107">在我們的 Windows 測試人員發行版本中，我們 **新增了 (App 安裝程式) 的新功能，可讓您在 HoloLens 2 裝置上更順暢地安裝應用程式** 。</span><span class="sxs-lookup"><span data-stu-id="d8323-107">In our Windows Insider release, we are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="d8323-108">預設會將 **未受管理的裝置的功能預設為開啟**。</span><span class="sxs-lookup"><span data-stu-id="d8323-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="d8323-109">為了避免中斷企業，目前 **不會對受管理的裝置提供** app 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="d8323-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="d8323-110">如果下列 **任一** 條件成立，裝置就會被視為「受管理」：</span><span class="sxs-lookup"><span data-stu-id="d8323-110">A device is considered “managed” if **any** of the following are true:</span></span>
- <span data-ttu-id="d8323-111">已[註冊](hololens-enroll-mdm.md)MDM</span><span class="sxs-lookup"><span data-stu-id="d8323-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="d8323-112">使用[預配套件](hololens-provisioning.md)進行設定</span><span class="sxs-lookup"><span data-stu-id="d8323-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="d8323-113">使用者身分 [識別](hololens-identity.md) 為 AAD</span><span class="sxs-lookup"><span data-stu-id="d8323-113">User [Identity](hololens-identity.md) is AAD</span></span>

<span data-ttu-id="d8323-114">您現在可以安裝應用程式，而不需要啟用開發人員模式或使用 Device Portal。</span><span class="sxs-lookup"><span data-stu-id="d8323-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="d8323-115">只要透過 USB 或邊緣) 將 (下載到您的裝置，然後在檔案資源管理器中流覽至 Appx 套件，就會提示您啟動安裝。</span><span class="sxs-lookup"><span data-stu-id="d8323-115">Simply download (over USB or through Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="d8323-116">或者， [從網頁啟動安裝](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。</span><span class="sxs-lookup"><span data-stu-id="d8323-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="d8323-117">就像從 Microsoft Store 或側載使用 MDM 的 LOB 應用程式部署功能所安裝的應用程式，應用程式必須使用 [簽署工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 進行數位簽署，而且在部署 App 之前，必須由 HoloLens 裝置 [信任用來簽署的憑證](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) 。</span><span class="sxs-lookup"><span data-stu-id="d8323-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>   

## <span data-ttu-id="d8323-118">需求</span><span class="sxs-lookup"><span data-stu-id="d8323-118">Requirements</span></span>

### <span data-ttu-id="d8323-119">針對您的裝置：</span><span class="sxs-lookup"><span data-stu-id="d8323-119">For your devices:</span></span> 
> [!NOTE]
> <span data-ttu-id="d8323-120">此功能目前僅適用于 Windows 測試人員組建 19041.1377 + 中的 avalible。</span><span class="sxs-lookup"><span data-stu-id="d8323-120">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="d8323-121">[深入瞭解如何在 Windows 測試人員組建中註冊](hololens-insider.md)。</span><span class="sxs-lookup"><span data-stu-id="d8323-121">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

### <span data-ttu-id="d8323-122">針對您的應用程式：</span><span class="sxs-lookup"><span data-stu-id="d8323-122">For your apps:</span></span> 
<span data-ttu-id="d8323-123">您 app 的解決方案設定必須是 [ **主版** ] 或 [ **發行** ]，因為 app 安裝程式會使用市集中的相依性。</span><span class="sxs-lookup"><span data-stu-id="d8323-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="d8323-124">查看更多關於 [建立應用程式套件](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)的資訊。</span><span class="sxs-lookup"><span data-stu-id="d8323-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="d8323-125">透過此方法所安裝的應用程式必須經過數位簽章。</span><span class="sxs-lookup"><span data-stu-id="d8323-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="d8323-126">您必須使用憑證來簽署 app。</span><span class="sxs-lookup"><span data-stu-id="d8323-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="d8323-127">您可以從 [MS 信任的 CA 清單](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)中取得證書，在這種情況下，您不需要採取任何其他動作。</span><span class="sxs-lookup"><span data-stu-id="d8323-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any additional action.</span></span> <span data-ttu-id="d8323-128">或者，您也可以簽署您自己的憑證，但必須將憑證推送到裝置上。</span><span class="sxs-lookup"><span data-stu-id="d8323-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span> 
- <span data-ttu-id="d8323-129">如何[使用 [簽署工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)] 簽署 app。</span><span class="sxs-lookup"><span data-stu-id="d8323-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="d8323-130">憑證選項：</span><span class="sxs-lookup"><span data-stu-id="d8323-130">Certificate options:</span></span>** 
- [<span data-ttu-id="d8323-131">MS 受信任的 CA 清單</span><span class="sxs-lookup"><span data-stu-id="d8323-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="d8323-132">挑選證書部署方法。</span><span class="sxs-lookup"><span data-stu-id="d8323-132">Pick a certificate deployment method.</span></span>** 
- <span data-ttu-id="d8323-133">您可以將[預配套件](hololens-provisioning.md)套用到本機裝置。</span><span class="sxs-lookup"><span data-stu-id="d8323-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="d8323-134">MDM 可用來 [將憑證與裝置](https://docs.microsoft.com/mem/intune/protect/certificates-configure)設定搭配使用。</span><span class="sxs-lookup"><span data-stu-id="d8323-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="d8323-135">使用 [裝置 [憑證管理員](hololens-insider.md#certificate-manager)]。</span><span class="sxs-lookup"><span data-stu-id="d8323-135">Use the on device [Certificate Manager](hololens-insider.md#certificate-manager).</span></span> 

## <span data-ttu-id="d8323-136">安裝方法</span><span class="sxs-lookup"><span data-stu-id="d8323-136">Installation method</span></span>

1.  <span data-ttu-id="d8323-137">確定您的裝置未被視為已管理。</span><span class="sxs-lookup"><span data-stu-id="d8323-137">Ensure that your device is not considered managed.</span></span>
1.  <span data-ttu-id="d8323-138">確定您的 HoloLens 2 裝置已通電且已登入。</span><span class="sxs-lookup"><span data-stu-id="d8323-138">Ensure that your HoloLens 2 device is powered on and you are signed in.</span></span>
1.  <span data-ttu-id="d8323-139">在您的電腦上流覽至您的自訂應用程式，並將 yourapp 複製到 yourdevicename\Internal Storage\Downloads。</span><span class="sxs-lookup"><span data-stu-id="d8323-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span> 
    <span data-ttu-id="d8323-140">完成檔案複製之後，您可能會中斷裝置連線，並在稍後完成安裝。</span><span class="sxs-lookup"><span data-stu-id="d8323-140">After your finish copying your file you may disconnect your device and finish the install later.</span></span>
1.  <span data-ttu-id="d8323-141">從您的 HoloLens 2 裝置開啟 [ **開始] 功能表**，選取 [ **所有應用程式** ]，然後啟動檔案 **資源管理器** 應用程式。</span><span class="sxs-lookup"><span data-stu-id="d8323-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1.  <span data-ttu-id="d8323-142">流覽至 [下載] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="d8323-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="d8323-143">您可能需要在應用程式的左面板上，選取 [ **此裝置** ]，然後流覽至 [下載]。</span><span class="sxs-lookup"><span data-stu-id="d8323-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="d8323-144">選取 yourapp 檔案。</span><span class="sxs-lookup"><span data-stu-id="d8323-144">Select the yourapp.appxbundle file.</span></span> 
1.  <span data-ttu-id="d8323-145">App 安裝程式將會啟動。</span><span class="sxs-lookup"><span data-stu-id="d8323-145">The App Installer will launch.</span></span> <span data-ttu-id="d8323-146">選取 [ **安裝** ] 按鈕來安裝您的 app。</span><span class="sxs-lookup"><span data-stu-id="d8323-146">Select the **Install** button to install your app.</span></span> 

<span data-ttu-id="d8323-147">已安裝的應用程式會在安裝完成後自動啟動。</span><span class="sxs-lookup"><span data-stu-id="d8323-147">The installed app will automatically launch upon the completion of installing.</span></span> 

![透過 App 安裝程式安裝 MRTK 範例](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="d8323-149">疑難排解安裝</span><span class="sxs-lookup"><span data-stu-id="d8323-149">Troubleshooting Installs</span></span>
<span data-ttu-id="d8323-150">如果您的 app 安裝失敗，請檢查下列專案：</span><span class="sxs-lookup"><span data-stu-id="d8323-150">If your app failed to install check the following:</span></span>
-   <span data-ttu-id="d8323-151">您的應用程式是主版本或發行組建。</span><span class="sxs-lookup"><span data-stu-id="d8323-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="d8323-152">您的裝置已更新為可使用此功能的組建。</span><span class="sxs-lookup"><span data-stu-id="d8323-152">Your device is updated to a build on which this feature is available.</span></span> 
-   <span data-ttu-id="d8323-153">您已 [連線至網際網路](hololens-network.md)。</span><span class="sxs-lookup"><span data-stu-id="d8323-153">You are [connected to the internet](hololens-network.md).</span></span>
-   <span data-ttu-id="d8323-154">您 [的 Microsoft Store 端點](hololens-offline.md) 已正確設定。</span><span class="sxs-lookup"><span data-stu-id="d8323-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="d8323-155">Web 安裝程式</span><span class="sxs-lookup"><span data-stu-id="d8323-155">Web Installer</span></span>

<span data-ttu-id="d8323-156">使用者可以直接從 web 伺服器安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="d8323-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="d8323-157">這會將 App 安裝程式與簡單的下載和安裝分發方法結合使用。</span><span class="sxs-lookup"><span data-stu-id="d8323-157">This takes use of the App Installer combined with an easy download and install distribution method.</span></span> 

### <span data-ttu-id="d8323-158">如何設定網路安裝：</span><span class="sxs-lookup"><span data-stu-id="d8323-158">How to set up web install:</span></span>
1.  <span data-ttu-id="d8323-159">確定您的 app 已正確設定為 [安裝]。</span><span class="sxs-lookup"><span data-stu-id="d8323-159">Ensure your app is correctly configured to install.</span></span>
1.  <span data-ttu-id="d8323-160">請依照下列 [步驟在網頁上啟用此操作](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。</span><span class="sxs-lookup"><span data-stu-id="d8323-160">Follow these [steps to enable this on a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span> 

### <span data-ttu-id="d8323-161">使用者體驗：</span><span class="sxs-lookup"><span data-stu-id="d8323-161">End user experience:</span></span>
1. <span data-ttu-id="d8323-162">使用者使用先前選取的方法，接收並將憑證安裝到裝置。</span><span class="sxs-lookup"><span data-stu-id="d8323-162">User receives and installs certificate to the device using a method previously chosen above.</span></span> 
1. <span data-ttu-id="d8323-163">使用者造訪上述步驟所建立的 URL。</span><span class="sxs-lookup"><span data-stu-id="d8323-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="d8323-164">App 現在將會安裝到裝置上。</span><span class="sxs-lookup"><span data-stu-id="d8323-164">The app will now install to the device.</span></span> <span data-ttu-id="d8323-165">若要尋找應用程式，請開啟 [ **開始] 功能表** ，然後選取 [ **所有應用程式** ] 按鈕來尋找您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="d8323-165">To find the app open the **Start menu** and select the **All apps** button to find your app.</span></span> 

-   <span data-ttu-id="d8323-166">如需此安裝方法的疑難排解說明，請參閱 [app 安裝程式問題疑難排解](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)。</span><span class="sxs-lookup"><span data-stu-id="d8323-166">For help troubleshooting this installation method please visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span> 

> [!NOTE]
> <span data-ttu-id="d8323-167">更新程式中不支援 UI。</span><span class="sxs-lookup"><span data-stu-id="d8323-167">UI during the update process is not supported.</span></span> <span data-ttu-id="d8323-168">所以不支援 [此頁面](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 上的 [ShowPrompt] 選項和相關選項。</span><span class="sxs-lookup"><span data-stu-id="d8323-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="d8323-169">範例應用程式</span><span class="sxs-lookup"><span data-stu-id="d8323-169">Sample Apps</span></span>

<span data-ttu-id="d8323-170">如果您想要使用一些範例應用程式試試，請查看一些可用的範例：</span><span class="sxs-lookup"><span data-stu-id="d8323-170">If you'd like to try this out with some sample apps please check out some of our available samples:</span></span>
- [<span data-ttu-id="d8323-171">MRTK 範例中心</span><span class="sxs-lookup"><span data-stu-id="d8323-171">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="d8323-172">表面</span><span class="sxs-lookup"><span data-stu-id="d8323-172">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="d8323-173">可用於測試的 UWP 範例應用程式</span><span class="sxs-lookup"><span data-stu-id="d8323-173">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
