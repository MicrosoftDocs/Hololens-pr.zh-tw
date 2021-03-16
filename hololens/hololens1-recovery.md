---
title: 重新啟動、重設或復原 HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: 如何使用 Windows Device Recovery Tool，將影像快閃刷新至 HoloLens 第 1 代。
keywords: 操作說明、重新啟動、重設、復原、硬重設、軟重設、電源重新啟動、HoloLens、關機、wdrt、Windows Device Recovery Tool
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
ms.openlocfilehash: f50a885f6cc82256d146d7f4914aca934e81c0c0
ms.sourcegitcommit: 01c0b0a789e156a9d29aaf6f61e36dfd09b8c01a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439039"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="d30b9-104">重新開機、重設或復原 HoloLens （第1代）</span><span class="sxs-lookup"><span data-stu-id="d30b9-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="d30b9-105">如果您在使用 HoloLens 時，發生問題，請嘗試重新啟動、重設或甚至使用裝置復原功能來重新快閃刷新。</span><span class="sxs-lookup"><span data-stu-id="d30b9-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="d30b9-106">本文將逐步引導您完成建議的復原步驟。</span><span class="sxs-lookup"><span data-stu-id="d30b9-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="d30b9-107">如果您想要復原 HoloLens 2，請參閱 [復原 HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery)，因為這個過程有所不同。</span><span class="sxs-lookup"><span data-stu-id="d30b9-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="d30b9-108">本文著重于 HoloLens 裝置和軟體。</span><span class="sxs-lookup"><span data-stu-id="d30b9-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="d30b9-109">如果您的全像投影看起來不正常，請參閱 **[HoloLens 的環境考慮](hololens-environment-considerations.md)**，瞭解改善全像投影品質的因素。</span><span class="sxs-lookup"><span data-stu-id="d30b9-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="d30b9-110">重新啟動</span><span class="sxs-lookup"><span data-stu-id="d30b9-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="d30b9-111">使用 Cortana 執行安全重新啟動</span><span class="sxs-lookup"><span data-stu-id="d30b9-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="d30b9-112">重新啟動 HoloLens 最安全的方法是使用 Cortana，這項功能通常是在您使用 HoloLens 出問題時，第一件應該嘗試的動作。</span><span class="sxs-lookup"><span data-stu-id="d30b9-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="d30b9-113">並非所有裝置都能使用 Cortana 功能。</span><span class="sxs-lookup"><span data-stu-id="d30b9-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="d30b9-114">Cortana 功能可在所有 HoloLens (第 1 代)裝置上使用。</span><span class="sxs-lookup"><span data-stu-id="d30b9-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="d30b9-115">在 Windows Holograpic 的版本 2004 更新之前的HoloLens 2 上裝置可使用 Cortana。</span><span class="sxs-lookup"><span data-stu-id="d30b9-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="d30b9-116">開啟您的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="d30b9-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="d30b9-117">請確認使用者已登入，且裝置並未等待密碼解鎖。</span><span class="sxs-lookup"><span data-stu-id="d30b9-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="d30b9-118">請說出「嗨 Cortana，重新開機」或「嗨 Cortana，重新啟動」。</span><span class="sxs-lookup"><span data-stu-id="d30b9-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="d30b9-119">Cortana 會回復並提示您進行確認。</span><span class="sxs-lookup"><span data-stu-id="d30b9-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="d30b9-120">在問題之後，請等候音效聲，然後說「是」。</span><span class="sxs-lookup"><span data-stu-id="d30b9-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="d30b9-121">裝置會重新啟動。</span><span class="sxs-lookup"><span data-stu-id="d30b9-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="d30b9-122">使用 [電源] 按鈕來執行安全重新啟動</span><span class="sxs-lookup"><span data-stu-id="d30b9-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="d30b9-123">如果您仍然無法重新啟動裝置，請嘗試使用 **電源** 按鈕來重新啟動裝置：</span><span class="sxs-lookup"><span data-stu-id="d30b9-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="d30b9-124">按住**電源**按鈕 5 秒。</span><span class="sxs-lookup"><span data-stu-id="d30b9-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="d30b9-125">1秒之後，所有五個 LED 燈都會亮起，然後再慢慢地從右至左一個一個關閉。</span><span class="sxs-lookup"><span data-stu-id="d30b9-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="d30b9-126">5秒之後，所有的 LED 燈都會關閉，表示裝置已成功關閉。</span><span class="sxs-lookup"><span data-stu-id="d30b9-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="d30b9-127">在所有 LED 燈關閉之後，請務必立即停止按壓按鈕。</span><span class="sxs-lookup"><span data-stu-id="d30b9-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="d30b9-128">等待1分鐘，讓裝置完全關閉。</span><span class="sxs-lookup"><span data-stu-id="d30b9-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="d30b9-129">即使顯示器已關閉，關機動作仍可能還在進行中。</span><span class="sxs-lookup"><span data-stu-id="d30b9-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="d30b9-130">按住 **電源** 按鈕 1 秒，以再次開啟裝置。</span><span class="sxs-lookup"><span data-stu-id="d30b9-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="d30b9-131">使用 Windows 裝置入口網站來執行安全重新啟動</span><span class="sxs-lookup"><span data-stu-id="d30b9-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="d30b9-132">在此程式中，您必須將 HoloLens 設定為開發人員裝置。</span><span class="sxs-lookup"><span data-stu-id="d30b9-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="d30b9-133">深入了解 [Windows 裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="d30b9-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="d30b9-134">如果前述程式無法運作，您可以使用 [Windows 裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 以嘗試重新啟動裝置。</span><span class="sxs-lookup"><span data-stu-id="d30b9-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="d30b9-135">找到右上角可重新啟動或關閉裝置的選項。</span><span class="sxs-lookup"><span data-stu-id="d30b9-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="d30b9-136">執行不安全的強制重新啟動</span><span class="sxs-lookup"><span data-stu-id="d30b9-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="d30b9-137">如果前述方法並無法重新啟動您的 HoloLens，請強制重新啟動。</span><span class="sxs-lookup"><span data-stu-id="d30b9-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="d30b9-138">此方法相當於移除並重新安裝電池。</span><span class="sxs-lookup"><span data-stu-id="d30b9-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="d30b9-139">這可能有點危險，因為這可能會讓您的裝置處於損毀狀態。</span><span class="sxs-lookup"><span data-stu-id="d30b9-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="d30b9-140">如果發生這種情況，您必須快閃刷新您的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="d30b9-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="d30b9-141">這是一種可能有害的方法，僅適用於前述所提及的方法均無效的情況下，才可以使用。</span><span class="sxs-lookup"><span data-stu-id="d30b9-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="d30b9-142">按住 **電源** 按鈕至少 10 秒。</span><span class="sxs-lookup"><span data-stu-id="d30b9-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="d30b9-143">您可將按鈕按住 10 秒以上。</span><span class="sxs-lookup"><span data-stu-id="d30b9-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="d30b9-144">您可以放心忽略任何 LED 活動。</span><span class="sxs-lookup"><span data-stu-id="d30b9-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="d30b9-145">放開按鈕並靜待 2-3 秒。</span><span class="sxs-lookup"><span data-stu-id="d30b9-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="d30b9-146">按住**電源**按鈕 1 秒。</span><span class="sxs-lookup"><span data-stu-id="d30b9-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="d30b9-147">如果仍有問題，請按**電源**按鈕 4 秒，直到所有電池指示器都淡出，且畫面停止顯示全像投影。</span><span class="sxs-lookup"><span data-stu-id="d30b9-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="d30b9-148">等待 1 分鐘，然後再按一次**電源**按鈕以開啟裝置。</span><span class="sxs-lookup"><span data-stu-id="d30b9-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="d30b9-149">重設成出廠預設值</span><span class="sxs-lookup"><span data-stu-id="d30b9-149">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="d30b9-150">電池至少需要有 40% 的電量才能重設。</span><span class="sxs-lookup"><span data-stu-id="d30b9-150">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="d30b9-151">如果您的 HoloLens 仍有問題，請嘗試將它重設為出廠狀態。</span><span class="sxs-lookup"><span data-stu-id="d30b9-151">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="d30b9-152">此步驟會保留所安裝的 Windows Holographic 軟體版本，並將其他所有內容復原為出廠設定。</span><span class="sxs-lookup"><span data-stu-id="d30b9-152">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="d30b9-153">如果重設裝置，您所有的個人資料、應用程式和設定都會被清除，包含 TPM 重設資訊。</span><span class="sxs-lookup"><span data-stu-id="d30b9-153">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="d30b9-154">重設只能安裝最新版的 Windows Holographic。</span><span class="sxs-lookup"><span data-stu-id="d30b9-154">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="d30b9-155">您必須重新執行所有的初始化步驟（校準、連線至 Wi-Fi、建立使用者帳戶、下載應用程式等等）。</span><span class="sxs-lookup"><span data-stu-id="d30b9-155">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="d30b9-156">開啟 [設定] 應用程式，然後選取 **[更新]**  > **[復原]**。</span><span class="sxs-lookup"><span data-stu-id="d30b9-156">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="d30b9-157">選擇 [重設裝置]\*\*\*\* 選項，然後閱讀確認訊息。</span><span class="sxs-lookup"><span data-stu-id="d30b9-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="d30b9-158">確認重設。</span><span class="sxs-lookup"><span data-stu-id="d30b9-158">Confirm the reset.</span></span> <span data-ttu-id="d30b9-159">裝置將重新啟動，並顯示一組旋轉的齒輪和進度列。</span><span class="sxs-lookup"><span data-stu-id="d30b9-159">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="d30b9-160">完成此程序約需 30 分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="d30b9-160">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="d30b9-161">重設完成後，裝置將重新啟動至 [全新] 體驗。</span><span class="sxs-lookup"><span data-stu-id="d30b9-161">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="d30b9-162">重新安裝作業系統</span><span class="sxs-lookup"><span data-stu-id="d30b9-162">Reinstall the operating system</span></span>

<span data-ttu-id="d30b9-163">如果在重新啟動並重設之後裝置仍有問題，您可以在電腦上使用復原工具來重新安裝 HoloLens 作業系統和韌體。</span><span class="sxs-lookup"><span data-stu-id="d30b9-163">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="d30b9-164">重設時，HoloLens 所需的資料會封裝在完整刷新更新（FFU）中，類似于 .iso、.wim 或 .vhd 檔案。</span><span class="sxs-lookup"><span data-stu-id="d30b9-164">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="d30b9-165">了解 FFU 影像檔案格式。</span><span class="sxs-lookup"><span data-stu-id="d30b9-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="d30b9-166">您可以使用 Windows Device Recovery Tool 在 HoloLens (第 1 代) 上安裝全新的作業系統。</span><span class="sxs-lookup"><span data-stu-id="d30b9-166">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="d30b9-167">使用此工具之前，請先查看重新啟動或重設 HoloLens 是否可以解決問題。</span><span class="sxs-lookup"><span data-stu-id="d30b9-167">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="d30b9-168">修復程式可能需要一段時間。</span><span class="sxs-lookup"><span data-stu-id="d30b9-168">The recovery process may take a while.</span></span> <span data-ttu-id="d30b9-169">完成後，將安裝最新版本的 Windows Holographic 軟體。</span><span class="sxs-lookup"><span data-stu-id="d30b9-169">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="d30b9-170">若要使用此工具，您需要一部執行 Windows 10 或更新版本的電腦，並具備至少 4 GB 的可用儲存空間。</span><span class="sxs-lookup"><span data-stu-id="d30b9-170">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="d30b9-171">您無法在虛擬電腦上執行此工具。</span><span class="sxs-lookup"><span data-stu-id="d30b9-171">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="d30b9-172">復原您的 HoloLens</span><span class="sxs-lookup"><span data-stu-id="d30b9-172">Recover your HoloLens</span></span>

1. <span data-ttu-id="d30b9-173">在您的電腦上下載並安裝 [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)。</span><span class="sxs-lookup"><span data-stu-id="d30b9-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="d30b9-174">使用 HoloLens 隨附的 Micro USB 連接線，將 HoloLens (第 1 代) 連線至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="d30b9-174">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="d30b9-175">開啟 Windows Device Recovery Tool 並依照指示操作。</span><span class="sxs-lookup"><span data-stu-id="d30b9-175">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="d30b9-176">如果未自動偵測到 HoloLens （第1代），請選取 **[未偵測到我的裝置]**。</span><span class="sxs-lookup"><span data-stu-id="d30b9-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="d30b9-177">然後按照指示將裝置置於修復模式。</span><span class="sxs-lookup"><span data-stu-id="d30b9-177">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="d30b9-178">手動快閃刷新模式</span><span class="sxs-lookup"><span data-stu-id="d30b9-178">Manual flashing mode</span></span>

<span data-ttu-id="d30b9-179">如果未偵測到您的裝置，請按照下列步驟將它置於快閃刷新模式：</span><span class="sxs-lookup"><span data-stu-id="d30b9-179">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="d30b9-180">斷開裝置的所有電源連接。</span><span class="sxs-lookup"><span data-stu-id="d30b9-180">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="d30b9-181">如果裝置已開啟，請按住 **電源**按鈕，直到裝置完全關閉。</span><span class="sxs-lookup"><span data-stu-id="d30b9-181">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="d30b9-182">按住**調高音量**按鈕，然後點一下 **電源** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="d30b9-182">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="d30b9-183">裝置應該會開啟，並只顯示中間的 LED 燈。</span><span class="sxs-lookup"><span data-stu-id="d30b9-183">The device should start and display only the middle LED light.</span></span>
3. <span data-ttu-id="d30b9-184">將裝置插入您的電腦。</span><span class="sxs-lookup"><span data-stu-id="d30b9-184">Plug the device into your PC.</span></span>
4. <span data-ttu-id="d30b9-185">開啟 Windows Device Recovery Tool。</span><span class="sxs-lookup"><span data-stu-id="d30b9-185">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="d30b9-186">選取 **[未偵測到我的裝置]**，然後選取 **HoloLens**。</span><span class="sxs-lookup"><span data-stu-id="d30b9-186">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="d30b9-187">按照指示復原您的裝置。</span><span class="sxs-lookup"><span data-stu-id="d30b9-187">Follow the instructions to recover your device.</span></span>
