---
title: 適用於 Microsoft HoloLens 的 Insider Preview
description: 您可以輕鬆開始使用測試人員組建，並為我們的下一個主要作業系統更新提供寶貴的意見反應，以進行 HoloLens。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 6/29/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 5cdb7302aec5b37a5071f2192f7c8bc5df760ac7
ms.sourcegitcommit: 3db43bc4a007b10901d8edb045f66e1e299c57a9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882425"
---
# <span data-ttu-id="15b4b-103">適用於 Microsoft HoloLens 的 Insider Preview</span><span class="sxs-lookup"><span data-stu-id="15b4b-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="15b4b-104">歡迎使用 HoloLens 的最新 Insider Preview 組建！</span><span class="sxs-lookup"><span data-stu-id="15b4b-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span>  <span data-ttu-id="15b4b-105">開始使用並為我們的下一個重要作業系統更新提供寶貴的意見反應，這是一件簡單的工作。</span><span class="sxs-lookup"><span data-stu-id="15b4b-105">It's simple to get started and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

<span data-ttu-id="15b4b-106">Windows 測試人員現在正在移至 [頻道]。</span><span class="sxs-lookup"><span data-stu-id="15b4b-106">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="15b4b-107">[**快速**響鈴] 會成為**開發人員通道**，**慢速**環將變成**Beta 通道**，而 [**放開預覽**] 鈴聲將成為**發行預覽頻道**。</span><span class="sxs-lookup"><span data-stu-id="15b4b-107">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="15b4b-108">對應如下：</span><span class="sxs-lookup"><span data-stu-id="15b4b-108">Here is what that mapping looks like:</span></span>

![Windows 測試人員頻道說明](images/WindowsInsiderChannels.png)

<span data-ttu-id="15b4b-110">如需詳細資訊： [Windows 博客專案](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)</span><span class="sxs-lookup"><span data-stu-id="15b4b-110">For more information: [Windows Blog entry](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)</span></span>

## <span data-ttu-id="15b4b-111">開始接收測試人員組建</span><span class="sxs-lookup"><span data-stu-id="15b4b-111">Start receiving Insider builds</span></span>

<span data-ttu-id="15b4b-112">在 HoloLens 2 裝置上，移至 [**設定**  ->  **更新] & 安全性**  ->  **Windows**測試人員計畫，然後選取 [**開始**使用]。</span><span class="sxs-lookup"><span data-stu-id="15b4b-112">On a HoloLens 2 device go to **Settings** -> **Update & Security** -> **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="15b4b-113">連結您用來註冊為「Windows 測試人員」的帳戶。</span><span class="sxs-lookup"><span data-stu-id="15b4b-113">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="15b4b-114">接著，選取 [Windows 作用中**的開發**]，選擇您要接收**開發人員通道**或**Beta 通道**組建，並查看程式條款。</span><span class="sxs-lookup"><span data-stu-id="15b4b-114">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="15b4b-115">選取 [**確認]-> [立即重新開機**] 完成。</span><span class="sxs-lookup"><span data-stu-id="15b4b-115">Select **Confirm -> Restart Now** to finish up.</span></span> <span data-ttu-id="15b4b-116">重新開機裝置之後，請移至 [**設定]-> 更新 & 安全性-> 檢查更新**以取得最新的組建。</span><span class="sxs-lookup"><span data-stu-id="15b4b-116">After your device has rebooted, go to **Settings -> Update & Security -> Check for updates** to get the latest build.</span></span>

## <span data-ttu-id="15b4b-117">停止接收測試人員組建</span><span class="sxs-lookup"><span data-stu-id="15b4b-117">Stop receiving Insider builds</span></span>

