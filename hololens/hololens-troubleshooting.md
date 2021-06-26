---
title: HoloLens 裝置疑難排解
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
keywords: 問題、錯誤、疑難排解、修正、說明、支援、HoloLens、模擬器
ms.openlocfilehash: b69dddf04ac31b69f0b2f8759d095806189f33ab
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924616"
---
# <a name="device-troubleshooting"></a><span data-ttu-id="ce00d-104">裝置疑難排解</span><span class="sxs-lookup"><span data-stu-id="ce00d-104">Device Troubleshooting</span></span>

<span data-ttu-id="ce00d-105">本文說明如何解決數個常見的 HoloLens 問題。</span><span class="sxs-lookup"><span data-stu-id="ce00d-105">This article describes how to resolve several common HoloLens issues.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="ce00d-106">在開始進行任何疑難排解程式之前，請確定您的裝置必須支付 **20% 到 40%** 的電池容量（如果可能的話）。</span><span class="sxs-lookup"><span data-stu-id="ce00d-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="ce00d-107">位於 [電源] 按鈕下的 [電池指標燈](hololens2-setup.md#lights-that-indicate-the-battery-level) 是快速驗證電池容量，而不需要登入裝置的方式。</span><span class="sxs-lookup"><span data-stu-id="ce00d-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<a id="list"></a>

