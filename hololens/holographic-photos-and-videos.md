---
title: 捕獲及管理混合現實相片和影片
description: 瞭解如何使用 HoloLens 來捕獲、查看及共用混合現實相片和影片。
keywords: hololens、相片、影片、捕獲、mrc、混合現實捕獲、相片、相機、串流、livestream、示範
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
ms.openlocfilehash: 452164caaad09f2caecf7c4a51cda6242d805d7f
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163116"
---
# <span data-ttu-id="36e15-104">建立混合實境相片和影片</span><span class="sxs-lookup"><span data-stu-id="36e15-104">Create mixed reality photos and videos</span></span>

<span data-ttu-id="36e15-105">HoloLens 讓使用者能夠與數位世界混合現實世界。</span><span class="sxs-lookup"><span data-stu-id="36e15-105">HoloLens gives users the experience of mixing the real world with the digital world.</span></span>  <span data-ttu-id="36e15-106">混合式現實捕獲 (MRC) 可讓您以相片或影片的形式捕獲該體驗，或與其他人即時共用您所看到的內容。</span><span class="sxs-lookup"><span data-stu-id="36e15-106">Mixed reality capture (MRC) lets you capture that experience as a photo or video, or share what you see with others in real-time.</span></span>

<span data-ttu-id="36e15-107">混合式現實捕獲會使用第一個人員的觀點，讓其他人可以在您看到全息影像時看到它們。</span><span class="sxs-lookup"><span data-stu-id="36e15-107">Mixed reality capture uses a first-person point of view so other people can see holograms as you see them.</span></span> <span data-ttu-id="36e15-108">如果是第三人的觀點，請使用 [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view)。</span><span class="sxs-lookup"><span data-stu-id="36e15-108">For a third-person point of view, use [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view).</span></span> <span data-ttu-id="36e15-109">Spectator view 對於示範特別有用。</span><span class="sxs-lookup"><span data-stu-id="36e15-109">Spectator view is especially useful for demos.</span></span>

<span data-ttu-id="36e15-110">您可以在朋友和同事之間共用影片，同時也能協助其他人使用 app 或傳達應用程式和體驗的問題。</span><span class="sxs-lookup"><span data-stu-id="36e15-110">While it's fun to share videos amongst friends and colleagues, videos can also help teach other people to use an app or to communicate problems with apps and experiences.</span></span>

> [!NOTE]
> <span data-ttu-id="36e15-111">如果您無法啟動混合式現實捕獲體驗，且您的 HoloLens 是工作裝置，請諮詢您的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="36e15-111">If you can't launch mixed reality capture experiences and your HoloLens is a work device, check with your system administrator.</span></span> <span data-ttu-id="36e15-112">您可以透過公司原則限制對相機的存取權。</span><span class="sxs-lookup"><span data-stu-id="36e15-112">Access to the camera can be restricted through company policy.</span></span>

## <span data-ttu-id="36e15-113">捕獲混合式現實相片</span><span class="sxs-lookup"><span data-stu-id="36e15-113">Capture a mixed reality photo</span></span>

<span data-ttu-id="36e15-114">有幾種方法可以在 HoloLens 上拍攝混合現實相片;您可以使用硬體按鈕、語音或 [開始] 功能表。</span><span class="sxs-lookup"><span data-stu-id="36e15-114">There are several ways to take a photo of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <span data-ttu-id="36e15-115">[拍攝相片] 的硬體按鈕</span><span class="sxs-lookup"><span data-stu-id="36e15-115">Hardware buttons to take photos</span></span>

<span data-ttu-id="36e15-116">若要拍攝目前視圖的快速相片，請同步選取 [音量] 和 [音量] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="36e15-116">To take a quick photo of your current view, press the volume up and volume down buttons at the same time.</span></span>  <span data-ttu-id="36e15-117">這有點像是 HoloLens 版本的螢幕擷取畫面或列印畫面。</span><span class="sxs-lookup"><span data-stu-id="36e15-117">This is a bit like the HoloLens version of a screenshot or print screen.</span></span>

