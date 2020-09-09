---
title: HoloLens 2 版本資訊
description: 瞭解每個新版 HoloLens 2 發行版本中的更新。
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 06/9/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 0fe78d4b668523de4faa66a64f54c14760a81b12
ms.sourcegitcommit: bddd470ac475dd8fc7b69e8904d18082a83f39e0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/08/2020
ms.locfileid: "10997214"
---
# <span data-ttu-id="424cc-103">HoloLens 2 版本資訊</span><span class="sxs-lookup"><span data-stu-id="424cc-103">HoloLens 2 release notes</span></span>

<span data-ttu-id="424cc-104">為了確保您在 HoloLens 裝置上擁有生產力的體驗，我們會繼續發行功能、錯誤和安全性更新。</span><span class="sxs-lookup"><span data-stu-id="424cc-104">To ensure you have a productive experience with your HoloLens devices, we continue to release feature, bug, and security updates.</span></span> <span data-ttu-id="424cc-105">在此頁面上，您可以查看每個月的 HoloLens 新功能。</span><span class="sxs-lookup"><span data-stu-id="424cc-105">On this page, you can see what’s new for HoloLens each month.</span></span> <span data-ttu-id="424cc-106">若要取得最新的 HoloLens 2 完整快閃記憶體更新 (FFU) 若要透過 [高級恢復隨附裝置快閃](hololens-recovery.md#clean-reflash-the-device)，請 [在此下載](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="424cc-106">To get the latest HoloLens 2 Full Flash Update (FFU) to [flash your device via Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device), [download it here](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="424cc-107">下載會保持最新狀態，並提供最新的一般可用組建。</span><span class="sxs-lookup"><span data-stu-id="424cc-107">The download is kept up to date and provides the latest generally available build.</span></span>

>[!NOTE]
> <span data-ttu-id="424cc-108">若要閱讀 HoloLens 模擬器版本資訊，請 [造訪](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)封存。</span><span class="sxs-lookup"><span data-stu-id="424cc-108">To read HoloLens Emulator release notes, [visit the archive](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive).</span></span>

## <span data-ttu-id="424cc-109">Windows 全息版 2004-2020 年9月更新</span><span class="sxs-lookup"><span data-stu-id="424cc-109">Windows Holographic, version 2004 - September 2020 Update</span></span>
- <span data-ttu-id="424cc-110">組建19041.1117</span><span class="sxs-lookup"><span data-stu-id="424cc-110">Build 19041.1117</span></span>

<span data-ttu-id="424cc-111">更新中的改進與修正：</span><span class="sxs-lookup"><span data-stu-id="424cc-111">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="424cc-112">解決當 package.appxmanifest 中有 SupportsMultipleInstances = "true" 時，Visual Studio 無法調試應用程式的問題。</span><span class="sxs-lookup"><span data-stu-id="424cc-112">Addresses an issue that prevented Visual Studio from debugging an application when SupportsMultipleInstances=”true” is present in the appxmanifest.</span></span>
- <span data-ttu-id="424cc-113">此版本包含 NCSI proxy 偵測修正，以解決透過網路 proxy 的網際網路偵測失敗的問題。</span><span class="sxs-lookup"><span data-stu-id="424cc-113">This release includes NCSI proxy detection fix to address failed Internet detection over network proxy.</span></span> <span data-ttu-id="424cc-114">NCSI 可以使用電腦 proxy 和每個設定檔 proxy 進行網際網路連線偵測。</span><span class="sxs-lookup"><span data-stu-id="424cc-114">NCSI can use machine proxy and per-profile proxy for Internet connectivity detection.</span></span> <span data-ttu-id="424cc-115">在未來版本中，NCSI 將支援每個使用者的 proxy。</span><span class="sxs-lookup"><span data-stu-id="424cc-115">Per-user proxy will be supported by NCSI in future release.</span></span>
- <span data-ttu-id="424cc-116">在大多數 Windows Mixed Reality 裝置上，當使用者的頭位於想要往前的位置時，轉寄方向向量會平行于地面。</span><span class="sxs-lookup"><span data-stu-id="424cc-116">On most Windows Mixed Reality devices, the forward direction vector is parallel to the ground when the user's head is in a neutral position looking forward.</span></span> <span data-ttu-id="424cc-117">不過，較舊版本的 HoloLens 2 會將向量調整為與顯示器垂直，而不是相對於理想方向向下傾斜幾度。</span><span class="sxs-lookup"><span data-stu-id="424cc-117">However, earlier versions of HoloLens 2 aligned the vector to be perpendicular to the display panels instead, which is tilted downward a few degrees relative to the ideal orientation.</span></span> <span data-ttu-id="424cc-118">較新版本的 HoloLens 2 已修正此情況，以確保各個外形規格的語義一致性。</span><span class="sxs-lookup"><span data-stu-id="424cc-118">Newer versions of HoloLens 2 have corrected this to ensure semantic consistency across form factors.</span></span>
- <span data-ttu-id="424cc-119">改良的手追蹤穩定性，在特定情況下會導致追蹤損失較少。</span><span class="sxs-lookup"><span data-stu-id="424cc-119">Improved hand tracking robustness that will result in fewer tracking losses in specific scenarios.</span></span>
- <span data-ttu-id="424cc-120">此版本包含可改善音訊時間戳記品質的修正程式，這可能已參與視頻捕獲問題。</span><span class="sxs-lookup"><span data-stu-id="424cc-120">This release contains a fix to improve audio timestamp quality which may have contributed to video capture issues.</span></span>

## <span data-ttu-id="424cc-121">Windows 全息版 1903-2020 年9月更新</span><span class="sxs-lookup"><span data-stu-id="424cc-121">Windows Holographic, version 1903 - September 2020 Update</span></span>
- <span data-ttu-id="424cc-122">組建18362.1079</span><span class="sxs-lookup"><span data-stu-id="424cc-122">Build 18362.1079</span></span>

<span data-ttu-id="424cc-123">更新中的改進與修正：</span><span class="sxs-lookup"><span data-stu-id="424cc-123">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="424cc-124">在大多數 Windows Mixed Reality 裝置上，當使用者的頭位於想要往前的位置時，轉寄方向向量會平行于地面。</span><span class="sxs-lookup"><span data-stu-id="424cc-124">On most Windows Mixed Reality devices, the forward direction vector is parallel to the ground when the user's head is in a neutral position looking forward.</span></span> <span data-ttu-id="424cc-125">不過，較舊版本的 HoloLens 2 會將向量調整為與顯示器垂直，而不是相對於理想方向向下傾斜幾度。</span><span class="sxs-lookup"><span data-stu-id="424cc-125">However, earlier versions of HoloLens 2 aligned the vector to be perpendicular to the display panels instead, which is tilted downward a few degrees relative to the ideal orientation.</span></span> <span data-ttu-id="424cc-126">較新版本的 HoloLens 2 已修正此情況，以確保各個外形規格的語義一致性。</span><span class="sxs-lookup"><span data-stu-id="424cc-126">Newer versions of HoloLens 2 have corrected this to ensure semantic consistency across form factors.</span></span>
- <span data-ttu-id="424cc-127">改良的手追蹤穩定性，在特定情況下會導致追蹤損失較少。</span><span class="sxs-lookup"><span data-stu-id="424cc-127">Improved hand tracking robustness that will result in fewer tracking losses in specific scenarios.</span></span>

## <span data-ttu-id="424cc-128">Windows 全息版 2004-2020 年8月更新</span><span class="sxs-lookup"><span data-stu-id="424cc-128">Windows Holographic, version 2004 - August 2020 Update</span></span>
- <span data-ttu-id="424cc-129">組建19041.1113</span><span class="sxs-lookup"><span data-stu-id="424cc-129">Build 19041.1113</span></span>

<span data-ttu-id="424cc-130">更新中的改進與修正：</span><span class="sxs-lookup"><span data-stu-id="424cc-130">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="424cc-131">[設定] 應用程式將不會追蹤使用者進入虹彩註冊或目視追蹤校準體驗。</span><span class="sxs-lookup"><span data-stu-id="424cc-131">Settings app will no longer follow the user into Iris Enrollment or Eye Tracking Calibration experiences.</span></span>
- <span data-ttu-id="424cc-132">已修正在 OOBE 期間套用置備套件並執行其他動作 (例如，連線至網路) 的錯誤，在裝置重新開機後由於重新命名，就無法執行其他動作。</span><span class="sxs-lookup"><span data-stu-id="424cc-132">Fixed a bug where applying a provisioning package during OOBE that renames the device and performs other actions (such as connecting to a network) would fail to perform the other actions after the device reboot due to rename.</span></span>
- <span data-ttu-id="424cc-133">已修改初始裝置設定流程的色彩配置，以改善視覺品質。</span><span class="sxs-lookup"><span data-stu-id="424cc-133">Modified color scheme of initial device setup flows to improve visual quality.</span></span>

## <span data-ttu-id="424cc-134">Windows 全息版 1903-2020 年8月更新</span><span class="sxs-lookup"><span data-stu-id="424cc-134">Windows Holographic, version 1903 - August 2020 Update</span></span>
- <span data-ttu-id="424cc-135">組建18362.1074</span><span class="sxs-lookup"><span data-stu-id="424cc-135">Build 18362.1074</span></span>

<span data-ttu-id="424cc-136">此每月品質更新不包含任何明顯的變更，我們鼓勵您試用 Windows 全息版（版本2004）的最新組建。</span><span class="sxs-lookup"><span data-stu-id="424cc-136">This monthly quality update doesn't contain any notable changes, we encourage you to try out our latest builds for Windows Holographic, version 2004.</span></span>

## <span data-ttu-id="424cc-137">Windows 全息版 2004-2020 年7月更新</span><span class="sxs-lookup"><span data-stu-id="424cc-137">Windows Holographic, version 2004 - July 2020 Update</span></span>
- <span data-ttu-id="424cc-138">組建19041.1109</span><span class="sxs-lookup"><span data-stu-id="424cc-138">Build 19041.1109</span></span>

<span data-ttu-id="424cc-139">更新中的改進與修正：</span><span class="sxs-lookup"><span data-stu-id="424cc-139">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="424cc-140">現在，開發人員可以選擇 [啟用] 或 [停用裝置入口網站需要安全連線]。</span><span class="sxs-lookup"><span data-stu-id="424cc-140">Developers can now choose between enabling or disabling having Device Portal require a secure connection.</span></span>
- <span data-ttu-id="424cc-141">改善作業系統更新後，應用程式會啟動的可靠性。</span><span class="sxs-lookup"><span data-stu-id="424cc-141">Reliability improved for application launches after OS updates.</span></span>
- <span data-ttu-id="424cc-142">已將預設收件匣亮度變更為100%。</span><span class="sxs-lookup"><span data-stu-id="424cc-142">Changed default inbox brightness to 100 percent.</span></span>
- <span data-ttu-id="424cc-143">已解決 HoloLens 2 上 Windows Device Portal 的 HTTPS 轉移問題。</span><span class="sxs-lookup"><span data-stu-id="424cc-143">Addressed an issue about HTTPS forwarding for the Windows Device Portal on HoloLens 2.</span></span>

## <span data-ttu-id="424cc-144">Windows 全息版 1903-2020 年7月更新</span><span class="sxs-lookup"><span data-stu-id="424cc-144">Windows Holographic, version 1903 - July 2020 Update</span></span>
- <span data-ttu-id="424cc-145">組建18362.1071</span><span class="sxs-lookup"><span data-stu-id="424cc-145">Build 18362.1071</span></span>

<span data-ttu-id="424cc-146">更新中的改進與修正：</span><span class="sxs-lookup"><span data-stu-id="424cc-146">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="424cc-147">已修正可能導致全息影像在失去或調整追蹤時，會在 Unity 應用程式中消失的問題。</span><span class="sxs-lookup"><span data-stu-id="424cc-147">Fixed an issue that could cause holograms to disappear in Unity applications when losing or regaining tracking.</span></span>
- <span data-ttu-id="424cc-148">已修正導致專屬 HoloLens app 在特定裝置上使用 HoloLens 模擬程式與硬體加速時，會造成專屬 HoloLens 應用程式損毀的問題。</span><span class="sxs-lookup"><span data-stu-id="424cc-148">Fixed an issue that caused exclusive HoloLens apps to crash back to the shell while using the HoloLens Emulator with hardware acceleration on certain devices.</span></span>
- <span data-ttu-id="424cc-149">已解決 HoloLens 2 上 Windows Device Portal 的 HTTPS 轉移問題。</span><span class="sxs-lookup"><span data-stu-id="424cc-149">Addressed an issue concerning HTTPS forwarding for the Windows Device Portal on HoloLens 2.</span></span>

## <span data-ttu-id="424cc-150">Windows 全息版 2004-2020 年6月更新</span><span class="sxs-lookup"><span data-stu-id="424cc-150">Windows Holographic, version 2004 - June 2020 Update</span></span>
- <span data-ttu-id="424cc-151">組建19041.1106</span><span class="sxs-lookup"><span data-stu-id="424cc-151">Build 19041.1106</span></span>

<span data-ttu-id="424cc-152">更新中的改進與修正：</span><span class="sxs-lookup"><span data-stu-id="424cc-152">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="424cc-153">如果沒有指定，自訂 MRC 記錄器現在會有特定屬性的新預設值。</span><span class="sxs-lookup"><span data-stu-id="424cc-153">Custom MRC recorders now have new default values for certain properties if they aren't specified.</span></span>
  - <span data-ttu-id="424cc-154">在 *MRC 影片效果*上：</span><span class="sxs-lookup"><span data-stu-id="424cc-154">On the *MRC Video Effect*:</span></span>
    - <span data-ttu-id="424cc-155">PreferredHologramPerspective (1 PhotoVideoCamera) </span><span class="sxs-lookup"><span data-stu-id="424cc-155">PreferredHologramPerspective (1 PhotoVideoCamera)</span></span>
    - <span data-ttu-id="424cc-156">GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式耳機) # A5</span><span class="sxs-lookup"><span data-stu-id="424cc-156">GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (Immersive headset))</span></span>
  - <span data-ttu-id="424cc-157">在 *MRC 音訊效果*上：</span><span class="sxs-lookup"><span data-stu-id="424cc-157">On the *MRC Audio Effect*:</span></span>
    - <span data-ttu-id="424cc-158">LoopbackGain (Windows Device Portal 中混合現實捕獲頁面上的目前「應用程式音訊增益」值) </span><span class="sxs-lookup"><span data-stu-id="424cc-158">LoopbackGain (the current "App Audio Gain" value on the Mixed Reality Capture page in Windows Device Portal)</span></span>
    - <span data-ttu-id="424cc-159">MicrophoneGain (Windows Device Portal 中混合現實捕獲頁面上目前的「麥克風音訊增益」值) </span><span class="sxs-lookup"><span data-stu-id="424cc-159">MicrophoneGain (the current "Mic Audio Gain" value on the Mixed Reality Capture page in Windows Device Portal)</span></span>
