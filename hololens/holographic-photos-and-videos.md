---
title: 拍攝、錄製及分享混合實境相片和影片
description: 瞭解如何使用 HoloLens 混合實境裝置來拍攝、錄製及觀看混合實境相片和影片。 瞭解如何透過 Miracast 或收集的檔案共用。
keywords: hololens， photo， video， capture， mrc， mixed reality capture， 相片， 相機， miracast， stream， livestream， demo， record
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
ms.openlocfilehash: 86ef4328869c15517732eedf3dfb9e2a8252e713
ms.sourcegitcommit: 047738224840013bede45dbb642a0ad2115a9c84
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2021
ms.locfileid: "11406707"
---
# <a name="create-mixed-reality-photos-and-videos"></a><span data-ttu-id="a6a91-105">建立混合實境相片和影片</span><span class="sxs-lookup"><span data-stu-id="a6a91-105">Create mixed reality photos and videos</span></span>

<span data-ttu-id="a6a91-106">HoloLens 為使用者提供將真實世界與數位世界混在一起的體驗。</span><span class="sxs-lookup"><span data-stu-id="a6a91-106">HoloLens gives users the experience of mixing the real world with the digital world.</span></span>  <span data-ttu-id="a6a91-107">混合實境 (MRC) 可讓您以相片或影片來拍攝該體驗，或與其他人即時分享您所看到的內容。</span><span class="sxs-lookup"><span data-stu-id="a6a91-107">Mixed reality capture (MRC) lets you capture that experience as a photo or video, or share what you see with others in real-time.</span></span>

