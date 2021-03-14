---
title: 重新啟動、重設或復原 HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
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
ms.openlocfilehash: b5b9568bab5afebe4ac3e9d57645c18837c71cb6
ms.sourcegitcommit: fdae5b561d56d3d4e62da4db15f07bc10249398a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2021
ms.locfileid: "11408423"
---
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="286d1-104">重新啟動、重設或復原 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="286d1-104">Restart, reset, or recover HoloLens 2</span></span>

## <a name="charge-the-device"></a><span data-ttu-id="286d1-105">為裝置充電</span><span class="sxs-lookup"><span data-stu-id="286d1-105">Charge the device</span></span>

<span data-ttu-id="286d1-106">開始進行任何疑難排解程序之前，如果可以，請先確認您的裝置已具備 20% 到40% 的電量。</span><span class="sxs-lookup"><span data-stu-id="286d1-106">Before you start any troubleshooting procedure, make sure that your device is charged to 20 to 40 percent of battery capacity if possible.</span></span> <span data-ttu-id="286d1-107">使用在 HoloLens 2 裝置隨附的[充電器和 USB 類型-C 型纜線](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1)。</span><span class="sxs-lookup"><span data-stu-id="286d1-107">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that come with the HoloLens 2 device.</span></span> <span data-ttu-id="286d1-108">裝置附帶的電源供應器和 USB-C-to-C 纜線是為 HoloLens 2 充電的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="286d1-108">The power supply and USB-C-to-C cable that come with the device are the best way to charge your HoloLens 2.</span></span> <span data-ttu-id="286d1-109">電源供應器提供 18W 的電力 (2A 時為 9V)。</span><span class="sxs-lookup"><span data-stu-id="286d1-109">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="286d1-110">使用提供的壁掛式充電器，HoloLens 2 裝置可以在裝置處於待機狀態時，在 65 分鐘內將電量充滿。</span><span class="sxs-lookup"><span data-stu-id="286d1-110">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="286d1-111">如果您無法使用這些附件，請確認提供的充電器是可以使用且可支援至少 15 瓦的電源。</span><span class="sxs-lookup"><span data-stu-id="286d1-111">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="286d1-112">如果可以，請避免使用電腦透過 USB 為裝置充電 (速度慢)。</span><span class="sxs-lookup"><span data-stu-id="286d1-112">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="286d1-113">如果裝置已正確啟動並運行，則可以使用三種方法來檢查電池電量等級:</span><span class="sxs-lookup"><span data-stu-id="286d1-113">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="286d1-114">從 HoloLens 裝置 UI 的主要功能表。</span><span class="sxs-lookup"><span data-stu-id="286d1-114">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="286d1-115">檢視靠近電源按鈕的 LED (若具有 40% 的電量，您應至少看到兩個亮起的 LED 燈)。</span><span class="sxs-lookup"><span data-stu-id="286d1-115">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDS).</span></span>
    - <span data-ttu-id="286d1-116">裝置充電時，電池指示燈會亮起，指出目前的電量。</span><span class="sxs-lookup"><span data-stu-id="286d1-116">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="286d1-117">最後一個燈號會淡入和淡出以表示正在充電。</span><span class="sxs-lookup"><span data-stu-id="286d1-117">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="286d1-118">當您的 HoloLens 開啟時，電池指示器會以五個增量來顯示電池電量。</span><span class="sxs-lookup"><span data-stu-id="286d1-118">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="286d1-119">五個燈號中只有一個亮起時，表示電池電量低於 20%。</span><span class="sxs-lookup"><span data-stu-id="286d1-119">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="286d1-120">如果電池電量嚴重偏低，而您嘗試開啟裝置，就會有一個燈號短暫閃爍，然後熄滅。</span><span class="sxs-lookup"><span data-stu-id="286d1-120">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="286d1-121">在您的主機電腦上，開啟 **File Explorer 文件資源管理** 器，然後在**This PC 這台電腦** 的左方, 尋找您的 HoloLens 2 裝置.</span><span class="sxs-lookup"><span data-stu-id="286d1-121">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="286d1-122">以滑鼠右鍵按一下裝置，並選取 **[內容]**。</span><span class="sxs-lookup"><span data-stu-id="286d1-122">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="286d1-123">對話方塊會隨即顯示電池電量等級。</span><span class="sxs-lookup"><span data-stu-id="286d1-123">A dialog box will show the battery charge level.</span></span>

   ![HoloLens 2 屬性畫面會顯示電池電量等級](images/ResetRecovery2.png)