- <span data-ttu-id="424cc-160">修正了錯誤，以改善混合式現實捕獲案例中的音訊品質。</span><span class="sxs-lookup"><span data-stu-id="424cc-160">Fixed a bug to improve audio quality in mixed reality capture scenarios.</span></span> <span data-ttu-id="424cc-161">具體說來，此修正程式應該在顯示 [ **開始** ] 功能表時消除錄製中的音訊 glitching。</span><span class="sxs-lookup"><span data-stu-id="424cc-161">Specifically, this fix should eliminate audio glitching in the recording when the **Start** menu is displayed.</span></span>
- <span data-ttu-id="424cc-162">改善錄製的影片中的全息圖穩定性。</span><span class="sxs-lookup"><span data-stu-id="424cc-162">Improved hologram stability in recorded videos.</span></span>
- <span data-ttu-id="424cc-163">已解決混合式現實捕獲在超過數天后進入待機狀態後無法錄製影片的問題。</span><span class="sxs-lookup"><span data-stu-id="424cc-163">Resolved an issue where mixed reality capture couldn't record video after the device was left in standby state for multiple days.</span></span>
- <span data-ttu-id="424cc-164">Unity 應用程式通常會停用 HolographicSpace UserPresence API。</span><span class="sxs-lookup"><span data-stu-id="424cc-164">The HolographicSpace.UserPresence API is generally disabled for Unity applications.</span></span> <span data-ttu-id="424cc-165">此行為可避免在面板翻轉時，會導致某些 app 暫停的問題，即使已啟用 [在背景執行] 設定也一樣。</span><span class="sxs-lookup"><span data-stu-id="424cc-165">This behavior avoids an issue that caused some apps to pause when the visor was flipped up, even if the "run in the background" setting was enabled.</span></span> <span data-ttu-id="424cc-166">現在可針對 Unity 版本2018.4.18 及更新版本和2019.3.4 及更新版本啟用 API。</span><span class="sxs-lookup"><span data-stu-id="424cc-166">The API is now enabled for Unity versions 2018.4.18 and later and 2019.3.4 and later.</span></span>
- <span data-ttu-id="424cc-167">當您透過 Wi-fi 連線存取裝置入口網站時，網頁瀏覽器可能會因為證書無效而無法存取。</span><span class="sxs-lookup"><span data-stu-id="424cc-167">When you access Device Portal over a Wi-Fi connection, a web browser might prevent access to due to an invalid certificate.</span></span> <span data-ttu-id="424cc-168">瀏覽器可能會報告諸如「ERR_SSL_PROTOCOL_ERROR」之類的錯誤，即使裝置憑證先前是受信任的。</span><span class="sxs-lookup"><span data-stu-id="424cc-168">The browser might report an error such as "ERR_SSL_PROTOCOL_ERROR," even if the device certificate was previously trusted.</span></span> <span data-ttu-id="424cc-169">在此情況下，您無法對 Device Portal 進行進度，因為沒有任何選項可忽略安全性警告。</span><span class="sxs-lookup"><span data-stu-id="424cc-169">In this case, you can't progress to Device Portal, as there's no option to ignore security warnings.</span></span> <span data-ttu-id="424cc-170">此更新解決了問題。</span><span class="sxs-lookup"><span data-stu-id="424cc-170">This update resolved the issue.</span></span> <span data-ttu-id="424cc-171">如果裝置憑證先前是在電腦上下載並信任，以移除瀏覽器安全性警告，且發生 SSL 錯誤，則必須下載新憑證，並信任該憑證，才能解決瀏覽器安全性警告。</span><span class="sxs-lookup"><span data-stu-id="424cc-171">If the device certificate was previously downloaded and trusted on a PC to remove browser security warnings, and the SSL error occurs, the new certificate has to be downloaded and trusted to address browser security warnings.</span></span>
- <span data-ttu-id="424cc-172">已啟用建立執行時間預配套件的功能，可使用 MSIX 套件安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="424cc-172">Enabled the ability to create a runtime provisioning package that can install an app by using MSIX packages.</span></span>
- <span data-ttu-id="424cc-173">已在 [**設定**系統全息影像] 中新增一個設定  >  **System**  >  **Holograms** ，可讓使用者在裝置關閉時，自動移除混合現實家用版中的所有全息影像。</span><span class="sxs-lookup"><span data-stu-id="424cc-173">Added a setting in **Settings** > **System** > **Holograms** that allows users to automatically remove all holograms from Mixed Reality home when the device shuts down.</span></span>
- <span data-ttu-id="424cc-174">已修正導致 HoloLens app 變更其像素格式以在 HoloLens 模擬器中呈現黑色的問題。</span><span class="sxs-lookup"><span data-stu-id="424cc-174">Fixed an issue that caused HoloLens apps that change their pixel format to render black in the HoloLens emulator.</span></span>
- <span data-ttu-id="424cc-175">修正了在虹彩登入期間導致當機的錯誤。</span><span class="sxs-lookup"><span data-stu-id="424cc-175">Fixed a bug that caused a crash during Iris login.</span></span>
- <span data-ttu-id="424cc-176">已修正現有應用程式重複存放下載專案的相關問題。</span><span class="sxs-lookup"><span data-stu-id="424cc-176">Fixed an issue about repeated store downloads for already-current apps.</span></span>
- <span data-ttu-id="424cc-177">修正了錯誤，以避免沉浸式應用程式重複地開啟 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="424cc-177">Fixed a bug to prevent immersive apps from opening Microsoft Edge repeatedly.</span></span>
- <span data-ttu-id="424cc-178">修正從1903版本更新後開始啟動相片 app 的問題。</span><span class="sxs-lookup"><span data-stu-id="424cc-178">Fixed an issue with launches of the Photos app in initial boots after updating from the 1903 release.</span></span>
- <span data-ttu-id="424cc-179">改善效能與可靠性。</span><span class="sxs-lookup"><span data-stu-id="424cc-179">Improved performance and reliability.</span></span>

