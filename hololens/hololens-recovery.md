---
title: 重新啟動、重設或復原 HoloLens
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
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
ms.openlocfilehash: 9c9dd12b596d8fafdfe575797193f18e7b96919c
ms.sourcegitcommit: 2122490074adb7f63edfc3576441980caa22695f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2020
ms.locfileid: "10915955"
---
# <span data-ttu-id="93182-104">重新啟動、重設或復原 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="93182-104">Restart, reset, or recover HoloLens 2</span></span>

## <span data-ttu-id="93182-105">為裝置充電</span><span class="sxs-lookup"><span data-stu-id="93182-105">Charge the device</span></span>

<span data-ttu-id="93182-106">開始進行任何疑難排解程序之前，如果可以，請先確認您的裝置已具備 20% 到40% 的電量。</span><span class="sxs-lookup"><span data-stu-id="93182-106">Before you start any troubleshooting procedure, make sure that your device is charged to 20 to 40 percent of battery capacity if possible.</span></span> <span data-ttu-id="93182-107">使用 HoloLens2 裝置隨附的充電器和 USB Type-C 連接線。</span><span class="sxs-lookup"><span data-stu-id="93182-107">Use the charger and the USB Type-C cables that come with the HoloLens2 device.</span></span> <span data-ttu-id="93182-108">如果您無法使用這些附件，請確認可用的充電器可支援至少 15 瓦的電源。</span><span class="sxs-lookup"><span data-stu-id="93182-108">If those accessories aren't available, make sure the charger that's available can support at least 15 W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="93182-109">如果可以，請避免使用電腦透過 USB 為裝置充電 (速度慢)。</span><span class="sxs-lookup"><span data-stu-id="93182-109">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="93182-110">如果裝置已正確啟動並運行，則可以使用三種方法來檢查電池電量等級:</span><span class="sxs-lookup"><span data-stu-id="93182-110">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="93182-111">從 HoloLens 裝置 UI 的主要功能表。</span><span class="sxs-lookup"><span data-stu-id="93182-111">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="93182-112">檢視靠近電源按鈕的 LED (若具有 40% 的電量，您應至少看到兩個亮起的 LED 燈)。</span><span class="sxs-lookup"><span data-stu-id="93182-112">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDS).</span></span>
- <span data-ttu-id="93182-113">在您的主機電腦上開啟 [檔案總管]，然後在 **[這台電腦]** 下方左側尋找您的 HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="93182-113">On your host PC, open File Explorer and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="93182-114">以滑鼠右鍵按一下裝置，並選取 **[內容]**。</span><span class="sxs-lookup"><span data-stu-id="93182-114">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="93182-115">對話方塊會隨即顯示電池電量等級。</span><span class="sxs-lookup"><span data-stu-id="93182-115">A dialog box will show the battery charge level.</span></span>

   ![HoloLens 2 屬性畫面會顯示電池電量等級](images/ResetRecovery2.png)

