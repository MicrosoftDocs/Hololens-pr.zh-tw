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
ms.openlocfilehash: be33eb5d06ee7d63f1f598792ff75605b0eb4424
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923630"
---
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="a36a7-104">重新開機、重設或復原 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="a36a7-104">Restart, reset, or recover HoloLens 2</span></span>

>[!IMPORTANT]
> <span data-ttu-id="a36a7-105">在開始進行任何疑難排解程式之前，請確定您的裝置必須支付 **20% 到 40%** 的電池容量（如果可能的話）。</span><span class="sxs-lookup"><span data-stu-id="a36a7-105">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="a36a7-106">位於 [電源] 按鈕下的 [電池指標燈](hololens2-setup.md#lights-that-indicate-the-battery-level) 是快速驗證電池容量，而不需要登入裝置的方式。</span><span class="sxs-lookup"><span data-stu-id="a36a7-106">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<span data-ttu-id="a36a7-107">使用 HoloLens 2 隨附的 [充電器和 USB 類型 C 纜線](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) ，因為這是向裝置收費的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="a36a7-107">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="a36a7-108">充電器在 2A) 提供 power (9V 的18W。</span><span class="sxs-lookup"><span data-stu-id="a36a7-108">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="a36a7-109">在裝置處於待命狀態的情況下，HoloLens 2 裝置可使用所提供的牆充電器，在65分鐘內將電池充電以填滿。</span><span class="sxs-lookup"><span data-stu-id="a36a7-109">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="a36a7-110">如果無法使用這些附屬應用程式，請確定提供的充電可支援至少15W 的電源。</span><span class="sxs-lookup"><span data-stu-id="a36a7-110">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="a36a7-111">可能的話，請避免使用電腦透過 USB 收取裝置的費用，這會很慢。</span><span class="sxs-lookup"><span data-stu-id="a36a7-111">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="a36a7-112">如果裝置正確開機且正在執行，有三種方式可以檢查電池計量等級：</span><span class="sxs-lookup"><span data-stu-id="a36a7-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="a36a7-113">從 HoloLens 裝置 UI 的主功能表。</span><span class="sxs-lookup"><span data-stu-id="a36a7-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="a36a7-114">查看電源按鈕 (接近電源按鈕有40% 的費用，您應該會看到至少兩個穩固的 Led) 。</span><span class="sxs-lookup"><span data-stu-id="a36a7-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="a36a7-115">當裝置充電時，電池指示燈會亮起以指出目前的收費層級。</span><span class="sxs-lookup"><span data-stu-id="a36a7-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="a36a7-116">最後一個光線會淡入和淡出以表示主動充電。</span><span class="sxs-lookup"><span data-stu-id="a36a7-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="a36a7-117">當 HoloLens 開啟時，電池指示器會以五個增量顯示電池計量。</span><span class="sxs-lookup"><span data-stu-id="a36a7-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="a36a7-118">當您只開啟五個燈的其中一個時，電池計量低於20%。</span><span class="sxs-lookup"><span data-stu-id="a36a7-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="a36a7-119">如果電池計量偏低，而您嘗試開啟裝置，則會短暫閃爍一次，然後移出。</span><span class="sxs-lookup"><span data-stu-id="a36a7-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="a36a7-120">在您的主機電腦上，開啟 **檔案總管** ，然後在這部 **電腦** 的左側尋找您的 HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="a36a7-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="a36a7-121">在裝置上按一下滑鼠右鍵，然後選取 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="a36a7-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="a36a7-122">對話方塊會顯示電池計量的等級。</span><span class="sxs-lookup"><span data-stu-id="a36a7-122">A dialog box will show the battery charge level.</span></span>

   ![顯示電池變更層級的 HoloLens 2 屬性畫面](images/ResetRecovery2.png)

<span data-ttu-id="a36a7-124">如果裝置無法開機至 [啟動] 功能表，請注意主機電腦上的 LED 外觀和裝置列舉。</span><span class="sxs-lookup"><span data-stu-id="a36a7-124">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="a36a7-125">然後遵循 [疑難排解指南](hololens-troubleshooting.md)。</span><span class="sxs-lookup"><span data-stu-id="a36a7-125">Then follow the [troubleshooting guide](hololens-troubleshooting.md).</span></span> <span data-ttu-id="a36a7-126">如果裝置的狀態不符合疑難排解指南中所列的任何狀態，請執行 [硬重設](hololens-recovery.md#hard-reset-procedure) 程式，將裝置連接到電源供應器，而不是您的主機電腦。</span><span class="sxs-lookup"><span data-stu-id="a36a7-126">If the state of the device doesn't match any of the states listed in the troubleshooting guide, perform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="a36a7-127">請等候至少一小時讓裝置向您收費。</span><span class="sxs-lookup"><span data-stu-id="a36a7-127">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="a36a7-128">重設裝置</span><span class="sxs-lookup"><span data-stu-id="a36a7-128">Reset the device</span></span>

<span data-ttu-id="a36a7-129">在某些情況下，您可能必須手動重設裝置，而不需要使用軟體 UI。</span><span class="sxs-lookup"><span data-stu-id="a36a7-129">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="a36a7-130">標準程式</span><span class="sxs-lookup"><span data-stu-id="a36a7-130">Standard procedure</span></span>

1. <span data-ttu-id="a36a7-131">拔下類型 C 纜線，以中斷裝置與電源供應器或主機電腦的連線。</span><span class="sxs-lookup"><span data-stu-id="a36a7-131">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="a36a7-132">按住 **電源** 按鈕15秒。</span><span class="sxs-lookup"><span data-stu-id="a36a7-132">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="a36a7-133">所有 Led 都應該關閉。</span><span class="sxs-lookup"><span data-stu-id="a36a7-133">All LEDs should be off.</span></span>

3. <span data-ttu-id="a36a7-134">等候2-3 秒，然後按下 **電源** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a36a7-134">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="a36a7-135">接近電源按鈕的 Led 會亮起，且裝置將開始啟動。</span><span class="sxs-lookup"><span data-stu-id="a36a7-135">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="a36a7-136">將裝置連接到主機電腦，然後開啟裝置管理員。</span><span class="sxs-lookup"><span data-stu-id="a36a7-136">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="a36a7-137">針對 Windows 10 的 (，按下 **Windows** 鍵，然後按 **X** 鍵，然後選取 [ **裝置管理員**]。 ) 確定裝置已正確列舉為 *Microsoft HoloLens* ，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="a36a7-137">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery devive manager](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="a36a7-139">硬重設程式</span><span class="sxs-lookup"><span data-stu-id="a36a7-139">Hard-reset procedure</span></span>

<span data-ttu-id="a36a7-140">如果標準重設程式無法運作，請使用硬重設程式：</span><span class="sxs-lookup"><span data-stu-id="a36a7-140">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="a36a7-141">拔下類型 C 纜線，以中斷裝置與電源供應器或主機電腦的連線。</span><span class="sxs-lookup"><span data-stu-id="a36a7-141">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="a36a7-142">按住音量的  +  **電源** 按鈕15秒。</span><span class="sxs-lookup"><span data-stu-id="a36a7-142">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="a36a7-143">裝置會自動重新開機。</span><span class="sxs-lookup"><span data-stu-id="a36a7-143">The device will automatically restart.</span></span>

4. <span data-ttu-id="a36a7-144">將裝置連線到主機電腦。</span><span class="sxs-lookup"><span data-stu-id="a36a7-144">Connect the device to the host PC.</span></span>

5. <span data-ttu-id="a36a7-145">開啟裝置管理員 (Windows 10 按下 **Windows** 鍵，然後選取 [ **X** ] 鍵，然後選取 [ **裝置管理員**) ]。</span><span class="sxs-lookup"><span data-stu-id="a36a7-145">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="a36a7-146">請確定裝置已正確列舉為 *Microsoft HoloLens* ，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="a36a7-146">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery device maanger 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="a36a7-148">清除重新刷新裝置</span><span class="sxs-lookup"><span data-stu-id="a36a7-148">Clean-reflash the device</span></span>

<span data-ttu-id="a36a7-149">在特殊情況下，您可能必須「清理」 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="a36a7-149">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="a36a7-150">請注意，重新刷新不應該影響下列問題：</span><span class="sxs-lookup"><span data-stu-id="a36a7-150">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="a36a7-151">顯示色彩一致性</span><span class="sxs-lookup"><span data-stu-id="a36a7-151">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="a36a7-152">使用音效開機但沒有顯示輸出</span><span class="sxs-lookup"><span data-stu-id="a36a7-152">Booting with sound but no display output</span></span>
- [<span data-ttu-id="a36a7-153">1-3-5-LED 模式</span><span class="sxs-lookup"><span data-stu-id="a36a7-153">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="a36a7-154">過熱</span><span class="sxs-lookup"><span data-stu-id="a36a7-154">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="a36a7-155">作業系統損毀 (與應用程式損毀不同) </span><span class="sxs-lookup"><span data-stu-id="a36a7-155">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="a36a7-156">重新刷新裝置的方式有兩種。</span><span class="sxs-lookup"><span data-stu-id="a36a7-156">There are two ways to reflash the device.</span></span> <span data-ttu-id="a36a7-157">針對這兩種情況，您必須先 [從 Windows 市集中安裝 Advanced Recovery 附隨](https://www.microsoft.com/store/productId/9P74Z35SFRS8)。</span><span class="sxs-lookup"><span data-stu-id="a36a7-157">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="a36a7-158">如果您重新刷新您的裝置，將會清除您的所有個人資料、應用程式和設定，包括 TPM 重設資訊。</span><span class="sxs-lookup"><span data-stu-id="a36a7-158">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="a36a7-159">根據預設，Advanced Recovery 附屬設定為下載最新的功能發行組建，請參閱這裡以閱讀我們的 [版本](hololens-release-notes.md#) 資訊，以瞭解最新的功能版本。</span><span class="sxs-lookup"><span data-stu-id="a36a7-159">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="a36a7-160">若要取得最新的 HoloLens 2 Full Flash Update (FFU) 套件以透過 Advanced Recovery 隨附重新刷新您的裝置，請 [按一下這裡下載最新的每月 HoloLens 2 映射](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="a36a7-160">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="a36a7-161">此版本是最新正式推出的組建。</span><span class="sxs-lookup"><span data-stu-id="a36a7-161">This version is the latest generally available build.</span></span>

<span data-ttu-id="a36a7-162">開始重新刷新程式之前，請確定已在 Windows 10 電腦上安裝並執行應用程式，並已準備好偵測裝置。</span><span class="sxs-lookup"><span data-stu-id="a36a7-162">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="a36a7-163">此外，也請確定您的 HoloLens 最少支付40% 的費用。</span><span class="sxs-lookup"><span data-stu-id="a36a7-163">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![HoloLens 2 乾淨重新刷新螢幕擷取畫面](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="a36a7-165">一般程式</span><span class="sxs-lookup"><span data-stu-id="a36a7-165">Normal procedure</span></span>

1. <span data-ttu-id="a36a7-166">當 HoloLens 裝置正在執行時，請將它連接到您先前開啟 Advanced Recovery 附屬應用程式的 Windows 10 電腦。</span><span class="sxs-lookup"><span data-stu-id="a36a7-166">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="a36a7-167">系統會自動偵測裝置，而且 Advanced Recovery 附屬應用程式 UI 將會啟動更新程式：</span><span class="sxs-lookup"><span data-stu-id="a36a7-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 clean 重新刷新初始畫面](images/ARC2.png)

3. <span data-ttu-id="a36a7-169">在 Advanced Recovery 附屬應用程式 UI 中選取 HoloLens 2 裝置，並遵循指示來完成重新刷新。</span><span class="sxs-lookup"><span data-stu-id="a36a7-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="a36a7-170">手動程式</span><span class="sxs-lookup"><span data-stu-id="a36a7-170">Manual procedure</span></span>

<span data-ttu-id="a36a7-171">如果 HoloLens 2 無法正確啟動，或如果 Advanced Recovery 附屬無法偵測到裝置，您可能需要讓裝置進入修復模式：</span><span class="sxs-lookup"><span data-stu-id="a36a7-171">If the HoloLens 2 doesn't start correctly or if Advanced Recovery Companion cannot detect the device, you may need to put the device into recovery mode:</span></span>

1. <span data-ttu-id="a36a7-172">拔下類型 C 纜線，以中斷裝置與電源供應器或主機電腦的連線。</span><span class="sxs-lookup"><span data-stu-id="a36a7-172">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="a36a7-173">按住 **電源** 按鈕15秒。</span><span class="sxs-lookup"><span data-stu-id="a36a7-173">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="a36a7-174">所有 Led 都應該關閉。</span><span class="sxs-lookup"><span data-stu-id="a36a7-174">All LEDs should turn off.</span></span>

3. <span data-ttu-id="a36a7-175">按下 **音量** 按鈕時，請按下並放開 **電源** 按鈕以啟動裝置。</span><span class="sxs-lookup"><span data-stu-id="a36a7-175">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="a36a7-176">等候15秒，然後放開 **音量** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a36a7-176">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="a36a7-177">只有五個 Led 的中間 LED 會亮著。</span><span class="sxs-lookup"><span data-stu-id="a36a7-177">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="a36a7-178">將裝置連接到主機電腦，然後開啟裝置管理員。</span><span class="sxs-lookup"><span data-stu-id="a36a7-178">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="a36a7-179"> (Windows 10 按下 **Windows** 鍵，然後選取 [ **X** ] 鍵，然後選取 [ **裝置管理員**]。 ) 確認裝置已正確列舉為 Microsoft HoloLens，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="a36a7-179">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="a36a7-181">系統會自動偵測裝置，而且 Advanced Recovery 附屬應用程式 UI 將會啟動更新程式：</span><span class="sxs-lookup"><span data-stu-id="a36a7-181">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 clean 重新刷新畫面](images/ARC2.png)

6. <span data-ttu-id="a36a7-183">在 Advanced Recovery 附屬應用程式 UI 中選取 HoloLens 2 裝置，然後遵循指示來完成重新刷新。</span><span class="sxs-lookup"><span data-stu-id="a36a7-183">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="troubleshoot-advanced-recovery-companion"></a><span data-ttu-id="a36a7-184">疑難排解 Advanced Recovery 附屬</span><span class="sxs-lookup"><span data-stu-id="a36a7-184">Troubleshoot Advanced Recovery Companion</span></span>

1. <span data-ttu-id="a36a7-185">嘗試快閃之前，請確定您的裝置已向40% 或更高的費用。</span><span class="sxs-lookup"><span data-stu-id="a36a7-185">Ensure your device is charged to 40% or more before attempting to flash.</span></span>

2. <span data-ttu-id="a36a7-186">檢查您的裝置是否已解除鎖定。</span><span class="sxs-lookup"><span data-stu-id="a36a7-186">Check that your device is unlocked.</span></span>

3. <span data-ttu-id="a36a7-187">如果 ARC 偵測不到您的裝置，請確定您可以透過電腦上的檔案總管連接到您的裝置。</span><span class="sxs-lookup"><span data-stu-id="a36a7-187">If ARC does not detect your device, ensure that you can connect to your device via File Explorer on your PC.</span></span> <span data-ttu-id="a36a7-188">如果您無法;</span><span class="sxs-lookup"><span data-stu-id="a36a7-188">If you cannot;</span></span>

    1.  <span data-ttu-id="a36a7-189">您的裝置可能會有停用該連線的 USB 原則。</span><span class="sxs-lookup"><span data-stu-id="a36a7-189">It is possible that your device may have USB policies that disable that connection.</span></span> <span data-ttu-id="a36a7-190">若是如此，請嘗試 [手動閃爍模式](hololens-recovery.md#manual-procedure)。</span><span class="sxs-lookup"><span data-stu-id="a36a7-190">If so, try [Manual Flashing mode](hololens-recovery.md#manual-procedure).</span></span>
    2.  <span data-ttu-id="a36a7-191">如果沒有原則，請嘗試不同的 USB 纜線。</span><span class="sxs-lookup"><span data-stu-id="a36a7-191">If there are no policies, try a different USB cable.</span></span>

1. <span data-ttu-id="a36a7-192">檢查您的裝置是否未顯示 [1-3-5 LED 模式](hololens2-setup.md#lights-to-indicate-problems)。</span><span class="sxs-lookup"><span data-stu-id="a36a7-192">Check that your device doesn't display a [1-3-5-LED pattern](hololens2-setup.md#lights-to-indicate-problems).</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="a36a7-193">下載 ARC 而不使用 app store</span><span class="sxs-lookup"><span data-stu-id="a36a7-193">Download ARC without using the app store</span></span>

<span data-ttu-id="a36a7-194">如果 IT 環境防止使用 Windows Store 應用程式或限制零售商店的存取權，IT 系統管理員可以透過「離線」部署路徑，讓此應用程式可供使用。</span><span class="sxs-lookup"><span data-stu-id="a36a7-194">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="a36a7-195">IT 系統管理員也可以透過 System Center 設定管理員 (SCCM) 或 Intune 發佈此應用程式。</span><span class="sxs-lookup"><span data-stu-id="a36a7-195">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="a36a7-196">本指南著重于先進的復原，但此程式也可以用於其他「離線」應用程式。</span><span class="sxs-lookup"><span data-stu-id="a36a7-196">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="a36a7-197">遵循下列步驟來啟用部署路徑：</span><span class="sxs-lookup"><span data-stu-id="a36a7-197">Follow these steps to enable the deployment path:</span></span>

1. <span data-ttu-id="a36a7-198">移至 [商務用 Microsoft Store](https://businessstore.microsoft.com) ，並使用 Azure Active Directory 身分識別登入。</span><span class="sxs-lookup"><span data-stu-id="a36a7-198">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="a36a7-199">移至 [ **管理-設定**]。</span><span class="sxs-lookup"><span data-stu-id="a36a7-199">Go to **Manage – Settings**.</span></span> <span data-ttu-id="a36a7-200">開啟 [在 **購物體驗** 時 **顯示離線應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="a36a7-200">Turn on **Show offline apps** under **Shopping experience**.</span></span>

1. <span data-ttu-id="a36a7-201">移至 [ **為我的群組購物**]，並搜尋 [**_Advanced Recovery 附屬_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)。</span><span class="sxs-lookup"><span data-stu-id="a36a7-201">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>

1. <span data-ttu-id="a36a7-202">將 [**授權類型**] 變更為 [ **_離線_]*，然後選取 _*[管理**]。</span><span class="sxs-lookup"><span data-stu-id="a36a7-202">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>

1. <span data-ttu-id="a36a7-203">在 **[下載套件以供離線使用**] 底下，選取第二個藍色的 [ **下載** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a36a7-203">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="a36a7-204">請確定副檔名是 *.appxbundle*。</span><span class="sxs-lookup"><span data-stu-id="a36a7-204">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="a36a7-205">在這個階段中，如果桌上型電腦可以存取網際網路，請按兩下套件以安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="a36a7-205">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="a36a7-206">如果目的地電腦沒有網際網路連線能力，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a36a7-206">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="a36a7-207">選取未編碼的授權，然後選取 [ **產生授權**]。</span><span class="sxs-lookup"><span data-stu-id="a36a7-207">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="a36a7-208">在 [ **必要 framework**] 下，選取 [ **下載**]。</span><span class="sxs-lookup"><span data-stu-id="a36a7-208">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="a36a7-209">使用 DISM 以相依性和授權套用封裝。</span><span class="sxs-lookup"><span data-stu-id="a36a7-209">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="a36a7-210">從系統管理員命令提示字元中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a36a7-210">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > <span data-ttu-id="a36a7-211">這個程式碼範例中的版本號碼可能不符合目前可用的版本。</span><span class="sxs-lookup"><span data-stu-id="a36a7-211">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="a36a7-212">您也可能選擇的下載位置與範例中的不同。</span><span class="sxs-lookup"><span data-stu-id="a36a7-212">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="a36a7-213">視需要對命令進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="a36a7-213">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="a36a7-214">當您想要使用「高階復原」隨附于離線安裝 FFU 時，下載 flash 映射可能會很有用。</span><span class="sxs-lookup"><span data-stu-id="a36a7-214">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="a36a7-215">[**下載 HoloLens 2 的目前映射**](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="a36a7-215">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>


<span data-ttu-id="a36a7-216">其他資源：</span><span class="sxs-lookup"><span data-stu-id="a36a7-216">Other resources:</span></span>
- [<span data-ttu-id="a36a7-217">散發離線 App</span><span class="sxs-lookup"><span data-stu-id="a36a7-217">Distribute offline apps</span></span>](/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="a36a7-218">DISM 應用程式封裝 ( .appx 或 .appxbundle) 服務命令列選項</span><span class="sxs-lookup"><span data-stu-id="a36a7-218">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
