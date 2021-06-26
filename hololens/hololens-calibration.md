---
title: 改善視覺品質和緩和
description: 瞭解如何 (IPD) 校正您的 interpupillary 距離，以改善您在 HoloLens 裝置上的視覺效果品質。
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: 校正、舒適、視覺效果、品質、ipd、HoloLens、Windows Mixed Reality、VR 耳機
ms.openlocfilehash: 62d83aa5c6032d15b26fbc7938859bdaf74151f4
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924140"
---
# <a name="improve-visual-quality-and-comfort"></a><span data-ttu-id="e81f0-104">改善視覺品質和緩和</span><span class="sxs-lookup"><span data-stu-id="e81f0-104">Improve visual quality and comfort</span></span>

<span data-ttu-id="e81f0-105">HoloLens 2 和 HoloLens (第1代) 都能更妥善地校正為您獨特的眼睛。</span><span class="sxs-lookup"><span data-stu-id="e81f0-105">HoloLens 2 and HoloLens (1st gen) both work better when they're calibrated to your unique eyes.</span></span>

<span data-ttu-id="e81f0-106">雖然這兩個裝置都需要校正以獲得最佳的全像全像觀賞體驗，但它們使用不同的校正技術和技巧。</span><span class="sxs-lookup"><span data-stu-id="e81f0-106">While both devices need to calibrate for the best hologram viewing experience, they use different calibration technologies and techniques.</span></span>  <span data-ttu-id="e81f0-107">跳至 [HoloLens 2 校正](#calibrating-your-hololens-2) 或 [HoloLens (第一代) 校正](#calibrating-your-hololens-1st-gen)。</span><span class="sxs-lookup"><span data-stu-id="e81f0-107">Jump to [HoloLens 2 calibration](#calibrating-your-hololens-2) or [HoloLens (1st gen) calibration](#calibrating-your-hololens-1st-gen).</span></span>

## <a name="calibrating-your-hololens-2"></a><span data-ttu-id="e81f0-108">校正您的 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="e81f0-108">Calibrating your HoloLens 2</span></span>

<span data-ttu-id="e81f0-109">HoloLens 2 使用眼睛追蹤技術來改善您的體驗，以及與虛擬環境互動。</span><span class="sxs-lookup"><span data-stu-id="e81f0-109">HoloLens 2 uses eye-tracking technology to improve your experience seeing and interacting with the virtual environment.</span></span> <span data-ttu-id="e81f0-110">校正 HoloLens 2 可確保它可以精確地追蹤您的眼睛 (，以及使用裝置) 的任何其他人的眼睛。</span><span class="sxs-lookup"><span data-stu-id="e81f0-110">Calibrating the HoloLens 2 ensures that it can accurately track your eyes (and the eyes of anyone else who uses the device).</span></span> <span data-ttu-id="e81f0-111">它也可協助使用者緩和、全息全像對齊，以及進行手動追蹤。</span><span class="sxs-lookup"><span data-stu-id="e81f0-111">It also helps with user comfort, hologram alignment, and hand tracking.</span></span> <span data-ttu-id="e81f0-112">在校正之後，即使面板在您的頭上轉移，還是會正確顯示全像投影。</span><span class="sxs-lookup"><span data-stu-id="e81f0-112">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

<span data-ttu-id="e81f0-113">HoloLens 2 在下列情況下會提示使用者校正裝置：</span><span class="sxs-lookup"><span data-stu-id="e81f0-113">HoloLens 2 prompts a user to calibrate the device under the following circumstances:</span></span>

- <span data-ttu-id="e81f0-114">使用者第一次使用裝置</span><span class="sxs-lookup"><span data-stu-id="e81f0-114">The user is using the device for the first time</span></span>
- <span data-ttu-id="e81f0-115">使用者先前退出宣告校正流程</span><span class="sxs-lookup"><span data-stu-id="e81f0-115">The user previously opted out of the calibration process</span></span>
- <span data-ttu-id="e81f0-116">上次使用者使用裝置時，校正程式未成功</span><span class="sxs-lookup"><span data-stu-id="e81f0-116">The calibration process didn't succeed the last time the user used the device</span></span>
- <span data-ttu-id="e81f0-117">使用者已刪除其校正設定檔</span><span class="sxs-lookup"><span data-stu-id="e81f0-117">The user has deleted their calibration profiles</span></span>
- <span data-ttu-id="e81f0-118">裝置會關閉並重新開啟，且適用上述任何情況</span><span class="sxs-lookup"><span data-stu-id="e81f0-118">The device is taken off and puts back on and any of the above circumstances apply</span></span> 


![調整為眼睛的校正提示。](./images/07-et-adjust-for-your-eyes.png)

<span data-ttu-id="e81f0-120">在這個過程中，您將會看到一組目標 (gem) 。</span><span class="sxs-lookup"><span data-stu-id="e81f0-120">During this process, you'll look at a set of targets (gems).</span></span> <span data-ttu-id="e81f0-121">如果您在校正期間閃爍，但試著將焦點放在 gem 上，而不是在房間內的其他物件，則會有問題。</span><span class="sxs-lookup"><span data-stu-id="e81f0-121">It's fine if you blink during calibration, but try to stay focused on the gems instead of other objects in the room.</span></span>  <span data-ttu-id="e81f0-122">將焦點放在 gem 上，可讓 HoloLens 學習呈現您的全像世界的眼睛。</span><span class="sxs-lookup"><span data-stu-id="e81f0-122">Focusing on the gems allows HoloLens to learn about your eye position to render your holographic world.</span></span>

![校正提示會告知使用者保持不進入，並遵循其眼睛的點。](./images/07-et-hold-head-still.png)

![使用 gem 範例的校正提示。](./images/08-et-gems.png)

![校正提示調整。](./images/09-et-adjusting.png)

<span data-ttu-id="e81f0-126">如果校正成功，您會看到成功畫面。</span><span class="sxs-lookup"><span data-stu-id="e81f0-126">If calibration was successful, you'll see a success screen.</span></span>  <span data-ttu-id="e81f0-127">如果沒有，請閱讀更多有關 [診斷校正失敗](hololens2-display.md#troubleshooting)的資訊。</span><span class="sxs-lookup"><span data-stu-id="e81f0-127">If not, read more about [diagnosing calibration failures](hololens2-display.md#troubleshooting).</span></span>

![校正提示成功。](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a><span data-ttu-id="e81f0-129">共用裝置或會話時的校正</span><span class="sxs-lookup"><span data-stu-id="e81f0-129">Calibration when sharing a device or session</span></span>

<span data-ttu-id="e81f0-130">多個使用者可以共用 HoloLens 2 的裝置，而不需要每個人都經過裝置設定。</span><span class="sxs-lookup"><span data-stu-id="e81f0-130">Multiple users can share a HoloLens 2 device, without a need for each person to go through device setup.</span></span> <span data-ttu-id="e81f0-131">當新的使用者第一次將裝置置於其前端時，HoloLens 2 會自動提示使用者校正視覺效果。</span><span class="sxs-lookup"><span data-stu-id="e81f0-131">When a new user puts the device on their head for the first time, HoloLens 2 automatically prompts the user to calibrate visuals.</span></span> <span data-ttu-id="e81f0-132">當先前已校正視覺效果的使用者將裝置置於其前端時，顯示器會順暢地調整品質和舒適的觀賞體驗。</span><span class="sxs-lookup"><span data-stu-id="e81f0-132">When a user that has previously calibrated visuals puts the device on their head, the display seamlessly adjusts for quality and a comfortable viewing experience.</span></span>  

### <a name="manually-starting-the-calibration-process"></a><span data-ttu-id="e81f0-133">手動啟動校正程式</span><span class="sxs-lookup"><span data-stu-id="e81f0-133">Manually starting the calibration process</span></span>

1. <span data-ttu-id="e81f0-134">使用 [開始] 手勢開啟 [ [**開始** ] 功能表](hololens2-basic-usage.md#start-gesture)。</span><span class="sxs-lookup"><span data-stu-id="e81f0-134">Use the start gesture to open the [**Start** menu](hololens2-basic-usage.md#start-gesture).</span></span>
1. <span data-ttu-id="e81f0-135">如果設定應用程式未釘選到 **開始**，請選取 [ **所有應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="e81f0-135">If the Settings app isn't pinned to **Start**, select **All Apps**.</span></span>
1. <span data-ttu-id="e81f0-136">選取 [**設定**]，然後選取 [**系統**  >  **校正**  >  **視覺校正**]  >  **執行眼睛校正**。</span><span class="sxs-lookup"><span data-stu-id="e81f0-136">Select **Settings**, and then select **System** > **Calibration** > **Eye Calibration** > **Run eye calibration**.</span></span>

   ![[設定] 應用程式，顯示 [執行眼睛校正] 選項](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a><span data-ttu-id="e81f0-138">自動眼睛位置支援</span><span class="sxs-lookup"><span data-stu-id="e81f0-138">Auto Eye Position Support</span></span>

<span data-ttu-id="e81f0-139">在 HoloLens 2 中，眼睛可提供精確的全息圖定位、熟悉的觀賞體驗，以及改善的顯示器品質。</span><span class="sxs-lookup"><span data-stu-id="e81f0-139">In HoloLens 2, eye positions enable accurate hologram positioning, comfortable viewing experience, and improved display quality.</span></span> <span data-ttu-id="e81f0-140">眼睛的位置會在內部計算為眼睛追蹤計算的一部分。</span><span class="sxs-lookup"><span data-stu-id="e81f0-140">Eye positions are computed internally as part of the eye tracking computation.</span></span> <span data-ttu-id="e81f0-141">不過，這會要求每位使用者經過眼睛追蹤校正，即使體驗可能不需要眼睛的輸入。</span><span class="sxs-lookup"><span data-stu-id="e81f0-141">However, this requires each user to go through eye tracking calibration, even when the experience might not require eye gaze input.</span></span>

<span data-ttu-id="e81f0-142">**自動眼睛位置 (AEP)** 可讓這些案例具有無互動的方式，以計算使用者的眼睛位置。</span><span class="sxs-lookup"><span data-stu-id="e81f0-142">**Auto Eye Position (AEP)** enables these scenarios with an interaction-free way to compute eye positions for the user.</span></span> <span data-ttu-id="e81f0-143">自動眼睛位置會從使用者放置於裝置的時刻，自動開始在背景中工作。</span><span class="sxs-lookup"><span data-stu-id="e81f0-143">Auto Eye Position starts working in the background automatically from the moment the user puts on the device.</span></span> <span data-ttu-id="e81f0-144">如果使用者沒有先前的眼睛追蹤校正，則在處理時間 20-30 秒後，自動眼睛位置將開始提供使用者的眼睛位置給顯示系統。</span><span class="sxs-lookup"><span data-stu-id="e81f0-144">If the user doesn't have a prior eye tracking calibration, Auto Eye Position will start providing the user's eye positions to the display system after a processing time of 20 - 30 seconds.</span></span> <span data-ttu-id="e81f0-145">使用者資料不會保存在裝置上，而且如果使用者關閉裝置，或裝置重新開機或從睡眠狀態喚醒，則會重複此程式。</span><span class="sxs-lookup"><span data-stu-id="e81f0-145">The user data isn't persisted on the device and this process is repeated if the user takes off and puts the device back on or if the device reboots or wakes up from sleep.</span></span>

<span data-ttu-id="e81f0-146">當 uncalibrated 使用者放在裝置上時，會有一些系統行為變更，以及自動眼睛位置功能。</span><span class="sxs-lookup"><span data-stu-id="e81f0-146">There are a few system behavior changes with Auto Eye Position feature when an uncalibrated user puts on the device.</span></span> <span data-ttu-id="e81f0-147">在此內容中，uncalibrated 使用者是指未曾在裝置上經歷過眼睛追蹤校正程式的人。</span><span class="sxs-lookup"><span data-stu-id="e81f0-147">In this context, an uncalibrated user refers to someone who hasn't gone through the eye tracking calibration process on the device previously.</span></span>

| <span data-ttu-id="e81f0-148">作用中的應用程式</span><span class="sxs-lookup"><span data-stu-id="e81f0-148">Active Application</span></span> | <span data-ttu-id="e81f0-149">先前的行為</span><span class="sxs-lookup"><span data-stu-id="e81f0-149">Prior Behavior</span></span> | <span data-ttu-id="e81f0-150">Windows 全像版本 20H2 Update 的行為</span><span class="sxs-lookup"><span data-stu-id="e81f0-150">Behavior from Windows Holographic, version 20H2 Update</span></span> |
|:-------------------|:-----------------|:-----------------------------------|
| <span data-ttu-id="e81f0-151">未啟用的應用程式或全息式 Shell</span><span class="sxs-lookup"><span data-stu-id="e81f0-151">Non-gaze enabled app or Holographic Shell</span></span> |<span data-ttu-id="e81f0-152">隨即顯示 [眼睛追蹤校正提示] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="e81f0-152">Eye tracking calibration prompt dialog is displayed.</span></span> | <span data-ttu-id="e81f0-153">不會顯示任何提示。</span><span class="sxs-lookup"><span data-stu-id="e81f0-153">No prompt is displayed.</span></span> |
| <span data-ttu-id="e81f0-154">啟用注視的應用程式</span><span class="sxs-lookup"><span data-stu-id="e81f0-154">Gaze enabled app</span></span> | <span data-ttu-id="e81f0-155">隨即顯示 [眼睛追蹤校正提示] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="e81f0-155">Eye tracking calibration prompt dialog is displayed.</span></span> | <span data-ttu-id="e81f0-156">只有當應用程式存取眼睛眼的串流時，才會顯示眼睛追蹤校正提示。</span><span class="sxs-lookup"><span data-stu-id="e81f0-156">Eye tracking calibration prompt is displayed only when the application accesses eye gaze stream.</span></span> |

<span data-ttu-id="e81f0-157">如果使用者從未啟用的已啟用應用程式轉換為存取注視資料的應用程式，則會顯示校正提示。</span><span class="sxs-lookup"><span data-stu-id="e81f0-157">If the user transitions from a non-gaze enabled application to one that accesses the gaze data, the calibration prompt will be displayed.</span></span> 

<span data-ttu-id="e81f0-158">所有其他系統行為會類似于目前的使用者沒有使用中的眼睛追蹤校正。</span><span class="sxs-lookup"><span data-stu-id="e81f0-158">All other system behavior will be similar to when the current user doesn't have an active eye tracking calibration.</span></span> <span data-ttu-id="e81f0-159">例如，將不會啟用單次開始手勢。</span><span class="sxs-lookup"><span data-stu-id="e81f0-159">For example, the One-handed Start gesture won't be enabled.</span></span> <span data-ttu-id="e81f0-160">初始設定的全新體驗將不會有任何變更。</span><span class="sxs-lookup"><span data-stu-id="e81f0-160">There will be no change to the Out-Of-Box-Experience for initial setup.</span></span>

<span data-ttu-id="e81f0-161">針對需要眼睛資料或精確全息圖定位的體驗，建議 uncalibrated 使用者執行眼睛追蹤校正。</span><span class="sxs-lookup"><span data-stu-id="e81f0-161">For experiences that require eye gaze data or precise hologram positioning, we recommend uncalibrated users to run eye tracking calibration.</span></span> <span data-ttu-id="e81f0-162">您可以從眼睛追蹤校正提示字元，或從 [開始] 功能表啟動 [設定] 應用程式，然後選取 [ **系統 > 校正] > 眼睛校正 > 執行眼睛校正**] 來存取它。</span><span class="sxs-lookup"><span data-stu-id="e81f0-162">It's accessible from the eye tracking calibration prompt or by launching the Settings app from the start menu, and then selecting **System > Calibration > Eye Calibration > Run eye calibration**.</span></span>

#### <a name="deferred-calibration-prompt"></a><span data-ttu-id="e81f0-163">延後校正提示</span><span class="sxs-lookup"><span data-stu-id="e81f0-163">Deferred Calibration Prompt</span></span>

<span data-ttu-id="e81f0-164">使用自動眼睛位置時，會延後眼睛追蹤校正提示對話方塊，直到應用程式要求眼睛眼的資料為止。</span><span class="sxs-lookup"><span data-stu-id="e81f0-164">With Auto Eye Position, the Eye Tracking Calibration prompt dialog is deferred until an application requests Eye Gaze data.</span></span> <span data-ttu-id="e81f0-165">這可確保當使用中的應用程式不需要注視時，不會提示使用者。</span><span class="sxs-lookup"><span data-stu-id="e81f0-165">This ensures that there's no prompt to the user when the active application doesn't require gaze.</span></span> <span data-ttu-id="e81f0-166">如果應用程式需要注視資料，而目前的使用者未經過校正，則會顯示一則校正提示。</span><span class="sxs-lookup"><span data-stu-id="e81f0-166">If the application does require gaze data and the current user isn't calibrated, the user is presented with a calibration prompt.</span></span> <span data-ttu-id="e81f0-167">這種行為可用來在適當的時間為體驗顯示眼睛追蹤校正提示。</span><span class="sxs-lookup"><span data-stu-id="e81f0-167">This behavior could be used to display eye tracking calibration prompt at a suitable time for the experience.</span></span> <span data-ttu-id="e81f0-168">基於下列原因，建議使用這個方法</span><span class="sxs-lookup"><span data-stu-id="e81f0-168">This method is recommended for the following reasons</span></span>

1.  <span data-ttu-id="e81f0-169">[眼睛追蹤校正提示] 對話方塊會提供使用者有關為何需要眼睛追蹤的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e81f0-169">The Eye Tracking Calibration Prompt dialog provides the user with details on why eye tracking is needed.</span></span>
2.  <span data-ttu-id="e81f0-170">讓使用者有辦法拒絕其眼睛。</span><span class="sxs-lookup"><span data-stu-id="e81f0-170">Presents the user a way to decline to have their eyes calibrated.</span></span>

<span data-ttu-id="e81f0-171">如果使用者選擇啟動眼睛追蹤校正，則在完成校正之後，焦點應該會返回原始應用程式。</span><span class="sxs-lookup"><span data-stu-id="e81f0-171">If the user chooses to launch the Eye Tracking Calibration, the focus should returning to the original application after calibration completes.</span></span> 

### <a name="calibration-data-and-security"></a><span data-ttu-id="e81f0-172">校正資料和安全性</span><span class="sxs-lookup"><span data-stu-id="e81f0-172">Calibration data and security</span></span>

<span data-ttu-id="e81f0-173">校正資訊會儲存在本機裝置上，且不會與任何帳戶資訊相關聯。</span><span class="sxs-lookup"><span data-stu-id="e81f0-173">Calibration information is stored locally on the device and isn't associated with any account information.</span></span> <span data-ttu-id="e81f0-174">沒有任何已使用裝置而不需要校正的記錄。</span><span class="sxs-lookup"><span data-stu-id="e81f0-174">There's no record of who has used the device without calibration.</span></span> <span data-ttu-id="e81f0-175">這表示新的使用者第一次使用裝置時，會收到提示以校正視覺效果，以及選擇不進行校正的使用者或校正不成功。</span><span class="sxs-lookup"><span data-stu-id="e81f0-175">This mean new users will get prompted to calibrate visuals when they use the device for the first time, and users who opted out of calibration previously or if calibration was unsuccessful.</span></span>

<span data-ttu-id="e81f0-176">裝置可在本機儲存高達50的校正設定檔。</span><span class="sxs-lookup"><span data-stu-id="e81f0-176">The device can locally store up to 50 calibration profiles.</span></span> <span data-ttu-id="e81f0-177">到達這個號碼之後，裝置會自動刪除最舊的未使用設定檔。</span><span class="sxs-lookup"><span data-stu-id="e81f0-177">After this number is reached, the device automatically deletes the oldest unused profile.</span></span>

<span data-ttu-id="e81f0-178">您一律可以從裝置的 [**設定**  >  **隱私權**  >  **留意追蹤**] 中刪除校正資訊。</span><span class="sxs-lookup"><span data-stu-id="e81f0-178">Calibration information can always be deleted from the device in **Settings** > **Privacy** > **Eye tracker**.</span></span>  

### <a name="disable-calibration"></a><span data-ttu-id="e81f0-179">停用校正</span><span class="sxs-lookup"><span data-stu-id="e81f0-179">Disable calibration</span></span>

<span data-ttu-id="e81f0-180">您也可以遵循下列步驟來停用校正提示：</span><span class="sxs-lookup"><span data-stu-id="e81f0-180">You can also disable the calibration prompt by following these steps:</span></span>

1. <span data-ttu-id="e81f0-181">選取 [**設定**  >  **系統**  >  **校正**]。</span><span class="sxs-lookup"><span data-stu-id="e81f0-181">Select **Settings** > **System** > **Calibration**.</span></span>
1. <span data-ttu-id="e81f0-182">**當新的人員使用此 HoloLens 時，請關閉，自動要求執行眼睛校正**。</span><span class="sxs-lookup"><span data-stu-id="e81f0-182">Turn off **When a new person uses this HoloLens, automatically ask to run eye calibration**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e81f0-183">這種設定可能會對全像影像轉譯品質和緩和造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="e81f0-183">This setting may adversely affect hologram rendering quality and comfort.</span></span>  <span data-ttu-id="e81f0-184">當您關閉這項設定時，與眼睛追蹤 (的功能（例如文字滾動）) 無法再于沉浸式應用程式中運作。</span><span class="sxs-lookup"><span data-stu-id="e81f0-184">When you turn off this setting, features that depend on eye tracking (such as text scrolling) no longer work in immersive applications.</span></span>

### <a name="hololens-2-eye-tracking-technology"></a><span data-ttu-id="e81f0-185">HoloLens 2 眼睛追蹤技術</span><span class="sxs-lookup"><span data-stu-id="e81f0-185">HoloLens 2 eye-tracking technology</span></span>

<span data-ttu-id="e81f0-186">裝置使用其眼睛追蹤技術來改善顯示器品質，並確保所有的全像投影都正確定位，並可讓您更輕鬆地在3D 中觀看。</span><span class="sxs-lookup"><span data-stu-id="e81f0-186">The device uses its eye-tracking technology to improve display quality, and to ensure that all holograms are positioned accurately and comfortable to view in 3D.</span></span> <span data-ttu-id="e81f0-187">因為它使用眼睛作為地標，所以裝置可以自行調整每位使用者的視覺效果，並調整其視覺效果，因為耳機在使用時稍微移動。</span><span class="sxs-lookup"><span data-stu-id="e81f0-187">Because it uses the eyes as landmarks, the device can adjust itself for every user and tune its visuals as the headset shifts slightly throughout use.</span></span>  <span data-ttu-id="e81f0-188">所有調整都會立即進行，而不需要手動調整。</span><span class="sxs-lookup"><span data-stu-id="e81f0-188">All adjustments happen on the fly without a need for manual tuning.</span></span>
> [!NOTE]
> <span data-ttu-id="e81f0-189">設定 IPD 並非適用于 Hololens 2，因為眼睛的位置是由系統所計算。</span><span class="sxs-lookup"><span data-stu-id="e81f0-189">Setting the IPD is not applicable for Hololens 2, since eye positions are computed by the system.</span></span>

<span data-ttu-id="e81f0-190">HoloLens 應用程式會使用眼睛追蹤來追蹤您即時查看的位置。</span><span class="sxs-lookup"><span data-stu-id="e81f0-190">HoloLens applications use eye tracking to track where you're looking in real time.</span></span> <span data-ttu-id="e81f0-191">這是開發人員可使用的主要功能，可讓您在全像全像的環境中，啟用全新的內容層級、人類理解以及互動。</span><span class="sxs-lookup"><span data-stu-id="e81f0-191">This is the main capability developers can use to enable a whole new level of context, human understanding, and interactions within the Holographic experience.</span></span> <span data-ttu-id="e81f0-192">開發人員不需要執行任何動作，即可使用這項功能。</span><span class="sxs-lookup"><span data-stu-id="e81f0-192">Developers don’t need to do anything to use this capability.</span></span>

## <a name="calibrating-your-hololens-1st-gen"></a><span data-ttu-id="e81f0-193"> (第1代) 校準 HoloLens</span><span class="sxs-lookup"><span data-stu-id="e81f0-193">Calibrating your HoloLens (1st gen)</span></span>

<span data-ttu-id="e81f0-194">HoloLens (第1代) 會根據您的 [interpupillary 距離](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD) 來調整全像顯示器。</span><span class="sxs-lookup"><span data-stu-id="e81f0-194">HoloLens (1st gen) adjusts hologram display according to your [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD).</span></span> <span data-ttu-id="e81f0-195">如果 IPD 不正確，可能會顯示不穩定或距離不穩定的全像。</span><span class="sxs-lookup"><span data-stu-id="e81f0-195">If the IPD isn't accurate, holograms may appear unstable or at an incorrect distance.</span></span> <span data-ttu-id="e81f0-196">您可以藉由將裝置校準至 interpupillary 距離 (IPD) ，來改善視覺效果的品質。</span><span class="sxs-lookup"><span data-stu-id="e81f0-196">You can improve the quality of your visuals by calibrating the device to your interpupillary distance (IPD).</span></span>

<span data-ttu-id="e81f0-197">當您將 HoloLens (第1代) 裝置時，它會在 Cortana 引進您的視覺效果之後，提示您進行校正。</span><span class="sxs-lookup"><span data-stu-id="e81f0-197">When you set up your HoloLens (1st gen) device, it prompts to calibrate your visuals after Cortana introduces herself.</span></span> <span data-ttu-id="e81f0-198">建議您在此設定階段完成校正步驟。</span><span class="sxs-lookup"><span data-stu-id="e81f0-198">It's recommended that you complete the calibration step during this setup phase.</span></span> <span data-ttu-id="e81f0-199">不過，您可以等候 Cortana 提示您，然後說「略過」來略過。</span><span class="sxs-lookup"><span data-stu-id="e81f0-199">However you can skip it by waiting until Cortana prompts you and then saying "Skip."</span></span>

<span data-ttu-id="e81f0-200">在校正程式進行期間，HoloLens 會要求您將手指與每一系列的六個目標對齊。</span><span class="sxs-lookup"><span data-stu-id="e81f0-200">During the calibration process, HoloLens asks you to align your finger with a series of six targets per eye.</span></span> <span data-ttu-id="e81f0-201">HoloLens 會使用此程式，為您的眼睛正確設定 IPD。</span><span class="sxs-lookup"><span data-stu-id="e81f0-201">HoloLens uses this process to set the IPD correctly for your eyes.</span></span>

![第二個步驟中的 IPD 手指對齊畫面](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a><span data-ttu-id="e81f0-203">手動啟動校正程式</span><span class="sxs-lookup"><span data-stu-id="e81f0-203">Manually start the calibration process</span></span>

<span data-ttu-id="e81f0-204">如果您需要更新校正，或如果新使用者需要調整，您可以在任何時間手動執行校正應用程式。</span><span class="sxs-lookup"><span data-stu-id="e81f0-204">If you need to update the calibration or if a new user needs to adjust it, you can manually run the Calibration app at any time.</span></span> <span data-ttu-id="e81f0-205">預設會安裝校正應用程式。</span><span class="sxs-lookup"><span data-stu-id="e81f0-205">The Calibration app is installed by default.</span></span> <span data-ttu-id="e81f0-206">您可以使用 [ **開始** ] 功能表或 [設定] 應用程式來存取它。</span><span class="sxs-lookup"><span data-stu-id="e81f0-206">You can access it by using either the **Start** menu or the Settings app.</span></span>

<span data-ttu-id="e81f0-207">若要使用 [ **開始** ] 功能表來執行校正應用程式，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e81f0-207">To use the **Start** menu to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="e81f0-208">使用 [bloom](hololens1-basic-usage.md) 手勢開啟 [ **開始** ] 功能表。</span><span class="sxs-lookup"><span data-stu-id="e81f0-208">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="e81f0-209">若要查看所有應用程式，請選取 [] **+** 。</span><span class="sxs-lookup"><span data-stu-id="e81f0-209">To view all apps, select **+**.</span></span>
1. <span data-ttu-id="e81f0-210">選取 [ **校正**]。</span><span class="sxs-lookup"><span data-stu-id="e81f0-210">Select **Calibration**.</span></span>

![從 shell 存取校正應用程式](./images/calibration-shell.png)

![在啟動後，會顯示為即時 Cube 的校正應用程式](./images/calibration-livecube-200px.png)

<span data-ttu-id="e81f0-213">若要使用 [設定] 應用程式來執行校正應用程式，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e81f0-213">To use the Settings app to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="e81f0-214">使用 [bloom](hololens1-basic-usage.md) 手勢開啟 [ **開始** ] 功能表。</span><span class="sxs-lookup"><span data-stu-id="e81f0-214">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="e81f0-215">如果 **設定** 未釘選到 **開始**，請選取 **+** 以查看所有應用程式。</span><span class="sxs-lookup"><span data-stu-id="e81f0-215">If **Settings** isn't pinned to **Start**, select **+** to view all apps.</span></span>
1. <span data-ttu-id="e81f0-216">選取 [設定]。</span><span class="sxs-lookup"><span data-stu-id="e81f0-216">Select **Settings**.</span></span>
1. <span data-ttu-id="e81f0-217">選取 [**系統**  >  **公用程式**]  >  **開啟校正**。</span><span class="sxs-lookup"><span data-stu-id="e81f0-217">Select **System** > **Utilities** > **Open Calibration**.</span></span>

![從設定應用程式啟動校正應用程式](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a><span data-ttu-id="e81f0-219">沉浸式頭戴裝置</span><span class="sxs-lookup"><span data-stu-id="e81f0-219">Immersive headsets</span></span>

<span data-ttu-id="e81f0-220">有些沉浸式耳機提供自訂 IPD 設定的能力。</span><span class="sxs-lookup"><span data-stu-id="e81f0-220">Some immersive headsets provide the ability to customize the IPD setting.</span></span> <span data-ttu-id="e81f0-221">若要變更耳機的 IPD，請開啟 [設定] 應用程式並選取 [**混合現實**  >  **耳機顯示**]，然後移動滑杆控制項。</span><span class="sxs-lookup"><span data-stu-id="e81f0-221">To change the IPD for your headset, open the Settings app and select **Mixed reality** > **Headset display**, and then move the slider control.</span></span> <span data-ttu-id="e81f0-222">您將會在耳機中即時看到變更。</span><span class="sxs-lookup"><span data-stu-id="e81f0-222">You’ll see the changes in real time in your headset.</span></span> <span data-ttu-id="e81f0-223">如果您知道您的 IPD，或許可以造訪 optometrist，也可以直接輸入。</span><span class="sxs-lookup"><span data-stu-id="e81f0-223">If you know your IPD, maybe from a visit to the optometrist, you can enter it directly as well.</span></span>

<span data-ttu-id="e81f0-224">您也可以選取 [**設定**  >  **混合現實**  >  **耳機顯示**] 來調整電腦上的這項設定。</span><span class="sxs-lookup"><span data-stu-id="e81f0-224">You can also adjust this setting on your PC by selecting **Settings** > **Mixed reality** > **Headset display**.</span></span>

<span data-ttu-id="e81f0-225">如果您的耳機不支援 IPD 自訂，則會停用此設定。</span><span class="sxs-lookup"><span data-stu-id="e81f0-225">If your headset doesn't support IPD customization, this setting will be disabled.</span></span>
