---
title: HoloLens 裝置和全像影像的常見問題
description: 您是否有關于 HoloLens 的快速問題或與全像的互動？  本文提供快速解答和更多資源。
keywords: hololens、常見問題、已知問題、協助
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ae44ae1d9a2e088a1ef746f4e929e8fae73880bf
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924021"
---
# <a name="holograms-and-interactions-troubleshooting"></a><span data-ttu-id="82fc7-105">全像影像和互動疑難排解</span><span class="sxs-lookup"><span data-stu-id="82fc7-105">Holograms and interactions troubleshooting</span></span>

<span data-ttu-id="82fc7-106">這篇文章會針對放置全像空間、使用空間以及回報全息文問題的問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="82fc7-106">This article troubleshoots issues with placing holograms, working with spaces, and reporting issues with holograms.</span></span>

<span data-ttu-id="82fc7-107">每當您遇到問題時，請務必：</span><span class="sxs-lookup"><span data-stu-id="82fc7-107">Anytime that you have problems, make sure:</span></span>
- <span data-ttu-id="82fc7-108">請嘗試將 [它重新開機](hololens-restart-recover.md) ，以查看是否能修正問題。</span><span class="sxs-lookup"><span data-stu-id="82fc7-108">Try [restarting it](hololens-restart-recover.md) to see whether that fixes things.</span></span>
- <span data-ttu-id="82fc7-109">進行疑難排解之前，請確定 HoloLens 的 [計費](hololens2-charging.md) (至少) 一小時的費用。</span><span class="sxs-lookup"><span data-stu-id="82fc7-109">Before troubleshooting, ensure the HoloLens is [charged up](hololens2-charging.md) (charged for at least an hour).</span></span> 


<span data-ttu-id="82fc7-110">請使用意見反應應用程式將問題的相關資訊傳送給我們。</span><span class="sxs-lookup"><span data-stu-id="82fc7-110">Please use the Feedback app to send us information about the issue.</span></span> <span data-ttu-id="82fc7-111">您會在 [ [**開始** ] 功能表](holographic-home.md)上找到意見反應應用程式。</span><span class="sxs-lookup"><span data-stu-id="82fc7-111">You'll find the Feedback app on the [**Start** menu](holographic-home.md).</span></span> 

