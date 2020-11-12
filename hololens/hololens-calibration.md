---
title: 提高視覺品質和舒適度
description: 校正您的 IPD (瞳距) 可以提高視覺效果的品質。 HoloLens 和 Windows Mixed Reality 沉浸式頭戴裝置都提供自訂 IPD 的方法。
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
keywords: 校正, 舒適度, 視覺效果, 品質, ipd
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f466d64da8ef122ce2917117a74ab904a573b4e3
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163055"
---
# <span data-ttu-id="27a36-105">提高視覺品質和舒適度</span><span class="sxs-lookup"><span data-stu-id="27a36-105">Improve visual quality and comfort</span></span>

<span data-ttu-id="27a36-106">HoloLens 2 和 HoloLens (第 1 代) 在與您獨一無二的眼球校正後，都能運作地更理想。</span><span class="sxs-lookup"><span data-stu-id="27a36-106">HoloLens 2 and HoloLens (1st gen) both work better when they're calibrated to your unique eyes.</span></span>

<span data-ttu-id="27a36-107">這兩個裝置都需要校正以提供最佳的全像投影觀賞體驗，但它們使用不同的校正技術和技巧。</span><span class="sxs-lookup"><span data-stu-id="27a36-107">While both devices need to calibrate for the best hologram viewing experience, they use different calibration technologies and techniques.</span></span>  <span data-ttu-id="27a36-108">請跳至 [HoloLens 2 校正](#calibrating-your-hololens-2)或 [HoloLens (第 1 代) 校正](#calibrating-your-hololens-1st-gen)。</span><span class="sxs-lookup"><span data-stu-id="27a36-108">Jump to [HoloLens 2 calibration](#calibrating-your-hololens-2) or [HoloLens (1st gen) calibration](#calibrating-your-hololens-1st-gen).</span></span>

## <span data-ttu-id="27a36-109">校正 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="27a36-109">Calibrating your HoloLens 2</span></span>

<span data-ttu-id="27a36-110">HoloLens 2 使用眼球追蹤技術來改善您觀看虛擬環境並與其互動的體驗。</span><span class="sxs-lookup"><span data-stu-id="27a36-110">HoloLens 2 uses eye-tracking technology to improve your experience seeing and interacting with the virtual environment.</span></span> <span data-ttu-id="27a36-111">校正 HoloLens 2 可確保它能準確追蹤您的眼球 (以及使用裝置的任何其他人的眼球)。</span><span class="sxs-lookup"><span data-stu-id="27a36-111">Calibrating the HoloLens 2 ensures that it can accurately track your eyes (and the eyes of anyone else who uses the device).</span></span> <span data-ttu-id="27a36-112">這也有助於使用者的舒適度、全像投影對齊，和手部追蹤。</span><span class="sxs-lookup"><span data-stu-id="27a36-112">It also helps with user comfort, hologram alignment, and hand tracking.</span></span> <span data-ttu-id="27a36-113">校正之後，即使面板在您的頭上移動，全像投影仍能正確顯示。</span><span class="sxs-lookup"><span data-stu-id="27a36-113">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

<span data-ttu-id="27a36-114">在下列情況下，HoloLens 2 會提示使用者校正裝置：</span><span class="sxs-lookup"><span data-stu-id="27a36-114">HoloLens 2 prompts a user to calibrate the device under the following circumstances:</span></span>

- <span data-ttu-id="27a36-115">使用者第一次使用裝置</span><span class="sxs-lookup"><span data-stu-id="27a36-115">The user is using the device for the first time</span></span>
- <span data-ttu-id="27a36-116">使用者先前退出校正程序</span><span class="sxs-lookup"><span data-stu-id="27a36-116">The user previously opted out of the calibration process</span></span>
- <span data-ttu-id="27a36-117">上次使用者使用裝置時，無法成功進行校正程序</span><span class="sxs-lookup"><span data-stu-id="27a36-117">The calibration process did not succeed the last time the user used the device</span></span>
- <span data-ttu-id="27a36-118">使用者已刪除其校正設定檔</span><span class="sxs-lookup"><span data-stu-id="27a36-118">The user has deleted their calibration profiles</span></span>
- <span data-ttu-id="27a36-119">裝置被移除並重新放回，而上述任何一種情況均適用</span><span class="sxs-lookup"><span data-stu-id="27a36-119">The device is taken off and put back on and any of the above circumstances apply</span></span> 


![調整眼球的校正提示。](./images/07-et-adjust-for-your-eyes.png)

<span data-ttu-id="27a36-121">在此程序中，您會看到一組目標 (寶石)。</span><span class="sxs-lookup"><span data-stu-id="27a36-121">During this process, you'll look at a set of targets (gems).</span></span> <span data-ttu-id="27a36-122">您在校正期間眨眼是沒關係的，但請盡量專注在寶石上，而非房間中的其他物體。</span><span class="sxs-lookup"><span data-stu-id="27a36-122">It's fine if you blink during calibration, but try to stay focused on the gems instead of other objects in the room.</span></span>  <span data-ttu-id="27a36-123">這可讓 HoloLens 了解您的眼球位置，以呈現您的全像世界。</span><span class="sxs-lookup"><span data-stu-id="27a36-123">This allows HoloLens to learn about your eye position to render your holographic world.</span></span>

![校正提示提示使用者保持頭部靜止，用眼睛跟隨圓點。](./images/07-et-hold-head-still.png)

![帶有寶石示例的校正提示。](./images/08-et-gems.png)

![校正提示調整。](./images/09-et-adjusting.png)

<span data-ttu-id="27a36-127">如果校正成功，您會看到成功畫面。</span><span class="sxs-lookup"><span data-stu-id="27a36-127">If calibration was successful, you'll see a success screen.</span></span>  <span data-ttu-id="27a36-128">如果沒有，請參閱[此處](#troubleshooting-hololens-2-calibration)的診斷校正失敗詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="27a36-128">If not, read more about diagnosing calibration failures [here](#troubleshooting-hololens-2-calibration).</span></span>

![校正提示成功。](./images/10-et-success.png)

### <span data-ttu-id="27a36-130">共用裝置或工作階段時的校正</span><span class="sxs-lookup"><span data-stu-id="27a36-130">Calibration when sharing a device or session</span></span>

<span data-ttu-id="27a36-131">多個使用者可以共用 HoloLens 2 裝置，而不需要每個人都進行裝置設定。</span><span class="sxs-lookup"><span data-stu-id="27a36-131">Multiple users can share a HoloLens 2 device, without a need for each person to go through device setup.</span></span> <span data-ttu-id="27a36-132">當新的使用者第一次將裝置放到頭上時，HoloLens 2 會自動提示使用者校正視覺效果。</span><span class="sxs-lookup"><span data-stu-id="27a36-132">When a new user puts the device on their head for the first time, HoloLens 2 automatically prompts the user to calibrate visuals.</span></span> <span data-ttu-id="27a36-133">當先前已校正視覺效果的使用者將裝置放到頭上時，顯示器會順暢地調整品質並提供舒適的觀賞體驗。</span><span class="sxs-lookup"><span data-stu-id="27a36-133">When a user that has previously calibrated visuals puts the device on their head, the display seamlessly adjusts for quality and a comfortable viewing experience.</span></span>  

### <span data-ttu-id="27a36-134">手動開始校正程序</span><span class="sxs-lookup"><span data-stu-id="27a36-134">Manually starting the calibration process</span></span>

1. <span data-ttu-id="27a36-135">使用 [開始] 手勢開啟 [**[開始]** 功能表](hololens2-basic-usage.md#start-gesture)。</span><span class="sxs-lookup"><span data-stu-id="27a36-135">Use the start gesture to open the [**Start** menu](hololens2-basic-usage.md#start-gesture).</span></span>
1. <span data-ttu-id="27a36-136">如果 [設定] 應用程式未釘選至 [開始]\*\*\*\*，請選取 [所有應用程式]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="27a36-136">If the Settings app isn't pinned to **Start**, select **All Apps**.</span></span>
1. <span data-ttu-id="27a36-137">選取 [設定]\*\*\*\*，然後選取 **[系統]** > **[校正]** > **[眼球校正]** > **[執行眼球校正]**。</span><span class="sxs-lookup"><span data-stu-id="27a36-137">Select **Settings**, and then select **System** > **Calibration** > **Eye Calibration** > **Run eye calibration**.</span></span>

   ![顯示 [執行眼球校正] 選項的 [設定] 應用程式](./images/C-Settings.Calibration.png)

### <span data-ttu-id="27a36-139">自動眼部定位支援</span><span class="sxs-lookup"><span data-stu-id="27a36-139">Auto Eye Position Support</span></span>
- <span data-ttu-id="27a36-140">我們現在可透過自動眼部定位支援，為全像投影定位提供更高的精確度，讓您能更輕鬆地查看，並改善顯示品質。</span><span class="sxs-lookup"><span data-stu-id="27a36-140">We now provide higher accuracy for hologram positioning through Auto Eye Position Support for elevated viewing comfort and improved display quality.</span></span> 

<span data-ttu-id="27a36-141">在 HoloLens 2 中，眼部定位可實現正確的全像投影定位、舒適的觀賞體驗，以及改善顯示品質。</span><span class="sxs-lookup"><span data-stu-id="27a36-141">In HoloLens 2, eye positions enable accurate hologram positioning, comfortable viewing experience and improved display quality.</span></span> <span data-ttu-id="27a36-142">眼部定位會計算為眼睛追蹤結果的一部分。</span><span class="sxs-lookup"><span data-stu-id="27a36-142">Eye positions are computed as part of the eye tracking result.</span></span> <span data-ttu-id="27a36-143">然而，這需要每個使用者透過眼球追蹤校正，即使體驗不需要眼球注視輸入。</span><span class="sxs-lookup"><span data-stu-id="27a36-143">However, this requires each user to go through eye tracking calibration, even when the experience does not require eye gaze input.</span></span>

<span data-ttu-id="27a36-144">**自動眼部定位 (AEP)** 允許這些案例以無互動方式為使用者計算眼睛位置。</span><span class="sxs-lookup"><span data-stu-id="27a36-144">**Auto Eye Position (AEP)** enables these scenarios with an interaction-free way to compute eye positions for the user.</span></span>  <span data-ttu-id="27a36-145">從使用者開啟裝置的那一刻起，自動眼部定位開始在背景自動工作。</span><span class="sxs-lookup"><span data-stu-id="27a36-145">Auto Eye Position starts working in the background automatically from the moment the user puts the device on.</span></span> <span data-ttu-id="27a36-146">如果使用者沒有事先的眼球追蹤校正，[自動眼部定位] 會在較小的處理時間之後，在顯示系統中開始提供使用者的眼部定位。</span><span class="sxs-lookup"><span data-stu-id="27a36-146">If the user does not have a prior eye tracking calibration, Auto Eye position will start providing the user's eye positions to the display system after a small processing time.</span></span> <span data-ttu-id="27a36-147">這個處理時間通常介於 20-60 秒之間。</span><span class="sxs-lookup"><span data-stu-id="27a36-147">This processing time typically is between 20 - 60 seconds.</span></span> <span data-ttu-id="27a36-148">使用者資料不會保留在裝置上，因此如果使用者移除並重新佩戴裝置，或裝置重新開機或從睡眠中喚醒，則會重複此程式。</span><span class="sxs-lookup"><span data-stu-id="27a36-148">The user data is not persisted on the device and hence this process is repeated if the user takes off and puts the device back on or if the device reboots or wakes up from sleep.</span></span>  

<span data-ttu-id="27a36-149">當未經校正的使用者佩戴裝置時，[自動眼部定位] 會有一些系統行為的變更。</span><span class="sxs-lookup"><span data-stu-id="27a36-149">There are a few system behavior changes with Auto Eye Position feature when an uncalibrated user puts on the device.</span></span> <span data-ttu-id="27a36-150">未校正使用者是指之前未在裝置上透過眼球追蹤校正程式的使用者。</span><span class="sxs-lookup"><span data-stu-id="27a36-150">An uncalibrated user refers to someone who has not gone through the eye tracking calibration process on the device previously.</span></span>

|     <span data-ttu-id="27a36-151">作用中應用程式</span><span class="sxs-lookup"><span data-stu-id="27a36-151">Active Application</span></span>                           |     <span data-ttu-id="27a36-152">舊行為</span><span class="sxs-lookup"><span data-stu-id="27a36-152">Old Behavior</span></span>                                   |     <span data-ttu-id="27a36-153">Windows HWindows 全像攝影、版本 20H2 以上版本的行為</span><span class="sxs-lookup"><span data-stu-id="27a36-153">Behavior for Windows HWindows Holographic, version 20H2 onwards</span></span>                                                     |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="27a36-154">啟用無凝視的應用程式或全像攝影殼層</span><span class="sxs-lookup"><span data-stu-id="27a36-154">Non-gaze enabled app or Holographic Shell</span></span>    |     <span data-ttu-id="27a36-155">會顯示眼球追蹤校正提示。</span><span class="sxs-lookup"><span data-stu-id="27a36-155">Eye tracking calibration prompt is displayed.</span></span>    |     <span data-ttu-id="27a36-156">不會顯示任何提示。</span><span class="sxs-lookup"><span data-stu-id="27a36-156">No prompt is displayed.</span></span>                                                                                |
|     <span data-ttu-id="27a36-157">已啟用凝視的應用程式</span><span class="sxs-lookup"><span data-stu-id="27a36-157">Gaze enabled app</span></span>                             |     <span data-ttu-id="27a36-158">會顯示眼球追蹤校正提示。</span><span class="sxs-lookup"><span data-stu-id="27a36-158">Eye tracking calibration prompt is displayed.</span></span>    |     <span data-ttu-id="27a36-159">只會在應用程式存取眼球注視串流時顯示眼球追蹤校正提示。</span><span class="sxs-lookup"><span data-stu-id="27a36-159">Eye tracking calibration prompt is   displayed only when the application accesses eye gaze stream.</span></span>     |

 <span data-ttu-id="27a36-160">如果使用者從尚未啟用注視的應用程式轉換到存取注視資料的應用程式，則會顯示校正提示。</span><span class="sxs-lookup"><span data-stu-id="27a36-160">If the user transitions from a non-gaze enabled application to one that accesses the gaze data, the calibration prompt will be displayed.</span></span> <span data-ttu-id="27a36-161">全新體驗流程不會變更。</span><span class="sxs-lookup"><span data-stu-id="27a36-161">There will be no changed to Out Of Box Experience flow.</span></span> 
 
<span data-ttu-id="27a36-162">對於需要眼球注視資料或非常精確的全像投影定位的體驗，我們建議未校正的使用者透過眼球追蹤校正提示或從 [開始] 選單啟動 [設定] 應用程式，然後選取 **[系統] > [校正] > [眼球校正] > [執行眼球校正]**。</span><span class="sxs-lookup"><span data-stu-id="27a36-162">For experiences that require eye gaze data or very precise hologram positioning, we recommend uncalibrated users to run eye tracking calibration from the eye tracking calibration prompt or by launching the Settings app from the start menu, and then selecting **System > Calibration > Eye Calibration > Run eye calibration**.</span></span>

**<span data-ttu-id="27a36-163">已知問題</span><span class="sxs-lookup"><span data-stu-id="27a36-163">Known issues</span></span>**
 - <span data-ttu-id="27a36-164">我們正在調查眼球追蹤器驅動程式主機處理程序在記憶體負載過重的情况下可能會當機的問題。</span><span class="sxs-lookup"><span data-stu-id="27a36-164">We're investigating an issue where the eye tracker driver host process could crash when running under heavy memory load.</span></span> <span data-ttu-id="27a36-165">眼球追蹤驅動程式主機處理程序應該會自動復原。</span><span class="sxs-lookup"><span data-stu-id="27a36-165">The eye tracking driver host process should auto recover.</span></span>


### <span data-ttu-id="27a36-166">疑難排解 HoloLens 2 校正</span><span class="sxs-lookup"><span data-stu-id="27a36-166">Troubleshooting HoloLens 2 calibration</span></span>

<span data-ttu-id="27a36-167">校正應該適用於大部分人，但在某些情況下，校正會失敗。</span><span class="sxs-lookup"><span data-stu-id="27a36-167">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="27a36-168">校正失敗的一些可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="27a36-168">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="27a36-169">分心而未跟隨校正目標</span><span class="sxs-lookup"><span data-stu-id="27a36-169">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="27a36-170">裝置面板髒汙或有刮痕，或裝置面板的位置不正確</span><span class="sxs-lookup"><span data-stu-id="27a36-170">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="27a36-171">鏡片髒汙或有刮痕</span><span class="sxs-lookup"><span data-stu-id="27a36-171">Dirty or scratched glasses</span></span>
- <span data-ttu-id="27a36-172">特定類型的隱形眼鏡與眼鏡 (有色隱形眼鏡、部分散光隱形眼鏡、防紅外線眼鏡、高處方眼鏡、太陽眼鏡或類似項目)</span><span class="sxs-lookup"><span data-stu-id="27a36-172">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="27a36-173">化妝較濃以及假睫毛</span><span class="sxs-lookup"><span data-stu-id="27a36-173">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="27a36-174">頭髮或眼鏡框較粗，可能阻擋裝置看到您的眼球</span><span class="sxs-lookup"><span data-stu-id="27a36-174">Hair or thick eyeglass frames if they are blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="27a36-175">某些眼部生理構造、眼部疾病或眼科手術，例如細長眼、長睫毛、弱視、眼球震顫、某些 LASIK 雷射手術或其他眼科手術</span><span class="sxs-lookup"><span data-stu-id="27a36-175">Certain eye physiology, eye conditions or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="27a36-176">如果校正失敗，請嘗試：</span><span class="sxs-lookup"><span data-stu-id="27a36-176">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="27a36-177">清潔您的裝置面板</span><span class="sxs-lookup"><span data-stu-id="27a36-177">Cleaning your device visor</span></span>
- <span data-ttu-id="27a36-178">清潔您的眼鏡</span><span class="sxs-lookup"><span data-stu-id="27a36-178">Cleaning your glasses</span></span>
- <span data-ttu-id="27a36-179">盡可能將裝置面板推近您的眼睛</span><span class="sxs-lookup"><span data-stu-id="27a36-179">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="27a36-180">清除面板中的物體 (例如頭髮)</span><span class="sxs-lookup"><span data-stu-id="27a36-180">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="27a36-181">開啟房間中的光源或避免陽光直射</span><span class="sxs-lookup"><span data-stu-id="27a36-181">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="27a36-182">如果您已遵守所有指導方針，且校準仍然失敗，您可以在 [設定] 中停用校準提示。</span><span class="sxs-lookup"><span data-stu-id="27a36-182">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="27a36-183">請在 [意見反應中樞](hololens-feedback.md)中提出您的意見反應，讓我們知道。</span><span class="sxs-lookup"><span data-stu-id="27a36-183">Please also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="27a36-184">也請參閱[影像色彩或亮度疑難排解](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="27a36-184">Please also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="27a36-185">請注意，設定 IPD 不適用於 Hololens 2，因為眼球位置是由系統計算。</span><span class="sxs-lookup"><span data-stu-id="27a36-185">Note that setting IPD is not applicable for Hololens 2, since eye positions are computed by the system.</span></span> 

### <span data-ttu-id="27a36-186">校正資料與安全性</span><span class="sxs-lookup"><span data-stu-id="27a36-186">Calibration data and security</span></span>

<span data-ttu-id="27a36-187">校正資訊是儲存在裝置本機上，不會與任何帳戶資訊相關聯。</span><span class="sxs-lookup"><span data-stu-id="27a36-187">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="27a36-188">不會記錄誰在未校正的情況下使用裝置。</span><span class="sxs-lookup"><span data-stu-id="27a36-188">There is no record of who has used the device without calibration.</span></span> <span data-ttu-id="27a36-189">這表示新的使用者第一次使用裝置時，以及對於先前退出校正或校正失敗的使用者，系統會提示他們校正視覺效果。</span><span class="sxs-lookup"><span data-stu-id="27a36-189">This mean new users will get prompted to calibrate visuals when they use the device for the first time, as well as users who opted out of calibration previously or if calibration was unsuccessful.</span></span>

<span data-ttu-id="27a36-190">此裝置可以在本機儲存多達 50 組校準設定檔。</span><span class="sxs-lookup"><span data-stu-id="27a36-190">The device can locally store up to 50 calibration profiles.</span></span> <span data-ttu-id="27a36-191">在達到此數量之後，裝置會自動將最舊的未使用設定檔刪除。</span><span class="sxs-lookup"><span data-stu-id="27a36-191">After this number is reached, the device automatically deletes the oldest unused profile.</span></span>

<span data-ttu-id="27a36-192">您隨時能從裝置的 **\[設定\]** > **\[隱私權\]** > **\[眼動追蹤儀\]** 中刪除校正資訊。</span><span class="sxs-lookup"><span data-stu-id="27a36-192">Calibration information can always be deleted from the device in **Settings** > **Privacy** > **Eye tracker**.</span></span>  

### <span data-ttu-id="27a36-193">停用校正</span><span class="sxs-lookup"><span data-stu-id="27a36-193">Disable calibration</span></span>

<span data-ttu-id="27a36-194">您也可以遵循下列步驟來停用校正提示：</span><span class="sxs-lookup"><span data-stu-id="27a36-194">You can also disable the calibration prompt by following these steps:</span></span>

1. <span data-ttu-id="27a36-195">選取 **\[設定\]** > **\[系統\]** > **\[校正\]**。</span><span class="sxs-lookup"><span data-stu-id="27a36-195">Select **Settings** > **System** > **Calibration**.</span></span>
1. <span data-ttu-id="27a36-196">關閉 **\[在新人員使用此 HoloLens 時，自動要求執行眼球校正\]**。</span><span class="sxs-lookup"><span data-stu-id="27a36-196">Turn off **When a new person uses this HoloLens, automatically ask to run eye calibration**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="27a36-197">此設定可能會對全像投影轉譯品質和舒適度造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="27a36-197">This setting may adversely affect hologram rendering quality and comfort.</span></span>  <span data-ttu-id="27a36-198">關閉此設定後，依賴眼球追蹤 (例如文字捲動) 的功能就無法在沉浸式應用程式中發揮作用。</span><span class="sxs-lookup"><span data-stu-id="27a36-198">When you turn off this setting, features that depend on eye tracking (such as text scrolling) no longer work in immersive applications.</span></span>

### <span data-ttu-id="27a36-199">HoloLens 2 眼球追蹤技術</span><span class="sxs-lookup"><span data-stu-id="27a36-199">HoloLens 2 eye-tracking technology</span></span>

<span data-ttu-id="27a36-200">裝置會使用其眼球追蹤技術來改善顯示品質，並確保所有全像投影都能正確放置且舒適地在 3D 中觀看。</span><span class="sxs-lookup"><span data-stu-id="27a36-200">The device uses its eye-tracking technology to improve display quality, and to ensure that all holograms are positioned accurately and comfortable to view in 3D.</span></span> <span data-ttu-id="27a36-201">因為它使用眼睛作為地標，所以裝置可以針對每位使用者自行調整，並隨著頭戴式裝置在使用過程中稍微移動而調整其視覺效果。</span><span class="sxs-lookup"><span data-stu-id="27a36-201">Because it uses the eyes as landmarks, the device can adjust itself for every user and tune its visuals as the headset shifts slightly throughout use.</span></span>  <span data-ttu-id="27a36-202">所有調整都會動態發生，不需要手動調整。</span><span class="sxs-lookup"><span data-stu-id="27a36-202">All adjustments happen on the fly without a need for manual tuning.</span></span>
> [!NOTE]
> <span data-ttu-id="27a36-203">設定 IPD 不適用於 Hololens 2，因為眼球位置是由系統計算。</span><span class="sxs-lookup"><span data-stu-id="27a36-203">Setting the IPD is not applicable for Hololens 2, since eye positions are computed by the system.</span></span>

<span data-ttu-id="27a36-204">HoloLens 應用程式使用眼球追蹤來即時追蹤您注視的位置。</span><span class="sxs-lookup"><span data-stu-id="27a36-204">HoloLens applications use eye tracking to track where you are looking in real time.</span></span> <span data-ttu-id="27a36-205">這是開發人員可以利用的主要功能，可讓您在全像體驗中實現全新的環境層級、人類理解及互動。</span><span class="sxs-lookup"><span data-stu-id="27a36-205">This is the main capability developers can leverage to enable a whole new level of context, human understanding and interactions within the Holographic experience.</span></span> <span data-ttu-id="27a36-206">開發人員不需要執行任何動作就能利用這項功能。</span><span class="sxs-lookup"><span data-stu-id="27a36-206">Developers don’t need to do anything to leverage this capability.</span></span>

## <span data-ttu-id="27a36-207">校正 HoloLens (第 1 代)</span><span class="sxs-lookup"><span data-stu-id="27a36-207">Calibrating your HoloLens (1st gen)</span></span>

<span data-ttu-id="27a36-208">HoloLens (第 1 代) 根據您的[瞳距](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD) 調整全像投影顯示。</span><span class="sxs-lookup"><span data-stu-id="27a36-208">HoloLens (1st gen) adjusts hologram display according to the your [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD).</span></span> <span data-ttu-id="27a36-209">如果 IPD 不準確，全像投影可能會不穩定或呈現不正確的距離。</span><span class="sxs-lookup"><span data-stu-id="27a36-209">If the IPD is not accurate, holograms may appear unstable or at an incorrect distance.</span></span> <span data-ttu-id="27a36-210">您可以透過將裝置校正至您的瞳距 (IPD) 來改善視覺效果品質。</span><span class="sxs-lookup"><span data-stu-id="27a36-210">You can improve the quality of your visuals by calibrating the device to your interpupillary distance (IPD).</span></span>

<span data-ttu-id="27a36-211">當您設定 Hololens (第 1 代) 裝置時，系統會在 Cortana 自我介紹之後提示您校正視覺效果。</span><span class="sxs-lookup"><span data-stu-id="27a36-211">When you set up your Hololens (1st gen) device, it prompts to calibrate your visuals after Cortana introduces herself.</span></span> <span data-ttu-id="27a36-212">建議您在此設定階段完成校正步驟。</span><span class="sxs-lookup"><span data-stu-id="27a36-212">It's recommended that you complete the calibration step during this setup phase.</span></span> <span data-ttu-id="27a36-213">不過，您也可以等到 Cortana 提示您的時候說「略過」，來略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="27a36-213">However you can skip it by waiting until Cortana prompts you and then saying "Skip."</span></span>

<span data-ttu-id="27a36-214">在校正程序期間，HoloLens 會要求您在每隻眼睛將手指對準一系列六個目標。</span><span class="sxs-lookup"><span data-stu-id="27a36-214">During the calibration process, HoloLens asks you to align your finger with a series of six targets per eye.</span></span> <span data-ttu-id="27a36-215">HoloLens 使用此程序，為您的眼球正確設定 IPD。</span><span class="sxs-lookup"><span data-stu-id="27a36-215">HoloLens uses this process to set the IPD correctly for your eyes.</span></span>

![第二個步驟的 IPD 手指對準畫面](./images/ipd-finger-alignment-300px.jpg)

### <span data-ttu-id="27a36-217">手動啟動校正程序</span><span class="sxs-lookup"><span data-stu-id="27a36-217">Manually start the calibration process</span></span>

<span data-ttu-id="27a36-218">如果需要更新校正，或如果新使用者需要調整它，您隨時可以手動執行校正應用程式。</span><span class="sxs-lookup"><span data-stu-id="27a36-218">If you need to update the calibration or if a new user needs to adjust it, you can manually run the Calibration app at any time.</span></span> <span data-ttu-id="27a36-219">預設會安裝校正應用程式。</span><span class="sxs-lookup"><span data-stu-id="27a36-219">The Calibration app is installed by default.</span></span> <span data-ttu-id="27a36-220">您可以使用 [開始]\*\*\*\* 功能表或 [設定] 應用程式來存取它。</span><span class="sxs-lookup"><span data-stu-id="27a36-220">You can access it by using eihter the **Start** menu or the Settings app.</span></span>

<span data-ttu-id="27a36-221">若要使用 [開始]\*\*\*\* 功能表來執行校正應用程式，請依照下列步驟執行：</span><span class="sxs-lookup"><span data-stu-id="27a36-221">To use the **Start** menu to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="27a36-222">使用[綻開](hololens1-basic-usage.md)手勢開啟 [開始]\*\*\*\* 功能表。</span><span class="sxs-lookup"><span data-stu-id="27a36-222">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="27a36-223">若要檢視所有應用程式，請選取 [**+**]。</span><span class="sxs-lookup"><span data-stu-id="27a36-223">To view all apps, select **+**.</span></span>
1. <span data-ttu-id="27a36-224">選取 [校正]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="27a36-224">Select **Calibration**.</span></span>

![從殼層存取校正應用程式](./images/calibration-shell.png)

![校正應用程式啟動後，會顯示為動態立方體](./images/calibration-livecube-200px.png)

<span data-ttu-id="27a36-227">若要使用 [設定] 應用程式來執行校正應用程式，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="27a36-227">To use the Settings app to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="27a36-228">使用[綻開](hololens1-basic-usage.md)手勢開啟 [開始]\*\*\*\* 功能表。</span><span class="sxs-lookup"><span data-stu-id="27a36-228">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="27a36-229">如果 [設定]\*\*\*\* 未釘選至 [開始]\*\*\*\*，請選取 [**+**] 以檢視所有應用程式。</span><span class="sxs-lookup"><span data-stu-id="27a36-229">If **Settings** isn't pinned to **Start**, select **+** to view all apps.</span></span>
1. <span data-ttu-id="27a36-230">選取 [設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="27a36-230">Select **Settings**.</span></span>
1. <span data-ttu-id="27a36-231">選取 **[系統]** > **[公用程式]** > **[開啟校正]**。</span><span class="sxs-lookup"><span data-stu-id="27a36-231">Select **System** > **Utilities** > **Open Calibration**.</span></span>

![從 [設定] 應用程式啟動校正應用程式](./images/calibration-settings-500px.jpg)

## <span data-ttu-id="27a36-233">沉浸式頭戴裝置</span><span class="sxs-lookup"><span data-stu-id="27a36-233">Immersive headsets</span></span>

<span data-ttu-id="27a36-234">某些沉浸式頭戴裝置提供自訂 IPD 設定的功能。</span><span class="sxs-lookup"><span data-stu-id="27a36-234">Some immersive headsets provide the ability to customize the IPD setting.</span></span> <span data-ttu-id="27a36-235">若要變更頭戴式裝置的 IPD，請開啟 [設定] 應用程式，然後選取 **[混合實境]** > **[頭戴式裝置顯示器]**，然後移動滑桿控制項。</span><span class="sxs-lookup"><span data-stu-id="27a36-235">To change the IPD for your headset, open the Settings app and select **Mixed reality** > **Headset display**, and then move the slider control.</span></span> <span data-ttu-id="27a36-236">您會在頭戴式裝置中即時看到所做的變更。</span><span class="sxs-lookup"><span data-stu-id="27a36-236">You’ll see the changes in real time in your headset.</span></span> <span data-ttu-id="27a36-237">如果您知道您的 IPD (比如由驗光師提供)，也可以直接輸入。</span><span class="sxs-lookup"><span data-stu-id="27a36-237">If you know your IPD, maybe from a visit to the optometrist, you can enter it directly as well.</span></span>

<span data-ttu-id="27a36-238">您也可以在電腦上選取 **[設定]** > **[混合實境]** > **[頭戴式裝置顯示器]** 來調整此設定。</span><span class="sxs-lookup"><span data-stu-id="27a36-238">You can also adjust this setting on your PC by selecting **Settings** > **Mixed reality** > **Headset display**.</span></span>

<span data-ttu-id="27a36-239">如果您的頭戴式裝置不支援 IPD 自訂，則會停用此設定。</span><span class="sxs-lookup"><span data-stu-id="27a36-239">If your headset does not support IPD customization, this setting will be disabled.</span></span>
