---
title: 使用您的聲音操作 HoloLens
description: Cortana 可以協助您在 HoloLens 上執行各式各樣的動作
ms.assetid: fd96fb0e-6759-4dbe-be1f-58bedad66fed
ms.date: 03/10/2020
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
audience: ITPro
ms.author: v-tea
ms.topic: article
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: d6fc83e81ce6f02047cff8a5d1944156f769e056
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828381"
---
# <span data-ttu-id="bfb67-104">使用您的聲音操作 HoloLens</span><span class="sxs-lookup"><span data-stu-id="bfb67-104">Use your voice to operate HoloLens</span></span>

<span data-ttu-id="bfb67-105">您可以使用語音，在 HoloLens 上執行幾乎任何動作，例如快速拍照或開啟應用程式。</span><span class="sxs-lookup"><span data-stu-id="bfb67-105">You can use your voice to do almost anything on HoloLens, such as taking a quick photo or opening an app.</span></span> <span data-ttu-id="bfb67-106">許多語音命令已內建於 HoloLens，而其他命令則可透過 Cortana 來提供。</span><span class="sxs-lookup"><span data-stu-id="bfb67-106">Many voice commands are built into HoloLens, while others are available through Cortana.</span></span>

<span data-ttu-id="bfb67-107">本文將告訴您如何使用語音和 Cortana 來控制 HoloLens 以及您的全息影像世界。</span><span class="sxs-lookup"><span data-stu-id="bfb67-107">This article teaches you how to control HoloLens and your holographic world with your voice and with Cortana.</span></span>

> [!NOTE]
> <span data-ttu-id="bfb67-108">只有[某些語言](hololens2-language-support.md)支援語音功能。</span><span class="sxs-lookup"><span data-stu-id="bfb67-108">Speech is only supported in [some languages](hololens2-language-support.md).</span></span> <span data-ttu-id="bfb67-109">對語音語言的支援，根據的是 Windows 顯示語言，而不是鍵盤語言。</span><span class="sxs-lookup"><span data-stu-id="bfb67-109">The speech language is based on the Windows display language, not the keyboard language.</span></span>  
>  
> <span data-ttu-id="bfb67-110">您可以選取**設定** > **時間與語言** > **語言**來確認 Windows 顯示語言。</span><span class="sxs-lookup"><span data-stu-id="bfb67-110">You can verify the Windows display language by selecting **Settings** > **Time and Language** > **Language**.</span></span>

## <span data-ttu-id="bfb67-111">內建語音命令</span><span class="sxs-lookup"><span data-stu-id="bfb67-111">Built-in voice commands</span></span>

<span data-ttu-id="bfb67-112">使用這些基本命令，更快速地操作 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="bfb67-112">Get around HoloLens faster with these basic commands.</span></span> <span data-ttu-id="bfb67-113">若要使用這些命令，您必須在初次執行裝置時，或是在 [設定]\*\*\*\*  >  [隱私權]\*\*\*\*  >  [語音]\*\*\*\* 中啟用語音功能。</span><span class="sxs-lookup"><span data-stu-id="bfb67-113">In order to use these, you need to enable Speech during the first run of the device or in **Settings** > **Privacy** > **Speech**.</span></span> <span data-ttu-id="bfb67-114">您隨時都可以於 [開始] 功能表頂端查看狀態，檢查語音是否已啟用。</span><span class="sxs-lookup"><span data-stu-id="bfb67-114">You can always check whether speech is enabled by looking at the status at the top of the Start menu.</span></span> <span data-ttu-id="bfb67-115">為了獲得最佳的語音辨識結果，HoloLens 2 會使用 Microsoft 雲端服務。</span><span class="sxs-lookup"><span data-stu-id="bfb67-115">For the best speech recognition results, HoloLens 2 uses the Microsoft cloud-based services.</span></span> <span data-ttu-id="bfb67-116">不過，您可以使用 [設定] 來停用這項功能。</span><span class="sxs-lookup"><span data-stu-id="bfb67-116">However, you can use Settings to disable this feature.</span></span> <span data-ttu-id="bfb67-117">若要這麼做，請在 [設定] 中關閉 [線上語音辨識]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bfb67-117">To do this, in Settings, turn off **Online speech recognition**.</span></span> <span data-ttu-id="bfb67-118">變更此設定之後，HoloLens 2 就只會在本機處理語音資料，以辨識命令和聽寫，且 Cortana 將無法使用。</span><span class="sxs-lookup"><span data-stu-id="bfb67-118">After you change this setting, HoloLens 2 will only process voice data locally to recognize commands and dictation, and Cortana will not be available.</span></span>

