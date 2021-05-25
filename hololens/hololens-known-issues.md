---
title: HoloLens 的已知問題
description: 隨時掌握已知問題和因應措施的清單，這些問題可能會影響使用 Unity 和 Windows 裝置入口網站的 HoloLens 客戶和開發人員。
keywords: 疑難排解、已知問題、協助
author: mattzmsft
ms.author: mazeller
ms.date: 11/30/2020
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
- HoloLens 2
ms.openlocfilehash: bc1d399a07a6a0622c953178cad7be1b8a018fdb
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397779"
---
# <a name="known-issues-for-hololens"></a><span data-ttu-id="3f87e-104">HoloLens 的已知問題</span><span class="sxs-lookup"><span data-stu-id="3f87e-104">Known issues for HoloLens</span></span>

<span data-ttu-id="3f87e-105">以下是 HoloLens 裝置已知問題的目前清單。</span><span class="sxs-lookup"><span data-stu-id="3f87e-105">Here is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="3f87e-106">如果您看到奇怪的行為，請先檢查此處。</span><span class="sxs-lookup"><span data-stu-id="3f87e-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="3f87e-107">這份清單會在探索或回報新問題時保持更新狀態，或在未來的 HoloLens 軟體更新中解決問題。</span><span class="sxs-lookup"><span data-stu-id="3f87e-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="3f87e-108">如果您發現未封鎖的問題，請透過 [意見反應中樞](hololens-feedback.md)在 HoloLens 裝置上報告。</span><span class="sxs-lookup"><span data-stu-id="3f87e-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="3f87e-109">如果您遇到的問題正在封鎖您，除了提出意見反應之外，請提出 [支援要求](https://aka.ms/hlsupport)。</span><span class="sxs-lookup"><span data-stu-id="3f87e-109">If the issue you are facing is blocking you, in addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).</span></span>

