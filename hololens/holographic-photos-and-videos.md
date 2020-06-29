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
ms.openlocfilehash: 1be4e80c040d5b8e451c07fb931c7c7fb8d5ab48
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828291"
---
# <span data-ttu-id="c8188-104">建立混合實境相片和影片</span><span class="sxs-lookup"><span data-stu-id="c8188-104">Create mixed reality photos and videos</span></span>

<span data-ttu-id="c8188-105">HoloLens 讓使用者能夠與數位世界混合現實世界。</span><span class="sxs-lookup"><span data-stu-id="c8188-105">HoloLens gives users the experience of mixing the real world with the digital world.</span></span>  <span data-ttu-id="c8188-106">混合式現實捕獲（MRC）可讓您以相片或影片的形式捕獲該體驗，或與其他人即時共用您所看到的內容。</span><span class="sxs-lookup"><span data-stu-id="c8188-106">Mixed reality capture (MRC) lets you capture that experience as a photo or video, or share what you see with others in real-time.</span></span>

<span data-ttu-id="c8188-107">混合式現實捕獲會使用第一個人員的觀點，讓其他人可以在您看到全息影像時看到它們。</span><span class="sxs-lookup"><span data-stu-id="c8188-107">Mixed reality capture uses a first-person point of view so other people can see holograms as you see them.</span></span> <span data-ttu-id="c8188-108">如果是第三人的觀點，請使用[spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view)。</span><span class="sxs-lookup"><span data-stu-id="c8188-108">For a third-person point of view, use [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view).</span></span> <span data-ttu-id="c8188-109">Spectator view 對於示範特別有用。</span><span class="sxs-lookup"><span data-stu-id="c8188-109">Spectator view is especially useful for demos.</span></span>

<span data-ttu-id="c8188-110">您可以在朋友和同事之間共用影片，同時也能協助其他人使用 app 或傳達應用程式和體驗的問題。</span><span class="sxs-lookup"><span data-stu-id="c8188-110">While it's fun to share videos amongst friends and colleagues, videos can also help teach other people to use an app or to communicate problems with apps and experiences.</span></span>

> [!NOTE]
> <span data-ttu-id="c8188-111">如果您無法啟動混合式現實捕獲體驗，且您的 HoloLens 是工作裝置，請諮詢您的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="c8188-111">If you can't launch mixed reality capture experiences and your HoloLens is a work device, check with your system administrator.</span></span> <span data-ttu-id="c8188-112">您可以透過公司原則限制對相機的存取權。</span><span class="sxs-lookup"><span data-stu-id="c8188-112">Access to the camera can be restricted through company policy.</span></span>

## <span data-ttu-id="c8188-113">捕獲混合式現實相片</span><span class="sxs-lookup"><span data-stu-id="c8188-113">Capture a mixed reality photo</span></span>

<span data-ttu-id="c8188-114">有幾種方法可以在 HoloLens 上拍攝混合現實相片;您可以使用硬體按鈕、語音或 [開始] 功能表。</span><span class="sxs-lookup"><span data-stu-id="c8188-114">There are several ways to take a photo of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <span data-ttu-id="c8188-115">[拍攝相片] 的硬體按鈕</span><span class="sxs-lookup"><span data-stu-id="c8188-115">Hardware buttons to take photos</span></span>

<span data-ttu-id="c8188-116">若要拍攝目前視圖的快速相片，請同步選取 [音量] 和 [音量] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c8188-116">To take a quick photo of your current view, press the volume up and volume down buttons at the same time.</span></span>  <span data-ttu-id="c8188-117">這有點像是 HoloLens 版本的螢幕擷取畫面或列印畫面。</span><span class="sxs-lookup"><span data-stu-id="c8188-117">This is a bit like the HoloLens version of a screenshot or print screen.</span></span>