- [<span data-ttu-id="36e15-118">HoloLens 2 上的按鈕位置</span><span class="sxs-lookup"><span data-stu-id="36e15-118">Button locations on HoloLens 2</span></span>](hololens2-hardware.md)
- [<span data-ttu-id="36e15-119">HoloLens (第一代) 上的按鈕位置</span><span class="sxs-lookup"><span data-stu-id="36e15-119">Button locations on HoloLens (1st gen)</span></span>](hololens1-hardware.md#hololens-components)

> [!NOTE]
> <span data-ttu-id="36e15-120">按住 [ **音量** ] 和 [ **音量** ] 按鈕三秒，就可以開始錄製影片，而不是拍攝相片。</span><span class="sxs-lookup"><span data-stu-id="36e15-120">Holding the **volume up** and **volume down** buttons for three seconds will start recording a video rather than taking a photo.</span></span> <span data-ttu-id="36e15-121">若要停止錄製，請同步選取 [ **音量** ] 和 [調 **低音量** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="36e15-121">To stop recording, tap both **volume up** and **volume down** buttons simultaneously.</span></span>

### <span data-ttu-id="36e15-122">[拍攝相片] 的語音命令</span><span class="sxs-lookup"><span data-stu-id="36e15-122">Voice commands to take photos</span></span>

<span data-ttu-id="36e15-123">在 HoloLens 2、版本 2004 (及更新版本) ，請說：「拍攝圖片」。</span><span class="sxs-lookup"><span data-stu-id="36e15-123">On HoloLens 2, version 2004 (and later), say: "Take a picture."</span></span>

<span data-ttu-id="36e15-124">在 HoloLens (1 gen) 或 HoloLens 2，版本1903，請說：「你好小娜，請拍攝圖片」。</span><span class="sxs-lookup"><span data-stu-id="36e15-124">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, take a picture."</span></span>

### <span data-ttu-id="36e15-125">[開始] 功能表拍攝相片</span><span class="sxs-lookup"><span data-stu-id="36e15-125">Start menu to take photos</span></span>

<span data-ttu-id="36e15-126">使用 [開始] 手勢移至 [ **開始**]，然後選取 **相機** 圖示。</span><span class="sxs-lookup"><span data-stu-id="36e15-126">Use the Start gesture to go to **Start**, then select the **camera** icon.</span></span>

<span data-ttu-id="36e15-127">將您的頭指向您想要捕獲的方向，然後 [按一下 [air](hololens2-basic-usage.md#touch-holograms-near-you) ] 拍攝相片。</span><span class="sxs-lookup"><span data-stu-id="36e15-127">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to take a photo.</span></span> <span data-ttu-id="36e15-128">您可以繼續空中輕觸並捕獲其他相片。</span><span class="sxs-lookup"><span data-stu-id="36e15-128">You can continue to air tap and capture additional photos.</span></span> <span data-ttu-id="36e15-129">您捕獲的任何相片都會儲存至您的裝置。</span><span class="sxs-lookup"><span data-stu-id="36e15-129">Any photos you capture will be saved to your device.</span></span>

<span data-ttu-id="36e15-130">再次使用 [開始] 手勢來結束相片捕獲。</span><span class="sxs-lookup"><span data-stu-id="36e15-130">Use the Start gesture again to end photo capture.</span></span>  

## <span data-ttu-id="36e15-131">捕獲混合式現實影片</span><span class="sxs-lookup"><span data-stu-id="36e15-131">Capture a mixed reality video</span></span>

<span data-ttu-id="36e15-132">有幾種方法可以在 HoloLens 上錄製混合現實的影片;您可以使用硬體按鈕、語音或 [開始] 功能表。</span><span class="sxs-lookup"><span data-stu-id="36e15-132">There are several ways to record a video of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <span data-ttu-id="36e15-133">錄製影片的硬體按鈕</span><span class="sxs-lookup"><span data-stu-id="36e15-133">Hardware buttons to record videos</span></span>

<span data-ttu-id="36e15-134">錄製影片最快速的方式，就是在三秒倒計時開始前，同時按住 [ **音量** ] 和 [ **音量** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="36e15-134">The quickest way to record a video is to press and hold the **volume up** and **volume down** buttons simultaneously until a three-second countdown begins.</span></span> <span data-ttu-id="36e15-135">若要停止錄製，請同時輕觸兩個按鈕。</span><span class="sxs-lookup"><span data-stu-id="36e15-135">To stop recording, tap both buttons simultaneously.</span></span>

> [!NOTE]
> <span data-ttu-id="36e15-136">您可以同時快速地同步選取 [ **音量** ] 和 [ **音量** ] 按鈕，而不需要錄製影片。</span><span class="sxs-lookup"><span data-stu-id="36e15-136">Quickly pressing the **volume up** and **volume down** buttons at the same time will take a photo rather than recording a video.</span></span>

### <span data-ttu-id="36e15-137">錄製影片的語音</span><span class="sxs-lookup"><span data-stu-id="36e15-137">Voice to record videos</span></span>

<span data-ttu-id="36e15-138">在 HoloLens 2、版本 2004 (及更新版本) ，請說：「開始錄製」。</span><span class="sxs-lookup"><span data-stu-id="36e15-138">On HoloLens 2, version 2004 (and later), say: "Start recording."</span></span> <span data-ttu-id="36e15-139">若要停止錄製，請說「停止錄製」。</span><span class="sxs-lookup"><span data-stu-id="36e15-139">To stop recording, say "Stop recording."</span></span>

<span data-ttu-id="36e15-140">在 HoloLens (1 gen) 或 HoloLens 2，版本1903，請說：「你好小娜，請開始錄製」。</span><span class="sxs-lookup"><span data-stu-id="36e15-140">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, start recording."</span></span> <span data-ttu-id="36e15-141">若要停止錄製，請說「你好小娜，停止錄製」。</span><span class="sxs-lookup"><span data-stu-id="36e15-141">To stop recording, say "Hey Cortana, stop recording."</span></span>

### <span data-ttu-id="36e15-142">[開始] 功能表以錄製影片</span><span class="sxs-lookup"><span data-stu-id="36e15-142">Start menu to record videos</span></span>

<span data-ttu-id="36e15-143">使用 [開始] 手勢移至 [ **開始**]，然後選取 [ **影片** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="36e15-143">Use the Start gesture to go to **Start**, then select the **video** icon.</span></span> <span data-ttu-id="36e15-144">將您的頭指向您想要捕獲的方向，然後 [按一下 [air](hololens2-basic-usage.md#touch-holograms-near-you) ] （開始錄製）。</span><span class="sxs-lookup"><span data-stu-id="36e15-144">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to start recording.</span></span> <span data-ttu-id="36e15-145">會有三秒的倒計時，您的錄製將會開始。</span><span class="sxs-lookup"><span data-stu-id="36e15-145">There will be a three second countdown and your recording will begin.</span></span>

<span data-ttu-id="36e15-146">若要停止錄製，請使用 [開始] 手勢，然後選取 [醒目提示的 **影片** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="36e15-146">To stop recording, use the Start gesture and select the highlighted **video** icon.</span></span> <span data-ttu-id="36e15-147">影片將會儲存至您的裝置。</span><span class="sxs-lookup"><span data-stu-id="36e15-147">The video will be saved to your device.</span></span>

> [!NOTE]
> **<span data-ttu-id="36e15-148">僅適用于 HoloLens (1 gen) </span><span class="sxs-lookup"><span data-stu-id="36e15-148">Applies to HoloLens (1st gen) only</span></span>**  
> <span data-ttu-id="36e15-149">[Windows 10 年 10 2018 月更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)會變更 [開始手勢] 和 [windows] 按鈕在 HoloLens (第一代) 上的行為方式。</span><span class="sxs-lookup"><span data-stu-id="36e15-149">The [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) changes how the Start gesture and Windows button behave on HoloLens (1st gen).</span></span> <span data-ttu-id="36e15-150">更新前，[開始手勢] 或 [Windows] 按鈕會停止視頻錄製。</span><span class="sxs-lookup"><span data-stu-id="36e15-150">Before the update, the Start gesture or Windows button would stop a video recording.</span></span> <span data-ttu-id="36e15-151">在更新之後，如果您使用的是沉浸式應用程式) ，[開始] 手勢或 Windows 按鈕會開啟 [ **開始** ] 功能表 (或 [ **快速動作] 功能表** ，您可以在其中選取醒目提示的 **影片** 圖示以停止錄製。</span><span class="sxs-lookup"><span data-stu-id="36e15-151">After the update, however, the Start gesture or Windows button opens the **Start** menu (or the **quick actions menu** if you are in an immersive app), from which you can select the highlighted **video** icon to stop recording.</span></span>

## <span data-ttu-id="36e15-152">共用您即時看到的內容</span><span class="sxs-lookup"><span data-stu-id="36e15-152">Share what you see in real-time</span></span>

<span data-ttu-id="36e15-153">您可以在 HoloLens 中即時與您的朋友和同事共用您所看到的內容。</span><span class="sxs-lookup"><span data-stu-id="36e15-153">You can share what you see in HoloLens with friends and colleagues in real-time.</span></span> <span data-ttu-id="36e15-154">有幾種方法可供使用：</span><span class="sxs-lookup"><span data-stu-id="36e15-154">There are a few methods available:</span></span>

1. <span data-ttu-id="36e15-155">連線至支援 Miracast 的裝置或配接器，以在電視上觀看。</span><span class="sxs-lookup"><span data-stu-id="36e15-155">Connecting to a Miracast-enabled device or adapter to watch on a TV.</span></span>
1. <span data-ttu-id="36e15-156">使用 [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 在電腦上觀看</span><span class="sxs-lookup"><span data-stu-id="36e15-156">Using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to watch on a PC</span></span>
1. <span data-ttu-id="36e15-157">使用 [Microsoft HoloLens 隨附應用程式](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 在電腦上觀看。</span><span class="sxs-lookup"><span data-stu-id="36e15-157">Using the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) to watch on a PC.</span></span>
1. <span data-ttu-id="36e15-158">部署 [Microsoft Dynamics 365 遠端協助](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) 應用程式，這可讓前線工作者流式處理他們對遠端專家所看到的內容。</span><span class="sxs-lookup"><span data-stu-id="36e15-158">Deploying the [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) app, which enables front-line workers to stream what they see to a remote expert.</span></span> <span data-ttu-id="36e15-159">然後，遠端專家就可以在他們的世界中引導前一行的工作人員 verbally 或進行標注。</span><span class="sxs-lookup"><span data-stu-id="36e15-159">The remote expert can then guide the front-line worker verbally or by annotating in their world.</span></span>

> [!NOTE]
> <span data-ttu-id="36e15-160">透過 Windows Device Portal 或 Microsoft HoloLens 隨附應用程式共用所看到的內容，需要您的 HoloLens 才能處於 [開發人員模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="36e15-160">Sharing what you see via Windows Device Portal or Microsoft HoloLens companion app requires your HoloLens to be in [Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal).</span></span>

### <span data-ttu-id="36e15-161">使用 Miracast 進行串流影片</span><span class="sxs-lookup"><span data-stu-id="36e15-161">Stream video with Miracast</span></span>

<span data-ttu-id="36e15-162">使用 [開始] 手勢移至 [ **開始**]，然後選取 [ **連接]** 圖示。</span><span class="sxs-lookup"><span data-stu-id="36e15-162">Use the Start gesture to go to **Start**, then select the **connect** icon.</span></span> <span data-ttu-id="36e15-163">從顯示的選擇器中，選取您要連接的已啟用 Miracast 的裝置或配接器。</span><span class="sxs-lookup"><span data-stu-id="36e15-163">From the picker that appears, select the Miracast-enabled device or adapter to which you want to connect.</span></span>

<span data-ttu-id="36e15-164">若要停止共用，請使用 [開始] 手勢，然後選取 [醒目提示的連線 **]** 圖示。</span><span class="sxs-lookup"><span data-stu-id="36e15-164">To stop sharing, use the Start gesture and select the highlighted **connect** icon.</span></span> <span data-ttu-id="36e15-165">因為您正在進行流式處理，所以不會將任何內容儲存至您的裝置。</span><span class="sxs-lookup"><span data-stu-id="36e15-165">Because you were streaming, nothing will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="36e15-166">從 [Windows 10 年10月2018更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)開始，在 HoloLens (1 gen) 上已啟用 Miracast 支援。</span><span class="sxs-lookup"><span data-stu-id="36e15-166">Miracast support was enabled on HoloLens (1st gen) beginning with the [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018).</span></span>

### <span data-ttu-id="36e15-167">Windows Device Portal 的即時影片</span><span class="sxs-lookup"><span data-stu-id="36e15-167">Real time video with Windows Device Portal</span></span>

<span data-ttu-id="36e15-168">因為透過 Windows 裝置入口網站共用需要在 HoloLens 上啟用開發人員模式，請依照開發人員檔中的指示進行，以 [設定開發人員模式並流覽 Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="36e15-168">Because sharing via Windows Device Portal requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode and navigate Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

### <span data-ttu-id="36e15-169">Microsoft HoloLens 隨附應用程式</span><span class="sxs-lookup"><span data-stu-id="36e15-169">Microsoft HoloLens companion app</span></span>

<span data-ttu-id="36e15-170">因為透過 Microsoft HoloLens 隨附 app 進行共用需要在 HoloLens 上啟用開發人員模式，請依照開發人員檔中的指示來 [設定開發人員模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="36e15-170">Because sharing via the Microsoft HoloLens companion app requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="36e15-171">然後，下載 [Microsoft HoloLens 隨附應用程式](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) ，並依照 app 內的指示連線至您的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="36e15-171">Then, download the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) and follow the instructions within the app to connect to your HoloLens.</span></span>

<span data-ttu-id="36e15-172">使用您的 HoloLens 設定應用程式後，請從應用程式的主功能表選取 [ **即時資料流** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="36e15-172">Once the app is set up with your HoloLens, select the **Live stream** option from the app's main menu.</span></span>

## <span data-ttu-id="36e15-173">查看您的混合現實相片和影片</span><span class="sxs-lookup"><span data-stu-id="36e15-173">View your mixed reality photos and videos</span></span>

<span data-ttu-id="36e15-174">混合現實相片和影片會儲存到裝置的「相機捲筒」。</span><span class="sxs-lookup"><span data-stu-id="36e15-174">Mixed reality photos and videos are saved to the device's "Camera Roll".</span></span> <span data-ttu-id="36e15-175">您可以在您的 HoloLens 上使用 [檔案資源管理器] app 來流覽此資料夾的內容， (流覽至 [相機投影) ] > [圖片]。</span><span class="sxs-lookup"><span data-stu-id="36e15-175">You can browse the contents of this folder on your HoloLens with the File Explorer app (navigate to Pictures > Camera Roll).</span></span>

<span data-ttu-id="36e15-176">您也可以在已預先安裝在 HoloLens 上的相片 app 中，查看您的混合現實相片和影片。</span><span class="sxs-lookup"><span data-stu-id="36e15-176">You can also view your mixed reality photos and videos in the Photos app, which is pre-installed on HoloLens.</span></span> <span data-ttu-id="36e15-177">若要固定您世界上的相片，請在 [相片] 應用程式中選取，然後選擇 [ **混合世界**] 中的 [位置]。</span><span class="sxs-lookup"><span data-stu-id="36e15-177">To pin a photo in your world, select it in the Photos app and choose **Place in mixed world**.</span></span> <span data-ttu-id="36e15-178">您可以在放置之後，在您的世界周圍移動相片。</span><span class="sxs-lookup"><span data-stu-id="36e15-178">You can move the photo around your world after it's been placed.</span></span>

<span data-ttu-id="36e15-179">若要在連線至 HoloLens 的電腦上查看和/或儲存您的混合現實相片和影片，您可以透過 MTP 使用 [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) 或 [電腦的檔案資源管理器](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="36e15-179">To view and/or save your mixed reality photos and videos on a PC connected to HoloLens, you can use [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) or your [PC's File Explorer via MTP](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens).</span></span>

### <span data-ttu-id="36e15-180">使用檔案資源管理器來取得您的圖片、影片和檔案</span><span class="sxs-lookup"><span data-stu-id="36e15-180">Use File Explorer to get your pictures, videos and files</span></span>

<span data-ttu-id="36e15-181">與其他行動裝置類似，將您的 HoloLens 連接至您的電腦，以調高檔案資源管理器，以存取您的 HoloLens 文件庫 (相片、影片、檔) 輕鬆傳送。</span><span class="sxs-lookup"><span data-stu-id="36e15-181">Similar to other mobile devices, connect your HoloLens to your PC to bring up File Explorer to access your HoloLens libraries (photos, videos, documents) for easy transfer.</span></span> <span data-ttu-id="36e15-182">這個方法很容易使用，而且不需要使用 device portal 或 Wi-fi。</span><span class="sxs-lookup"><span data-stu-id="36e15-182">This method is easy to use and does not require the use of device portal or Wi-Fi.</span></span>

1. <span data-ttu-id="36e15-183">解除鎖定裝置。</span><span class="sxs-lookup"><span data-stu-id="36e15-183">Unlock the device.</span></span>
1. <span data-ttu-id="36e15-184">透過 USB 將裝置連線到電腦。</span><span class="sxs-lookup"><span data-stu-id="36e15-184">Connect the device to a PC via USB.</span></span>
1. <span data-ttu-id="36e15-185">檔案瀏覽器應該在您的電腦上開啟。</span><span class="sxs-lookup"><span data-stu-id="36e15-185">File Explorer should open on your PC.</span></span>
1. <span data-ttu-id="36e15-186">流覽至：此 PC\\*yourhololensname*\Internal Storage\Pictures\Camera 捲筒</span><span class="sxs-lookup"><span data-stu-id="36e15-186">Navigate to: This PC\\*yourhololensname*\Internal Storage\Pictures\Camera Roll</span></span>
1. <span data-ttu-id="36e15-187">將任何您需要的檔案複製到電腦上。</span><span class="sxs-lookup"><span data-stu-id="36e15-187">Copy whatever files you need to your PC.</span></span>

<span data-ttu-id="36e15-188">秘訣：</span><span class="sxs-lookup"><span data-stu-id="36e15-188">Tips:</span></span>
- <span data-ttu-id="36e15-189">如果您沒有看到任何檔案，請確認您已登入您的 HoloLens，以啟用資料存取權。</span><span class="sxs-lookup"><span data-stu-id="36e15-189">If you don't see any files, please ensure you sign in to your HoloLens to enable access to your data.</span></span>
- <span data-ttu-id="36e15-190">您可以在其他資料夾中取得其他檔案，例如 [檔] 資料夾中的 [ [診斷](hololens-diagnostic-logs.md#offline-diagnostics) 檔案]。</span><span class="sxs-lookup"><span data-stu-id="36e15-190">You can get other files in other folders, such as [diagnostics files](hololens-diagnostic-logs.md#offline-diagnostics) from the Documents folder.</span></span>
- <span data-ttu-id="36e15-191">從您電腦上的檔案資源管理器，您可以選取 [裝置屬性]，以查看 Windows 全息 OS 版本號碼 (固件版本) 與裝置序列值及電池百分比。</span><span class="sxs-lookup"><span data-stu-id="36e15-191">From File Explorer on your PC, you can select Device properties to see Windows Holographic OS version number (firmware version) and device serial number and battery percentage.</span></span>
- <span data-ttu-id="36e15-192">如果您的組織已使用 MDM 停用 [連接/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) ，則您將無法連線到您的裝置。</span><span class="sxs-lookup"><span data-stu-id="36e15-192">If your Organization has used MDM to disable [Connectivity/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) then you will be unable to connect to your device.</span></span>

## <span data-ttu-id="36e15-193">分享您的混合現實相片和影片</span><span class="sxs-lookup"><span data-stu-id="36e15-193">Share your mixed reality photos and videos</span></span>

<span data-ttu-id="36e15-194">在捕獲混合式現實相片或影片之後，會出現預覽。</span><span class="sxs-lookup"><span data-stu-id="36e15-194">After capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="36e15-195">選取預覽上方的 [ **共用** ] 圖示，以顯示 [共用小幫手]。</span><span class="sxs-lookup"><span data-stu-id="36e15-195">Select the **share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="36e15-196">您可以從這裡選取您想要共用該相片或影片的終點。</span><span class="sxs-lookup"><span data-stu-id="36e15-196">From there, you can select the end point to which you'd like to share that photo or video.</span></span>

<span data-ttu-id="36e15-197">您也可以透過自動上傳您的混合現實相片和影片，從 OneDrive 共用混合現實相片和影片。</span><span class="sxs-lookup"><span data-stu-id="36e15-197">You can also share mixed reality photos and videos from OneDrive, by automatically uploading your mixed reality photos and videos.</span></span> <span data-ttu-id="36e15-198">在 HoloLens 上開啟 OneDrive app，並使用個人的 [Microsoft 帳戶](https://account.microsoft.com) 登入（如果您尚未這麼做）。</span><span class="sxs-lookup"><span data-stu-id="36e15-198">Open the OneDrive app on HoloLens and sign in with a personal [Microsoft account](https://account.microsoft.com) if you haven't already.</span></span> <span data-ttu-id="36e15-199">選取 [ **設定** ] 圖示，然後選擇 [ **相機上傳**]。</span><span class="sxs-lookup"><span data-stu-id="36e15-199">Select the **settings** icon and choose **Camera upload**.</span></span> <span data-ttu-id="36e15-200">開啟 [相機上傳]。</span><span class="sxs-lookup"><span data-stu-id="36e15-200">Turn Camera upload on.</span></span> <span data-ttu-id="36e15-201">每當您在 HoloLens 上啟動 app 時，您的混合現實相片和影片現在都會上傳到 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="36e15-201">Your mixed reality photos and videos will now be uploaded to OneDrive each time you launch the app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="36e15-202">如果您已使用個人 Microsoft 帳戶登入 OneDrive，您就只能在 OneDrive 中啟用相機上傳。</span><span class="sxs-lookup"><span data-stu-id="36e15-202">You can only enable camera upload in OneDrive if you’re signed into OneDrive with a personal Microsoft account.</span></span> <span data-ttu-id="36e15-203">如果您使用公司或學校帳戶設定 HoloLens，您可以在 OneDrive app 中新增個人 Microsoft 帳戶，以啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="36e15-203">If you set up HoloLens with a work or school account, you can add a personal Microsoft account in the OneDrive app to enable this feature.</span></span>

## <span data-ttu-id="36e15-204">混合現實捕獲的限制</span><span class="sxs-lookup"><span data-stu-id="36e15-204">Limitations of mixed reality capture</span></span>

- <span data-ttu-id="36e15-205">使用混合現實捕獲時，HoloLens 的幀頻會減半到 30 Hz。</span><span class="sxs-lookup"><span data-stu-id="36e15-205">While using mixed reality capture, the framerate of HoloLens will be halved to 30 Hz.</span></span>
- <span data-ttu-id="36e15-206">如果相片/視頻攝影機已由另一個應用程式、即時資料流或系統資源不足，可能會降低相片和影片的解析度。</span><span class="sxs-lookup"><span data-stu-id="36e15-206">The resolution of photos and videos may be reduced if the photo/video camera is already in use by another application, while live streaming, or when system resources are low.</span></span>

### <span data-ttu-id="36e15-207">最大錄製長度</span><span class="sxs-lookup"><span data-stu-id="36e15-207">Maximum recording length</span></span>

<span data-ttu-id="36e15-208">在 Windows 全息版前的 HoloLens 2 裝置上，在裝置上錄製的版本20H2 影片的長度限制為最多五分鐘。</span><span class="sxs-lookup"><span data-stu-id="36e15-208">On HoloLens 2 devices before the Windows Holographic, version 20H2 videos recorded on the device were limited to maximum length of five minutes.</span></span>

<span data-ttu-id="36e15-209">由於客戶意見反應，我們已增加 [混合現實捕獲](holographic-photos-and-videos.md)的錄製長度。</span><span class="sxs-lookup"><span data-stu-id="36e15-209">Due to customer feedback we’ve increased the recording length of [mixed reality captures](holographic-photos-and-videos.md).</span></span> <span data-ttu-id="36e15-210">預設只會將混合的實際捕獲限制為5分鐘，但會根據可用磁碟空間來計算最大錄製長度。</span><span class="sxs-lookup"><span data-stu-id="36e15-210">Mixed reality captures will no longer be limited to 5 minutes by default but instead will calculate the maximum recording length based on available disk space.</span></span> <span data-ttu-id="36e15-211">裝置會根據可用磁碟空間達到總磁碟空間的80%，來估計最大影片錄製持續時間。</span><span class="sxs-lookup"><span data-stu-id="36e15-211">The device will estimate the max video recording duration based on available disk space up to 80% of the total disk space.</span></span>

> [!NOTE]
> <span data-ttu-id="36e15-212">如果發生下列其中一種情況，HoloLens 會將預設的視頻錄製長度 (5 分鐘) ：</span><span class="sxs-lookup"><span data-stu-id="36e15-212">The HoloLens will use default video recording length (5 minutes) if one of the following occurs:</span></span>
> - <span data-ttu-id="36e15-213">估計的最大錄製持續時間小於預設值5分鐘。</span><span class="sxs-lookup"><span data-stu-id="36e15-213">The estimated max recording duration is smaller than the default 5 mins.</span></span>
> - <span data-ttu-id="36e15-214">可用磁碟空間少於磁片總空間的20%。</span><span class="sxs-lookup"><span data-stu-id="36e15-214">The available disk space is less than 20% of the total disk space.</span></span>

## <span data-ttu-id="36e15-215">預設檔案格式及解析度</span><span class="sxs-lookup"><span data-stu-id="36e15-215">Default file format and resolution</span></span>

### <span data-ttu-id="36e15-216">預設相片格式及解析度</span><span class="sxs-lookup"><span data-stu-id="36e15-216">Default photo format and resolution</span></span>

|  <span data-ttu-id="36e15-217">裝置</span><span class="sxs-lookup"><span data-stu-id="36e15-217">Device</span></span>  |  <span data-ttu-id="36e15-218">格式</span><span class="sxs-lookup"><span data-stu-id="36e15-218">Format</span></span>  |  <span data-ttu-id="36e15-219">擴充功能</span><span class="sxs-lookup"><span data-stu-id="36e15-219">Extension</span></span>  |  <span data-ttu-id="36e15-220">解決方法</span><span class="sxs-lookup"><span data-stu-id="36e15-220">Resolution</span></span>  |
|----------|----------|----------|----------|
| <span data-ttu-id="36e15-221">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="36e15-221">HoloLens 2</span></span> | [<span data-ttu-id="36e15-222">JPEG</span><span class="sxs-lookup"><span data-stu-id="36e15-222">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="36e15-223">.jpg</span><span class="sxs-lookup"><span data-stu-id="36e15-223">.jpg</span></span> | <span data-ttu-id="36e15-224">3904x2196px</span><span class="sxs-lookup"><span data-stu-id="36e15-224">3904x2196px</span></span> |
| <span data-ttu-id="36e15-225">HoloLens (1 gen) </span><span class="sxs-lookup"><span data-stu-id="36e15-225">HoloLens (1st gen)</span></span> | [<span data-ttu-id="36e15-226">JPEG</span><span class="sxs-lookup"><span data-stu-id="36e15-226">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="36e15-227">.jpg</span><span class="sxs-lookup"><span data-stu-id="36e15-227">.jpg</span></span> | <span data-ttu-id="36e15-228">1408x792px</span><span class="sxs-lookup"><span data-stu-id="36e15-228">1408x792px</span></span> |

### <span data-ttu-id="36e15-229">錄製的影片格式及解析度</span><span class="sxs-lookup"><span data-stu-id="36e15-229">Recorded video format and resolution</span></span>

| <span data-ttu-id="36e15-230">裝置</span><span class="sxs-lookup"><span data-stu-id="36e15-230">Device</span></span> | <span data-ttu-id="36e15-231">格式</span><span class="sxs-lookup"><span data-stu-id="36e15-231">Format</span></span> | <span data-ttu-id="36e15-232">擴充功能</span><span class="sxs-lookup"><span data-stu-id="36e15-232">Extension</span></span> | <span data-ttu-id="36e15-233">解決方法</span><span class="sxs-lookup"><span data-stu-id="36e15-233">Resolution</span></span> | <span data-ttu-id="36e15-234">網速</span><span class="sxs-lookup"><span data-stu-id="36e15-234">Speed</span></span> | <span data-ttu-id="36e15-235">音效</span><span class="sxs-lookup"><span data-stu-id="36e15-235">Audio</span></span> |
|----------|----------|----------|----------|----------|----------|
| <span data-ttu-id="36e15-236">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="36e15-236">HoloLens 2</span></span> | [<span data-ttu-id="36e15-237">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="36e15-237">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="36e15-238">.mp4</span><span class="sxs-lookup"><span data-stu-id="36e15-238">.mp4</span></span> | <span data-ttu-id="36e15-239">1920x1080px</span><span class="sxs-lookup"><span data-stu-id="36e15-239">1920x1080px</span></span> | <span data-ttu-id="36e15-240">30fps</span><span class="sxs-lookup"><span data-stu-id="36e15-240">30fps</span></span> | <span data-ttu-id="36e15-241">48kHz 身歷聲</span><span class="sxs-lookup"><span data-stu-id="36e15-241">48kHz Stereo</span></span> |
| <span data-ttu-id="36e15-242">HoloLens (1 gen) </span><span class="sxs-lookup"><span data-stu-id="36e15-242">HoloLens (1st gen)</span></span> |  [<span data-ttu-id="36e15-243">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="36e15-243">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="36e15-244">.mp4</span><span class="sxs-lookup"><span data-stu-id="36e15-244">.mp4</span></span> | <span data-ttu-id="36e15-245">1216x684px</span><span class="sxs-lookup"><span data-stu-id="36e15-245">1216x684px</span></span> | <span data-ttu-id="36e15-246">24fps</span><span class="sxs-lookup"><span data-stu-id="36e15-246">24fps</span></span> | <span data-ttu-id="36e15-247">48kHz 身歷聲</span><span class="sxs-lookup"><span data-stu-id="36e15-247">48kHz Stereo</span></span> |