### <span data-ttu-id="bfb67-119">一般語音命令</span><span class="sxs-lookup"><span data-stu-id="bfb67-119">General speech commands</span></span>

<span data-ttu-id="bfb67-120">在整個 Windows Mixed Reality 中使用這些命令，以加快操作。</span><span class="sxs-lookup"><span data-stu-id="bfb67-120">Use these commands throughout Windows Mixed Reality to get around faster.</span></span> <span data-ttu-id="bfb67-121">有些命令會使用注視游標，您可以說出「選取」來顯示。</span><span class="sxs-lookup"><span data-stu-id="bfb67-121">Some commands use the gaze cursor, which you bring up by saying "select."</span></span>

> [!NOTE]
> <span data-ttu-id="bfb67-122">HoloLens (第一代) 不支援手部射線。</span><span class="sxs-lookup"><span data-stu-id="bfb67-122">Hand rays are not supported on HoloLens (1st Gen).</span></span>

| <span data-ttu-id="bfb67-123">請說</span><span class="sxs-lookup"><span data-stu-id="bfb67-123">Say this</span></span> | <span data-ttu-id="bfb67-124">若要這樣做</span><span class="sxs-lookup"><span data-stu-id="bfb67-124">To do this</span></span> |
| - | - |
| <span data-ttu-id="bfb67-125">"Select"</span><span class="sxs-lookup"><span data-stu-id="bfb67-125">"Select"</span></span> | <span data-ttu-id="bfb67-126">說「選取」以顯示注視游標。</span><span class="sxs-lookup"><span data-stu-id="bfb67-126">Say "select" to bring up the gaze cursor.</span></span> <span data-ttu-id="bfb67-127">接著，轉動頭部將游標移到您要選取的項目，然後再次說「選取」。</span><span class="sxs-lookup"><span data-stu-id="bfb67-127">Then, turn your head to position the cursor on the thing you want to select, and say "select" again.</span></span> |
|<span data-ttu-id="bfb67-128">Open the Start menu</span><span class="sxs-lookup"><span data-stu-id="bfb67-128">Open the Start menu</span></span> | <span data-ttu-id="bfb67-129">「移至開始」</span><span class="sxs-lookup"><span data-stu-id="bfb67-129">"Go to Start"</span></span> |
|<span data-ttu-id="bfb67-130">Close the Start menu</span><span class="sxs-lookup"><span data-stu-id="bfb67-130">Close the Start menu</span></span> | <span data-ttu-id="bfb67-131">「關閉」</span><span class="sxs-lookup"><span data-stu-id="bfb67-131">"Close"</span></span> |
|<span data-ttu-id="bfb67-132">Leave an immersive app</span><span class="sxs-lookup"><span data-stu-id="bfb67-132">Leave an immersive app</span></span> | <span data-ttu-id="bfb67-133">說「移至開始」以顯示 [快閃操作] 功能表，然後說「混合實境住家」。</span><span class="sxs-lookup"><span data-stu-id="bfb67-133">Say "Go to Start" to bring up the quick actions menu, then say "Mixed reality home."</span></span> |
|<span data-ttu-id="bfb67-134">Hide and show hand ray</span><span class="sxs-lookup"><span data-stu-id="bfb67-134">Hide and show hand ray</span></span> | <span data-ttu-id="bfb67-135">「隱藏手部射線」/「顯示手部射線」</span><span class="sxs-lookup"><span data-stu-id="bfb67-135">"Hide hand ray" / "Show hand ray"</span></span> |
|<span data-ttu-id="bfb67-136">See available speech commands</span><span class="sxs-lookup"><span data-stu-id="bfb67-136">See available speech commands</span></span> | <span data-ttu-id="bfb67-137">「我可以說什麼？」</span><span class="sxs-lookup"><span data-stu-id="bfb67-137">"What can I say?"</span></span> |

