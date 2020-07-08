---
title: 重新啟動、重設或復原 HoloLens
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
description: 如何使用 Advanced Recovery Companion 將影像快閃匯入到 HoloLens 2。
keywords: 操作說明、重新開機、重設、復原、硬重設、軟重設、電源重新啟動、HoloLens、關機、ARC、advanced recovery companion
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
ms.openlocfilehash: 2c7fa9b8c86900c89bbced1a10f3e9e2bc69bcd0
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857761"
---
# <span data-ttu-id="c9799-104">重新啟動、重設或復原 HoloLens</span><span class="sxs-lookup"><span data-stu-id="c9799-104">Restart, reset, or recover HoloLens</span></span>

## <span data-ttu-id="c9799-105">正在對裝置充電</span><span class="sxs-lookup"><span data-stu-id="c9799-105">Charging the device</span></span>

<span data-ttu-id="c9799-106">在啟動任何疑難排解程序之前，請先確認您的裝置電量至少在 20% 到 40% 之間。</span><span class="sxs-lookup"><span data-stu-id="c9799-106">Before starting any troubleshooting procedure, if possible, ensure that your device is charged at least between 20% and 40%.</span></span>

<span data-ttu-id="c9799-107">請確認您使用的是 HoloLens2 裝置隨附的充電器和 USB Type-C 纜線。</span><span class="sxs-lookup"><span data-stu-id="c9799-107">Please ensure you are using the charger and the USB Type-C cables that come with the HoloLens2 device.</span></span> <span data-ttu-id="c9799-108">如果無法使用，請確保可使用的充電器最低可支援 15W。</span><span class="sxs-lookup"><span data-stu-id="c9799-108">In case they are not available ensure the charger available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="c9799-109">如果可能，請不要使用電腦透過 USB 對裝置充電，因為這會讓充電非常緩慢。</span><span class="sxs-lookup"><span data-stu-id="c9799-109">If possible, do not use a PC to charge the device over USB as this will provide a very slow charge.</span></span>

<span data-ttu-id="c9799-110">如果裝置已正確啟動並運行，則可以使用三種不同的方法來檢查電池電量。</span><span class="sxs-lookup"><span data-stu-id="c9799-110">If the device is correctly booted and running there are three different ways of checking the charge of your battery.</span></span>

1. <span data-ttu-id="c9799-111">從 HoloLens 裝置 UI 的主要功能表。</span><span class="sxs-lookup"><span data-stu-id="c9799-111">From the main menu of the HoloLens Device UI.</span></span>
2. <span data-ttu-id="c9799-112">使用靠近電源按鈕的 LED (就 40% 而言，您應該至少看到兩個實心 LED)。</span><span class="sxs-lookup"><span data-stu-id="c9799-112">Using the LED close to the power button (for 40% you should see at least two solid LEDS).</span></span>
3. <span data-ttu-id="c9799-113">在您的主機電腦上開啟 [檔案總管] 視窗，然後在左側 [這台電腦] 底下尋找您的 HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="c9799-113">On your Host PC open File Explorer window and look for your HoloLens 2 device on left side under “This PC”.</span></span>
    
      <span data-ttu-id="c9799-114">a.</span><span class="sxs-lookup"><span data-stu-id="c9799-114">a.</span></span> <span data-ttu-id="c9799-115">以滑鼠右鍵按一下裝置名稱，然後選取 [內容]。</span><span class="sxs-lookup"><span data-stu-id="c9799-115">Right click on the name of the device and select properties.</span></span> <span data-ttu-id="c9799-116">畫面會顯示您裝置的電池電量。</span><span class="sxs-lookup"><span data-stu-id="c9799-116">A dialog will appear showing the battery level for your device.</span></span>

![HoloLens 2 ResetRecovery](images/ResetRecovery2.png)

