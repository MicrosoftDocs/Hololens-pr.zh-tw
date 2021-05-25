---
title: 重新開機、重設或復原 HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: 如何使用 Windows 裝置復原工具將映射快閃到 HoloLens 第1代。
keywords: 作法、重新開機、重設、復原、硬重設、軟重設、電源週期、HoloLens、關機、wdrt、windows 裝置修復工具
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f855aa84a347edc85e5b9f02458721778eb2515a
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397689"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="e2452-104">重新開機、重設或復原 HoloLens (第1代) </span><span class="sxs-lookup"><span data-stu-id="e2452-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="e2452-105">如果您的 HoloLens 遇到問題，您可能會想要嘗試重新開機或重設，或甚至使用裝置復原來重新刷新裝置。</span><span class="sxs-lookup"><span data-stu-id="e2452-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="e2452-106">本文將逐步引導您完成依序執行的建議復原步驟。</span><span class="sxs-lookup"><span data-stu-id="e2452-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="e2452-107">如果您想要復原 HoloLens 2，請參閱 [復原 HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery)，因為該進程不同。</span><span class="sxs-lookup"><span data-stu-id="e2452-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="e2452-108">本文著重于 HoloLens 裝置和軟體。</span><span class="sxs-lookup"><span data-stu-id="e2452-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="e2452-109">如果您的全像是看不到，請參閱 **[HoloLens 環境考慮](hololens-environment-considerations.md)** ，以取得改善全像影像品質之因素的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e2452-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="e2452-110">重新啟動</span><span class="sxs-lookup"><span data-stu-id="e2452-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="e2452-111">使用 Cortana 進行安全重新開機</span><span class="sxs-lookup"><span data-stu-id="e2452-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="e2452-112">重新開機 HoloLens 最安全的方式是使用 Cortana，這通常是您在 HoloLens 遇到問題時的第一件事。</span><span class="sxs-lookup"><span data-stu-id="e2452-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="e2452-113">Cortana 無法在所有裝置上使用。</span><span class="sxs-lookup"><span data-stu-id="e2452-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="e2452-114">Cortana 在所有 HoloLens (第1代) 裝置上都有提供。</span><span class="sxs-lookup"><span data-stu-id="e2452-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="e2452-115">在 Windows Holograpic 2004 版更新之前，您可以在組建的 HoloLens 2 裝置上使用 Cortana。</span><span class="sxs-lookup"><span data-stu-id="e2452-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="e2452-116">開啟 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="e2452-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="e2452-117">請確定使用者已登入，而裝置未等候密碼解除鎖定。</span><span class="sxs-lookup"><span data-stu-id="e2452-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="e2452-118">說「嗨 Cortana、重新開機」或「嗨 Cortana，重新開機」。</span><span class="sxs-lookup"><span data-stu-id="e2452-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="e2452-119">Cortana 將會回應並提示您確認。</span><span class="sxs-lookup"><span data-stu-id="e2452-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="e2452-120">在問題之後等候音效播放，然後說「是」。</span><span class="sxs-lookup"><span data-stu-id="e2452-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="e2452-121">裝置將會重新開機。</span><span class="sxs-lookup"><span data-stu-id="e2452-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="e2452-122">使用電源按鈕來進行安全重新開機</span><span class="sxs-lookup"><span data-stu-id="e2452-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="e2452-123">如果您仍然無法重新開機裝置，請嘗試使用 [ **電源** ] 按鈕重新開機裝置：</span><span class="sxs-lookup"><span data-stu-id="e2452-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="e2452-124">按住 **電源** 按鈕5秒。</span><span class="sxs-lookup"><span data-stu-id="e2452-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="e2452-125">1秒之後，所有五個 Led 都會閃爍，然後從右至左一次慢慢關閉。</span><span class="sxs-lookup"><span data-stu-id="e2452-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="e2452-126">5秒之後，所有 Led 將會關閉，表示成功關機。</span><span class="sxs-lookup"><span data-stu-id="e2452-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="e2452-127">關閉所有 Led 之後，立即停止按下按鈕。</span><span class="sxs-lookup"><span data-stu-id="e2452-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="e2452-128">等候1分鐘，讓關機完成。</span><span class="sxs-lookup"><span data-stu-id="e2452-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="e2452-129">即使關閉顯示之後，關機仍可能仍在進行中。</span><span class="sxs-lookup"><span data-stu-id="e2452-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="e2452-130">按住 **電源** 按鈕的1秒，再次開啟裝置。</span><span class="sxs-lookup"><span data-stu-id="e2452-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="e2452-131">使用 Windows 裝置入口網站進行安全重新開機</span><span class="sxs-lookup"><span data-stu-id="e2452-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="e2452-132">在此程式中，HoloLens 必須設定為開發人員裝置。</span><span class="sxs-lookup"><span data-stu-id="e2452-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="e2452-133">若要深入瞭解，請參閱 [Windows 裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="e2452-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="e2452-134">如果上述程式無法運作，請嘗試使用 [Windows 裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="e2452-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="e2452-135">在右上角尋找重新開機或關閉裝置的選項。</span><span class="sxs-lookup"><span data-stu-id="e2452-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="e2452-136">執行不安全的強制重新開機</span><span class="sxs-lookup"><span data-stu-id="e2452-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="e2452-137">如果先前的方法未重新開機 HoloLens，請強制重新開機。</span><span class="sxs-lookup"><span data-stu-id="e2452-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="e2452-138">這個方法相當於移除並重新安裝電池。</span><span class="sxs-lookup"><span data-stu-id="e2452-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="e2452-139">這是危險的，因為它可能會讓您的裝置處於損毀的狀態。</span><span class="sxs-lookup"><span data-stu-id="e2452-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="e2452-140">如果發生這種情況，您必須將 HoloLens 閃爍。</span><span class="sxs-lookup"><span data-stu-id="e2452-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="e2452-141">這是可能有害的方法，只有在先前提到的方法無法運作時，才應該使用。</span><span class="sxs-lookup"><span data-stu-id="e2452-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="e2452-142">按住 **電源** 按鈕至少10秒鐘。</span><span class="sxs-lookup"><span data-stu-id="e2452-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="e2452-143">您可以保留按鈕超過10秒。</span><span class="sxs-lookup"><span data-stu-id="e2452-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="e2452-144">您可以放心地忽略任何 LED 的活動。</span><span class="sxs-lookup"><span data-stu-id="e2452-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="e2452-145">放開按鈕並等候2-3 秒。</span><span class="sxs-lookup"><span data-stu-id="e2452-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="e2452-146">按住 **電源** 按鈕的1秒。</span><span class="sxs-lookup"><span data-stu-id="e2452-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="e2452-147">如果您仍然遇到問題，請按 [ **電源** ] 按鈕4秒，直到所有電池指示器淡出，而螢幕停止顯示全像全像。</span><span class="sxs-lookup"><span data-stu-id="e2452-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="e2452-148">等候1分鐘，然後再按一次 **電源** 按鈕來開啟裝置。</span><span class="sxs-lookup"><span data-stu-id="e2452-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="e2452-149">重設為原廠設定</span><span class="sxs-lookup"><span data-stu-id="e2452-149">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="e2452-150">電池需要至少40% 的費用才能重設。</span><span class="sxs-lookup"><span data-stu-id="e2452-150">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="e2452-151">如果您的 HoloLens 仍有問題，請嘗試將其重設為原廠狀態。</span><span class="sxs-lookup"><span data-stu-id="e2452-151">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="e2452-152">此步驟會保留安裝在其上的 Windows 全像軟體版本，並傳回所有其他的原廠設定。</span><span class="sxs-lookup"><span data-stu-id="e2452-152">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="e2452-153">如果您重設裝置，將會清除您的所有個人資料、應用程式和設定，包括 TPM 重設資訊。</span><span class="sxs-lookup"><span data-stu-id="e2452-153">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="e2452-154">重設只會安裝最新版的 Windows 全像安裝版本。</span><span class="sxs-lookup"><span data-stu-id="e2452-154">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="e2452-155">您必須重做所有的初始化步驟， (校正、連線至 Wi-fi、建立使用者帳戶、下載應用程式等) 。</span><span class="sxs-lookup"><span data-stu-id="e2452-155">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="e2452-156">開啟 [設定] 應用程式，然後選取 [**更新**  >  **修復**]。</span><span class="sxs-lookup"><span data-stu-id="e2452-156">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="e2452-157">選取 [ **重設裝置** ] 選項，並閱讀確認訊息。</span><span class="sxs-lookup"><span data-stu-id="e2452-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="e2452-158">確認重設。</span><span class="sxs-lookup"><span data-stu-id="e2452-158">Confirm the reset.</span></span> <span data-ttu-id="e2452-159">裝置將會重新開機，並顯示一組旋轉的齒輪和進度列。</span><span class="sxs-lookup"><span data-stu-id="e2452-159">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="e2452-160">等候約30分鐘，讓此程式完成。</span><span class="sxs-lookup"><span data-stu-id="e2452-160">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="e2452-161">完成時，裝置將會重新開機為「現成」體驗。</span><span class="sxs-lookup"><span data-stu-id="e2452-161">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="e2452-162">重新安裝作業系統</span><span class="sxs-lookup"><span data-stu-id="e2452-162">Reinstall the operating system</span></span>

<span data-ttu-id="e2452-163">如果裝置在重新開機和重設之後仍有問題，您可以在電腦上使用修復工具來重新安裝 HoloLens 作業系統和固件。</span><span class="sxs-lookup"><span data-stu-id="e2452-163">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="e2452-164">HoloLens 針對重設所需的資料封裝在完整的 Flash 更新 (FFU) ，類似于 .iso、.wim 或 .vhd 檔案。</span><span class="sxs-lookup"><span data-stu-id="e2452-164">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="e2452-165">深入瞭解 FFU 影像檔案格式。</span><span class="sxs-lookup"><span data-stu-id="e2452-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="e2452-166">您可以使用 Windows 裝置復原工具，在 HoloLens (第1代) 上安裝新的作業系統。</span><span class="sxs-lookup"><span data-stu-id="e2452-166">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="e2452-167">使用該工具之前，請先查看是否重新開機或重設 HoloLens 修正問題。</span><span class="sxs-lookup"><span data-stu-id="e2452-167">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="e2452-168">修復程式可能需要一段時間。</span><span class="sxs-lookup"><span data-stu-id="e2452-168">The recovery process may take a while.</span></span> <span data-ttu-id="e2452-169">完成時，將會安裝最新版的 Windows 全像軟體。</span><span class="sxs-lookup"><span data-stu-id="e2452-169">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="e2452-170">若要使用此工具，您需要執行 Windows 10 或更新版本且至少有 4 GB 可用儲存空間的電腦。</span><span class="sxs-lookup"><span data-stu-id="e2452-170">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="e2452-171">您無法在虛擬機器上執行此工具。</span><span class="sxs-lookup"><span data-stu-id="e2452-171">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="e2452-172">復原您的 HoloLens</span><span class="sxs-lookup"><span data-stu-id="e2452-172">Recover your HoloLens</span></span>

1. <span data-ttu-id="e2452-173">在您的電腦上下載並安裝 [Windows 裝置修復工具](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) 。</span><span class="sxs-lookup"><span data-stu-id="e2452-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="e2452-174">使用 HoloLens 隨附的微型 USB 纜線，將 HoloLens (第一代) 連接到您的電腦。</span><span class="sxs-lookup"><span data-stu-id="e2452-174">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="e2452-175">開啟 Windows 裝置復原工具，並遵循指示進行。</span><span class="sxs-lookup"><span data-stu-id="e2452-175">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="e2452-176">如果未自動偵測到 HoloLens (第1代) ，請選取 [ **我的裝置** 未偵測到]。</span><span class="sxs-lookup"><span data-stu-id="e2452-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="e2452-177">然後遵循指示，讓裝置進入修復模式。</span><span class="sxs-lookup"><span data-stu-id="e2452-177">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="e2452-178">手動閃爍模式</span><span class="sxs-lookup"><span data-stu-id="e2452-178">Manual flashing mode</span></span>

<span data-ttu-id="e2452-179">如果未偵測到您的裝置，請遵循下列步驟使其進入閃爍模式：</span><span class="sxs-lookup"><span data-stu-id="e2452-179">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="e2452-180">從任何電源線拔下裝置。</span><span class="sxs-lookup"><span data-stu-id="e2452-180">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="e2452-181">如果裝置已開啟，請按住 **電源** 按鈕，直到完全關閉為止。</span><span class="sxs-lookup"><span data-stu-id="e2452-181">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="e2452-182">按住 **音量** 按鈕，並短暫地點一下 **電源** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="e2452-182">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="e2452-183">裝置應該會啟動，而且只會顯示中間 LED。</span><span class="sxs-lookup"><span data-stu-id="e2452-183">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="e2452-184">將裝置插入您的電腦。</span><span class="sxs-lookup"><span data-stu-id="e2452-184">Plug the device into your PC.</span></span>
4. <span data-ttu-id="e2452-185">開啟 Windows 裝置修復工具。</span><span class="sxs-lookup"><span data-stu-id="e2452-185">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="e2452-186">選取 [ **我的裝置未偵測到** ]，然後選取 [ **HoloLens**]。</span><span class="sxs-lookup"><span data-stu-id="e2452-186">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="e2452-187">請依照指示來復原您的裝置。</span><span class="sxs-lookup"><span data-stu-id="e2452-187">Follow the instructions to recover your device.</span></span>
