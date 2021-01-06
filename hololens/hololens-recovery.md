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
ms.openlocfilehash: ad162d1f415430e22e683280089cacf2e1cef02a
ms.sourcegitcommit: 3827d244426ffecb517f6cfa714eeef9363c062d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/05/2021
ms.locfileid: "11253579"
---
# <span data-ttu-id="601d8-104">重新啟動、重設或復原 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="601d8-104">Restart, reset, or recover HoloLens 2</span></span>

## <span data-ttu-id="601d8-105">為裝置充電</span><span class="sxs-lookup"><span data-stu-id="601d8-105">Charge the device</span></span>

<span data-ttu-id="601d8-106">開始進行任何疑難排解程序之前，如果可以，請先確認您的裝置已具備 20% 到40% 的電量。</span><span class="sxs-lookup"><span data-stu-id="601d8-106">Before you start any troubleshooting procedure, make sure that your device is charged to 20 to 40 percent of battery capacity if possible.</span></span> <span data-ttu-id="601d8-107">使用在 HoloLens 2 裝置隨附的充電器和 USB 類型-C 型纜線。</span><span class="sxs-lookup"><span data-stu-id="601d8-107">Use the charger and the USB Type-C cables that come with the HoloLens 2 device.</span></span> <span data-ttu-id="601d8-108">裝置附帶的電源供應器和 USB-C-to-C 纜線是為 HoloLens 2 充電的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="601d8-108">The power supply and USB-C-to-C cable that come with the device are the best way to charge your HoloLens 2.</span></span> <span data-ttu-id="601d8-109">電源供應器提供 18W 的電力 (2A 時為 9V)。</span><span class="sxs-lookup"><span data-stu-id="601d8-109">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="601d8-110">使用提供的壁掛式充電器，HoloLens 2 裝置可以在裝置處於待機狀態時，在 65 分鐘內將電量充滿。</span><span class="sxs-lookup"><span data-stu-id="601d8-110">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="601d8-111">如果您無法使用這些附件，請確認提供的充電器是可以使用且可支援至少 15 瓦的電源。</span><span class="sxs-lookup"><span data-stu-id="601d8-111">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="601d8-112">如果可以，請避免使用電腦透過 USB 為裝置充電 (速度慢)。</span><span class="sxs-lookup"><span data-stu-id="601d8-112">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="601d8-113">如果裝置已正確啟動並運行，則可以使用三種方法來檢查電池電量等級:</span><span class="sxs-lookup"><span data-stu-id="601d8-113">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="601d8-114">從 HoloLens 裝置 UI 的主要功能表。</span><span class="sxs-lookup"><span data-stu-id="601d8-114">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="601d8-115">檢視靠近電源按鈕的 LED (若具有 40% 的電量，您應至少看到兩個亮起的 LED 燈)。</span><span class="sxs-lookup"><span data-stu-id="601d8-115">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDS).</span></span>
    - <span data-ttu-id="601d8-116">裝置充電時，電池指示燈會亮起，指出目前的電量。</span><span class="sxs-lookup"><span data-stu-id="601d8-116">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="601d8-117">最後一個燈號會淡入和淡出以表示正在充電。</span><span class="sxs-lookup"><span data-stu-id="601d8-117">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="601d8-118">當您的 HoloLens 開啟時，電池指示器會以五個增量來顯示電池電量。</span><span class="sxs-lookup"><span data-stu-id="601d8-118">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="601d8-119">五個燈號中只有一個亮起時，表示電池電量低於 20%。</span><span class="sxs-lookup"><span data-stu-id="601d8-119">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="601d8-120">如果電池電量嚴重偏低，而您嘗試開啟裝置，就會有一個燈號短暫閃爍，然後熄滅。</span><span class="sxs-lookup"><span data-stu-id="601d8-120">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="601d8-121">在您的主機電腦上，開啟 **File Explorer 文件資源管理** 器，然後在**This PC 這台電腦** 的左方, 尋找您的 HoloLens 2 裝置.</span><span class="sxs-lookup"><span data-stu-id="601d8-121">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="601d8-122">以滑鼠右鍵按一下裝置，並選取 **[內容]**。</span><span class="sxs-lookup"><span data-stu-id="601d8-122">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="601d8-123">對話方塊會隨即顯示電池電量等級。</span><span class="sxs-lookup"><span data-stu-id="601d8-123">A dialog box will show the battery charge level.</span></span>

   ![HoloLens 2 屬性畫面會顯示電池電量等級](images/ResetRecovery2.png)