## <span data-ttu-id="424cc-180">Windows 全息版 1903-2020 年6月更新</span><span class="sxs-lookup"><span data-stu-id="424cc-180">Windows Holographic, version 1903 - June 2020 Update</span></span>
- <span data-ttu-id="424cc-181">組建18362.1064</span><span class="sxs-lookup"><span data-stu-id="424cc-181">Build 18362.1064</span></span>

<span data-ttu-id="424cc-182">更新中的改進與修正：</span><span class="sxs-lookup"><span data-stu-id="424cc-182">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="424cc-183">如果沒有指定，自訂 MRC 記錄器會有特定屬性的新預設值。</span><span class="sxs-lookup"><span data-stu-id="424cc-183">Custom MRC recorders have new default values for certain properties if they aren't specified.</span></span>
  - <span data-ttu-id="424cc-184">在 *MRC 影片效果*上：</span><span class="sxs-lookup"><span data-stu-id="424cc-184">On the *MRC Video Effect*:</span></span>
    - <span data-ttu-id="424cc-185">PreferredHologramPerspective (1 PhotoVideoCamera) </span><span class="sxs-lookup"><span data-stu-id="424cc-185">PreferredHologramPerspective (1 PhotoVideoCamera)</span></span>
    - <span data-ttu-id="424cc-186">GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式耳機) # A5</span><span class="sxs-lookup"><span data-stu-id="424cc-186">GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (Immersive headset))</span></span>
  - <span data-ttu-id="424cc-187">在 *MRC 音訊效果*上：</span><span class="sxs-lookup"><span data-stu-id="424cc-187">On the *MRC Audio Effect*:</span></span>
    - <span data-ttu-id="424cc-188">LoopbackGain (Windows Device Portal 中混合現實捕獲頁面上的目前「應用程式音訊增益」值) </span><span class="sxs-lookup"><span data-stu-id="424cc-188">LoopbackGain (the current "App Audio Gain" value on the Mixed Reality Capture page in Windows Device Portal)</span></span>
    - <span data-ttu-id="424cc-189">MicrophoneGain (Windows Device Portal 中混合現實捕獲頁面上目前的「麥克風音訊增益」值) </span><span class="sxs-lookup"><span data-stu-id="424cc-189">MicrophoneGain (the current "Mic Audio Gain" value on the Mixed Reality Capture page in Windows Device Portal)</span></span>
- <span data-ttu-id="424cc-190">Unity 應用程式通常會停用 HolographicSpace UserPresence API。</span><span class="sxs-lookup"><span data-stu-id="424cc-190">The HolographicSpace.UserPresence API is generally disabled for Unity applications.</span></span> <span data-ttu-id="424cc-191">此行為可避免在面板翻轉時，導致某些 app 暫停的問題，即使已啟用在背景中執行的設定，也是如此。</span><span class="sxs-lookup"><span data-stu-id="424cc-191">This behavior avoids an issue that causes some apps to pause when the visor is flipped up, even if the setting to run in the background is enabled.</span></span> <span data-ttu-id="424cc-192">現在已針對 Unity 版本2018.4.18 及更新版本啟用 API，以及2019.3.4 及更新版本。</span><span class="sxs-lookup"><span data-stu-id="424cc-192">The API is now enabled for Unity versions 2018.4.18 and later, and 2019.3.4 and later.</span></span>
- <span data-ttu-id="424cc-193">已修正導致 HoloLens app 變更其像素格式以在 HoloLens 模擬器中呈現黑色的問題。</span><span class="sxs-lookup"><span data-stu-id="424cc-193">Fixed an issue that caused HoloLens apps that change their pixel format to render black in the HoloLens Emulator.</span></span>
- <span data-ttu-id="424cc-194">已修正從1903版本更新後開始啟動相片 app 的問題。</span><span class="sxs-lookup"><span data-stu-id="424cc-194">Fixed an issue about launches of the Photos app in initial boots after updating from the 1903 release.</span></span>

## <span data-ttu-id="424cc-195">Windows 全息版，版本2004</span><span class="sxs-lookup"><span data-stu-id="424cc-195">Windows Holographic, version 2004</span></span>  
- <span data-ttu-id="424cc-196">組建-19041.1103</span><span class="sxs-lookup"><span data-stu-id="424cc-196">Build - 19041.1103</span></span>

<span data-ttu-id="424cc-197">2020年5月2日 *Windows 全息2004版* 軟體更新包含一種令人興奮的新功能，例如支援 Windows Autopilot、應用程式暗模式、USB 乙太網上支援 5G/LTE 熱點，以及更多功能。</span><span class="sxs-lookup"><span data-stu-id="424cc-197">The May 2020 major software update for HoloLens 2, *Windows Holographic, version 2004* includes a host of exciting new capabilities, such as support for Windows Autopilot, app dark mode, USB Ethernet support for 5G/LTE hotspots, and much more.</span></span> <span data-ttu-id="424cc-198">若要更新為最新版本，請開啟 [**設定**]   應用程式，移至 [ **更新 & 安全性**]，然後選取 [ **檢查更新**]   按鈕。</span><span class="sxs-lookup"><span data-stu-id="424cc-198">To update to the latest release, open the **Settings** app, go to **Update & Security**, and select the **Check for Updates** button.</span></span> 

