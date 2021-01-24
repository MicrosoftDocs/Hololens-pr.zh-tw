---
title: 提高視覺品質和舒適度
description: 瞭解如何校正您的瞳孔距離 (IPD) ，以改善 HoloLens 裝置上的視覺效果品質。
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
keywords: 校準、舒適、視覺效果、品質、ipd、HoloLens、Windows Mixed Reality、VR 頭戴式裝置
ms.openlocfilehash: e975e2ccd978d4ec6b5331af0ae566af116711c5
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283544"
---
# <span data-ttu-id="91d31-104">改善視覺品質和舒適度</span><span class="sxs-lookup"><span data-stu-id="91d31-104">Improve visual quality and comfort</span></span>

<span data-ttu-id="91d31-105">HoloLens 2 和 HoloLens (第 1 代) 在與您獨一無二的眼球校正後，都能運作地更理想。</span><span class="sxs-lookup"><span data-stu-id="91d31-105">HoloLens 2 and HoloLens (1st gen) both work better when they're calibrated to your unique eyes.</span></span>

<span data-ttu-id="91d31-106">這兩個裝置都需要校正以提供最佳的全像投影觀賞體驗，但它們使用不同的校正技術和技巧。</span><span class="sxs-lookup"><span data-stu-id="91d31-106">While both devices need to calibrate for the best hologram viewing experience, they use different calibration technologies and techniques.</span></span>  <span data-ttu-id="91d31-107">請跳至 [HoloLens 2 校正](#calibrating-your-hololens-2)或 [HoloLens (第 1 代) 校正](#calibrating-your-hololens-1st-gen)。</span><span class="sxs-lookup"><span data-stu-id="91d31-107">Jump to [HoloLens 2 calibration](#calibrating-your-hololens-2) or [HoloLens (1st gen) calibration](#calibrating-your-hololens-1st-gen).</span></span>

## <span data-ttu-id="91d31-108">校正 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="91d31-108">Calibrating your HoloLens 2</span></span>

<span data-ttu-id="91d31-109">HoloLens 2 使用眼球追蹤技術來改善您觀看虛擬環境並與其互動的體驗。</span><span class="sxs-lookup"><span data-stu-id="91d31-109">HoloLens 2 uses eye-tracking technology to improve your experience seeing and interacting with the virtual environment.</span></span> <span data-ttu-id="91d31-110">校正 HoloLens 2 可確保它能準確追蹤您的眼球 (以及使用裝置的任何其他人的眼球)。</span><span class="sxs-lookup"><span data-stu-id="91d31-110">Calibrating the HoloLens 2 ensures that it can accurately track your eyes (and the eyes of anyone else who uses the device).</span></span> <span data-ttu-id="91d31-111">這也有助於使用者的舒適度、全像投影對齊，和手部追蹤。</span><span class="sxs-lookup"><span data-stu-id="91d31-111">It also helps with user comfort, hologram alignment, and hand tracking.</span></span> <span data-ttu-id="91d31-112">校正之後，即使面板在您的頭上移動，全像投影仍能正確顯示。</span><span class="sxs-lookup"><span data-stu-id="91d31-112">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

<span data-ttu-id="91d31-113">在下列情況下，HoloLens 2 會提示使用者校正裝置：</span><span class="sxs-lookup"><span data-stu-id="91d31-113">HoloLens 2 prompts a user to calibrate the device under the following circumstances:</span></span>

- <span data-ttu-id="91d31-114">使用者第一次使用裝置</span><span class="sxs-lookup"><span data-stu-id="91d31-114">The user is using the device for the first time</span></span>
- <span data-ttu-id="91d31-115">使用者先前退出校正程序</span><span class="sxs-lookup"><span data-stu-id="91d31-115">The user previously opted out of the calibration process</span></span>
- <span data-ttu-id="91d31-116">使用者最後一次使用裝置時，無法成功進行校正處理程序</span><span class="sxs-lookup"><span data-stu-id="91d31-116">The calibration process didn't succeed the last time the user used the device</span></span>
- <span data-ttu-id="91d31-117">使用者已刪除其校正設定檔</span><span class="sxs-lookup"><span data-stu-id="91d31-117">The user has deleted their calibration profiles</span></span>
- <span data-ttu-id="91d31-118">裝置被移除並重新放回，而上述任何一種情況均適用</span><span class="sxs-lookup"><span data-stu-id="91d31-118">The device is taken off and puts back on and any of the above circumstances apply</span></span> 


![調整眼球的校正提示。](./images/07-et-adjust-for-your-eyes.png)

<span data-ttu-id="91d31-120">在此程序中，您會看到一組目標 (寶石)。</span><span class="sxs-lookup"><span data-stu-id="91d31-120">During this process, you'll look at a set of targets (gems).</span></span> <span data-ttu-id="91d31-121">您在校正期間眨眼是沒關係的，但請盡量專注在寶石上，而非房間中的其他物體。</span><span class="sxs-lookup"><span data-stu-id="91d31-121">It's fine if you blink during calibration, but try to stay focused on the gems instead of other objects in the room.</span></span>  <span data-ttu-id="91d31-122">專注在寶石上可讓 HoloLens 了解您的眼球位置，以呈現您的全像世界。</span><span class="sxs-lookup"><span data-stu-id="91d31-122">Focusing on the gems allows HoloLens to learn about your eye position to render your holographic world.</span></span>

![校正提示會告訴使用者保持頭部靜止，並用眼睛追蹤圓點。](./images/07-et-hold-head-still.png)

![使用寶石範例的校正提示。](./images/08-et-gems.png)

![校正提示正在調整。](./images/09-et-adjusting.png)

<span data-ttu-id="91d31-126">如果校正成功，您會看到成功畫面。</span><span class="sxs-lookup"><span data-stu-id="91d31-126">If calibration was successful, you'll see a success screen.</span></span>  <span data-ttu-id="91d31-127">如果沒有，請參閱[診斷校正失敗](#troubleshooting-hololens-2-calibration)。</span><span class="sxs-lookup"><span data-stu-id="91d31-127">If not, read more about [diagnosing calibration failures](#troubleshooting-hololens-2-calibration).</span></span>

![校正提示成功。](./images/10-et-success.png)

### <span data-ttu-id="91d31-129">共用裝置或工作階段時的校正</span><span class="sxs-lookup"><span data-stu-id="91d31-129">Calibration when sharing a device or session</span></span>

<span data-ttu-id="91d31-130">多個使用者可以共用 HoloLens 2 裝置，而不需要每個人都進行裝置設定。</span><span class="sxs-lookup"><span data-stu-id="91d31-130">Multiple users can share a HoloLens 2 device, without a need for each person to go through device setup.</span></span> <span data-ttu-id="91d31-131">當新的使用者第一次將裝置放到頭上時，HoloLens 2 會自動提示使用者校正視覺效果。</span><span class="sxs-lookup"><span data-stu-id="91d31-131">When a new user puts the device on their head for the first time, HoloLens 2 automatically prompts the user to calibrate visuals.</span></span> <span data-ttu-id="91d31-132">當先前已校正視覺效果的使用者將裝置放到頭上時，顯示器會順暢地調整品質並提供舒適的觀賞體驗。</span><span class="sxs-lookup"><span data-stu-id="91d31-132">When a user that has previously calibrated visuals puts the device on their head, the display seamlessly adjusts for quality and a comfortable viewing experience.</span></span>  

### <span data-ttu-id="91d31-133">手動開始校正程序</span><span class="sxs-lookup"><span data-stu-id="91d31-133">Manually starting the calibration process</span></span>

1. <span data-ttu-id="91d31-134">使用 [開始] 手勢開啟 [**[開始]** 功能表](hololens2-basic-usage.md#start-gesture)。</span><span class="sxs-lookup"><span data-stu-id="91d31-134">Use the start gesture to open the [**Start** menu](hololens2-basic-usage.md#start-gesture).</span></span>
1. <span data-ttu-id="91d31-135">如果 [設定] 應用程式未釘選至 [開始]\*\*\*\*，請選取 [所有應用程式]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91d31-135">If the Settings app isn't pinned to **Start**, select **All Apps**.</span></span>
1. <span data-ttu-id="91d31-136">選取 [設定]\*\*\*\*，然後選取 **[系統]** > **[校正]** > **[眼球校正]** > **[執行眼球校正]**。</span><span class="sxs-lookup"><span data-stu-id="91d31-136">Select **Settings**, and then select **System** > **Calibration** > **Eye Calibration** > **Run eye calibration**.</span></span>

   ![顯示 [執行眼球校正] 選項的 [設定] 應用程式](./images/C-Settings.Calibration.png)

### <span data-ttu-id="91d31-138">自動眼部定位支援</span><span class="sxs-lookup"><span data-stu-id="91d31-138">Auto Eye Position Support</span></span>

<span data-ttu-id="91d31-139">在 HoloLens 2 中，眼部定位可實現正確的全像投影定位、舒適的觀賞體驗，以及改善顯示品質。</span><span class="sxs-lookup"><span data-stu-id="91d31-139">In HoloLens 2, eye positions enable accurate hologram positioning, comfortable viewing experience, and improved display quality.</span></span> <span data-ttu-id="91d31-140">眼部定位會在內部計算，屬於眼球追蹤計算的一部分。</span><span class="sxs-lookup"><span data-stu-id="91d31-140">Eye positions are computed internally as part of the eye tracking computation.</span></span> <span data-ttu-id="91d31-141">不過，這只需要每位使用者進行眼球追蹤校正，即使體驗可能不需要眼睛注視輸入也一樣。</span><span class="sxs-lookup"><span data-stu-id="91d31-141">However, this requires each user to go through eye tracking calibration, even when the experience might not require eye gaze input.</span></span>

<span data-ttu-id="91d31-142">**自動眼部定位 (AEP)** 允許這些案例以無互動方式為使用者計算眼睛位置。</span><span class="sxs-lookup"><span data-stu-id="91d31-142">**Auto Eye Position (AEP)** enables these scenarios with an interaction-free way to compute eye positions for the user.</span></span> <span data-ttu-id="91d31-143">從使用者戴上裝置開始，[自動眼部定位] 會在背景自動開始運作。</span><span class="sxs-lookup"><span data-stu-id="91d31-143">Auto Eye Position starts working in the background automatically from the moment the user puts on the device.</span></span> <span data-ttu-id="91d31-144">如果使用者沒有先前的眼球追蹤校正，[自動眼部定位] 就會在 20 至 30 秒的處理時間後開始提供使用者的眼部定位給顯示系統。</span><span class="sxs-lookup"><span data-stu-id="91d31-144">If the user doesn't have a prior eye tracking calibration, Auto Eye Position will start providing the user's eye positions to the display system after a processing time of 20 - 30 seconds.</span></span> <span data-ttu-id="91d31-145">如果使用者移除並重新佩戴裝置，或裝置重新開機或從睡眠中喚醒，使用者資料則不會保留在裝置上，且會重複此程序。</span><span class="sxs-lookup"><span data-stu-id="91d31-145">The user data isn't persisted on the device and this process is repeated if the user takes off and puts the device back on or if the device reboots or wakes up from sleep.</span></span>

<span data-ttu-id="91d31-146">當未經校正的使用者配戴裝置時，有一些系統行為會隨著 [自動眼部定位] 功能而變更。</span><span class="sxs-lookup"><span data-stu-id="91d31-146">There are a few system behavior changes with Auto Eye Position feature when an uncalibrated user puts on the device.</span></span> <span data-ttu-id="91d31-147">在這種情況下，未經校正的使用者是指之前未在裝置上透過眼球追蹤校正程式的使用者。</span><span class="sxs-lookup"><span data-stu-id="91d31-147">In this context, an uncalibrated user refers to someone who hasn't gone through the eye tracking calibration process on the device previously.</span></span>

| <span data-ttu-id="91d31-148">使用中應用程式</span><span class="sxs-lookup"><span data-stu-id="91d31-148">Active Application</span></span> | <span data-ttu-id="91d31-149">先前行為</span><span class="sxs-lookup"><span data-stu-id="91d31-149">Prior Behavior</span></span> | <span data-ttu-id="91d31-150">Windows 全像攝影版、版本20H2 更新的行為</span><span class="sxs-lookup"><span data-stu-id="91d31-150">Behavior from Windows Holographic, version 20H2 Update</span></span> |
|:-------------------|:-----------------|:-----------------------------------|
| <span data-ttu-id="91d31-151">未啟用注視的應用程式或全像攝影命令介面</span><span class="sxs-lookup"><span data-stu-id="91d31-151">Non-gaze enabled app or Holographic Shell</span></span> |<span data-ttu-id="91d31-152">會顯示 [眼球追蹤校正提示] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="91d31-152">Eye tracking calibration prompt dialog is displayed.</span></span> | <span data-ttu-id="91d31-153">不會顯示任何提示。</span><span class="sxs-lookup"><span data-stu-id="91d31-153">No prompt is displayed.</span></span> |
| <span data-ttu-id="91d31-154">已啟用注視的應用程式</span><span class="sxs-lookup"><span data-stu-id="91d31-154">Gaze enabled app</span></span> | <span data-ttu-id="91d31-155">會顯示 [眼球追蹤校正提示] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="91d31-155">Eye tracking calibration prompt dialog is displayed.</span></span> | <span data-ttu-id="91d31-156">只會在應用程式存取眼睛注視串流時顯示眼球追蹤校正提示。</span><span class="sxs-lookup"><span data-stu-id="91d31-156">Eye tracking calibration prompt is displayed only when the application accesses eye gaze stream.</span></span> |

<span data-ttu-id="91d31-157">如果使用者從以無凝視啟用的應用程式轉換到一個存取注視資料的應用程式，則會顯示校正提示。</span><span class="sxs-lookup"><span data-stu-id="91d31-157">If the user transitions from a non-gaze enabled application to one that accesses the gaze data, the calibration prompt will be displayed.</span></span> 

<span data-ttu-id="91d31-158">所有其他的系統行為都類似於目前使用者沒有作用中的眼球追蹤校正時的行為。</span><span class="sxs-lookup"><span data-stu-id="91d31-158">All other system behavior will be similar to when the current user doesn't have an active eye tracking calibration.</span></span> <span data-ttu-id="91d31-159">例如，將不會啟用單手 [開始] 手勢。</span><span class="sxs-lookup"><span data-stu-id="91d31-159">For example, the One-handed Start gesture won't be enabled.</span></span> <span data-ttu-id="91d31-160">在初始設定中，全新體驗將不會有任何變更。</span><span class="sxs-lookup"><span data-stu-id="91d31-160">There will be no change to the Out-Of-Box-Experience for initial setup.</span></span>

<span data-ttu-id="91d31-161">針對需要眼睛注視資料或精確的全像投影定位之體驗，我們建議未校正的使用者執行眼球追蹤校正。</span><span class="sxs-lookup"><span data-stu-id="91d31-161">For experiences that require eye gaze data or precise hologram positioning, we recommend uncalibrated users to run eye tracking calibration.</span></span> <span data-ttu-id="91d31-162">您可以從 [眼球追蹤校正提示]，或從 [開始] 功能表啟動 [設定] 應用程式，然後選取 **[系統] > [校正] > [眼球校正] > [執行眼球校正]**。</span><span class="sxs-lookup"><span data-stu-id="91d31-162">It's accessible from the eye tracking calibration prompt or by launching the Settings app from the start menu, and then selecting **System > Calibration > Eye Calibration > Run eye calibration**.</span></span>

#### <span data-ttu-id="91d31-163">延遲校正提示</span><span class="sxs-lookup"><span data-stu-id="91d31-163">Deferred Calibration Prompt</span></span>

<span data-ttu-id="91d31-164">透過 [自動眼部定位]，[眼球追蹤校正提示] 對話方塊會延遲到應用程式要求眼睛注視資料為止。</span><span class="sxs-lookup"><span data-stu-id="91d31-164">With Auto Eye Position, the Eye Tracking Calibration prompt dialog is deferred until an application requests Eye Gaze data.</span></span> <span data-ttu-id="91d31-165">這可確保當使用中的應用程式不需要注視時，系統不會向使用者顯示提示。</span><span class="sxs-lookup"><span data-stu-id="91d31-165">This ensures that there's no prompt to the user when the active application doesn't require gaze.</span></span> <span data-ttu-id="91d31-166">如果應用程式確實需要注視資料，而目前使用者並未校正，系統會顯示校正提示給使用者。</span><span class="sxs-lookup"><span data-stu-id="91d31-166">If the application does require gaze data and the current user isn't calibrated, the user is presented with a calibration prompt.</span></span> <span data-ttu-id="91d31-167">此行為可用來在適當的時間顯示眼球追蹤校正提示。</span><span class="sxs-lookup"><span data-stu-id="91d31-167">This behavior could be used to display eye tracking calibration prompt at a suitable time for the experience.</span></span> <span data-ttu-id="91d31-168">出於下列原因，建議使用此方法</span><span class="sxs-lookup"><span data-stu-id="91d31-168">This method is recommended for the following reasons</span></span>

1.  <span data-ttu-id="91d31-169">[眼球追蹤校正提示] 對話方塊可為使用者提供為何需要眼球追蹤的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="91d31-169">The Eye Tracking Calibration Prompt dialog provides the user with details on why eye tracking is needed.</span></span>
2.  <span data-ttu-id="91d31-170">為使用者提供一種拒絕進行其眼球校正的方法。</span><span class="sxs-lookup"><span data-stu-id="91d31-170">Presents the user a way to decline to have their eyes calibrated.</span></span>

<span data-ttu-id="91d31-171">如果使用者選擇要啟動 [眼球追蹤校正]，在校正完成之後，焦點就會回到原始應用程式。</span><span class="sxs-lookup"><span data-stu-id="91d31-171">If the user chooses to launch the Eye Tracking Calibration, the focus should returning to the original application after calibration completes.</span></span> 

### <span data-ttu-id="91d31-172">疑難排解 HoloLens 2 校正</span><span class="sxs-lookup"><span data-stu-id="91d31-172">Troubleshooting HoloLens 2 calibration</span></span>

<span data-ttu-id="91d31-173">校正應該適用於大部分人，但在某些情況下，校正會失敗。</span><span class="sxs-lookup"><span data-stu-id="91d31-173">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="91d31-174">校正失敗的一些可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="91d31-174">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="91d31-175">分心而未跟隨校正目標</span><span class="sxs-lookup"><span data-stu-id="91d31-175">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="91d31-176">裝置面板髒汙或有刮痕，或裝置面板的位置不正確</span><span class="sxs-lookup"><span data-stu-id="91d31-176">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="91d31-177">鏡片髒汙或有刮痕</span><span class="sxs-lookup"><span data-stu-id="91d31-177">Dirty or scratched glasses</span></span>
- <span data-ttu-id="91d31-178">特定類型的隱形眼鏡與眼鏡 (有色隱形眼鏡、部分散光隱形眼鏡、防紅外線眼鏡、高處方眼鏡、太陽眼鏡或類似項目)</span><span class="sxs-lookup"><span data-stu-id="91d31-178">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="91d31-179">化妝較濃以及假睫毛</span><span class="sxs-lookup"><span data-stu-id="91d31-179">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="91d31-180">頭髮或粗框眼鏡，可能阻擋裝置看到您的眼球</span><span class="sxs-lookup"><span data-stu-id="91d31-180">Hair or thick eyeglass frames if they're blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="91d31-181">某些眼部生理構造、眼部疾病或眼科手術，例如細長眼、長睫毛、弱視、眼球震顫、某些 LASIK 雷射手術或其他眼科手術</span><span class="sxs-lookup"><span data-stu-id="91d31-181">Certain eye physiology, eye conditions, or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="91d31-182">如果校正失敗，請嘗試：</span><span class="sxs-lookup"><span data-stu-id="91d31-182">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="91d31-183">清潔您的裝置面板</span><span class="sxs-lookup"><span data-stu-id="91d31-183">Cleaning your device visor</span></span>
- <span data-ttu-id="91d31-184">清潔您的眼鏡</span><span class="sxs-lookup"><span data-stu-id="91d31-184">Cleaning your glasses</span></span>
- <span data-ttu-id="91d31-185">盡可能將裝置面板推近您的眼睛</span><span class="sxs-lookup"><span data-stu-id="91d31-185">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="91d31-186">清除面板中的物體 (例如頭髮)</span><span class="sxs-lookup"><span data-stu-id="91d31-186">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="91d31-187">開啟房間中的光源或避免陽光直射</span><span class="sxs-lookup"><span data-stu-id="91d31-187">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="91d31-188">如果您已遵守所有指導方針，且仍然校正失敗，您可以在 [設定] 中停用校正提示。</span><span class="sxs-lookup"><span data-stu-id="91d31-188">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="91d31-189">您也可以在 [意見反應中樞](hololens-feedback.md)中提出意見反應，讓我們知道。</span><span class="sxs-lookup"><span data-stu-id="91d31-189">Also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="91d31-190">另請參閱[影像色彩或亮度疑難排解](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="91d31-190">Also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="91d31-191">設定 IPD 並不適用於 HoloLens 2，因為眼球位置是由系統計算。</span><span class="sxs-lookup"><span data-stu-id="91d31-191">Setting IPD is not applicable for HoloLens 2, since eye positions are computed by the system.</span></span> 

### <span data-ttu-id="91d31-192">校正資料與安全性</span><span class="sxs-lookup"><span data-stu-id="91d31-192">Calibration data and security</span></span>

<span data-ttu-id="91d31-193">校正資訊是儲存在裝置本機上，且不會與任何帳戶資訊相關聯。</span><span class="sxs-lookup"><span data-stu-id="91d31-193">Calibration information is stored locally on the device and isn't associated with any account information.</span></span> <span data-ttu-id="91d31-194">沒有已使用裝置而沒有校準的人員記錄。</span><span class="sxs-lookup"><span data-stu-id="91d31-194">There's no record of who has used the device without calibration.</span></span> <span data-ttu-id="91d31-195">這表示新的使用者在第一次使用裝置時，以及對於先前退出校正或校正失敗的使用者，系統會提示他們校正視覺效果。</span><span class="sxs-lookup"><span data-stu-id="91d31-195">This mean new users will get prompted to calibrate visuals when they use the device for the first time, and users who opted out of calibration previously or if calibration was unsuccessful.</span></span>

<span data-ttu-id="91d31-196">此裝置可以在本機儲存多達 50 組校正設定檔。</span><span class="sxs-lookup"><span data-stu-id="91d31-196">The device can locally store up to 50 calibration profiles.</span></span> <span data-ttu-id="91d31-197">在達到此數量之後，裝置會自動將最舊的未使用設定檔刪除。</span><span class="sxs-lookup"><span data-stu-id="91d31-197">After this number is reached, the device automatically deletes the oldest unused profile.</span></span>

<span data-ttu-id="91d31-198">您隨時能從裝置的 **\[設定\]** > **\[隱私權\]** > **\[眼動追蹤儀\]** 中刪除校正資訊。</span><span class="sxs-lookup"><span data-stu-id="91d31-198">Calibration information can always be deleted from the device in **Settings** > **Privacy** > **Eye tracker**.</span></span>  

### <span data-ttu-id="91d31-199">停用校正</span><span class="sxs-lookup"><span data-stu-id="91d31-199">Disable calibration</span></span>

<span data-ttu-id="91d31-200">您也可以遵循下列步驟來停用校正提示：</span><span class="sxs-lookup"><span data-stu-id="91d31-200">You can also disable the calibration prompt by following these steps:</span></span>

1. <span data-ttu-id="91d31-201">選取 **\[設定\]** > **\[系統\]** > **\[校正\]**。</span><span class="sxs-lookup"><span data-stu-id="91d31-201">Select **Settings** > **System** > **Calibration**.</span></span>
1. <span data-ttu-id="91d31-202">關閉 **\[在新人員使用此 HoloLens 時，自動要求執行眼球校正\]**。</span><span class="sxs-lookup"><span data-stu-id="91d31-202">Turn off **When a new person uses this HoloLens, automatically ask to run eye calibration**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="91d31-203">此設定可能會對全像投影轉譯品質和舒適度造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="91d31-203">This setting may adversely affect hologram rendering quality and comfort.</span></span>  <span data-ttu-id="91d31-204">關閉此設定後，依賴眼球追蹤 (例如文字捲動) 的功能就無法在沉浸式應用程式中發揮作用。</span><span class="sxs-lookup"><span data-stu-id="91d31-204">When you turn off this setting, features that depend on eye tracking (such as text scrolling) no longer work in immersive applications.</span></span>

### <span data-ttu-id="91d31-205">HoloLens 2 眼球追蹤技術</span><span class="sxs-lookup"><span data-stu-id="91d31-205">HoloLens 2 eye-tracking technology</span></span>

<span data-ttu-id="91d31-206">裝置會使用其眼球追蹤技術來改善顯示品質，並確保所有全像投影都能正確放置且舒適地在 3D 中觀看。</span><span class="sxs-lookup"><span data-stu-id="91d31-206">The device uses its eye-tracking technology to improve display quality, and to ensure that all holograms are positioned accurately and comfortable to view in 3D.</span></span> <span data-ttu-id="91d31-207">因為它使用眼睛作為地標，所以裝置可以針對每位使用者自行調整，並隨著頭戴式裝置在使用過程中稍微移動而調整其視覺效果。</span><span class="sxs-lookup"><span data-stu-id="91d31-207">Because it uses the eyes as landmarks, the device can adjust itself for every user and tune its visuals as the headset shifts slightly throughout use.</span></span>  <span data-ttu-id="91d31-208">所有調整都會動態發生，不需要手動調整。</span><span class="sxs-lookup"><span data-stu-id="91d31-208">All adjustments happen on the fly without a need for manual tuning.</span></span>
> [!NOTE]
> <span data-ttu-id="91d31-209">設定 IPD 不適用於 Hololens 2，因為眼球位置是由系統計算。</span><span class="sxs-lookup"><span data-stu-id="91d31-209">Setting the IPD is not applicable for Hololens 2, since eye positions are computed by the system.</span></span>

<span data-ttu-id="91d31-210">HoloLens 應用程式使用眼球追蹤以即時追蹤您注視的位置。</span><span class="sxs-lookup"><span data-stu-id="91d31-210">HoloLens applications use eye tracking to track where you're looking in real time.</span></span> <span data-ttu-id="91d31-211">這是開發人員可以使用的主要功能，可啟動全像體驗中的全新環境層級、人類理解及互動。</span><span class="sxs-lookup"><span data-stu-id="91d31-211">This is the main capability developers can use to enable a whole new level of context, human understanding, and interactions within the Holographic experience.</span></span> <span data-ttu-id="91d31-212">開發人員不需要執行任何動作就能使用這項功能。</span><span class="sxs-lookup"><span data-stu-id="91d31-212">Developers don’t need to do anything to use this capability.</span></span>

## <span data-ttu-id="91d31-213">校正 HoloLens (第 1 代)</span><span class="sxs-lookup"><span data-stu-id="91d31-213">Calibrating your HoloLens (1st gen)</span></span>

<span data-ttu-id="91d31-214">HoloLens (第 1 代) 可根據您的 [瞳孔距離](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD) 調整全像投影顯示。</span><span class="sxs-lookup"><span data-stu-id="91d31-214">HoloLens (1st gen) adjusts hologram display according to your [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD).</span></span> <span data-ttu-id="91d31-215">如果 IPD 不精確，全像投影可能會不穩定或呈現不正確的距離。</span><span class="sxs-lookup"><span data-stu-id="91d31-215">If the IPD isn't accurate, holograms may appear unstable or at an incorrect distance.</span></span> <span data-ttu-id="91d31-216">您可以透過將裝置校正至您的瞳孔距離 (IPD) 改善視覺效果品質。</span><span class="sxs-lookup"><span data-stu-id="91d31-216">You can improve the quality of your visuals by calibrating the device to your interpupillary distance (IPD).</span></span>

<span data-ttu-id="91d31-217">當您設定 Hololens (第 1 代) 裝置時，系統會在 Cortana 自我介紹之後提示您校正視覺效果。</span><span class="sxs-lookup"><span data-stu-id="91d31-217">When you set up your HoloLens (1st gen) device, it prompts to calibrate your visuals after Cortana introduces herself.</span></span> <span data-ttu-id="91d31-218">建議您在此設定階段完成校正步驟。</span><span class="sxs-lookup"><span data-stu-id="91d31-218">It's recommended that you complete the calibration step during this setup phase.</span></span> <span data-ttu-id="91d31-219">不過，您也可以等到 Cortana 提示您的時候說「略過」，來略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="91d31-219">However you can skip it by waiting until Cortana prompts you and then saying "Skip."</span></span>

<span data-ttu-id="91d31-220">在校正程序期間，HoloLens 會要求您在每隻眼睛將手指對準一系列六個目標。</span><span class="sxs-lookup"><span data-stu-id="91d31-220">During the calibration process, HoloLens asks you to align your finger with a series of six targets per eye.</span></span> <span data-ttu-id="91d31-221">HoloLens 使用此程序，為您的眼球正確設定 IPD。</span><span class="sxs-lookup"><span data-stu-id="91d31-221">HoloLens uses this process to set the IPD correctly for your eyes.</span></span>

![第二個步驟的 IPD 手指對準畫面](./images/ipd-finger-alignment-300px.jpg)

### <span data-ttu-id="91d31-223">手動啟動校正程序</span><span class="sxs-lookup"><span data-stu-id="91d31-223">Manually start the calibration process</span></span>

<span data-ttu-id="91d31-224">如果需要更新校正，或如果新使用者需要調整它，您隨時可以手動執行校正應用程式。</span><span class="sxs-lookup"><span data-stu-id="91d31-224">If you need to update the calibration or if a new user needs to adjust it, you can manually run the Calibration app at any time.</span></span> <span data-ttu-id="91d31-225">預設會安裝校正應用程式。</span><span class="sxs-lookup"><span data-stu-id="91d31-225">The Calibration app is installed by default.</span></span> <span data-ttu-id="91d31-226">您可以使用 **開始** 功能表或 [設定] 應用程式存取它。</span><span class="sxs-lookup"><span data-stu-id="91d31-226">You can access it by using either the **Start** menu or the Settings app.</span></span>

<span data-ttu-id="91d31-227">若要使用 **[開始]** 功能表以執行校正應用程式，請依照下列步驟執行：</span><span class="sxs-lookup"><span data-stu-id="91d31-227">To use the **Start** menu to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="91d31-228">使用[綻開](hololens1-basic-usage.md)手勢開啟 [開始]\*\*\*\* 功能表。</span><span class="sxs-lookup"><span data-stu-id="91d31-228">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="91d31-229">若要檢視所有應用程式，請選取 [**+**]。</span><span class="sxs-lookup"><span data-stu-id="91d31-229">To view all apps, select **+**.</span></span>
1. <span data-ttu-id="91d31-230">選取 [校正]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91d31-230">Select **Calibration**.</span></span>

![從殼層存取校正應用程式](./images/calibration-shell.png)

![校正應用程式啟動後，會顯示為動態立方體](./images/calibration-livecube-200px.png)

<span data-ttu-id="91d31-233">若要使用 [設定] 應用程式來執行校正應用程式，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="91d31-233">To use the Settings app to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="91d31-234">使用[綻開](hololens1-basic-usage.md)手勢開啟 [開始]\*\*\*\* 功能表。</span><span class="sxs-lookup"><span data-stu-id="91d31-234">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="91d31-235">如果 [設定]\*\*\*\* 未釘選至 [開始]\*\*\*\*，請選取 [**+**] 以檢視所有應用程式。</span><span class="sxs-lookup"><span data-stu-id="91d31-235">If **Settings** isn't pinned to **Start**, select **+** to view all apps.</span></span>
1. <span data-ttu-id="91d31-236">選取 [設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91d31-236">Select **Settings**.</span></span>
1. <span data-ttu-id="91d31-237">選取 **[系統]** > **[公用程式]** > **[開啟校正]**。</span><span class="sxs-lookup"><span data-stu-id="91d31-237">Select **System** > **Utilities** > **Open Calibration**.</span></span>

![從 [設定] 應用程式啟動校正應用程式](./images/calibration-settings-500px.jpg)

## <span data-ttu-id="91d31-239">沉浸式頭戴裝置</span><span class="sxs-lookup"><span data-stu-id="91d31-239">Immersive headsets</span></span>

<span data-ttu-id="91d31-240">某些沉浸式頭戴裝置提供自訂 IPD 設定的功能。</span><span class="sxs-lookup"><span data-stu-id="91d31-240">Some immersive headsets provide the ability to customize the IPD setting.</span></span> <span data-ttu-id="91d31-241">若要變更頭戴式裝置的 IPD，請開啟 [設定] 應用程式，然後選取 **[混合實境]** > **[頭戴式裝置顯示器]**，然後移動滑桿控制項。</span><span class="sxs-lookup"><span data-stu-id="91d31-241">To change the IPD for your headset, open the Settings app and select **Mixed reality** > **Headset display**, and then move the slider control.</span></span> <span data-ttu-id="91d31-242">您會在頭戴式裝置中即時看到所做的變更。</span><span class="sxs-lookup"><span data-stu-id="91d31-242">You’ll see the changes in real time in your headset.</span></span> <span data-ttu-id="91d31-243">如果您知道您的 IPD (比如由驗光師提供)，也可以直接輸入。</span><span class="sxs-lookup"><span data-stu-id="91d31-243">If you know your IPD, maybe from a visit to the optometrist, you can enter it directly as well.</span></span>

<span data-ttu-id="91d31-244">您也可以在電腦上選取 **[設定]** > **[混合實境]** > **[頭戴式裝置顯示器]** 以調整此設定。</span><span class="sxs-lookup"><span data-stu-id="91d31-244">You can also adjust this setting on your PC by selecting **Settings** > **Mixed reality** > **Headset display**.</span></span>

<span data-ttu-id="91d31-245">如果您的頭戴式裝置不支援 IPD 自訂，則會停用此設定。</span><span class="sxs-lookup"><span data-stu-id="91d31-245">If your headset doesn't support IPD customization, this setting will be disabled.</span></span>