<span data-ttu-id="601d8-125">如果裝置無法引導至 [啟動] 功能表，請注意主機電腦上的 LED 外觀和裝置枚舉。</span><span class="sxs-lookup"><span data-stu-id="601d8-125">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="601d8-126">然後按照 [疑難排解指南](https://docs.microsoft.com/hololens/hololens-troubleshooting)。</span><span class="sxs-lookup"><span data-stu-id="601d8-126">Then follow the [troubleshooting guide](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="601d8-127">如果裝置狀態不符合疑難排解指南中所列的任何狀態，請將裝置連線至電源執行[硬重設程序](hololens-recovery.md#hard-reset-procedure) ，而不是連接到您的主機電腦。</span><span class="sxs-lookup"><span data-stu-id="601d8-127">If the state of the device doesn't match any of the states listed in the troubleshooting guide, preform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="601d8-128">請至少等候一個小時，讓裝置充電。</span><span class="sxs-lookup"><span data-stu-id="601d8-128">Wait at least one hour for the device to charge.</span></span>

## <span data-ttu-id="601d8-129">重設裝置</span><span class="sxs-lookup"><span data-stu-id="601d8-129">Reset the device</span></span>

<span data-ttu-id="601d8-130">在某些情況下，您可能需要手動重設裝置，而不需要使用軟體 UI。</span><span class="sxs-lookup"><span data-stu-id="601d8-130">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <span data-ttu-id="601d8-131">標準程序</span><span class="sxs-lookup"><span data-stu-id="601d8-131">Standard procedure</span></span>
1. <span data-ttu-id="601d8-132">取下 Type-C 連接線，以中斷裝置和電源或主機電腦的連線。</span><span class="sxs-lookup"><span data-stu-id="601d8-132">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="601d8-133">按住**電源**按鈕 15 秒。</span><span class="sxs-lookup"><span data-stu-id="601d8-133">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="601d8-134">所有的 LED 均應關閉。</span><span class="sxs-lookup"><span data-stu-id="601d8-134">All LEDs should be off.</span></span>

3. <span data-ttu-id="601d8-135">等待2-3 秒，然後按一下 **電源** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="601d8-135">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="601d8-136">靠近電源按鈕的 LED 燈會亮起，而裝置將開始啟動。</span><span class="sxs-lookup"><span data-stu-id="601d8-136">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="601d8-137">將裝置連線到主機電腦，然後開啟 [裝置管理員]。</span><span class="sxs-lookup"><span data-stu-id="601d8-137">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="601d8-138">(針對 Windows 10，請按 **Windows** 鍵，再按 **X** 鍵，然後選取 **裝置管理員**。) 確認裝置枚舉正確為 *Microsoft HoloLens* 如以下影像所示:</span><span class="sxs-lookup"><span data-stu-id="601d8-138">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery 裝置管理員](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="601d8-140">硬重設程序</span><span class="sxs-lookup"><span data-stu-id="601d8-140">Hard-reset procedure</span></span>

<span data-ttu-id="601d8-141">如果標準重設程序無法運作，請使用硬重設程序:</span><span class="sxs-lookup"><span data-stu-id="601d8-141">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="601d8-142">取下 Type-C 連接線，以中斷裝置和電源或主機電腦的連線。</span><span class="sxs-lookup"><span data-stu-id="601d8-142">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="601d8-143">按住 **調低音量** + **電源** 按鈕 15 秒。</span><span class="sxs-lookup"><span data-stu-id="601d8-143">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="601d8-144">裝置會自動重新啟動。</span><span class="sxs-lookup"><span data-stu-id="601d8-144">The device will automatically restart.</span></span>

4. <span data-ttu-id="601d8-145">將裝置連接到主機電腦。</span><span class="sxs-lookup"><span data-stu-id="601d8-145">Connect the device to the host PC.</span></span>
5. <span data-ttu-id="601d8-146">開啟 [裝置管理員] （如果是 Windows 10，請按 **Windows** 鍵，然後按 **X** 鍵，並選取 **[裝置管理員]**）。</span><span class="sxs-lookup"><span data-stu-id="601d8-146">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="601d8-147">請確認裝置枚舉正確為 *Microsoft HoloLens*，如下列影像所示：</span><span class="sxs-lookup"><span data-stu-id="601d8-147">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery 裝置管理員 2](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="601d8-149">乾淨重新快閃刷新裝置</span><span class="sxs-lookup"><span data-stu-id="601d8-149">Clean-reflash the device</span></span>

<span data-ttu-id="601d8-150">在特別的情況下，您可能需要乾淨快閃刷新 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="601d8-150">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="601d8-151">請注意，乾淨重新快閃刷新不會影響下列問題：</span><span class="sxs-lookup"><span data-stu-id="601d8-151">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="601d8-152">顯示色彩一致性</span><span class="sxs-lookup"><span data-stu-id="601d8-152">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="601d8-153">使用音效啟動但沒有顯示輸出</span><span class="sxs-lookup"><span data-stu-id="601d8-153">Booting with sound but no display output</span></span>
- [<span data-ttu-id="601d8-154">1-3-5-LED 模式</span><span class="sxs-lookup"><span data-stu-id="601d8-154">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="601d8-155">過熱</span><span class="sxs-lookup"><span data-stu-id="601d8-155">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="601d8-156">OS 當機（不同於應用程式的當機）</span><span class="sxs-lookup"><span data-stu-id="601d8-156">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="601d8-157">有兩種方法可以快閃刷新裝置。</span><span class="sxs-lookup"><span data-stu-id="601d8-157">There are two ways to reflash the device.</span></span> <span data-ttu-id="601d8-158">針對這兩者，您必須先 [從 Windows 市集中安裝 [進階修復小幫手]](https://www.microsoft.com/store/productId/9P74Z35SFRS8)。</span><span class="sxs-lookup"><span data-stu-id="601d8-158">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="601d8-159">如果快閃刷新裝置，您所有的個人資料、應用程式和設定都會被清除，包含 TPM 重設資訊。</span><span class="sxs-lookup"><span data-stu-id="601d8-159">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="601d8-160">根據預設，[進階修復小幫手] 設定為下載最新的功能版本版本，請查看此處以閱讀我們的[版本資訊](hololens-release-notes.md#)以瞭解最新功能版本。</span><span class="sxs-lookup"><span data-stu-id="601d8-160">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="601d8-161">若要取得最新的 HoloLens 2 完整刷新更新 (FFU) 套件，以透過 [進階修復小幫手] 快閃刷新您的裝置，請按一下此處下載最新的每月 HoloLens 2 影像[。](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="601d8-161">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="601d8-162">此版本是最新的萬用組建。</span><span class="sxs-lookup"><span data-stu-id="601d8-162">This version is the latest generally available build.</span></span>

<span data-ttu-id="601d8-163">在啟動快閃刷新程序前，請確認已在 Windows 10 電腦上安裝並執行該應用程式，並準備好偵測裝置。</span><span class="sxs-lookup"><span data-stu-id="601d8-163">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![HoloLens 2 乾淨快閃刷新螢幕擷取畫面](images/ARC1.png)

### <span data-ttu-id="601d8-165">正常程序</span><span class="sxs-lookup"><span data-stu-id="601d8-165">Normal procedure</span></span>

1. <span data-ttu-id="601d8-166">當 HoloLens 裝置執行時，請將它連線到先前開啟的 Advanced Recovery Companion 應用程式的 Windows 10 電腦。</span><span class="sxs-lookup"><span data-stu-id="601d8-166">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="601d8-167">系統會自動偵測到裝置，而 Advanced Recovery Companion 應用程式 UI 則會開始更新程序：</span><span class="sxs-lookup"><span data-stu-id="601d8-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 乾淨快閃刷新初始畫面](images/ARC2.png)

3. <span data-ttu-id="601d8-169">在 Advanced Recovery Companion 應用程式 UI 中選取 HoloLens 2 裝置，並依照指示完成快閃刷新。</span><span class="sxs-lookup"><span data-stu-id="601d8-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <span data-ttu-id="601d8-170">手動程序</span><span class="sxs-lookup"><span data-stu-id="601d8-170">Manual procedure</span></span>

<span data-ttu-id="601d8-171">如果 HoloLens2 無法正確啟動，您可能需要將裝置置於修復模式:</span><span class="sxs-lookup"><span data-stu-id="601d8-171">If the HoloLens 2 doesn't start correctly, you may need to put the device into Recovery mode:</span></span>

1. <span data-ttu-id="601d8-172">取下 Type-C 連接線，以中斷裝置和電源或主機電腦的連線。</span><span class="sxs-lookup"><span data-stu-id="601d8-172">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="601d8-173">按住**電源**按鈕 15 秒。</span><span class="sxs-lookup"><span data-stu-id="601d8-173">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="601d8-174">此時應該會關閉所有 LED。</span><span class="sxs-lookup"><span data-stu-id="601d8-174">All LEDs should turn off.</span></span>

3. <span data-ttu-id="601d8-175">按下**調高音量**按鈕時，請按下並放開**電源** 按鈕以啟動裝置。</span><span class="sxs-lookup"><span data-stu-id="601d8-175">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="601d8-176">請等候 15 秒，然後再放開 **調高音量**按鈕。</span><span class="sxs-lookup"><span data-stu-id="601d8-176">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="601d8-177">只有中間的五個 LED 燈會亮起。</span><span class="sxs-lookup"><span data-stu-id="601d8-177">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="601d8-178">將裝置連線到主機電腦，並開啟 [裝置管理員]。</span><span class="sxs-lookup"><span data-stu-id="601d8-178">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="601d8-179">(針對 Windows 10，請按 **Windows** 鍵，再按 **X** 鍵，然後選取 **裝置管理員**。) 確認裝置枚舉正確為 Microsoft HoloLens 如以下影像所示:</span><span class="sxs-lookup"><span data-stu-id="601d8-179">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="601d8-181">系統會自動偵測到裝置，而 Advanced Recovery Companion 應用程式 UI 則會開始更新程序：</span><span class="sxs-lookup"><span data-stu-id="601d8-181">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 乾淨快閃刷新畫面](images/ARC2.png)

6. <span data-ttu-id="601d8-183">在 Advanced Recovery Companion 應用程式 UI 中選取 HoloLens 2 裝置，然後依照指示完成快閃刷新。</span><span class="sxs-lookup"><span data-stu-id="601d8-183">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <span data-ttu-id="601d8-184">不使用應用程式商店來下載 ARC</span><span class="sxs-lookup"><span data-stu-id="601d8-184">Download ARC without using the app store</span></span>

<span data-ttu-id="601d8-185">如果 IT 環境禁止使用 Windows Store 應用程式或限制存取零售商店，則 IT 系統管理員可以透過「離線」部署路徑，提供此應用程式。</span><span class="sxs-lookup"><span data-stu-id="601d8-185">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE] 
 > - <span data-ttu-id="601d8-186">IT 系統管理員也可以透過 [系統中心設定管理員(SCCM)] 或 Intune 來分發這個應用程式。</span><span class="sxs-lookup"><span data-stu-id="601d8-186">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="601d8-187">本指南將側重於 Advance Recovery Companion，但該程式也適用於其他 [離線] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="601d8-187">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="601d8-188">按照下列步驟啟用部署路徑：</span><span class="sxs-lookup"><span data-stu-id="601d8-188">Follow these steps to enable the deployment path:</span></span>
1. <span data-ttu-id="601d8-189">請移至 [商務用 Microsoft Store](https://businessstore.microsoft.com)，並使用 Azure Active Directory 身分識別登入。</span><span class="sxs-lookup"><span data-stu-id="601d8-189">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="601d8-190">移至 **管理-設定**。</span><span class="sxs-lookup"><span data-stu-id="601d8-190">Go to **Manage – Settings**.</span></span> <span data-ttu-id="601d8-191">開啟 **[購物體驗]** 底下的 **[顯示離線應用程式]**。</span><span class="sxs-lookup"><span data-stu-id="601d8-191">Turn on **Show offline apps** under **Shopping experience**.</span></span> 
1. <span data-ttu-id="601d8-192">移至**為我的群組採購**並搜尋 [\**_進階修復小幫手_*_](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)。</span><span class="sxs-lookup"><span data-stu-id="601d8-192">Go to **shop for my group**, and search for [\**_Advanced Recovery Companion_*_](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>
1. <span data-ttu-id="601d8-193">將_\*授權類型\*\*變更為 \*\*_離線_\*_，然後按一下_\*[管理]\*\*。</span><span class="sxs-lookup"><span data-stu-id="601d8-193">Change the _*License Type*\* to \**_offline_*_, and select _\*Manage\*\*.</span></span>
1. <span data-ttu-id="601d8-194">在 **[下載套件供離線使用]** 底下，選取第二個藍色 **[下載]** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="601d8-194">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="601d8-195">請確定檔案副檔名為 *.appxbundle*。</span><span class="sxs-lookup"><span data-stu-id="601d8-195">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="601d8-196">在這個階段，如果桌上型電腦具有網際網路存取，只要按兩下套件以安裝應用程式即可。</span><span class="sxs-lookup"><span data-stu-id="601d8-196">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>


    - <span data-ttu-id="601d8-197">如果目的地電腦沒有網際網路連線，請依照下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="601d8-197">If the destination PC has no internet connectivity, follow these steps:</span></span> 
       1. <span data-ttu-id="601d8-198">選取未編碼的授權，然後選取 **[產生授權]**。</span><span class="sxs-lookup"><span data-stu-id="601d8-198">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="601d8-199">在 **[所需的框架]** 底下，選取 **[下載]**。</span><span class="sxs-lookup"><span data-stu-id="601d8-199">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="601d8-200">使用 DISM 將套件與依存關係和授權一起套用。</span><span class="sxs-lookup"><span data-stu-id="601d8-200">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="601d8-201">在系統管理員的命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="601d8-201">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > <span data-ttu-id="601d8-202">此代碼範例中的版本號碼可能不符目前可用的版本。</span><span class="sxs-lookup"><span data-stu-id="601d8-202">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="601d8-203">您可能也選取了不同於範例的下載位置。</span><span class="sxs-lookup"><span data-stu-id="601d8-203">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="601d8-204">視需要變更命令。</span><span class="sxs-lookup"><span data-stu-id="601d8-204">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="601d8-205">當您打算使用 Advanced Recovery Companion 離線安裝 FFU 時，下載快閃影像可能會很有用。</span><span class="sxs-lookup"><span data-stu-id="601d8-205">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="601d8-206">[**下載 HoloLens 2 目前的影像**](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="601d8-206">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="601d8-207">其他資源：</span><span class="sxs-lookup"><span data-stu-id="601d8-207">Other resources:</span></span>
- [<span data-ttu-id="601d8-208">散發離線 App</span><span class="sxs-lookup"><span data-stu-id="601d8-208">Distribute offline apps</span></span>](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="601d8-209">DISM 應用程式套件（.appx 或 .appxbundle）服務命令列選項</span><span class="sxs-lookup"><span data-stu-id="601d8-209">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