<span data-ttu-id="93182-117">如果裝置無法引導至 [啟動] 功能表，請注意主機電腦上的 LED 外觀和裝置枚舉。</span><span class="sxs-lookup"><span data-stu-id="93182-117">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="93182-118">然後按照 [疑難排解指南](https://docs.microsoft.com/hololens/hololens-troubleshooting)。</span><span class="sxs-lookup"><span data-stu-id="93182-118">Then follow the [troubleshooting guide](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="93182-119">如果裝置狀態不符合疑難排解指南中所列的任何一種狀態，請執行*硬重設程序*，並將裝置連結到電源，而非您的主機電腦。</span><span class="sxs-lookup"><span data-stu-id="93182-119">If the state of the device doesn't match any of the states listed in the troubleshooting guide, do the *hard reset procedure* with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="93182-120">請至少等候一個小時，讓裝置充電。</span><span class="sxs-lookup"><span data-stu-id="93182-120">Wait at least one hour for the device to charge.</span></span>

## <span data-ttu-id="93182-121">重設裝置</span><span class="sxs-lookup"><span data-stu-id="93182-121">Reset the device</span></span>

<span data-ttu-id="93182-122">在某些情況下，您可能需要在不使用 SW UI 的狀況下，手動重設裝置。</span><span class="sxs-lookup"><span data-stu-id="93182-122">Under certain circumstances, you may have to manually reset the device without using the SW UI.</span></span>

### <span data-ttu-id="93182-123">標準程序</span><span class="sxs-lookup"><span data-stu-id="93182-123">Standard procedure</span></span>
1. <span data-ttu-id="93182-124">取下 Type-C 連接線，以中斷裝置和電源或主機電腦的連線。</span><span class="sxs-lookup"><span data-stu-id="93182-124">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="93182-125">按住**電源**按鈕 15 秒。</span><span class="sxs-lookup"><span data-stu-id="93182-125">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="93182-126">所有的 LED 均應關閉。</span><span class="sxs-lookup"><span data-stu-id="93182-126">All LEDs should be off.</span></span>

3. <span data-ttu-id="93182-127">等待2-3 秒，然後按一下 **電源** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="93182-127">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="93182-128">靠近電源按鈕的 LED 燈會亮起，而裝置將開始啟動。</span><span class="sxs-lookup"><span data-stu-id="93182-128">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="93182-129">將裝置連線到主機電腦，然後開啟 [裝置管理員]。</span><span class="sxs-lookup"><span data-stu-id="93182-129">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="93182-130">(針對 Windows 10，請按 **Windows** 鍵，再按 **X** 鍵，然後選取 **裝置管理員**。) 確認裝置枚舉正確為 *Microsoft HoloLens* 如以下影像所示:</span><span class="sxs-lookup"><span data-stu-id="93182-130">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="93182-132">硬重設程序</span><span class="sxs-lookup"><span data-stu-id="93182-132">Hard-reset procedure</span></span>

<span data-ttu-id="93182-133">如果標準重設程序無法運作，請使用硬重設程序:</span><span class="sxs-lookup"><span data-stu-id="93182-133">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="93182-134">取下 Type-C 連接線，以中斷裝置和電源或主機電腦的連線。</span><span class="sxs-lookup"><span data-stu-id="93182-134">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="93182-135">按住 **調低音量** + **電源** 按鈕 15 秒。</span><span class="sxs-lookup"><span data-stu-id="93182-135">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="93182-136">裝置會自動重新啟動。</span><span class="sxs-lookup"><span data-stu-id="93182-136">The device will automatically restart.</span></span>

4. <span data-ttu-id="93182-137">將裝置連接到主機電腦。</span><span class="sxs-lookup"><span data-stu-id="93182-137">Connect the device to the host PC.</span></span>
5. <span data-ttu-id="93182-138">開啟 [裝置管理員] （如果是 Windows 10，請按 **Windows** 鍵，然後按 **X** 鍵，並選取 **[裝置管理員]**）。</span><span class="sxs-lookup"><span data-stu-id="93182-138">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="93182-139">請確認裝置枚舉正確為 *Microsoft HoloLens*，如下列影像所示：</span><span class="sxs-lookup"><span data-stu-id="93182-139">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="93182-141">乾淨重新快閃刷新裝置</span><span class="sxs-lookup"><span data-stu-id="93182-141">Clean-reflash the device</span></span>

<span data-ttu-id="93182-142">在特別的情況下，您可能需要乾淨快閃刷新 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="93182-142">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="93182-143">有兩種方法可以快閃刷新裝置。</span><span class="sxs-lookup"><span data-stu-id="93182-143">There are two ways to reflash the device.</span></span> <span data-ttu-id="93182-144">針對這兩種方法，您必須先 [從 Windows Store 上安裝 Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8)。</span><span class="sxs-lookup"><span data-stu-id="93182-144">For both, you must first install [Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="93182-145">如果快閃刷新裝置，您所有的個人資料、應用程式和設定都會被清除，包含 TPM 重設資訊。</span><span class="sxs-lookup"><span data-stu-id="93182-145">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="93182-146">根據預設，[Advanced Recovery Companion] 目前已設定為下載 [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004) 發行組建功能。</span><span class="sxs-lookup"><span data-stu-id="93182-146">By default, Advanced Recovery Companion is currently set to download the feature release build for [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004).</span></span> <span data-ttu-id="93182-147">若要取得最新的 HoloLens 2 完整刷新更新（FFU）套件，以透過 [Advanced Recovery Companion] 快閃刷新您的裝置，請 [於此下載](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="93182-147">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [download it here](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="93182-148">此版本是最新的萬用組建。</span><span class="sxs-lookup"><span data-stu-id="93182-148">This version is the latest generally available build.</span></span>

<span data-ttu-id="93182-149">在啟動快閃刷新程序前，請確認已在 Windows 10 電腦上安裝並執行該應用程式，並準備好偵測裝置。</span><span class="sxs-lookup"><span data-stu-id="93182-149">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![HoloLens 2 乾淨快閃刷新螢幕擷取畫面](images/ARC1.png)

### <span data-ttu-id="93182-151">正常程序</span><span class="sxs-lookup"><span data-stu-id="93182-151">Normal procedure</span></span>

1. <span data-ttu-id="93182-152">當 HoloLens 裝置執行時，請將它連線到先前開啟的 Advanced Recovery Companion 應用程式的 Windows 10 電腦。</span><span class="sxs-lookup"><span data-stu-id="93182-152">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="93182-153">系統會自動偵測到裝置，而 Advanced Recovery Companion 應用程式 UI 則會開始更新程序：</span><span class="sxs-lookup"><span data-stu-id="93182-153">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 乾淨快閃刷新初始畫面](images/ARC2.png)

3. <span data-ttu-id="93182-155">在 Advanced Recovery Companion 應用程式 UI 中選取 HoloLens 2 裝置，並依照指示完成快閃刷新。</span><span class="sxs-lookup"><span data-stu-id="93182-155">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <span data-ttu-id="93182-156">手動程序</span><span class="sxs-lookup"><span data-stu-id="93182-156">Manual procedure</span></span>

<span data-ttu-id="93182-157">如果 HoloLens2 無法正確啟動，您可能需要將裝置置於修復模式:</span><span class="sxs-lookup"><span data-stu-id="93182-157">If the HoloLens 2 doesn't start correctly, you may need to put the device into Recovery mode:</span></span>

1. <span data-ttu-id="93182-158">取下 Type-C 連接線，以中斷裝置和電源或主機電腦的連線。</span><span class="sxs-lookup"><span data-stu-id="93182-158">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="93182-159">按住**電源**按鈕 15 秒。</span><span class="sxs-lookup"><span data-stu-id="93182-159">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="93182-160">此時應該會關閉所有 LED。</span><span class="sxs-lookup"><span data-stu-id="93182-160">All LEDs should turn off.</span></span>

3. <span data-ttu-id="93182-161">按下**調高音量**按鈕時，請按下並放開**電源** 按鈕以啟動裝置。</span><span class="sxs-lookup"><span data-stu-id="93182-161">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="93182-162">請等候 15 秒，然後再放開 **調高音量**按鈕。</span><span class="sxs-lookup"><span data-stu-id="93182-162">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="93182-163">只有中間的五個 LED 燈會亮起。</span><span class="sxs-lookup"><span data-stu-id="93182-163">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="93182-164">將裝置連線到主機電腦，並開啟 [裝置管理員]。</span><span class="sxs-lookup"><span data-stu-id="93182-164">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="93182-165">(針對 Windows 10，請按 **Windows** 鍵，再按 **X** 鍵，然後選取 **裝置管理員**。) 確認裝置枚舉正確為 Microsoft HoloLens 如以下影像所示:</span><span class="sxs-lookup"><span data-stu-id="93182-165">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="93182-167">系統會自動偵測到裝置，而 Advanced Recovery Companion 應用程式 UI 則會開始更新程序：</span><span class="sxs-lookup"><span data-stu-id="93182-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 乾淨快閃刷新畫面](images/ARC2.png)

6. <span data-ttu-id="93182-169">在 Advanced Recovery Companion 應用程式 UI 中選取 HoloLens 2 裝置，然後依照指示完成快閃刷新。</span><span class="sxs-lookup"><span data-stu-id="93182-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <span data-ttu-id="93182-170">不使用應用程式商店來下載 ARC</span><span class="sxs-lookup"><span data-stu-id="93182-170">Download ARC without using the app store</span></span>

<span data-ttu-id="93182-171">如果 IT 環境禁止使用 Windows Store 應用程式或限制存取零售商店，則 IT 系統管理員可以透過「離線」部署路徑，提供此應用程式。</span><span class="sxs-lookup"><span data-stu-id="93182-171">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE] 
 > - <span data-ttu-id="93182-172">IT 系統管理員也可以透過 [系統中心設定管理員(SCCM)] 或 Intune 來分發這個應用程式。</span><span class="sxs-lookup"><span data-stu-id="93182-172">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="93182-173">本指南將側重於 Advance Recovery Companion，但該程式也適用於其他 [離線] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="93182-173">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="93182-174">按照下列步驟啟用部署路徑：</span><span class="sxs-lookup"><span data-stu-id="93182-174">Follow these steps to enable the deployment path:</span></span>
1. <span data-ttu-id="93182-175">請移至 [商務用 Microsoft Store](https://businessstore.microsoft.com)，並使用 Azure Active Directory 身分識別登入。</span><span class="sxs-lookup"><span data-stu-id="93182-175">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="93182-176">移至 **管理-設定**。</span><span class="sxs-lookup"><span data-stu-id="93182-176">Go to **Manage – Settings**.</span></span> <span data-ttu-id="93182-177">開啟 **[購物體驗]** 底下的 **[顯示離線應用程式]**。</span><span class="sxs-lookup"><span data-stu-id="93182-177">Turn on **Show offline apps** under **Shopping experience**.</span></span> 
1. <span data-ttu-id="93182-178">移至**為我的群組採購**並搜尋 [***Advanced Recovery Companion***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)。</span><span class="sxs-lookup"><span data-stu-id="93182-178">Go to **shop for my group**, and search for [***Advanced Recovery Companion***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>
1. <span data-ttu-id="93182-179">將**授權類型**變更為 ***離線***，然後按一下 **[管理]**。</span><span class="sxs-lookup"><span data-stu-id="93182-179">Change the **License Type** to ***offline***, and select **Manage**.</span></span>
1. <span data-ttu-id="93182-180">在 **[下載套件供離線使用]** 底下，選取第二個藍色 **[下載]** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="93182-180">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="93182-181">請確定檔案副檔名為 *.appxbundle*。</span><span class="sxs-lookup"><span data-stu-id="93182-181">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="93182-182">在這個階段，如果桌上型電腦具有網際網路存取權，只要按兩下套件以安裝應用程式即可。</span><span class="sxs-lookup"><span data-stu-id="93182-182">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>


    - <span data-ttu-id="93182-183">如果目的地電腦沒有網際網路連線能力，請遵循下列步驟操作：</span><span class="sxs-lookup"><span data-stu-id="93182-183">If the desination PC has no internet connectivity, follow these steps:</span></span> 
       1. <span data-ttu-id="93182-184">選取未編碼的授權，然後選取 **[產生授權]**。</span><span class="sxs-lookup"><span data-stu-id="93182-184">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="93182-185">在 **[所需的框架]** 底下，選取 **[下載]**。</span><span class="sxs-lookup"><span data-stu-id="93182-185">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="93182-186">使用 DISM 將套件與依存關係和授權一起套用。</span><span class="sxs-lookup"><span data-stu-id="93182-186">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="93182-187">在系統管理員的命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="93182-187">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > <span data-ttu-id="93182-188">此代碼範例中的版本號碼可能不符目前可用的版本。</span><span class="sxs-lookup"><span data-stu-id="93182-188">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="93182-189">您可能也選取了不同於範例的下載位置。</span><span class="sxs-lookup"><span data-stu-id="93182-189">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="93182-190">視需要變更命令。</span><span class="sxs-lookup"><span data-stu-id="93182-190">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="93182-191">當您打算使用 Advanced Recovery Companion 離線安裝 FFU 時，下載快閃影像可能會很有用。</span><span class="sxs-lookup"><span data-stu-id="93182-191">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="93182-192">[**下載 HoloLens 2 目前的影像**](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="93182-192">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="93182-193">其他資源：</span><span class="sxs-lookup"><span data-stu-id="93182-193">Other resources:</span></span>
- [<span data-ttu-id="93182-194">散發離線 App</span><span class="sxs-lookup"><span data-stu-id="93182-194">Distribute offline apps</span></span>](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="93182-195">DISM 應用程式套件（.appx 或 .appxbundle）服務命令列選項</span><span class="sxs-lookup"><span data-stu-id="93182-195">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