|             <span data-ttu-id="424cc-199">功能</span><span class="sxs-lookup"><span data-stu-id="424cc-199">Feature</span></span>                              |          <span data-ttu-id="424cc-200">說明</span><span class="sxs-lookup"><span data-stu-id="424cc-200">Description</span></span>                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       <span data-ttu-id="424cc-201">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="424cc-201">Windows Autopilot</span></span>                          |          <span data-ttu-id="424cc-202">使用 Windows AutoPilot 進行預設定及無縫的新裝置製作</span><span class="sxs-lookup"><span data-stu-id="424cc-202">Pre-configure and seamlessly set up   new devices for production by using Windows AutoPilot</span></span>                 |
|       <span data-ttu-id="424cc-203">FIDO 2 支援</span><span class="sxs-lookup"><span data-stu-id="424cc-203">FIDO 2 support</span></span>                             |          <span data-ttu-id="424cc-204">支援 FIDO2 安全金鑰以針對共用裝置啟用快速及安全的驗證</span><span class="sxs-lookup"><span data-stu-id="424cc-204">Support for FIDO2 Security Keys to   enable fast and secure authentication for shared devices</span></span>            |
|       <span data-ttu-id="424cc-205">改良的資源調配</span><span class="sxs-lookup"><span data-stu-id="424cc-205">Improved provisioning</span></span>                      |          <span data-ttu-id="424cc-206">將預配套件從 USB 磁碟機無縫套用至 HoloLens</span><span class="sxs-lookup"><span data-stu-id="424cc-206">Seamlessly apply a provisioning   package from a USB drive to your HoloLens</span></span>                              |
|       <span data-ttu-id="424cc-207">應用程式安裝狀態</span><span class="sxs-lookup"><span data-stu-id="424cc-207">Application install status</span></span>                 |          <span data-ttu-id="424cc-208">透過 MDM 將 app 的 [設定] 應用程式中的 [安裝狀態] 推送至 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="424cc-208">Check install status in the Settings app for apps have been pushed to HoloLens 2 via MDM</span></span>               |
|       <span data-ttu-id="424cc-209"> (Csp) 的配置服務提供者</span><span class="sxs-lookup"><span data-stu-id="424cc-209">Configuration service providers   (CSPs)</span></span>   |          <span data-ttu-id="424cc-210">新增新的配置服務提供者以加強管理員控制功能</span><span class="sxs-lookup"><span data-stu-id="424cc-210">Added new configuration service providers to enhance admin control capabilities</span></span>                 |
|       <span data-ttu-id="424cc-211">USB 5G/LTE 支援</span><span class="sxs-lookup"><span data-stu-id="424cc-211">USB 5G/LTE support</span></span>                       |          <span data-ttu-id="424cc-212">擴充的 USB 乙太網功能可支援 5G/LTE</span><span class="sxs-lookup"><span data-stu-id="424cc-212">Expanded USB Ethernet capability   enables support for 5G/LTE</span></span>                                    |
|       <span data-ttu-id="424cc-213">深色 app 模式</span><span class="sxs-lookup"><span data-stu-id="424cc-213">Dark app mode</span></span>                              |          <span data-ttu-id="424cc-214">適用于支援暗色及淡模式的 app 的深色 app 模式，可改善觀賞體驗</span><span class="sxs-lookup"><span data-stu-id="424cc-214">Dark app mode available for apps that support both dark and light modes, improving the viewing experience</span></span>        |
|       <span data-ttu-id="424cc-215">語音命令</span><span class="sxs-lookup"><span data-stu-id="424cc-215">Voice commands</span></span>                             |          <span data-ttu-id="424cc-216">支援其他系統語音命令來控制 HoloLens 免提</span><span class="sxs-lookup"><span data-stu-id="424cc-216">Support for additional system voice   commands to control HoloLens hands-free</span></span>                           |
|       <span data-ttu-id="424cc-217">手動追蹤改善</span><span class="sxs-lookup"><span data-stu-id="424cc-217">Hand tracking improvements</span></span>                 |          <span data-ttu-id="424cc-218">[手追蹤] 改進讓按鈕和2D 石板互動更精確</span><span class="sxs-lookup"><span data-stu-id="424cc-218">Hand tracking improvements make buttons and 2D slate interactions more accurate</span></span>                        |
|       <span data-ttu-id="424cc-219">改善品質與修正</span><span class="sxs-lookup"><span data-stu-id="424cc-219">Quality improvements and fixes</span></span>                 |          <span data-ttu-id="424cc-220">跨平臺的各種系統效能與可靠性改進</span><span class="sxs-lookup"><span data-stu-id="424cc-220">Various system performance and   reliability improvements across the platform</span></span>                            |

### <span data-ttu-id="424cc-221">Windows Autopilot 支援</span><span class="sxs-lookup"><span data-stu-id="424cc-221">Support for Windows Autopilot</span></span>

<span data-ttu-id="424cc-222">HoloLens 2 的 Windows Autopilot 可讓裝置銷售通道預先登記 HoloLens 至您的 Intune 租使用者。</span><span class="sxs-lookup"><span data-stu-id="424cc-222">Windows Autopilot for HoloLens 2 lets the device sales channel pre-enroll HoloLens into your Intune tenant.</span></span> <span data-ttu-id="424cc-223">裝置到達時，就準備好在您的租使用者底下將其自行部署為共用裝置。</span><span class="sxs-lookup"><span data-stu-id="424cc-223">When devices arrive, they’re ready to self-deploy as shared devices under your tenant.</span></span> <span data-ttu-id="424cc-224">若要充分利用自行部署，在安裝程式的第一個畫面中，裝置必須使用 USB-乙太網或 USB 到 LTE 連接器連線到網路。</span><span class="sxs-lookup"><span data-stu-id="424cc-224">To take advantage of self-deployment, the device must connect to a network during the first screen in setup by using a USB-C-to-Ethernet or USB-C-to-LTE dongle.</span></span>

<span data-ttu-id="424cc-225">使用者啟動 Autopilot 自我部署程式後，此程式會完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="424cc-225">After a user starts the Autopilot self-deploying process, the process completes the following steps:</span></span>

1. <span data-ttu-id="424cc-226">將裝置加入 Azure Active Directory (Azure AD)。</span><span class="sxs-lookup"><span data-stu-id="424cc-226">Join the device to Azure Active Directory (Azure AD).</span></span>
1. <span data-ttu-id="424cc-227">在 Microsoft Intune (或另一個 MDM 服務) 中使用 Azure AD 註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="424cc-227">Use Azure AD to enroll the device in Microsoft Intune (or another MDM service).</span></span>
1. <span data-ttu-id="424cc-228">下載以裝置為目標的原則、憑證和網路設定檔。</span><span class="sxs-lookup"><span data-stu-id="424cc-228">Download the device-targeted policies, certificates, and networking profiles.</span></span>
1. <span data-ttu-id="424cc-229">佈建裝置。</span><span class="sxs-lookup"><span data-stu-id="424cc-229">Provision the device.</span></span>
1. <span data-ttu-id="424cc-230">向使用者呈現登入畫面。</span><span class="sxs-lookup"><span data-stu-id="424cc-230">Present the sign-in screen to the user.</span></span>