<span data-ttu-id="286d1-125">如果裝置無法引導至 [啟動] 功能表，請注意主機電腦上的 LED 外觀和裝置枚舉。</span><span class="sxs-lookup"><span data-stu-id="286d1-125">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="286d1-126">然後按照 [疑難排解指南](https://docs.microsoft.com/hololens/hololens-troubleshooting)。</span><span class="sxs-lookup"><span data-stu-id="286d1-126">Then follow the [troubleshooting guide](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="286d1-127">如果裝置狀態不符合疑難排解指南中所列的任何狀態，請將裝置連線至電源執行[硬重設程序](hololens-recovery.md#hard-reset-procedure) ，而不是連接到您的主機電腦。</span><span class="sxs-lookup"><span data-stu-id="286d1-127">If the state of the device doesn't match any of the states listed in the troubleshooting guide, preform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="286d1-128">請至少等候一個小時，讓裝置充電。</span><span class="sxs-lookup"><span data-stu-id="286d1-128">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="286d1-129">重設裝置</span><span class="sxs-lookup"><span data-stu-id="286d1-129">Reset the device</span></span>

<span data-ttu-id="286d1-130">在某些情況下，您可能需要手動重設裝置，而不需要使用軟體 UI。</span><span class="sxs-lookup"><span data-stu-id="286d1-130">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="286d1-131">標準程序</span><span class="sxs-lookup"><span data-stu-id="286d1-131">Standard procedure</span></span>

1. <span data-ttu-id="286d1-132">取下 Type-C 連接線，以中斷裝置和電源或主機電腦的連線。</span><span class="sxs-lookup"><span data-stu-id="286d1-132">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="286d1-133">按住**電源**按鈕 15 秒。</span><span class="sxs-lookup"><span data-stu-id="286d1-133">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="286d1-134">所有的 LED 均應關閉。</span><span class="sxs-lookup"><span data-stu-id="286d1-134">All LEDs should be off.</span></span>

3. <span data-ttu-id="286d1-135">等待2-3 秒，然後按一下 **電源** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="286d1-135">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="286d1-136">靠近電源按鈕的 LED 燈會亮起，而裝置將開始啟動。</span><span class="sxs-lookup"><span data-stu-id="286d1-136">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="286d1-137">將裝置連線到主機電腦，然後開啟 [裝置管理員]。</span><span class="sxs-lookup"><span data-stu-id="286d1-137">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="286d1-138">(針對 Windows 10，請按 **Windows** 鍵，再按 **X** 鍵，然後選取 **裝置管理員**。) 確認裝置枚舉正確為 *Microsoft HoloLens* 如以下影像所示:</span><span class="sxs-lookup"><span data-stu-id="286d1-138">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery 裝置管理員](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="286d1-140">硬重設程序</span><span class="sxs-lookup"><span data-stu-id="286d1-140">Hard-reset procedure</span></span>

<span data-ttu-id="286d1-141">如果標準重設程序無法運作，請使用硬重設程序:</span><span class="sxs-lookup"><span data-stu-id="286d1-141">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="286d1-142">取下 Type-C 連接線，以中斷裝置和電源或主機電腦的連線。</span><span class="sxs-lookup"><span data-stu-id="286d1-142">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="286d1-143">按住 **調低音量** + **電源** 按鈕 15 秒。</span><span class="sxs-lookup"><span data-stu-id="286d1-143">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="286d1-144">裝置會自動重新啟動。</span><span class="sxs-lookup"><span data-stu-id="286d1-144">The device will automatically restart.</span></span>

4. <span data-ttu-id="286d1-145">將裝置連接到主機電腦。</span><span class="sxs-lookup"><span data-stu-id="286d1-145">Connect the device to the host PC.</span></span>
5. <span data-ttu-id="286d1-146">開啟 [裝置管理員] （如果是 Windows 10，請按 **Windows** 鍵，然後按 **X** 鍵，並選取 **[裝置管理員]**）。</span><span class="sxs-lookup"><span data-stu-id="286d1-146">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="286d1-147">請確認裝置枚舉正確為 *Microsoft HoloLens*，如下列影像所示：</span><span class="sxs-lookup"><span data-stu-id="286d1-147">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery 裝置管理員 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="286d1-149">乾淨重新快閃刷新裝置</span><span class="sxs-lookup"><span data-stu-id="286d1-149">Clean-reflash the device</span></span>

<span data-ttu-id="286d1-150">在特別的情況下，您可能需要乾淨快閃刷新 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="286d1-150">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="286d1-151">請注意，乾淨重新快閃刷新不會影響下列問題：</span><span class="sxs-lookup"><span data-stu-id="286d1-151">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="286d1-152">顯示色彩一致性</span><span class="sxs-lookup"><span data-stu-id="286d1-152">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="286d1-153">使用音效啟動但沒有顯示輸出</span><span class="sxs-lookup"><span data-stu-id="286d1-153">Booting with sound but no display output</span></span>
- [<span data-ttu-id="286d1-154">1-3-5-LED 模式</span><span class="sxs-lookup"><span data-stu-id="286d1-154">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="286d1-155">過熱</span><span class="sxs-lookup"><span data-stu-id="286d1-155">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="286d1-156">OS 當機（不同於應用程式的當機）</span><span class="sxs-lookup"><span data-stu-id="286d1-156">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="286d1-157">有兩種方法可以快閃刷新裝置。</span><span class="sxs-lookup"><span data-stu-id="286d1-157">There are two ways to reflash the device.</span></span> <span data-ttu-id="286d1-158">針對這兩者，您必須先 [從 Windows 市集中安裝 [進階修復小幫手]](https://www.microsoft.com/store/productId/9P74Z35SFRS8)。</span><span class="sxs-lookup"><span data-stu-id="286d1-158">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="286d1-159">如果快閃刷新裝置，您所有的個人資料、應用程式和設定都會被清除，包含 TPM 重設資訊。</span><span class="sxs-lookup"><span data-stu-id="286d1-159">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="286d1-160">根據預設，[進階修復小幫手] 設定為下載最新的功能版本版本，請查看此處以閱讀我們的[版本資訊](hololens-release-notes.md#)以瞭解最新功能版本。</span><span class="sxs-lookup"><span data-stu-id="286d1-160">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="286d1-161">若要取得最新的 HoloLens 2 完整刷新更新 (FFU) 套件，以透過 [進階修復小幫手] 快閃刷新您的裝置，請按一下此處下載最新的每月 HoloLens 2 影像[。](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="286d1-161">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="286d1-162">此版本是最新的萬用組建。</span><span class="sxs-lookup"><span data-stu-id="286d1-162">This version is the latest generally available build.</span></span>

<span data-ttu-id="286d1-163">在啟動快閃刷新程序前，請確認已在 Windows 10 電腦上安裝並執行該應用程式，並準備好偵測裝置。</span><span class="sxs-lookup"><span data-stu-id="286d1-163">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="286d1-164">另外，請確定您的 HoloLens 的電量至少為40%。</span><span class="sxs-lookup"><span data-stu-id="286d1-164">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![HoloLens 2 乾淨快閃刷新螢幕擷取畫面](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="286d1-166">正常程序</span><span class="sxs-lookup"><span data-stu-id="286d1-166">Normal procedure</span></span>

1. <span data-ttu-id="286d1-167">當 HoloLens 裝置執行時，請將它連線到先前開啟的 Advanced Recovery Companion 應用程式的 Windows 10 電腦。</span><span class="sxs-lookup"><span data-stu-id="286d1-167">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="286d1-168">系統會自動偵測到裝置，而 Advanced Recovery Companion 應用程式 UI 則會開始更新程序：</span><span class="sxs-lookup"><span data-stu-id="286d1-168">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 乾淨快閃刷新初始畫面](images/ARC2.png)

3. <span data-ttu-id="286d1-170">在 Advanced Recovery Companion 應用程式 UI 中選取 HoloLens 2 裝置，並依照指示完成快閃刷新。</span><span class="sxs-lookup"><span data-stu-id="286d1-170">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="286d1-171">手動程序</span><span class="sxs-lookup"><span data-stu-id="286d1-171">Manual procedure</span></span>

<span data-ttu-id="286d1-172">如果 HoloLens2 無法正確啟動，您可能需要將裝置置於修復模式:</span><span class="sxs-lookup"><span data-stu-id="286d1-172">If the HoloLens 2 doesn't start correctly, you may need to put the device into Recovery mode:</span></span>

1. <span data-ttu-id="286d1-173">取下 Type-C 連接線，以中斷裝置和電源或主機電腦的連線。</span><span class="sxs-lookup"><span data-stu-id="286d1-173">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="286d1-174">按住**電源**按鈕 15 秒。</span><span class="sxs-lookup"><span data-stu-id="286d1-174">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="286d1-175">此時應該會關閉所有 LED。</span><span class="sxs-lookup"><span data-stu-id="286d1-175">All LEDs should turn off.</span></span>

3. <span data-ttu-id="286d1-176">按下**調高音量**按鈕時，請按下並放開**電源** 按鈕以啟動裝置。</span><span class="sxs-lookup"><span data-stu-id="286d1-176">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="286d1-177">請等候 15 秒，然後再放開 **調高音量**按鈕。</span><span class="sxs-lookup"><span data-stu-id="286d1-177">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="286d1-178">只有中間的五個 LED 燈會亮起。</span><span class="sxs-lookup"><span data-stu-id="286d1-178">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="286d1-179">將裝置連線到主機電腦，並開啟 [裝置管理員]。</span><span class="sxs-lookup"><span data-stu-id="286d1-179">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="286d1-180">(針對 Windows 10，請按 **Windows** 鍵，再按 **X** 鍵，然後選取 **裝置管理員**。) 確認裝置枚舉正確為 Microsoft HoloLens 如以下影像所示:</span><span class="sxs-lookup"><span data-stu-id="286d1-180">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="286d1-182">系統會自動偵測到裝置，而 Advanced Recovery Companion 應用程式 UI 則會開始更新程序：</span><span class="sxs-lookup"><span data-stu-id="286d1-182">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 乾淨快閃刷新畫面](images/ARC2.png)

6. <span data-ttu-id="286d1-184">在 Advanced Recovery Companion 應用程式 UI 中選取 HoloLens 2 裝置，然後依照指示完成快閃刷新。</span><span class="sxs-lookup"><span data-stu-id="286d1-184">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="286d1-185">不使用應用程式商店來下載 ARC</span><span class="sxs-lookup"><span data-stu-id="286d1-185">Download ARC without using the app store</span></span>

<span data-ttu-id="286d1-186">如果 IT 環境禁止使用 Windows Store 應用程式或限制存取零售商店，則 IT 系統管理員可以透過「離線」部署路徑，提供此應用程式。</span><span class="sxs-lookup"><span data-stu-id="286d1-186">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="286d1-187">IT 系統管理員也可以透過 [系統中心設定管理員(SCCM)] 或 Intune 來分發這個應用程式。</span><span class="sxs-lookup"><span data-stu-id="286d1-187">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="286d1-188">本指南將側重於 Advance Recovery Companion，但該程式也適用於其他 [離線] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="286d1-188">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="286d1-189">按照下列步驟啟用部署路徑：</span><span class="sxs-lookup"><span data-stu-id="286d1-189">Follow these steps to enable the deployment path:</span></span>
1. <span data-ttu-id="286d1-190">請移至 [商務用 Microsoft Store](https://businessstore.microsoft.com)，並使用 Azure Active Directory 身分識別登入。</span><span class="sxs-lookup"><span data-stu-id="286d1-190">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="286d1-191">移至 **管理-設定**。</span><span class="sxs-lookup"><span data-stu-id="286d1-191">Go to **Manage – Settings**.</span></span> <span data-ttu-id="286d1-192">開啟**購物體驗**底下的**顯示離線應用程式**。</span><span class="sxs-lookup"><span data-stu-id="286d1-192">Turn on **Show offline apps** under **Shopping experience**.</span></span>
1. <span data-ttu-id="286d1-193">移至**為我的群組採購**並搜尋[**_進階修復小幫手_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)。</span><span class="sxs-lookup"><span data-stu-id="286d1-193">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>
1. <span data-ttu-id="286d1-194">將**授權類型**變更為\**_離線_，然後選取_*管理\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="286d1-194">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>
1. <span data-ttu-id="286d1-195">在**下載套件供離線使用**底下，選取第二個藍色**下載**按鈕。</span><span class="sxs-lookup"><span data-stu-id="286d1-195">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="286d1-196">請確定檔案副檔名為 *.appxbundle*。</span><span class="sxs-lookup"><span data-stu-id="286d1-196">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="286d1-197">在這個階段，如果桌上型電腦具有網際網路存取，只要按兩下套件以安裝應用程式即可。</span><span class="sxs-lookup"><span data-stu-id="286d1-197">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="286d1-198">如果目的地電腦沒有網際網路連線，請依照下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="286d1-198">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="286d1-199">選取未編碼的授權，然後選取 **[產生授權]**。</span><span class="sxs-lookup"><span data-stu-id="286d1-199">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="286d1-200">在 **[所需的框架]** 底下，選取 **[下載]**。</span><span class="sxs-lookup"><span data-stu-id="286d1-200">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="286d1-201">使用 DISM 將套件與依存關係和授權一起套用。</span><span class="sxs-lookup"><span data-stu-id="286d1-201">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="286d1-202">在系統管理員的命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="286d1-202">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > <span data-ttu-id="286d1-203">此代碼範例中的版本號碼可能不符目前可用的版本。</span><span class="sxs-lookup"><span data-stu-id="286d1-203">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="286d1-204">您可能也選取了不同於範例的下載位置。</span><span class="sxs-lookup"><span data-stu-id="286d1-204">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="286d1-205">視需要變更命令。</span><span class="sxs-lookup"><span data-stu-id="286d1-205">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="286d1-206">當您打算使用 Advanced Recovery Companion 離線安裝 FFU 時，下載快閃影像可能會很有用。</span><span class="sxs-lookup"><span data-stu-id="286d1-206">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="286d1-207">[**下載 HoloLens 2 目前的影像**](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="286d1-207">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>

<span data-ttu-id="286d1-208">其他資源：</span><span class="sxs-lookup"><span data-stu-id="286d1-208">Other resources:</span></span>
- [<span data-ttu-id="286d1-209">散發離線 App</span><span class="sxs-lookup"><span data-stu-id="286d1-209">Distribute offline apps</span></span>](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="286d1-210">DISM 應用程式套件（.appx 或 .appxbundle）服務命令列選項</span><span class="sxs-lookup"><span data-stu-id="286d1-210">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