- [<span data-ttu-id="c8188-118">HoloLens 2 上的按鈕位置</span><span class="sxs-lookup"><span data-stu-id="c8188-118">Button locations on HoloLens 2</span></span>](hololens2-hardware.md)
- [<span data-ttu-id="c8188-119">HoloLens 上的按鈕位置（第1代）</span><span class="sxs-lookup"><span data-stu-id="c8188-119">Button locations on HoloLens (1st gen)</span></span>](hololens1-hardware.md#hololens-components)

> [!NOTE]
> <span data-ttu-id="c8188-120">按住 [**音量**] 和 [**音量**] 按鈕三秒，就可以開始錄製影片，而不是拍攝相片。</span><span class="sxs-lookup"><span data-stu-id="c8188-120">Holding the **volume up** and **volume down** buttons for three seconds will start recording a video rather than taking a photo.</span></span> <span data-ttu-id="c8188-121">若要停止錄製，請同步選取 [**音量**] 和 [調**低音量**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c8188-121">To stop recording, tap both **volume up** and **volume down** buttons simultaneously.</span></span>

### <span data-ttu-id="c8188-122">[拍攝相片] 的語音命令</span><span class="sxs-lookup"><span data-stu-id="c8188-122">Voice commands to take photos</span></span>

<span data-ttu-id="c8188-123">在 HoloLens 2 上，版本2004（及更新版本），請說：「拍攝圖片」。</span><span class="sxs-lookup"><span data-stu-id="c8188-123">On HoloLens 2, version 2004 (and later), say: "Take a picture."</span></span>

<span data-ttu-id="c8188-124">在 HoloLens （第1代）或 HoloLens 2 （版本1903）上，說：「你好小娜，請拍攝圖片」。</span><span class="sxs-lookup"><span data-stu-id="c8188-124">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, take a picture."</span></span>

### <span data-ttu-id="c8188-125">[開始] 功能表拍攝相片</span><span class="sxs-lookup"><span data-stu-id="c8188-125">Start menu to take photos</span></span>

<span data-ttu-id="c8188-126">使用 [開始] 手勢移至 [**開始**]，然後選取**相機**圖示。</span><span class="sxs-lookup"><span data-stu-id="c8188-126">Use the Start gesture to go to **Start**, then select the **camera** icon.</span></span>

<span data-ttu-id="c8188-127">將您的頭指向您想要捕獲的方向，然後[按一下 [air](hololens2-basic-usage.md#touch-holograms-near-you) ] 拍攝相片。</span><span class="sxs-lookup"><span data-stu-id="c8188-127">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to take a photo.</span></span> <span data-ttu-id="c8188-128">您可以繼續空中輕觸並捕獲其他相片。</span><span class="sxs-lookup"><span data-stu-id="c8188-128">You can continue to air tap and capture additional photos.</span></span> <span data-ttu-id="c8188-129">您捕獲的任何相片都會儲存至您的裝置。</span><span class="sxs-lookup"><span data-stu-id="c8188-129">Any photos you capture will be saved to your device.</span></span>

<span data-ttu-id="c8188-130">再次使用 [開始] 手勢來結束相片捕獲。</span><span class="sxs-lookup"><span data-stu-id="c8188-130">Use the Start gesture again to end photo capture.</span></span>  

## <span data-ttu-id="c8188-131">捕獲混合式現實影片</span><span class="sxs-lookup"><span data-stu-id="c8188-131">Capture a mixed reality video</span></span>

<span data-ttu-id="c8188-132">有幾種方法可以在 HoloLens 上錄製混合現實的影片;您可以使用硬體按鈕、語音或 [開始] 功能表。</span><span class="sxs-lookup"><span data-stu-id="c8188-132">There are several ways to record a video of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <span data-ttu-id="c8188-133">錄製影片的硬體按鈕</span><span class="sxs-lookup"><span data-stu-id="c8188-133">Hardware buttons to record videos</span></span>

<span data-ttu-id="c8188-134">錄製影片最快速的方式，就是在三秒倒計時開始前，同時按住 [**音量**] 和 [**音量**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c8188-134">The quickest way to record a video is to press and hold the **volume up** and **volume down** buttons simultaneously until a three-second countdown begins.</span></span> <span data-ttu-id="c8188-135">若要停止錄製，請同時輕觸兩個按鈕。</span><span class="sxs-lookup"><span data-stu-id="c8188-135">To stop recording, tap both buttons simultaneously.</span></span>

> [!NOTE]
> <span data-ttu-id="c8188-136">您可以同時快速地同步選取 [**音量**] 和 [**音量**] 按鈕，而不需要錄製影片。</span><span class="sxs-lookup"><span data-stu-id="c8188-136">Quickly pressing the **volume up** and **volume down** buttons at the same time will take a photo rather than recording a video.</span></span>

### <span data-ttu-id="c8188-137">錄製影片的語音</span><span class="sxs-lookup"><span data-stu-id="c8188-137">Voice to record videos</span></span>

<span data-ttu-id="c8188-138">在 HoloLens 2 上，版本2004（及更新版本），請說：「開始錄製」。</span><span class="sxs-lookup"><span data-stu-id="c8188-138">On HoloLens 2, version 2004 (and later), say: "Start recording."</span></span> <span data-ttu-id="c8188-139">若要停止錄製，請說「停止錄製」。</span><span class="sxs-lookup"><span data-stu-id="c8188-139">To stop recording, say "Stop recording."</span></span>

<span data-ttu-id="c8188-140">在 HoloLens （第1代）或 HoloLens 2 （版本1903）上，說：「你好小娜，開始錄製」。</span><span class="sxs-lookup"><span data-stu-id="c8188-140">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, start recording."</span></span> <span data-ttu-id="c8188-141">若要停止錄製，請說「你好小娜，停止錄製」。</span><span class="sxs-lookup"><span data-stu-id="c8188-141">To stop recording, say "Hey Cortana, stop recording."</span></span>

### <span data-ttu-id="c8188-142">[開始] 功能表以錄製影片</span><span class="sxs-lookup"><span data-stu-id="c8188-142">Start menu to record videos</span></span>

<span data-ttu-id="c8188-143">使用 [開始] 手勢移至 [**開始**]，然後選取 [**影片**] 圖示。</span><span class="sxs-lookup"><span data-stu-id="c8188-143">Use the Start gesture to go to **Start**, then select the **video** icon.</span></span> <span data-ttu-id="c8188-144">將您的頭指向您想要捕獲的方向，然後[按一下 [air](hololens2-basic-usage.md#touch-holograms-near-you) ] （開始錄製）。</span><span class="sxs-lookup"><span data-stu-id="c8188-144">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to start recording.</span></span> <span data-ttu-id="c8188-145">會有三秒的倒計時，您的錄製將會開始。</span><span class="sxs-lookup"><span data-stu-id="c8188-145">There will be a three second countdown and your recording will begin.</span></span>

<span data-ttu-id="c8188-146">若要停止錄製，請使用 [開始] 手勢，然後選取 [醒目提示的**影片**] 圖示。</span><span class="sxs-lookup"><span data-stu-id="c8188-146">To stop recording, use the Start gesture and select the highlighted **video** icon.</span></span> <span data-ttu-id="c8188-147">影片將會儲存至您的裝置。</span><span class="sxs-lookup"><span data-stu-id="c8188-147">The video will be saved to your device.</span></span>

> [!NOTE]
> **<span data-ttu-id="c8188-148">僅適用于 HoloLens （第1代）</span><span class="sxs-lookup"><span data-stu-id="c8188-148">Applies to HoloLens (1st gen) only</span></span>**  
> <span data-ttu-id="c8188-149">[Windows 10 月2018更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)會變更 [開始] 手勢和 Windows 按鈕在 HoloLens （第1代）上的行為方式。</span><span class="sxs-lookup"><span data-stu-id="c8188-149">The [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) changes how the Start gesture and Windows button behave on HoloLens (1st gen).</span></span> <span data-ttu-id="c8188-150">更新前，[開始手勢] 或 [Windows] 按鈕會停止視頻錄製。</span><span class="sxs-lookup"><span data-stu-id="c8188-150">Before the update, the Start gesture or Windows button would stop a video recording.</span></span> <span data-ttu-id="c8188-151">在更新之後，[開始] 手勢或 Windows 按鈕會開啟 [**開始**] 功能表（如果您使用的是沉浸式應用程式，則會顯示 [**快速動作] 功能表**），您可以在其中選取醒目提示的**影片**圖示以停止錄製。</span><span class="sxs-lookup"><span data-stu-id="c8188-151">After the update, however, the Start gesture or Windows button opens the **Start** menu (or the **quick actions menu** if you are in an immersive app), from which you can select the highlighted **video** icon to stop recording.</span></span>

## <span data-ttu-id="c8188-152">共用您即時看到的內容</span><span class="sxs-lookup"><span data-stu-id="c8188-152">Share what you see in real-time</span></span>

<span data-ttu-id="c8188-153">您可以在 HoloLens 中即時與您的朋友和同事共用您所看到的內容。</span><span class="sxs-lookup"><span data-stu-id="c8188-153">You can share what you see in HoloLens with friends and colleagues in real-time.</span></span> <span data-ttu-id="c8188-154">有幾種方法可供使用：</span><span class="sxs-lookup"><span data-stu-id="c8188-154">There are a few methods available:</span></span>

1. <span data-ttu-id="c8188-155">連線至支援 Miracast 的裝置或配接器，以在電視上觀看。</span><span class="sxs-lookup"><span data-stu-id="c8188-155">Connecting to a Miracast-enabled device or adapter to watch on a TV.</span></span>
1. <span data-ttu-id="c8188-156">使用[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)在電腦上觀看</span><span class="sxs-lookup"><span data-stu-id="c8188-156">Using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to watch on a PC</span></span>
1. <span data-ttu-id="c8188-157">使用[Microsoft HoloLens 隨附應用程式](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)在電腦上觀看。</span><span class="sxs-lookup"><span data-stu-id="c8188-157">Using the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) to watch on a PC.</span></span>
1. <span data-ttu-id="c8188-158">部署[Microsoft Dynamics 365 遠端協助](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist)應用程式，這可讓前線工作者流式處理他們對遠端專家所看到的內容。</span><span class="sxs-lookup"><span data-stu-id="c8188-158">Deploying the [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) app, which enables front-line workers to stream what they see to a remote expert.</span></span> <span data-ttu-id="c8188-159">然後，遠端專家就可以在他們的世界中引導前一行的工作人員 verbally 或進行標注。</span><span class="sxs-lookup"><span data-stu-id="c8188-159">The remote expert can then guide the front-line worker verbally or by annotating in their world.</span></span>

> [!NOTE]
> <span data-ttu-id="c8188-160">透過 Windows Device Portal 或 Microsoft HoloLens 隨附應用程式共用所看到的內容，需要您的 HoloLens 才能處於[開發人員模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="c8188-160">Sharing what you see via Windows Device Portal or Microsoft HoloLens companion app requires your HoloLens to be in [Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal).</span></span>

### <span data-ttu-id="c8188-161">使用 Miracast 進行串流影片</span><span class="sxs-lookup"><span data-stu-id="c8188-161">Stream video with Miracast</span></span>

<span data-ttu-id="c8188-162">使用 [開始] 手勢移至 [**開始**]，然後選取 [**連接]** 圖示。</span><span class="sxs-lookup"><span data-stu-id="c8188-162">Use the Start gesture to go to **Start**, then select the **connect** icon.</span></span> <span data-ttu-id="c8188-163">從顯示的選擇器中，選取您要連接的已啟用 Miracast 的裝置或配接器。</span><span class="sxs-lookup"><span data-stu-id="c8188-163">From the picker that appears, select the Miracast-enabled device or adapter to which you want to connect.</span></span>

<span data-ttu-id="c8188-164">若要停止共用，請使用 [開始] 手勢，然後選取 [醒目提示的連線 **]** 圖示。</span><span class="sxs-lookup"><span data-stu-id="c8188-164">To stop sharing, use the Start gesture and select the highlighted **connect** icon.</span></span> <span data-ttu-id="c8188-165">因為您正在進行流式處理，所以不會將任何內容儲存至您的裝置。</span><span class="sxs-lookup"><span data-stu-id="c8188-165">Because you were streaming, nothing will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="c8188-166">從[Windows 10 年10月2018更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)開始，HoloLens （1st gen）已啟用 Miracast 支援。</span><span class="sxs-lookup"><span data-stu-id="c8188-166">Miracast support was enabled on HoloLens (1st gen) beginning with the [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018).</span></span>

### <span data-ttu-id="c8188-167">Windows Device Portal 的即時影片</span><span class="sxs-lookup"><span data-stu-id="c8188-167">Real time video with Windows Device Portal</span></span>

<span data-ttu-id="c8188-168">因為透過 Windows 裝置入口網站共用需要在 HoloLens 上啟用開發人員模式，請依照開發人員檔中的指示進行，以[設定開發人員模式並流覽 Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="c8188-168">Because sharing via Windows Device Portal requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode and navigate Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

### <span data-ttu-id="c8188-169">Microsoft HoloLens 隨附應用程式</span><span class="sxs-lookup"><span data-stu-id="c8188-169">Microsoft HoloLens companion app</span></span>

<span data-ttu-id="c8188-170">因為透過 Microsoft HoloLens 隨附 app 進行共用需要在 HoloLens 上啟用開發人員模式，請依照開發人員檔中的指示來[設定開發人員模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="c8188-170">Because sharing via the Microsoft HoloLens companion app requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="c8188-171">然後，下載[Microsoft HoloLens 隨附應用程式](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)，並依照 app 內的指示連線至您的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="c8188-171">Then, download the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) and follow the instructions within the app to connect to your HoloLens.</span></span>

<span data-ttu-id="c8188-172">使用您的 HoloLens 設定應用程式後，請從應用程式的主功能表選取 [**即時資料流**] 選項。</span><span class="sxs-lookup"><span data-stu-id="c8188-172">Once the app is set up with your HoloLens, select the **Live stream** option from the app's main menu.</span></span>

## <span data-ttu-id="c8188-173">查看您的混合現實相片和影片</span><span class="sxs-lookup"><span data-stu-id="c8188-173">View your mixed reality photos and videos</span></span>

<span data-ttu-id="c8188-174">混合現實相片和影片會儲存到裝置的「相機捲筒」。</span><span class="sxs-lookup"><span data-stu-id="c8188-174">Mixed reality photos and videos are saved to the device's "Camera Roll".</span></span> <span data-ttu-id="c8188-175">您可以在您的 HoloLens 上使用 [檔案資源管理器] 應用程式（流覽至 [圖片] > [相機投影圖]）流覽此資料夾的內容。</span><span class="sxs-lookup"><span data-stu-id="c8188-175">You can browse the contents of this folder on your HoloLens with the File Explorer app (navigate to Pictures > Camera Roll).</span></span>

<span data-ttu-id="c8188-176">您也可以在已預先安裝在 HoloLens 上的相片 app 中，查看您的混合現實相片和影片。</span><span class="sxs-lookup"><span data-stu-id="c8188-176">You can also view your mixed reality photos and videos in the Photos app, which is pre-installed on HoloLens.</span></span> <span data-ttu-id="c8188-177">若要固定您世界上的相片，請在 [相片] 應用程式中選取，然後選擇 [**混合世界**] 中的 [位置]。</span><span class="sxs-lookup"><span data-stu-id="c8188-177">To pin a photo in your world, select it in the Photos app and choose **Place in mixed world**.</span></span> <span data-ttu-id="c8188-178">您可以在放置之後，在您的世界周圍移動相片。</span><span class="sxs-lookup"><span data-stu-id="c8188-178">You can move the photo around your world after it's been placed.</span></span>

<span data-ttu-id="c8188-179">若要在連線至 HoloLens 的電腦上查看和/或儲存您的混合現實相片和影片，您可以透過 MTP 使用[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)或[電腦的檔案資源管理器](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="c8188-179">To view and/or save your mixed reality photos and videos on a PC connected to HoloLens, you can use [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) or your [PC's File Explorer via MTP](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens).</span></span>

## <span data-ttu-id="c8188-180">分享您的混合現實相片和影片</span><span class="sxs-lookup"><span data-stu-id="c8188-180">Share your mixed reality photos and videos</span></span>

<span data-ttu-id="c8188-181">在捕獲混合式現實相片或影片之後，會出現預覽。</span><span class="sxs-lookup"><span data-stu-id="c8188-181">After capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="c8188-182">選取預覽上方的 [**共用**] 圖示，以顯示 [共用小幫手]。</span><span class="sxs-lookup"><span data-stu-id="c8188-182">Select the **share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="c8188-183">您可以從這裡選取您想要共用該相片或影片的終點。</span><span class="sxs-lookup"><span data-stu-id="c8188-183">From there, you can select the end point to which you'd like to share that photo or video.</span></span>

<span data-ttu-id="c8188-184">您也可以透過自動上傳您的混合現實相片和影片，從 OneDrive 共用混合現實相片和影片。</span><span class="sxs-lookup"><span data-stu-id="c8188-184">You can also share mixed reality photos and videos from OneDrive, by automatically uploading your mixed reality photos and videos.</span></span> <span data-ttu-id="c8188-185">在 HoloLens 上開啟 OneDrive app，並使用個人的[Microsoft 帳戶](https://account.microsoft.com)登入（如果您尚未這麼做）。</span><span class="sxs-lookup"><span data-stu-id="c8188-185">Open the OneDrive app on HoloLens and sign in with a personal [Microsoft account](https://account.microsoft.com) if you haven't already.</span></span> <span data-ttu-id="c8188-186">選取 [**設定**] 圖示，然後選擇 [**相機上傳**]。</span><span class="sxs-lookup"><span data-stu-id="c8188-186">Select the **settings** icon and choose **Camera upload**.</span></span> <span data-ttu-id="c8188-187">開啟 [相機上傳]。</span><span class="sxs-lookup"><span data-stu-id="c8188-187">Turn Camera upload on.</span></span> <span data-ttu-id="c8188-188">每當您在 HoloLens 上啟動 app 時，您的混合現實相片和影片現在都會上傳到 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="c8188-188">Your mixed reality photos and videos will now be uploaded to OneDrive each time you launch the app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="c8188-189">如果您已使用個人 Microsoft 帳戶登入 OneDrive，您就只能在 OneDrive 中啟用相機上傳。</span><span class="sxs-lookup"><span data-stu-id="c8188-189">You can only enable camera upload in OneDrive if you’re signed into OneDrive with a personal Microsoft account.</span></span> <span data-ttu-id="c8188-190">如果您使用公司或學校帳戶設定 HoloLens，您可以在 OneDrive app 中新增個人 Microsoft 帳戶，以啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="c8188-190">If you set up HoloLens with a work or school account, you can add a personal Microsoft account in the OneDrive app to enable this feature.</span></span>

## <span data-ttu-id="c8188-191">混合現實捕獲的限制</span><span class="sxs-lookup"><span data-stu-id="c8188-191">Limitations of mixed reality capture</span></span>

- <span data-ttu-id="c8188-192">使用混合現實捕獲時，HoloLens 的幀頻會減半到 30 Hz。</span><span class="sxs-lookup"><span data-stu-id="c8188-192">While using mixed reality capture, the framerate of HoloLens will be halved to 30 Hz.</span></span>
- <span data-ttu-id="c8188-193">影片的最大長度為5分鐘。</span><span class="sxs-lookup"><span data-stu-id="c8188-193">Videos have a maximum length of five minutes.</span></span>
- <span data-ttu-id="c8188-194">如果相片/視頻攝影機已由另一個應用程式、即時資料流或系統資源不足，可能會降低相片和影片的解析度。</span><span class="sxs-lookup"><span data-stu-id="c8188-194">The resolution of photos and videos may be reduced if the photo/video camera is already in use by another application, while live streaming, or when system resources are low.</span></span>

## <span data-ttu-id="c8188-195">預設檔案格式及解析度</span><span class="sxs-lookup"><span data-stu-id="c8188-195">Default file format and resolution</span></span>

### <span data-ttu-id="c8188-196">預設相片格式及解析度</span><span class="sxs-lookup"><span data-stu-id="c8188-196">Default photo format and resolution</span></span>

|  <span data-ttu-id="c8188-197">裝置</span><span class="sxs-lookup"><span data-stu-id="c8188-197">Device</span></span>  |  <span data-ttu-id="c8188-198">格式</span><span class="sxs-lookup"><span data-stu-id="c8188-198">Format</span></span>  |  <span data-ttu-id="c8188-199">擴充功能</span><span class="sxs-lookup"><span data-stu-id="c8188-199">Extension</span></span>  |  <span data-ttu-id="c8188-200">解決方法</span><span class="sxs-lookup"><span data-stu-id="c8188-200">Resolution</span></span>  |
|----------|----------|----------|----------|
| <span data-ttu-id="c8188-201">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="c8188-201">HoloLens 2</span></span> | [<span data-ttu-id="c8188-202">JPEG</span><span class="sxs-lookup"><span data-stu-id="c8188-202">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="c8188-203">.jpg</span><span class="sxs-lookup"><span data-stu-id="c8188-203">.jpg</span></span> | <span data-ttu-id="c8188-204">3904x2196px</span><span class="sxs-lookup"><span data-stu-id="c8188-204">3904x2196px</span></span> |
| <span data-ttu-id="c8188-205">HoloLens （第1代）</span><span class="sxs-lookup"><span data-stu-id="c8188-205">HoloLens (1st gen)</span></span> | [<span data-ttu-id="c8188-206">JPEG</span><span class="sxs-lookup"><span data-stu-id="c8188-206">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="c8188-207">.jpg</span><span class="sxs-lookup"><span data-stu-id="c8188-207">.jpg</span></span> | <span data-ttu-id="c8188-208">1408x792px</span><span class="sxs-lookup"><span data-stu-id="c8188-208">1408x792px</span></span> |

### <span data-ttu-id="c8188-209">錄製的影片格式及解析度</span><span class="sxs-lookup"><span data-stu-id="c8188-209">Recorded video format and resolution</span></span>

| <span data-ttu-id="c8188-210">裝置</span><span class="sxs-lookup"><span data-stu-id="c8188-210">Device</span></span> | <span data-ttu-id="c8188-211">格式</span><span class="sxs-lookup"><span data-stu-id="c8188-211">Format</span></span> | <span data-ttu-id="c8188-212">擴充功能</span><span class="sxs-lookup"><span data-stu-id="c8188-212">Extension</span></span> | <span data-ttu-id="c8188-213">解決方法</span><span class="sxs-lookup"><span data-stu-id="c8188-213">Resolution</span></span> | <span data-ttu-id="c8188-214">網速</span><span class="sxs-lookup"><span data-stu-id="c8188-214">Speed</span></span> | <span data-ttu-id="c8188-215">音效</span><span class="sxs-lookup"><span data-stu-id="c8188-215">Audio</span></span> |
|----------|----------|----------|----------|----------|----------|
| <span data-ttu-id="c8188-216">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="c8188-216">HoloLens 2</span></span> | [<span data-ttu-id="c8188-217">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="c8188-217">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="c8188-218">.mp4</span><span class="sxs-lookup"><span data-stu-id="c8188-218">.mp4</span></span> | <span data-ttu-id="c8188-219">1920x1080px</span><span class="sxs-lookup"><span data-stu-id="c8188-219">1920x1080px</span></span> | <span data-ttu-id="c8188-220">30fps</span><span class="sxs-lookup"><span data-stu-id="c8188-220">30fps</span></span> | <span data-ttu-id="c8188-221">48kHz 身歷聲</span><span class="sxs-lookup"><span data-stu-id="c8188-221">48kHz Stereo</span></span> |
| <span data-ttu-id="c8188-222">HoloLens （第1代）</span><span class="sxs-lookup"><span data-stu-id="c8188-222">HoloLens (1st gen)</span></span> |  [<span data-ttu-id="c8188-223">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="c8188-223">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="c8188-224">.mp4</span><span class="sxs-lookup"><span data-stu-id="c8188-224">.mp4</span></span> | <span data-ttu-id="c8188-225">1216x684px</span><span class="sxs-lookup"><span data-stu-id="c8188-225">1216x684px</span></span> | <span data-ttu-id="c8188-226">24fps</span><span class="sxs-lookup"><span data-stu-id="c8188-226">24fps</span></span> | <span data-ttu-id="c8188-227">48kHz 身歷聲</span><span class="sxs-lookup"><span data-stu-id="c8188-227">48kHz Stereo</span></span> |