<span data-ttu-id="bfb67-138">從 HoloLens 2 的版本 19041.x 開始，您也可以使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="bfb67-138">Starting with version 19041.x of HoloLens 2, you can also use these commands:</span></span>

| <span data-ttu-id="bfb67-139">請說</span><span class="sxs-lookup"><span data-stu-id="bfb67-139">Say this</span></span> | <span data-ttu-id="bfb67-140">進行此動作</span><span class="sxs-lookup"><span data-stu-id="bfb67-140">To do this</span></span> |
| - | - |
| <span data-ttu-id="bfb67-141">"Restart device"</span><span class="sxs-lookup"><span data-stu-id="bfb67-141">"Restart device"</span></span> | <span data-ttu-id="bfb67-142">出現對話方塊以確認您要重新啟動裝置。</span><span class="sxs-lookup"><span data-stu-id="bfb67-142">Bring up a dialogue to confirm you want to restart the device.</span></span> <span data-ttu-id="bfb67-143">您可以說「是」重新啟動。</span><span class="sxs-lookup"><span data-stu-id="bfb67-143">You can say "yes" to restart.</span></span> |
| <span data-ttu-id="bfb67-144">"Shutdown device"</span><span class="sxs-lookup"><span data-stu-id="bfb67-144">"Shutdown device"</span></span> | <span data-ttu-id="bfb67-145">出現對話方塊以確認您要關閉裝置。</span><span class="sxs-lookup"><span data-stu-id="bfb67-145">Bring up a dialogue to confirm you want to turn off the device.</span></span> <span data-ttu-id="bfb67-146">您可以說「是」以確認。</span><span class="sxs-lookup"><span data-stu-id="bfb67-146">You can say "yes" to confirm.</span></span> |
| <span data-ttu-id="bfb67-147">"Brightness up/down"</span><span class="sxs-lookup"><span data-stu-id="bfb67-147">"Brightness up/down"</span></span> | <span data-ttu-id="bfb67-148">將顯示器亮度增加或減少 10%。</span><span class="sxs-lookup"><span data-stu-id="bfb67-148">Increase or decrease the display brightness by 10%.</span></span> |
| <span data-ttu-id="bfb67-149">"Volume up/down"</span><span class="sxs-lookup"><span data-stu-id="bfb67-149">"Volume up/down"</span></span> | <span data-ttu-id="bfb67-150">將音量增加或減少 10%。</span><span class="sxs-lookup"><span data-stu-id="bfb67-150">Increase or decrease the volume by 10%.</span></span> |
| <span data-ttu-id="bfb67-151">"What's my IP address"</span><span class="sxs-lookup"><span data-stu-id="bfb67-151">"What's my IP address"</span></span> | <span data-ttu-id="bfb67-152">出現對話方塊，顯示您的裝置目前在本機網路中的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="bfb67-152">Bring up a dialogue displaying your device's current IP address on the local network.</span></span> |
| <span data-ttu-id="bfb67-153">"Take a picture"</span><span class="sxs-lookup"><span data-stu-id="bfb67-153">"Take a picture"</span></span> | <span data-ttu-id="bfb67-154">擷取目前看到的混合實境相片。</span><span class="sxs-lookup"><span data-stu-id="bfb67-154">Capture a mixed reality photo of what you are currently seeing.</span></span> |
| <span data-ttu-id="bfb67-155">"Take a video"</span><span class="sxs-lookup"><span data-stu-id="bfb67-155">"Take a video"</span></span> | <span data-ttu-id="bfb67-156">開始錄製混合實境影片。</span><span class="sxs-lookup"><span data-stu-id="bfb67-156">Start recording a mixed reality video.</span></span> | 
| <span data-ttu-id="bfb67-157">"Stop recording"</span><span class="sxs-lookup"><span data-stu-id="bfb67-157">"Stop recording"</span></span> | <span data-ttu-id="bfb67-158">如果有混合實境影片錄製正在進行中，則加以停止。</span><span class="sxs-lookup"><span data-stu-id="bfb67-158">Stops the current mixed reality video recording if one is in progress.</span></span> |