<span data-ttu-id="a6a91-108">混合實境捕獲使用第一人稱觀點，讓其他人可以在您看到全像影像時看到全像影像。</span><span class="sxs-lookup"><span data-stu-id="a6a91-108">Mixed reality capture uses a first-person point of view so other people can see holograms as you see them.</span></span> <span data-ttu-id="a6a91-109">對於第三人觀點，請使用流覽 [視圖](https://docs.microsoft.com/windows/mixed-reality/spectator-view)。</span><span class="sxs-lookup"><span data-stu-id="a6a91-109">For a third-person point of view, use [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view).</span></span> <span data-ttu-id="a6a91-110">流覽視圖在示範中特別有用。</span><span class="sxs-lookup"><span data-stu-id="a6a91-110">Spectator view is especially useful for demos.</span></span>

<span data-ttu-id="a6a91-111">在朋友和同事之間分享影片雖然有趣，但影片也可以協助教導其他人使用應用程式，或溝通應用程式與體驗的問題。</span><span class="sxs-lookup"><span data-stu-id="a6a91-111">While it's fun to share videos amongst friends and colleagues, videos can also help teach other people to use an app or to communicate problems with apps and experiences.</span></span>

> [!NOTE]
> <span data-ttu-id="a6a91-112">如果您無法啟動混合實境捕獲體驗，而且您的 HoloLens 是工作裝置，請連系系統管理員。</span><span class="sxs-lookup"><span data-stu-id="a6a91-112">If you can't launch mixed reality capture experiences and your HoloLens is a work device, check with your system administrator.</span></span> <span data-ttu-id="a6a91-113">您可以透過公司政策限制攝影機的存取權。</span><span class="sxs-lookup"><span data-stu-id="a6a91-113">Access to the camera can be restricted through company policy.</span></span>

## <a name="capture-a-mixed-reality-photo"></a><span data-ttu-id="a6a91-114">拍攝混合實境相片</span><span class="sxs-lookup"><span data-stu-id="a6a91-114">Capture a mixed reality photo</span></span>

<span data-ttu-id="a6a91-115">在 HoloLens 上拍攝混合實境相片的方法有好幾種;您可以使用硬體按鈕、語音或開始功能表。</span><span class="sxs-lookup"><span data-stu-id="a6a91-115">There are several ways to take a photo of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <a name="hardware-buttons-to-take-photos"></a><span data-ttu-id="a6a91-116">拍攝相片的硬體按鈕</span><span class="sxs-lookup"><span data-stu-id="a6a91-116">Hardware buttons to take photos</span></span>

<span data-ttu-id="a6a91-117">若要快速拍攝目前視野的相片，請同時按調高音量和降低音量按鈕。</span><span class="sxs-lookup"><span data-stu-id="a6a91-117">To take a quick photo of your current view, press the volume up and volume down buttons at the same time.</span></span>  <span data-ttu-id="a6a91-118">這有點像是 HoloLens 版本的螢幕擷取畫面或列印畫面。</span><span class="sxs-lookup"><span data-stu-id="a6a91-118">This is a bit like the HoloLens version of a screenshot or print screen.</span></span>

- [<span data-ttu-id="a6a91-119">HoloLens 2 上的按鈕位置</span><span class="sxs-lookup"><span data-stu-id="a6a91-119">Button locations on HoloLens 2</span></span>](hololens2-hardware.md)
- [<span data-ttu-id="a6a91-120">HoloLens 上的按鈕位置 (第一代) </span><span class="sxs-lookup"><span data-stu-id="a6a91-120">Button locations on HoloLens (1st gen)</span></span>](hololens1-hardware.md#hololens-components)

> [!NOTE]
> <span data-ttu-id="a6a91-121">按住 **調高音量** 和 **降低音量** 按鈕三秒鐘後，就會開始錄製影片，而不是拍照。</span><span class="sxs-lookup"><span data-stu-id="a6a91-121">Holding the **volume up** and **volume down** buttons for three seconds will start recording a video rather than taking a photo.</span></span> <span data-ttu-id="a6a91-122">若要停止錄製，請同時 **點選調** 高 **音量和降低** 音量按鈕。</span><span class="sxs-lookup"><span data-stu-id="a6a91-122">To stop recording, tap both **volume up** and **volume down** buttons simultaneously.</span></span>

### <a name="voice-commands-to-take-photos"></a><span data-ttu-id="a6a91-123">拍照的語音命令</span><span class="sxs-lookup"><span data-stu-id="a6a91-123">Voice commands to take photos</span></span>

<span data-ttu-id="a6a91-124">在 HoloLens 2，版本 2004 (及更新) ，請說：「拍照」。</span><span class="sxs-lookup"><span data-stu-id="a6a91-124">On HoloLens 2, version 2004 (and later), say: "Take a picture."</span></span>

<span data-ttu-id="a6a91-125">在 HoloLens (第一代) 或 HoloLens 2，版本 1903 上，說：「嗨 Cortana，拍照」。</span><span class="sxs-lookup"><span data-stu-id="a6a91-125">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, take a picture."</span></span>

### <a name="start-menu-to-take-photos"></a><span data-ttu-id="a6a91-126">拍攝相片的開始功能表</span><span class="sxs-lookup"><span data-stu-id="a6a91-126">Start menu to take photos</span></span>

<span data-ttu-id="a6a91-127">使用開始手勢 **前往開始，** 然後選取 **相機** 圖示。</span><span class="sxs-lookup"><span data-stu-id="a6a91-127">Use the Start gesture to go to **Start**, then select the **camera** icon.</span></span>

<span data-ttu-id="a6a91-128">將頭指向您想要拍攝之專案的方向，然後空中點 [一](hololens2-basic-usage.md#touch-holograms-near-you) 下以拍攝相片。</span><span class="sxs-lookup"><span data-stu-id="a6a91-128">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to take a photo.</span></span> <span data-ttu-id="a6a91-129">您可以繼續空中點一下並拍攝其他相片。</span><span class="sxs-lookup"><span data-stu-id="a6a91-129">You can continue to air tap and capture additional photos.</span></span> <span data-ttu-id="a6a91-130">您拍攝的任何相片都會儲存到您的裝置。</span><span class="sxs-lookup"><span data-stu-id="a6a91-130">Any photos you capture will be saved to your device.</span></span>

<span data-ttu-id="a6a91-131">再次使用開始手勢來結束相片拍攝。</span><span class="sxs-lookup"><span data-stu-id="a6a91-131">Use the Start gesture again to end photo capture.</span></span>  

## <a name="capture-a-mixed-reality-video"></a><span data-ttu-id="a6a91-132">拍攝混合實境影片</span><span class="sxs-lookup"><span data-stu-id="a6a91-132">Capture a mixed reality video</span></span>

<span data-ttu-id="a6a91-133">有幾種方法可以錄製 HoloLens 上混合實境的影片;您可以使用硬體按鈕、語音或開始功能表。</span><span class="sxs-lookup"><span data-stu-id="a6a91-133">There are several ways to record a video of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <a name="hardware-buttons-to-record-videos"></a><span data-ttu-id="a6a91-134">錄製影片的硬體按鈕</span><span class="sxs-lookup"><span data-stu-id="a6a91-134">Hardware buttons to record videos</span></span>

<span data-ttu-id="a6a91-135">錄製影片的最快方式，是同時按住調高音量和降低\*\*\*\* 音量按鈕，\*\*\*\* 直到三秒倒數開始。</span><span class="sxs-lookup"><span data-stu-id="a6a91-135">The quickest way to record a video is to press and hold the **volume up** and **volume down** buttons simultaneously until a three-second countdown begins.</span></span> <span data-ttu-id="a6a91-136">若要停止錄製，請同時點選兩個按鈕。</span><span class="sxs-lookup"><span data-stu-id="a6a91-136">To stop recording, tap both buttons simultaneously.</span></span>

> [!NOTE]
> <span data-ttu-id="a6a91-137">同時快速 **按調高音量** 和降低 **音量** 按鈕會拍攝相片，而不是錄製影片。</span><span class="sxs-lookup"><span data-stu-id="a6a91-137">Quickly pressing the **volume up** and **volume down** buttons at the same time will take a photo rather than recording a video.</span></span>

### <a name="voice-to-record-videos"></a><span data-ttu-id="a6a91-138">錄製影片的語音</span><span class="sxs-lookup"><span data-stu-id="a6a91-138">Voice to record videos</span></span>

<span data-ttu-id="a6a91-139">在 HoloLens 2，版本 2004 (及更新版本) ，請說：「開始錄製」。</span><span class="sxs-lookup"><span data-stu-id="a6a91-139">On HoloLens 2, version 2004 (and later), say: "Start recording."</span></span> <span data-ttu-id="a6a91-140">若要停止錄製，請說「停止錄製」。</span><span class="sxs-lookup"><span data-stu-id="a6a91-140">To stop recording, say "Stop recording."</span></span>

<span data-ttu-id="a6a91-141">在 HoloLens (第一代) 或 HoloLens 2，版本 1903 上，說：「嗨 Cortana，開始錄製」。</span><span class="sxs-lookup"><span data-stu-id="a6a91-141">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, start recording."</span></span> <span data-ttu-id="a6a91-142">若要停止錄製，請說「嗨 Cortana，停止錄製」。</span><span class="sxs-lookup"><span data-stu-id="a6a91-142">To stop recording, say "Hey Cortana, stop recording."</span></span>

### <a name="start-menu-to-record-videos"></a><span data-ttu-id="a6a91-143">錄製影片的開始功能表</span><span class="sxs-lookup"><span data-stu-id="a6a91-143">Start menu to record videos</span></span>

<span data-ttu-id="a6a91-144">使用開始手勢 **前往開始，** 然後選取 **視音訊** 圖示。</span><span class="sxs-lookup"><span data-stu-id="a6a91-144">Use the Start gesture to go to **Start**, then select the **video** icon.</span></span> <span data-ttu-id="a6a91-145">將頭指向您想要拍攝之內容的方向，然後空中 [點一](hololens2-basic-usage.md#touch-holograms-near-you) 下即可開始錄製。</span><span class="sxs-lookup"><span data-stu-id="a6a91-145">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to start recording.</span></span> <span data-ttu-id="a6a91-146">有三秒鐘的倒數計時，您的錄製將會開始。</span><span class="sxs-lookup"><span data-stu-id="a6a91-146">There will be a three second countdown and your recording will begin.</span></span>

<span data-ttu-id="a6a91-147">若要停止錄製，請使用開始手勢，然後選取強調的 **視區** 圖示。</span><span class="sxs-lookup"><span data-stu-id="a6a91-147">To stop recording, use the Start gesture and select the highlighted **video** icon.</span></span> <span data-ttu-id="a6a91-148">影片將會儲存到您的裝置。</span><span class="sxs-lookup"><span data-stu-id="a6a91-148">The video will be saved to your device.</span></span>

> [!NOTE]
> **<span data-ttu-id="a6a91-149">僅適用于 HoloLens (第 1 代) </span><span class="sxs-lookup"><span data-stu-id="a6a91-149">Applies to HoloLens (1st gen) only</span></span>**  
> <span data-ttu-id="a6a91-150">[Windows 10 2018 年 10](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)月更新會變更第一代的 HoloLens 上的開始手勢和 Windows 按鈕 (行為) 。</span><span class="sxs-lookup"><span data-stu-id="a6a91-150">The [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) changes how the Start gesture and Windows button behave on HoloLens (1st gen).</span></span> <span data-ttu-id="a6a91-151">更新之前，啟動手勢或 Windows 按鈕會停止視訊錄製。</span><span class="sxs-lookup"><span data-stu-id="a6a91-151">Before the update, the Start gesture or Windows button would stop a video recording.</span></span> <span data-ttu-id="a6a91-152">不過，更新之後，如果您用的是沉浸式應用程式 (，則啟動手勢或 Windows\*\*\*\* 按鈕會開啟開始功能表 (或快速動作功能表) 您可以在其中選取強調的視訊圖示以停止\*\*\*\* 錄製。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a6a91-152">After the update, however, the Start gesture or Windows button opens the **Start** menu (or the **quick actions menu** if you are in an immersive app), from which you can select the highlighted **video** icon to stop recording.</span></span>

## <a name="share-what-you-see-in-real-time"></a><span data-ttu-id="a6a91-153">即時分享您所看到的專案</span><span class="sxs-lookup"><span data-stu-id="a6a91-153">Share what you see in real-time</span></span>

<span data-ttu-id="a6a91-154">您可以即時與朋友和同事分享在 HoloLens 中所看到的專案。</span><span class="sxs-lookup"><span data-stu-id="a6a91-154">You can share what you see in HoloLens with friends and colleagues in real-time.</span></span> <span data-ttu-id="a6a91-155">有一些方法可用：</span><span class="sxs-lookup"><span data-stu-id="a6a91-155">There are a few methods available:</span></span>

1. <span data-ttu-id="a6a91-156">連接到已啟用 Miracast 的裝置或介面卡，以在電視上觀看。</span><span class="sxs-lookup"><span data-stu-id="a6a91-156">Connecting to a Miracast-enabled device or adapter to watch on a TV.</span></span>
1. <span data-ttu-id="a6a91-157">使用 [Windows 裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 在 PC 上觀看</span><span class="sxs-lookup"><span data-stu-id="a6a91-157">Using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to watch on a PC</span></span>
1. <span data-ttu-id="a6a91-158">使用 [Microsoft HoloLens 小夥伴應用程式](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 在 PC 上觀看。</span><span class="sxs-lookup"><span data-stu-id="a6a91-158">Using the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) to watch on a PC.</span></span>
1. <span data-ttu-id="a6a91-159">部署 [Microsoft Dynamics 365 遠端](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) 協助應用程式，可讓第一線工作人員將看到的資料串流給遠端專家。</span><span class="sxs-lookup"><span data-stu-id="a6a91-159">Deploying the [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) app, which enables front-line workers to stream what they see to a remote expert.</span></span> <span data-ttu-id="a6a91-160">接著，遠端專家就可以用口頭或批註來引導第一線員工。</span><span class="sxs-lookup"><span data-stu-id="a6a91-160">The remote expert can then guide the front-line worker verbally or by annotating in their world.</span></span>

> [!NOTE]
> <span data-ttu-id="a6a91-161">透過 Windows 裝置入口網站或 Microsoft HoloLens 小夥伴應用程式分享您所看到的內容，您的 HoloLens 必須進入 [開發人員模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="a6a91-161">Sharing what you see via Windows Device Portal or Microsoft HoloLens companion app requires your HoloLens to be in [Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal).</span></span>

### <a name="stream-video-with-miracast"></a><span data-ttu-id="a6a91-162">使用 Miracast 串流影片</span><span class="sxs-lookup"><span data-stu-id="a6a91-162">Stream video with Miracast</span></span>

<span data-ttu-id="a6a91-163">使用開始手勢 **前往開始，** 然後 **選取連接圖示** 。</span><span class="sxs-lookup"><span data-stu-id="a6a91-163">Use the Start gesture to go to **Start**, then select the **connect** icon.</span></span> <span data-ttu-id="a6a91-164">從出現的選擇器中，選取您想要連接之已啟用 Miracast 的裝置或介面卡。</span><span class="sxs-lookup"><span data-stu-id="a6a91-164">From the picker that appears, select the Miracast-enabled device or adapter to which you want to connect.</span></span>

<span data-ttu-id="a6a91-165">若要停止共用，請使用開始手勢，然後選取已強調的 **連接** 圖示。</span><span class="sxs-lookup"><span data-stu-id="a6a91-165">To stop sharing, use the Start gesture and select the highlighted **connect** icon.</span></span> <span data-ttu-id="a6a91-166">由於您進行串流，因此不會將任何內容儲存到您的裝置。</span><span class="sxs-lookup"><span data-stu-id="a6a91-166">Because you were streaming, nothing will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="a6a91-167">自 [2018 年 10 月 10](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) (起，第一代的 HoloLens) 已啟用 Miracast 支援。</span><span class="sxs-lookup"><span data-stu-id="a6a91-167">Miracast support was enabled on HoloLens (1st gen) beginning with the [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018).</span></span>

### <a name="real-time-video-with-windows-device-portal"></a><span data-ttu-id="a6a91-168">使用 Windows 裝置入口網站即時影片</span><span class="sxs-lookup"><span data-stu-id="a6a91-168">Real time video with Windows Device Portal</span></span>

<span data-ttu-id="a6a91-169">由於透過 Windows 裝置入口網站共用需要啟用 HoloLens 上的開發人員模式，請遵循開發人員檔中的指示來設定 [開發人員模式並流覽 Windows 裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="a6a91-169">Because sharing via Windows Device Portal requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode and navigate Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

### <a name="microsoft-hololens-companion-app"></a><span data-ttu-id="a6a91-170">Microsoft HoloLens 小夥伴應用程式</span><span class="sxs-lookup"><span data-stu-id="a6a91-170">Microsoft HoloLens companion app</span></span>

<span data-ttu-id="a6a91-171">由於透過 Microsoft HoloLens 小夥伴應用程式共用需要啟用 HoloLens 上的開發人員模式，請遵循開發人員檔中的指示來 [設定開發人員模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="a6a91-171">Because sharing via the Microsoft HoloLens companion app requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="a6a91-172">接著，下載 [Microsoft HoloLens 小夥伴應用程式](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) ，然後按照 App 中的指示來連接到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="a6a91-172">Then, download the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) and follow the instructions within the app to connect to your HoloLens.</span></span>

<span data-ttu-id="a6a91-173">一旦將應用程式設定為 HoloLens，請從應用程式\*\*\*\* 的主功能表中選取即時串流選項。</span><span class="sxs-lookup"><span data-stu-id="a6a91-173">Once the app is set up with your HoloLens, select the **Live stream** option from the app's main menu.</span></span>

## <a name="view-your-mixed-reality-photos-and-videos"></a><span data-ttu-id="a6a91-174">查看混合實境相片和影片</span><span class="sxs-lookup"><span data-stu-id="a6a91-174">View your mixed reality photos and videos</span></span>

<span data-ttu-id="a6a91-175">混合實境相片和影片會儲存到裝置中的「相機膠捲」。</span><span class="sxs-lookup"><span data-stu-id="a6a91-175">Mixed reality photos and videos are saved to the device's "Camera Roll".</span></span> <span data-ttu-id="a6a91-176">您可以使用檔案總管應用程式流覽 HoloLens 上此資料夾的內容， (流覽至圖片>相) 。</span><span class="sxs-lookup"><span data-stu-id="a6a91-176">You can browse the contents of this folder on your HoloLens with the File Explorer app (navigate to Pictures > Camera Roll).</span></span>

<span data-ttu-id="a6a91-177">您也可以在 HoloLens 上預先安裝的相片應用程式中，查看混合實境相片和影片。</span><span class="sxs-lookup"><span data-stu-id="a6a91-177">You can also view your mixed reality photos and videos in the Photos app, which is pre-installed on HoloLens.</span></span> <span data-ttu-id="a6a91-178">若要釘選您世界中的相片，請在相片應用程式中選取相片，然後選擇 **混合世界中的位置**。</span><span class="sxs-lookup"><span data-stu-id="a6a91-178">To pin a photo in your world, select it in the Photos app and choose **Place in mixed world**.</span></span> <span data-ttu-id="a6a91-179">放置相片之後，您可以將相片移動到您的全世界。</span><span class="sxs-lookup"><span data-stu-id="a6a91-179">You can move the photo around your world after it's been placed.</span></span>

<span data-ttu-id="a6a91-180">若要在連接到 HoloLens 的 PC 上，查看和/或儲存混合實境相片和影片，您可以透過[MTP](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)使用[Windows 裝置](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)入口網站或您電腦中的檔案總管。</span><span class="sxs-lookup"><span data-stu-id="a6a91-180">To view and/or save your mixed reality photos and videos on a PC connected to HoloLens, you can use [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) or your [PC's File Explorer via MTP](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens).</span></span>

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a><span data-ttu-id="a6a91-181">使用檔案管理器取得圖片、影片和檔案</span><span class="sxs-lookup"><span data-stu-id="a6a91-181">Use File Explorer to get your pictures, videos and files</span></span>

<span data-ttu-id="a6a91-182">與其他行動裝置類似，將您的 HoloLens 連接到您的電腦，讓檔案總管存取 HoloLens 文件庫 (相片、影片、檔) 輕鬆傳輸。</span><span class="sxs-lookup"><span data-stu-id="a6a91-182">Similar to other mobile devices, connect your HoloLens to your PC to bring up File Explorer to access your HoloLens libraries (photos, videos, documents) for easy transfer.</span></span> <span data-ttu-id="a6a91-183">這個方法便於使用，而且不需要使用裝置入口網站或 Wi-Fi。</span><span class="sxs-lookup"><span data-stu-id="a6a91-183">This method is easy to use and does not require the use of device portal or Wi-Fi.</span></span>

1. <span data-ttu-id="a6a91-184">解除鎖定裝置。</span><span class="sxs-lookup"><span data-stu-id="a6a91-184">Unlock the device.</span></span>
1. <span data-ttu-id="a6a91-185">透過 USB 將裝置連接到電腦。</span><span class="sxs-lookup"><span data-stu-id="a6a91-185">Connect the device to a PC via USB.</span></span>
1. <span data-ttu-id="a6a91-186">檔案檔案管理器應該會開啟您的電腦。</span><span class="sxs-lookup"><span data-stu-id="a6a91-186">File Explorer should open on your PC.</span></span>
1. <span data-ttu-id="a6a91-187">流覽至：此電腦\\*yourhololensname*\Internal Storage\Pictures\Camera Roll</span><span class="sxs-lookup"><span data-stu-id="a6a91-187">Navigate to: This PC\\*yourhololensname*\Internal Storage\Pictures\Camera Roll</span></span>
1. <span data-ttu-id="a6a91-188">將您需要的任何檔案複製到您的電腦。</span><span class="sxs-lookup"><span data-stu-id="a6a91-188">Copy whatever files you need to your PC.</span></span>

<span data-ttu-id="a6a91-189">秘訣：</span><span class="sxs-lookup"><span data-stu-id="a6a91-189">Tips:</span></span>
- <span data-ttu-id="a6a91-190">如果您沒看到任何檔案，請確保您已登錄 HoloLens 以啟用資料的存取。</span><span class="sxs-lookup"><span data-stu-id="a6a91-190">If you don't see any files, please ensure you sign in to your HoloLens to enable access to your data.</span></span>
- <span data-ttu-id="a6a91-191">您可以在其他資料夾中取得其他檔案，例如 [從](hololens-diagnostic-logs.md#offline-diagnostics) 檔資料夾取得診斷檔案。</span><span class="sxs-lookup"><span data-stu-id="a6a91-191">You can get other files in other folders, such as [diagnostics files](hololens-diagnostic-logs.md#offline-diagnostics) from the Documents folder.</span></span>
- <span data-ttu-id="a6a91-192">在 PC 上的檔案總管中，您可以選取裝置屬性以查看 Windows 全攝影 OS 版本號碼 () 、裝置序號和電池百分比。</span><span class="sxs-lookup"><span data-stu-id="a6a91-192">From File Explorer on your PC, you can select Device properties to see Windows Holographic OS version number (firmware version), device serial number, and battery percentage.</span></span>
- <span data-ttu-id="a6a91-193">如果貴組織已使用 MDM 停用連接 [/AllowDMConnection，](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 您將無法連接到您的裝置。</span><span class="sxs-lookup"><span data-stu-id="a6a91-193">If your Organization has used MDM to disable [Connectivity/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) then you will be unable to connect to your device.</span></span>

## <a name="share-your-mixed-reality-photos-and-videos"></a><span data-ttu-id="a6a91-194">分享混合實境相片和影片</span><span class="sxs-lookup"><span data-stu-id="a6a91-194">Share your mixed reality photos and videos</span></span>

<span data-ttu-id="a6a91-195">拍攝混合實境相片或影片之後，將會顯示預覽。</span><span class="sxs-lookup"><span data-stu-id="a6a91-195">After capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="a6a91-196">選取 **預覽上方** 的共用圖示，即可顯示共用小幫手。</span><span class="sxs-lookup"><span data-stu-id="a6a91-196">Select the **share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="a6a91-197">您可以在那裡選取要分享該相片或影片的終點。</span><span class="sxs-lookup"><span data-stu-id="a6a91-197">From there, you can select the end point to which you'd like to share that photo or video.</span></span>

<span data-ttu-id="a6a91-198">您也可以從 OneDrive 分享混合實境相片和影片，自動上傳混合實境相片和影片。</span><span class="sxs-lookup"><span data-stu-id="a6a91-198">You can also share mixed reality photos and videos from OneDrive, by automatically uploading your mixed reality photos and videos.</span></span> <span data-ttu-id="a6a91-199">在 HoloLens 上開啟 OneDrive 應用程式，如果您尚未使用 [個人 Microsoft](https://account.microsoft.com) 帳戶，請以個人 Microsoft 帳戶進行登錄。</span><span class="sxs-lookup"><span data-stu-id="a6a91-199">Open the OneDrive app on HoloLens and sign in with a personal [Microsoft account](https://account.microsoft.com) if you haven't already.</span></span> <span data-ttu-id="a6a91-200">選取設定 **圖示** ，然後選擇相機 **上傳**。</span><span class="sxs-lookup"><span data-stu-id="a6a91-200">Select the **settings** icon and choose **Camera upload**.</span></span> <span data-ttu-id="a6a91-201">開啟相機上傳。</span><span class="sxs-lookup"><span data-stu-id="a6a91-201">Turn Camera upload on.</span></span> <span data-ttu-id="a6a91-202">每次在 HoloLens 上啟動應用程式時，混合實境相片和影片現在都會上傳到 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="a6a91-202">Your mixed reality photos and videos will now be uploaded to OneDrive each time you launch the app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="a6a91-203">您必須使用個人 Microsoft 帳戶已登錄 OneDrive，才能在 OneDrive 中啟用相機上傳。</span><span class="sxs-lookup"><span data-stu-id="a6a91-203">You can only enable camera upload in OneDrive if you’re signed into OneDrive with a personal Microsoft account.</span></span> <span data-ttu-id="a6a91-204">如果您使用公司或學校帳戶設定 HoloLens，您可以在 OneDrive App 中新增個人 Microsoft 帳戶以啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="a6a91-204">If you set up HoloLens with a work or school account, you can add a personal Microsoft account in the OneDrive app to enable this feature.</span></span>

## <a name="limitations-of-mixed-reality-capture"></a><span data-ttu-id="a6a91-205">混合實境捕獲的限制</span><span class="sxs-lookup"><span data-stu-id="a6a91-205">Limitations of mixed reality capture</span></span>

- <span data-ttu-id="a6a91-206">使用混合實境捕獲時，HoloLens 的框架速率會減少為 30 Hz。</span><span class="sxs-lookup"><span data-stu-id="a6a91-206">While using mixed reality capture, the framerate of HoloLens will be halved to 30 Hz.</span></span>
- <span data-ttu-id="a6a91-207">如果另一個應用程式已在使用相片/攝影機、即時串流，或系統資源不足時，相片和影片的解析度可能會降低。</span><span class="sxs-lookup"><span data-stu-id="a6a91-207">The resolution of photos and videos may be reduced if the photo/video camera is already in use by another application, while live streaming, or when system resources are low.</span></span>

### <a name="maximum-recording-length"></a><span data-ttu-id="a6a91-208">錄製長度上限</span><span class="sxs-lookup"><span data-stu-id="a6a91-208">Maximum recording length</span></span>

<span data-ttu-id="a6a91-209">在 Windows 全像攝影之前，在 HoloLens 2 裝置上，錄製于裝置上的版本 20H2 影片限制為長度上限為 5 分鐘。</span><span class="sxs-lookup"><span data-stu-id="a6a91-209">On HoloLens 2 devices before the Windows Holographic, version 20H2 videos recorded on the device were limited to maximum length of five minutes.</span></span>

<span data-ttu-id="a6a91-210">由於客戶的意見回饋，我們已增加混合實境捕獲 [的錄製長度](holographic-photos-and-videos.md)。</span><span class="sxs-lookup"><span data-stu-id="a6a91-210">Due to customer feedback we’ve increased the recording length of [mixed reality captures](holographic-photos-and-videos.md).</span></span> <span data-ttu-id="a6a91-211">根據預設，混合實境捕獲將不再限制為 5 分鐘，而是會根據可用的磁碟空間來計算最大錄製長度。</span><span class="sxs-lookup"><span data-stu-id="a6a91-211">Mixed reality captures will no longer be limited to 5 minutes by default but instead will calculate the maximum recording length based on available disk space.</span></span> <span data-ttu-id="a6a91-212">裝置會根據可用磁碟空間預估最大視音訊錄製持續時間，最多占總磁碟空間的 80%。</span><span class="sxs-lookup"><span data-stu-id="a6a91-212">The device will estimate the max video recording duration based on available disk space up to 80% of the total disk space.</span></span>

> [!NOTE]
> <span data-ttu-id="a6a91-213">如果發生下列其中一個 (，HoloLens) 5 分鐘：</span><span class="sxs-lookup"><span data-stu-id="a6a91-213">The HoloLens will use default video recording length (5 minutes) if one of the following occurs:</span></span>
> - <span data-ttu-id="a6a91-214">估計的最大錄製持續時間小於預設的 5 分鐘。</span><span class="sxs-lookup"><span data-stu-id="a6a91-214">The estimated max recording duration is smaller than the default 5 mins.</span></span>
> - <span data-ttu-id="a6a91-215">可用磁碟空間小於總磁碟空間的 20%。</span><span class="sxs-lookup"><span data-stu-id="a6a91-215">The available disk space is less than 20% of the total disk space.</span></span>

## <a name="default-file-format-and-resolution"></a><span data-ttu-id="a6a91-216">預設檔案格式和解析度</span><span class="sxs-lookup"><span data-stu-id="a6a91-216">Default file format and resolution</span></span>

### <a name="default-photo-format-and-resolution"></a><span data-ttu-id="a6a91-217">預設相片格式和解析度</span><span class="sxs-lookup"><span data-stu-id="a6a91-217">Default photo format and resolution</span></span>

|  <span data-ttu-id="a6a91-218">裝置</span><span class="sxs-lookup"><span data-stu-id="a6a91-218">Device</span></span>  |  <span data-ttu-id="a6a91-219">格式</span><span class="sxs-lookup"><span data-stu-id="a6a91-219">Format</span></span>  |  <span data-ttu-id="a6a91-220">擴充功能</span><span class="sxs-lookup"><span data-stu-id="a6a91-220">Extension</span></span>  |  <span data-ttu-id="a6a91-221">解決方法</span><span class="sxs-lookup"><span data-stu-id="a6a91-221">Resolution</span></span>  |
|----------|----------|----------|----------|
| <span data-ttu-id="a6a91-222">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="a6a91-222">HoloLens 2</span></span> | [<span data-ttu-id="a6a91-223">JPEG</span><span class="sxs-lookup"><span data-stu-id="a6a91-223">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="a6a91-224">.jpg</span><span class="sxs-lookup"><span data-stu-id="a6a91-224">.jpg</span></span> | <span data-ttu-id="a6a91-225">3904x2196px</span><span class="sxs-lookup"><span data-stu-id="a6a91-225">3904x2196px</span></span> |
| <span data-ttu-id="a6a91-226">HoloLens (第一代) </span><span class="sxs-lookup"><span data-stu-id="a6a91-226">HoloLens (1st gen)</span></span> | [<span data-ttu-id="a6a91-227">JPEG</span><span class="sxs-lookup"><span data-stu-id="a6a91-227">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="a6a91-228">.jpg</span><span class="sxs-lookup"><span data-stu-id="a6a91-228">.jpg</span></span> | <span data-ttu-id="a6a91-229">1408x792px</span><span class="sxs-lookup"><span data-stu-id="a6a91-229">1408x792px</span></span> |

### <a name="recorded-video-format-and-resolution"></a><span data-ttu-id="a6a91-230">錄製的視視格式和解析度</span><span class="sxs-lookup"><span data-stu-id="a6a91-230">Recorded video format and resolution</span></span>

| <span data-ttu-id="a6a91-231">裝置</span><span class="sxs-lookup"><span data-stu-id="a6a91-231">Device</span></span> | <span data-ttu-id="a6a91-232">格式</span><span class="sxs-lookup"><span data-stu-id="a6a91-232">Format</span></span> | <span data-ttu-id="a6a91-233">擴充功能</span><span class="sxs-lookup"><span data-stu-id="a6a91-233">Extension</span></span> | <span data-ttu-id="a6a91-234">解決方法</span><span class="sxs-lookup"><span data-stu-id="a6a91-234">Resolution</span></span> | <span data-ttu-id="a6a91-235">速度</span><span class="sxs-lookup"><span data-stu-id="a6a91-235">Speed</span></span> | <span data-ttu-id="a6a91-236">音效</span><span class="sxs-lookup"><span data-stu-id="a6a91-236">Audio</span></span> |
|----------|----------|----------|----------|----------|----------|
| <span data-ttu-id="a6a91-237">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="a6a91-237">HoloLens 2</span></span> | [<span data-ttu-id="a6a91-238">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="a6a91-238">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="a6a91-239">.mp4</span><span class="sxs-lookup"><span data-stu-id="a6a91-239">.mp4</span></span> | <span data-ttu-id="a6a91-240">1920x1080px</span><span class="sxs-lookup"><span data-stu-id="a6a91-240">1920x1080px</span></span> | <span data-ttu-id="a6a91-241">30fps</span><span class="sxs-lookup"><span data-stu-id="a6a91-241">30fps</span></span> | <span data-ttu-id="a6a91-242">48kHz 身歷聲</span><span class="sxs-lookup"><span data-stu-id="a6a91-242">48kHz Stereo</span></span> |
| <span data-ttu-id="a6a91-243">HoloLens (第一代) </span><span class="sxs-lookup"><span data-stu-id="a6a91-243">HoloLens (1st gen)</span></span> |  [<span data-ttu-id="a6a91-244">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="a6a91-244">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="a6a91-245">.mp4</span><span class="sxs-lookup"><span data-stu-id="a6a91-245">.mp4</span></span> | <span data-ttu-id="a6a91-246">1216x684px</span><span class="sxs-lookup"><span data-stu-id="a6a91-246">1216x684px</span></span> | <span data-ttu-id="a6a91-247">24fps</span><span class="sxs-lookup"><span data-stu-id="a6a91-247">24fps</span></span> | <span data-ttu-id="a6a91-248">48kHz 身歷聲</span><span class="sxs-lookup"><span data-stu-id="a6a91-248">48kHz Stereo</span></span> |
