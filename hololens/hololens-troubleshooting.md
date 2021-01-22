---
title: 疑難排解
description: 掌握最新的 HoloLens 裝置問題與疑難排解技巧的常見方案。
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
ms.openlocfilehash: f57aea52337f7ca7e15bda1363f73a3a7265a025
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283044"
---
# <span data-ttu-id="189d2-104">疑難排解</span><span class="sxs-lookup"><span data-stu-id="189d2-104">Troubleshooting</span></span>

<span data-ttu-id="189d2-105">本文說明如何解決幾個常見的 HoloLens 問題。</span><span class="sxs-lookup"><span data-stu-id="189d2-105">This article describes how to resolve several common HoloLens issues.</span></span>

## <span data-ttu-id="189d2-106">我的 HoloLens 沒有回應或無法啟動</span><span class="sxs-lookup"><span data-stu-id="189d2-106">My HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="189d2-107">如果您的 HoloLens 無法啟動：</span><span class="sxs-lookup"><span data-stu-id="189d2-107">If your HoloLens won't start:</span></span>

- <span data-ttu-id="189d2-108">如果電源按鈕旁的指示燈不亮，或只有一個指示燈短暫閃爍，您可能需要為 [HoloLens 充電。](hololens-recovery.md#charge-the-device)</span><span class="sxs-lookup"><span data-stu-id="189d2-108">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens-recovery.md#charge-the-device)</span></span>
- <span data-ttu-id="189d2-109">當您按下電源按鈕時，如果指示燈看不到任何內容，請 [preform 裝置的硬重設](hololens-recovery.md#hard-reset-procedure)。</span><span class="sxs-lookup"><span data-stu-id="189d2-109">If the LEDs light up when you press the power button but you can't see anything on the displays, [preform a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="189d2-110">如果您的 HoloLens 遭到凍結或沒有回應：</span><span class="sxs-lookup"><span data-stu-id="189d2-110">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="189d2-111">您可以按下電源按鈕來關閉您的 HoloLens，直到所有5個指示燈關閉為止，或在指示燈沒有回應的情況下，再按15秒。</span><span class="sxs-lookup"><span data-stu-id="189d2-111">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="189d2-112">若要啟動 HoloLens，請再按一次 [電源] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="189d2-112">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="189d2-113">如果這些步驟無法運作，您可以嘗試 [將 hololens 2 裝置](hololens-recovery.md) 或 [hololens 復原 (1 gen) 裝置。](hololens1-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="189d2-113">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

## <span data-ttu-id="189d2-114">全息影像看起來不好</span><span class="sxs-lookup"><span data-stu-id="189d2-114">Holograms don't look good</span></span>

<span data-ttu-id="189d2-115">如果您的全息影像不穩定、jumpy 或看起來不正確，請嘗試：</span><span class="sxs-lookup"><span data-stu-id="189d2-115">If your holograms are unstable, jumpy, or don't look right, try:</span></span>

- <span data-ttu-id="189d2-116">在您的 HoloLens 前，清理您的裝置面板和感應器列。</span><span class="sxs-lookup"><span data-stu-id="189d2-116">Cleaning your device visor and sensor bar on the front of your HoloLens.</span></span>
- <span data-ttu-id="189d2-117">增加房間中的光線。</span><span class="sxs-lookup"><span data-stu-id="189d2-117">Increasing the light in your room.</span></span>
- <span data-ttu-id="189d2-118">流覽並查看您的周圍，讓 HoloLens 能更完整地進行掃描。</span><span class="sxs-lookup"><span data-stu-id="189d2-118">Walking around and looking at your surroundings so that HoloLens can scan them more completely.</span></span>
- <span data-ttu-id="189d2-119">為您的眼睛校準您的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="189d2-119">Calibrating your HoloLens for your eyes.</span></span> <span data-ttu-id="189d2-120">移至 [**設定**  >  **系統**  >  **工具**]。</span><span class="sxs-lookup"><span data-stu-id="189d2-120">Go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="189d2-121">在 [校正]\*\*\*\* 底下，選取 [開啟校正]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="189d2-121">Under **Calibration**, select **Open Calibration**.</span></span>
 
### <span data-ttu-id="189d2-122">報告全息圖不穩定或看起來不正確的問題</span><span class="sxs-lookup"><span data-stu-id="189d2-122">Reporting issues where Holograms are unstable or don't look right</span></span>
 
1. <span data-ttu-id="189d2-123">請錄製並將問題的 [混合現實捕獲影片](holographic-photos-and-videos.md#capture-a-mixed-reality-video) 中。</span><span class="sxs-lookup"><span data-stu-id="189d2-123">Please record and a [Mixed Reality Capture video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) of the issue.</span></span> <span data-ttu-id="189d2-124">您可以稍後透過意見反應中樞將這個影片上傳成附加的檔案。</span><span class="sxs-lookup"><span data-stu-id="189d2-124">This video can be later uploaded through Feedback Hub as an attached file.</span></span>  
1. <span data-ttu-id="189d2-125">透過 [**設定**] 應用程式啟用完整遙測->**隱私權**  ->  **診斷 & 意見**反應，並在 [**選擇性診斷資料**] 底下，確保已將切換設定為 [**開啟**]</span><span class="sxs-lookup"><span data-stu-id="189d2-125">Enable full telemetry via the **Settings** app -> **Privacy** -> **Diagnostics & feedback** and under **Optional diagnostics data** ensure the toggle is set to **On**</span></span>
1. <span data-ttu-id="189d2-126">更新至最新的 [Windows 全息 OS、 (20H2 或更高版本的) ， ](hololens-release-notes.md#windows-holographic-version-20h2)以取得最新的全息圖縮放與穩定性修正。</span><span class="sxs-lookup"><span data-stu-id="189d2-126">Get the latest hologram scale and stability fixes by updating to the latest [Windows Holographic OS, (20H2 or higher)](hololens-release-notes.md#windows-holographic-version-20h2).</span></span> <span data-ttu-id="189d2-127">更新完成後，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="189d2-127">After updating perform the following:</span></span>
    1. <span data-ttu-id="189d2-128">透過 [**設定**] app 移除所有全息影像->**系統**  ->  **全息影像**-> 然後選取 [**移除所有全息影像**]，然後從新的地圖開始。</span><span class="sxs-lookup"><span data-stu-id="189d2-128">Remove all Holograms via **Settings** app -> **System** -> **Holograms** -> then select **Remove all holograms** and start with a fresh map.</span></span>
    1. <span data-ttu-id="189d2-129">戴上 HoloLens 並流覽房間並查看空間中的所有區域和表面，以建立新的空間地圖。</span><span class="sxs-lookup"><span data-stu-id="189d2-129">Create a new map of your space by wearing the HoloLens and walking around your room and looking at all areas and surfaces in the space.</span></span> <span data-ttu-id="189d2-130">針對2-3 分鐘執行此動作。</span><span class="sxs-lookup"><span data-stu-id="189d2-130">Do this for 2-3 minutes.</span></span>
    1. <span data-ttu-id="189d2-131">執行 IPD 校準。</span><span class="sxs-lookup"><span data-stu-id="189d2-131">Perform IPD calibration.</span></span> <span data-ttu-id="189d2-132">移至 [**設定**  >  **系統**  >  **工具**]。</span><span class="sxs-lookup"><span data-stu-id="189d2-132">Go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="189d2-133">在 [校正]\*\*\*\* 底下，選取 [開啟校正]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="189d2-133">Under **Calibration**, select **Open Calibration**.</span></span>
    1. <span data-ttu-id="189d2-134">重新測試案例，看看它是否仍然存在。</span><span class="sxs-lookup"><span data-stu-id="189d2-134">Re-test the scenario and see if it still persists.</span></span>
1. <span data-ttu-id="189d2-135">如果更新無法修正問題，請歸檔 [意見反應中樞問題](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="189d2-135">If updating does not fix the issue, please file a [Feedback Hub issue](hololens-feedback.md).</span></span> <span data-ttu-id="189d2-136">在您填入意見反應之後，您可以使用 [ **共用** ] 按鈕，建立可在聯絡支援時傳送的輕鬆共用連結。</span><span class="sxs-lookup"><span data-stu-id="189d2-136">After you've filled feedback you can use the **Share** button, to create an easy to share link that can be sent when contacting support.</span></span>

## <span data-ttu-id="189d2-137">HoloLens 沒有回應手動輸入</span><span class="sxs-lookup"><span data-stu-id="189d2-137">HoloLens doesn't respond to hand input</span></span>

<span data-ttu-id="189d2-138">若要確保 HoloLens 能看到您的手，您必須將它們放在手勢框架中。</span><span class="sxs-lookup"><span data-stu-id="189d2-138">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="189d2-139">[混合現實] 家用提供可讓您瞭解手追蹤時間的意見反應。</span><span class="sxs-lookup"><span data-stu-id="189d2-139">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="189d2-140">在不同版本的 HoloLens 上，意見反應會有所不同：</span><span class="sxs-lookup"><span data-stu-id="189d2-140">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="189d2-141">在 HoloLens (1 gen) ，看著游標會從某個點變更為環</span><span class="sxs-lookup"><span data-stu-id="189d2-141">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="189d2-142">在 HoloLens 2 上，當您的手接近平板時，會出現指尖游標，而當 slates 離開時，就會出現手光線</span><span class="sxs-lookup"><span data-stu-id="189d2-142">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="189d2-143">許多沉浸式應用程式都遵循與混合現實家用類似的輸入模式。</span><span class="sxs-lookup"><span data-stu-id="189d2-143">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="189d2-144">深入瞭解在 HoloLens 上使用 [手動輸入] [ (1 gen) ](hololens1-basic-usage.md#use-hololens-with-your-hands) 與 [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame)。</span><span class="sxs-lookup"><span data-stu-id="189d2-144">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="189d2-145">如果您佩戴手套，請注意，某些類型的手套無法搭配手動追蹤。</span><span class="sxs-lookup"><span data-stu-id="189d2-145">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="189d2-146">常見的範例是黑色橡膠手套，通常是用來吸收紅外光源，而不是由深度相機拾取。</span><span class="sxs-lookup"><span data-stu-id="189d2-146">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="189d2-147">如果您的工作涉及橡膠手套，我們建議您嘗試較淺的色彩，例如藍色或灰色。</span><span class="sxs-lookup"><span data-stu-id="189d2-147">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="189d2-148">另一個範例是大型 baggy 手套，通常是遮住您手的圖形。</span><span class="sxs-lookup"><span data-stu-id="189d2-148">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="189d2-149">我們建議您使用以表單管接頭作為最佳結果的手套。</span><span class="sxs-lookup"><span data-stu-id="189d2-149">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="189d2-150">如果您的面板有指紋或塗抹，請使用 HoloLens 隨附的 microfiber 清潔布，以輕輕清除您的面板。</span><span class="sxs-lookup"><span data-stu-id="189d2-150">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

## <span data-ttu-id="189d2-151">HoloLens 沒有回應我的語音命令</span><span class="sxs-lookup"><span data-stu-id="189d2-151">HoloLens doesn't respond to my voice commands</span></span>

<span data-ttu-id="189d2-152">如果 Cortana 沒有回應您的語音命令，請確定 Cortana 已開啟。</span><span class="sxs-lookup"><span data-stu-id="189d2-152">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="189d2-153">在 [所有應用程式] 清單中，選取 [ **Cortana**  >  **功能表**  >  **筆記本**  >  **設定**] 來進行變更。</span><span class="sxs-lookup"><span data-stu-id="189d2-153">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="189d2-154">若要深入了解您可以說什麼，請參閱[使用您的聲音操作 HoloLens](hololens-cortana.md)。</span><span class="sxs-lookup"><span data-stu-id="189d2-154">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

## <span data-ttu-id="189d2-155">我無法放置全息影像，或查看我先前放置的全息影像</span><span class="sxs-lookup"><span data-stu-id="189d2-155">I can't place holograms or see holograms that I previously placed</span></span>

<span data-ttu-id="189d2-156">如果 HoloLens 無法對應或載入您的空間，它會進入 [限制模式]，而且您無法放置全息影像，或查看您所放置的全息影像。</span><span class="sxs-lookup"><span data-stu-id="189d2-156">If HoloLens can't map or load your space, it enters Limited mode and you won't be able to place holograms or see holograms that you've placed.</span></span> <span data-ttu-id="189d2-157">您可以嘗試以下方法：</span><span class="sxs-lookup"><span data-stu-id="189d2-157">Here are some things to try:</span></span>

- <span data-ttu-id="189d2-158">請確定您的環境中有足夠的光線，因此 HoloLens 可以查看並對應空間。</span><span class="sxs-lookup"><span data-stu-id="189d2-158">Make sure that there's enough light in your environment so HoloLens can see and map the space.</span></span>
- <span data-ttu-id="189d2-159">請確認您已連線至 Wi-Fi 網路。</span><span class="sxs-lookup"><span data-stu-id="189d2-159">Make sure that you're connected to a Wi-Fi network.</span></span> <span data-ttu-id="189d2-160">如果您未連線到 Wi-fi，HoloLens 就無法識別並載入已知的空間。</span><span class="sxs-lookup"><span data-stu-id="189d2-160">If you're not connected to Wi-Fi, HoloLens can't identify and load a known space.</span></span>
- <span data-ttu-id="189d2-161">如果您需要建立新的空間，請連線至 Wi-fi，然後重新開機 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="189d2-161">If you need to create a new space, connect to Wi-Fi, then restart your HoloLens.</span></span>
- <span data-ttu-id="189d2-162">若要查看正確的空間是否作用中，或是要手動載入空格，請移至 [**設定**  >  **系統**  >  **空間**]。</span><span class="sxs-lookup"><span data-stu-id="189d2-162">To see if the correct space is active, or to manually load a space, go to **Settings** > **System** > **Spaces**.</span></span>
- <span data-ttu-id="189d2-163">如果載入了正確的空間，但仍有問題，可能是空間已損毀。</span><span class="sxs-lookup"><span data-stu-id="189d2-163">If the correct space is loaded and you're still having problems, the space may be corrupt.</span></span> <span data-ttu-id="189d2-164">若要修正此問題，請選取空格，然後選取 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="189d2-164">To fix this issue, select the space, then select **Remove**.</span></span> <span data-ttu-id="189d2-165">移除空格之後，HoloLens 就會開始對應您的環境，並建立新的空間。</span><span class="sxs-lookup"><span data-stu-id="189d2-165">After you remove the space, HoloLens starts to map your surroundings and create a new space.</span></span>

## <span data-ttu-id="189d2-166">我的 HoloLens 無法判斷我正在進行的空間</span><span class="sxs-lookup"><span data-stu-id="189d2-166">My HoloLens can't tell what space I'm in</span></span>

<span data-ttu-id="189d2-167">如果您的 HoloLens 無法識別並載入您要自動進行的空間，請檢查下列因素：</span><span class="sxs-lookup"><span data-stu-id="189d2-167">If your HoloLens can't identify and load the space you're in automatically, check the following factors:</span></span>

- <span data-ttu-id="189d2-168">請確定您已連線至 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="189d2-168">Make sure that you're connected to Wi-Fi</span></span>
- <span data-ttu-id="189d2-169">確定房間中有足夠的光線</span><span class="sxs-lookup"><span data-stu-id="189d2-169">Make sure that there's plenty of light in the room</span></span>
- <span data-ttu-id="189d2-170">確定周圍沒有任何主要的變更。</span><span class="sxs-lookup"><span data-stu-id="189d2-170">Make sure that there haven't been any major changes to the surroundings.</span></span>

<span data-ttu-id="189d2-171">您也可以移至 [**設定**  >  **系統**  >  **空間**]，手動載入空格或管理您的共用空間。</span><span class="sxs-lookup"><span data-stu-id="189d2-171">You can also load a space manually or manage your spaces by going to **Settings** > **System** > **Spaces**.</span></span>

## <span data-ttu-id="189d2-172">我收到「磁碟空間不足」錯誤</span><span class="sxs-lookup"><span data-stu-id="189d2-172">I'm getting a "low disk space" error</span></span>

<span data-ttu-id="189d2-173">您必須執行下列一或多個動作來釋放一些儲存空間：</span><span class="sxs-lookup"><span data-stu-id="189d2-173">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="189d2-174">刪除部分未使用的空格。</span><span class="sxs-lookup"><span data-stu-id="189d2-174">Delete some unused spaces.</span></span> <span data-ttu-id="189d2-175">移至 [**設定**  >  **系統**  >  **空間**]，選取您不再需要的空間，然後選取 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="189d2-175">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="189d2-176">移除您所放置的一些全息影像。</span><span class="sxs-lookup"><span data-stu-id="189d2-176">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="189d2-177">從 [相片] 應用程式刪除一些圖片和影片。</span><span class="sxs-lookup"><span data-stu-id="189d2-177">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="189d2-178">從您的 HoloLens 解除安裝部分應用程式。</span><span class="sxs-lookup"><span data-stu-id="189d2-178">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="189d2-179">在 [ **所有應用程式** ] 清單中，按住您要卸載的應用程式，然後選取 [ **卸載**]。</span><span class="sxs-lookup"><span data-stu-id="189d2-179">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

## <span data-ttu-id="189d2-180">我的 HoloLens 無法建立新的空間</span><span class="sxs-lookup"><span data-stu-id="189d2-180">My HoloLens can't create a new space</span></span>

<span data-ttu-id="189d2-181">最可能的問題是您的儲存空間不足。</span><span class="sxs-lookup"><span data-stu-id="189d2-181">The most likely problem is that you're running low on storage space.</span></span> <span data-ttu-id="189d2-182">請嘗試上述其中一種 [秘訣](#im-getting-a-low-disk-space-error) ，以釋放一些磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="189d2-182">Try one of the [previous tips](#im-getting-a-low-disk-space-error) to free up some disk space.</span></span>

## <span data-ttu-id="189d2-183">HoloLens 模擬器無法運作</span><span class="sxs-lookup"><span data-stu-id="189d2-183">The HoloLens emulator isn't working</span></span>

<span data-ttu-id="189d2-184">有關 HoloLens 模擬器的資訊位於我們的開發人員檔中。</span><span class="sxs-lookup"><span data-stu-id="189d2-184">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="189d2-185">閱讀更多關於 [HoloLens 模擬器疑難排解的](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)資訊。</span><span class="sxs-lookup"><span data-stu-id="189d2-185">Read more about [troubleshooting the HoloLens emulator](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).</span></span>