### <span data-ttu-id="bfb67-159">全像投影命令</span><span class="sxs-lookup"><span data-stu-id="bfb67-159">Hologram commands</span></span>

<span data-ttu-id="bfb67-160">若要使用這些命令，請注視 3D 物件、全像投影或應用程式視窗。</span><span class="sxs-lookup"><span data-stu-id="bfb67-160">To use these commands, gaze at a 3D object, hologram, or app window.</span></span>

| <span data-ttu-id="bfb67-161">請說</span><span class="sxs-lookup"><span data-stu-id="bfb67-161">Say this</span></span> | <span data-ttu-id="bfb67-162">進行此動作</span><span class="sxs-lookup"><span data-stu-id="bfb67-162">To do this</span></span> |
| - | - |
| <span data-ttu-id="bfb67-163">"Bigger"</span><span class="sxs-lookup"><span data-stu-id="bfb67-163">"Bigger"</span></span> | <span data-ttu-id="bfb67-164">將它放大</span><span class="sxs-lookup"><span data-stu-id="bfb67-164">Make it bigger</span></span> |
| <span data-ttu-id="bfb67-165">"Smaller"</span><span class="sxs-lookup"><span data-stu-id="bfb67-165">"Smaller"</span></span> | <span data-ttu-id="bfb67-166">將它縮小</span><span class="sxs-lookup"><span data-stu-id="bfb67-166">Make it smaller</span></span> |
| <span data-ttu-id="bfb67-167">"Face me"</span><span class="sxs-lookup"><span data-stu-id="bfb67-167">"Face me"</span></span> | <span data-ttu-id="bfb67-168">讓它面向您</span><span class="sxs-lookup"><span data-stu-id="bfb67-168">Turn it to face you</span></span> |
| <span data-ttu-id="bfb67-169">"Move this"</span><span class="sxs-lookup"><span data-stu-id="bfb67-169">"Move this"</span></span> | <span data-ttu-id="bfb67-170">移動它 (跟隨您的目光)</span><span class="sxs-lookup"><span data-stu-id="bfb67-170">Move it (follow your gaze)</span></span> |
| <span data-ttu-id="bfb67-171">"Close"</span><span class="sxs-lookup"><span data-stu-id="bfb67-171">"Close"</span></span> | <span data-ttu-id="bfb67-172">將它關閉</span><span class="sxs-lookup"><span data-stu-id="bfb67-172">Close it</span></span> |
| <span data-ttu-id="bfb67-173">"Follow me" / "Stop following"</span><span class="sxs-lookup"><span data-stu-id="bfb67-173">"Follow me" / "Stop following"</span></span> | <span data-ttu-id="bfb67-174">讓它跟隨您四處移動</span><span class="sxs-lookup"><span data-stu-id="bfb67-174">Make it follow you as you move around</span></span> |

### <span data-ttu-id="bfb67-175">邊看邊說</span><span class="sxs-lookup"><span data-stu-id="bfb67-175">See it, say it</span></span>

