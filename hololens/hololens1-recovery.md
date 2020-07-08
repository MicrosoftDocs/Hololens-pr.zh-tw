---
title: 重新啟動、重設或復原 HoloLens 1
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
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
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 36192315e234db16c7747457e69d6d6281c31bfe
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857731"
---
# <span data-ttu-id="a454f-104">重新開機、重設或復原 HoloLens （第1代）</span><span class="sxs-lookup"><span data-stu-id="a454f-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="a454f-105">如果您遇到 HoloLens 問題，您可以嘗試嘗試重新啟動、重設或甚至是使用裝置復原功能來重新快閃刷新。</span><span class="sxs-lookup"><span data-stu-id="a454f-105">If you're experiencing problems with your HoloLens you may want to try a restart, reset, or even re-flash with device recovery.</span></span>

<span data-ttu-id="a454f-106">如果您的 HoloLens 運作不良，以下是您可以嘗試的一些方法。</span><span class="sxs-lookup"><span data-stu-id="a454f-106">Here are some things to try if your HoloLens isn't running well.</span></span>  <span data-ttu-id="a454f-107">本文將逐步引導您逐步完成建議的復原步驟。</span><span class="sxs-lookup"><span data-stu-id="a454f-107">This article will guide you through the recommended recovery steps in succession.</span></span>