<span data-ttu-id="82fc7-112">如需有關如何磨損 HoloLens 的秘訣，請參閱 [調整大小](hololens2-setup.md#adjust-fit)。</span><span class="sxs-lookup"><span data-stu-id="82fc7-112">For tips about how to wear your HoloLens, see [Adjust Fit](hololens2-setup.md#adjust-fit).</span></span>

<a id="list"></a>
- [<span data-ttu-id="82fc7-113">無法建立新的空格</span><span class="sxs-lookup"><span data-stu-id="82fc7-113">New spaces can't be created</span></span>](#new-spaces-cant-be-created)
- [<span data-ttu-id="82fc7-114">無法識別或載入空格</span><span class="sxs-lookup"><span data-stu-id="82fc7-114">Spaces can't be identified or loaded</span></span>](#spaces-cant-be-identified-or-loaded)
- [<span data-ttu-id="82fc7-115">如何? 刪除所有空格？</span><span class="sxs-lookup"><span data-stu-id="82fc7-115">How do I delete all spaces?</span></span>](#how-do-i-delete-all-spaces)
- [<span data-ttu-id="82fc7-116">全像全像</span><span class="sxs-lookup"><span data-stu-id="82fc7-116">Holograms don't look right or are moving around</span></span>](#holograms-dont-look-right-or-are-moving-around)
- [<span data-ttu-id="82fc7-117">「尋找您的空間」訊息</span><span class="sxs-lookup"><span data-stu-id="82fc7-117">"Finding your space" message</span></span>](#finding-your-space-message)
- [<span data-ttu-id="82fc7-118">我的空間中未顯示預期的全像影像</span><span class="sxs-lookup"><span data-stu-id="82fc7-118">Expected holograms aren't showing in my space</span></span>](#expected-holograms-arent-showing-in-my-space)
- [<span data-ttu-id="82fc7-119">無法放置全像影像，或看過先前放置的全像投影</span><span class="sxs-lookup"><span data-stu-id="82fc7-119">Can't place holograms or see previously placed holograms</span></span>](#cant-place-holograms-or-see-previously-placed-holograms)
- [<span data-ttu-id="82fc7-120">全像是 encased 在其他的全像投影或物件中</span><span class="sxs-lookup"><span data-stu-id="82fc7-120">Holograms disappear or are encased in other holograms or objects</span></span>](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [<span data-ttu-id="82fc7-121">在牆的另一端顯示全像影像</span><span class="sxs-lookup"><span data-stu-id="82fc7-121">Holograms are appearing on the other side of a wall</span></span>](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [<span data-ttu-id="82fc7-122">在牆上放置全息圖之後，似乎是 float</span><span class="sxs-lookup"><span data-stu-id="82fc7-122">After placing a hologram on a wall, it seems to float</span></span>](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [<span data-ttu-id="82fc7-123">應用程式移動後顯示太接近</span><span class="sxs-lookup"><span data-stu-id="82fc7-123">Apps appear too close after moving them</span></span>](#apps-appear-too-close-after-moving-them)
- [<span data-ttu-id="82fc7-124">報告不穩定或不精確的全像投影問題</span><span class="sxs-lookup"><span data-stu-id="82fc7-124">Reporting issues with unstable or inexact holograms</span></span>](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a><span data-ttu-id="82fc7-125">無法建立新的空格</span><span class="sxs-lookup"><span data-stu-id="82fc7-125">New spaces can't be created</span></span>

<span data-ttu-id="82fc7-126">最可能的問題是您的儲存空間不足。</span><span class="sxs-lookup"><span data-stu-id="82fc7-126">The most likely problem is that you're running low on storage space.</span></span> <span data-ttu-id="82fc7-127">請[釋放一些磁碟空間](hololens-troubleshooting.md#low-disk-space-error)，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="82fc7-127">[Free up some disk space](hololens-troubleshooting.md#low-disk-space-error) and then retry.</span></span>

[<span data-ttu-id="82fc7-128">返回清單</span><span class="sxs-lookup"><span data-stu-id="82fc7-128">Back to list</span></span>](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a><span data-ttu-id="82fc7-129">無法識別或載入空格</span><span class="sxs-lookup"><span data-stu-id="82fc7-129">Spaces can't be identified or loaded</span></span>

<span data-ttu-id="82fc7-130">如果您的 HoloLens 無法識別和載入您所要自動的空間，請檢查下列因素：</span><span class="sxs-lookup"><span data-stu-id="82fc7-130">If your HoloLens can't identify and load the space you're in automatically, check the following factors:</span></span>

- <span data-ttu-id="82fc7-131">請確定您已連線到 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="82fc7-131">Make sure that you're connected to Wi-Fi</span></span>
- <span data-ttu-id="82fc7-132">請確定空間中有很多光線</span><span class="sxs-lookup"><span data-stu-id="82fc7-132">Make sure that there's plenty of light in the room</span></span>
- <span data-ttu-id="82fc7-133">請確定周圍沒有任何重大變更。</span><span class="sxs-lookup"><span data-stu-id="82fc7-133">Make sure that there haven't been any major changes to the surroundings.</span></span>

<span data-ttu-id="82fc7-134">您也可以手動載入空格，或前往 [**設定**  >  **系統**  >  **空間**] 來管理您的空間。</span><span class="sxs-lookup"><span data-stu-id="82fc7-134">You can also load a space manually or manage your spaces by going to **Settings** > **System** > **Spaces**.</span></span>

[<span data-ttu-id="82fc7-135">返回清單</span><span class="sxs-lookup"><span data-stu-id="82fc7-135">Back to list</span></span>](#list)

## <a name="how-do-i-delete-all-spaces"></a><span data-ttu-id="82fc7-136">如何? 刪除所有空格？</span><span class="sxs-lookup"><span data-stu-id="82fc7-136">How do I delete all spaces?</span></span>

<span data-ttu-id="82fc7-137">*即將推出*</span><span class="sxs-lookup"><span data-stu-id="82fc7-137">*Coming soon*</span></span>

[<span data-ttu-id="82fc7-138">返回清單</span><span class="sxs-lookup"><span data-stu-id="82fc7-138">Back to list</span></span>](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a><span data-ttu-id="82fc7-139">全像全像</span><span class="sxs-lookup"><span data-stu-id="82fc7-139">Holograms don't look right or are moving around</span></span>

<span data-ttu-id="82fc7-140">如果您的全像是看起來不正確 (例如，它們會抖動或晃動，或是您在上面看到黑色修補程式) ，請嘗試下列其中一個修正：</span><span class="sxs-lookup"><span data-stu-id="82fc7-140">If your holograms don't look right (for example, they're jittery or shaky, or you see black patches on top of them), try one of these fixes:</span></span>

- <span data-ttu-id="82fc7-141">[清除您的裝置面板](hololens1-hardware.md#care-and-cleaning) ，並確定沒有任何專案封鎖感應器。</span><span class="sxs-lookup"><span data-stu-id="82fc7-141">[Clean your device visor](hololens1-hardware.md#care-and-cleaning) and make sure nothing is blocking the sensors.</span></span>
- <span data-ttu-id="82fc7-142">請確定您是在沒有大量直接日光的知名房間內。</span><span class="sxs-lookup"><span data-stu-id="82fc7-142">Make sure that you're in a well-lit room that does not have a lot of direct sunlight.</span></span>
- <span data-ttu-id="82fc7-143">試著在您的環境中撥雲見日，讓 HoloLens 可以更完整地掃描。</span><span class="sxs-lookup"><span data-stu-id="82fc7-143">Try walking around and gazing at your surroundings so that HoloLens can scan them more completely.</span></span>
- <span data-ttu-id="82fc7-144">如果您已放入大量的全像投影，請嘗試移除一些。</span><span class="sxs-lookup"><span data-stu-id="82fc7-144">If you've placed a lot of holograms, try removing some.</span></span>

<span data-ttu-id="82fc7-145">如果您仍遇到問題，請嘗試執行校正應用程式。</span><span class="sxs-lookup"><span data-stu-id="82fc7-145">If you're still having problems, trying running the Calibration app.</span></span> <span data-ttu-id="82fc7-146">此應用程式會校正您的 HoloLens，以協助讓您的全像投影更加完美。</span><span class="sxs-lookup"><span data-stu-id="82fc7-146">This app calibrates your HoloLens just for you to help keep your holograms looking their best.</span></span> <span data-ttu-id="82fc7-147">若要這樣做，請移至 [**設定**  >  **系統**  >  **公用程式**]。</span><span class="sxs-lookup"><span data-stu-id="82fc7-147">To do this, go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="82fc7-148">在 [ **校正**] 下，選取 [ **開啟校正**]。</span><span class="sxs-lookup"><span data-stu-id="82fc7-148">Under **Calibration**, select **Open Calibration**.</span></span>

[<span data-ttu-id="82fc7-149">返回清單</span><span class="sxs-lookup"><span data-stu-id="82fc7-149">Back to list</span></span>](#list)

## <a name="finding-your-space-message"></a><span data-ttu-id="82fc7-150">「尋找您的空間」訊息</span><span class="sxs-lookup"><span data-stu-id="82fc7-150">"Finding your space" message</span></span>

<span data-ttu-id="82fc7-151">當 HoloLens 正在學習或載入空間時，您可能會看到簡短的訊息，指出「找出您的空間」。</span><span class="sxs-lookup"><span data-stu-id="82fc7-151">When HoloLens is learning or loading a space, you may see a brief message that says "Finding your space."</span></span> <span data-ttu-id="82fc7-152">如果這則訊息顯示超過幾秒鐘，您會在 [開始] 功能表下看到另一則訊息，指出「仍在尋找您的空間」。</span><span class="sxs-lookup"><span data-stu-id="82fc7-152">If this message displays for more than a few seconds, you'll see another message under the Start menu that says "Still looking for your space."</span></span>

<span data-ttu-id="82fc7-153">這些訊息表示 HoloLens 在對應您的空間時遇到問題。</span><span class="sxs-lookup"><span data-stu-id="82fc7-153">These messages mean that HoloLens is having trouble mapping your space.</span></span> <span data-ttu-id="82fc7-154">當發生這種情況時，您可以開啟應用程式，但無法在您的環境中放置全像影像。</span><span class="sxs-lookup"><span data-stu-id="82fc7-154">When this happens, you can open apps, but you can't place holograms in your environment.</span></span>

<span data-ttu-id="82fc7-155">如果您經常看到這些訊息，請嘗試下列一或多個修正：</span><span class="sxs-lookup"><span data-stu-id="82fc7-155">If you see these messages often, try one or more of the following fixes:</span></span>

- <span data-ttu-id="82fc7-156">請確定您是在沒有大量直接日光的知名房間內。</span><span class="sxs-lookup"><span data-stu-id="82fc7-156">Make sure that you're in a well-lit room that does not have a lot of direct sunlight.</span></span>
- <span data-ttu-id="82fc7-157">請確定您的裝置面板已清除。</span><span class="sxs-lookup"><span data-stu-id="82fc7-157">Make sure that your device visor is clean.</span></span> <span data-ttu-id="82fc7-158">[瞭解如何清理您的面板](hololens1-hardware.md#care-and-cleaning)。</span><span class="sxs-lookup"><span data-stu-id="82fc7-158">[Learn how to clean your visor](hololens1-hardware.md#care-and-cleaning).</span></span>
- <span data-ttu-id="82fc7-159">請確定您有強式 Wi-Fi 信號。</span><span class="sxs-lookup"><span data-stu-id="82fc7-159">Make sure that you have a strong Wi-Fi signal.</span></span> <span data-ttu-id="82fc7-160">如果您輸入的新環境沒有 Wi-Fi 或弱 Wi-Fi 信號，HoloLens 將無法找到您的空間。</span><span class="sxs-lookup"><span data-stu-id="82fc7-160">If you enter a new environment that has no Wi-Fi or a weak Wi-Fi signal, HoloLens won't be able find your space.</span></span> <span data-ttu-id="82fc7-161">前往 [**設定**  >  **網路 &amp; 網際網路**  >  **wi-fi**]，檢查您的 Wi-Fi 連接。</span><span class="sxs-lookup"><span data-stu-id="82fc7-161">Check your Wi-Fi connection by going to **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span>
- <span data-ttu-id="82fc7-162">請嘗試移動更慢的速度。</span><span class="sxs-lookup"><span data-stu-id="82fc7-162">Try moving more slowly.</span></span>

[<span data-ttu-id="82fc7-163">返回清單</span><span class="sxs-lookup"><span data-stu-id="82fc7-163">Back to list</span></span>](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a><span data-ttu-id="82fc7-164">我的空間中未顯示預期的全像影像</span><span class="sxs-lookup"><span data-stu-id="82fc7-164">Expected holograms aren't showing in my space</span></span>

<span data-ttu-id="82fc7-165">如果您看不到您所放置的全像影像，或您看到的部分未預期，請嘗試下列一或多個修正：</span><span class="sxs-lookup"><span data-stu-id="82fc7-165">If you don't see the holograms that you placed, or if you're seeing some that you don't expect, try one or more of the following fixes:</span></span>

- <span data-ttu-id="82fc7-166">開啟一些燈。</span><span class="sxs-lookup"><span data-stu-id="82fc7-166">Turn on some lights.</span></span> <span data-ttu-id="82fc7-167">HoloLens 最適合用在妥善的空間中。</span><span class="sxs-lookup"><span data-stu-id="82fc7-167">HoloLens works best in a well-lit space.</span></span>
- <span data-ttu-id="82fc7-168">移至 [**設定** 系統全像投影]，以移除您不需要的全像全像的全像影像  >    >    >  \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="82fc7-168">Remove holograms that you don't need by going to **Settings** > **System** > **Holograms** > **Remove nearby holograms**.</span></span> <span data-ttu-id="82fc7-169">或者，若有需要，請選取 [ **移除所有的全** 像]。</span><span class="sxs-lookup"><span data-stu-id="82fc7-169">Or, if needed, select **Remove all holograms**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="82fc7-170">如果您空間中的版面配置或光線大幅變更，您的裝置可能會無法識別您的空間並顯示您的全像影像。</span><span class="sxs-lookup"><span data-stu-id="82fc7-170">If the layout or lighting in your space changes significantly, your device might have trouble identifying your space and showing your holograms.</span></span>

[<span data-ttu-id="82fc7-171">返回清單</span><span class="sxs-lookup"><span data-stu-id="82fc7-171">Back to list</span></span>](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a><span data-ttu-id="82fc7-172">無法放置全像影像，或看過先前放置的全像投影</span><span class="sxs-lookup"><span data-stu-id="82fc7-172">Can't place holograms or see previously placed holograms</span></span>

<span data-ttu-id="82fc7-173">如果 HoloLens 無法對應或載入您的空間，則會進入有限的模式，而且您將無法放置全像影像或查看您所放置的全像全像。</span><span class="sxs-lookup"><span data-stu-id="82fc7-173">If HoloLens can't map or load your space, it enters Limited mode and you won't be able to place holograms or see holograms that you've placed.</span></span> <span data-ttu-id="82fc7-174">您可以嘗試以下方法：</span><span class="sxs-lookup"><span data-stu-id="82fc7-174">Here are some things to try:</span></span>

- <span data-ttu-id="82fc7-175">請確定您的環境中有足夠的光線，讓 HoloLens 可以看到並對應空間。</span><span class="sxs-lookup"><span data-stu-id="82fc7-175">Make sure that there's enough light in your environment so HoloLens can see and map the space.</span></span>
- <span data-ttu-id="82fc7-176">從您嘗試放置全像位置的一到三個計量。</span><span class="sxs-lookup"><span data-stu-id="82fc7-176">Stand between one and three meters from where you're trying to place the hologram.</span></span>
- <span data-ttu-id="82fc7-177">請勿在黑色或反射表面上放置全像影像。</span><span class="sxs-lookup"><span data-stu-id="82fc7-177">Don't place holograms on black or reflective surfaces.</span></span>
- <span data-ttu-id="82fc7-178">請確定您已連線到 Wi-Fi 網路。</span><span class="sxs-lookup"><span data-stu-id="82fc7-178">Make sure that you're connected to a Wi-Fi network.</span></span> <span data-ttu-id="82fc7-179">如果您未連線到 Wi-fi，HoloLens 就無法識別並載入已知的空間。</span><span class="sxs-lookup"><span data-stu-id="82fc7-179">If you're not connected to Wi-Fi, HoloLens can't identify and load a known space.</span></span>
- <span data-ttu-id="82fc7-180">您可以四處解說房間，讓 HoloLens 可以重新掃描您的環境。</span><span class="sxs-lookup"><span data-stu-id="82fc7-180">Walk around the rooms so HoloLens can rescan your surroundings.</span></span> <span data-ttu-id="82fc7-181">若要查看已掃描的內容，請按一下以顯示地圖網格圖形。</span><span class="sxs-lookup"><span data-stu-id="82fc7-181">To see what's already been scanned, air tap to reveal the mapping mesh graphic.</span></span>
- <span data-ttu-id="82fc7-182">如果您需要建立新的空間，請連接到 Wi-fi，然後重新開機 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="82fc7-182">If you need to create a new space, connect to Wi-Fi, then restart your HoloLens.</span></span>
- <span data-ttu-id="82fc7-183">若要查看正確的空間是否為作用中，或要手動載入空格，請移至 [**設定**  >  **系統**  >  **空間**]。</span><span class="sxs-lookup"><span data-stu-id="82fc7-183">To see if the correct space is active, or to manually load a space, go to **Settings** > **System** > **Spaces**.</span></span>
- <span data-ttu-id="82fc7-184">如果載入正確的空間，但您仍遇到問題，空間可能已損毀。</span><span class="sxs-lookup"><span data-stu-id="82fc7-184">If the correct space is loaded and you're still having problems, the space may be corrupt.</span></span> <span data-ttu-id="82fc7-185">若要修正此問題，請選取 [空間]，然後選取 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="82fc7-185">To fix this issue, select the space, then select **Remove**.</span></span> <span data-ttu-id="82fc7-186">移除空間之後，HoloLens 會開始對應您的環境，並建立新的空間。</span><span class="sxs-lookup"><span data-stu-id="82fc7-186">After you remove the space, HoloLens starts to map your surroundings and create a new space.</span></span>

[<span data-ttu-id="82fc7-187">返回清單</span><span class="sxs-lookup"><span data-stu-id="82fc7-187">Back to list</span></span>](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a><span data-ttu-id="82fc7-188">全像是 encased 在其他的全像投影或物件中</span><span class="sxs-lookup"><span data-stu-id="82fc7-188">Holograms disappear or are encased in other holograms or objects</span></span>

<span data-ttu-id="82fc7-189">如果您太接近了全息圖，它會暫時消失， &mdash; 以還原全像移動。</span><span class="sxs-lookup"><span data-stu-id="82fc7-189">If you get too close to a hologram, it will temporarily disappear&mdash;to restore the hologram, just move away from it.</span></span> <span data-ttu-id="82fc7-190">此外，如果您將數個全息合在一起，有些可能會消失。</span><span class="sxs-lookup"><span data-stu-id="82fc7-190">Also, if you've placed several holograms close together, some may disappear.</span></span> <span data-ttu-id="82fc7-191">請嘗試移除一些。</span><span class="sxs-lookup"><span data-stu-id="82fc7-191">Try removing a few.</span></span>

<span data-ttu-id="82fc7-192">您也可以透過其他的全像或牆壁等物件來封鎖或 encased 全像影像。</span><span class="sxs-lookup"><span data-stu-id="82fc7-192">Holograms can also be blocked or encased by other holograms or by objects such as walls.</span></span> <span data-ttu-id="82fc7-193">如果發生這種情況，請嘗試下列其中一個修正：</span><span class="sxs-lookup"><span data-stu-id="82fc7-193">If this happens, try one of the following fixes:</span></span>

- <span data-ttu-id="82fc7-194">如果 encased 在另一個全息圖中，請將 encased 的全息圖移至另一個位置。</span><span class="sxs-lookup"><span data-stu-id="82fc7-194">If the hologram is encased in another hologram, move the encased hologram to another location.</span></span> <span data-ttu-id="82fc7-195">若要這樣做，請選取 [ **調整**]，然後按住以定位。</span><span class="sxs-lookup"><span data-stu-id="82fc7-195">To do this, select **Adjust**, then tap and hold to position it.</span></span>
- <span data-ttu-id="82fc7-196">如果在牆中 encased 了全息圖，請選取 [ **調整**]，然後向下流覽至牆上，直到出現全像影像為止。</span><span class="sxs-lookup"><span data-stu-id="82fc7-196">If the hologram is encased in a wall, select **Adjust**, then walk toward the wall until the hologram appears.</span></span> <span data-ttu-id="82fc7-197">按住並按住，然後從牆上向前和向外拉出全像影像。</span><span class="sxs-lookup"><span data-stu-id="82fc7-197">Tap and hold, then pull the hologram forward and out of the wall.</span></span>
- <span data-ttu-id="82fc7-198">如果您無法使用手勢來移動全息圖，請使用您的聲音將它移除。</span><span class="sxs-lookup"><span data-stu-id="82fc7-198">If you can't move the hologram by using gestures, use your voice to remove it.</span></span> <span data-ttu-id="82fc7-199">看一下全像影像，然後說「移除」。</span><span class="sxs-lookup"><span data-stu-id="82fc7-199">Gaze at the hologram, then say "Remove."</span></span> <span data-ttu-id="82fc7-200">然後重新開啟全息圖，並將它放在新的位置。</span><span class="sxs-lookup"><span data-stu-id="82fc7-200">Then reopen the hologram and place it in a new location.</span></span>

[<span data-ttu-id="82fc7-201">返回清單</span><span class="sxs-lookup"><span data-stu-id="82fc7-201">Back to list</span></span>](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a><span data-ttu-id="82fc7-202">在牆的另一端顯示全像影像</span><span class="sxs-lookup"><span data-stu-id="82fc7-202">Holograms are appearing on the other side of a wall</span></span>

<span data-ttu-id="82fc7-203">如果您很接近牆，或 HoloLens 尚未掃描牆，您可以看到下個房間的全像投影。</span><span class="sxs-lookup"><span data-stu-id="82fc7-203">If you're very close to a wall, or if HoloLens hasn't scanned the wall yet, you can see holograms that are in the next room.</span></span> <span data-ttu-id="82fc7-204">若要掃描牆，請從牆中離開一到三個計量，然後看看它。</span><span class="sxs-lookup"><span data-stu-id="82fc7-204">To scan the wall, stand between one and three meters from the wall and gaze at it.</span></span>

<span data-ttu-id="82fc7-205">黑色或反光的物件 (例如，黑色沙發或附近的 stainless 鋼冰箱) 可能會在 HoloLens 嘗試掃描牆壁時發生問題。</span><span class="sxs-lookup"><span data-stu-id="82fc7-205">A black or reflective object (for example, a black couch or a stainless steel refrigerator) near the wall may cause problems when HoloLens tries to scan the wall.</span></span> <span data-ttu-id="82fc7-206">如果有這類物件，請掃描牆的另一端。</span><span class="sxs-lookup"><span data-stu-id="82fc7-206">If there is such an object, scan the other side of the wall.</span></span>

[<span data-ttu-id="82fc7-207">返回清單</span><span class="sxs-lookup"><span data-stu-id="82fc7-207">Back to list</span></span>](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a><span data-ttu-id="82fc7-208">在牆上放置全息圖之後，似乎是 float</span><span class="sxs-lookup"><span data-stu-id="82fc7-208">After placing a hologram on a wall, it seems to float</span></span>

<span data-ttu-id="82fc7-209">您放置在牆上的全像影像，通常會顯示為一英寸或遠離牆。</span><span class="sxs-lookup"><span data-stu-id="82fc7-209">A hologram that you place on a wall typically appears to be an inch or so away from the wall.</span></span> <span data-ttu-id="82fc7-210">如果看起來更遠，請嘗試下列一或多個修正：</span><span class="sxs-lookup"><span data-stu-id="82fc7-210">If it appears to be farther away, try one or more of the following fixes:</span></span>

- <span data-ttu-id="82fc7-211">當您在牆上放置全像投影時，請從牆上的一到三個計量表，並直接朝上臉部。</span><span class="sxs-lookup"><span data-stu-id="82fc7-211">When you place a hologram on a wall, stand between one and three meters from the wall and face the wall straight on.</span></span>
- <span data-ttu-id="82fc7-212">按一下牆以顯示地圖網格圖形。</span><span class="sxs-lookup"><span data-stu-id="82fc7-212">Air tap the wall to reveal the mapping mesh graphic.</span></span> <span data-ttu-id="82fc7-213">請確定網格與牆對齊。</span><span class="sxs-lookup"><span data-stu-id="82fc7-213">Make sure that the mesh aligns with the wall.</span></span> <span data-ttu-id="82fc7-214">如果不是，請移除全像影像、重新掃描牆，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="82fc7-214">If it doesn't, remove the hologram, rescan the wall, and then try again.</span></span>
- <span data-ttu-id="82fc7-215">如果問題持續發生，請執行校正應用程式。</span><span class="sxs-lookup"><span data-stu-id="82fc7-215">If the issue persists, run the Calibration app.</span></span> <span data-ttu-id="82fc7-216">您可以在 **設定**  >  **系統**  >  **公用程式** 中找到它。</span><span class="sxs-lookup"><span data-stu-id="82fc7-216">You'll find it in **Settings** > **System** > **Utilities**.</span></span>

[<span data-ttu-id="82fc7-217">返回清單</span><span class="sxs-lookup"><span data-stu-id="82fc7-217">Back to list</span></span>](#list)

## <a name="apps-appear-too-close-after-moving-them"></a><span data-ttu-id="82fc7-218">應用程式移動後顯示太接近</span><span class="sxs-lookup"><span data-stu-id="82fc7-218">Apps appear too close after moving them</span></span>

<span data-ttu-id="82fc7-219">請試著流覽並查看您要放置應用程式的區域，讓 HoloLens 從不同的角度掃描區域。</span><span class="sxs-lookup"><span data-stu-id="82fc7-219">Try walking around and looking at the area where you're placing the app so that HoloLens scans the area from different angles.</span></span> <span data-ttu-id="82fc7-220">[清除您的裝置面板](hololens1-hardware.md#care-and-cleaning) 也可能有所説明。</span><span class="sxs-lookup"><span data-stu-id="82fc7-220">[Cleaning your device visor](hololens1-hardware.md#care-and-cleaning) may also help.</span></span>

[<span data-ttu-id="82fc7-221">返回清單</span><span class="sxs-lookup"><span data-stu-id="82fc7-221">Back to list</span></span>](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a><span data-ttu-id="82fc7-222">報告不穩定或不精確的全像投影問題</span><span class="sxs-lookup"><span data-stu-id="82fc7-222">Reporting issues with unstable or inexact holograms</span></span>
 
1. <span data-ttu-id="82fc7-223">請記錄並混合實境擷取問題的 [影片](holographic-photos-and-videos.md#capture-a-mixed-reality-video) 。</span><span class="sxs-lookup"><span data-stu-id="82fc7-223">Please record and a [Mixed Reality Capture video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) of the issue.</span></span> <span data-ttu-id="82fc7-224">這段影片稍後可以透過意見反應中樞上傳至附加的檔案。</span><span class="sxs-lookup"><span data-stu-id="82fc7-224">This video can be later uploaded through Feedback Hub as an attached file.</span></span>  
1. <span data-ttu-id="82fc7-225">透過 [**設定**] 應用程式啟用完整遙測->**隱私權**  ->  **診斷 & 意見** 反應，並在 **選擇性診斷資料** 下，確定切換開關設定為 [**開啟**]</span><span class="sxs-lookup"><span data-stu-id="82fc7-225">Enable full telemetry via the **Settings** app -> **Privacy** -> **Diagnostics & feedback** and under **Optional diagnostics data** ensure the toggle is set to **On**</span></span>
1. <span data-ttu-id="82fc7-226">藉由更新至最新的 Windows 全像 [作業系統， (20H2 或更高的) ， ](hololens-release-notes.md#windows-holographic-version-20h2)取得最新的全像全像調整和穩定性。</span><span class="sxs-lookup"><span data-stu-id="82fc7-226">Get the latest hologram scale and stability fixes by updating to the latest [Windows Holographic OS, (20H2 or higher)](hololens-release-notes.md#windows-holographic-version-20h2).</span></span> <span data-ttu-id="82fc7-227">更新之後，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="82fc7-227">After updating perform the following:</span></span>
    1. <span data-ttu-id="82fc7-228">透過 [**設定**] 應用程式移除所有的全像/>**系統**  ->  **全像**> 然後選取 [**移除所有的全** 像]，然後以全新的地圖開始。</span><span class="sxs-lookup"><span data-stu-id="82fc7-228">Remove all Holograms via **Settings** app -> **System** -> **Holograms** -> then select **Remove all holograms** and start with a fresh map.</span></span>
    1. <span data-ttu-id="82fc7-229">在您的房間周圍接住 HoloLens，並查看空間中的所有區域和表面，以建立新的空間地圖。</span><span class="sxs-lookup"><span data-stu-id="82fc7-229">Create a new map of your space by wearing the HoloLens and walking around your room and looking at all areas and surfaces in the space.</span></span> <span data-ttu-id="82fc7-230">請在2-3 分鐘內進行此作業。</span><span class="sxs-lookup"><span data-stu-id="82fc7-230">Do this for 2-3 minutes.</span></span>
    1. <span data-ttu-id="82fc7-231">執行 IPD 校正。</span><span class="sxs-lookup"><span data-stu-id="82fc7-231">Perform IPD calibration.</span></span> <span data-ttu-id="82fc7-232">移至 [**設定**  >  **系統**  >  **公用程式**]。</span><span class="sxs-lookup"><span data-stu-id="82fc7-232">Go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="82fc7-233">在 [ **校正**] 下，選取 [ **開啟校正**]。</span><span class="sxs-lookup"><span data-stu-id="82fc7-233">Under **Calibration**, select **Open Calibration**.</span></span>
    1. <span data-ttu-id="82fc7-234">重新測試案例，並查看它是否仍持續存在。</span><span class="sxs-lookup"><span data-stu-id="82fc7-234">Re-test the scenario and see if it still persists.</span></span>
1. <span data-ttu-id="82fc7-235">如果更新無法修正問題，請提出 [意見反應中樞問題](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="82fc7-235">If updating does not fix the issue, please file a [Feedback Hub issue](hololens-feedback.md).</span></span> <span data-ttu-id="82fc7-236">填寫意見反應之後，您可以使用 [ **共用** ] 按鈕來建立可在聯繫支援時傳送的簡易共用連結。</span><span class="sxs-lookup"><span data-stu-id="82fc7-236">After you've filled feedback you can use the **Share** button, to create an easy to share link that can be sent when contacting support.</span></span>

[<span data-ttu-id="82fc7-237">返回清單</span><span class="sxs-lookup"><span data-stu-id="82fc7-237">Back to list</span></span>](#list)