<span data-ttu-id="bfb67-176">HoloLens 上的許多按鈕及其他元素也會回應您的聲音：例如，應用程式列上的**跟隨我**和**關閉**，或是 Edge 中的**返回**按鈕。</span><span class="sxs-lookup"><span data-stu-id="bfb67-176">Many buttons and other elements on HoloLens also respond to your voice—for example, **Follow me** and **Close** on the app bar, or the **Back** button in Edge.</span></span> <span data-ttu-id="bfb67-177">若要了解按鈕是否已啟用語音控制，請將**注視游標**、**觸控游標**或**手部射線**停留其上一段時間。</span><span class="sxs-lookup"><span data-stu-id="bfb67-177">To find out if a button is voice-enabled, rest your **gaze cursor**,**touch cursor** or one **hand ray** on it for a moment.</span></span> <span data-ttu-id="bfb67-178">如果按鈕已啟用語音控制，您會看到語音提示。</span><span class="sxs-lookup"><span data-stu-id="bfb67-178">If the button is voice-enabled, you'll see a voice tip.</span></span>

### <span data-ttu-id="bfb67-179">聽寫模式</span><span class="sxs-lookup"><span data-stu-id="bfb67-179">Dictation mode</span></span>

<span data-ttu-id="bfb67-180">厭倦了打字輸入？</span><span class="sxs-lookup"><span data-stu-id="bfb67-180">Tired of typing?</span></span> <span data-ttu-id="bfb67-181">只要全像攝影鍵盤已啟用，隨時都可切換到聽寫模式。</span><span class="sxs-lookup"><span data-stu-id="bfb67-181">Switch to dictation mode any time that the holographic keyboard is active.</span></span> <span data-ttu-id="bfb67-182">若要開始使用，請選取麥克風按鈕，或說「開始聽寫」。</span><span class="sxs-lookup"><span data-stu-id="bfb67-182">To get started, select the microphone button or say "Start dictating."</span></span> <span data-ttu-id="bfb67-183">若要停止聽寫，請再次選取該按鈕，或說「停止聽寫」。</span><span class="sxs-lookup"><span data-stu-id="bfb67-183">To stop dictating, select the button again or say "Stop dictating."</span></span> <span data-ttu-id="bfb67-184">若要刪除剛才聽寫的內容，請說「刪除這個」。</span><span class="sxs-lookup"><span data-stu-id="bfb67-184">To delete what you just dictated, say "Delete that."</span></span> 

> [!NOTE]
> <span data-ttu-id="bfb67-185">為了使用聽寫模式，就必須有網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="bfb67-185">To use dictation mode, you have to have an internet connection.</span></span>

<span data-ttu-id="bfb67-186">HoloLens 聽寫使用顯式標點符號，也就是您得說出所要使用標點符號的名稱。</span><span class="sxs-lookup"><span data-stu-id="bfb67-186">HoloLens dictation uses explicit punctuation, meaning that you say the name of the punctuation you want to use.</span></span> <span data-ttu-id="bfb67-187">例如，您可以說「嗨**逗號**要做什麼**問號**」。</span><span class="sxs-lookup"><span data-stu-id="bfb67-187">For instance, you might say "Hey **comma** what are you up to **question mark**."</span></span>

<span data-ttu-id="bfb67-188">以下是您可以使用的標點符號關鍵字：</span><span class="sxs-lookup"><span data-stu-id="bfb67-188">Here are the punctuation keywords that you can use:</span></span>

- <span data-ttu-id="bfb67-189">句號、逗號、問號、驚嘆號</span><span class="sxs-lookup"><span data-stu-id="bfb67-189">Period, comma, question mark, exclamation point/exclamation mark</span></span>
- <span data-ttu-id="bfb67-190">新行/新段落</span><span class="sxs-lookup"><span data-stu-id="bfb67-190">New line/new paragraph</span></span>
- <span data-ttu-id="bfb67-191">分號、冒號</span><span class="sxs-lookup"><span data-stu-id="bfb67-191">Semicolon, colon</span></span>
- <span data-ttu-id="bfb67-192">左引號、右引號</span><span class="sxs-lookup"><span data-stu-id="bfb67-192">Open quote(s), close quote(s)</span></span>
- <span data-ttu-id="bfb67-193">主題標籤、微笑/笑臉、皺眉、眨眼</span><span class="sxs-lookup"><span data-stu-id="bfb67-193">Hashtag, smiley/smiley face, frowny, winky</span></span>
- <span data-ttu-id="bfb67-194">美元、百分比</span><span class="sxs-lookup"><span data-stu-id="bfb67-194">Dollar, percent</span></span>

