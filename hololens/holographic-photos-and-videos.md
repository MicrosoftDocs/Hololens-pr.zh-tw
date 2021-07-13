---
title: 捕捉、記錄和共用混合的現實照片和影片
description: 瞭解如何使用 HoloLens 混合的現實裝置來捕捉、錄製和觀賞現實照片和影片。 瞭解如何透過 Miracast 或收集的檔案共用。
keywords: hololens、相片、影片、捕捉、mrc、混合現實拍攝、相片、攝影機、miracast、串流、即時資料流、示範、記錄
ms.assetid: 1b636ec3-6186-4fbb-81b2-71155aef0593
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 10/28/2019
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: daced6fab65f779b7bd670bf1275f99ae5311d3f
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635954"
---
# <a name="create-mixed-reality-photos-and-videos"></a><span data-ttu-id="28c99-105">建立混合的現實照片和影片</span><span class="sxs-lookup"><span data-stu-id="28c99-105">Create mixed reality photos and videos</span></span>

<span data-ttu-id="28c99-106">HoloLens 為使用者提供了將真實世界與數位世界混合的體驗。</span><span class="sxs-lookup"><span data-stu-id="28c99-106">HoloLens gives users the experience of mixing the real world with the digital world.</span></span>  <span data-ttu-id="28c99-107">Mixed reality capture (MRC) 可讓您以相片或影片形式來捕捉該體驗，或與其他人分享您所看到的內容。</span><span class="sxs-lookup"><span data-stu-id="28c99-107">Mixed reality capture (MRC) lets you capture that experience as a photo or video, or share what you see with others in real-time.</span></span>

<span data-ttu-id="28c99-108">Mixed reality capture 使用第一個人的觀點，讓其他人可以看到您看到的全像投影。</span><span class="sxs-lookup"><span data-stu-id="28c99-108">Mixed reality capture uses a first-person point of view so other people can see holograms as you see them.</span></span> <span data-ttu-id="28c99-109">若為協力廠商的觀點，請使用 [spectator view](/windows/mixed-reality/spectator-view)。</span><span class="sxs-lookup"><span data-stu-id="28c99-109">For a third-person point of view, use [spectator view](/windows/mixed-reality/spectator-view).</span></span> <span data-ttu-id="28c99-110">Spectator view 特別適用于示範。</span><span class="sxs-lookup"><span data-stu-id="28c99-110">Spectator view is especially useful for demos.</span></span>

<span data-ttu-id="28c99-111">雖然在朋友和同事之間分享影片很有趣，但影片也可以協助其他人使用應用程式，或與應用程式和體驗溝通問題。</span><span class="sxs-lookup"><span data-stu-id="28c99-111">While it's fun to share videos amongst friends and colleagues, videos can also help teach other people to use an app or to communicate problems with apps and experiences.</span></span>

> [!NOTE]
> <span data-ttu-id="28c99-112">如果您無法啟動 mixed reality capture 體驗，而您的 HoloLens 是工作裝置，請洽詢您的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="28c99-112">If you can't launch mixed reality capture experiences and your HoloLens is a work device, check with your system administrator.</span></span> <span data-ttu-id="28c99-113">您可以透過公司原則來限制相機的存取。</span><span class="sxs-lookup"><span data-stu-id="28c99-113">Access to the camera can be restricted through company policy.</span></span>

## <a name="capture-a-mixed-reality-photo"></a><span data-ttu-id="28c99-114">捕捉混合現實照片</span><span class="sxs-lookup"><span data-stu-id="28c99-114">Capture a mixed reality photo</span></span>

<span data-ttu-id="28c99-115">有幾種方式可以在 HoloLens 上拍攝混合現實的相片;您可以使用硬體按鈕、語音或 [開始] 功能表。</span><span class="sxs-lookup"><span data-stu-id="28c99-115">There are several ways to take a photo of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <a name="hardware-buttons-to-take-photos"></a><span data-ttu-id="28c99-116">拍攝相片的硬體按鈕</span><span class="sxs-lookup"><span data-stu-id="28c99-116">Hardware buttons to take photos</span></span>

<span data-ttu-id="28c99-117">若要拍攝目前視圖的快速相片，請同步選取音量和音量按鈕。</span><span class="sxs-lookup"><span data-stu-id="28c99-117">To take a quick photo of your current view, press the volume up and volume down buttons at the same time.</span></span>  <span data-ttu-id="28c99-118">這有點類似于螢幕擷取畫面或列印畫面的 HoloLens 版本。</span><span class="sxs-lookup"><span data-stu-id="28c99-118">This is a bit like the HoloLens version of a screenshot or print screen.</span></span>

