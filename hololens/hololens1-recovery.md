---
title: 重新開機、重設或復原 HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: 如何使用 Windows 裝置復原工具，將映射快閃以 HoloLens 第1代。
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
ms.openlocfilehash: 4840535030cc81f222cb25357474f1c751426e91
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635223"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="26b23-104">重新開機、重設或復原 HoloLens (第1代) </span><span class="sxs-lookup"><span data-stu-id="26b23-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="26b23-105">如果您在 HoloLens 遇到問題，您可能會想要嘗試重新開機或重設，或甚至是使用裝置復原來重新刷新裝置。</span><span class="sxs-lookup"><span data-stu-id="26b23-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="26b23-106">本文將逐步引導您完成依序執行的建議復原步驟。</span><span class="sxs-lookup"><span data-stu-id="26b23-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="26b23-107">如果您想要復原 HoloLens 2，請參閱[復原 HoloLens 2](hololens-recovery.md)，因為該進程不同。</span><span class="sxs-lookup"><span data-stu-id="26b23-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](hololens-recovery.md), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="26b23-108">本文著重于 HoloLens 裝置和軟體。</span><span class="sxs-lookup"><span data-stu-id="26b23-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="26b23-109">如果您的全像是找不到，請參閱 **[HoloLens 環境考慮](hololens-environment-considerations.md)**，以取得改善全像影像品質的因素相關資訊。</span><span class="sxs-lookup"><span data-stu-id="26b23-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="26b23-110">重新啟動</span><span class="sxs-lookup"><span data-stu-id="26b23-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="26b23-111">使用 Cortana 進行安全重新開機</span><span class="sxs-lookup"><span data-stu-id="26b23-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="26b23-112">重新開機 HoloLens 最安全的方式是使用 Cortana，這通常是您在 HoloLens 遇到問題時所要嘗試的第一件事。</span><span class="sxs-lookup"><span data-stu-id="26b23-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="26b23-113">Cortana 在所有裝置上都無法使用。</span><span class="sxs-lookup"><span data-stu-id="26b23-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="26b23-114">Cortana 適用于所有 HoloLens (1 代) 裝置。</span><span class="sxs-lookup"><span data-stu-id="26b23-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="26b23-115">Cortana 可在 Windows Holograpic 2004 版之前的組建 HoloLens 2 裝置上取得。</span><span class="sxs-lookup"><span data-stu-id="26b23-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="26b23-116">開啟您的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="26b23-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="26b23-117">請確定使用者已登入，而裝置未等候密碼解除鎖定。</span><span class="sxs-lookup"><span data-stu-id="26b23-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="26b23-118">說「嗨 Cortana、重新開機」或「嗨 Cortana，重新開機」。</span><span class="sxs-lookup"><span data-stu-id="26b23-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="26b23-119">Cortana 會回應並提示您確認。</span><span class="sxs-lookup"><span data-stu-id="26b23-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="26b23-120">在問題之後等候音效播放，然後說「是」。</span><span class="sxs-lookup"><span data-stu-id="26b23-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="26b23-121">裝置將會重新開機。</span><span class="sxs-lookup"><span data-stu-id="26b23-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="26b23-122">使用電源按鈕來進行安全重新開機</span><span class="sxs-lookup"><span data-stu-id="26b23-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="26b23-123">如果您仍然無法重新開機裝置，請嘗試使用 [ **電源** ] 按鈕重新開機裝置：</span><span class="sxs-lookup"><span data-stu-id="26b23-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="26b23-124">按住 **電源** 按鈕5秒。</span><span class="sxs-lookup"><span data-stu-id="26b23-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="26b23-125">1秒之後，所有五個 Led 都會閃爍，然後從右至左一次慢慢關閉。</span><span class="sxs-lookup"><span data-stu-id="26b23-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="26b23-126">5秒之後，所有 Led 將會關閉，表示成功關機。</span><span class="sxs-lookup"><span data-stu-id="26b23-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="26b23-127">關閉所有 Led 之後，立即停止按下按鈕。</span><span class="sxs-lookup"><span data-stu-id="26b23-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="26b23-128">等候1分鐘，讓關機完成。</span><span class="sxs-lookup"><span data-stu-id="26b23-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="26b23-129">即使關閉顯示之後，關機仍可能仍在進行中。</span><span class="sxs-lookup"><span data-stu-id="26b23-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="26b23-130">按住 **電源** 按鈕的1秒，再次開啟裝置。</span><span class="sxs-lookup"><span data-stu-id="26b23-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="26b23-131">使用 Windows 裝置入口網站進行安全重新開機</span><span class="sxs-lookup"><span data-stu-id="26b23-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="26b23-132">在此程式中，必須將 HoloLens 設定為開發人員裝置。</span><span class="sxs-lookup"><span data-stu-id="26b23-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="26b23-133">若要深入瞭解，請參閱[Windows 裝置入口網站](/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="26b23-133">Learn more at [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="26b23-134">如果上述程式無法運作，請嘗試使用[Windows 裝置入口網站](/windows/mixed-reality/using-the-windows-device-portal)重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="26b23-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="26b23-135">在右上角尋找重新開機或關閉裝置的選項。</span><span class="sxs-lookup"><span data-stu-id="26b23-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="26b23-136">執行不安全的強制重新開機</span><span class="sxs-lookup"><span data-stu-id="26b23-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="26b23-137">如果先前的方法未重新開機 HoloLens，請強制重新開機。</span><span class="sxs-lookup"><span data-stu-id="26b23-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="26b23-138">這個方法相當於移除並重新安裝電池。</span><span class="sxs-lookup"><span data-stu-id="26b23-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="26b23-139">這是危險的，因為它可能會讓您的裝置處於損毀的狀態。</span><span class="sxs-lookup"><span data-stu-id="26b23-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="26b23-140">如果發生這種情況，您必須將 HoloLens 閃爍。</span><span class="sxs-lookup"><span data-stu-id="26b23-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="26b23-141">這是可能有害的方法，只有在先前提到的方法無法運作時，才應該使用。</span><span class="sxs-lookup"><span data-stu-id="26b23-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="26b23-142">按住 **電源** 按鈕至少10秒鐘。</span><span class="sxs-lookup"><span data-stu-id="26b23-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="26b23-143">您可以保留按鈕超過10秒。</span><span class="sxs-lookup"><span data-stu-id="26b23-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="26b23-144">您可以放心地忽略任何 LED 的活動。</span><span class="sxs-lookup"><span data-stu-id="26b23-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="26b23-145">放開按鈕並等候2-3 秒。</span><span class="sxs-lookup"><span data-stu-id="26b23-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="26b23-146">按住 **電源** 按鈕的1秒。</span><span class="sxs-lookup"><span data-stu-id="26b23-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="26b23-147">如果您仍然遇到問題，請按 [ **電源** ] 按鈕4秒，直到所有電池指示器淡出，而螢幕停止顯示全像全像。</span><span class="sxs-lookup"><span data-stu-id="26b23-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="26b23-148">等候1分鐘，然後再按一次 **電源** 按鈕來開啟裝置。</span><span class="sxs-lookup"><span data-stu-id="26b23-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="26b23-149">返回至上一版的 HoloLens (第一代) </span><span class="sxs-lookup"><span data-stu-id="26b23-149">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="26b23-150">在某些情況下，您可能想要回到舊版的 HoloLens 軟體。</span><span class="sxs-lookup"><span data-stu-id="26b23-150">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="26b23-151">若要這麼做，您可以使用 Windows 裝置復原工具，將 HoloLens 重設為較早的版本。</span><span class="sxs-lookup"><span data-stu-id="26b23-151">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="26b23-152">回到較舊的版本會刪除您的個人檔案和設定。</span><span class="sxs-lookup"><span data-stu-id="26b23-152">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="26b23-153">若要回到舊版的 HoloLens 1，請依照下列步驟執行：</span><span class="sxs-lookup"><span data-stu-id="26b23-153">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="26b23-154">請確定您沒有任何電話或 Windows 裝置插入電腦。</span><span class="sxs-lookup"><span data-stu-id="26b23-154">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="26b23-155">在您的電腦上，下載[Windows 的裝置復原工具 (WDRT) ](https://support.microsoft.com/help/12379)。</span><span class="sxs-lookup"><span data-stu-id="26b23-155">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="26b23-156">下載[HoloLens 周年更新修復套件](https://aka.ms/hololensrecovery)。</span><span class="sxs-lookup"><span data-stu-id="26b23-156">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="26b23-157">當下載完成時，開啟 [檔案 **瀏覽器**  >  **下載**]。</span><span class="sxs-lookup"><span data-stu-id="26b23-157">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="26b23-158">在您剛剛下載的壓縮資料夾上按一下滑鼠右鍵，然後選取 [**解壓縮全部**  >  **解壓縮**] 將它解壓縮。</span><span class="sxs-lookup"><span data-stu-id="26b23-158">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="26b23-159">使用隨附的微型 USB 纜線連線您的電腦 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="26b23-159">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="26b23-160"> (即使您已經使用其他纜線來連接 HoloLens，這項功能的效果最好。 ) </span><span class="sxs-lookup"><span data-stu-id="26b23-160">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="26b23-161">WDRT 會自動偵測您的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="26b23-161">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="26b23-162">選取 **Microsoft HoloLens** 圖格。</span><span class="sxs-lookup"><span data-stu-id="26b23-162">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="26b23-163">在下一個畫面中，選取 [ **手動封裝選取專案** ]，然後選擇您在步驟4解壓縮的資料夾中所包含的安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="26b23-163">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="26b23-164"> (尋找副檔名為 ffu 的檔案 ) </span><span class="sxs-lookup"><span data-stu-id="26b23-164">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="26b23-165">選取 [ **安裝軟體**]，並遵循指示進行。</span><span class="sxs-lookup"><span data-stu-id="26b23-165">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="26b23-166">如果 WDRT 偵測不到您的 HoloLens，請嘗試重新開機您的電腦。</span><span class="sxs-lookup"><span data-stu-id="26b23-166">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="26b23-167">如果無法運作，請選取 [**未偵測到我的裝置**]，選取 [ **Microsoft HoloLens**]，然後依照指示進行。</span><span class="sxs-lookup"><span data-stu-id="26b23-167">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="26b23-168">重設為原廠設定</span><span class="sxs-lookup"><span data-stu-id="26b23-168">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="26b23-169">電池需要至少40% 的費用才能重設。</span><span class="sxs-lookup"><span data-stu-id="26b23-169">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="26b23-170">如果您的 HoloLens 仍有問題，請嘗試將其重設為原廠狀態。</span><span class="sxs-lookup"><span data-stu-id="26b23-170">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="26b23-171">此步驟會保留安裝在其上的 Windows 全息版軟體的版本，並將其他內容傳回給原廠設定。</span><span class="sxs-lookup"><span data-stu-id="26b23-171">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="26b23-172">如果您重設裝置，將會清除您的所有個人資料、應用程式和設定，包括 TPM 重設資訊。</span><span class="sxs-lookup"><span data-stu-id="26b23-172">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="26b23-173">重設只會安裝最新安裝的 Windows 全息版。</span><span class="sxs-lookup"><span data-stu-id="26b23-173">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="26b23-174">您必須重做所有的初始化步驟， (校正、連線至 Wi-fi、建立使用者帳戶、下載應用程式等) 。</span><span class="sxs-lookup"><span data-stu-id="26b23-174">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="26b23-175">開啟設定應用程式，然後選取 [**更新** 復原]  >  \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="26b23-175">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="26b23-176">選取 [ **重設裝置** ] 選項，並閱讀確認訊息。</span><span class="sxs-lookup"><span data-stu-id="26b23-176">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="26b23-177">確認重設。</span><span class="sxs-lookup"><span data-stu-id="26b23-177">Confirm the reset.</span></span> <span data-ttu-id="26b23-178">裝置將會重新開機，並顯示一組旋轉的齒輪和進度列。</span><span class="sxs-lookup"><span data-stu-id="26b23-178">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="26b23-179">等候約30分鐘，讓此程式完成。</span><span class="sxs-lookup"><span data-stu-id="26b23-179">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="26b23-180">完成時，裝置將會重新開機為「現成」體驗。</span><span class="sxs-lookup"><span data-stu-id="26b23-180">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="26b23-181">重新安裝作業系統</span><span class="sxs-lookup"><span data-stu-id="26b23-181">Reinstall the operating system</span></span>

<span data-ttu-id="26b23-182">如果裝置在重新開機和重設後仍有問題，您可以在電腦上使用復原工具，重新安裝 HoloLens 作業系統和固件。</span><span class="sxs-lookup"><span data-stu-id="26b23-182">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="26b23-183">HoloLens 重設所需的資料會封裝在完整的 Flash 更新 (FFU) ，類似于 .iso、.wim 或 .vhd 檔案。</span><span class="sxs-lookup"><span data-stu-id="26b23-183">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="26b23-184">深入瞭解 FFU 影像檔案格式。</span><span class="sxs-lookup"><span data-stu-id="26b23-184">Learn about FFU image file formats.</span></span>](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="26b23-185">您可以使用 Windows 裝置復原工具，在 HoloLens (第1代) 上安裝新的作業系統。</span><span class="sxs-lookup"><span data-stu-id="26b23-185">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="26b23-186">使用該工具之前，請先查看是否重新開機或重設您的 HoloLens，以修正問題。</span><span class="sxs-lookup"><span data-stu-id="26b23-186">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="26b23-187">修復程式可能需要一段時間。</span><span class="sxs-lookup"><span data-stu-id="26b23-187">The recovery process may take a while.</span></span> <span data-ttu-id="26b23-188">完成時，將會安裝最新版的 Windows 全像攝影軟體。</span><span class="sxs-lookup"><span data-stu-id="26b23-188">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="26b23-189">若要使用此工具，您需要執行 Windows 10 或更新版本且至少有 4 GB 可用儲存空間的電腦。</span><span class="sxs-lookup"><span data-stu-id="26b23-189">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="26b23-190">您無法在虛擬機器上執行此工具。</span><span class="sxs-lookup"><span data-stu-id="26b23-190">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="26b23-191">復原您的 HoloLens</span><span class="sxs-lookup"><span data-stu-id="26b23-191">Recover your HoloLens</span></span>

1. <span data-ttu-id="26b23-192">在您的電腦上下載並安裝[Windows 的裝置修復工具](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)。</span><span class="sxs-lookup"><span data-stu-id="26b23-192">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="26b23-193">使用 HoloLens 隨附的微型 USB 纜線，連線 HoloLens (第一代) 到電腦上。</span><span class="sxs-lookup"><span data-stu-id="26b23-193">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="26b23-194">開啟 Windows 裝置復原工具，並遵循指示進行。</span><span class="sxs-lookup"><span data-stu-id="26b23-194">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="26b23-195">如果未自動偵測到 HoloLens (第1代) ，請選取 [**我的裝置未偵測到**]。</span><span class="sxs-lookup"><span data-stu-id="26b23-195">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="26b23-196">然後遵循指示，讓裝置進入修復模式。</span><span class="sxs-lookup"><span data-stu-id="26b23-196">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="26b23-197">手動閃爍模式</span><span class="sxs-lookup"><span data-stu-id="26b23-197">Manual flashing mode</span></span>

<span data-ttu-id="26b23-198">如果未偵測到您的裝置，請遵循下列步驟使其進入閃爍模式：</span><span class="sxs-lookup"><span data-stu-id="26b23-198">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="26b23-199">從任何電源線拔下裝置。</span><span class="sxs-lookup"><span data-stu-id="26b23-199">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="26b23-200">如果裝置已開啟，請按住 **電源** 按鈕，直到完全關閉為止。</span><span class="sxs-lookup"><span data-stu-id="26b23-200">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="26b23-201">按住 **音量** 按鈕，並短暫地點一下 **電源** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="26b23-201">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="26b23-202">裝置應該會啟動，而且只會顯示中間 LED。</span><span class="sxs-lookup"><span data-stu-id="26b23-202">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="26b23-203">將裝置插入您的電腦。</span><span class="sxs-lookup"><span data-stu-id="26b23-203">Plug the device into your PC.</span></span>
4. <span data-ttu-id="26b23-204">開啟 Windows 裝置修復工具。</span><span class="sxs-lookup"><span data-stu-id="26b23-204">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="26b23-205">選取 [**我的裝置未偵測到**]，然後 **HoloLens**]。</span><span class="sxs-lookup"><span data-stu-id="26b23-205">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="26b23-206">請依照指示來復原您的裝置。</span><span class="sxs-lookup"><span data-stu-id="26b23-206">Follow the instructions to recover your device.</span></span>