<span data-ttu-id="bfb67-195">這對拼出像電子郵件地址這樣的內容，有時會很有幫助。</span><span class="sxs-lookup"><span data-stu-id="bfb67-195">Sometimes it's helpful to spell out things like email addresses.</span></span> <span data-ttu-id="bfb67-196">例如，要聽寫 example@outlook.com，您會說「E X A M P L E at outlook dot com」。</span><span class="sxs-lookup"><span data-stu-id="bfb67-196">For instance, to dictate example@outlook.com, you'd say "E X A M P L E at outlook dot com."</span></span>

## <span data-ttu-id="bfb67-197">使用 Cortana 執行更多動作</span><span class="sxs-lookup"><span data-stu-id="bfb67-197">Do more with Cortana</span></span>

<span data-ttu-id="bfb67-198">Cortana 可協助您在 HoloLens 上執行各種工作，但是根據您使用的 Windows Holographic 版本而定，功能可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="bfb67-198">Cortana can help you do all kinds of things on your HoloLens, but depending on which version of Windows Holographic you're using, the capablities may be different.</span></span> <span data-ttu-id="bfb67-199">您可以在[這裡](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)深入了解最新版本 Cortana 的最新資訊。</span><span class="sxs-lookup"><span data-stu-id="bfb67-199">You can learn more about the updated capabilites of the latest version of Cortana [here](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).</span></span> 

![Hey Cortana!](images/cortana-on-hololens.png)

<span data-ttu-id="bfb67-201">以下是一些您可嘗試的命令 (記得先說「Hey Cortana」)。</span><span class="sxs-lookup"><span data-stu-id="bfb67-201">Here are some things you can try saying (remember to say "Hey Cortana" first).</span></span>

<span data-ttu-id="bfb67-202">**Hey, Cortana**...</span><span class="sxs-lookup"><span data-stu-id="bfb67-202">**Hey, Cortana**...</span></span>

- <span data-ttu-id="bfb67-203">What can I say?</span><span class="sxs-lookup"><span data-stu-id="bfb67-203">What can I say?</span></span>
- <span data-ttu-id="bfb67-204">Launch <*應用程式名稱*>。</span><span class="sxs-lookup"><span data-stu-id="bfb67-204">Launch <*app name*>.</span></span>
- <span data-ttu-id="bfb67-205">What time is it?</span><span class="sxs-lookup"><span data-stu-id="bfb67-205">What time is it?</span></span>
- <span data-ttu-id="bfb67-206">Show me the latest NBA scores.</span><span class="sxs-lookup"><span data-stu-id="bfb67-206">Show me the latest NBA scores.</span></span>
- <span data-ttu-id="bfb67-207">Tell me a joke.</span><span class="sxs-lookup"><span data-stu-id="bfb67-207">Tell me a joke.</span></span>

<span data-ttu-id="bfb67-208">如果您使用的是 *版本 18362.x 或較舊版本*，您也可以使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="bfb67-208">If you're using *version 18362.x or earlier*, you can also use these commands:</span></span>

<span data-ttu-id="bfb67-209">**Hey, Cortana**...</span><span class="sxs-lookup"><span data-stu-id="bfb67-209">**Hey, Cortana**...</span></span>