<span data-ttu-id="ce00d-108">**已知問題**</span><span class="sxs-lookup"><span data-stu-id="ce00d-108">**Known Issues**</span></span>
- [<span data-ttu-id="ce00d-109">遠端協助影片在20分鐘後凍結</span><span class="sxs-lookup"><span data-stu-id="ce00d-109">Remote Assist video freezes after 20 minutes</span></span>](#remote-assist-video-freezes-after-20-minutes)
- [<span data-ttu-id="ce00d-110">自動登入要求登入</span><span class="sxs-lookup"><span data-stu-id="ce00d-110">Auto-login asks for log-in</span></span>](#auto-login-asks-for-log-in)
- [<span data-ttu-id="ce00d-111">無法啟動 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ce00d-111">Microsoft Edge fails to launch</span></span>](#microsoft-edge-fails-to-launch)
- [<span data-ttu-id="ce00d-112">鍵盤未切換至特殊字元</span><span class="sxs-lookup"><span data-stu-id="ce00d-112">Keyboard doesn't switch to special characters</span></span>](#keyboard-doesnt-switch-to-special-characters)
- [<span data-ttu-id="ce00d-113">下載鎖定的檔案不會顯示錯誤</span><span class="sxs-lookup"><span data-stu-id="ce00d-113">Downloading locked files doesn't show error</span></span>](#downloading-locked-files-doesnt-error)
- [<span data-ttu-id="ce00d-114">裝置入口網站檔案上傳/下載超時</span><span class="sxs-lookup"><span data-stu-id="ce00d-114">Device Portal file upload/download times out</span></span>](#device-portal-file-uploaddownload-times-out)
- [<span data-ttu-id="ce00d-115">在使用 Insider build 進行閃爍的裝置上，從 Insider preview 取消註冊後的藍色畫面</span><span class="sxs-lookup"><span data-stu-id="ce00d-115">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [<span data-ttu-id="ce00d-116">OneDrive 不會自動上傳圖片</span><span class="sxs-lookup"><span data-stu-id="ce00d-116">OneDrive doesn't automatically upload pictures</span></span>](#onedrive-doesnt-automatically-upload-pictures)

<span data-ttu-id="ce00d-117">**一般**</span><span class="sxs-lookup"><span data-stu-id="ce00d-117">**General**</span></span>
- [<span data-ttu-id="ce00d-118">HoloLens 沒有回應或無法啟動</span><span class="sxs-lookup"><span data-stu-id="ce00d-118">HoloLens is unresponsive or won't start</span></span>](#hololens-is-unresponsive-or-wont-start)
- [<span data-ttu-id="ce00d-119">「磁碟空間不足」錯誤</span><span class="sxs-lookup"><span data-stu-id="ce00d-119">"Low Disk Space" error</span></span>](#low-disk-space-error)
- [<span data-ttu-id="ce00d-120">校正失敗</span><span class="sxs-lookup"><span data-stu-id="ce00d-120">Calibration Fails</span></span>](#calibration-fails)
- [<span data-ttu-id="ce00d-121">無法登入，因為先前已為他人設定過 HoloLens</span><span class="sxs-lookup"><span data-stu-id="ce00d-121">Can't sign in because my HoloLens was previously set up for someone else</span></span>](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [<span data-ttu-id="ce00d-122">Unity 無法運作</span><span class="sxs-lookup"><span data-stu-id="ce00d-122">Unity isn't working</span></span>](#unity-isnt-working)
- [<span data-ttu-id="ce00d-123">Windows 裝置入口網站無法正常運作</span><span class="sxs-lookup"><span data-stu-id="ce00d-123">Windows Device Portal isn't working correctly</span></span>](#windows-device-portal-isnt-working-correctly)
- [<span data-ttu-id="ce00d-124">HoloLens 模擬器無法運作</span><span class="sxs-lookup"><span data-stu-id="ce00d-124">The HoloLens Emulator isn't working</span></span>](#the-hololens-emulator-isnt-working)

<span data-ttu-id="ce00d-125">**輸入**</span><span class="sxs-lookup"><span data-stu-id="ce00d-125">**Input**</span></span>
- [<span data-ttu-id="ce00d-126">語音命令無法運作</span><span class="sxs-lookup"><span data-stu-id="ce00d-126">Voice commands aren't working</span></span>](#voice-commands-arent-working)
- [<span data-ttu-id="ce00d-127">手輸入無法運作</span><span class="sxs-lookup"><span data-stu-id="ce00d-127">Hand input isn't working</span></span>](#hand-input-isnt-working)

<span data-ttu-id="ce00d-128">**連線能力**</span><span class="sxs-lookup"><span data-stu-id="ce00d-128">**Connectivity**</span></span>
- [<span data-ttu-id="ce00d-129">無法連接到 Wi-fi</span><span class="sxs-lookup"><span data-stu-id="ce00d-129">Can't connect to Wi-Fi</span></span>](#cant-connect-to-wi-fi)

<span data-ttu-id="ce00d-130">**外部裝置**</span><span class="sxs-lookup"><span data-stu-id="ce00d-130">**External Devices**</span></span> 
- [<span data-ttu-id="ce00d-131">藍牙裝置未配對</span><span class="sxs-lookup"><span data-stu-id="ce00d-131">Bluetooth devices aren't pairing</span></span>](#bluetooth-devices-arent-pairing)
- [<span data-ttu-id="ce00d-132">USB-C 麥克風無法運作</span><span class="sxs-lookup"><span data-stu-id="ce00d-132">USB-C Microphone isn't working</span></span>](#usb-c-microphone-isnt-working)
- [<span data-ttu-id="ce00d-133">在設定中列為可用的裝置無法運作</span><span class="sxs-lookup"><span data-stu-id="ce00d-133">Devices listed as available in Settings don't work</span></span>](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a><span data-ttu-id="ce00d-134">遠端協助影片在20分鐘後凍結</span><span class="sxs-lookup"><span data-stu-id="ce00d-134">Remote Assist video freezes after 20 minutes</span></span>

> [!NOTE]
> <span data-ttu-id="ce00d-135">由於這個已知問題的嚴重性，我們目前已暫停 Windows 全像21H1 版的可用性。</span><span class="sxs-lookup"><span data-stu-id="ce00d-135">Due to this Known Issue's severity we have currently paused the availability of Windows Holographic, version 21H1.</span></span> <span data-ttu-id="ce00d-136">如果您仍想要將裝置更新為21H1，請參閱 [頁面頂端的版本資訊中的指示。](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="ce00d-136">If you would like to still update your devices to 21H1, please refer to [the instructions in our release notes at the top of the page.](hololens-release-notes.md)</span></span>

<span data-ttu-id="ce00d-137">在最新版的 Windows 全像 [21H1 版](hololens-release-notes.md#windows-holographic-version-21h1)中，某些遠端協助的使用者在呼叫期間會有20分鐘的影片凍結。</span><span class="sxs-lookup"><span data-stu-id="ce00d-137">On the latest release of [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), some users of Remote Assist have experienced video freezing during calls over 20 minutes.</span></span> <span data-ttu-id="ce00d-138">這是 **已知的問題**。</span><span class="sxs-lookup"><span data-stu-id="ce00d-138">This is a **known issue**.</span></span>

### <a name="workarounds"></a><span data-ttu-id="ce00d-139">因應措施</span><span class="sxs-lookup"><span data-stu-id="ce00d-139">Workarounds</span></span>

#### <a name="restart-in-between-calls"></a><span data-ttu-id="ce00d-140">在呼叫之間重新開機</span><span class="sxs-lookup"><span data-stu-id="ce00d-140">Restart in between calls</span></span>

<span data-ttu-id="ce00d-141">如果您的呼叫超過20分鐘的時間，而您遇到此問題，請嘗試重新開機您的裝置。</span><span class="sxs-lookup"><span data-stu-id="ce00d-141">If your calls are going over a length of 20 minutes and you are experiencing this issue, try rebooting your device.</span></span> <span data-ttu-id="ce00d-142">在遠端協助電話之間重新開機裝置，將會重新整理您的裝置，並讓裝置恢復正常狀態。</span><span class="sxs-lookup"><span data-stu-id="ce00d-142">Rebooting your device between Remote Assist calls will refresh your device and put it back into a good state.</span></span>

<span data-ttu-id="ce00d-143">若要在 Windows 全像攝影版上快速重新開機裝置 [，版本 21H1](hololens-release-notes.md#windows-holographic-version-21h1) 開啟 [開始] 功能表，並選取 [使用者] 圖示，然後選取 [ **重新開機**]。</span><span class="sxs-lookup"><span data-stu-id="ce00d-143">To quickly restart a device on [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) open the start menu, and select the user icon, then select **Restart**.</span></span>

#### <a name="revert-to-an-older-build"></a><span data-ttu-id="ce00d-144">還原為較舊的組建</span><span class="sxs-lookup"><span data-stu-id="ce00d-144">Revert to an older build</span></span>

<span data-ttu-id="ce00d-145">某些客戶發現，在還原至舊版的作業系統版本時，他們不再遇到此問題。</span><span class="sxs-lookup"><span data-stu-id="ce00d-145">Some customers have found that when reverting to an earlier OS version they no longer experience this issue.</span></span> <span data-ttu-id="ce00d-146">如果您發現您的裝置遇到此問題，請嘗試下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ce00d-146">If you have found that your devices are experiencing this issue, try these steps:</span></span>


<span data-ttu-id="ce00d-147">因應措施：</span><span class="sxs-lookup"><span data-stu-id="ce00d-147">Workarounds:</span></span>

- <span data-ttu-id="ce00d-148">如果您的企業可以使用，則在取用者 Microsoft 帳戶上可支援自動相機上傳。</span><span class="sxs-lookup"><span data-stu-id="ce00d-148">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="ce00d-149">除了您的工作或學校帳戶之外，您還可以登入 Microsoft 帳戶 (OneDrive 應用程式支援雙重登入) 。</span><span class="sxs-lookup"><span data-stu-id="ce00d-149">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="ce00d-150">從 OneDrive 內的 Microsoft 帳戶設定檔，您可以啟用自動的背景相機滾動上傳。</span><span class="sxs-lookup"><span data-stu-id="ce00d-150">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="ce00d-151">如果您無法安全地使用取用者 Microsoft 帳戶自動上傳您的相片，您可以從 OneDrive 應用程式手動將相片上傳至您的工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="ce00d-151">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="ce00d-152">若要這樣做，請確定您已登入 OneDrive 應用程式中的公司或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="ce00d-152">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="ce00d-153">選取 **+** 按鈕，然後選擇 [ **上傳**]。</span><span class="sxs-lookup"><span data-stu-id="ce00d-153">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="ce00d-154">藉由流覽至 [ **圖片] > 相機滾動** 圖，尋找您想要上傳的相片或影片。</span><span class="sxs-lookup"><span data-stu-id="ce00d-154">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="ce00d-155">選取您要上傳的相片或影片，然後選取 [ **開啟** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="ce00d-155">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>


1. [<span data-ttu-id="ce00d-156">下載適用于 Windows 全像20H2 版的組建-5 月2021更新</span><span class="sxs-lookup"><span data-stu-id="ce00d-156">Download the build for Windows Holographic, version 20H2 – May 2021 Update</span></span>](https://aka.ms/hololens2download/10.0.19041.1146)
1. <span data-ttu-id="ce00d-157">遵循 [指示回到先前的作業系統版本](hololens-update-hololens.md#go-back-to-a-previous-version)</span><span class="sxs-lookup"><span data-stu-id="ce00d-157">Follow the [instructions return to a previous OS version](hololens-update-hololens.md#go-back-to-a-previous-version)</span></span>
1. <span data-ttu-id="ce00d-158">請手動或針對許多裝置 [暫停裝置上的作業系統更新](hololens-updates.md#pause-updates-via-device) ，以使用 [延遲至 MDM](hololens-updates.md#configure-an-update-deferral-policy)。</span><span class="sxs-lookup"><span data-stu-id="ce00d-158">Either [pause OS updates on the device manually](hololens-updates.md#pause-updates-via-device) or for many devices use [deferral through MDM](hololens-updates.md#configure-an-update-deferral-policy).</span></span>

[<span data-ttu-id="ce00d-159">返回清單</span><span class="sxs-lookup"><span data-stu-id="ce00d-159">Back to list</span></span>](#list)

## <a name="auto-login-asks-for-log-in"></a><span data-ttu-id="ce00d-160">自動登入要求登入</span><span class="sxs-lookup"><span data-stu-id="ce00d-160">Auto-login asks for log-in</span></span>

<span data-ttu-id="ce00d-161">HoloLens 2 裝置可設定為自動透過 **設定**  ->  **帳戶** 登  ->  **入選項** 登入->，而且在 **必要** 時，將值設為 [**永不**]。</span><span class="sxs-lookup"><span data-stu-id="ce00d-161">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="ce00d-162">使用重大更新（例如功能更新）更新裝置時，某些使用者可能需要再次登入裝置。</span><span class="sxs-lookup"><span data-stu-id="ce00d-162">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span> <span data-ttu-id="ce00d-163">這是 **已知的問題**。</span><span class="sxs-lookup"><span data-stu-id="ce00d-163">This is a **known issue**.</span></span>

<span data-ttu-id="ce00d-164">發生這種情況的範例：</span><span class="sxs-lookup"><span data-stu-id="ce00d-164">Example of when this could occur:</span></span>

- <span data-ttu-id="ce00d-165">將裝置從 Windows 全像2004版 (組建) 19041）更新為 Windows 全像21H1 版， (組建 20346. xxxx) </span><span class="sxs-lookup"><span data-stu-id="ce00d-165">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="ce00d-166">將裝置更新為在相同的主要組建上進行大量更新，例如 Windows 全像 Windows 全像，2004版到 Windows 全像20H2 版</span><span class="sxs-lookup"><span data-stu-id="ce00d-166">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="ce00d-167">將裝置從原廠映射更新為最新影像</span><span class="sxs-lookup"><span data-stu-id="ce00d-167">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="ce00d-168">這應該不會在下列情況中發生：</span><span class="sxs-lookup"><span data-stu-id="ce00d-168">This should not occur during:</span></span>

- <span data-ttu-id="ce00d-169">取得每月服務更新的裝置</span><span class="sxs-lookup"><span data-stu-id="ce00d-169">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="ce00d-170">解決方法：</span><span class="sxs-lookup"><span data-stu-id="ce00d-170">Work around methods:</span></span>

- <span data-ttu-id="ce00d-171">登入方法，例如 PIN、密碼、鳶尾花、Web 驗證或 FIDO2 金鑰。</span><span class="sxs-lookup"><span data-stu-id="ce00d-171">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="ce00d-172">如果無法記住裝置 PIN，而且無法使用其他驗證方法，則使用者可以使用 [手動 reflashing 模式](hololens-recovery.md#manual-procedure)。</span><span class="sxs-lookup"><span data-stu-id="ce00d-172">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

[<span data-ttu-id="ce00d-173">返回清單</span><span class="sxs-lookup"><span data-stu-id="ce00d-173">Back to list</span></span>](#list)

## <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="ce00d-174">無法啟動 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ce00d-174">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="ce00d-175">此問題原本是使用 Microsoft Edge 的出貨版本所建立。</span><span class="sxs-lookup"><span data-stu-id="ce00d-175">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="ce00d-176">此問題可在 [新的 Microsoft Edge](hololens-new-edge.md)中解決。</span><span class="sxs-lookup"><span data-stu-id="ce00d-176">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="ce00d-177">如果不是，請提出意見反應。</span><span class="sxs-lookup"><span data-stu-id="ce00d-177">If it is not, please file feedback.</span></span>

<span data-ttu-id="ce00d-178">少數客戶回報了 Microsoft Edge 無法啟動的問題。</span><span class="sxs-lookup"><span data-stu-id="ce00d-178">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="ce00d-179">針對這些客戶，問題會透過重新開機持續存在，而且無法透過 Windows 或應用程式更新解決。</span><span class="sxs-lookup"><span data-stu-id="ce00d-179">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="ce00d-180">如果您遇到此問題，而且已確認 [Windows 是最](hololens-updates.md#manually-check-for-updates)新狀態，請從 [意見反應中樞應用程式](hololens-feedback.md) 提出 bug，並列出下列類別和子類別：安裝和更新 > 下載、安裝和設定 Windows Update。</span><span class="sxs-lookup"><span data-stu-id="ce00d-180">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="ce00d-181">沒有任何已知的因應措施，因為我們目前無法解決問題的根本原因。</span><span class="sxs-lookup"><span data-stu-id="ce00d-181">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="ce00d-182">透過意見反應中樞提出 bug 將有助於進行調查！</span><span class="sxs-lookup"><span data-stu-id="ce00d-182">Filing a bug via Feedback Hub will help our investigation!</span></span> <span data-ttu-id="ce00d-183">這是 **已知的問題**。</span><span class="sxs-lookup"><span data-stu-id="ce00d-183">This is a **known issue**.</span></span>

[<span data-ttu-id="ce00d-184">返回清單</span><span class="sxs-lookup"><span data-stu-id="ce00d-184">Back to list</span></span>](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a><span data-ttu-id="ce00d-185">鍵盤未切換至特殊字元</span><span class="sxs-lookup"><span data-stu-id="ce00d-185">Keyboard doesn't switch to special characters</span></span>

<span data-ttu-id="ce00d-186">在 OOBE 期間發生問題，當使用者選擇了工作或學校帳戶，並輸入其密碼時，藉由使用 [123] &按鈕並不會變更為特殊字元，藉以嘗試切換至鍵盤上的特殊字元。</span><span class="sxs-lookup"><span data-stu-id="ce00d-186">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> <span data-ttu-id="ce00d-187">這是 **已知的問題**。</span><span class="sxs-lookup"><span data-stu-id="ce00d-187">This is a **known issue**.</span></span>

<span data-ttu-id="ce00d-188">解決辦法：</span><span class="sxs-lookup"><span data-stu-id="ce00d-188">Work-arounds:</span></span>
-   <span data-ttu-id="ce00d-189">關閉鍵盤，然後藉由點擊文字欄位將它重新開啟。</span><span class="sxs-lookup"><span data-stu-id="ce00d-189">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="ce00d-190">輸入您的密碼不正確。</span><span class="sxs-lookup"><span data-stu-id="ce00d-190">Incorrectly enter your password.</span></span> <span data-ttu-id="ce00d-191">下一次 relaunched 鍵盤時，它會如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="ce00d-191">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="ce00d-192">Web 驗證，關閉鍵盤，然後選取 [ **從另一部裝置登入**]。</span><span class="sxs-lookup"><span data-stu-id="ce00d-192">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="ce00d-193">如果只輸入數位，使用者可以按住某些按鍵以開啟展開的功能表。</span><span class="sxs-lookup"><span data-stu-id="ce00d-193">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="ce00d-194">使用 USB 鍵盤。</span><span class="sxs-lookup"><span data-stu-id="ce00d-194">Using a USB keyboard.</span></span>

<span data-ttu-id="ce00d-195">這不會影響：</span><span class="sxs-lookup"><span data-stu-id="ce00d-195">This does not affect:</span></span>
- <span data-ttu-id="ce00d-196">選擇使用個人帳戶的使用者。</span><span class="sxs-lookup"><span data-stu-id="ce00d-196">Users who choose to use a personal account.</span></span>

[<span data-ttu-id="ce00d-197">返回清單</span><span class="sxs-lookup"><span data-stu-id="ce00d-197">Back to list</span></span>](#list)


## <a name="downloading-locked-files-doesnt-error"></a><span data-ttu-id="ce00d-198">下載鎖定的檔案並不會發生錯誤</span><span class="sxs-lookup"><span data-stu-id="ce00d-198">Downloading locked files doesn't error</span></span>
> <span data-ttu-id="ce00d-199">!請注意，這是 Windows 測試人員 build，version 20348.1403 中已修正的 **已知問題** 。</span><span class="sxs-lookup"><span data-stu-id="ce00d-199">!NOTE This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span>


<span data-ttu-id="ce00d-200">在先前的 Windows 全像組建中，嘗試下載鎖定的檔案時，結果會是 HTTP 錯誤網頁。</span><span class="sxs-lookup"><span data-stu-id="ce00d-200">In previous builds of Windows Holographic, when attempting to download a locked file, the result would be an HTTP error page.</span></span> <span data-ttu-id="ce00d-201">在 Windows 全像版本21H1 更新中，嘗試下載鎖定的檔案會導致看不到任何東西，也就是檔案不會下載，也不會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="ce00d-201">In the Windows Holographic, version 21H1 update, trying to download a locked file results in nothing visible happening—the file doesn’t download and there’s no error.</span></span> 

[<span data-ttu-id="ce00d-202">返回清單</span><span class="sxs-lookup"><span data-stu-id="ce00d-202">Back to list</span></span>](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a><span data-ttu-id="ce00d-203">裝置入口網站檔案上傳/下載超時</span><span class="sxs-lookup"><span data-stu-id="ce00d-203">Device Portal file upload/download times out</span></span>
> <span data-ttu-id="ce00d-204">!請注意，這是 Windows 測試人員 build，version 20348.1403 中已修正的 **已知問題** 。</span><span class="sxs-lookup"><span data-stu-id="ce00d-204">!NOTE This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span> <span data-ttu-id="ce00d-205">如果您先前已在因應措施中停用 SSL 連線，強烈建議您重新啟用 SSL 連線。</span><span class="sxs-lookup"><span data-stu-id="ce00d-205">If you previously disabled SSL Connection as part of the workaround, we highly recommend you re-enable it.</span></span>


<span data-ttu-id="ce00d-206">某些客戶在嘗試上傳或下載檔案時，該作業可能會似乎停止回應，而不會完成時間。</span><span class="sxs-lookup"><span data-stu-id="ce00d-206">Some customers have found, when attempting to upload or download files, the operation might appear to hang and then time out or never complete.</span></span> <span data-ttu-id="ce00d-207">這與「檔案鎖定」的[已知問題](#downloading-locked-files-doesnt-error) 不同，這會影響 Windows 全像版本2004、20H2 和21H1 的市場內建。</span><span class="sxs-lookup"><span data-stu-id="ce00d-207">This is separate from the '[file locked' known issue](#downloading-locked-files-doesnt-error) -- this affects Windows Holographic, versions 2004, 20H2 and 21H1 in-market builds.</span></span> <span data-ttu-id="ce00d-208">問題的根本原因是裝置入口網站處理某些要求時發生錯誤，而且在使用 HTTPs （預設值）時，最常受到持續的點擊。</span><span class="sxs-lookup"><span data-stu-id="ce00d-208">The problem has been root caused to a bug in Device Portal's handling of certain requests, and is most consistently hit when using https, which is the default.</span></span> 

### <a name="workaround"></a><span data-ttu-id="ce00d-209">因應措施</span><span class="sxs-lookup"><span data-stu-id="ce00d-209">Workaround</span></span>

<span data-ttu-id="ce00d-210">此因應措施（同樣適用于 Wi-Fi 和 UsbNcm）是停用 [SSL 連線] 底下的 [必要] 選項。</span><span class="sxs-lookup"><span data-stu-id="ce00d-210">This workaround, which applies equally to Wi-Fi and UsbNcm, is to disable the "required" option under "SSL Connection".</span></span> <span data-ttu-id="ce00d-211">若要這樣做，請流覽至 [裝置入口網站]、[ **系統**]，然後選取 [ **喜好** 設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="ce00d-211">To do so, navigate to Device Portal, **System**, and select the **Preferences** page.</span></span> <span data-ttu-id="ce00d-212">在 [ **裝置安全性** ] 區段中，找出 [ **SSL** 連線]，然後取消核取以停用 **必要** 項。</span><span class="sxs-lookup"><span data-stu-id="ce00d-212">In the **Device Security** section, locate **SSL Connection**, and uncheck to disable **Required**.</span></span>

<span data-ttu-id="ce00d-213">使用者接著應該移至 HTTP://，而不是 HTTPs:// (IP 位址) 和檔案上傳和下載等功能都能運作。</span><span class="sxs-lookup"><span data-stu-id="ce00d-213">The user should then go to http://, not https:// (IP address) and features like file upload and download will work.</span></span>

[<span data-ttu-id="ce00d-214">返回清單</span><span class="sxs-lookup"><span data-stu-id="ce00d-214">Back to list</span></span>](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a><span data-ttu-id="ce00d-215">在使用 Insider build 進行閃爍的裝置上，從 Insider preview 取消註冊後的藍色畫面</span><span class="sxs-lookup"><span data-stu-id="ce00d-215">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>

<span data-ttu-id="ce00d-216">這是影響的問題，它會影響屬於 Insider preview 組建的使用者、使用新的 insider preview 組建 reflashed 其 HoloLens 2，然後從 Insider 計畫取消註冊。</span><span class="sxs-lookup"><span data-stu-id="ce00d-216">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> <span data-ttu-id="ce00d-217">這是 **已知的問題**。</span><span class="sxs-lookup"><span data-stu-id="ce00d-217">This is a **known issue**.</span></span>

<span data-ttu-id="ce00d-218">這不會影響：</span><span class="sxs-lookup"><span data-stu-id="ce00d-218">This does not affect:</span></span>
- <span data-ttu-id="ce00d-219">未註冊 Windows 測試人員中的使用者</span><span class="sxs-lookup"><span data-stu-id="ce00d-219">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="ce00d-220">業內 人士：</span><span class="sxs-lookup"><span data-stu-id="ce00d-220">Insiders:</span></span>
    - <span data-ttu-id="ce00d-221">如果裝置已註冊，因為 Insider build 是 version 18362. x</span><span class="sxs-lookup"><span data-stu-id="ce00d-221">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="ce00d-222">如果他們將 Insider 已簽署的19041建立並在測試人員計畫中保持註冊，</span><span class="sxs-lookup"><span data-stu-id="ce00d-222">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="ce00d-223">解決辦法：</span><span class="sxs-lookup"><span data-stu-id="ce00d-223">Work-around:</span></span> 
- <span data-ttu-id="ce00d-224">避免此問題</span><span class="sxs-lookup"><span data-stu-id="ce00d-224">Avoid the issue</span></span> 
    - <span data-ttu-id="ce00d-225">Flash 非 insider build。</span><span class="sxs-lookup"><span data-stu-id="ce00d-225">Flash a non-insider build.</span></span> <span data-ttu-id="ce00d-226">其中一個一般的每月更新。</span><span class="sxs-lookup"><span data-stu-id="ce00d-226">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="ce00d-227">掌握 Insider Preview</span><span class="sxs-lookup"><span data-stu-id="ce00d-227">Stay on Insider Preview</span></span>
- <span data-ttu-id="ce00d-228">重新刷新裝置</span><span class="sxs-lookup"><span data-stu-id="ce00d-228">Reflash the device</span></span>

    1. <span data-ttu-id="ce00d-229">請在未連線的情況下完全關閉，以手動方式將 [HoloLens 2 進入閃爍模式](hololens-recovery.md) 。</span><span class="sxs-lookup"><span data-stu-id="ce00d-229">Put the [HoloLens 2 into flashing mode](hololens-recovery.md) manually by fully powering down while not connect.</span></span> <span data-ttu-id="ce00d-230">然後按住音量，然後按一下 [電源] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="ce00d-230">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="ce00d-231">連接到電腦並開啟 Advanced Recovery 隨附。</span><span class="sxs-lookup"><span data-stu-id="ce00d-231">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="ce00d-232">將 HoloLens 2 快閃至預設組建。</span><span class="sxs-lookup"><span data-stu-id="ce00d-232">Flash the HoloLens 2 to the default build.</span></span>

[<span data-ttu-id="ce00d-233">返回清單</span><span class="sxs-lookup"><span data-stu-id="ce00d-233">Back to list</span></span>](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a><span data-ttu-id="ce00d-234">OneDrive 不會自動上傳圖片</span><span class="sxs-lookup"><span data-stu-id="ce00d-234">OneDrive doesn't automatically upload pictures</span></span>

<span data-ttu-id="ce00d-235">適用于 HoloLens 的 OneDrive 應用程式不支援工作或學校帳戶的自動攝影機上傳。</span><span class="sxs-lookup"><span data-stu-id="ce00d-235">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span> <span data-ttu-id="ce00d-236">這是 **已知的問題**。</span><span class="sxs-lookup"><span data-stu-id="ce00d-236">This is a **known issue**.</span></span>

<span data-ttu-id="ce00d-237">因應措施：</span><span class="sxs-lookup"><span data-stu-id="ce00d-237">Workarounds:</span></span>

- <span data-ttu-id="ce00d-238">如果您的企業可以使用，則在取用者 Microsoft 帳戶上可支援自動相機上傳。</span><span class="sxs-lookup"><span data-stu-id="ce00d-238">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="ce00d-239">除了您的工作或學校帳戶之外，您還可以登入 Microsoft 帳戶 (OneDrive 應用程式支援雙重登入) 。</span><span class="sxs-lookup"><span data-stu-id="ce00d-239">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="ce00d-240">從 OneDrive 內的 Microsoft 帳戶設定檔，您可以啟用自動的背景相機滾動上傳。</span><span class="sxs-lookup"><span data-stu-id="ce00d-240">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="ce00d-241">如果您無法安全地使用取用者 Microsoft 帳戶自動上傳您的相片，您可以從 OneDrive 應用程式手動將相片上傳至您的工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="ce00d-241">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="ce00d-242">若要這樣做，請確定您已登入 OneDrive 應用程式中的公司或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="ce00d-242">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="ce00d-243">選取 **+** 按鈕，然後選擇 [ **上傳**]。</span><span class="sxs-lookup"><span data-stu-id="ce00d-243">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="ce00d-244">藉由流覽至 [ **圖片] > 相機滾動** 圖，尋找您想要上傳的相片或影片。</span><span class="sxs-lookup"><span data-stu-id="ce00d-244">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="ce00d-245">選取您要上傳的相片或影片，然後選取 [ **開啟** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="ce00d-245">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

[<span data-ttu-id="ce00d-246">返回清單</span><span class="sxs-lookup"><span data-stu-id="ce00d-246">Back to list</span></span>](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a><span data-ttu-id="ce00d-247">HoloLens 沒有回應或無法啟動</span><span class="sxs-lookup"><span data-stu-id="ce00d-247">HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="ce00d-248">如果您的 HoloLens 無法啟動：</span><span class="sxs-lookup"><span data-stu-id="ce00d-248">If your HoloLens won't start:</span></span>

- <span data-ttu-id="ce00d-249">如果電源按鈕旁的 Led 沒有亮，或只有一個 LED 短暫閃爍，您可能需要向 [HoloLens 收費。](hololens2-charging.md#charging-the-device)</span><span class="sxs-lookup"><span data-stu-id="ce00d-249">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens2-charging.md#charging-the-device)</span></span>
- <span data-ttu-id="ce00d-250">當您按下電源按鈕時，如果 Led 亮起，但看不到顯示器上的任何事物，請 [進行裝置的硬重設](hololens-recovery.md#hard-reset-procedure)。</span><span class="sxs-lookup"><span data-stu-id="ce00d-250">If the LEDs light up when you press the power button but you can't see anything on the displays, [do a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="ce00d-251">如果您的 HoloLens 變成凍結或沒有回應：</span><span class="sxs-lookup"><span data-stu-id="ce00d-251">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="ce00d-252">藉由按下電源按鈕，直到所有五個 Led 關閉，或15秒（如果 Led 沒有回應），關閉 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="ce00d-252">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="ce00d-253">若要開始 HoloLens，請再次按下電源按鈕。</span><span class="sxs-lookup"><span data-stu-id="ce00d-253">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="ce00d-254">如果這些步驟都沒有作用，您可以嘗試 [復原 HoloLens 2 裝置](hololens-recovery.md) 或 [HoloLens (第一代) 裝置。](hololens1-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="ce00d-254">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

[<span data-ttu-id="ce00d-255">返回清單</span><span class="sxs-lookup"><span data-stu-id="ce00d-255">Back to list</span></span>](#list)

## <a name="low-disk-space-error"></a><span data-ttu-id="ce00d-256">「磁碟空間不足」錯誤</span><span class="sxs-lookup"><span data-stu-id="ce00d-256">"Low Disk Space" error</span></span>

<span data-ttu-id="ce00d-257">您必須執行下列一或多個動作，以釋出一些儲存空間：</span><span class="sxs-lookup"><span data-stu-id="ce00d-257">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="ce00d-258">刪除一些未使用的空間。</span><span class="sxs-lookup"><span data-stu-id="ce00d-258">Delete some unused spaces.</span></span> <span data-ttu-id="ce00d-259">移至 [**設定**  >  **系統**  >  **空間**]，選取您不再需要的空間，然後選取 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="ce00d-259">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="ce00d-260">移除您所放置的一些全息。</span><span class="sxs-lookup"><span data-stu-id="ce00d-260">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="ce00d-261">從相片應用程式刪除部分圖片和影片。</span><span class="sxs-lookup"><span data-stu-id="ce00d-261">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="ce00d-262">從 HoloLens 卸載一些應用程式。</span><span class="sxs-lookup"><span data-stu-id="ce00d-262">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="ce00d-263">在 **所有應用程式** 清單中，按住您要卸載的應用程式，然後選取 [ **卸載**]。</span><span class="sxs-lookup"><span data-stu-id="ce00d-263">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

[<span data-ttu-id="ce00d-264">返回清單</span><span class="sxs-lookup"><span data-stu-id="ce00d-264">Back to list</span></span>](#list)

## <a name="calibration-fails"></a><span data-ttu-id="ce00d-265">校正失敗</span><span class="sxs-lookup"><span data-stu-id="ce00d-265">Calibration fails</span></span>

<span data-ttu-id="ce00d-266">校正應該適用于大部分的人，但在某些情況下，校正會失敗。</span><span class="sxs-lookup"><span data-stu-id="ce00d-266">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="ce00d-267">校正失敗的一些可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="ce00d-267">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="ce00d-268">因應注意力而不是遵循校正目標</span><span class="sxs-lookup"><span data-stu-id="ce00d-268">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="ce00d-269">中途或有劃痕的裝置面板或裝置面板未正確定位</span><span class="sxs-lookup"><span data-stu-id="ce00d-269">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="ce00d-270">中途或有劃痕的眼鏡</span><span class="sxs-lookup"><span data-stu-id="ce00d-270">Dirty or scratched glasses</span></span>
- <span data-ttu-id="ce00d-271">特定類型的連絡人鏡頭和眼鏡 (彩色連絡人鏡頭、某些 toric contact 鏡頭、IR 封鎖眼鏡、一些高處方眼鏡、太陽眼鏡或類似的) </span><span class="sxs-lookup"><span data-stu-id="ce00d-271">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="ce00d-272">更多發音的構成和一些 eyelash 延伸模組</span><span class="sxs-lookup"><span data-stu-id="ce00d-272">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="ce00d-273">Eyeglass 框架，如果他們封鎖裝置看不見您的眼睛</span><span class="sxs-lookup"><span data-stu-id="ce00d-273">Hair or thick eyeglass frames if they're blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="ce00d-274">某些眼睛生理學、眼睛狀況或眼睛外科，例如窄眼、long eyelashes、amblyopia、nystagmus、某些案例 LASIK 或其他眼睛手術</span><span class="sxs-lookup"><span data-stu-id="ce00d-274">Certain eye physiology, eye conditions, or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="ce00d-275">如果校正失敗，請嘗試：</span><span class="sxs-lookup"><span data-stu-id="ce00d-275">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="ce00d-276">清除您的裝置面板</span><span class="sxs-lookup"><span data-stu-id="ce00d-276">Cleaning your device visor</span></span>
- <span data-ttu-id="ce00d-277">清除您的眼鏡</span><span class="sxs-lookup"><span data-stu-id="ce00d-277">Cleaning your glasses</span></span>
- <span data-ttu-id="ce00d-278">盡可能將您的裝置面板推送到最接近您的眼睛</span><span class="sxs-lookup"><span data-stu-id="ce00d-278">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="ce00d-279">將面板中的物件移出 (例如頭髮) </span><span class="sxs-lookup"><span data-stu-id="ce00d-279">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="ce00d-280">開啟房間內的燈光或移出直接的直射</span><span class="sxs-lookup"><span data-stu-id="ce00d-280">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="ce00d-281">如果您遵循所有指導方針，而且校正仍失敗，您可以在 [設定] 中停用校正提示。</span><span class="sxs-lookup"><span data-stu-id="ce00d-281">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="ce00d-282">也請在 [意見反應中樞](hololens-feedback.md)中提出意見反應，讓我們知道。</span><span class="sxs-lookup"><span data-stu-id="ce00d-282">Also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="ce00d-283">另請參閱[影像色彩或亮度疑難排解](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ce00d-283">Also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="ce00d-284">設定 IPD 並不適用于 HoloLens 2，因為眼睛的位置是由系統計算。</span><span class="sxs-lookup"><span data-stu-id="ce00d-284">Setting IPD is not applicable for HoloLens 2, since eye positions are computed by the system.</span></span> 

[<span data-ttu-id="ce00d-285">返回清單</span><span class="sxs-lookup"><span data-stu-id="ce00d-285">Back to list</span></span>](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a><span data-ttu-id="ce00d-286">無法登入，因為先前已為他人設定過 HoloLens</span><span class="sxs-lookup"><span data-stu-id="ce00d-286">Can't sign in because my HoloLens was previously set up for someone else</span></span>

<span data-ttu-id="ce00d-287">您可以 [讓裝置進入 **閃爍模式** ，並使用先進](hololens-recovery.md#clean-reflash-the-device) 的復原輔助來復原裝置。</span><span class="sxs-lookup"><span data-stu-id="ce00d-287">You can [put the device into **Flashing Mode** and use Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) to recover the device.</span></span>

[<span data-ttu-id="ce00d-288">返回清單</span><span class="sxs-lookup"><span data-stu-id="ce00d-288">Back to list</span></span>](#list)


## <a name="unity-isnt-working"></a><span data-ttu-id="ce00d-289">Unity 無法運作</span><span class="sxs-lookup"><span data-stu-id="ce00d-289">Unity isn't working</span></span>

- <span data-ttu-id="ce00d-290">請參閱安裝適用于最新版本之 Unity 的 [工具](/windows/mixed-reality/install-the-tools) ，建議用於 HoloLens 開發。</span><span class="sxs-lookup"><span data-stu-id="ce00d-290">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="ce00d-291">有關 Unity HoloLens Technical Preview 的已知問題記載于 [HoloLens Unity 論壇](https://forum.unity3d.com/threads/known-issues.394627/)中。</span><span class="sxs-lookup"><span data-stu-id="ce00d-291">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

[<span data-ttu-id="ce00d-292">返回清單</span><span class="sxs-lookup"><span data-stu-id="ce00d-292">Back to list</span></span>](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a><span data-ttu-id="ce00d-293">Windows 裝置入口網站無法正常運作</span><span class="sxs-lookup"><span data-stu-id="ce00d-293">Windows Device Portal isn't working correctly</span></span>

- <span data-ttu-id="ce00d-294">Mixed Reality capture 中的即時預覽功能可能會顯示幾秒鐘的延遲時間。</span><span class="sxs-lookup"><span data-stu-id="ce00d-294">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="ce00d-295">在 [虛擬輸入] 頁面上，[虛擬手勢] 區段底下的手勢和 Scroll 控制項無法運作。</span><span class="sxs-lookup"><span data-stu-id="ce00d-295">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="ce00d-296">使用這些專案將不會有任何作用。</span><span class="sxs-lookup"><span data-stu-id="ce00d-296">Using them will have no effect.</span></span> <span data-ttu-id="ce00d-297">虛擬輸入頁面上的虛擬鍵盤可正常運作。</span><span class="sxs-lookup"><span data-stu-id="ce00d-297">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="ce00d-298">在設定中啟用開發人員模式之後，可能需要幾秒鐘的時間，才會啟用裝置入口網站的開啟。</span><span class="sxs-lookup"><span data-stu-id="ce00d-298">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

[<span data-ttu-id="ce00d-299">返回清單</span><span class="sxs-lookup"><span data-stu-id="ce00d-299">Back to list</span></span>](#list)

## <a name="emulator"></a><span data-ttu-id="ce00d-300">模擬器</span><span class="sxs-lookup"><span data-stu-id="ce00d-300">Emulator</span></span>
### <a name="the-hololens-emulator-isnt-working"></a><span data-ttu-id="ce00d-301">HoloLens 模擬器無法運作</span><span class="sxs-lookup"><span data-stu-id="ce00d-301">The HoloLens Emulator isn't working</span></span>

<span data-ttu-id="ce00d-302">HoloLens 模擬器的相關資訊位於我們的開發人員檔中。</span><span class="sxs-lookup"><span data-stu-id="ce00d-302">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="ce00d-303">深入瞭解 [HoloLens 模擬器的疑難排解](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)。</span><span class="sxs-lookup"><span data-stu-id="ce00d-303">Read more about [troubleshooting the HoloLens emulator](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).</span></span>


- <span data-ttu-id="ce00d-304">並非 Microsoft Store 中的所有應用程式都與模擬器相容。</span><span class="sxs-lookup"><span data-stu-id="ce00d-304">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="ce00d-305">例如，在模擬器上無法播放年輕 Conker 和片段。</span><span class="sxs-lookup"><span data-stu-id="ce00d-305">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="ce00d-306">您無法在模擬器中使用電腦網路攝影機。</span><span class="sxs-lookup"><span data-stu-id="ce00d-306">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="ce00d-307">Windows 裝置入口網站的即時預覽功能無法與模擬器搭配使用。</span><span class="sxs-lookup"><span data-stu-id="ce00d-307">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="ce00d-308">您仍然可以捕獲混合的現實影片和影像。</span><span class="sxs-lookup"><span data-stu-id="ce00d-308">You can still capture Mixed Reality videos and images.</span></span>

[<span data-ttu-id="ce00d-309">返回清單</span><span class="sxs-lookup"><span data-stu-id="ce00d-309">Back to list</span></span>](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a><span data-ttu-id="ce00d-310">我找不到或無法使用鍵盤來輸入 HoloLens 2 模擬器</span><span class="sxs-lookup"><span data-stu-id="ce00d-310">I cannot find or use the keyboard to type in the HoloLens 2 Emulator</span></span>

<span data-ttu-id="ce00d-311">*即將推出*</span><span class="sxs-lookup"><span data-stu-id="ce00d-311">*Coming soon*</span></span>

[<span data-ttu-id="ce00d-312">返回清單</span><span class="sxs-lookup"><span data-stu-id="ce00d-312">Back to list</span></span>](#list)

## <a name="voice-commands-arent-working"></a><span data-ttu-id="ce00d-313">語音命令無法運作</span><span class="sxs-lookup"><span data-stu-id="ce00d-313">Voice commands aren't working</span></span>

<span data-ttu-id="ce00d-314">如果 Cortana 未回應您的語音命令，請確定已開啟 Cortana。</span><span class="sxs-lookup"><span data-stu-id="ce00d-314">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="ce00d-315">在所有應用程式清單中，選取 [ **Cortana**  >  **功能表**  >  **筆記本**  >  **設定**] 以進行變更。</span><span class="sxs-lookup"><span data-stu-id="ce00d-315">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="ce00d-316">若要深入瞭解您可以說的內容，請參閱搭配 [HoloLens 使用您的語音](hololens-cortana.md)。</span><span class="sxs-lookup"><span data-stu-id="ce00d-316">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

<span data-ttu-id="ce00d-317">在 HoloLens (第1代) 中，內建的語音辨識無法設定。</span><span class="sxs-lookup"><span data-stu-id="ce00d-317">On HoloLens (1st gen), built-in speech recognition is not configurable.</span></span> <span data-ttu-id="ce00d-318">它一定會開啟。</span><span class="sxs-lookup"><span data-stu-id="ce00d-318">It is always turned on.</span></span> <span data-ttu-id="ce00d-319">在 HoloLens 2 上，您可以選擇是否要在裝置設定期間開啟語音辨識和 Cortana。</span><span class="sxs-lookup"><span data-stu-id="ce00d-319">On HoloLens 2, you can choose whether to turn on both speech recognition and Cortana during device setup.</span></span>

<span data-ttu-id="ce00d-320">如果您的 HoloLens 2 沒有回應您的聲音，請確定已開啟 [語音辨識]。</span><span class="sxs-lookup"><span data-stu-id="ce00d-320">If your HoloLens 2 is not responding to your voice, make sure Speech recognition is turned on.</span></span> <span data-ttu-id="ce00d-321">移至 [**開始**  >  **設定**  >  **隱私權**  >  **語音**]，然後開啟 [**語音辨識**]。</span><span class="sxs-lookup"><span data-stu-id="ce00d-321">Go to **Start** > **Settings** > **Privacy** > **Speech** and turn on **Speech recognition**.</span></span>

[<span data-ttu-id="ce00d-322">返回清單</span><span class="sxs-lookup"><span data-stu-id="ce00d-322">Back to list</span></span>](#list)

## <a name="hand-input-isnt-working"></a><span data-ttu-id="ce00d-323">手輸入無法運作</span><span class="sxs-lookup"><span data-stu-id="ce00d-323">Hand input isn't working</span></span>

<span data-ttu-id="ce00d-324">為了確保 HoloLens 可以看到您的手，您需要將它們保留在手勢框架中。</span><span class="sxs-lookup"><span data-stu-id="ce00d-324">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="ce00d-325">Mixed Reality Home 提供的意見反應可讓您知道何時追蹤您的手。</span><span class="sxs-lookup"><span data-stu-id="ce00d-325">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="ce00d-326">不同的 HoloLens 版本上的意見反應不同：</span><span class="sxs-lookup"><span data-stu-id="ce00d-326">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="ce00d-327">在 HoloLens (第1代) 中，注視游標會從點變更為環形</span><span class="sxs-lookup"><span data-stu-id="ce00d-327">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="ce00d-328">在 HoloLens 2 上，當您的手接近某個平板電腦時，會出現 fingertip 游標，而且當平板不再出現時，會出現一張光線</span><span class="sxs-lookup"><span data-stu-id="ce00d-328">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="ce00d-329">許多沉浸式應用程式都遵循類似于混合現實首頁的輸入模式。</span><span class="sxs-lookup"><span data-stu-id="ce00d-329">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="ce00d-330">深入瞭解如何在 [HoloLens (第1代) ](hololens1-basic-usage.md#use-hololens-with-your-hands) 和 [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame)上使用手動輸入。</span><span class="sxs-lookup"><span data-stu-id="ce00d-330">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="ce00d-331">如果您有佩戴手套，請注意某些類型的手套無法與手動追蹤搭配使用。</span><span class="sxs-lookup"><span data-stu-id="ce00d-331">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="ce00d-332">常見的範例是黑色橡膠手套，其通常會吸收紅外線燈，且深度相機不會挑選。</span><span class="sxs-lookup"><span data-stu-id="ce00d-332">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="ce00d-333">如果您的工作牽涉到橡膠手套，建議您嘗試較淺的色彩，例如藍色或灰色。</span><span class="sxs-lookup"><span data-stu-id="ce00d-333">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="ce00d-334">另一個例子是大型 baggy 手套，這通常會遮蔽您手的形狀。</span><span class="sxs-lookup"><span data-stu-id="ce00d-334">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="ce00d-335">建議您盡可能使用可作為表單調整的手套以獲得最佳結果。</span><span class="sxs-lookup"><span data-stu-id="ce00d-335">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="ce00d-336">如果您的面板有指紋或塗抹，請使用 HoloLens 隨附的 microfiber 清潔抹布，以輕輕地清除面板。</span><span class="sxs-lookup"><span data-stu-id="ce00d-336">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

[<span data-ttu-id="ce00d-337">返回清單</span><span class="sxs-lookup"><span data-stu-id="ce00d-337">Back to list</span></span>](#list)

## <a name="cant-connect-to-wi-fi"></a><span data-ttu-id="ce00d-338">無法連接到 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="ce00d-338">Can't connect to Wi-Fi</span></span>

<span data-ttu-id="ce00d-339">如果您無法將 HoloLens 連接到 Wi-Fi 網路，請嘗試下列一些事項：</span><span class="sxs-lookup"><span data-stu-id="ce00d-339">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

- <span data-ttu-id="ce00d-340">請確定 Wi-Fi 已開啟。</span><span class="sxs-lookup"><span data-stu-id="ce00d-340">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="ce00d-341">若要檢查，請使用開始手勢，然後選取 [**設定**  >  **網路 &amp; 網際網路**  >  **wi-fi**]。</span><span class="sxs-lookup"><span data-stu-id="ce00d-341">To check, use the Start gesture, then select **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="ce00d-342">如果 Wi-Fi 是開啟的，請嘗試關閉它，然後再重新開啟。</span><span class="sxs-lookup"><span data-stu-id="ce00d-342">If Wi-Fi is on, try turning it off and then on again.</span></span>
- <span data-ttu-id="ce00d-343">移到較靠近路由器或存取點的位置。</span><span class="sxs-lookup"><span data-stu-id="ce00d-343">Move closer to the router or access point.</span></span>
- <span data-ttu-id="ce00d-344">重新開機 Wi-Fi 路由器，然後 [重新開機 HoloLens](hololens-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="ce00d-344">Restart your Wi-Fi router, then [restart HoloLens](hololens-recovery.md).</span></span> <span data-ttu-id="ce00d-345">請嘗試重新連線。</span><span class="sxs-lookup"><span data-stu-id="ce00d-345">Try connecting again.</span></span>
- <span data-ttu-id="ce00d-346">如果上述專案都無法運作，請檢查以確定您的路由器使用的是最新的固件。</span><span class="sxs-lookup"><span data-stu-id="ce00d-346">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="ce00d-347">您可以在製造商網站上找到此資訊。</span><span class="sxs-lookup"><span data-stu-id="ce00d-347">You can find this information on the manufacturer website.</span></span>

[<span data-ttu-id="ce00d-348">返回清單</span><span class="sxs-lookup"><span data-stu-id="ce00d-348">Back to list</span></span>](#list)
## <a name="bluetooth-devices-arent-pairing"></a><span data-ttu-id="ce00d-349">藍牙裝置未配對</span><span class="sxs-lookup"><span data-stu-id="ce00d-349">Bluetooth devices aren't pairing</span></span>

<span data-ttu-id="ce00d-350">如果您在 [配對藍牙裝置](hololens-connect-devices.md)時遇到問題，請嘗試下列動作：</span><span class="sxs-lookup"><span data-stu-id="ce00d-350">If you're having problems [pairing a Bluetooth device](hololens-connect-devices.md), try the following:</span></span>

- <span data-ttu-id="ce00d-351">移至 [**設定**  >  **裝置**]，並確定已開啟藍牙。</span><span class="sxs-lookup"><span data-stu-id="ce00d-351">Go to **Settings** > **Devices**, and make sure that Bluetooth is turned on.</span></span> <span data-ttu-id="ce00d-352">如果是，請將它關閉，然後再重新開啟。</span><span class="sxs-lookup"><span data-stu-id="ce00d-352">If it is, turn it off and on again.</span></span>
- <span data-ttu-id="ce00d-353">請確定您的藍牙裝置已完全收費，或有全新的電池。</span><span class="sxs-lookup"><span data-stu-id="ce00d-353">Make sure that your Bluetooth device is fully charged or has fresh batteries.</span></span>
- <span data-ttu-id="ce00d-354">如果您仍然無法連線，請 [重新開機 HoloLens](hololens-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="ce00d-354">If you still can't connect, [restart the HoloLens](hololens-recovery.md).</span></span>

[<span data-ttu-id="ce00d-355">返回清單</span><span class="sxs-lookup"><span data-stu-id="ce00d-355">Back to list</span></span>](#list)

## <a name="usb-c-microphone-isnt-working"></a><span data-ttu-id="ce00d-356">USB-C 麥克風無法運作</span><span class="sxs-lookup"><span data-stu-id="ce00d-356">USB-C Microphone isn't working</span></span>
<span data-ttu-id="ce00d-357">請注意，某些 USB C 麥克風錯誤地將本身視為麥克風 *和* 說話者。</span><span class="sxs-lookup"><span data-stu-id="ce00d-357">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="ce00d-358">這是麥克風的問題，而不是 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="ce00d-358">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="ce00d-359">將其中一個麥克風插入 HoloLens 時，可能會遺失音效。</span><span class="sxs-lookup"><span data-stu-id="ce00d-359">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="ce00d-360">幸運的是，有一個簡單的修正程式。</span><span class="sxs-lookup"><span data-stu-id="ce00d-360">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="ce00d-361">在 [**設定**  ->  **系統**  ->  **音效**] 中，將內建的喇叭明確設定 **(類比功能音訊驅動程式)** 作為 **預設裝置**。</span><span class="sxs-lookup"><span data-stu-id="ce00d-361">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="ce00d-362">HoloLens 應該記得這項設定，即使已移除麥克風，稍後再重新連線也是如此。</span><span class="sxs-lookup"><span data-stu-id="ce00d-362">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![疑難排解 USB-C 麥克風](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a><span data-ttu-id="ce00d-364">在設定中列為可用的裝置無法運作</span><span class="sxs-lookup"><span data-stu-id="ce00d-364">Devices listed as available in Settings don't work</span></span>

<span data-ttu-id="ce00d-365">HoloLens (第1代) 不支援藍牙音訊設定檔。</span><span class="sxs-lookup"><span data-stu-id="ce00d-365">HoloLens (1st gen) doesn't support Bluetooth audio profiles.</span></span> <span data-ttu-id="ce00d-366">藍牙音訊裝置（例如喇叭和耳機）在 HoloLens 設定中可能會顯示為可用，但不受支援。</span><span class="sxs-lookup"><span data-stu-id="ce00d-366">Bluetooth audio devices, such as speakers and headsets, may appear as available in HoloLens settings, but they aren't supported.</span></span>

<span data-ttu-id="ce00d-367">HoloLens 2 支援適用于身歷聲播放的藍牙 A2DP 音訊設定檔。</span><span class="sxs-lookup"><span data-stu-id="ce00d-367">HoloLens 2 supports the Bluetooth A2DP audio profile for stereo playback.</span></span> <span data-ttu-id="ce00d-368">HoloLens 2 不支援可從藍牙周邊啟用麥克風捕捉的藍牙手入設定檔。</span><span class="sxs-lookup"><span data-stu-id="ce00d-368">The Bluetooth Hands Free profile which enables microphone capture from a Bluetooth peripheral is not supported on HoloLens 2.</span></span>

<span data-ttu-id="ce00d-369">如果您在使用藍牙裝置時遇到問題，請確定它是支援的裝置。</span><span class="sxs-lookup"><span data-stu-id="ce00d-369">If you're having trouble using a Bluetooth device, make sure that it's a supported device.</span></span> <span data-ttu-id="ce00d-370">支援的裝置包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="ce00d-370">Supported devices include the following:</span></span>

- <span data-ttu-id="ce00d-371">英文版的繁體中文藍牙鍵盤 (您可以在使用全像全像鍵盤) 的任何地方使用這些鍵盤。</span><span class="sxs-lookup"><span data-stu-id="ce00d-371">English-language QWERTY Bluetooth keyboards (you can use these anywhere that you use the holographic keyboard).</span></span>
- <span data-ttu-id="ce00d-372">藍牙滑鼠。</span><span class="sxs-lookup"><span data-stu-id="ce00d-372">Bluetooth mice.</span></span>
- <span data-ttu-id="ce00d-373">[HoloLens clicker](hololens1-clicker.md)。</span><span class="sxs-lookup"><span data-stu-id="ce00d-373">The [HoloLens clicker](hololens1-clicker.md).</span></span>

<span data-ttu-id="ce00d-374">您可以將其他 Bluetooth 的 HID 和 GATT 裝置與 HoloLens 配對在一起。</span><span class="sxs-lookup"><span data-stu-id="ce00d-374">You can pair other Bluetooth HID and GATT devices together with your HoloLens.</span></span> <span data-ttu-id="ce00d-375">不過，您可能必須從 Microsoft Store 安裝對應的附屬應用程式，才能實際使用裝置。</span><span class="sxs-lookup"><span data-stu-id="ce00d-375">However, you may have to install corresponding companion apps from Microsoft Store to actually use the devices.</span></span>

[<span data-ttu-id="ce00d-376">返回清單</span><span class="sxs-lookup"><span data-stu-id="ce00d-376">Back to list</span></span>](#list)