- [<span data-ttu-id="28c99-119">HoloLens 2 上的按鈕位置</span><span class="sxs-lookup"><span data-stu-id="28c99-119">Button locations on HoloLens 2</span></span>](hololens2-hardware.md)
- [<span data-ttu-id="28c99-120">HoloLens (第1代) 上的按鈕位置</span><span class="sxs-lookup"><span data-stu-id="28c99-120">Button locations on HoloLens (1st gen)</span></span>](hololens1-hardware.md#hololens-components)

> [!NOTE]
> <span data-ttu-id="28c99-121">將 [ **音量增加** ] 和 [ **音量降低** ] 按鈕用於三秒，將會開始錄製影片，而不是拍攝相片。</span><span class="sxs-lookup"><span data-stu-id="28c99-121">Holding the **volume up** and **volume down** buttons for three seconds will start recording a video rather than taking a photo.</span></span> <span data-ttu-id="28c99-122">若要停止錄製，請同時點擊 **音量** 和 **音量** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="28c99-122">To stop recording, tap both **volume up** and **volume down** buttons simultaneously.</span></span>

### <a name="voice-commands-to-take-photos"></a><span data-ttu-id="28c99-123">拍攝相片的聲音命令</span><span class="sxs-lookup"><span data-stu-id="28c99-123">Voice commands to take photos</span></span>

<span data-ttu-id="28c99-124">在 HoloLens 2 上，版本 2004 (和更新版本) ，例如：「拍攝相片」。</span><span class="sxs-lookup"><span data-stu-id="28c99-124">On HoloLens 2, version 2004 (and later), say: "Take a picture."</span></span>

<span data-ttu-id="28c99-125">在 HoloLens (第1代) 或 HoloLens 2 1903 版，例如： "嗨 Cortana，拍照。"</span><span class="sxs-lookup"><span data-stu-id="28c99-125">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, take a picture."</span></span>

### <a name="start-menu-to-take-photos"></a><span data-ttu-id="28c99-126">拍攝相片的 [開始] 功能表</span><span class="sxs-lookup"><span data-stu-id="28c99-126">Start menu to take photos</span></span>

<span data-ttu-id="28c99-127">使用開始手勢移至 [ **開始**]，然後選取 **相機** 圖示。</span><span class="sxs-lookup"><span data-stu-id="28c99-127">Use the Start gesture to go to **Start**, then select the **Camera** icon.</span></span>

<span data-ttu-id="28c99-128">將您的頭部指向您想要捕捉的方向，然後 [按一下](hololens2-basic-usage.md#touch-holograms-near-you) 以拍攝相片。</span><span class="sxs-lookup"><span data-stu-id="28c99-128">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to take a photo.</span></span> <span data-ttu-id="28c99-129">您可以繼續操作並抓住其他相片。</span><span class="sxs-lookup"><span data-stu-id="28c99-129">You can continue to air tap and capture additional photos.</span></span> <span data-ttu-id="28c99-130">您捕捉的任何相片都會儲存到您的裝置。</span><span class="sxs-lookup"><span data-stu-id="28c99-130">Any photos you capture will be saved to your device.</span></span>

<span data-ttu-id="28c99-131">再次使用開始手勢來結束照片捕捉。</span><span class="sxs-lookup"><span data-stu-id="28c99-131">Use the Start gesture again to end photo capture.</span></span>  

## <a name="capture-a-mixed-reality-video"></a><span data-ttu-id="28c99-132">捕捉混合現實影片</span><span class="sxs-lookup"><span data-stu-id="28c99-132">Capture a mixed reality video</span></span>

<span data-ttu-id="28c99-133">有幾種方式可以在 HoloLens 上錄製 mixed reality 的影片;您可以使用硬體按鈕、語音或 [開始] 功能表。</span><span class="sxs-lookup"><span data-stu-id="28c99-133">There are several ways to record a video of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <a name="hardware-buttons-to-record-videos"></a><span data-ttu-id="28c99-134">錄製影片的硬體按鈕</span><span class="sxs-lookup"><span data-stu-id="28c99-134">Hardware buttons to record videos</span></span>

<span data-ttu-id="28c99-135">錄製影片最快的方式是在第三秒倒數計時開始之前，同時按住 **音量** 和 **音量** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="28c99-135">The quickest way to record a video is to press and hold the **volume up** and **volume down** buttons simultaneously until a three-second countdown begins.</span></span> <span data-ttu-id="28c99-136">若要停止錄製，請同時點擊兩個按鈕。</span><span class="sxs-lookup"><span data-stu-id="28c99-136">To stop recording, tap both buttons simultaneously.</span></span>

> [!NOTE]
> <span data-ttu-id="28c99-137">同時快速按下 **音量** 和 **音量** 按鈕將會拍攝相片，而不是錄製影片。</span><span class="sxs-lookup"><span data-stu-id="28c99-137">Quickly pressing the **volume up** and **volume down** buttons at the same time will take a photo rather than recording a video.</span></span>

### <a name="voice-to-record-videos"></a><span data-ttu-id="28c99-138">語音錄影影片</span><span class="sxs-lookup"><span data-stu-id="28c99-138">Voice to record videos</span></span>

<span data-ttu-id="28c99-139">在 HoloLens 2 上，版本 2004 (和更新版本) ，例如：「開始錄製」。</span><span class="sxs-lookup"><span data-stu-id="28c99-139">On HoloLens 2, version 2004 (and later), say: "Start recording."</span></span> <span data-ttu-id="28c99-140">若要停止錄製，請說「停止錄製」。</span><span class="sxs-lookup"><span data-stu-id="28c99-140">To stop recording, say "Stop recording."</span></span>

<span data-ttu-id="28c99-141">在 HoloLens (第1代) 或 HoloLens 2 1903 版，例如：「嗨 Cortana，開始錄製」。</span><span class="sxs-lookup"><span data-stu-id="28c99-141">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, start recording."</span></span> <span data-ttu-id="28c99-142">若要停止錄製，請說「嗨 Cortana，停止錄製」。</span><span class="sxs-lookup"><span data-stu-id="28c99-142">To stop recording, say "Hey Cortana, stop recording."</span></span>

### <a name="start-menu-to-record-videos"></a><span data-ttu-id="28c99-143">記錄影片的 [開始] 功能表</span><span class="sxs-lookup"><span data-stu-id="28c99-143">Start menu to record videos</span></span>

<span data-ttu-id="28c99-144">使用開始手勢移至 [ **開始**]，然後選取 **影片** 圖示。</span><span class="sxs-lookup"><span data-stu-id="28c99-144">Use the Start gesture to go to **Start**, then select the **Video** icon.</span></span> <span data-ttu-id="28c99-145">將您的頭部指向您想要捕捉的方向 [，然後按下 [開始](hololens2-basic-usage.md#touch-holograms-near-you) 錄製]。</span><span class="sxs-lookup"><span data-stu-id="28c99-145">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to start recording.</span></span> <span data-ttu-id="28c99-146">將會有三秒的倒數計時，而您的記錄將會開始。</span><span class="sxs-lookup"><span data-stu-id="28c99-146">There will be a three second countdown and your recording will begin.</span></span>

<span data-ttu-id="28c99-147">若要停止錄製，請使用開始手勢並選取反白顯示的 **影片** 圖示。</span><span class="sxs-lookup"><span data-stu-id="28c99-147">To stop recording, use the Start gesture and select the highlighted **Video** icon.</span></span> <span data-ttu-id="28c99-148">影片將會儲存到您的裝置。</span><span class="sxs-lookup"><span data-stu-id="28c99-148">The video will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="28c99-149">**僅適用于 HoloLens (第1代)**</span><span class="sxs-lookup"><span data-stu-id="28c99-149">**Applies to HoloLens (1st gen) only**</span></span>  
> <span data-ttu-id="28c99-150">[Windows 10 2018 年10月更新](/windows/mixed-reality/release-notes-october-2018)會變更 [開始手勢] 和 [Windows] 按鈕在 HoloLens (第一代) 的行為。</span><span class="sxs-lookup"><span data-stu-id="28c99-150">The [Windows 10 October 2018 Update](/windows/mixed-reality/release-notes-october-2018) changes how the Start gesture and Windows button behave on HoloLens (1st gen).</span></span> <span data-ttu-id="28c99-151">在更新之前，[開始手勢] 或 [Windows] 按鈕會停止錄製錄影。</span><span class="sxs-lookup"><span data-stu-id="28c99-151">Before the update, the Start gesture or Windows button would stop a video recording.</span></span> <span data-ttu-id="28c99-152">但是在更新之後，如果您是在沉浸式應用程式) 中，則 [開始手勢] 或 [Windows] 按鈕會開啟 [**開始**] 功能表 (或 [**快速動作] 功能表**，您可以在其中選取反白顯示的 **影片** 圖示來停止錄製。</span><span class="sxs-lookup"><span data-stu-id="28c99-152">After the update, however, the Start gesture or Windows button opens the **Start** menu (or the **quick actions menu** if you are in an immersive app), from which you can select the highlighted **video** icon to stop recording.</span></span>

## <a name="share-what-you-see-in-real-time"></a><span data-ttu-id="28c99-153">共用您即時看到的內容</span><span class="sxs-lookup"><span data-stu-id="28c99-153">Share what you see in real-time</span></span>

<span data-ttu-id="28c99-154">您可以將您在 HoloLens 中看到的內容即時分享給朋友和同事。</span><span class="sxs-lookup"><span data-stu-id="28c99-154">You can share what you see in HoloLens with friends and colleagues in real-time.</span></span> <span data-ttu-id="28c99-155">有幾種方法可供使用：</span><span class="sxs-lookup"><span data-stu-id="28c99-155">There are a few methods available:</span></span>

1. <span data-ttu-id="28c99-156">連接到已啟用 Miracast 的裝置或介面卡，以在電視上觀賞。</span><span class="sxs-lookup"><span data-stu-id="28c99-156">Connecting to a Miracast-enabled device or adapter to watch on a TV.</span></span>
1. <span data-ttu-id="28c99-157">使用[Windows 裝置入口網站](/windows/mixed-reality/using-the-windows-device-portal)在電腦上觀賞</span><span class="sxs-lookup"><span data-stu-id="28c99-157">Using [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal) to watch on a PC</span></span>
1. <span data-ttu-id="28c99-158">使用[Microsoft HoloLens 附屬應用程式](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)在電腦上觀賞。</span><span class="sxs-lookup"><span data-stu-id="28c99-158">Using the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) to watch on a PC.</span></span>
1. <span data-ttu-id="28c99-159">部署[Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist)應用程式，讓前端工作者能夠將看到的內容串流到遠端專家。</span><span class="sxs-lookup"><span data-stu-id="28c99-159">Deploying the [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) app, which enables front-line workers to stream what they see to a remote expert.</span></span> <span data-ttu-id="28c99-160">然後，遠端專家可以引導 verbally，或在他們的世界中進行批註。</span><span class="sxs-lookup"><span data-stu-id="28c99-160">The remote expert can then guide the front-line worker verbally or by annotating in their world.</span></span>

> [!NOTE]
> <span data-ttu-id="28c99-161">透過 Windows 裝置入口網站或 Microsoft HoloLens 附屬應用程式共用您所看到的內容，必須讓您的 HoloLens 處於[開發人員模式](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="28c99-161">Sharing what you see via Windows Device Portal or Microsoft HoloLens companion app requires your HoloLens to be in [Developer mode](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal).</span></span>

### <a name="stream-video-with-miracast"></a><span data-ttu-id="28c99-162">使用 Miracast 串流影片</span><span class="sxs-lookup"><span data-stu-id="28c99-162">Stream video with Miracast</span></span>

<span data-ttu-id="28c99-163">使用開始手勢移至 [**開始**]，然後選取 **連線** 圖示。</span><span class="sxs-lookup"><span data-stu-id="28c99-163">Use the Start gesture to go to **Start**, then select the **Connect** icon.</span></span> <span data-ttu-id="28c99-164">從顯示的選擇器中，選取您要連線的已啟用 Miracast 裝置或介面卡。</span><span class="sxs-lookup"><span data-stu-id="28c99-164">From the picker that appears, select the Miracast-enabled device or adapter to which you want to connect.</span></span>

<span data-ttu-id="28c99-165">若要停止共用，請使用開始手勢並選取反白顯示的 **連線** 圖示。</span><span class="sxs-lookup"><span data-stu-id="28c99-165">To stop sharing, use the Start gesture and select the highlighted **Connect** icon.</span></span> <span data-ttu-id="28c99-166">因為您已串流處理，所以不會將任何專案儲存到您的裝置。</span><span class="sxs-lookup"><span data-stu-id="28c99-166">Because you were streaming, nothing will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="28c99-167">Miracast 支援已在 HoloLens 從[Windows 10 2018 年10月更新](/windows/mixed-reality/release-notes-october-2018)開始的 (1 代) 上啟用。</span><span class="sxs-lookup"><span data-stu-id="28c99-167">Miracast support was enabled on HoloLens (1st gen) beginning with the [Windows 10 October 2018 Update](/windows/mixed-reality/release-notes-october-2018).</span></span>

### <a name="real-time-video-with-windows-device-portal"></a><span data-ttu-id="28c99-168">使用 Windows 裝置入口網站的即時影片</span><span class="sxs-lookup"><span data-stu-id="28c99-168">Real time video with Windows Device Portal</span></span>

<span data-ttu-id="28c99-169">因為透過 Windows 裝置入口網站的共用需要在 HoloLens 上啟用開發人員模式，請遵循開發人員檔中的指示來[設定開發人員模式並流覽 Windows 裝置入口網站](/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="28c99-169">Because sharing via Windows Device Portal requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode and navigate Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span>

### <a name="microsoft-hololens-companion-app"></a><span data-ttu-id="28c99-170">Microsoft HoloLens 附屬應用程式</span><span class="sxs-lookup"><span data-stu-id="28c99-170">Microsoft HoloLens companion app</span></span>

<span data-ttu-id="28c99-171">因為透過 Microsoft HoloLens 附屬應用程式共用需要在 HoloLens 上啟用開發人員模式，請遵循開發人員檔中的指示來[設定開發人員模式](/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="28c99-171">Because sharing via the Microsoft HoloLens companion app requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode](/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="28c99-172">然後，下載[Microsoft HoloLens 附屬應用程式](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)，並遵循應用程式中的指示，以連接到您的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="28c99-172">Then, download the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) and follow the instructions within the app to connect to your HoloLens.</span></span>

<span data-ttu-id="28c99-173">使用您的 HoloLens 設定應用程式之後，請從應用程式的主功能表中選取 [**即時串流**] 選項。</span><span class="sxs-lookup"><span data-stu-id="28c99-173">Once the app is set up with your HoloLens, select the **Live stream** option from the app's main menu.</span></span>

## <a name="view-your-mixed-reality-photos-and-videos"></a><span data-ttu-id="28c99-174">觀看您的混合現實照片和影片</span><span class="sxs-lookup"><span data-stu-id="28c99-174">View your mixed reality photos and videos</span></span>

<span data-ttu-id="28c99-175">混合現實照片和影片會儲存至裝置的「相機變換」。</span><span class="sxs-lookup"><span data-stu-id="28c99-175">Mixed reality photos and videos are saved to the device's "Camera Roll".</span></span> <span data-ttu-id="28c99-176">您可以使用檔案總管應用程式來流覽 HoloLens 上此資料夾的內容 (流覽至 **> 攝影機滾動**) 的圖片。</span><span class="sxs-lookup"><span data-stu-id="28c99-176">You can browse the contents of this folder on your HoloLens with the File Explorer app (navigate to **Pictures > Camera Roll**).</span></span>

<span data-ttu-id="28c99-177">您也可以在已預先安裝于 HoloLens 上的「相片」應用程式中，查看您的混合現實照片和影片。</span><span class="sxs-lookup"><span data-stu-id="28c99-177">You can also view your mixed reality photos and videos in the Photos app, which is pre-installed on HoloLens.</span></span> <span data-ttu-id="28c99-178">若要釘選您世界中的相片，請在相片應用程式中選取該相片，然後選擇 [ **在混合式環境中放置**]。</span><span class="sxs-lookup"><span data-stu-id="28c99-178">To pin a photo in your world, select it in the Photos app and choose **Place in mixed world**.</span></span> <span data-ttu-id="28c99-179">放在世界各地之後，您就可以在世界各地移動相片。</span><span class="sxs-lookup"><span data-stu-id="28c99-179">You can move the photo around your world after it's been placed.</span></span>

<span data-ttu-id="28c99-180">若要在連接到 HoloLens 的電腦上查看及/或儲存您的混合現實照片和影片，您可以使用[Windows 裝置入口網站](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)或電腦[檔案總管 via MTP](/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="28c99-180">To view and/or save your mixed reality photos and videos on a PC connected to HoloLens, you can use [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) or your [PC's File Explorer via MTP](/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens).</span></span>

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a><span data-ttu-id="28c99-181">使用檔案總管取得圖片、影片和檔案</span><span class="sxs-lookup"><span data-stu-id="28c99-181">Use File Explorer to get your pictures, videos and files</span></span>

<span data-ttu-id="28c99-182">類似于其他行動裝置，請將您的 HoloLens 連接到您的電腦，以顯示檔案總管來存取 HoloLens 程式庫 (相片、影片、檔) 方便傳送。</span><span class="sxs-lookup"><span data-stu-id="28c99-182">Similar to other mobile devices, connect your HoloLens to your PC to bring up File Explorer to access your HoloLens libraries (photos, videos, documents) for easy transfer.</span></span> <span data-ttu-id="28c99-183">這種方法很容易使用，而且不需要使用裝置入口網站或 Wi-fi。</span><span class="sxs-lookup"><span data-stu-id="28c99-183">This method is easy to use and does not require the use of device portal or Wi-Fi.</span></span>

1. <span data-ttu-id="28c99-184">解除鎖定裝置。</span><span class="sxs-lookup"><span data-stu-id="28c99-184">Unlock the device.</span></span>
1. <span data-ttu-id="28c99-185">透過 USB 將裝置連線到電腦上。</span><span class="sxs-lookup"><span data-stu-id="28c99-185">Connect the device to a PC via USB.</span></span>
1. <span data-ttu-id="28c99-186">檔案總管應該會在您的電腦上開啟。</span><span class="sxs-lookup"><span data-stu-id="28c99-186">File Explorer should open on your PC.</span></span>
1. <span data-ttu-id="28c99-187">流覽至：此 PC \\ *yourhololensname*\Internal 儲存體 \Pictures\Camera</span><span class="sxs-lookup"><span data-stu-id="28c99-187">Navigate to: This PC\\*yourhololensname*\Internal Storage\Pictures\Camera Roll</span></span>
1. <span data-ttu-id="28c99-188">將任何需要的檔案複製到您的電腦。</span><span class="sxs-lookup"><span data-stu-id="28c99-188">Copy whatever files you need to your PC.</span></span>

<span data-ttu-id="28c99-189">祕訣：</span><span class="sxs-lookup"><span data-stu-id="28c99-189">Tips:</span></span>
- <span data-ttu-id="28c99-190">如果您沒有看到任何檔案，請確定您已登入 HoloLens，以啟用資料的存取權。</span><span class="sxs-lookup"><span data-stu-id="28c99-190">If you don't see any files, please ensure you sign in to your HoloLens to enable access to your data.</span></span>
- <span data-ttu-id="28c99-191">您可以從 [檔] 資料夾中取得其他資料夾中的其他檔案，例如 [診斷](hololens-diagnostic-logs.md#offline-diagnostics) 檔案。</span><span class="sxs-lookup"><span data-stu-id="28c99-191">You can get other files in other folders, such as [diagnostics files](hololens-diagnostic-logs.md#offline-diagnostics) from the Documents folder.</span></span>
- <span data-ttu-id="28c99-192">從電腦上的檔案總管，您可以選取裝置屬性，以查看 Windows 的全像 OS 版本號碼 (的固件版本) 、裝置序號和電池百分比。</span><span class="sxs-lookup"><span data-stu-id="28c99-192">From File Explorer on your PC, you can select Device properties to see Windows Holographic OS version number (firmware version), device serial number, and battery percentage.</span></span>
- <span data-ttu-id="28c99-193">如果您的組織已使用 MDM 來停用連線 [能力/AllowUSBConnection](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) ，則您將無法連線到您的裝置。</span><span class="sxs-lookup"><span data-stu-id="28c99-193">If your Organization has used MDM to disable [Connectivity/AllowUSBConnection](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) then you will be unable to connect to your device.</span></span>

## <a name="share-your-mixed-reality-photos-and-videos"></a><span data-ttu-id="28c99-194">分享您的混合現實照片和影片</span><span class="sxs-lookup"><span data-stu-id="28c99-194">Share your mixed reality photos and videos</span></span>

<span data-ttu-id="28c99-195">在 Windows 全像[21H1 版](hololens-release-notes.md#windows-holographic-version-21h1)之前，在捕捉到混合現實照片或影片之後，將會顯示預覽。</span><span class="sxs-lookup"><span data-stu-id="28c99-195">Prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), after capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="28c99-196">選取預覽上方的 **共用** 圖示，以顯示共用助理。</span><span class="sxs-lookup"><span data-stu-id="28c99-196">Select the **Share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="28c99-197">從該處，您可以選取您想要與該相片或影片共用的結束點。</span><span class="sxs-lookup"><span data-stu-id="28c99-197">From there, you can select the end point to which you'd like to share that photo or video.</span></span>

<span data-ttu-id="28c99-198">有了 Windows 的全像21H1 版，在捕捉到混合現實照片或影片之後，將會顯示預覽。</span><span class="sxs-lookup"><span data-stu-id="28c99-198">With Windows Holographic, version 21H1, after capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="28c99-199">選取預覽上方的 **共用** 圖示，以顯示共用助理。</span><span class="sxs-lookup"><span data-stu-id="28c99-199">Select the **Share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="28c99-200">從該處，您可以選取要與照片或影片共用的端點 (Mail、OneDrive 等 ) 。</span><span class="sxs-lookup"><span data-stu-id="28c99-200">From there, you can select the end point (Mail, OneDrive, etc.) to which you'd like to share that photo or video.</span></span> <span data-ttu-id="28c99-201">您也可以透過 **設定 > 系統 > 共用體驗**，讓您的 HoloLens 與附近的裝置共用。</span><span class="sxs-lookup"><span data-stu-id="28c99-201">You can also enable your HoloLens to share with nearby devices by going to **Settings -> System -> Shared Experiences**.</span></span> <span data-ttu-id="28c99-202">如需詳細資訊，請參閱[Windows 10 中附近裝置的共用內容](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)。</span><span class="sxs-lookup"><span data-stu-id="28c99-202">For more details, read [Share things with nearby devices in Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).</span></span>

> [!TIP] 
> <span data-ttu-id="28c99-203">您也可以透過自動上傳您的混合現實照片和影片，從 OneDrive 共用混合現實照片和影片。</span><span class="sxs-lookup"><span data-stu-id="28c99-203">You can also share mixed reality photos and videos from OneDrive by automatically uploading your mixed reality photos and videos.</span></span> <span data-ttu-id="28c99-204">開啟 HoloLens 上的 OneDrive 應用程式，並使用 **個人 [Microsoft 帳戶](https://account.microsoft.com)** 登入（如果尚未登入）。</span><span class="sxs-lookup"><span data-stu-id="28c99-204">Open the OneDrive app on HoloLens and sign in with a **personal [Microsoft account](https://account.microsoft.com)**, if you haven't already.</span></span> <span data-ttu-id="28c99-205">選取 **設定** 圖示，然後選擇 [**相機上傳**]。</span><span class="sxs-lookup"><span data-stu-id="28c99-205">Select the **Settings** icon and choose **Camera upload**.</span></span> <span data-ttu-id="28c99-206">開啟相機上傳。</span><span class="sxs-lookup"><span data-stu-id="28c99-206">Turn Camera upload on.</span></span> <span data-ttu-id="28c99-207">您的混合現實照片和影片現在會在您每次於 HoloLens 上啟動應用程式時上傳至 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="28c99-207">Your mixed reality photos and videos will now be uploaded to OneDrive each time you launch the app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="28c99-208">如果您已使用個人 Microsoft 帳戶登入 OneDrive，您只能在 OneDrive 中啟用相機上傳。</span><span class="sxs-lookup"><span data-stu-id="28c99-208">You can only enable camera upload in OneDrive if you’re signed into OneDrive with a personal Microsoft account.</span></span> <span data-ttu-id="28c99-209">如果您使用工作或學校帳戶設定 HoloLens，您可以在 OneDrive 應用程式中新增個人 Microsoft 帳戶，以啟用這項功能。</span><span class="sxs-lookup"><span data-stu-id="28c99-209">If you set up HoloLens with a work or school account, you can add a personal Microsoft account in the OneDrive app to enable this feature.</span></span>

## <a name="limitations-of-mixed-reality-capture"></a><span data-ttu-id="28c99-210">混合現實 capture 的限制</span><span class="sxs-lookup"><span data-stu-id="28c99-210">Limitations of mixed reality capture</span></span>

- <span data-ttu-id="28c99-211">使用混合現實捕捉時，HoloLens 的畫面播放速率將會減半至 30 Hz。</span><span class="sxs-lookup"><span data-stu-id="28c99-211">While using mixed reality capture, the frame rate of HoloLens will be halved to 30 Hz.</span></span>
- <span data-ttu-id="28c99-212">如果相片/攝影機已由另一個應用程式使用中、即時串流，或系統資源不足，可能會減少相片和影片的解析度。</span><span class="sxs-lookup"><span data-stu-id="28c99-212">The resolution of photos and videos may be reduced if the photo/video camera is already in use by another application, while live streaming, or when system resources are low.</span></span>

### <a name="maximum-recording-length"></a><span data-ttu-id="28c99-213">錄製長度上限</span><span class="sxs-lookup"><span data-stu-id="28c99-213">Maximum recording length</span></span>

<span data-ttu-id="28c99-214">在 Windows 全像20H2 版之前 HoloLens 2 裝置上，裝置上錄製的影片受限於五分鐘的最大長度。</span><span class="sxs-lookup"><span data-stu-id="28c99-214">On HoloLens 2 devices before the Windows Holographic, version 20H2, videos recorded on the device were limited to maximum length of five minutes.</span></span>

<span data-ttu-id="28c99-215">由於客戶的意見反應，我們增加了 [混合現實捕捉](holographic-photos-and-videos.md)的錄製長度。</span><span class="sxs-lookup"><span data-stu-id="28c99-215">Due to customer feedback, we’ve increased the recording length of [mixed reality captures](holographic-photos-and-videos.md).</span></span> <span data-ttu-id="28c99-216">依預設，混合現實捕獲將不再受限於5分鐘，但會根據可用的磁碟空間來計算最大錄製長度。</span><span class="sxs-lookup"><span data-stu-id="28c99-216">Mixed reality captures will no longer be limited to 5 minutes by default, but instead will calculate the maximum recording length based on available disk space.</span></span> <span data-ttu-id="28c99-217">裝置會根據可用的磁碟空間（最高達80% 的總磁碟空間）來預估錄影最大持續時間。</span><span class="sxs-lookup"><span data-stu-id="28c99-217">The device will estimate the max video recording duration based on available disk space up to 80% of the total disk space.</span></span>

> [!NOTE]
> <span data-ttu-id="28c99-218">如果發生下列其中一種情況，HoloLens 將會使用預設的影片錄製長度 (5 分鐘) ：</span><span class="sxs-lookup"><span data-stu-id="28c99-218">The HoloLens will use default video recording length (5 minutes) if one of the following occurs:</span></span>
> - <span data-ttu-id="28c99-219">預估的記錄持續時間上限小於預設的5分鐘。</span><span class="sxs-lookup"><span data-stu-id="28c99-219">The estimated max recording duration is smaller than the default 5 mins.</span></span>
> - <span data-ttu-id="28c99-220">可用磁碟空間小於總磁碟空間的20%。</span><span class="sxs-lookup"><span data-stu-id="28c99-220">The available disk space is less than 20% of the total disk space.</span></span>

## <a name="default-file-format-and-resolution"></a><span data-ttu-id="28c99-221">預設檔案格式和解析度</span><span class="sxs-lookup"><span data-stu-id="28c99-221">Default file format and resolution</span></span>

### <a name="default-photo-format-and-resolution"></a><span data-ttu-id="28c99-222">預設相片格式與解析度</span><span class="sxs-lookup"><span data-stu-id="28c99-222">Default photo format and resolution</span></span>

|  <span data-ttu-id="28c99-223">裝置</span><span class="sxs-lookup"><span data-stu-id="28c99-223">Device</span></span>  |  <span data-ttu-id="28c99-224">格式</span><span class="sxs-lookup"><span data-stu-id="28c99-224">Format</span></span>  |  <span data-ttu-id="28c99-225">分機</span><span class="sxs-lookup"><span data-stu-id="28c99-225">Extension</span></span>  |  <span data-ttu-id="28c99-226">解決方案</span><span class="sxs-lookup"><span data-stu-id="28c99-226">Resolution</span></span>  |
|----------|----------|----------|----------|
| <span data-ttu-id="28c99-227">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="28c99-227">HoloLens 2</span></span> | [<span data-ttu-id="28c99-228">JPEG</span><span class="sxs-lookup"><span data-stu-id="28c99-228">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="28c99-229">.jpg</span><span class="sxs-lookup"><span data-stu-id="28c99-229">.jpg</span></span> | <span data-ttu-id="28c99-230">3904x2196px</span><span class="sxs-lookup"><span data-stu-id="28c99-230">3904x2196px</span></span> |
| <span data-ttu-id="28c99-231">HoloLens (第 1 代)</span><span class="sxs-lookup"><span data-stu-id="28c99-231">HoloLens (1st gen)</span></span> | [<span data-ttu-id="28c99-232">JPEG</span><span class="sxs-lookup"><span data-stu-id="28c99-232">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="28c99-233">.jpg</span><span class="sxs-lookup"><span data-stu-id="28c99-233">.jpg</span></span> | <span data-ttu-id="28c99-234">1408x792px</span><span class="sxs-lookup"><span data-stu-id="28c99-234">1408x792px</span></span> |

### <a name="recorded-video-format-and-resolution"></a><span data-ttu-id="28c99-235">錄製的影片格式與解析度</span><span class="sxs-lookup"><span data-stu-id="28c99-235">Recorded video format and resolution</span></span>

| <span data-ttu-id="28c99-236">裝置</span><span class="sxs-lookup"><span data-stu-id="28c99-236">Device</span></span> | <span data-ttu-id="28c99-237">格式</span><span class="sxs-lookup"><span data-stu-id="28c99-237">Format</span></span> | <span data-ttu-id="28c99-238">分機</span><span class="sxs-lookup"><span data-stu-id="28c99-238">Extension</span></span> | <span data-ttu-id="28c99-239">解決方案</span><span class="sxs-lookup"><span data-stu-id="28c99-239">Resolution</span></span> | <span data-ttu-id="28c99-240">速度</span><span class="sxs-lookup"><span data-stu-id="28c99-240">Speed</span></span> | <span data-ttu-id="28c99-241">音訊</span><span class="sxs-lookup"><span data-stu-id="28c99-241">Audio</span></span> |
|----------|----------|----------|----------|----------|----------|
| <span data-ttu-id="28c99-242">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="28c99-242">HoloLens 2</span></span> | [<span data-ttu-id="28c99-243">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="28c99-243">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="28c99-244">.mp4</span><span class="sxs-lookup"><span data-stu-id="28c99-244">.mp4</span></span> | <span data-ttu-id="28c99-245">1920x1080px<br></span><span class="sxs-lookup"><span data-stu-id="28c99-245">1920x1080px</span></span> | <span data-ttu-id="28c99-246">30fps</span><span class="sxs-lookup"><span data-stu-id="28c99-246">30fps</span></span> | <span data-ttu-id="28c99-247">48kHz 身歷聲</span><span class="sxs-lookup"><span data-stu-id="28c99-247">48kHz Stereo</span></span> |
| <span data-ttu-id="28c99-248">HoloLens (第 1 代)</span><span class="sxs-lookup"><span data-stu-id="28c99-248">HoloLens (1st gen)</span></span> |  [<span data-ttu-id="28c99-249">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="28c99-249">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="28c99-250">.mp4</span><span class="sxs-lookup"><span data-stu-id="28c99-250">.mp4</span></span> | <span data-ttu-id="28c99-251">1216x684px</span><span class="sxs-lookup"><span data-stu-id="28c99-251">1216x684px</span></span> | <span data-ttu-id="28c99-252">24fps</span><span class="sxs-lookup"><span data-stu-id="28c99-252">24fps</span></span> | <span data-ttu-id="28c99-253">48kHz 身歷聲</span><span class="sxs-lookup"><span data-stu-id="28c99-253">48kHz Stereo</span></span> |
