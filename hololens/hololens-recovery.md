---
title: 重新開機、重設或復原 HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: 如何使用 Advanced Recovery 將映射快閃以 HoloLens 2。
keywords: how to、重新開機、重設、復原、硬重設、軟重設、電源週期、HoloLens、關機、arc、advanced recovery 輔助
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
appliesto:
- HoloLens 2
ms.openlocfilehash: 0124453ef9e3b21722acaf2c6b438ebdfbd65043
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635937"
---
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="df1ef-104">重新開機、重設或復原 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="df1ef-104">Restart, reset, or recover HoloLens 2</span></span>

>[!IMPORTANT]
> <span data-ttu-id="df1ef-105">在開始進行任何疑難排解程式之前，請確定您的裝置必須支付 **20% 到 40%** 的電池容量（如果可能的話）。</span><span class="sxs-lookup"><span data-stu-id="df1ef-105">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="df1ef-106">位於 [電源] 按鈕下的 [電池指標燈](hololens2-setup.md#lights-that-indicate-the-battery-level) 是快速驗證電池容量，而不需要登入裝置的方式。</span><span class="sxs-lookup"><span data-stu-id="df1ef-106">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<span data-ttu-id="df1ef-107">使用 HoloLens 2 隨附的[充電器和 USB 類型 C 纜線](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1)，因為這是向裝置收費的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="df1ef-107">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="df1ef-108">充電器在 2A) 提供 power (9V 的18W。</span><span class="sxs-lookup"><span data-stu-id="df1ef-108">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="df1ef-109">在裝置處於待命狀態的情況下，HoloLens 2 裝置可使用所提供的牆充電器，在65分鐘內將電池充電以填滿。</span><span class="sxs-lookup"><span data-stu-id="df1ef-109">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="df1ef-110">如果無法使用這些附屬應用程式，請確定提供的充電可支援至少15W 的電源。</span><span class="sxs-lookup"><span data-stu-id="df1ef-110">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="df1ef-111">可能的話，請避免使用電腦透過 USB 收取裝置的費用，這會很慢。</span><span class="sxs-lookup"><span data-stu-id="df1ef-111">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="df1ef-112">如果裝置正確開機且正在執行，有三種方式可以檢查電池計量等級：</span><span class="sxs-lookup"><span data-stu-id="df1ef-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="df1ef-113">從 HoloLens 裝置 UI 的主功能表。</span><span class="sxs-lookup"><span data-stu-id="df1ef-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="df1ef-114">查看電源按鈕 (接近電源按鈕有40% 的費用，您應該會看到至少兩個穩固的 Led) 。</span><span class="sxs-lookup"><span data-stu-id="df1ef-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="df1ef-115">當裝置充電時，電池指示燈會亮起以指出目前的收費層級。</span><span class="sxs-lookup"><span data-stu-id="df1ef-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="df1ef-116">最後一個光線會淡入和淡出以表示主動充電。</span><span class="sxs-lookup"><span data-stu-id="df1ef-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="df1ef-117">當您的 HoloLens 開啟時，電池指示器會以五個增量顯示電池計量。</span><span class="sxs-lookup"><span data-stu-id="df1ef-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="df1ef-118">當您只開啟五個燈的其中一個時，電池計量低於20%。</span><span class="sxs-lookup"><span data-stu-id="df1ef-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="df1ef-119">如果電池計量偏低，而您嘗試開啟裝置，則會短暫閃爍一次，然後移出。</span><span class="sxs-lookup"><span data-stu-id="df1ef-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="df1ef-120">在您的主機電腦上，開啟 **檔案總管**，然後在這部 **電腦** 的左側尋找您的 HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="df1ef-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="df1ef-121">在裝置上按一下滑鼠右鍵，然後選取 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="df1ef-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="df1ef-122">對話方塊會顯示電池計量的等級。</span><span class="sxs-lookup"><span data-stu-id="df1ef-122">A dialog box will show the battery charge level.</span></span>

   ![顯示電池變更層級的 HoloLens 2 屬性畫面](images/ResetRecovery2.png)

<span data-ttu-id="df1ef-124">如果裝置無法開機至 [啟動] 功能表，請注意主機電腦上的 LED 外觀和裝置列舉。</span><span class="sxs-lookup"><span data-stu-id="df1ef-124">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="df1ef-125">然後遵循 [疑難排解指南](hololens-troubleshooting.md)。</span><span class="sxs-lookup"><span data-stu-id="df1ef-125">Then follow the [troubleshooting guide](hololens-troubleshooting.md).</span></span> <span data-ttu-id="df1ef-126">如果裝置的狀態不符合疑難排解指南中所列的任何狀態，請執行 [硬重設](hololens-recovery.md#hard-reset-procedure) 程式，將裝置連接到電源供應器，而不是您的主機電腦。</span><span class="sxs-lookup"><span data-stu-id="df1ef-126">If the state of the device doesn't match any of the states listed in the troubleshooting guide, perform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="df1ef-127">請等候至少一小時讓裝置向您收費。</span><span class="sxs-lookup"><span data-stu-id="df1ef-127">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="df1ef-128">重設裝置</span><span class="sxs-lookup"><span data-stu-id="df1ef-128">Reset the device</span></span>

<span data-ttu-id="df1ef-129">在某些情況下，您可能必須手動重設裝置，而不需要使用軟體 UI。</span><span class="sxs-lookup"><span data-stu-id="df1ef-129">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="df1ef-130">標準程式</span><span class="sxs-lookup"><span data-stu-id="df1ef-130">Standard procedure</span></span>

1. <span data-ttu-id="df1ef-131">拔下類型 C 纜線，以中斷裝置與電源供應器或主機電腦的連線。</span><span class="sxs-lookup"><span data-stu-id="df1ef-131">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="df1ef-132">按住 **電源** 按鈕15秒。</span><span class="sxs-lookup"><span data-stu-id="df1ef-132">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="df1ef-133">所有 Led 都應該關閉。</span><span class="sxs-lookup"><span data-stu-id="df1ef-133">All LEDs should be off.</span></span>

3. <span data-ttu-id="df1ef-134">等候2-3 秒，然後按下 **電源** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="df1ef-134">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="df1ef-135">接近電源按鈕的 Led 會亮起，且裝置將開始啟動。</span><span class="sxs-lookup"><span data-stu-id="df1ef-135">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="df1ef-136">連線裝置到主機電腦，然後開啟裝置管理員。</span><span class="sxs-lookup"><span data-stu-id="df1ef-136">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="df1ef-137">針對 Windows 10 (，請按下 **Windows** 鍵，然後按 **X** 鍵，然後選取 [**裝置管理員**]。 ) 確定裝置已正確列舉為 *Microsoft HoloLens* ，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="df1ef-137">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2MicrosoftHoloLensRecovery devive 管理員](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="df1ef-139">硬重設程式</span><span class="sxs-lookup"><span data-stu-id="df1ef-139">Hard-reset procedure</span></span>

<span data-ttu-id="df1ef-140">如果標準重設程式無法運作，請使用硬重設程式：</span><span class="sxs-lookup"><span data-stu-id="df1ef-140">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="df1ef-141">拔下類型 C 纜線，以中斷裝置與電源供應器或主機電腦的連線。</span><span class="sxs-lookup"><span data-stu-id="df1ef-141">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="df1ef-142">按住音量的  +  **電源** 按鈕15秒。</span><span class="sxs-lookup"><span data-stu-id="df1ef-142">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="df1ef-143">裝置會自動重新開機。</span><span class="sxs-lookup"><span data-stu-id="df1ef-143">The device will automatically restart.</span></span>

4. <span data-ttu-id="df1ef-144">連線裝置到主機電腦。</span><span class="sxs-lookup"><span data-stu-id="df1ef-144">Connect the device to the host PC.</span></span>


5. <span data-ttu-id="df1ef-145">開啟裝置管理員 (Windows 10 按下 **Windows** 鍵，然後選取 [ **X** ] 鍵，然後選取 [**裝置管理員**) ]。</span><span class="sxs-lookup"><span data-stu-id="df1ef-145">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="df1ef-146">請確定裝置已正確列舉為 *Microsoft HoloLens* ，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="df1ef-146">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2MicrosoftHoloLensRecovery 裝置 maanger 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="df1ef-148">清除重新刷新裝置</span><span class="sxs-lookup"><span data-stu-id="df1ef-148">Clean-reflash the device</span></span>

<span data-ttu-id="df1ef-149">在特殊情況下，您可能必須「清理」 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="df1ef-149">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="df1ef-150">請注意，重新刷新不應該影響下列問題：</span><span class="sxs-lookup"><span data-stu-id="df1ef-150">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="df1ef-151">顯示色彩一致性</span><span class="sxs-lookup"><span data-stu-id="df1ef-151">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="df1ef-152">使用音效開機但沒有顯示輸出</span><span class="sxs-lookup"><span data-stu-id="df1ef-152">Booting with sound but no display output</span></span>
- [<span data-ttu-id="df1ef-153">1-3-5-LED 模式</span><span class="sxs-lookup"><span data-stu-id="df1ef-153">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="df1ef-154">過熱</span><span class="sxs-lookup"><span data-stu-id="df1ef-154">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="df1ef-155">作業系統損毀 (與應用程式損毀不同) </span><span class="sxs-lookup"><span data-stu-id="df1ef-155">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="df1ef-156">重新刷新裝置的方式有兩種。</span><span class="sxs-lookup"><span data-stu-id="df1ef-156">There are two ways to reflash the device.</span></span> <span data-ttu-id="df1ef-157">針對這兩種情況，您必須先[從 Windows 存放區安裝 Advanced Recovery 附隨](https://www.microsoft.com/store/productId/9P74Z35SFRS8)。</span><span class="sxs-lookup"><span data-stu-id="df1ef-157">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="df1ef-158">如果您重新刷新您的裝置，將會清除您的所有個人資料、應用程式和設定，包括 TPM 重設資訊。</span><span class="sxs-lookup"><span data-stu-id="df1ef-158">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="df1ef-159">根據預設，Advanced Recovery 附屬設定為下載最新的功能發行組建，請參閱這裡以閱讀我們的 [版本](hololens-release-notes.md#) 資訊，以瞭解最新的功能版本。</span><span class="sxs-lookup"><span data-stu-id="df1ef-159">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="df1ef-160">若要取得最新的 HoloLens 2 Full Flash Update (FFU) 套件以透過 Advanced Recovery 隨附重新刷新您的裝置，請[按一下這裡下載最新的每月 HoloLens 2 映射](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="df1ef-160">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="df1ef-161">此版本是最新正式推出的組建。</span><span class="sxs-lookup"><span data-stu-id="df1ef-161">This version is the latest generally available build.</span></span>

<span data-ttu-id="df1ef-162">開始重新刷新程式之前，請確定已在 Windows 10 電腦上安裝並執行應用程式，並已準備好偵測裝置。</span><span class="sxs-lookup"><span data-stu-id="df1ef-162">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="df1ef-163">也請確定您的 HoloLens 是以最少40% 的費率計費。</span><span class="sxs-lookup"><span data-stu-id="df1ef-163">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![HoloLens 2 乾淨重新刷新螢幕擷取畫面](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="df1ef-165">一般程式</span><span class="sxs-lookup"><span data-stu-id="df1ef-165">Normal procedure</span></span>

1. <span data-ttu-id="df1ef-166">當 HoloLens 裝置正在執行時，請將它連接到您先前開啟 Advanced Recovery 附屬應用程式的 Windows 10 電腦。</span><span class="sxs-lookup"><span data-stu-id="df1ef-166">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="df1ef-167">系統會自動偵測裝置，而且 Advanced Recovery 附屬應用程式 UI 將會啟動更新程式：</span><span class="sxs-lookup"><span data-stu-id="df1ef-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 clean 重新刷新初始畫面](images/ARC2.png)

3. <span data-ttu-id="df1ef-169">在 Advanced Recovery 附屬應用程式 UI 中選取 HoloLens 2 裝置，並遵循指示來完成重新刷新。</span><span class="sxs-lookup"><span data-stu-id="df1ef-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="df1ef-170">手動程式</span><span class="sxs-lookup"><span data-stu-id="df1ef-170">Manual procedure</span></span>

<span data-ttu-id="df1ef-171">如果 HoloLens 2 無法正確啟動，或如果 Advanced Recovery 附屬無法偵測到裝置，您可能需要讓裝置進入修復模式：</span><span class="sxs-lookup"><span data-stu-id="df1ef-171">If the HoloLens 2 doesn't start correctly or if Advanced Recovery Companion cannot detect the device, you may need to put the device into recovery mode:</span></span>

1. <span data-ttu-id="df1ef-172">拔下類型 C 纜線，以中斷裝置與電源供應器或主機電腦的連線。</span><span class="sxs-lookup"><span data-stu-id="df1ef-172">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="df1ef-173">按住 **電源** 按鈕15秒。</span><span class="sxs-lookup"><span data-stu-id="df1ef-173">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="df1ef-174">所有 Led 都應該關閉。</span><span class="sxs-lookup"><span data-stu-id="df1ef-174">All LEDs should turn off.</span></span>

3. <span data-ttu-id="df1ef-175">按下 **音量** 按鈕時，請按下並放開 **電源** 按鈕以啟動裝置。</span><span class="sxs-lookup"><span data-stu-id="df1ef-175">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="df1ef-176">等候15秒，然後放開 **音量** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="df1ef-176">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="df1ef-177">只有五個 Led 的中間 LED 會亮著。</span><span class="sxs-lookup"><span data-stu-id="df1ef-177">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="df1ef-178">連線裝置到主機電腦，然後開啟裝置管理員。</span><span class="sxs-lookup"><span data-stu-id="df1ef-178">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="df1ef-179"> (Windows 10 按下 **Windows** 鍵，然後選取 [ **X** ] 鍵，然後選取 [**裝置管理員**]。 ) 確定裝置已正確列舉為 Microsoft HoloLens，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="df1ef-179">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="df1ef-181">系統會自動偵測裝置，而且 Advanced Recovery 附屬應用程式 UI 將會啟動更新程式：</span><span class="sxs-lookup"><span data-stu-id="df1ef-181">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 clean 重新刷新畫面](images/ARC2.png)

6. <span data-ttu-id="df1ef-183">在 Advanced Recovery 附屬應用程式 UI 中選取 HoloLens 2 裝置，然後遵循指示來完成重新刷新。</span><span class="sxs-lookup"><span data-stu-id="df1ef-183">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="troubleshoot-advanced-recovery-companion"></a><span data-ttu-id="df1ef-184">疑難排解 Advanced Recovery 附屬</span><span class="sxs-lookup"><span data-stu-id="df1ef-184">Troubleshoot Advanced Recovery Companion</span></span>

1. <span data-ttu-id="df1ef-185">嘗試快閃之前，請確定您的裝置已向40% 或更高的費用。</span><span class="sxs-lookup"><span data-stu-id="df1ef-185">Ensure your device is charged to 40% or more before attempting to flash.</span></span>

2. <span data-ttu-id="df1ef-186">檢查您的裝置是否已解除鎖定。</span><span class="sxs-lookup"><span data-stu-id="df1ef-186">Check your device is unlocked.</span></span>

1. <span data-ttu-id="df1ef-187">檢查您的裝置是否直接插入主機電腦，而不是中樞。</span><span class="sxs-lookup"><span data-stu-id="df1ef-187">Check your device is plugged directly into the host PC, not a hub.</span></span>

1. <span data-ttu-id="df1ef-188">如果您的裝置未在通用序列匯流排驅動程式下顯示為 HoloLens/HoloLens 復原裝置，請檢查：</span><span class="sxs-lookup"><span data-stu-id="df1ef-188">If your device is not showing as a HoloLens/HoloLens Recovery device under Universal Serial Bus Drivers, check:</span></span>
    1. <span data-ttu-id="df1ef-189">作為 Qualcomm HS-USB 裝置的 **埠**</span><span class="sxs-lookup"><span data-stu-id="df1ef-189">**Ports**, as a Qualcomm HS-USB device</span></span>
    1.   <span data-ttu-id="df1ef-190">**其他裝置**（作為 QUSB_BULK 裝置）-您的主機電腦缺少偵測 HoloLens 所需的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="df1ef-190">**Other Devices**, as a QUSB_BULK device - your host PC is missing the necessary drivers to detect your HoloLens.</span></span> <span data-ttu-id="df1ef-191">以滑鼠右鍵按一下並選取 [更新驅動程式]，並在線上搜尋驅動程式，或[在 Windows Update 設定中檢查選用的更新](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674)。</span><span class="sxs-lookup"><span data-stu-id="df1ef-191">Right click and select Update Driver and search for drivers online or [check Optional Updates in your Windows Update settings](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674).</span></span> <span data-ttu-id="df1ef-192">下載驅動程式之後，ARC 應該可以偵測到它。</span><span class="sxs-lookup"><span data-stu-id="df1ef-192">After the driver is downloaded, ARC should be able to detect it.</span></span>
 
1. <span data-ttu-id="df1ef-193">如果 ARC 偵測不到您的裝置，請確定您可以透過電腦上的檔案總管連接到您的裝置。</span><span class="sxs-lookup"><span data-stu-id="df1ef-193">If ARC does not detect your device, ensure that you can connect to your device via File Explorer on your PC.</span></span> <span data-ttu-id="df1ef-194">如果您無法;</span><span class="sxs-lookup"><span data-stu-id="df1ef-194">If you cannot;</span></span>

    1.  <span data-ttu-id="df1ef-195">您的裝置可能會有停用該連線的 USB 原則。</span><span class="sxs-lookup"><span data-stu-id="df1ef-195">It is possible that your device may have USB policies that disable that connection.</span></span> <span data-ttu-id="df1ef-196">若是如此，請嘗試 [手動閃爍模式](hololens-recovery.md#manual-procedure)。</span><span class="sxs-lookup"><span data-stu-id="df1ef-196">If so, try [Manual Flashing mode](hololens-recovery.md#manual-procedure).</span></span>
    2.  <span data-ttu-id="df1ef-197">如果沒有原則，請嘗試不同的 USB 纜線。</span><span class="sxs-lookup"><span data-stu-id="df1ef-197">If there are no policies, try a different USB cable.</span></span>

1. <span data-ttu-id="df1ef-198">檢查您的裝置是否未顯示 [1-3-5 LED 模式](hololens2-setup.md#lights-to-indicate-problems)。</span><span class="sxs-lookup"><span data-stu-id="df1ef-198">Check that your device doesn't display a [1-3-5-LED pattern](hololens2-setup.md#lights-to-indicate-problems).</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="df1ef-199">下載 ARC 而不使用 app store</span><span class="sxs-lookup"><span data-stu-id="df1ef-199">Download ARC without using the app store</span></span>

<span data-ttu-id="df1ef-200">如果 it 環境防止使用 Windows Store 應用程式或限制零售商店的存取權，it 系統管理員可以透過「離線」部署路徑來提供此應用程式。</span><span class="sxs-lookup"><span data-stu-id="df1ef-200">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="df1ef-201">IT 系統管理員也可以透過 System Center Configuration Manager (SCCM) 或 Intune 來散發此應用程式。</span><span class="sxs-lookup"><span data-stu-id="df1ef-201">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="df1ef-202">本指南著重于先進的復原，但此程式也可以用於其他「離線」應用程式。</span><span class="sxs-lookup"><span data-stu-id="df1ef-202">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="df1ef-203">遵循下列步驟來啟用部署路徑：</span><span class="sxs-lookup"><span data-stu-id="df1ef-203">Follow these steps to enable the deployment path:</span></span>

1. <span data-ttu-id="df1ef-204">移至[商務用 Microsoft Store](https://businessstore.microsoft.com) ，並使用 Azure Active Directory 身分識別登入。</span><span class="sxs-lookup"><span data-stu-id="df1ef-204">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="df1ef-205">移至 [**管理–設定**]。</span><span class="sxs-lookup"><span data-stu-id="df1ef-205">Go to **Manage – Settings**.</span></span> <span data-ttu-id="df1ef-206">開啟 [在 **購物體驗** 時 **顯示離線應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="df1ef-206">Turn on **Show offline apps** under **Shopping experience**.</span></span>

1. <span data-ttu-id="df1ef-207">移至 [ **為我的群組購物**]，並搜尋 [**_Advanced Recovery 附屬_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)。</span><span class="sxs-lookup"><span data-stu-id="df1ef-207">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>

1. <span data-ttu-id="df1ef-208">將 [**授權類型**] 變更為 [ **_離線_]*，然後選取 _*[管理**]。</span><span class="sxs-lookup"><span data-stu-id="df1ef-208">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>

1. <span data-ttu-id="df1ef-209">在 **[下載套件以供離線使用**] 底下，選取第二個藍色的 [ **下載** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="df1ef-209">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="df1ef-210">請確定副檔名是 *.appxbundle*。</span><span class="sxs-lookup"><span data-stu-id="df1ef-210">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="df1ef-211">在這個階段中，如果桌上型電腦可以存取網際網路，請按兩下套件以安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="df1ef-211">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="df1ef-212">如果目的地電腦沒有網際網路連線能力，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="df1ef-212">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="df1ef-213">選取未編碼的授權，然後選取 [ **產生授權**]。</span><span class="sxs-lookup"><span data-stu-id="df1ef-213">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="df1ef-214">在 [ **必要 framework**] 下，選取 [ **下載**]。</span><span class="sxs-lookup"><span data-stu-id="df1ef-214">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="df1ef-215">使用 DISM 以相依性和授權套用封裝。</span><span class="sxs-lookup"><span data-stu-id="df1ef-215">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="df1ef-216">從系統管理員命令提示字元中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="df1ef-216">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > <span data-ttu-id="df1ef-217">這個程式碼範例中的版本號碼可能不符合目前可用的版本。</span><span class="sxs-lookup"><span data-stu-id="df1ef-217">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="df1ef-218">您也可能選擇的下載位置與範例中的不同。</span><span class="sxs-lookup"><span data-stu-id="df1ef-218">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="df1ef-219">視需要對命令進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="df1ef-219">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="df1ef-220">當您想要使用「高階復原」隨附于離線安裝 FFU 時，下載 flash 映射可能會很有用。</span><span class="sxs-lookup"><span data-stu-id="df1ef-220">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="df1ef-221">[**下載 HoloLens 2 的目前映射**](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="df1ef-221">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>


<span data-ttu-id="df1ef-222">其他資源：</span><span class="sxs-lookup"><span data-stu-id="df1ef-222">Other resources:</span></span>
- [<span data-ttu-id="df1ef-223">散發離線 App</span><span class="sxs-lookup"><span data-stu-id="df1ef-223">Distribute offline apps</span></span>](/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="df1ef-224">DISM 應用程式封裝 ( .appx 或 .appxbundle) 服務命令列選項</span><span class="sxs-lookup"><span data-stu-id="df1ef-224">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