<span data-ttu-id="a454f-108">如果要復原 HoloLens 2，請檢視 [復原 HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery) 的頁面，因為過程會有所不同。</span><span class="sxs-lookup"><span data-stu-id="a454f-108">If you are looking to recover a HoloLens 2, please view the page for [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as there are differences in the processes.</span></span>

<span data-ttu-id="a454f-109">本文著重於 HoloLens 裝置和軟體，如果您的全像投影沒有正確顯示，[本文](hololens-environment-considerations.md)會討論改進全像投影品質的環境因素。</span><span class="sxs-lookup"><span data-stu-id="a454f-109">This article focuses on the HoloLens device and software, if your holograms don't look right, [this article](hololens-environment-considerations.md) talks about environmental factors that improve hologram quality.</span></span>

## <span data-ttu-id="a454f-110">重新啟動</span><span class="sxs-lookup"><span data-stu-id="a454f-110">Restart</span></span>

### <span data-ttu-id="a454f-111">使用 Cortana 執行安全重新啟動</span><span class="sxs-lookup"><span data-stu-id="a454f-111">Perform a safe restart by using Cortana</span></span>

<span data-ttu-id="a454f-112">HoloLens 重新啟動最安全的方法是使用 Cortana。</span><span class="sxs-lookup"><span data-stu-id="a454f-112">The safest way to restart the HoloLens is by using Cortana.</span></span> <span data-ttu-id="a454f-113">這通常是 HoloLens 發生問題時的簡單第一步驟。</span><span class="sxs-lookup"><span data-stu-id="a454f-113">This is generally an easy first-step when experiencing an issue with HoloLens.</span></span> 

> [!NOTE]
> <span data-ttu-id="a454f-114">並非所有裝置都提供 Cortana 功能。</span><span class="sxs-lookup"><span data-stu-id="a454f-114">Cortana is not avalible on all devices.</span></span> <span data-ttu-id="a454f-115">Cortana 適用於所有 HoloLens (第 1 代)裝置。</span><span class="sxs-lookup"><span data-stu-id="a454f-115">Cortana is avalible to all HoloLens (1st Gen) devices.</span></span>
> <span data-ttu-id="a454f-116">在 Windows Holograpic 的版本 2004 更新之前，HoloLens 2 裝置可使用 Cortana。</span><span class="sxs-lookup"><span data-stu-id="a454f-116">Cortana is avalible on HoloLens 2 devices on a build prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="a454f-117">戴上您的裝置</span><span class="sxs-lookup"><span data-stu-id="a454f-117">Put on your device</span></span>
1. <span data-ttu-id="a454f-118">請確認裝置已電源開啟，使用者已登入，且裝置並非正在等待密碼解鎖。</span><span class="sxs-lookup"><span data-stu-id="a454f-118">Make sure it's powered on, a user is logged in, and the device is not waiting for a password to unlock it.</span></span>
1. <span data-ttu-id="a454f-119">請說出「嗨 Cortana，重新開機」或「嗨 Cortana，重新啟動」。</span><span class="sxs-lookup"><span data-stu-id="a454f-119">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
1. <span data-ttu-id="a454f-120">當她確認收到時會要求您確認。</span><span class="sxs-lookup"><span data-stu-id="a454f-120">When she acknowledges she will ask you for confirmation.</span></span> <span data-ttu-id="a454f-121">完成問題後，請稍候等待播放音效，表明她在聽您說話，然後說出「是」。</span><span class="sxs-lookup"><span data-stu-id="a454f-121">Wait a second for a sound to play after she has finished her question, indicating she is listening to you and then say "Yes."</span></span>
1. <span data-ttu-id="a454f-122">裝置現在會重新啟動。</span><span class="sxs-lookup"><span data-stu-id="a454f-122">The device will now restart.</span></span>

### <span data-ttu-id="a454f-123">使用電源按鈕執行安全重新啟動</span><span class="sxs-lookup"><span data-stu-id="a454f-123">Perform a safe restart by using the power button</span></span>

<span data-ttu-id="a454f-124">如果您仍然無法重新啟動裝置，您可以嘗試使用電源按鈕來重新啟動裝置：</span><span class="sxs-lookup"><span data-stu-id="a454f-124">If you still can't restart your device, you can try to restart it by using the power button:</span></span>

1. <span data-ttu-id="a454f-125">按住電源按鈕五秒。</span><span class="sxs-lookup"><span data-stu-id="a454f-125">Press and hold the power button for five seconds.</span></span>
   1. <span data-ttu-id="a454f-126">一秒後，您會看到所有五個 LED 都亮起，然後從右至左慢慢關閉。</span><span class="sxs-lookup"><span data-stu-id="a454f-126">After one second, you will see all five LEDs illuminate, then slowly turn off from right to left.</span></span>
   1. <span data-ttu-id="a454f-127">五秒後，所有 LED 都會關閉，指出已成功發出關機命令。</span><span class="sxs-lookup"><span data-stu-id="a454f-127">After five seconds, all LEDs will be off, indicating the shutdown command was issued successfully.</span></span>
   1. <span data-ttu-id="a454f-128">請注意，關閉所有 LED 之後，請務必立即停止按下按鈕。</span><span class="sxs-lookup"><span data-stu-id="a454f-128">Note that it's important to stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="a454f-129">等待一分鐘，讓關閉完全成功。</span><span class="sxs-lookup"><span data-stu-id="a454f-129">Wait one minute for the shutdown to cleanly succeed.</span></span> <span data-ttu-id="a454f-130">請注意，即使關閉了顯示器，關機可能仍在進行中。</span><span class="sxs-lookup"><span data-stu-id="a454f-130">Note that the shutdown may still be in progress even if the displays are turned off.</span></span>
1. <span data-ttu-id="a454f-131">按住電源按鈕一秒，以再次電源開啟裝置。</span><span class="sxs-lookup"><span data-stu-id="a454f-131">Power on the device again by pressing and holding the power button for one second.</span></span>

### <span data-ttu-id="a454f-132">使用 Windows 裝置入口網站來執行安全重新啟動</span><span class="sxs-lookup"><span data-stu-id="a454f-132">Perform a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="a454f-133">若要這麼做，您必須將 HoloLens 設定為開發人員裝置。</span><span class="sxs-lookup"><span data-stu-id="a454f-133">To do this, HoloLens has to be configured as a developer device.</span></span>  
> <span data-ttu-id="a454f-134">閱讀有關 [Windows 裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)的更多資訊。</span><span class="sxs-lookup"><span data-stu-id="a454f-134">Read more about [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="a454f-135">如果上述程式無法運作，您可以使用 [Windows 裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)來嘗試重新啟動裝置。</span><span class="sxs-lookup"><span data-stu-id="a454f-135">If the previous procedure doesn't work, you can try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="a454f-136">右上角有一個可重新啟動或關閉裝置的選項。</span><span class="sxs-lookup"><span data-stu-id="a454f-136">In the upper right corner, there is an option to restart or shut down the device.</span></span>

### <span data-ttu-id="a454f-137">執行不安全的強制重新啟動</span><span class="sxs-lookup"><span data-stu-id="a454f-137">Perform an unsafe forced restart</span></span>

<span data-ttu-id="a454f-138">如果上述所有方法都無法順利重新啟動您的裝置，您可以強制重新啟動。</span><span class="sxs-lookup"><span data-stu-id="a454f-138">If none of the previous methods are able to successfully restart your device, you can force a restart.</span></span> <span data-ttu-id="a454f-139">此方法等同從 HoloLens 拉出電池。</span><span class="sxs-lookup"><span data-stu-id="a454f-139">This method is equivalent to pulling the battery from the HoloLens.</span></span>  <span data-ttu-id="a454f-140">這是危險的操作，可能會讓您的裝置損毀。</span><span class="sxs-lookup"><span data-stu-id="a454f-140">It is a dangerous operation which may leave your device in a corrupt state.</span></span>  <span data-ttu-id="a454f-141">如果發生這種情況，您必須快閃刷新您的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="a454f-141">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="a454f-142">這是一種可能有害的方法，應僅在上述方法均無效的情況下使用。</span><span class="sxs-lookup"><span data-stu-id="a454f-142">This is a potentially harmful method and should only be used in the event none of the above methods work.</span></span>

1. <span data-ttu-id="a454f-143">按住電源按鈕至少 10 秒。</span><span class="sxs-lookup"><span data-stu-id="a454f-143">Press and hold the power button for at least 10 seconds.</span></span>
   - <span data-ttu-id="a454f-144">您可將按鈕按住 10 秒以上。</span><span class="sxs-lookup"><span data-stu-id="a454f-144">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="a454f-145">您可以放心忽略任何 LED 活動。</span><span class="sxs-lookup"><span data-stu-id="a454f-145">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="a454f-146">放開按鈕並等待二到三秒。</span><span class="sxs-lookup"><span data-stu-id="a454f-146">Release the button and wait for two or three seconds.</span></span>
1. <span data-ttu-id="a454f-147">按住電源按鈕一秒，以再次電源開啟裝置。</span><span class="sxs-lookup"><span data-stu-id="a454f-147">Power on the device again by pressing and holding the power button for one second.</span></span>
<span data-ttu-id="a454f-148">如果仍有問題，請按電源按鈕 4 秒，直到所有電池指示器都淡出，且畫面停止顯示全像投影。</span><span class="sxs-lookup"><span data-stu-id="a454f-148">If you're still having problems, press the power button for 4 seconds, until all of the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="a454f-149">等待 1 分鐘，然後再按一次電源按鈕以開啟裝置。</span><span class="sxs-lookup"><span data-stu-id="a454f-149">Wait 1 minute, then press the power button again to turn on the device.</span></span>

## <span data-ttu-id="a454f-150">重設成出廠預設值</span><span class="sxs-lookup"><span data-stu-id="a454f-150">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="a454f-151">若要重設，電池至少需要充電 40%。</span><span class="sxs-lookup"><span data-stu-id="a454f-151">The battery needs at least 40 percent charge to reset.</span></span>

<span data-ttu-id="a454f-152">如果您的 HoloLens 在重新啟動後仍有問題，請嘗試將其重設為出廠狀態。</span><span class="sxs-lookup"><span data-stu-id="a454f-152">If your HoloLens is still experiencing issues after restarting, try resetting it to factory state.</span></span>  <span data-ttu-id="a454f-153">重設您的 HoloLens 會保留所安裝的 Windows Holographic 軟體版本，並將其他所有內容復原為出廠設定。</span><span class="sxs-lookup"><span data-stu-id="a454f-153">Resetting your HoloLens keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

<span data-ttu-id="a454f-154">如果重設裝置，您所有\*\*全部的個人資料、應用程式和設定都會被清除，包含 TPM 重設。</span><span class="sxs-lookup"><span data-stu-id="a454f-154">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset.</span></span> <span data-ttu-id="a454f-155">重設只會安裝最新版的 Windows Holographic，而您必須重做所有初始化步驟 (校準、連線至 Wi-Fi、建立使用者帳戶、下載應用程式等等)。</span><span class="sxs-lookup"><span data-stu-id="a454f-155">Resetting will only install the latest installed version of Windows Holographic and you will have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so forth).</span></span>

1. <span data-ttu-id="a454f-156">啟動 [設定] 應用程式，然後選擇 [更新]\*\*\*\* > [重設]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a454f-156">Launch the Settings app, and then select **Update** > **Reset**.</span></span>
1. <span data-ttu-id="a454f-157">選擇 [重設裝置]\*\*\*\* 選項，然後閱讀確認訊息。</span><span class="sxs-lookup"><span data-stu-id="a454f-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="a454f-158">如果您同意重設裝置，裝置將會重新啟動，並顯示一組旋轉的齒輪，並顯示進度列。</span><span class="sxs-lookup"><span data-stu-id="a454f-158">If you agree to reset your device, the device will restart and display a set of spinning gears with a progress bar.</span></span>
1. <span data-ttu-id="a454f-159">完成此程序約需 30 分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="a454f-159">Wait about 30 minutes for this process to complete.</span></span>
1. <span data-ttu-id="a454f-160">重設將會完成，且裝置將重新啟動即可使用。</span><span class="sxs-lookup"><span data-stu-id="a454f-160">The reset will complete and the device will restart into the out-of-the-box experience.</span></span>

## <span data-ttu-id="a454f-161">重新安裝作業系統</span><span class="sxs-lookup"><span data-stu-id="a454f-161">Re-install the operating system</span></span>

<span data-ttu-id="a454f-162">如果在重新啟動並重設之後裝置仍有問題，您可以在電腦上使用復原工具來重新安裝 HoloLens 的作業系統和韌體。</span><span class="sxs-lookup"><span data-stu-id="a454f-162">If the device is still having a problem after rebooting and resetting, you can use a recovery tool on your computer to reinstall the HoloLens' operating system and firmware.</span></span>  

<span data-ttu-id="a454f-163">HoloLens 必須要重設的所有資料都封裝在 Full Flash Update (ffu) 中。</span><span class="sxs-lookup"><span data-stu-id="a454f-163">All of the data HoloLens needs to reset is packaged in a Full Flash Update (ffu).</span></span>  <span data-ttu-id="a454f-164">這類似於 iso、wim 或 vhd。</span><span class="sxs-lookup"><span data-stu-id="a454f-164">This is similar to an iso, wim, or vhd.</span></span>  [<span data-ttu-id="a454f-165">了解 FFU 影像檔案格式。</span><span class="sxs-lookup"><span data-stu-id="a454f-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="a454f-166">如有必要，您可以使用 Windows Device Recovery Tool 在 HoloLens (第 1 代) 上安裝全新的作業系統。</span><span class="sxs-lookup"><span data-stu-id="a454f-166">If necessary, you can install a completely new operating system on your HoloLens (1st gen) with the Windows Device Recovery Tool.</span></span>

<span data-ttu-id="a454f-167">使用此工具之前，請確定重新啟動或重設 HoloLens 是否可以解決問題。</span><span class="sxs-lookup"><span data-stu-id="a454f-167">Before you use this tool, determine if restarting or resetting your HoloLens fixes the problem.</span></span> <span data-ttu-id="a454f-168">復原程式可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="a454f-168">The recovery process may take some time.</span></span>  <span data-ttu-id="a454f-169">完成後，將安裝針對您的 HoloLens 核可的最新版本 Windows Holographic 軟體。</span><span class="sxs-lookup"><span data-stu-id="a454f-169">When you're done, the latest version of the Windows Holographic software approved for your HoloLens will be installed.</span></span>

<span data-ttu-id="a454f-170">若要使用此工具，您需要一部執行 Windows 10 或更高版本的電腦，具備至少 4 GB 的可用儲存空間。</span><span class="sxs-lookup"><span data-stu-id="a454f-170">To use the tool, you'll need a computer running Windows 10 or later, with at least 4 GB of free storage space.</span></span>  <span data-ttu-id="a454f-171">請注意，您無法在虛擬機器上執行此工具。</span><span class="sxs-lookup"><span data-stu-id="a454f-171">Please note that you can't run this tool on a virtual machine.</span></span>

### <span data-ttu-id="a454f-172">復原您的 HoloLens：</span><span class="sxs-lookup"><span data-stu-id="a454f-172">Recover your HoloLens:</span></span>

1. <span data-ttu-id="a454f-173">在您的電腦上下載並安裝 [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)。</span><span class="sxs-lookup"><span data-stu-id="a454f-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="a454f-174">使用 HoloLens 隨附的 Micro USB 連接線，將 HoloLens (第 1 代) 連線至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="a454f-174">Connect the HoloLens (1st gen) to your computer using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="a454f-175">執行 Windows Device Recovery Tool 並依照指示操作。</span><span class="sxs-lookup"><span data-stu-id="a454f-175">Run the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="a454f-176">如果系統未自動偵測到 HoloLens (第 1 代)，請選取 [未偵測到我的裝置]\*\*\*\* ，並依照指示將裝置置於復原模式。</span><span class="sxs-lookup"><span data-stu-id="a454f-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected** and follow the instructions to put your device into recovery mode.</span></span>

### <span data-ttu-id="a454f-177">手動快閃刷新模式：</span><span class="sxs-lookup"><span data-stu-id="a454f-177">Manual Flashing Mode:</span></span>

<span data-ttu-id="a454f-178">如果您未偵測到您的裝置，請使用以下方法，將其手動置於快閃刷新模式。</span><span class="sxs-lookup"><span data-stu-id="a454f-178">In the event that your device is not being detected please use the following method to manually place it into flashing mode.</span></span>

1. <span data-ttu-id="a454f-179">中斷所有電源與裝置的連接。</span><span class="sxs-lookup"><span data-stu-id="a454f-179">Unplug the device from all power sources.</span></span>
1. <span data-ttu-id="a454f-180">如果裝置處於開啟狀態，請按住電源按鈕，直到完全關閉。</span><span class="sxs-lookup"><span data-stu-id="a454f-180">If the device is on please hold down the power button until it is completely off.</span></span>
1. <span data-ttu-id="a454f-181">按住**調高音量**按鈕，然後短暫點選**電源按鈕**。</span><span class="sxs-lookup"><span data-stu-id="a454f-181">Hold the **Volume Up** button, and breifly tap the **Power button**.</span></span> 
1. <span data-ttu-id="a454f-182">裝置應該會開機，然後只顯示中間的 LED。</span><span class="sxs-lookup"><span data-stu-id="a454f-182">The device should boot and then display only the middle LED light.</span></span>
1. <span data-ttu-id="a454f-183">將裝置插入您的電腦。</span><span class="sxs-lookup"><span data-stu-id="a454f-183">Plug the device into your PC.</span></span>
1. <span data-ttu-id="a454f-184">啟動 Windows Device Recovery Tool。</span><span class="sxs-lookup"><span data-stu-id="a454f-184">Launch Windows Device Recovery Tool.</span></span>
1. <span data-ttu-id="a454f-185">您必須選取\*未偵測到我的裝置\*\*，然後選取 **HoloLens**。</span><span class="sxs-lookup"><span data-stu-id="a454f-185">You will need to select \*My device was not detected\*\*, and then select **HoloLens**.</span></span> 
1. <span data-ttu-id="a454f-186">按照指示復原您的裝置。</span><span class="sxs-lookup"><span data-stu-id="a454f-186">Follow the instructions to recover your device.</span></span>