<span data-ttu-id="15b4b-118">如果您不想再收到 Windows 全息版的測試人員組建，您可以在 HoloLens 執行生產組建時退出宣告，或者，您可以[使用 [](hololens-recovery.md)高級恢復] 隨附的功能，將您的裝置復原至非測試人員版本的 Windows 全息版。</span><span class="sxs-lookup"><span data-stu-id="15b4b-118">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="15b4b-119">在手動重新安裝新的預覽組建之後，從測試人員預覽版中取消登錄的已知問題，將會出現藍屏。</span><span class="sxs-lookup"><span data-stu-id="15b4b-119">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="15b4b-120">之後，他們必須手動復原其裝置。</span><span class="sxs-lookup"><span data-stu-id="15b4b-120">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="15b4b-121">如需有關您是否會受到影響的完整詳細資料，請查看此[已知問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="15b4b-121">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="15b4b-122">若要確認您的 HoloLens 正在執行生產組建：</span><span class="sxs-lookup"><span data-stu-id="15b4b-122">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="15b4b-123">移至 [**設定] > [系統 >**]，然後找出組建編號。</span><span class="sxs-lookup"><span data-stu-id="15b4b-123">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="15b4b-124">[請參閱生產組建編號的版本](hololens-release-notes.md)資訊。</span><span class="sxs-lookup"><span data-stu-id="15b4b-124">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="15b4b-125">若要退出宣告測試人員組建：</span><span class="sxs-lookup"><span data-stu-id="15b4b-125">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="15b4b-126">在運行生產組建的 HoloLens 中，移至 [**設定] > 更新 & 安全性 > Windows**測試人員計畫，然後選取 [停止測試人員**組建**]。</span><span class="sxs-lookup"><span data-stu-id="15b4b-126">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="15b4b-127">依照指示操作以選擇您的裝置。</span><span class="sxs-lookup"><span data-stu-id="15b4b-127">Follow the instructions to opt out your device.</span></span>


## <span data-ttu-id="15b4b-128">提供意見反應與報告問題</span><span class="sxs-lookup"><span data-stu-id="15b4b-128">Provide feedback and report issues</span></span>

<span data-ttu-id="15b4b-129">請在您的 HoloLens 上使用「[意見反應中樞」 app](hololens-feedback.md) ，以提供意見反應與報告問題。</span><span class="sxs-lookup"><span data-stu-id="15b4b-129">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="15b4b-130">使用意見反應中樞可確保所有必要的診斷資訊都包含在內，以協助我們的工程師快速調試並解決問題。</span><span class="sxs-lookup"><span data-stu-id="15b4b-130">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="15b4b-131">使用中文和日文版的 HoloLens 時，必須以相同的方式報告問題。</span><span class="sxs-lookup"><span data-stu-id="15b4b-131">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="15b4b-132">請務必接受詢問您是否希望意見反應中樞存取您的 [檔] 資料夾的提示（在出現提示時，選取 **[是]** ）。</span><span class="sxs-lookup"><span data-stu-id="15b4b-132">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="15b4b-133">開發人員注意事項</span><span class="sxs-lookup"><span data-stu-id="15b4b-133">Note for developers</span></span>

<span data-ttu-id="15b4b-134">歡迎與鼓勵您使用 HoloLens 測試人員組建來開發應用程式。</span><span class="sxs-lookup"><span data-stu-id="15b4b-134">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="15b4b-135">請參閱[HoloLens 開發人員檔](https://developer.microsoft.com/windows/mixed-reality/development)以開始使用。</span><span class="sxs-lookup"><span data-stu-id="15b4b-135">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="15b4b-136">這些相同的指示可與 HoloLens 測試人員組建搭配使用。</span><span class="sxs-lookup"><span data-stu-id="15b4b-136">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="15b4b-137">您可以使用與您已在 HoloLens 開發中使用的相同 Unity 與 Visual Studio 組建。</span><span class="sxs-lookup"><span data-stu-id="15b4b-137">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>


## <span data-ttu-id="15b4b-138">Windows 測試人員版本資訊</span><span class="sxs-lookup"><span data-stu-id="15b4b-138">Windows Insider Release Notes</span></span>

<span data-ttu-id="15b4b-139">如果您要尋找的功能已不在此處列出，現在就能正式使用了。</span><span class="sxs-lookup"><span data-stu-id="15b4b-139">If you are looking for a feature that is no longer listed here, then it is now generally available.</span></span> <span data-ttu-id="15b4b-140">請查看[版本](hololens-release-notes.md)資訊，瞭解哪些組建具有您令人興奮的功能。</span><span class="sxs-lookup"><span data-stu-id="15b4b-140">Please review the [release notes](hololens-release-notes.md) to see what build has the feature(s) you are excited for.</span></span> <span data-ttu-id="15b4b-141">請務必[更新您的 HoloLens](hololens-update-hololens.md) ，以取得所有最新功能。</span><span class="sxs-lookup"><span data-stu-id="15b4b-141">Make sure to [update your HoloLens](hololens-update-hololens.md) to get all the latest features.</span></span>

<span data-ttu-id="15b4b-142">我們會在我們發行給 Windows 測試人員組建的新功能時再次更新此頁面。</span><span class="sxs-lookup"><span data-stu-id="15b4b-142">We'll be updating this page with new features again as we release them to Windows Insider builds.</span></span>

| <span data-ttu-id="15b4b-143">功能</span><span class="sxs-lookup"><span data-stu-id="15b4b-143">Feature</span></span>                               | <span data-ttu-id="15b4b-144">描述</span><span class="sxs-lookup"><span data-stu-id="15b4b-144">Description</span></span>                                                                                   | <span data-ttu-id="15b4b-145">可在測試人員組建中使用</span><span class="sxs-lookup"><span data-stu-id="15b4b-145">Available in insider builds</span></span> |
|---------------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------|
| <span data-ttu-id="15b4b-146">自動目視位置支援</span><span class="sxs-lookup"><span data-stu-id="15b4b-146">Auto Eye Position Support</span></span>             | <span data-ttu-id="15b4b-147">積極找出眼睛位置，並啟用正確的全息圖位置。</span><span class="sxs-lookup"><span data-stu-id="15b4b-147">Actively finds eye positions and enables accurate hologram positioning.</span></span>                       | <span data-ttu-id="15b4b-148">19041.1339 +</span><span class="sxs-lookup"><span data-stu-id="15b4b-148">19041.1339+</span></span>                 |
| <span data-ttu-id="15b4b-149">全域指派的存取</span><span class="sxs-lookup"><span data-stu-id="15b4b-149">Global Assigned Access</span></span>                | <span data-ttu-id="15b4b-150">針對適用于系統層級的多個 app kiosk 模式設定 HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="15b4b-150">Configure HoloLens 2 device for multiple app kiosk mode which is applicable at system level.</span></span>  | <span data-ttu-id="15b4b-151">19041.1346 +</span><span class="sxs-lookup"><span data-stu-id="15b4b-151">19041.1346+</span></span>                 |
| <span data-ttu-id="15b4b-152">在多應用程式亭中自動啟動應用程式</span><span class="sxs-lookup"><span data-stu-id="15b4b-152">Auto launch an app in multi-app kiosk</span></span> | <span data-ttu-id="15b4b-153">將應用程式設定為在登入多重應用程式亭模式時自動啟動。</span><span class="sxs-lookup"><span data-stu-id="15b4b-153">Sets an application to launch automatically when signing into into a multiple-app kiosk mode.</span></span> | <span data-ttu-id="15b4b-154">19041.1346 +</span><span class="sxs-lookup"><span data-stu-id="15b4b-154">19041.1346+</span></span>                 |

### <span data-ttu-id="15b4b-155">自動目視位置支援</span><span class="sxs-lookup"><span data-stu-id="15b4b-155">Auto Eye Position Support</span></span>

<span data-ttu-id="15b4b-156">在 HoloLens 2 中，目視位置可讓您實現正確的全息圖定位、舒適的觀賞體驗，以及改善顯示品質。</span><span class="sxs-lookup"><span data-stu-id="15b4b-156">In HoloLens 2, eye positions enable accurate hologram positioning, comfortable viewing experience and improved display quality.</span></span> <span data-ttu-id="15b4b-157">眼睛位置會計算為眼睛追蹤結果的一部分。</span><span class="sxs-lookup"><span data-stu-id="15b4b-157">Eye positions are computed as part of the eye tracking result.</span></span> <span data-ttu-id="15b4b-158">不過，這需要每個使用者都能透過目視追蹤校準，即使在體驗不需要目視眼睛的輸入時也一樣。</span><span class="sxs-lookup"><span data-stu-id="15b4b-158">However, this requires each user to go through eye tracking calibration, even when the experience does not require eye gaze input.</span></span>

<span data-ttu-id="15b4b-159">**自動目視位置（AEP）** 可讓這些案例使用互動式方式來計算使用者的目視位置。</span><span class="sxs-lookup"><span data-stu-id="15b4b-159">**Auto Eye Position (AEP)** enables these scenarios with an interaction-free way to compute eye positions for the user.</span></span>  <span data-ttu-id="15b4b-160">自動目視位置會在使用者將裝置放在背景的時刻自動開始運作。</span><span class="sxs-lookup"><span data-stu-id="15b4b-160">Auto Eye Position starts working in the background automatically from the moment the user puts the device on.</span></span> <span data-ttu-id="15b4b-161">如果使用者沒有先前的目視追蹤校準，自動目視位置將會在較小的處理時間之後，在顯示系統中開始提供使用者的目視位置。</span><span class="sxs-lookup"><span data-stu-id="15b4b-161">If the user does not have a prior eye tracking calibration, Auto Eye position will start providing the user's eye positions to the display system after a small processing time.</span></span> <span data-ttu-id="15b4b-162">這個處理時間通常介於 20-60 秒之間。</span><span class="sxs-lookup"><span data-stu-id="15b4b-162">This processing time typically is between 20 - 60 seconds.</span></span> <span data-ttu-id="15b4b-163">使用者資料不會保留在裝置上，因此，如果使用者要卸載並將裝置重新開機或從睡眠狀態喚醒，就會重複此處理程式。</span><span class="sxs-lookup"><span data-stu-id="15b4b-163">The user data is not persisted on the device and hence this process is repeated if the user takes off and puts the device back on or if the device reboots or wakes up from sleep.</span></span>  

<span data-ttu-id="15b4b-164">當 uncalibrated 使用者放在裝置上時，有一些系統行為會隨著自動目視位置功能而變更。</span><span class="sxs-lookup"><span data-stu-id="15b4b-164">There are a few system behavior changes with Auto Eye Position feature when an uncalibrated user puts on the device.</span></span> <span data-ttu-id="15b4b-165">Uncalibrated 使用者會參照尚未在裝置上透過目視追蹤校準程式的人。</span><span class="sxs-lookup"><span data-stu-id="15b4b-165">An uncalibrated user refers to someone who has not gone through the eye tracking calibration process on the device previously.</span></span>

|     <span data-ttu-id="15b4b-166">使用中的應用程式</span><span class="sxs-lookup"><span data-stu-id="15b4b-166">Active Application</span></span>                           |     <span data-ttu-id="15b4b-167">目前的行為</span><span class="sxs-lookup"><span data-stu-id="15b4b-167">Current Behavior</span></span>                                   |     <span data-ttu-id="15b4b-168">Windows 測試人員組建 19041.1339 + 的行為</span><span class="sxs-lookup"><span data-stu-id="15b4b-168">Behavior from Windows Insider   build 19041.1339+</span></span>                                                      |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="15b4b-169">看不到的已啟用 app 或全息式貝殼</span><span class="sxs-lookup"><span data-stu-id="15b4b-169">Non-gaze enabled app or Holographic Shell</span></span>    |     <span data-ttu-id="15b4b-170">隨即會顯示目視追蹤校準提示。</span><span class="sxs-lookup"><span data-stu-id="15b4b-170">Eye tracking calibration prompt is   displayed.</span></span>    |     <span data-ttu-id="15b4b-171">不會顯示任何提示。</span><span class="sxs-lookup"><span data-stu-id="15b4b-171">No prompt is displayed.</span></span>                                                                                |
|     <span data-ttu-id="15b4b-172">看著已啟用的 app</span><span class="sxs-lookup"><span data-stu-id="15b4b-172">Gaze enabled app</span></span>                             |     <span data-ttu-id="15b4b-173">隨即會顯示目視追蹤校準提示。</span><span class="sxs-lookup"><span data-stu-id="15b4b-173">Eye tracking calibration prompt is   displayed.</span></span>    |     <span data-ttu-id="15b4b-174">只會在應用程式存取目視注視串流時顯示目視追蹤校準提示。</span><span class="sxs-lookup"><span data-stu-id="15b4b-174">Eye tracking calibration prompt is   displayed only when the application accesses eye gaze stream.</span></span>     |

 <span data-ttu-id="15b4b-175">如果使用者從尚未看不到的應用程式轉換到一個存取注視資料的應用程式，則會顯示校準提示。</span><span class="sxs-lookup"><span data-stu-id="15b4b-175">If the user transitions from a non-gaze enabled application to one that accesses the gaze data, the calibration prompt will be displayed.</span></span> <span data-ttu-id="15b4b-176">不會變更為現成的體驗流程。</span><span class="sxs-lookup"><span data-stu-id="15b4b-176">There will be no changed to Out Of Box Experience flow.</span></span> 
 
<span data-ttu-id="15b4b-177">針對需要目視眼睛資料或非常精確的全息圖位置的體驗，我們建議 uncalibrated 使用者從目視追蹤校準提示，或從 [開始] 功能表啟動 [設定] 應用程式，然後選取 [**系統 > 校準] > 目視校準 > 執行目視校準**。</span><span class="sxs-lookup"><span data-stu-id="15b4b-177">For experiences that require eye gaze data or very precise hologram positioning, we recommend uncalibrated users to run eye tracking calibration from the eye tracking calibration prompt or by launching the Settings app from the start menu, and then selecting **System > Calibration > Eye Calibration > Run eye calibration**.</span></span>

**<span data-ttu-id="15b4b-178">已知問題</span><span class="sxs-lookup"><span data-stu-id="15b4b-178">Known issues</span></span>**
 - <span data-ttu-id="15b4b-179">我們正在調查在大量記憶體載入不足的情況下，目視追蹤器驅動程式主機進程可能會當機的問題。</span><span class="sxs-lookup"><span data-stu-id="15b4b-179">We're investigating an issue where the eye tracker driver host process could crash when running under heavy memory load.</span></span> <span data-ttu-id="15b4b-180">目視追蹤驅動程式主機進程應該會自動復原。</span><span class="sxs-lookup"><span data-stu-id="15b4b-180">The eye tracking driver host process should auto recover.</span></span>

### <span data-ttu-id="15b4b-181">全域指派的存取-Kiosk 模式</span><span class="sxs-lookup"><span data-stu-id="15b4b-181">Global Assigned Access – Kiosk Mode</span></span>
<span data-ttu-id="15b4b-182">這項新功能可讓 IT 系統管理員針對在系統層級適用的多個 app kiosk 模式設定 HoloLens 2 裝置，且與登入裝置的每個人都有關聯的資訊。</span><span class="sxs-lookup"><span data-stu-id="15b4b-182">This new feature allows an IT Admin to configure a HoloLens 2 device for multiple app kiosk mode which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span> <span data-ttu-id="15b4b-183">請在[此深入瞭解](hololens-global-assigned-access-kiosk.md)這項新功能。</span><span class="sxs-lookup"><span data-stu-id="15b4b-183">Read about this new feature in detail [here](hololens-global-assigned-access-kiosk.md).</span></span>

### <span data-ttu-id="15b4b-184">在多應用程式亭模式中自動啟動應用程式</span><span class="sxs-lookup"><span data-stu-id="15b4b-184">Automatic launch of an application in multiple-app kiosk mode</span></span> 
<span data-ttu-id="15b4b-185">僅適用于多應用程式亭模式，且只有1個 app 可以使用 [指派的存取設定] 底下的 [醒目提示] 屬性來自動啟動。</span><span class="sxs-lookup"><span data-stu-id="15b4b-185">Applies only to multiple-app kiosk mode and only 1 app can be designated to auto-launch using highlighted attribute below in Assigned Access configuration.</span></span> 

<span data-ttu-id="15b4b-186">應用程式會在使用者登入時自動啟動。</span><span class="sxs-lookup"><span data-stu-id="15b4b-186">Application is automatically launched when user signs-in.</span></span> 

```xml
<AllowedApps>                     
    <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

## <span data-ttu-id="15b4b-187">FFU 下載和快閃路線</span><span class="sxs-lookup"><span data-stu-id="15b4b-187">FFU download and flash directions</span></span>
<span data-ttu-id="15b4b-188">若要使用 [航班式簽署 ffu] 進行測試，您必須先將裝置解除鎖定，然後才能閃爍 [航班已簽署] ffu。</span><span class="sxs-lookup"><span data-stu-id="15b4b-188">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="15b4b-189">在 PC 上：</span><span class="sxs-lookup"><span data-stu-id="15b4b-189">On PC:</span></span>

    1. <span data-ttu-id="15b4b-190">從下載 ffu 到您的電腦 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。</span><span class="sxs-lookup"><span data-stu-id="15b4b-190">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="15b4b-191">從 Microsoft 網上商店安裝弧形（高級恢復隨附版）：[https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="15b4b-191">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span></span>
    
1. <span data-ttu-id="15b4b-192">在 HoloLens-航班解鎖：開啟**設定**  >  **更新 & 安全性**  >  **Windows**測試人員計畫，然後註冊、重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="15b4b-192">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="15b4b-193">快閃 FFU-現在您可以使用 ARC 來閃現已簽署的航班 FFU。</span><span class="sxs-lookup"><span data-stu-id="15b4b-193">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>