- [<span data-ttu-id="3f87e-110">所有 HoloLens 世代的已知問題</span><span class="sxs-lookup"><span data-stu-id="3f87e-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="3f87e-111">HoloLens 2 裝置的已知問題</span><span class="sxs-lookup"><span data-stu-id="3f87e-111">Known issues for HoloLens 2 devices</span></span>](#known-issues-for-hololens-2-devices)
- [<span data-ttu-id="3f87e-112">HoloLens (第一代) 的已知問題 </span><span class="sxs-lookup"><span data-stu-id="3f87e-112">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)
- [<span data-ttu-id="3f87e-113">HoloLens 模擬器的已知問題</span><span class="sxs-lookup"><span data-stu-id="3f87e-113">Known issues for HoloLens emulator</span></span>](#known-issues-for-hololens-emulator)

## <a name="known-issues-for-all-hololens-generations"></a><span data-ttu-id="3f87e-114">所有 HoloLens 世代的已知問題</span><span class="sxs-lookup"><span data-stu-id="3f87e-114">Known issues for all HoloLens generations</span></span>

### <a name="unity"></a><span data-ttu-id="3f87e-115">Unity</span><span class="sxs-lookup"><span data-stu-id="3f87e-115">Unity</span></span>

- <span data-ttu-id="3f87e-116">請參閱安裝適用于最新版本之 Unity 的 [工具](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) ，建議用於 HoloLens 開發。</span><span class="sxs-lookup"><span data-stu-id="3f87e-116">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="3f87e-117">有關 Unity HoloLens Technical Preview 的已知問題記載于 [HoloLens Unity 論壇](https://forum.unity3d.com/threads/known-issues.394627/)中。</span><span class="sxs-lookup"><span data-stu-id="3f87e-117">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <a name="windows-device-portal"></a><span data-ttu-id="3f87e-118">Windows 裝置入口網站</span><span class="sxs-lookup"><span data-stu-id="3f87e-118">Windows Device Portal</span></span>

- <span data-ttu-id="3f87e-119">Mixed Reality capture 中的即時預覽功能可能會顯示幾秒鐘的延遲時間。</span><span class="sxs-lookup"><span data-stu-id="3f87e-119">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="3f87e-120">在 [虛擬輸入] 頁面上，[虛擬手勢] 區段底下的手勢和 Scroll 控制項無法運作。</span><span class="sxs-lookup"><span data-stu-id="3f87e-120">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="3f87e-121">使用這些專案將不會有任何作用。</span><span class="sxs-lookup"><span data-stu-id="3f87e-121">Using them will have no effect.</span></span> <span data-ttu-id="3f87e-122">虛擬輸入頁面上的虛擬鍵盤可正常運作。</span><span class="sxs-lookup"><span data-stu-id="3f87e-122">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="3f87e-123">在設定中啟用開發人員模式之後，可能需要幾秒鐘的時間，才會啟用裝置入口網站的開啟。</span><span class="sxs-lookup"><span data-stu-id="3f87e-123">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <a name="onedrive-camera-upload"></a><span data-ttu-id="3f87e-124">OneDrive 相機上傳</span><span class="sxs-lookup"><span data-stu-id="3f87e-124">OneDrive camera upload</span></span>

<span data-ttu-id="3f87e-125">適用于 HoloLens 的 OneDrive 應用程式不支援工作或學校帳戶的自動攝影機上傳。</span><span class="sxs-lookup"><span data-stu-id="3f87e-125">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="3f87e-126">因應措施：</span><span class="sxs-lookup"><span data-stu-id="3f87e-126">Workarounds:</span></span>

- <span data-ttu-id="3f87e-127">如果您的企業可以使用，則在取用者 Microsoft 帳戶上可支援自動相機上傳。</span><span class="sxs-lookup"><span data-stu-id="3f87e-127">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="3f87e-128">除了您的工作或學校帳戶之外，您還可以登入 Microsoft 帳戶 (OneDrive 應用程式支援雙重登入) 。</span><span class="sxs-lookup"><span data-stu-id="3f87e-128">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="3f87e-129">從 OneDrive 內的 Microsoft 帳戶設定檔，您可以啟用自動的背景相機滾動上傳。</span><span class="sxs-lookup"><span data-stu-id="3f87e-129">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="3f87e-130">如果您無法安全地使用取用者 Microsoft 帳戶自動上傳您的相片，您可以從 OneDrive 應用程式手動將相片上傳至您的工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="3f87e-130">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="3f87e-131">若要這樣做，請確定您已登入 OneDrive 應用程式中的公司或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="3f87e-131">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="3f87e-132">選取 **+** 按鈕，然後選擇 [ **上傳**]。</span><span class="sxs-lookup"><span data-stu-id="3f87e-132">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="3f87e-133">藉由流覽至 [ **圖片] > 相機滾動** 圖，尋找您想要上傳的相片或影片。</span><span class="sxs-lookup"><span data-stu-id="3f87e-133">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="3f87e-134">選取您要上傳的相片或影片，然後選取 [ **開啟** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="3f87e-134">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <a name="known-issues-for-hololens-2-devices"></a><span data-ttu-id="3f87e-135">HoloLens 2 裝置的已知問題</span><span class="sxs-lookup"><span data-stu-id="3f87e-135">Known issues for HoloLens 2 devices</span></span>

### <a name="device-using-auto-login-asks-for-log-in"></a><span data-ttu-id="3f87e-136">使用自動登入的裝置要求登入</span><span class="sxs-lookup"><span data-stu-id="3f87e-136">Device using Auto-login asks for log-in</span></span>

<span data-ttu-id="3f87e-137">HoloLens 2 裝置可設定為自動透過 **設定**  ->  **帳戶** 登  ->  **入選項** 登入->，而且在 **必要** 時，將值設為 [**永不**]。</span><span class="sxs-lookup"><span data-stu-id="3f87e-137">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="3f87e-138">使用重大更新（例如功能更新）更新裝置時，某些使用者可能需要再次登入裝置。</span><span class="sxs-lookup"><span data-stu-id="3f87e-138">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span>

<span data-ttu-id="3f87e-139">發生這種情況的範例：</span><span class="sxs-lookup"><span data-stu-id="3f87e-139">Example of when this could occur:</span></span>

- <span data-ttu-id="3f87e-140">將裝置從 Windows 全像2004版 (組建) 19041）更新為 Windows 全像21H1 版， (組建 20346. xxxx) </span><span class="sxs-lookup"><span data-stu-id="3f87e-140">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="3f87e-141">將裝置更新為在相同的主要組建上進行大量更新，例如 Windows 全像 Windows 全像，2004版到 Windows 全像20H2 版</span><span class="sxs-lookup"><span data-stu-id="3f87e-141">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="3f87e-142">將裝置從原廠映射更新為最新影像</span><span class="sxs-lookup"><span data-stu-id="3f87e-142">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="3f87e-143">這應該不會在下列情況中發生：</span><span class="sxs-lookup"><span data-stu-id="3f87e-143">This should not occur during:</span></span>

- <span data-ttu-id="3f87e-144">取得每月服務更新的裝置</span><span class="sxs-lookup"><span data-stu-id="3f87e-144">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="3f87e-145">解決方法：</span><span class="sxs-lookup"><span data-stu-id="3f87e-145">Work around methods:</span></span>

- <span data-ttu-id="3f87e-146">登入方法，例如 PIN、密碼、鳶尾花、Web 驗證或 FIDO2 金鑰。</span><span class="sxs-lookup"><span data-stu-id="3f87e-146">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="3f87e-147">如果無法記住裝置 PIN，而且無法使用其他驗證方法，則使用者可以使用 [手動 reflashing 模式](hololens-recovery.md#manual-procedure)。</span><span class="sxs-lookup"><span data-stu-id="3f87e-147">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

### <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="3f87e-148">無法啟動 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3f87e-148">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="3f87e-149">此問題原本是使用 Microsoft Edge 的出貨版本所建立。</span><span class="sxs-lookup"><span data-stu-id="3f87e-149">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="3f87e-150">此問題可在 [新的 Microsoft Edge](hololens-new-edge.md)中解決。</span><span class="sxs-lookup"><span data-stu-id="3f87e-150">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="3f87e-151">如果不是，請提出意見反應。</span><span class="sxs-lookup"><span data-stu-id="3f87e-151">If it is not, please file feedback.</span></span>

<span data-ttu-id="3f87e-152">少數客戶回報了 Microsoft Edge 無法啟動的問題。</span><span class="sxs-lookup"><span data-stu-id="3f87e-152">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="3f87e-153">針對這些客戶，問題會透過重新開機持續存在，而且無法透過 Windows 或應用程式更新解決。</span><span class="sxs-lookup"><span data-stu-id="3f87e-153">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="3f87e-154">如果您遇到此問題，而且已確認 [Windows 是最](hololens-updates.md#manually-check-for-updates)新狀態，請從 [意見反應中樞應用程式](hololens-feedback.md) 提出 bug，並列出下列類別和子類別：安裝和更新 > 下載、安裝和設定 Windows Update。</span><span class="sxs-lookup"><span data-stu-id="3f87e-154">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="3f87e-155">沒有任何已知的因應措施，因為我們目前無法解決問題的根本原因。</span><span class="sxs-lookup"><span data-stu-id="3f87e-155">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="3f87e-156">透過意見反應中樞提出 bug 將有助於進行調查！</span><span class="sxs-lookup"><span data-stu-id="3f87e-156">Filing a bug via Feedback Hub will help our investigation!</span></span>

### <a name="keyboard-does-not-switch-to-special-characters"></a><span data-ttu-id="3f87e-157">鍵盤未切換為特殊字元</span><span class="sxs-lookup"><span data-stu-id="3f87e-157">Keyboard does not switch to special characters</span></span>

<span data-ttu-id="3f87e-158">在 OOBE 期間發生問題，當使用者選擇了工作或學校帳戶，並輸入其密碼時，藉由使用 [123] &按鈕並不會變更為特殊字元，藉以嘗試切換至鍵盤上的特殊字元。</span><span class="sxs-lookup"><span data-stu-id="3f87e-158">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span>

<span data-ttu-id="3f87e-159">解決辦法：</span><span class="sxs-lookup"><span data-stu-id="3f87e-159">Work-arounds:</span></span>
-   <span data-ttu-id="3f87e-160">關閉鍵盤，然後藉由點擊文字欄位將它重新開啟。</span><span class="sxs-lookup"><span data-stu-id="3f87e-160">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="3f87e-161">輸入您的密碼不正確。</span><span class="sxs-lookup"><span data-stu-id="3f87e-161">Incorrectly enter your password.</span></span> <span data-ttu-id="3f87e-162">下一次 relaunched 鍵盤時，它會如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="3f87e-162">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="3f87e-163">Web 驗證，關閉鍵盤，然後選取 [ **從另一部裝置登入**]。</span><span class="sxs-lookup"><span data-stu-id="3f87e-163">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="3f87e-164">如果只輸入數位，使用者可以按住某些按鍵以開啟展開的功能表。</span><span class="sxs-lookup"><span data-stu-id="3f87e-164">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="3f87e-165">使用 USB 鍵盤。</span><span class="sxs-lookup"><span data-stu-id="3f87e-165">Using a USB keyboard.</span></span>

<span data-ttu-id="3f87e-166">這不會影響：</span><span class="sxs-lookup"><span data-stu-id="3f87e-166">This does not affect:</span></span>
- <span data-ttu-id="3f87e-167">選擇使用個人帳戶的使用者。</span><span class="sxs-lookup"><span data-stu-id="3f87e-167">Users who choose to use a personal account.</span></span>

### <a name="blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-an-insider-build"></a><span data-ttu-id="3f87e-168">在具有 Insider 組建的裝置 reflashed 上取消註冊 Insider preview 組建之後，顯示藍色畫面</span><span class="sxs-lookup"><span data-stu-id="3f87e-168">Blue screen is shown after unenrolling from Insider preview builds on a device reflashed with an Insider build</span></span>

<span data-ttu-id="3f87e-169">這是影響的問題，它會影響屬於 Insider preview 組建的使用者、使用新的 insider preview 組建 reflashed 其 HoloLens 2，然後從 Insider 計畫取消註冊。</span><span class="sxs-lookup"><span data-stu-id="3f87e-169">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span>

<span data-ttu-id="3f87e-170">這不會影響：</span><span class="sxs-lookup"><span data-stu-id="3f87e-170">This does not affect:</span></span>
- <span data-ttu-id="3f87e-171">未註冊 Windows 測試人員中的使用者</span><span class="sxs-lookup"><span data-stu-id="3f87e-171">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="3f87e-172">業內 人士：</span><span class="sxs-lookup"><span data-stu-id="3f87e-172">Insiders:</span></span>
    - <span data-ttu-id="3f87e-173">如果裝置已註冊，因為 Insider build 是 version 18362. x</span><span class="sxs-lookup"><span data-stu-id="3f87e-173">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="3f87e-174">如果他們將 Insider 已簽署的19041建立並在測試人員計畫中保持註冊，</span><span class="sxs-lookup"><span data-stu-id="3f87e-174">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="3f87e-175">解決辦法：</span><span class="sxs-lookup"><span data-stu-id="3f87e-175">Work-around:</span></span> 
- <span data-ttu-id="3f87e-176">避免此問題</span><span class="sxs-lookup"><span data-stu-id="3f87e-176">Avoid the issue</span></span> 
    - <span data-ttu-id="3f87e-177">Flash 非 insider build。</span><span class="sxs-lookup"><span data-stu-id="3f87e-177">Flash a non-insider build.</span></span> <span data-ttu-id="3f87e-178">其中一個一般的每月更新。</span><span class="sxs-lookup"><span data-stu-id="3f87e-178">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="3f87e-179">掌握 Insider Preview</span><span class="sxs-lookup"><span data-stu-id="3f87e-179">Stay on Insider Preview</span></span>
- <span data-ttu-id="3f87e-180">重新刷新裝置</span><span class="sxs-lookup"><span data-stu-id="3f87e-180">Reflash the device</span></span>

    1. <span data-ttu-id="3f87e-181">請在未連線的情況下完全關閉，以手動方式將 [HoloLens 2 進入閃爍模式](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) 。</span><span class="sxs-lookup"><span data-stu-id="3f87e-181">Put the [HoloLens 2 into flashing mode](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) manually by fully powering down while not connect.</span></span> <span data-ttu-id="3f87e-182">然後按住音量，然後按一下 [電源] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="3f87e-182">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="3f87e-183">連接到電腦並開啟 Advanced Recovery 隨附。</span><span class="sxs-lookup"><span data-stu-id="3f87e-183">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="3f87e-184">將 HoloLens 2 快閃至預設組建。</span><span class="sxs-lookup"><span data-stu-id="3f87e-184">Flash the HoloLens 2 to the default build.</span></span>

## <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="3f87e-185">HoloLens (第一代) 的已知問題</span><span class="sxs-lookup"><span data-stu-id="3f87e-185">Known issues for HoloLens (1st Gen)</span></span>

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a><span data-ttu-id="3f87e-186">無法透過 Visual Studio 連接及部署至 HoloLens</span><span class="sxs-lookup"><span data-stu-id="3f87e-186">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="3f87e-187">上次更新日期： 8/8 @ 5：晚上11點-Visual Studio 已發行與 2019 16.2 版，其中包含此問題的修正。</span><span class="sxs-lookup"><span data-stu-id="3f87e-187">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="3f87e-188">建議您更新為此最新版本，以避免發生此錯誤。</span><span class="sxs-lookup"><span data-stu-id="3f87e-188">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="3f87e-189">Visual Studio 已發行 VS 2019 16.2 版，其中包含此問題的修正。</span><span class="sxs-lookup"><span data-stu-id="3f87e-189">Visual Studio has released VS 2019 Version 16.2, which includes a fix to this issue.</span></span> <span data-ttu-id="3f87e-190">建議您更新為此最新版本，以避免發生此錯誤。</span><span class="sxs-lookup"><span data-stu-id="3f87e-190">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="3f87e-191">問題根本原因：使用 Visual Studio 2015 或舊版 Visual Studio 2017 的使用者，在其 HoloLens 上部署和偵測應用程式，之後再使用相同 HoloLens 的最新版本 Visual Studio 2017 或 Visual Studio 2019 將會受到影響。</span><span class="sxs-lookup"><span data-stu-id="3f87e-191">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="3f87e-192">較新版本的 Visual Studio 會部署新版的元件，但較舊版本的檔案會留在裝置上，使較新的版本失敗。</span><span class="sxs-lookup"><span data-stu-id="3f87e-192">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="3f87e-193">這會導致下列錯誤訊息： DEP0100：確定目標裝置已啟用開發人員模式。</span><span class="sxs-lookup"><span data-stu-id="3f87e-193">This causes the following error message: DEP0100: Ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="3f87e-194">由於錯誤80004005，無法取得開發人員授權 \<ip\> 。</span><span class="sxs-lookup"><span data-stu-id="3f87e-194">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <a name="workaround"></a><span data-ttu-id="3f87e-195">因應措施</span><span class="sxs-lookup"><span data-stu-id="3f87e-195">Workaround</span></span>

<span data-ttu-id="3f87e-196">我們的小組目前正在進行修正。</span><span class="sxs-lookup"><span data-stu-id="3f87e-196">Our team is currently working on a fix.</span></span> <span data-ttu-id="3f87e-197">在此同時，您可以使用下列步驟來解決此問題，並協助解除封鎖部署和偵測：</span><span class="sxs-lookup"><span data-stu-id="3f87e-197">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="3f87e-198">開啟 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="3f87e-198">Open Visual Studio.</span></span>

1. <span data-ttu-id="3f87e-199">選取 [File] \(檔案\) >  [New] \(新增\) >  [Project] \(專案\)。</span><span class="sxs-lookup"><span data-stu-id="3f87e-199">Select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="3f87e-200">選取 [ **Visual c #**  >  **Windows 桌面**  >  **主控台應用程式 ( .NET Framework)**]。</span><span class="sxs-lookup"><span data-stu-id="3f87e-200">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>

1. <span data-ttu-id="3f87e-201">為專案命名 (例如 "HoloLensDeploymentFix" ) 並確定 Framework 設定為至少 .NET Framework 4.5，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3f87e-201">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>

1. <span data-ttu-id="3f87e-202">以滑鼠右鍵按一下方案總管中的 [ **參考** ] 節點，然後在 [ **流覽]** 區段中新增下列參考 (選取 [流覽]，然後選取 **[流覽**) ：</span><span class="sxs-lookup"><span data-stu-id="3f87e-202">Right-click the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="3f87e-203">如果您尚未安裝10.0.18362.0，請使用您擁有的最新版本。</span><span class="sxs-lookup"><span data-stu-id="3f87e-203">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span> 

1. <span data-ttu-id="3f87e-204">以滑鼠右鍵按一下方案總管中的專案，然後選取 [**加入**  >  **現有專案**]。</span><span class="sxs-lookup"><span data-stu-id="3f87e-204">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>

1. <span data-ttu-id="3f87e-205">流覽至 C:\Program Files (x86) \Windows Kits\10\bin\10.0.18362.0\x86，然後將篩選器變更為 **(的所有檔案 \* 。 \*)**。</span><span class="sxs-lookup"><span data-stu-id="3f87e-205">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>

1. <span data-ttu-id="3f87e-206">選取 SirepClient.dll 和 SshClient.dll，然後選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="3f87e-206">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>

1. <span data-ttu-id="3f87e-207">在方案總管中找出並選取兩個檔案， (它們應該位於檔案) 清單的底部，然後將 [**屬性**] 視窗中的 [**複製到輸出目錄**] 變更為 [**永遠複製**]。</span><span class="sxs-lookup"><span data-stu-id="3f87e-207">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>

1. <span data-ttu-id="3f87e-208">在檔案頂端，將下列內容新增至現有的 `using` 語句清單：</span><span class="sxs-lookup"><span data-stu-id="3f87e-208">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="3f87e-209">在中 `static void Main(...)` ，加入下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="3f87e-209">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="3f87e-210">選取 [建置] > [建置方案]。</span><span class="sxs-lookup"><span data-stu-id="3f87e-210">Select **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="3f87e-211">開啟 [命令提示字元] 視窗，並將 cd 放至包含已編譯 .exe 檔的資料夾 (例如，C:\MyProjects\HoloLensDeploymentFix\bin\Debug) 。</span><span class="sxs-lookup"><span data-stu-id="3f87e-211">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span></span>

1. <span data-ttu-id="3f87e-212">執行可執行檔，並提供裝置的 IP 位址做為命令列引數。</span><span class="sxs-lookup"><span data-stu-id="3f87e-212">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="3f87e-213"> (如果使用 USB 連接，您可以使用127.0.0.1，否則請使用裝置的 Wi-Fi IP 位址。 ) 例如 "HoloLensDeploymentFix 127.0.0.1"。</span><span class="sxs-lookup"><span data-stu-id="3f87e-213">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1".</span></span>

1. <span data-ttu-id="3f87e-214">當此工具結束時，如果沒有任何訊息 (這應該只需要幾秒鐘的時間) ，您就可以從 Visual Studio 2017 或更新版本進行部署和偵錯工具。</span><span class="sxs-lookup"><span data-stu-id="3f87e-214">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="3f87e-215">不需要繼續使用此工具。</span><span class="sxs-lookup"><span data-stu-id="3f87e-215">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="3f87e-216">我們會在可用時提供進一步的更新。</span><span class="sxs-lookup"><span data-stu-id="3f87e-216">We will provide further updates as they become available.</span></span>

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a><span data-ttu-id="3f87e-217">在 HoloLens 上啟動 Microsoft Store 和應用程式的問題</span><span class="sxs-lookup"><span data-stu-id="3f87e-217">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="3f87e-218">上次更新： 4/2 @ 上午10點-問題已解決。</span><span class="sxs-lookup"><span data-stu-id="3f87e-218">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span>

<span data-ttu-id="3f87e-219">當您嘗試在 HoloLens 上啟動 Microsoft Store 和應用程式時，可能會遇到問題。</span><span class="sxs-lookup"><span data-stu-id="3f87e-219">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="3f87e-220">我們已判斷當背景應用程式更新在特定序列中部署較新版本的 framework 套件，且其中一或多個相依的應用程式仍在執行時，就會發生此問題。</span><span class="sxs-lookup"><span data-stu-id="3f87e-220">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="3f87e-221">在此情況下，自動應用程式更新將新版本的 .NET Native Framework (10.0.25531 版本傳遞至 10.0.27413) 導致執行的應用程式不會針對所有使用舊版 Framework 的執行中應用程式正確更新。</span><span class="sxs-lookup"><span data-stu-id="3f87e-221">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="3f87e-222">架構更新的流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="3f87e-222">The flow for framework update is as follows:</span></span>

1. <span data-ttu-id="3f87e-223">新的架構套件會從存放區下載並安裝。</span><span class="sxs-lookup"><span data-stu-id="3f87e-223">The new framework package is downloaded from the store and installed.</span></span>

1. <span data-ttu-id="3f87e-224">使用較舊架構的所有應用程式會「更新」以使用較新的版本。</span><span class="sxs-lookup"><span data-stu-id="3f87e-224">All apps using the older framework are 'updated' to use the newer version.</span></span>

<span data-ttu-id="3f87e-225">如果步驟2在完成之前中斷，則不會註冊新 framework 的任何應用程式都將無法從 [開始] 功能表啟動。</span><span class="sxs-lookup"><span data-stu-id="3f87e-225">If step 2 is interrupted before completion, then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="3f87e-226">我們相信 HoloLens 上的任何應用程式可能會受到此問題影響。</span><span class="sxs-lookup"><span data-stu-id="3f87e-226">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="3f87e-227">有些使用者回報關閉無回應的應用程式，並啟動其他應用程式（例如意見反應中樞、3D 檢視器或相片）來解決問題，不過，這在100% 的時間內無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="3f87e-227">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them - however, this does not work 100% of the time.</span></span>

<span data-ttu-id="3f87e-228">我們的根本原因是這個問題不是由更新本身所造成，而是作業系統中造成 .NET Native framework 更新處理錯誤的錯誤。</span><span class="sxs-lookup"><span data-stu-id="3f87e-228">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="3f87e-229">我們很高興宣佈我們已找出修正程式，並已發行更新 (OS 17763.380 版) 包含修正。</span><span class="sxs-lookup"><span data-stu-id="3f87e-229">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="3f87e-230">若要查看您的裝置是否可以進行更新：</span><span class="sxs-lookup"><span data-stu-id="3f87e-230">To see if your device can take the update:</span></span>

1. <span data-ttu-id="3f87e-231">移至 [設定] 應用程式，並開啟 [ **更新 & 安全性**]。</span><span class="sxs-lookup"><span data-stu-id="3f87e-231">Go to the Settings app and open **Update & Security**.</span></span>

1. <span data-ttu-id="3f87e-232">選取 [ **檢查更新**]。</span><span class="sxs-lookup"><span data-stu-id="3f87e-232">Select **Check for Updates**.</span></span>

1. <span data-ttu-id="3f87e-233">如果有17763.380 的更新可供使用，請更新為此組建，以接收應用程式停止回應錯誤的修正程式。</span><span class="sxs-lookup"><span data-stu-id="3f87e-233">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug.</span></span>

1. <span data-ttu-id="3f87e-234">更新至此版本的作業系統時，應用程式應該會如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="3f87e-234">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="3f87e-235">此外，與每個 HoloLens 作業系統版本一樣，我們已將 FFU 映射張貼至 [Microsoft 下載中心](https://aka.ms/hololensdownload/10.0.17763.380)。</span><span class="sxs-lookup"><span data-stu-id="3f87e-235">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="3f87e-236">如果您不想要進行更新，我們發行了3/29 版的 Microsoft Store UWP 應用程式的新版本。</span><span class="sxs-lookup"><span data-stu-id="3f87e-236">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="3f87e-237">當您擁有更新版的存放區之後：</span><span class="sxs-lookup"><span data-stu-id="3f87e-237">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="3f87e-238">開啟存放區，並確認它是否已載入。</span><span class="sxs-lookup"><span data-stu-id="3f87e-238">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="3f87e-239">使用 bloom 手勢來開啟功能表。</span><span class="sxs-lookup"><span data-stu-id="3f87e-239">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="3f87e-240">嘗試開啟先前中斷的應用程式。</span><span class="sxs-lookup"><span data-stu-id="3f87e-240">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="3f87e-241">如果仍然無法啟動，請按一下並按住應用程式中斷的圖示，然後選取 [卸載]。</span><span class="sxs-lookup"><span data-stu-id="3f87e-241">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="3f87e-242">從存放區重新安裝這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="3f87e-242">Reinstall these apps from the store.</span></span>

<span data-ttu-id="3f87e-243">如果您的裝置仍無法載入應用程式，您可以遵循下列步驟，透過下載中心側載某個版本的 .NET Native Framework 和執行時間：</span><span class="sxs-lookup"><span data-stu-id="3f87e-243">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="3f87e-244">請從 Microsoft 下載中心下載 [此 zip](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) 檔案。</span><span class="sxs-lookup"><span data-stu-id="3f87e-244">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="3f87e-245">解壓縮將會產生兩個檔案。</span><span class="sxs-lookup"><span data-stu-id="3f87e-245">Unzipping will produce two files.</span></span>  <span data-ttu-id="3f87e-246">NET.TCP 和 NET.TCP..... t.. t..。</span><span class="sxs-lookup"><span data-stu-id="3f87e-246">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx.</span></span>

1. <span data-ttu-id="3f87e-247">請確認您的裝置已解除鎖定。</span><span class="sxs-lookup"><span data-stu-id="3f87e-247">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="3f87e-248">如果您尚未這麼做，請參閱 [使用 Windows 裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 以取得相關指示。</span><span class="sxs-lookup"><span data-stu-id="3f87e-248">If you haven't done that before, see [Using the Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) for instructions.</span></span>

1. <span data-ttu-id="3f87e-249">接著，您會想要進入 Windows 裝置入口網站。</span><span class="sxs-lookup"><span data-stu-id="3f87e-249">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="3f87e-250">我們的建議是透過 USB 執行此動作，您可以在 http://127.0.0.1:10080 瀏覽器中輸入。</span><span class="sxs-lookup"><span data-stu-id="3f87e-250">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>

1. <span data-ttu-id="3f87e-251">完成 Windows 裝置入口網站之後，您需要「側載」您下載的兩個檔案。</span><span class="sxs-lookup"><span data-stu-id="3f87e-251">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="3f87e-252">若要這樣做，您必須向下移至 [ **應用程式** ] 區段，然後選取 [ **應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="3f87e-252">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>

1. <span data-ttu-id="3f87e-253">然後，您會看到類似下面的畫面。</span><span class="sxs-lookup"><span data-stu-id="3f87e-253">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="3f87e-254">您想要移至「 **安裝應用程式** 」一節，然後流覽至您解壓縮這兩個 APPX 檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="3f87e-254">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="3f87e-255">您一次只能執行一次，因此選取第一個，然後按一下 [部署] 區段下的 [執行]。</span><span class="sxs-lookup"><span data-stu-id="3f87e-255">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="3f87e-256">然後對第二個 APPX 檔案進行此動作。</span><span class="sxs-lookup"><span data-stu-id="3f87e-256">Then do this for the second APPX file.</span></span>

   ![Windows 裝置入口網站安裝 Side-Loaded 應用程式](images/20190322-DevicePortal.png)
   
1. <span data-ttu-id="3f87e-258">至此，我們相信您的應用程式應該會再次開始運作，而且您也可以前往存放區。</span><span class="sxs-lookup"><span data-stu-id="3f87e-258">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>

1. <span data-ttu-id="3f87e-259">在某些情況下，必須先執行額外的步驟來啟動3D 檢視器應用程式，才會啟動受影響的應用程式。</span><span class="sxs-lookup"><span data-stu-id="3f87e-259">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span> 

<span data-ttu-id="3f87e-260">我們非常感謝您的耐心等候，因為我們已完成解決此問題的程式，我們期待繼續與我們的小組合作，以建立成功的混合現實體驗。</span><span class="sxs-lookup"><span data-stu-id="3f87e-260">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <a name="device-update"></a><span data-ttu-id="3f87e-261">裝置更新</span><span class="sxs-lookup"><span data-stu-id="3f87e-261">Device Update</span></span>

- <span data-ttu-id="3f87e-262">在新更新之後的30秒後，shell 可能會消失一次。</span><span class="sxs-lookup"><span data-stu-id="3f87e-262">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="3f87e-263">請執行 **bloom** 手勢以繼續您的會話。</span><span class="sxs-lookup"><span data-stu-id="3f87e-263">Please perform the **bloom** gesture to resume your session.</span></span>

### <a name="visual-studio"></a><span data-ttu-id="3f87e-264">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3f87e-264">Visual Studio</span></span>

- <span data-ttu-id="3f87e-265">請參閱安裝適用于 HoloLens 開發建議的最新 Visual Studio 版本的 [工具](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) 。</span><span class="sxs-lookup"><span data-stu-id="3f87e-265">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>

- <span data-ttu-id="3f87e-266">從 Visual Studio 將應用程式部署到 HoloLens 時，您可能會看到錯誤： **無法在開啟使用者對應區段的檔案上執行要求的作業。從 HRESULT (例外狀況： 0x800704C8)**。</span><span class="sxs-lookup"><span data-stu-id="3f87e-266">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="3f87e-267">如果發生這種情況，請再試一次，您的部署通常會成功。</span><span class="sxs-lookup"><span data-stu-id="3f87e-267">If this happens, try again and your deployment will generally succeed.</span></span>

### <a name="api"></a><span data-ttu-id="3f87e-268">API</span><span class="sxs-lookup"><span data-stu-id="3f87e-268">API</span></span>

- <span data-ttu-id="3f87e-269">如果應用程式將使用者的 [焦點放](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) 在使用者後方，或是將一般設定為攝影機，則全像投影不會出現在混合實境擷取的相片或影片中。</span><span class="sxs-lookup"><span data-stu-id="3f87e-269">If the application sets the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="3f87e-270">在 Windows 中修正這個 bug 之前，如果應用程式會主動設定 [焦點點](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) ，則應該確保平面的法線設定為相對相機向前 (例如，normal =-攝影機向前) 。</span><span class="sxs-lookup"><span data-stu-id="3f87e-270">Until this bug is fixed in Windows, if applications actively set the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <a name="xbox-wireless-controller"></a><span data-ttu-id="3f87e-271">Xbox 無線控制器</span><span class="sxs-lookup"><span data-stu-id="3f87e-271">Xbox Wireless Controller</span></span>

- <span data-ttu-id="3f87e-272">Xbox 無線控制器 S 必須先更新，才能搭配 HoloLens 使用。</span><span class="sxs-lookup"><span data-stu-id="3f87e-272">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="3f87e-273">嘗試將您的控制器與 HoloLens 配對之前，請確定您是 [最](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) 新的。</span><span class="sxs-lookup"><span data-stu-id="3f87e-273">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>

- <span data-ttu-id="3f87e-274">如果您在 Xbox 無線控制器連線時重新開機 HoloLens，控制器將不會自動重新連線到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="3f87e-274">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="3f87e-275">在控制器關閉3分鐘之後，[節目表] 按鈕淺色將會停止閃爍。</span><span class="sxs-lookup"><span data-stu-id="3f87e-275">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="3f87e-276">若要立即重新連接控制器，請按住 [節目表] 按鈕以關閉控制器，直到燈關閉為止。</span><span class="sxs-lookup"><span data-stu-id="3f87e-276">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="3f87e-277">當您重新開機控制器時，它會重新連接到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="3f87e-277">When you power your controller on again, it will reconnect to HoloLens.</span></span>

- <span data-ttu-id="3f87e-278">如果您的 HoloLens 在 Xbox 無線控制器連線時進入待命狀態，控制器上的任何輸入將會喚醒 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="3f87e-278">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="3f87e-279">您可以在使用控制器時關閉控制器來防止這種情況。</span><span class="sxs-lookup"><span data-stu-id="3f87e-279">You can prevent this by powering off your controller when you are done using it.</span></span>

## <a name="known-issues-for-hololens-emulator"></a><span data-ttu-id="3f87e-280">HoloLens 模擬器的已知問題</span><span class="sxs-lookup"><span data-stu-id="3f87e-280">Known issues for HoloLens emulator</span></span>

- <span data-ttu-id="3f87e-281">並非 Microsoft Store 中的所有應用程式都與模擬器相容。</span><span class="sxs-lookup"><span data-stu-id="3f87e-281">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="3f87e-282">例如，在模擬器上無法播放年輕 Conker 和片段。</span><span class="sxs-lookup"><span data-stu-id="3f87e-282">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="3f87e-283">您無法在模擬器中使用電腦網路攝影機。</span><span class="sxs-lookup"><span data-stu-id="3f87e-283">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="3f87e-284">Windows 裝置入口網站的即時預覽功能無法與模擬器搭配使用。</span><span class="sxs-lookup"><span data-stu-id="3f87e-284">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="3f87e-285">您仍然可以捕獲混合的現實影片和影像。</span><span class="sxs-lookup"><span data-stu-id="3f87e-285">You can still capture Mixed Reality videos and images.</span></span>