<span data-ttu-id="424cc-231">若要深入瞭解，請從 [適用于 HoloLens 2 評估指南的 Windows Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="424cc-231">Learn more from the [Windows Autopilot for HoloLens 2 evaluation guide](https://docs.microsoft.com/hololens/hololens2-autopilot).</span></span>

*<span data-ttu-id="424cc-232">請與您的客戶管理員聯繫，立即加入 AutoPilot preview。</span><span class="sxs-lookup"><span data-stu-id="424cc-232">Contact your Account Manager to join the AutoPilot preview now.</span></span> <span data-ttu-id="424cc-233">Autopilot 已就緒的裝置將會在不久後開始傳送。</span><span class="sxs-lookup"><span data-stu-id="424cc-233">Autopilot-ready devices will begin shipping soon.</span></span>*

### <span data-ttu-id="424cc-234">FIDO2 安全金鑰支援</span><span class="sxs-lookup"><span data-stu-id="424cc-234">FIDO2 security key support</span></span>

<span data-ttu-id="424cc-235">有些使用者在公司或學校環境中與其他人共用 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="424cc-235">Some users share a HoloLens device with others in a work or school environment.</span></span> <span data-ttu-id="424cc-236">所以很重要的是，使用者不需要輸入長的使用者名稱和密碼就能輕鬆。</span><span class="sxs-lookup"><span data-stu-id="424cc-236">So it's important that users can easily without typing long user names and passwords.</span></span> <span data-ttu-id="424cc-237">快速身分識別線上 (FIDO) 讓貴 (組織中的任何人都能在不輸入使用者名稱或密碼的情況下，) 無縫登入 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="424cc-237">Fast Identity Online (FIDO) lets anyone in your organization (Azure AD tenant) seamlessly sign-in to HoloLens without entering a user name or password.</span></span>

<span data-ttu-id="424cc-238">FIDO2 security 金鑰是「unphishable」標準的 passwordless 驗證方法，可以採用任何形式的外觀。</span><span class="sxs-lookup"><span data-stu-id="424cc-238">FIDO2 security keys are an "unphishable" standards-based passwordless authentication method that can come in any form factor.</span></span> <span data-ttu-id="424cc-239">FIDO 是 passwordless 驗證的開放標準。</span><span class="sxs-lookup"><span data-stu-id="424cc-239">FIDO is an open standard for passwordless authentication.</span></span> <span data-ttu-id="424cc-240">它可讓使用者和組織在不使用使用者名稱或密碼的情況下，登入其資源。</span><span class="sxs-lookup"><span data-stu-id="424cc-240">It allows users and organizations to sign in to their resources without a user name or password.</span></span> <span data-ttu-id="424cc-241">而是使用外部安全性金鑰或裝置內建的平臺金鑰。</span><span class="sxs-lookup"><span data-stu-id="424cc-241">Instead they use an external security key or a platform key built into a device.</span></span>

<span data-ttu-id="424cc-242">若要開始使用，請參閱 [啟用安全金鑰登入 passwordless](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)。</span><span class="sxs-lookup"><span data-stu-id="424cc-242">To get started, see [Enable passwordless security key sign-in](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key).</span></span>

### <span data-ttu-id="424cc-243">透過預配套件改善 MDM 登記</span><span class="sxs-lookup"><span data-stu-id="424cc-243">Improved MDM enrollment via provisioning package</span></span>

<span data-ttu-id="424cc-244">[預配套件] 可讓您透過 config 檔案設定 HoloLens 配置，而不是透過 HoloLens 全新體驗。</span><span class="sxs-lookup"><span data-stu-id="424cc-244">Provisioning packages let you set HoloLens configuration through a config file rather than through the HoloLens out-of-box experience.</span></span> <span data-ttu-id="424cc-245">先前，必須將預配套件複製到 HoloLens 內部記憶體。</span><span class="sxs-lookup"><span data-stu-id="424cc-245">Previously, provisioning packages had to be copied onto the HoloLens internal memory.</span></span> <span data-ttu-id="424cc-246">現在，他們可以在 USB 磁片磁碟機上，輕鬆地在多個 HoloLens 裝置上重複使用，而且您可以並行提供裝置。</span><span class="sxs-lookup"><span data-stu-id="424cc-246">Now they can be on a USB drive so they're easier to reuse on multiple HoloLens devices and you can provision devices in parallel.</span></span> <span data-ttu-id="424cc-247">[預配套件] 現在也支援在裝置管理中註冊欄位，因此在置備之後就沒有手動設定。</span><span class="sxs-lookup"><span data-stu-id="424cc-247">Provisioning packages now also support a field to enroll in device management so there's no manual setup after provisioning.</span></span>

<span data-ttu-id="424cc-248">試試看：</span><span class="sxs-lookup"><span data-stu-id="424cc-248">To try it out:</span></span>

1. <span data-ttu-id="424cc-249">從 Windows 網上商店將最新版本的 Windows 配置設計工具下載至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="424cc-249">Download the latest version of the Windows Configuration Designer from the Windows store onto your PC.</span></span>
1. <span data-ttu-id="424cc-250">選取 [**預配 hololens 裝置**]  >  **提供 hololens 2 裝置**。</span><span class="sxs-lookup"><span data-stu-id="424cc-250">Select **Provision HoloLens Devices** > **Provision HoloLens 2 devices**.</span></span>
2. <span data-ttu-id="424cc-251">建立您的設定檔。</span><span class="sxs-lookup"><span data-stu-id="424cc-251">Build your configuration profile.</span></span> <span data-ttu-id="424cc-252">然後複製已建立至 USB-C 儲存裝置的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="424cc-252">Then copy all files that were created to a USB-C storage device.</span></span>
3. <span data-ttu-id="424cc-253">將 USB-C 裝置插入任何剛剛閃爍的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="424cc-253">Plug the USB-C device into any freshly flashed HoloLens.</span></span> <span data-ttu-id="424cc-254">然後按**下 [音量**]  +  **power**按鈕，即可套用您的預配套件。</span><span class="sxs-lookup"><span data-stu-id="424cc-254">Then press the **volume down** + **power** buttons to apply your provisioning package.</span></span>

### <span data-ttu-id="424cc-255">商務線應用程式安裝狀態</span><span class="sxs-lookup"><span data-stu-id="424cc-255">Line-of-business application install status</span></span>

<span data-ttu-id="424cc-256">針對 HoloLens 的 MDM 應用程式部署與管理</span><span class="sxs-lookup"><span data-stu-id="424cc-256">MDM app deployment and management for line of business apps is critical to HoloLens.</span></span> <span data-ttu-id="424cc-257">系統管理員和使用者必須針對審核與診斷查看 app 安裝狀態。</span><span class="sxs-lookup"><span data-stu-id="424cc-257">Admins and users need to view app install status for auditing and diagnosis.</span></span> <span data-ttu-id="424cc-258">在這個版本中，我們在 [**設定**帳戶] 中新增了更多詳細資料，在 [  >  **Accounts**  >  **Access work or school**  >  **帳戶資訊] 上按一下**[工作]  >  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="424cc-258">In this release, we added more details in **Settings** > **Accounts** > **Access work or school** > **Click on your account** > **Info**.</span></span>

### <span data-ttu-id="424cc-259">其他 Csp 與原則</span><span class="sxs-lookup"><span data-stu-id="424cc-259">Additional CSPs and policies</span></span>

<span data-ttu-id="424cc-260">[配置服務提供者 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN)是一個介面，可用於讀取、設定、修改或刪除裝置上的設定設定。</span><span class="sxs-lookup"><span data-stu-id="424cc-260">A [configuration service provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) is an interface to read, set, modify, or delete configuration settings on a device.</span></span> <span data-ttu-id="424cc-261">在這個版本中，我們會新增支援來增加更多原則，以擴大控制管理員已部署的 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="424cc-261">In this release, we add support for more policies to increase the control administrators have over deployed HoloLens devices.</span></span> <span data-ttu-id="424cc-262">如需 HoloLens 支援的 Csp 清單，請參閱 [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。</span><span class="sxs-lookup"><span data-stu-id="424cc-262">For the list of CSPs supported by HoloLens, see [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span></span>

<span data-ttu-id="424cc-263">此版本中的新功能：</span><span class="sxs-lookup"><span data-stu-id="424cc-263">New in this release:</span></span>

**<span data-ttu-id="424cc-264">原則 CSP</span><span class="sxs-lookup"><span data-stu-id="424cc-264">Policy CSP</span></span>** 

<span data-ttu-id="424cc-265">策略配置服務提供者可讓企業設定 Windows 裝置上的原則。</span><span class="sxs-lookup"><span data-stu-id="424cc-265">The Policy configuration service provider enables the enterprise to configure policies on Windows devices.</span></span> <span data-ttu-id="424cc-266">在這個版本中，我們新增了 HoloLens 的新原則，這些原則如下所列。</span><span class="sxs-lookup"><span data-stu-id="424cc-266">In this release, we added new policies for HoloLens, which are listed here.</span></span> <span data-ttu-id="424cc-267">若要深入瞭解，請參閱 [HoloLens 2 支援的原則 csp](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)。</span><span class="sxs-lookup"><span data-stu-id="424cc-267">To learn more, see [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).</span></span>  

- <span data-ttu-id="424cc-268">LetAppsAccessCamera_ForceAllowTheseApps</span><span class="sxs-lookup"><span data-stu-id="424cc-268">LetAppsAccessCamera_ForceAllowTheseApps</span></span>  
- <span data-ttu-id="424cc-269">LetAppsAccessCamera_ForceDenyTheseApps</span><span class="sxs-lookup"><span data-stu-id="424cc-269">LetAppsAccessCamera_ForceDenyTheseApps</span></span>  
- <span data-ttu-id="424cc-270">LetAppsAccessCamera_UserInControlOfTheseApps</span><span class="sxs-lookup"><span data-stu-id="424cc-270">LetAppsAccessCamera_UserInControlOfTheseApps</span></span> 
- <span data-ttu-id="424cc-271">LetAppsAccessGazeInput</span><span class="sxs-lookup"><span data-stu-id="424cc-271">LetAppsAccessGazeInput</span></span> 
- <span data-ttu-id="424cc-272">LetAppsAccessGazeInput_ForceAllowTheseApps</span><span class="sxs-lookup"><span data-stu-id="424cc-272">LetAppsAccessGazeInput_ForceAllowTheseApps</span></span> 
- <span data-ttu-id="424cc-273">LetAppsAccessGazeInput_ForceDenyTheseApps</span><span class="sxs-lookup"><span data-stu-id="424cc-273">LetAppsAccessGazeInput_ForceDenyTheseApps</span></span> 
- <span data-ttu-id="424cc-274">LetAppsAccessGazeInput_UserInControlOfTheseApps</span><span class="sxs-lookup"><span data-stu-id="424cc-274">LetAppsAccessGazeInput_UserInControlOfTheseApps</span></span> 
- <span data-ttu-id="424cc-275">LetAppsAccessMicrophone_ForceAllowTheseApps</span><span class="sxs-lookup"><span data-stu-id="424cc-275">LetAppsAccessMicrophone_ForceAllowTheseApps</span></span> 
- <span data-ttu-id="424cc-276">LetAppsAccessMicrophone_ForceDenyTheseApps</span><span class="sxs-lookup"><span data-stu-id="424cc-276">LetAppsAccessMicrophone_ForceDenyTheseApps</span></span> 
- <span data-ttu-id="424cc-277">LetAppsAccessMicrophone_UserInControlOfTheseApps</span><span class="sxs-lookup"><span data-stu-id="424cc-277">LetAppsAccessMicrophone_UserInControlOfTheseApps</span></span> 
- <span data-ttu-id="424cc-278">AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="424cc-278">AllowWiFi</span></span> 

**<span data-ttu-id="424cc-279">NetworkQoSPolicy CSP</span><span class="sxs-lookup"><span data-stu-id="424cc-279">NetworkQoSPolicy CSP</span></span>**

<span data-ttu-id="424cc-280">NetworkQoSPolicy configuration 服務提供者會建立網路服務品質 (QoS) 原則。</span><span class="sxs-lookup"><span data-stu-id="424cc-280">The NetworkQoSPolicy configuration service provider creates network quality-of-service (QoS) policies.</span></span> <span data-ttu-id="424cc-281">QoS 原則會根據一組符合的條件在網路流量上執行一組動作。</span><span class="sxs-lookup"><span data-stu-id="424cc-281">A QoS policy performs a set of actions on network traffic based on a set of matching conditions.</span></span> <span data-ttu-id="424cc-282">若要深入瞭解，請參閱 [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。</span><span class="sxs-lookup"><span data-stu-id="424cc-282">To learn more, see [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span></span>

### <span data-ttu-id="424cc-283">已展開 5G/LTE tethered 裝置的 USB 乙太網上支援</span><span class="sxs-lookup"><span data-stu-id="424cc-283">Expanded USB Ethernet support for 5G/LTE tethered devices</span></span>

<span data-ttu-id="424cc-284">已新增支援，以啟用特定的行動寬頻裝置，例如 5G/LTE 手機和 Wi-fi hotpots （當他們透過 USB tethered 至 HoloLens 2 時）。</span><span class="sxs-lookup"><span data-stu-id="424cc-284">Support was added to enable certain mobile broadband devices, such as 5G/LTE phones and Wi-Fi hotpots, when they're tethered to the HoloLens 2 via USB.</span></span> <span data-ttu-id="424cc-285">這些裝置現在會以另一個乙太網連線的方式顯示在 [ **網路設定** ] 中。</span><span class="sxs-lookup"><span data-stu-id="424cc-285">These devices are now displayed in **network settings** as another Ethernet connection.</span></span> <span data-ttu-id="424cc-286"> (不支援需要外部驅動程式的行動寬頻裝置。 ) 此功能可在未提供 Wi-fi 且 Wi-fi tethering 無法正常使用時，啟用高頻寬連線。</span><span class="sxs-lookup"><span data-stu-id="424cc-286">(Mobile broadband devices that require an external driver aren't supported.) This functionality enables high-bandwidth connections when Wi-Fi is not available and Wi-Fi tethering isn't performant enough.</span></span> <span data-ttu-id="424cc-287">若要深入瞭解支援的 USB 裝置，請參閱連線 [至藍牙和 USB 裝置](https://docs.microsoft.com/hololens/hololens-connect-devices)。</span><span class="sxs-lookup"><span data-stu-id="424cc-287">To learn more about supported USB devices, see [Connect to Bluetooth and USB-C devices](https://docs.microsoft.com/hololens/hololens-connect-devices).</span></span>  

### <span data-ttu-id="424cc-288">手動追蹤改善</span><span class="sxs-lookup"><span data-stu-id="424cc-288">Hand tracking improvements</span></span>

<span data-ttu-id="424cc-289">此版本包含數種手追蹤改進功能：</span><span class="sxs-lookup"><span data-stu-id="424cc-289">This release includes several hand tracking improvements:</span></span>

- <span data-ttu-id="424cc-290">**指向會造成穩定性：** 當 palm 在 occluded 時，系統現在會 resists 折彎。</span><span class="sxs-lookup"><span data-stu-id="424cc-290">**Pointing pose stability:** The system now resists bending the index finger when it gets occluded by the palm.</span></span> <span data-ttu-id="424cc-291">當您按下按鈕、輸入、滾動內容及其他資訊時，這種變更可改善精確度。</span><span class="sxs-lookup"><span data-stu-id="424cc-291">This change improves the accuracy when you push buttons, type, scroll content, and more!</span></span> 
- <span data-ttu-id="424cc-292">**減少意外的空中點擊：** 我們改善了空中攻絲手勢的偵測。</span><span class="sxs-lookup"><span data-stu-id="424cc-292">**Reduced accidental air taps:** We improved detection of the air tap gesture.</span></span> <span data-ttu-id="424cc-293">現在，在幾個常見案例中的意外啟動較少，例如當您將手放在一邊時。</span><span class="sxs-lookup"><span data-stu-id="424cc-293">There are now fewer accidental activations in several common scenarios, such as when you drop your hands to your sides.</span></span>
- <span data-ttu-id="424cc-294">**使用者切換可靠性：** 當您共用裝置時，系統現在會更快且更可靠地更新手大小。</span><span class="sxs-lookup"><span data-stu-id="424cc-294">**User switch reliability:** The system is now faster and more reliable at updating the hand size when you share a device.</span></span>
- <span data-ttu-id="424cc-295">**減少手偷竊：** 我們改良了兩次手中的感應器視圖，我們已改善對這些案例的處理。</span><span class="sxs-lookup"><span data-stu-id="424cc-295">**Reduced hand stealing:** We improved handling of cases where there are more than two hands in view of the sensors.</span></span> <span data-ttu-id="424cc-296">如果有多個人員合在一起，現在就能讓追蹤手在場景中從使用者「跳躍」到其他人的機會。</span><span class="sxs-lookup"><span data-stu-id="424cc-296">If multiple people are working close together, there's now a much lower chance that the tracked hand will "jump" from the user to the hand of someone else in the scene.</span></span>
- <span data-ttu-id="424cc-297">**系統可靠性：** 已修正當裝置處於高負載時，會導致手動追蹤停止運作的問題。</span><span class="sxs-lookup"><span data-stu-id="424cc-297">**System reliability:** Fixed an issue that caused hand tracking to stop working when the device is under high load.</span></span>

### <span data-ttu-id="424cc-298">深色模式</span><span class="sxs-lookup"><span data-stu-id="424cc-298">Dark mode</span></span>

<span data-ttu-id="424cc-299">許多 Windows 應用程式現已支援深色和 light 模式。</span><span class="sxs-lookup"><span data-stu-id="424cc-299">Many Windows apps now support both dark and light modes.</span></span> <span data-ttu-id="424cc-300">HoloLens 2 使用者可以為支援這兩者的 app 選擇預設模式。</span><span class="sxs-lookup"><span data-stu-id="424cc-300">HoloLens 2 users can choose the default mode for apps that support both.</span></span> <span data-ttu-id="424cc-301">更新之後，預設的應用程式模式是「深色」，但您可以輕鬆地變更此設定：流覽至 [**設定**  >  ]**系統**  >  **色彩**  >  **選擇您的預設應用程式模式**。</span><span class="sxs-lookup"><span data-stu-id="424cc-301">After the update, the default app mode is "dark," but you can easily change this setting: Navigate to **Settings** > **System** > **Colors** > **Choose your default app mode**.</span></span> 

<span data-ttu-id="424cc-302">這些 [主機殼中] app 支援深色模式：</span><span class="sxs-lookup"><span data-stu-id="424cc-302">These "in-box" apps support dark mode:</span></span> 

- <span data-ttu-id="424cc-303">設定</span><span class="sxs-lookup"><span data-stu-id="424cc-303">Settings</span></span> 
- <span data-ttu-id="424cc-304">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="424cc-304">Microsoft Store</span></span> 
- <span data-ttu-id="424cc-305">郵件</span><span class="sxs-lookup"><span data-stu-id="424cc-305">Mail</span></span> 
- <span data-ttu-id="424cc-306">行事曆</span><span class="sxs-lookup"><span data-stu-id="424cc-306">Calendar</span></span> 
- <span data-ttu-id="424cc-307">檔案總管</span><span class="sxs-lookup"><span data-stu-id="424cc-307">File Explorer</span></span> 
- <span data-ttu-id="424cc-308">意見反應中樞</span><span class="sxs-lookup"><span data-stu-id="424cc-308">Feedback Hub</span></span> 
- <span data-ttu-id="424cc-309">OneDrive</span><span class="sxs-lookup"><span data-stu-id="424cc-309">OneDrive</span></span> 
- <span data-ttu-id="424cc-310">相片</span><span class="sxs-lookup"><span data-stu-id="424cc-310">Photos</span></span> 
- <span data-ttu-id="424cc-311">3D 檢視器</span><span class="sxs-lookup"><span data-stu-id="424cc-311">3D Viewer</span></span> 
- <span data-ttu-id="424cc-312">電影與電視</span><span class="sxs-lookup"><span data-stu-id="424cc-312">Movies & TV</span></span> 

![視窗平鋪的深色模式](images/DarkMode.jpg)

### <span data-ttu-id="424cc-314">系統 voice 命令</span><span class="sxs-lookup"><span data-stu-id="424cc-314">System voice commands</span></span>

<span data-ttu-id="424cc-315">您現在可以在裝置上的任何應用程式中使用語音命令。</span><span class="sxs-lookup"><span data-stu-id="424cc-315">You can now use voice commands with any app on the device.</span></span> <span data-ttu-id="424cc-316">如需詳細資訊，請參閱 [使用語音操作 HoloLens](https://docs.microsoft.com/hololens/hololens-cortana)。</span><span class="sxs-lookup"><span data-stu-id="424cc-316">For more information, see [Use your voice to operate HoloLens](https://docs.microsoft.com/hololens/hololens-cortana).</span></span> <span data-ttu-id="424cc-317">另請參閱 [HoloLens 2 支援的語言](https://docs.microsoft.com/hololens/hololens2-language-support)。</span><span class="sxs-lookup"><span data-stu-id="424cc-317">Also see [Supported languages for HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support).</span></span>  

### <span data-ttu-id="424cc-318">Cortana 更新</span><span class="sxs-lookup"><span data-stu-id="424cc-318">Cortana updates</span></span>

<span data-ttu-id="424cc-319">已更新的應用程式會整合 Microsoft 365，以協助您在裝置上進行更多的工作 (目前僅提供英文) 。</span><span class="sxs-lookup"><span data-stu-id="424cc-319">The updated app integrates with Microsoft 365 to help you get more done across your devices (currently in US-English only).</span></span> <span data-ttu-id="424cc-320">在 HoloLens 2 上，Cortana 不再支援特定裝置特定的命令，例如調整音量或重新開機。</span><span class="sxs-lookup"><span data-stu-id="424cc-320">On HoloLens 2, Cortana no longer supports certain device-specific commands, like adjusting volume or restarting.</span></span> <span data-ttu-id="424cc-321">這些選項現已由新的系統語音命令支援。</span><span class="sxs-lookup"><span data-stu-id="424cc-321">These options are now supported by the new system voice commands.</span></span> <span data-ttu-id="424cc-322">深入瞭解我們的 [博客](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)中的新 Cortana app。</span><span class="sxs-lookup"><span data-stu-id="424cc-322">Learn more about the new Cortana app in our [blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).</span></span>

### <span data-ttu-id="424cc-323">改善品質與修正</span><span class="sxs-lookup"><span data-stu-id="424cc-323">Quality improvements and fixes</span></span>

<span data-ttu-id="424cc-324">更新中也會有改進與修正：</span><span class="sxs-lookup"><span data-stu-id="424cc-324">Improvements and fixes also in the update:</span></span>  
- <span data-ttu-id="424cc-325">已推出活動的顯示校準系統。</span><span class="sxs-lookup"><span data-stu-id="424cc-325">Introduced an active display calibration system.</span></span> <span data-ttu-id="424cc-326">此功能可改善全息影像的穩定性與對齊方式。</span><span class="sxs-lookup"><span data-stu-id="424cc-326">This feature improves the stability and alignment of holograms.</span></span> <span data-ttu-id="424cc-327">當您將自己從一邊移到另一側時，它們就會保持在適當的位置。</span><span class="sxs-lookup"><span data-stu-id="424cc-327">They now stay in place when you move your head from side to side.</span></span>
- <span data-ttu-id="424cc-328">修正了將 Wi-fi 流式處理定期中斷的錯誤。</span><span class="sxs-lookup"><span data-stu-id="424cc-328">Fixed a bug where Wi-Fi streaming to HoloLens got disrupted periodically.</span></span> <span data-ttu-id="424cc-329">如果應用程式指出它需要低延遲的資料流程，請呼叫 [SetSocketMediaStreamingMode 函數](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)來實施修正程式。</span><span class="sxs-lookup"><span data-stu-id="424cc-329">If an application indicates that it needs low latency streaming, implement the fix by calling the [SetSocketMediaStreamingMode function](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).</span></span>
- <span data-ttu-id="424cc-330">已修正在研究模式中進行流式處理期間發生的裝置暫停問題。</span><span class="sxs-lookup"><span data-stu-id="424cc-330">Fixed a device hang that occurred during streaming in research mode.</span></span>
- <span data-ttu-id="424cc-331">修正錯誤：在某些情況下，當您繼續會話時，無法在登入畫面上顯示正確的使用者。</span><span class="sxs-lookup"><span data-stu-id="424cc-331">Fixed a bug where in some cases the right user wouldn't be displayed on the sign-in screen when resuming a session.</span></span>
- <span data-ttu-id="424cc-332">已修正使用者無法透過 [ **設定**] 匯出 MDM 記錄的問題。</span><span class="sxs-lookup"><span data-stu-id="424cc-332">Fixed an issue where users couldn't export MDM logs through **Settings**.</span></span>
- <span data-ttu-id="424cc-333">已修正立即追蹤 [全新] 設定的問題，可能比預期的要低。</span><span class="sxs-lookup"><span data-stu-id="424cc-333">Fixed an issue where the accuracy of eye tracking immediately following out-of-box setup could be lower than expected.</span></span>
- <span data-ttu-id="424cc-334">已修正目視追蹤子系統無法初始化或在特定情況下執行校準的問題。</span><span class="sxs-lookup"><span data-stu-id="424cc-334">Fixed an issue where the eye tracking subsystem failed to initialize or perform calibration under certain conditions.</span></span>
- <span data-ttu-id="424cc-335">已修正向已校準的使用者提示目視校準的問題。</span><span class="sxs-lookup"><span data-stu-id="424cc-335">Fixed an issue where eye calibration would be prompted for an already-calibrated user.</span></span>
- <span data-ttu-id="424cc-336">已修正在目視校準期間驅動程式可能會當機的問題。</span><span class="sxs-lookup"><span data-stu-id="424cc-336">Fixed an issue where a driver would crash during eye calibration.</span></span>
- <span data-ttu-id="424cc-337">已修正重複出現電源按鈕按下的問題，可能會導致60秒的系統超時和 shell 損毀。</span><span class="sxs-lookup"><span data-stu-id="424cc-337">Fixed an issue where repeated power button presses could cause a 60-second system timeout and shell crash.</span></span>
- <span data-ttu-id="424cc-338">改善深度緩衝區的穩定性。</span><span class="sxs-lookup"><span data-stu-id="424cc-338">Improved stability for depth buffers.</span></span>
- <span data-ttu-id="424cc-339">已在意見反應中樞中新增 [ **共用** ] 按鈕，讓使用者可以更輕鬆地共用意見反應。</span><span class="sxs-lookup"><span data-stu-id="424cc-339">Added a **Share** button in the Feedback Hub so users can more easily share feedback.</span></span>
- <span data-ttu-id="424cc-340">修正 RoboRaid wan't 正確安裝的錯誤。</span><span class="sxs-lookup"><span data-stu-id="424cc-340">Fixed a bug where RoboRaid wan't installed correctly.</span></span>

### <span data-ttu-id="424cc-341">已知問題</span><span class="sxs-lookup"><span data-stu-id="424cc-341">Known issues</span></span>

- <span data-ttu-id="424cc-342">Zh-cn&platform 系統語言的問題會阻止語音命令捕獲混合現實或顯示裝置 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="424cc-342">An issue with the zh-CN system language prevents voice commands from taking a mixed reality capture or displaying the device IP address.</span></span>
- <span data-ttu-id="424cc-343">問題需要您啟動裝置才能使用「你好小娜」語音啟用之後，才能啟動 Cortana app。</span><span class="sxs-lookup"><span data-stu-id="424cc-343">An issue requires you to launch the Cortana app after starting the device to use "Hey Cortana" voice activation.</span></span> <span data-ttu-id="424cc-344">如果您是從18362組建更新，您可能也會看到舊版 Cortana app 的第二個應用程式磚，該應用程式在 **啟動**時不再運作。</span><span class="sxs-lookup"><span data-stu-id="424cc-344">If you updated from a 18362 build, you may also see a second app tile for the previous version of the Cortana app that no longer works in **Start**.</span></span>

## <span data-ttu-id="424cc-345">Windows 全息版，版本 1903-可能2020更新</span><span class="sxs-lookup"><span data-stu-id="424cc-345">Windows Holographic, version 1903 - May 2020 Update</span></span> 
- <span data-ttu-id="424cc-346">組建18362.1061</span><span class="sxs-lookup"><span data-stu-id="424cc-346">Build 18362.1061</span></span>

<span data-ttu-id="424cc-347">這個每月品質更新不會包含任何明顯的變更，因為小組使用 Windows 全息版2004可能會更新（如前文所述）。</span><span class="sxs-lookup"><span data-stu-id="424cc-347">This monthly quality update doesn't contain any notable changes because the team was working on the Windows Holographic version 2004 May Update, as described earlier.</span></span>

## <span data-ttu-id="424cc-348">Windows 全息版 1903-2020 年4月更新</span><span class="sxs-lookup"><span data-stu-id="424cc-348">Windows Holographic, version 1903 - April 2020 Update</span></span>
- <span data-ttu-id="424cc-349">組建18362.1059</span><span class="sxs-lookup"><span data-stu-id="424cc-349">Build 18362.1059</span></span>

**<span data-ttu-id="424cc-350">支援的 app 的深色模式</span><span class="sxs-lookup"><span data-stu-id="424cc-350">Dark mode for supported apps</span></span>** 

<span data-ttu-id="424cc-351">許多 Windows app 支援深色和 light 模式。</span><span class="sxs-lookup"><span data-stu-id="424cc-351">Many Windows apps support both dark and light mode.</span></span> <span data-ttu-id="424cc-352">HoloLens 2 客戶現在可以為支援這兩種色彩配置的 app 選擇預設模式。</span><span class="sxs-lookup"><span data-stu-id="424cc-352">HoloLens 2 customers can now choose the default mode for apps that support both color schemes.</span></span> <span data-ttu-id="424cc-353">根據客戶的意見反應，我們將預設的應用程式模式設定為 [深色]，但您可以隨時輕鬆地變更此設定：流覽至 **[設定您的預設應用程式模式**] **> 系統 > 色彩**] 中的 [設定]。</span><span class="sxs-lookup"><span data-stu-id="424cc-353">Based on customer feedback, we set the default app mode to "dark," but you can easily change this setting at any time: Navigate to **Settings > System > Colors** to find **"Choose your default app mode."**</span></span>

<span data-ttu-id="424cc-354">這些 [主機殼中] app 支援深色模式：</span><span class="sxs-lookup"><span data-stu-id="424cc-354">These "in-box" apps support dark mode:</span></span>
- <span data-ttu-id="424cc-355">設定</span><span class="sxs-lookup"><span data-stu-id="424cc-355">Settings</span></span>
- <span data-ttu-id="424cc-356">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="424cc-356">Microsoft Store</span></span>
- <span data-ttu-id="424cc-357">郵件</span><span class="sxs-lookup"><span data-stu-id="424cc-357">Mail</span></span>
- <span data-ttu-id="424cc-358">行事曆</span><span class="sxs-lookup"><span data-stu-id="424cc-358">Calendar</span></span>
- <span data-ttu-id="424cc-359">檔案總管</span><span class="sxs-lookup"><span data-stu-id="424cc-359">File Explorer</span></span>
- <span data-ttu-id="424cc-360">意見反應中樞</span><span class="sxs-lookup"><span data-stu-id="424cc-360">Feedback Hub</span></span>
- <span data-ttu-id="424cc-361">OneDrive</span><span class="sxs-lookup"><span data-stu-id="424cc-361">OneDrive</span></span>
- <span data-ttu-id="424cc-362">相片</span><span class="sxs-lookup"><span data-stu-id="424cc-362">Photos</span></span>
- <span data-ttu-id="424cc-363">3D 檢視器</span><span class="sxs-lookup"><span data-stu-id="424cc-363">3D Viewer</span></span>
- <span data-ttu-id="424cc-364">電影與電視</span><span class="sxs-lookup"><span data-stu-id="424cc-364">Movies & TV</span></span>

**<span data-ttu-id="424cc-365">更新中也會有改進與修正：</span><span class="sxs-lookup"><span data-stu-id="424cc-365">Improvements and fixes also in the update:</span></span>** 
- <span data-ttu-id="424cc-366">已確保 shell 重迭包含在混合現實捕獲中。</span><span class="sxs-lookup"><span data-stu-id="424cc-366">Ensured that shell overlays are included in mixed reality captures.</span></span>
- <span data-ttu-id="424cc-367">Unreal 開發人員現在可以使用 Device Portal 中的 [3D 視圖] 頁面來測試及調試其應用程式。</span><span class="sxs-lookup"><span data-stu-id="424cc-367">Unreal developers can now use the 3D View page in Device Portal to test and debug their applications.</span></span>
- <span data-ttu-id="424cc-368">在使用 *HolographicDepthReprojectionMethod DepthReprojection* 演算法時，在混合現實捕獲中改善了全息圖穩定性。</span><span class="sxs-lookup"><span data-stu-id="424cc-368">Improved hologram stability in mixed reality capture when the *HolographicDepthReprojectionMethod DepthReprojection* algorithm is used.</span></span>
- <span data-ttu-id="424cc-369">修正了32位 ARM app 上的「WinRT IStreamSocketListener API 類別未註冊」錯誤。</span><span class="sxs-lookup"><span data-stu-id="424cc-369">Fixed the "WinRT IStreamSocketListener API Class not registered" error on 32-bit ARM apps.</span></span>

## <span data-ttu-id="424cc-370">Windows 全息版，版本 1903-2020 年3月更新</span><span class="sxs-lookup"><span data-stu-id="424cc-370">Windows Holographic, version 1903 - March 2020 Update</span></span> 
- <span data-ttu-id="424cc-371">組建18362.1056</span><span class="sxs-lookup"><span data-stu-id="424cc-371">Build 18362.1056</span></span>

<span data-ttu-id="424cc-372">更新中的改進與修正：</span><span class="sxs-lookup"><span data-stu-id="424cc-372">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="424cc-373">在使用 *HolographicDepthReprojectionMethod AutoPlanar* 演算法時，在混合現實捕獲中改善了全息圖穩定性。</span><span class="sxs-lookup"><span data-stu-id="424cc-373">Improved hologram stability in mixed reality capture when the *HolographicDepthReprojectionMethod AutoPlanar* algorithm is used.</span></span>
- <span data-ttu-id="424cc-374">已確保連接至 depth MF 範例的座標系統與公用檔一致。</span><span class="sxs-lookup"><span data-stu-id="424cc-374">Ensured that the coordinate system attached to a depth MF sample is consistent with public documentation.</span></span>
- <span data-ttu-id="424cc-375">透過讓客戶透過裝置入口網站貼上大量文字，改善開發人員的生產力。</span><span class="sxs-lookup"><span data-stu-id="424cc-375">Improved developer productivity by enabling customers to paste large amounts of text through the device portal.</span></span>

## <span data-ttu-id="424cc-376">Windows 全息版，版本 1903-2020 年2月更新</span><span class="sxs-lookup"><span data-stu-id="424cc-376">Windows Holographic, version 1903 - February 2020 Update</span></span> 
- <span data-ttu-id="424cc-377">組建18362.1053</span><span class="sxs-lookup"><span data-stu-id="424cc-377">Build 18362.1053</span></span>

<span data-ttu-id="424cc-378">更新中的改進與修正：</span><span class="sxs-lookup"><span data-stu-id="424cc-378">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="424cc-379">已暫時停用適用于 Unity 應用程式的 HolographicSpace UserPresence API。</span><span class="sxs-lookup"><span data-stu-id="424cc-379">Temporarily disabled the HolographicSpace.UserPresence API for Unity applications.</span></span> <span data-ttu-id="424cc-380">此變更可避免在面板翻轉時，會導致某些 app 暫停的問題，即使已啟用 [在背景執行] 設定也一樣。</span><span class="sxs-lookup"><span data-stu-id="424cc-380">This change avoids an issue that caused some apps to pause when the visor was flipped up, even if the "run in the background" setting was enabled.</span></span>
- <span data-ttu-id="424cc-381">修正手動追蹤所造成的隨機 HUP 當機，在數秒之後，使用者會注意到 UI 凍結，然後回到 shell。</span><span class="sxs-lookup"><span data-stu-id="424cc-381">Fixed a random HUP crash caused by hand tracking, in which the user noticed a UI freeze then back to shell after several seconds.</span></span>
- <span data-ttu-id="424cc-382">改良的手追蹤功能可讓您在使用食指進行前往時，手指的上方部分不會意外捲曲。</span><span class="sxs-lookup"><span data-stu-id="424cc-382">Improved hand tracking so that when you poke with your index finger, the upper part of that finger is less likely to curl unexpectedly.</span></span>
- <span data-ttu-id="424cc-383">改進標題追蹤、空間對應及其他執行時間的可靠性。</span><span class="sxs-lookup"><span data-stu-id="424cc-383">Improved reliability of head tracking, spatial mapping, and other runtimes.</span></span>

## <span data-ttu-id="424cc-384">Windows 全息版 1903-2020 年1月更新</span><span class="sxs-lookup"><span data-stu-id="424cc-384">Windows Holographic, version 1903 - January 2020 Update</span></span> 
- <span data-ttu-id="424cc-385">組建18362.1043</span><span class="sxs-lookup"><span data-stu-id="424cc-385">Build 18362.1043</span></span>
 
<span data-ttu-id="424cc-386">更新中的改進與修正：</span><span class="sxs-lookup"><span data-stu-id="424cc-386">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="424cc-387">在使用 HoloLens 2 模擬器時，改善獨佔式應用程式的穩定性。</span><span class="sxs-lookup"><span data-stu-id="424cc-387">Improved stability for exclusive apps when working with the HoloLens 2 emulator.</span></span>

## <span data-ttu-id="424cc-388">Windows 全息版 1903-2019 年12月更新</span><span class="sxs-lookup"><span data-stu-id="424cc-388">Windows Holographic, version 1903 - December 2019 Update</span></span> 
- <span data-ttu-id="424cc-389">組建18362.1042</span><span class="sxs-lookup"><span data-stu-id="424cc-389">Build 18362.1042</span></span>

<span data-ttu-id="424cc-390">更新中的改進與修正：</span><span class="sxs-lookup"><span data-stu-id="424cc-390">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="424cc-391">引進了上次階段複製 (LSR) 修正程式。</span><span class="sxs-lookup"><span data-stu-id="424cc-391">Introduced last stage reproduction (LSR) fixes.</span></span> <span data-ttu-id="424cc-392">改善全息影像的視覺轉譯，以更精確的方式來顯示其深度。</span><span class="sxs-lookup"><span data-stu-id="424cc-392">Improved visual rendering of holograms to appear more stable and crisp by more accurately accounting for their depth.</span></span> <span data-ttu-id="424cc-393">如果應用程式未正確設定全息影像的深度，此更新將會更明顯。</span><span class="sxs-lookup"><span data-stu-id="424cc-393">This symptom will be more noticeable after this update if apps don't set the depth of holograms correctly.</span></span>
- <span data-ttu-id="424cc-394">固定應用程式的穩定穩定性，並在獨佔 app 之間流覽。</span><span class="sxs-lookup"><span data-stu-id="424cc-394">Fixed stability of exclusive apps and navigation between exclusive apps.</span></span>
- <span data-ttu-id="424cc-395">已解決當裝置處於待機狀態幾天之後，混合現實捕獲無法錄製影片的問題。</span><span class="sxs-lookup"><span data-stu-id="424cc-395">Resolved an issue where mixed reality capture couldn't record video after the device was in standby state for several days.</span></span>
- <span data-ttu-id="424cc-396">改良的全息圖穩定性。</span><span class="sxs-lookup"><span data-stu-id="424cc-396">Improved hologram stability.</span></span>

## <span data-ttu-id="424cc-397">Windows 全息版，版本 1903-2019 年11月更新</span><span class="sxs-lookup"><span data-stu-id="424cc-397">Windows Holographic, version 1903 - November 2019 Update</span></span> 
- <span data-ttu-id="424cc-398">組建18362.1039</span><span class="sxs-lookup"><span data-stu-id="424cc-398">Build 18362.1039</span></span>

<span data-ttu-id="424cc-399">更新中的改進與修正：</span><span class="sxs-lookup"><span data-stu-id="424cc-399">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="424cc-400">固定的功能，可讓您在英文 CA 和 en-us 的初始設定期間， **選取** 語音命令。</span><span class="sxs-lookup"><span data-stu-id="424cc-400">Fixed functionality of **Select** voice commands during initial setup for en-CA and en-AU.</span></span>
- <span data-ttu-id="424cc-401">改善最新 Unity 及混合式現實工具 (MRTK) 版本中所放置之物件的視覺品質。</span><span class="sxs-lookup"><span data-stu-id="424cc-401">Improved visual quality of objects placed far away in the latest Unity and Mixed Reality Toolkit (MRTK) versions.</span></span>
- <span data-ttu-id="424cc-402">已修正在啟動時，全息版應用程式在啟動時停滯在暫停狀態的問題，直到 [開始] 功能表開啟然後關閉為止。</span><span class="sxs-lookup"><span data-stu-id="424cc-402">Fixed addressing issues with holographic applications getting stuck in a paused state on startup until the Start menu was opened and then closed.</span></span>
- <span data-ttu-id="424cc-403">OpenXR 與 HoloLens 2 和模擬器的執行時間一致性修正程式和改良功能。</span><span class="sxs-lookup"><span data-stu-id="424cc-403">OpenXR runtime conformance fixes and improvements for HoloLens 2 and the emulator.</span></span>