<span data-ttu-id="c9799-118">如果無法啟動裝置至 [開始功能表]，請注意主機電腦上的 LED 和細目，並遵循疑難排解指南進行 (https://docs.microsoft.com/hololens/hololens-troubleshooting)。</span><span class="sxs-lookup"><span data-stu-id="c9799-118">If the device cannot be booted to the Startup Menu, please take note of the LEDs and enumeration on the host PC and follow the troubleshooting guide (https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="c9799-119">當裝置狀態不屬於疑難排解指南中所列的任何一種時，請執行**硬重設程序**，而不需將裝置重新連結到您的主機電腦，只需將裝置連線至電源即可。</span><span class="sxs-lookup"><span data-stu-id="c9799-119">In case the state of the device does not fall in any of the states listed in the troubleshooting guide, execute the **hard reset procedure** without reconnecting the device to your host PC, but connect it instead to the power supply.</span></span> <span data-ttu-id="c9799-120">請至少等候一個小時後再讓裝置充電。</span><span class="sxs-lookup"><span data-stu-id="c9799-120">Wait for at least one hour for the device to charge.</span></span>

## <span data-ttu-id="c9799-121">重設裝置</span><span class="sxs-lookup"><span data-stu-id="c9799-121">Reset the device</span></span>

<span data-ttu-id="c9799-122">在某些情況下，客戶可能需要手動重設裝置，而不需使用 SW UI。</span><span class="sxs-lookup"><span data-stu-id="c9799-122">Under certain circumstances the customer may be required to manually reset the device without using the SW UI.</span></span> 

### <span data-ttu-id="c9799-123">標準程序</span><span class="sxs-lookup"><span data-stu-id="c9799-123">Standard procedure</span></span>
1. <span data-ttu-id="c9799-124">拔掉 Type-C 纜線，以中斷裝置和電源或主機電腦的連線。</span><span class="sxs-lookup"><span data-stu-id="c9799-124">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span>

2. <span data-ttu-id="c9799-125">按住**電源**按鈕 15 秒。</span><span class="sxs-lookup"><span data-stu-id="c9799-125">Press and hold the **power button** for 15 seconds.</span></span> <span data-ttu-id="c9799-126">所有的 LED 均應關閉。</span><span class="sxs-lookup"><span data-stu-id="c9799-126">All LEDs should be off.</span></span>

3. <span data-ttu-id="c9799-127">等待 2-3 秒並短按**電源按鈕**，電源按鈕附近的 LED 會亮起，裝置就會開始開機。</span><span class="sxs-lookup"><span data-stu-id="c9799-127">Wait 2-3 seconds and Short press the **power button**, the LEDs close to the power button will light up and the device will start to boot.</span></span> 

4. <span data-ttu-id="c9799-128">將裝置連線到主機電腦，然後開啟 [裝置管理員] (針對 Windows 10，請按下 **Windows 鍵**，再按下 **x** 鍵，然後按一下 [裝置管理員]) ，並確定裝置列舉方式如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="c9799-128">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the pictures below:</span></span>

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="c9799-130">硬重設程序</span><span class="sxs-lookup"><span data-stu-id="c9799-130">Hard-reset procedure</span></span>

<span data-ttu-id="c9799-131">如果標準重設程序無法運作，您可以使用硬重設程序。</span><span class="sxs-lookup"><span data-stu-id="c9799-131">If the standard reset procedure does not work, you can use the hard-reset procedure.</span></span>

1. <span data-ttu-id="c9799-132">拔掉 Type-C 纜線，以中斷裝置和電源或主機電腦的連線。</span><span class="sxs-lookup"><span data-stu-id="c9799-132">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span>

2. <span data-ttu-id="c9799-133">按住**調低音量 + 電源按鈕** 15 秒。</span><span class="sxs-lookup"><span data-stu-id="c9799-133">Hold **volume down + power button** for 15 seconds.</span></span>

3. <span data-ttu-id="c9799-134">裝置會自動重新開機。</span><span class="sxs-lookup"><span data-stu-id="c9799-134">The device will automatically reboot.</span></span> 

4. <span data-ttu-id="c9799-135">將裝置連線到主機電腦，然後開啟 [裝置管理員] (針對 Windows 10，請按下 **Windows 鍵**，再按下 **x** 鍵，然後按一下 [裝置管理員]) ，並確定裝置列舉方式如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="c9799-135">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the pictures below.</span></span>

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="c9799-137">乾淨重新快閃刷新裝置</span><span class="sxs-lookup"><span data-stu-id="c9799-137">Clean reflash the device</span></span>

<span data-ttu-id="c9799-138">在特別的情況下，您可能需要將裝置乾淨快閃刷新。</span><span class="sxs-lookup"><span data-stu-id="c9799-138">In extraordinary situations you may be required to clean flash the device.</span></span> <span data-ttu-id="c9799-139">有兩種方法可以重新快閃刷新 HoloLens2 裝置。</span><span class="sxs-lookup"><span data-stu-id="c9799-139">There are two ways to reflash a HoloLens2 device.</span></span> <span data-ttu-id="c9799-140">針對所有重新快閃刷新程序，您必須從 Windows 市集中[安裝 Advanced Recovery Companion 應用程式](https://www.microsoft.com/store/productId/9P74Z35SFRS8)。</span><span class="sxs-lookup"><span data-stu-id="c9799-140">For all reflashing procedures you will be required to [install the Advanced Recovery Companion app from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span> <span data-ttu-id="c9799-141">如果重設裝置，您所有的個人資料、應用程式和設定都會被清除，包括 TPM 重設。</span><span class="sxs-lookup"><span data-stu-id="c9799-141">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset.</span></span>

<span data-ttu-id="c9799-142">Advanced Recovery Companion 目前已設定為針對 [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004) 下載功能發行版本組建，如果您想要下載最新的 HoloLens 2 FFU，以透過 Advanced Recovery Companion 來快閃刷新您的裝置，可以從[此處](https://aka.ms/hololens2download)下載。</span><span class="sxs-lookup"><span data-stu-id="c9799-142">Advanced Recovery Companion is currently set to download the feature release build for [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004), if you would like to download the latest HoloLens 2 FFU to flash your device via Advanced Recovery Companion then you may download it from [here](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="c9799-143">此動作會保持為最新狀態，並會匹配最新的可用組建。</span><span class="sxs-lookup"><span data-stu-id="c9799-143">This is kept up-to-date and will match the latest generally available build.</span></span> 

<span data-ttu-id="c9799-144">啟動快閃刷新程序前，請確認已在 Windows 10 電腦上安裝並執行該應用程式，並準備好偵測裝置。</span><span class="sxs-lookup"><span data-stu-id="c9799-144">Before starting the flashing procedure make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![HoloLens 2 乾淨重新快閃刷新](images/ARC1.png)

### <span data-ttu-id="c9799-146">正常程序</span><span class="sxs-lookup"><span data-stu-id="c9799-146">Normal procedure</span></span>

1. <span data-ttu-id="c9799-147">當 HoloLens 裝置執行時，請將它連線到您先前啟動 Advanced Recovery Companion 應用程式的 Windows 10 電腦。</span><span class="sxs-lookup"><span data-stu-id="c9799-147">While the HoloLens device is running, connect it to your Windows 10 PC where you previously launched the Advanced Recovery Companion App.</span></span>

2. <span data-ttu-id="c9799-148">系統會自動偵測到裝置，且 Advanced Recovery Companion 應用程式 UI 會更新如下：</span><span class="sxs-lookup"><span data-stu-id="c9799-148">The device will automatically be detected and the Advanced Recovery Companion App UI will update as follows:</span></span>

![HoloLens 2 乾淨重新快閃刷新](images/ARC2.png)

3. <span data-ttu-id="c9799-150">在 Advanced Recovery Companion 應用程式 UI 中選取 HoloLens2 裝置，並依照指示完成快閃刷新。</span><span class="sxs-lookup"><span data-stu-id="c9799-150">Select the HoloLens2 device in the Advanced Recovery Companion App UI and follow the instructions to complete the flashing.</span></span>

### <span data-ttu-id="c9799-151">手動程序</span><span class="sxs-lookup"><span data-stu-id="c9799-151">Manual procedure</span></span>

<span data-ttu-id="c9799-152">如果裝置無法正確引導，您可能需要將 HoloLens 2 裝置置於復原模式。</span><span class="sxs-lookup"><span data-stu-id="c9799-152">If the device does not boot correctly you may need to put the HoloLens 2 device in Recovery mode.</span></span>

1. <span data-ttu-id="c9799-153">拔掉 Type-C 纜線，以中斷裝置和電源或主機電腦的連線。</span><span class="sxs-lookup"><span data-stu-id="c9799-153">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span> 

2. <span data-ttu-id="c9799-154">按住**電源**按鈕 15 秒。</span><span class="sxs-lookup"><span data-stu-id="c9799-154">Press and hold the **power button** for 15 seconds.</span></span> <span data-ttu-id="c9799-155">此時應該會關閉所有 LED。</span><span class="sxs-lookup"><span data-stu-id="c9799-155">All LEDs should turn off.</span></span> 

3. <span data-ttu-id="c9799-156">按下**調低音量**時，請按下並放開**電源按鈕** 以將裝置開機。</span><span class="sxs-lookup"><span data-stu-id="c9799-156">While pressing the **volume up button**, press and release the **power button** to boot the device.</span></span> <span data-ttu-id="c9799-157">請等候 15 秒，然後再放開調高音量按鈕。</span><span class="sxs-lookup"><span data-stu-id="c9799-157">Wait 15 seconds before releasing the volume up button.</span></span> <span data-ttu-id="c9799-158">在裝置上的 5 個 LED 中，只有中間的 LED 會亮起。</span><span class="sxs-lookup"><span data-stu-id="c9799-158">Out of the 5 LEDs on the device, only the middle LED will light up.</span></span>

4. <span data-ttu-id="c9799-159">將裝置連線到主機電腦，然後開啟 [裝置管理員] (針對 Windows 10，請按下 **Windows 鍵**，再按下 **x** 鍵，然後按一下 [裝置管理員]) ，並確定裝置列舉方式如下影像所示。</span><span class="sxs-lookup"><span data-stu-id="c9799-159">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the image below.</span></span>

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

5. <span data-ttu-id="c9799-161">系統會自動偵測到裝置，而 Advanced Recovery Companion 應用程式 UI 會更新如下：</span><span class="sxs-lookup"><span data-stu-id="c9799-161">The device will be automatically detected, and the Advanced Recovery Companion app UI will update as follows:</span></span>

![HoloLens 2 乾淨重新快閃刷新](images/ARC2.png)

6. <span data-ttu-id="c9799-163">在 Advanced Recovery Companion 應用程式 UI 中選取 HoloLens 2 裝置，並依照指示完成快閃刷新。</span><span class="sxs-lookup"><span data-stu-id="c9799-163">Select the HoloLens 2 device in the Advanced Recovery Companion app UI and follow the instructions to complete the flashing.</span></span>

## <span data-ttu-id="c9799-164">不使用應用程式商店來下載 ARC</span><span class="sxs-lookup"><span data-stu-id="c9799-164">Downloading ARC without using the app store</span></span>

<span data-ttu-id="c9799-165">如果 IT 環境禁止使用 Windows 市集應用程式或限制存取零售商店，IT 系統管理員可以透過其他「離線」部署路徑，以提供此應用程式。</span><span class="sxs-lookup"><span data-stu-id="c9799-165">If an IT environment prevents the use of the Windows Store app or limits access to the retail store, IT administrators can make this app available through other ‘offline’ deployment paths.</span></span> 

- <span data-ttu-id="c9799-166">這個程序也可以用於其他應用程式，如步驟 2 所示。</span><span class="sxs-lookup"><span data-stu-id="c9799-166">This process may also be used for other apps, as seen in step 2.</span></span> <span data-ttu-id="c9799-167">本指南將側重於 Recovery Companion，但可能會為其他離線應用程式修改。</span><span class="sxs-lookup"><span data-stu-id="c9799-167">This guide will focus on Advanced Recovery Companion, but my be modified for other offline apps.</span></span>  

<span data-ttu-id="c9799-168">您可以使用下列步驟啟用此部署路徑：</span><span class="sxs-lookup"><span data-stu-id="c9799-168">This deployment path can be enabled with the following steps:</span></span>
1.  <span data-ttu-id="c9799-169">移至 [商務用 Store 網站](https://businessstore.microsoft.com)，並使用 Azure AD 身分識別登入。</span><span class="sxs-lookup"><span data-stu-id="c9799-169">Go to the [Store For Business website](https://businessstore.microsoft.com) and sign-in with an Azure AD identity.</span></span>
1.  <span data-ttu-id="c9799-170">移至**管理 – 設定**，並開啟**購物體驗**底下的 [顯示離線應用程式]\*\*\*\* ，如 https://businessstore.microsoft.com/manage/settings/shop 所述</span><span class="sxs-lookup"><span data-stu-id="c9799-170">Go to **Manage – Settings**, and turn on **Show offline apps** under **Shopping experience** as described at https://businessstore.microsoft.com/manage/settings/shop</span></span> 
1.  <span data-ttu-id="c9799-171">移至**為我的群組採購**並搜尋 [Advanced Recovery Companion](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8) 應用程式。</span><span class="sxs-lookup"><span data-stu-id="c9799-171">Go to **shop for my group** and search for the [Advanced Recovery Companion](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8) app.</span></span>
1.  <span data-ttu-id="c9799-172">將**授權類型**方塊變更為離線，然後按一下 [管理]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c9799-172">Change the **License Type** box to offline and click **Manage**.</span></span>
1.  <span data-ttu-id="c9799-173">在 [下載套件供離線使用] 底下，按一下第二個藍色 [下載]\*\*\*\* 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c9799-173">Under Download the package for offline use click the second blue **“Download”** button .</span></span> <span data-ttu-id="c9799-174">請確定檔案副檔名為 .appxbundle。</span><span class="sxs-lookup"><span data-stu-id="c9799-174">Ensure the file extension is .appxbundle.</span></span>
1.  <span data-ttu-id="c9799-175">在這個階段，如果桌上型電腦能存取網際網路，只要按兩下並安裝即可。</span><span class="sxs-lookup"><span data-stu-id="c9799-175">At this stage, if the Desktop PC has Internet access, simply double click and install.</span></span> 
1.  <span data-ttu-id="c9799-176">IT 系統管理員也可以透過 System Center Configuration Manager (SCCM) 或 Intune 來分發這個應用程式。</span><span class="sxs-lookup"><span data-stu-id="c9799-176">The IT administrator can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
1.  <span data-ttu-id="c9799-177">如果目的電腦沒有網際網路連線，則需要採取一些額外的步驟：</span><span class="sxs-lookup"><span data-stu-id="c9799-177">If the target PC has no Internet connectivity, some additional steps are needed:</span></span> 
    1.  <span data-ttu-id="c9799-178">選取未編碼的授權並按一下 [產生授權]\*\*\*\*，並在 [必要的框架]\*\*\*\* 底下，按一下 [下載]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c9799-178">Select the unencoded license and click **“Generate license”** and under **“Required Frameworks”** click **“Download.”**</span></span> 
    1.  <span data-ttu-id="c9799-179">無網際網路存取的電腦，將需要使用 DISM，以相依性與授權來套用套件。</span><span class="sxs-lookup"><span data-stu-id="c9799-179">PCs without internet access will need to use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="c9799-180">在系統管理員命令提示字元中，輸入：</span><span class="sxs-lookup"><span data-stu-id="c9799-180">In an administrator command prompt, type:</span></span>

      ```console
      C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
      ```
> [!NOTE]
> <span data-ttu-id="c9799-181">此代碼範例中的版本號碼可能不符目前可用的版本。</span><span class="sxs-lookup"><span data-stu-id="c9799-181">The version number in this code example may not match the currently avalible version.</span></span> <span data-ttu-id="c9799-182">您可能已選取不同於所提供範例的下載位置。</span><span class="sxs-lookup"><span data-stu-id="c9799-182">You may have also choosen a different download location than in the example given.</span></span> <span data-ttu-id="c9799-183">請務必視需要進行變更。</span><span class="sxs-lookup"><span data-stu-id="c9799-183">Please make sure to make any changes as needed.</span></span>

> [!TIP]
> <span data-ttu-id="c9799-184">當您計畫使用 Advanced Recovery Companion 來離線安裝 ffu 時，建議先下載快閃刷新影像，以下是 [HoloLens 2 的目前影像](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="c9799-184">When planning to use Advanced Recovery Companion to install an ffu offline it may be useful to download your flashing image to be availible, here is the [current image for HoloLens 2](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="c9799-185">其他資源：</span><span class="sxs-lookup"><span data-stu-id="c9799-185">Other resources:</span></span>
- https://docs.microsoft.com/microsoft-store/distribute-offline-apps 
- https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options


