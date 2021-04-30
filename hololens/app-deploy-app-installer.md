---
title: 如何透過 HoloLens 2 應用程式安裝程式側載和安裝應用程式
description: 瞭解如何使用應用程式安裝程式和側載，以及透過 UI 安裝應用程式，來安裝應用程式並對其進行疑難排解。
keywords: 應用程式管理、應用程式、hololens、應用程式安裝程式
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 9e413963dbf34dd071fc9603487590065b967ee7
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308355"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="82b30-104">透過應用程式安裝程式在 HoloLens 2 上安裝應用程式</span><span class="sxs-lookup"><span data-stu-id="82b30-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="82b30-105">這項功能可在 Windows 全像 [20H2 –2020年12月更新](hololens-release-notes.md)中取得。</span><span class="sxs-lookup"><span data-stu-id="82b30-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="82b30-106">確定您的裝置已 [更新](hololens-update-hololens.md) 為使用此功能。</span><span class="sxs-lookup"><span data-stu-id="82b30-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="82b30-107">我們 **新增了 (應用程式安裝程式) 的新功能，可讓您更順暢地** 在 HoloLens 2 裝置上安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="82b30-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="82b30-108">**預設會針對未受管理的裝置開啟** 此功能。</span><span class="sxs-lookup"><span data-stu-id="82b30-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="82b30-109">為了避免對企業造成中斷， **受控裝置** 目前無法使用應用程式安裝程式。</span><span class="sxs-lookup"><span data-stu-id="82b30-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="82b30-110">如果下列 **任一** 條件成立，則會將裝置視為「受控」：</span><span class="sxs-lookup"><span data-stu-id="82b30-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="82b30-111">已[註冊](hololens-enroll-mdm.md)MDM</span><span class="sxs-lookup"><span data-stu-id="82b30-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="82b30-112">已設定布建 [套件](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="82b30-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="82b30-113">使用者身分 [識別](hololens-identity.md) 為 Azure AD</span><span class="sxs-lookup"><span data-stu-id="82b30-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="82b30-114">您現在可以安裝應用程式，而不需要啟用開發人員模式或使用裝置入口網站。</span><span class="sxs-lookup"><span data-stu-id="82b30-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="82b30-115">下載 (over USB 或透過 Microsoft Edge) Appx 套件組合移至您的裝置，並流覽至檔案總管中的 Appx 配套，以提示開始安裝。</span><span class="sxs-lookup"><span data-stu-id="82b30-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="82b30-116">或者， [從網頁起始安裝](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。</span><span class="sxs-lookup"><span data-stu-id="82b30-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="82b30-117">就像您使用 MDM 的 LOB 應用程式部署功能從 Microsoft Store 或側載安裝的應用程式一樣，應用程式必須使用 [簽署工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 進行數位簽署，而 [用來簽署的憑證必須](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) 由 HoloLens 裝置信任，才能部署應用程式。</span><span class="sxs-lookup"><span data-stu-id="82b30-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <a name="requirements"></a><span data-ttu-id="82b30-118">規格需求</span><span class="sxs-lookup"><span data-stu-id="82b30-118">Requirements</span></span>

### <a name="for-your-devices"></a><span data-ttu-id="82b30-119">針對您的裝置：</span><span class="sxs-lookup"><span data-stu-id="82b30-119">For your devices:</span></span>

<span data-ttu-id="82b30-120">這項功能目前適用于 HoloLens 2 裝置的 Windows 全像20H2 組建。</span><span class="sxs-lookup"><span data-stu-id="82b30-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="82b30-121">請確定使用此方法的任何裝置都已 [更新](hololens-update-hololens.md)。</span><span class="sxs-lookup"><span data-stu-id="82b30-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <a name="for-your-apps"></a><span data-ttu-id="82b30-122">針對您的應用程式：</span><span class="sxs-lookup"><span data-stu-id="82b30-122">For your apps:</span></span>

<span data-ttu-id="82b30-123">您應用程式的解決方案設定必須是 **Master** 或 **Release** ，因為應用程式安裝程式會使用存放區的相依性。</span><span class="sxs-lookup"><span data-stu-id="82b30-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="82b30-124">深入瞭解如何 [建立應用程式套件](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)。</span><span class="sxs-lookup"><span data-stu-id="82b30-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="82b30-125">透過此方法安裝的應用程式必須經過數位簽署。</span><span class="sxs-lookup"><span data-stu-id="82b30-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="82b30-126">您必須使用憑證來簽署應用程式。</span><span class="sxs-lookup"><span data-stu-id="82b30-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="82b30-127">您可以從「 [MS 受信任的 CA」清單](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)取得憑證，在這種情況下，您不需要採取任何額外的動作。</span><span class="sxs-lookup"><span data-stu-id="82b30-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="82b30-128">或者，您也可以簽署自己的憑證，但憑證需要推入裝置上。</span><span class="sxs-lookup"><span data-stu-id="82b30-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="82b30-129">如何[使用簽署工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)簽署應用程式。</span><span class="sxs-lookup"><span data-stu-id="82b30-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

<span data-ttu-id="82b30-130">**憑證選項：**</span><span class="sxs-lookup"><span data-stu-id="82b30-130">**Certificate options:**</span></span>

- [<span data-ttu-id="82b30-131">MS 受信任 CA 清單</span><span class="sxs-lookup"><span data-stu-id="82b30-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

<span data-ttu-id="82b30-132">**挑選憑證部署方法。**</span><span class="sxs-lookup"><span data-stu-id="82b30-132">**Pick a certificate deployment method.**</span></span>

- <span data-ttu-id="82b30-133">布建[套件](hololens-provisioning.md)可以套用至本機裝置。</span><span class="sxs-lookup"><span data-stu-id="82b30-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="82b30-134">MDM 可以用來 [將憑證](https://docs.microsoft.com/mem/intune/protect/certificates-configure)套用至裝置設定。</span><span class="sxs-lookup"><span data-stu-id="82b30-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="82b30-135">在裝置 [憑證管理員](certificate-manager.md)上使用。</span><span class="sxs-lookup"><span data-stu-id="82b30-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <a name="installation-method"></a><span data-ttu-id="82b30-136">安裝方法</span><span class="sxs-lookup"><span data-stu-id="82b30-136">Installation method</span></span>

1. <span data-ttu-id="82b30-137">檢查您的裝置是否未被視為受管理。</span><span class="sxs-lookup"><span data-stu-id="82b30-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="82b30-138">檢查您的 HoloLens 2 裝置已開啟電源且已登入。</span><span class="sxs-lookup"><span data-stu-id="82b30-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="82b30-139">在您的電腦上，流覽至您的自訂應用程式，並將 yourapp 複製到 yourdevicename\Internal Storage\Downloads。</span><span class="sxs-lookup"><span data-stu-id="82b30-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="82b30-140">完成檔案複製後，您可能會中斷裝置連線，並于稍後完成安裝。</span><span class="sxs-lookup"><span data-stu-id="82b30-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="82b30-141">從您的 HoloLens 2 裝置開啟 [ **開始] 功能表**，選取 [ **所有應用程式** ]，然後啟動 **檔案總管** 應用程式。</span><span class="sxs-lookup"><span data-stu-id="82b30-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="82b30-142">流覽至 [下載] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="82b30-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="82b30-143">您可能需要在應用程式的左側面板上先選取 **此裝置** ，然後流覽至 [下載]。</span><span class="sxs-lookup"><span data-stu-id="82b30-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="82b30-144">選取 yourapp .appxbundle 檔。</span><span class="sxs-lookup"><span data-stu-id="82b30-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="82b30-145">將會啟動應用程式安裝程式。</span><span class="sxs-lookup"><span data-stu-id="82b30-145">The App Installer will launch.</span></span> <span data-ttu-id="82b30-146">選取 [ **安裝** ] 按鈕以安裝您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="82b30-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="82b30-147">已安裝的應用程式會在安裝完成時自動啟動。</span><span class="sxs-lookup"><span data-stu-id="82b30-147">The installed app will automatically launch upon the completion of installing.</span></span>

![透過應用程式安裝程式安裝 MRTK 範例](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a><span data-ttu-id="82b30-149">安裝疑難排解</span><span class="sxs-lookup"><span data-stu-id="82b30-149">Troubleshooting Installs</span></span>

<span data-ttu-id="82b30-150">如果您的應用程式無法安裝，請檢查下列各項以進行疑難排解：</span><span class="sxs-lookup"><span data-stu-id="82b30-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="82b30-151">您的應用程式可以是主要或發行組建。</span><span class="sxs-lookup"><span data-stu-id="82b30-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="82b30-152">您的裝置已更新為可使用此功能的組建。</span><span class="sxs-lookup"><span data-stu-id="82b30-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="82b30-153">您已 [連線到網際網路](hololens-network.md)。</span><span class="sxs-lookup"><span data-stu-id="82b30-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="82b30-154">已正確設定 [Microsoft Store 的端點](hololens-offline.md) 。</span><span class="sxs-lookup"><span data-stu-id="82b30-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <a name="web-installer"></a><span data-ttu-id="82b30-155">Web 安裝程式</span><span class="sxs-lookup"><span data-stu-id="82b30-155">Web Installer</span></span>

<span data-ttu-id="82b30-156">使用者可以直接從 web 伺服器安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="82b30-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="82b30-157">此流程會使用應用程式安裝程式結合簡單的下載和安裝散發方法。</span><span class="sxs-lookup"><span data-stu-id="82b30-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <a name="how-to-set-up-web-install"></a><span data-ttu-id="82b30-158">如何設定 web 安裝：</span><span class="sxs-lookup"><span data-stu-id="82b30-158">How to set up web install:</span></span>

1. <span data-ttu-id="82b30-159">確定已正確設定您的應用程式以進行安裝。</span><span class="sxs-lookup"><span data-stu-id="82b30-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="82b30-160">請遵循下列 [步驟，以從網頁啟用安裝](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。</span><span class="sxs-lookup"><span data-stu-id="82b30-160">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="82b30-161">終端使用者體驗：</span><span class="sxs-lookup"><span data-stu-id="82b30-161">End user experience:</span></span>

1. <span data-ttu-id="82b30-162">使用者會使用先前選擇的方法，來接收並安裝憑證至裝置。</span><span class="sxs-lookup"><span data-stu-id="82b30-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="82b30-163">使用者造訪上述步驟所建立的 URL。</span><span class="sxs-lookup"><span data-stu-id="82b30-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="82b30-164">應用程式現在會安裝到裝置。</span><span class="sxs-lookup"><span data-stu-id="82b30-164">The app will now install to the device.</span></span> <span data-ttu-id="82b30-165">若要尋找應用程式，請開啟 **[開始] 功能表** ，然後選取 [ **所有應用程式** ] 按鈕以尋找您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="82b30-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="82b30-166">如需針對應用程式安裝程式安裝方法進行疑難排解的詳細說明，請造訪 [應用程式安裝程式問題疑難排解](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)。</span><span class="sxs-lookup"><span data-stu-id="82b30-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="82b30-167">不支援更新程式期間的 UI。</span><span class="sxs-lookup"><span data-stu-id="82b30-167">UI during the update process is not supported.</span></span> <span data-ttu-id="82b30-168">因此不支援 [這個頁面](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 上的 ShowPrompt 選項和相關的選項。</span><span class="sxs-lookup"><span data-stu-id="82b30-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <a name="sample-apps"></a><span data-ttu-id="82b30-169">範例應用程式</span><span class="sxs-lookup"><span data-stu-id="82b30-169">Sample Apps</span></span>

<span data-ttu-id="82b30-170">若要嘗試使用一些範例應用程式來應用程式安裝程式，請查看一些可用的範例：</span><span class="sxs-lookup"><span data-stu-id="82b30-170">To try the App Installer with some sample apps check out some of our available samples:</span></span>

- [<span data-ttu-id="82b30-171">MRTK 範例中樞</span><span class="sxs-lookup"><span data-stu-id="82b30-171">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="82b30-172">表面</span><span class="sxs-lookup"><span data-stu-id="82b30-172">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="82b30-173">可用於測試的 UWP 範例應用程式</span><span class="sxs-lookup"><span data-stu-id="82b30-173">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