- <span data-ttu-id="bfb67-210">Increase the volume.</span><span class="sxs-lookup"><span data-stu-id="bfb67-210">Increase the volume.</span></span>
- <span data-ttu-id="bfb67-211">Decrease the brightness.</span><span class="sxs-lookup"><span data-stu-id="bfb67-211">Decrease the brightness.</span></span>
- <span data-ttu-id="bfb67-212">Shut down.</span><span class="sxs-lookup"><span data-stu-id="bfb67-212">Shut down.</span></span>
- <span data-ttu-id="bfb67-213">Restart.</span><span class="sxs-lookup"><span data-stu-id="bfb67-213">Restart.</span></span>
- <span data-ttu-id="bfb67-214">Go to sleep.</span><span class="sxs-lookup"><span data-stu-id="bfb67-214">Go to sleep.</span></span>
- <span data-ttu-id="bfb67-215">Mute.</span><span class="sxs-lookup"><span data-stu-id="bfb67-215">Mute.</span></span>
- <span data-ttu-id="bfb67-216">Move <*應用程式名稱*> here (注視要將應用程式移到的位置)。</span><span class="sxs-lookup"><span data-stu-id="bfb67-216">Move <*app name*> here (gaze at the spot that you want the app to move to).</span></span>
- <span data-ttu-id="bfb67-217">Go to Start.</span><span class="sxs-lookup"><span data-stu-id="bfb67-217">Go to Start.</span></span>
- <span data-ttu-id="bfb67-218">Take a picture.</span><span class="sxs-lookup"><span data-stu-id="bfb67-218">Take a picture.</span></span>
- <span data-ttu-id="bfb67-219">Start recording.</span><span class="sxs-lookup"><span data-stu-id="bfb67-219">Start recording.</span></span> <span data-ttu-id="bfb67-220">(開始錄製影片)。</span><span class="sxs-lookup"><span data-stu-id="bfb67-220">(Starts recording a video.)</span></span>
- <span data-ttu-id="bfb67-221">Stop recording.</span><span class="sxs-lookup"><span data-stu-id="bfb67-221">Stop recording.</span></span> <span data-ttu-id="bfb67-222">(停止錄製影片)。</span><span class="sxs-lookup"><span data-stu-id="bfb67-222">(Stops recording a video.)</span></span>
- <span data-ttu-id="bfb67-223">How much battery do I have left?</span><span class="sxs-lookup"><span data-stu-id="bfb67-223">How much battery do I have left?</span></span>

<span data-ttu-id="bfb67-224">有些您在電腦或手機的 Windows 中所習慣的 Cortana 功能 (例如，提醒和通知)，Microsoft HoloLens 並不支援，並且 Cortana 體驗可能會因地區不同而有所不同。</span><span class="sxs-lookup"><span data-stu-id="bfb67-224">Some Cortana features that you're used to from Windows on your PC or phone (for example, reminders and notifications) aren't supported in Microsoft HoloLens, and the Cortana experience may vary from one region to another.</span></span>

### <span data-ttu-id="bfb67-225">關閉 Cortana</span><span class="sxs-lookup"><span data-stu-id="bfb67-225">Turn Cortana off</span></span>

<span data-ttu-id="bfb67-226">第一次使用 HoloLens 時，Cortana 是在您啟用語音時開啟。</span><span class="sxs-lookup"><span data-stu-id="bfb67-226">Cortana is on the first time you use HoloLens when you enable speech.</span></span> <span data-ttu-id="bfb67-227">您可以在 Cortana 的設定中將她關閉。</span><span class="sxs-lookup"><span data-stu-id="bfb67-227">You can turn her off in Cortana's settings.</span></span> <span data-ttu-id="bfb67-228">在**所有應用程式**清單中，選取 **Cortana** > **設定**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-228">In the **All apps** list, select **Cortana** > **Settings**.</span></span> <span data-ttu-id="bfb67-229">然後關閉 [Cortana 可提供您建議、想法、提醒、警示及其他]。</span><span class="sxs-lookup"><span data-stu-id="bfb67-229">Then turn off Cortana can give you suggestions, ideas, reminders, alerts, and more.</span></span>

<span data-ttu-id="bfb67-230">如果 Cortana 對「Hey Cortana」沒有回應，請檢查是否已在 [開始] 中啟用語音，然後移至 Cortana 的設定並確認她是在開啟狀態。</span><span class="sxs-lookup"><span data-stu-id="bfb67-230">If Cortana isn't responding to "Hey Cortana," check that speech is enabled on Start and go to Cortana's settings and check to make sure she's on.</span></span>
