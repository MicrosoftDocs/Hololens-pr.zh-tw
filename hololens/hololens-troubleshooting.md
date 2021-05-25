---
title: 疑難排解
description: 隨時掌握最新的 HoloLens 裝置問題和疑難排解技術最常見的解決方案。
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: 問題、錯誤、疑難排解、修正、說明、支援、HoloLens
ms.openlocfilehash: 1039af533b5039eb4eef6599c7cbb480955b0661
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397259"
---
# <a name="troubleshoot-common-issues"></a><span data-ttu-id="dda66-104">針對常見問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="dda66-104">Troubleshoot common issues</span></span>

<span data-ttu-id="dda66-105">本文說明如何解決數個常見的 HoloLens 問題。</span><span class="sxs-lookup"><span data-stu-id="dda66-105">This article describes how to resolve several common HoloLens issues.</span></span>

## <a name="my-hololens-is-unresponsive-or-wont-start"></a><span data-ttu-id="dda66-106">我的 HoloLens 沒有回應或無法啟動</span><span class="sxs-lookup"><span data-stu-id="dda66-106">My HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="dda66-107">如果您的 HoloLens 無法啟動：</span><span class="sxs-lookup"><span data-stu-id="dda66-107">If your HoloLens won't start:</span></span>

- <span data-ttu-id="dda66-108">如果電源按鈕旁的 Led 沒有亮，或只有一個 LED 短暫閃爍，您可能需要向 [HoloLens 收費。](hololens-recovery.md#charge-the-device)</span><span class="sxs-lookup"><span data-stu-id="dda66-108">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens-recovery.md#charge-the-device)</span></span>
- <span data-ttu-id="dda66-109">當您按下電源按鈕時，如果 Led 亮起，但看不到顯示器上的任何畫面，請 [執行裝置的硬重設](hololens-recovery.md#hard-reset-procedure)。</span><span class="sxs-lookup"><span data-stu-id="dda66-109">If the LEDs light up when you press the power button but you can't see anything on the displays, [preform a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="dda66-110">如果您的 HoloLens 變成凍結或沒有回應：</span><span class="sxs-lookup"><span data-stu-id="dda66-110">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="dda66-111">藉由按下電源按鈕，直到所有五個 Led 關閉，或15秒（如果 Led 沒有回應），關閉 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="dda66-111">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="dda66-112">若要開始 HoloLens，請再次按下電源按鈕。</span><span class="sxs-lookup"><span data-stu-id="dda66-112">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="dda66-113">如果這些步驟都沒有作用，您可以嘗試 [復原 HoloLens 2 裝置](hololens-recovery.md) 或 [HoloLens (第一代) 裝置。](hololens1-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="dda66-113">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

## <a name="holograms-dont-look-good"></a><span data-ttu-id="dda66-114">全像全像</span><span class="sxs-lookup"><span data-stu-id="dda66-114">Holograms don't look good</span></span>

<span data-ttu-id="dda66-115">如果您的全像是不穩定、跳動或看起來不穩定，請嘗試：</span><span class="sxs-lookup"><span data-stu-id="dda66-115">If your holograms are unstable, jumpy, or don't look right, try:</span></span>

- <span data-ttu-id="dda66-116">在 HoloLens 之前清除裝置面板和感應器列。</span><span class="sxs-lookup"><span data-stu-id="dda66-116">Cleaning your device visor and sensor bar on the front of your HoloLens.</span></span>
- <span data-ttu-id="dda66-117">增加房間的光線。</span><span class="sxs-lookup"><span data-stu-id="dda66-117">Increasing the light in your room.</span></span>
- <span data-ttu-id="dda66-118">請流覽並查看您的環境，讓 HoloLens 可以更完整地進行掃描。</span><span class="sxs-lookup"><span data-stu-id="dda66-118">Walking around and looking at your surroundings so that HoloLens can scan them more completely.</span></span>
- <span data-ttu-id="dda66-119">為您的眼睛校準 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="dda66-119">Calibrating your HoloLens for your eyes.</span></span> <span data-ttu-id="dda66-120">移至 [**設定**  >  **系統**  >  **公用程式**]。</span><span class="sxs-lookup"><span data-stu-id="dda66-120">Go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="dda66-121">在 [ **校正**] 下，選取 [ **開啟校正**]。</span><span class="sxs-lookup"><span data-stu-id="dda66-121">Under **Calibration**, select **Open Calibration**.</span></span>
 
### <a name="reporting-issues-where-holograms-are-unstable-or-dont-look-right"></a><span data-ttu-id="dda66-122">回報不穩定或看起來不穩定的問題</span><span class="sxs-lookup"><span data-stu-id="dda66-122">Reporting issues where Holograms are unstable or don't look right</span></span>
 
1. <span data-ttu-id="dda66-123">請記錄並混合實境擷取問題的 [影片](holographic-photos-and-videos.md#capture-a-mixed-reality-video) 。</span><span class="sxs-lookup"><span data-stu-id="dda66-123">Please record and a [Mixed Reality Capture video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) of the issue.</span></span> <span data-ttu-id="dda66-124">這段影片稍後可以透過意見反應中樞上傳至附加的檔案。</span><span class="sxs-lookup"><span data-stu-id="dda66-124">This video can be later uploaded through Feedback Hub as an attached file.</span></span>  
1. <span data-ttu-id="dda66-125">透過 [**設定**] 應用程式啟用完整遙測->**隱私權**  ->  **診斷 & 意見** 反應，並在 **選擇性診斷資料** 下，確定切換開關設定為 [**開啟**]</span><span class="sxs-lookup"><span data-stu-id="dda66-125">Enable full telemetry via the **Settings** app -> **Privacy** -> **Diagnostics & feedback** and under **Optional diagnostics data** ensure the toggle is set to **On**</span></span>
1. <span data-ttu-id="dda66-126">藉由更新至最新的 Windows 全像 [作業系統， (20H2 或更高的) ， ](hololens-release-notes.md#windows-holographic-version-20h2)取得最新的全像全像調整和穩定性。</span><span class="sxs-lookup"><span data-stu-id="dda66-126">Get the latest hologram scale and stability fixes by updating to the latest [Windows Holographic OS, (20H2 or higher)](hololens-release-notes.md#windows-holographic-version-20h2).</span></span> <span data-ttu-id="dda66-127">更新之後，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="dda66-127">After updating perform the following:</span></span>
    1. <span data-ttu-id="dda66-128">透過 [**設定**] 應用程式移除所有的全像/>**系統**  ->  **全像**> 然後選取 [**移除所有的全** 像]，然後以全新的地圖開始。</span><span class="sxs-lookup"><span data-stu-id="dda66-128">Remove all Holograms via **Settings** app -> **System** -> **Holograms** -> then select **Remove all holograms** and start with a fresh map.</span></span>
    1. <span data-ttu-id="dda66-129">在您的房間周圍接住 HoloLens，並查看空間中的所有區域和表面，以建立新的空間地圖。</span><span class="sxs-lookup"><span data-stu-id="dda66-129">Create a new map of your space by wearing the HoloLens and walking around your room and looking at all areas and surfaces in the space.</span></span> <span data-ttu-id="dda66-130">請在2-3 分鐘內進行此作業。</span><span class="sxs-lookup"><span data-stu-id="dda66-130">Do this for 2-3 minutes.</span></span>
    1. <span data-ttu-id="dda66-131">執行 IPD 校正。</span><span class="sxs-lookup"><span data-stu-id="dda66-131">Perform IPD calibration.</span></span> <span data-ttu-id="dda66-132">移至 [**設定**  >  **系統**  >  **公用程式**]。</span><span class="sxs-lookup"><span data-stu-id="dda66-132">Go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="dda66-133">在 [ **校正**] 下，選取 [ **開啟校正**]。</span><span class="sxs-lookup"><span data-stu-id="dda66-133">Under **Calibration**, select **Open Calibration**.</span></span>
    1. <span data-ttu-id="dda66-134">重新測試案例，並查看它是否仍持續存在。</span><span class="sxs-lookup"><span data-stu-id="dda66-134">Re-test the scenario and see if it still persists.</span></span>
1. <span data-ttu-id="dda66-135">如果更新無法修正問題，請提出 [意見反應中樞問題](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="dda66-135">If updating does not fix the issue, please file a [Feedback Hub issue](hololens-feedback.md).</span></span> <span data-ttu-id="dda66-136">填寫意見反應之後，您可以使用 [ **共用** ] 按鈕來建立可在聯繫支援時傳送的簡易共用連結。</span><span class="sxs-lookup"><span data-stu-id="dda66-136">After you've filled feedback you can use the **Share** button, to create an easy to share link that can be sent when contacting support.</span></span>

## <a name="hololens-doesnt-respond-to-hand-input"></a><span data-ttu-id="dda66-137">HoloLens 沒有回應手輸入</span><span class="sxs-lookup"><span data-stu-id="dda66-137">HoloLens doesn't respond to hand input</span></span>

<span data-ttu-id="dda66-138">為了確保 HoloLens 可以看到您的手，您需要將它們保留在手勢框架中。</span><span class="sxs-lookup"><span data-stu-id="dda66-138">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="dda66-139">Mixed Reality Home 提供的意見反應可讓您知道何時追蹤您的手。</span><span class="sxs-lookup"><span data-stu-id="dda66-139">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="dda66-140">不同的 HoloLens 版本上的意見反應不同：</span><span class="sxs-lookup"><span data-stu-id="dda66-140">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="dda66-141">在 HoloLens (第1代) 中，注視游標會從點變更為環形</span><span class="sxs-lookup"><span data-stu-id="dda66-141">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="dda66-142">在 HoloLens 2 上，當您的手接近某個平板電腦時，會出現 fingertip 游標，而且當平板不再出現時，會出現一張光線</span><span class="sxs-lookup"><span data-stu-id="dda66-142">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="dda66-143">許多沉浸式應用程式都遵循類似于混合現實首頁的輸入模式。</span><span class="sxs-lookup"><span data-stu-id="dda66-143">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="dda66-144">深入瞭解如何在 [HoloLens (第1代) ](hololens1-basic-usage.md#use-hololens-with-your-hands) 和 [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame)上使用手動輸入。</span><span class="sxs-lookup"><span data-stu-id="dda66-144">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="dda66-145">如果您有佩戴手套，請注意某些類型的手套無法與手動追蹤搭配使用。</span><span class="sxs-lookup"><span data-stu-id="dda66-145">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="dda66-146">常見的範例是黑色橡膠手套，其通常會吸收紅外線燈，且深度相機不會挑選。</span><span class="sxs-lookup"><span data-stu-id="dda66-146">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="dda66-147">如果您的工作牽涉到橡膠手套，建議您嘗試較淺的色彩，例如藍色或灰色。</span><span class="sxs-lookup"><span data-stu-id="dda66-147">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="dda66-148">另一個例子是大型 baggy 手套，這通常會遮蔽您手的形狀。</span><span class="sxs-lookup"><span data-stu-id="dda66-148">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="dda66-149">建議您盡可能使用可作為表單調整的手套以獲得最佳結果。</span><span class="sxs-lookup"><span data-stu-id="dda66-149">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="dda66-150">如果您的面板有指紋或塗抹，請使用 HoloLens 隨附的 microfiber 清潔抹布，以輕輕地清除面板。</span><span class="sxs-lookup"><span data-stu-id="dda66-150">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

## <a name="hololens-doesnt-respond-to-my-voice-commands"></a><span data-ttu-id="dda66-151">HoloLens 未回應我的語音命令</span><span class="sxs-lookup"><span data-stu-id="dda66-151">HoloLens doesn't respond to my voice commands</span></span>

<span data-ttu-id="dda66-152">如果 Cortana 未回應您的語音命令，請確定已開啟 Cortana。</span><span class="sxs-lookup"><span data-stu-id="dda66-152">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="dda66-153">在所有應用程式清單中，選取 [ **Cortana**  >  **功能表**  >  **筆記本**  >  **設定**] 以進行變更。</span><span class="sxs-lookup"><span data-stu-id="dda66-153">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="dda66-154">若要深入瞭解您可以說的內容，請參閱搭配 [HoloLens 使用您的語音](hololens-cortana.md)。</span><span class="sxs-lookup"><span data-stu-id="dda66-154">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

## <a name="i-cant-place-holograms-or-see-holograms-that-i-previously-placed"></a><span data-ttu-id="dda66-155">我無法放入全像投影，或看看我先前放置的全息</span><span class="sxs-lookup"><span data-stu-id="dda66-155">I can't place holograms or see holograms that I previously placed</span></span>

<span data-ttu-id="dda66-156">如果 HoloLens 無法對應或載入您的空間，則會進入有限的模式，而且您將無法放置全像影像或查看您所放置的全像全像。</span><span class="sxs-lookup"><span data-stu-id="dda66-156">If HoloLens can't map or load your space, it enters Limited mode and you won't be able to place holograms or see holograms that you've placed.</span></span> <span data-ttu-id="dda66-157">您可以嘗試以下方法：</span><span class="sxs-lookup"><span data-stu-id="dda66-157">Here are some things to try:</span></span>

- <span data-ttu-id="dda66-158">請確定您的環境中有足夠的光線，讓 HoloLens 可以看到並對應空間。</span><span class="sxs-lookup"><span data-stu-id="dda66-158">Make sure that there's enough light in your environment so HoloLens can see and map the space.</span></span>
- <span data-ttu-id="dda66-159">請確定您已連線到 Wi-Fi 網路。</span><span class="sxs-lookup"><span data-stu-id="dda66-159">Make sure that you're connected to a Wi-Fi network.</span></span> <span data-ttu-id="dda66-160">如果您未連線到 Wi-fi，HoloLens 就無法識別並載入已知的空間。</span><span class="sxs-lookup"><span data-stu-id="dda66-160">If you're not connected to Wi-Fi, HoloLens can't identify and load a known space.</span></span>
- <span data-ttu-id="dda66-161">如果您需要建立新的空間，請連接到 Wi-fi，然後重新開機 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="dda66-161">If you need to create a new space, connect to Wi-Fi, then restart your HoloLens.</span></span>
- <span data-ttu-id="dda66-162">若要查看正確的空間是否為作用中，或要手動載入空格，請移至 [**設定**  >  **系統**  >  **空間**]。</span><span class="sxs-lookup"><span data-stu-id="dda66-162">To see if the correct space is active, or to manually load a space, go to **Settings** > **System** > **Spaces**.</span></span>
- <span data-ttu-id="dda66-163">如果載入正確的空間，但您仍遇到問題，空間可能已損毀。</span><span class="sxs-lookup"><span data-stu-id="dda66-163">If the correct space is loaded and you're still having problems, the space may be corrupt.</span></span> <span data-ttu-id="dda66-164">若要修正此問題，請選取 [空間]，然後選取 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="dda66-164">To fix this issue, select the space, then select **Remove**.</span></span> <span data-ttu-id="dda66-165">移除空間之後，HoloLens 會開始對應您的環境，並建立新的空間。</span><span class="sxs-lookup"><span data-stu-id="dda66-165">After you remove the space, HoloLens starts to map your surroundings and create a new space.</span></span>

## <a name="my-hololens-cant-tell-what-space-im-in"></a><span data-ttu-id="dda66-166">我的 HoloLens 無法分辨我的空間</span><span class="sxs-lookup"><span data-stu-id="dda66-166">My HoloLens can't tell what space I'm in</span></span>

<span data-ttu-id="dda66-167">如果您的 HoloLens 無法識別和載入您所要自動的空間，請檢查下列因素：</span><span class="sxs-lookup"><span data-stu-id="dda66-167">If your HoloLens can't identify and load the space you're in automatically, check the following factors:</span></span>

- <span data-ttu-id="dda66-168">請確定您已連線到 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="dda66-168">Make sure that you're connected to Wi-Fi</span></span>
- <span data-ttu-id="dda66-169">請確定空間中有很多光線</span><span class="sxs-lookup"><span data-stu-id="dda66-169">Make sure that there's plenty of light in the room</span></span>
- <span data-ttu-id="dda66-170">請確定周圍沒有任何重大變更。</span><span class="sxs-lookup"><span data-stu-id="dda66-170">Make sure that there haven't been any major changes to the surroundings.</span></span>

<span data-ttu-id="dda66-171">您也可以手動載入空格，或前往 [**設定**  >  **系統**  >  **空間**] 來管理您的空間。</span><span class="sxs-lookup"><span data-stu-id="dda66-171">You can also load a space manually or manage your spaces by going to **Settings** > **System** > **Spaces**.</span></span>

## <a name="im-getting-a-low-disk-space-error"></a><span data-ttu-id="dda66-172">我收到「磁碟空間不足」錯誤</span><span class="sxs-lookup"><span data-stu-id="dda66-172">I'm getting a "low disk space" error</span></span>

<span data-ttu-id="dda66-173">您必須執行下列一或多個動作，以釋出一些儲存空間：</span><span class="sxs-lookup"><span data-stu-id="dda66-173">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="dda66-174">刪除一些未使用的空間。</span><span class="sxs-lookup"><span data-stu-id="dda66-174">Delete some unused spaces.</span></span> <span data-ttu-id="dda66-175">移至 [**設定**  >  **系統**  >  **空間**]，選取您不再需要的空間，然後選取 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="dda66-175">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="dda66-176">移除您所放置的一些全息。</span><span class="sxs-lookup"><span data-stu-id="dda66-176">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="dda66-177">從相片應用程式刪除部分圖片和影片。</span><span class="sxs-lookup"><span data-stu-id="dda66-177">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="dda66-178">從 HoloLens 卸載一些應用程式。</span><span class="sxs-lookup"><span data-stu-id="dda66-178">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="dda66-179">在 **所有應用程式** 清單中，按住您要卸載的應用程式，然後選取 [ **卸載**]。</span><span class="sxs-lookup"><span data-stu-id="dda66-179">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

## <a name="my-hololens-cant-create-a-new-space"></a><span data-ttu-id="dda66-180">我的 HoloLens 無法建立新的空間</span><span class="sxs-lookup"><span data-stu-id="dda66-180">My HoloLens can't create a new space</span></span>

<span data-ttu-id="dda66-181">最可能的問題是您的儲存空間不足。</span><span class="sxs-lookup"><span data-stu-id="dda66-181">The most likely problem is that you're running low on storage space.</span></span> <span data-ttu-id="dda66-182">請嘗試上述其中一個 [提示](#im-getting-a-low-disk-space-error) 來釋出部分磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="dda66-182">Try one of the [previous tips](#im-getting-a-low-disk-space-error) to free up some disk space.</span></span>

## <a name="the-hololens-emulator-isnt-working"></a><span data-ttu-id="dda66-183">HoloLens 模擬器無法運作</span><span class="sxs-lookup"><span data-stu-id="dda66-183">The HoloLens emulator isn't working</span></span>

<span data-ttu-id="dda66-184">HoloLens 模擬器的相關資訊位於我們的開發人員檔中。</span><span class="sxs-lookup"><span data-stu-id="dda66-184">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="dda66-185">深入瞭解 [HoloLens 模擬器的疑難排解](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)。</span><span class="sxs-lookup"><span data-stu-id="dda66-185">Read more about [troubleshooting the HoloLens emulator](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).</span></span>
