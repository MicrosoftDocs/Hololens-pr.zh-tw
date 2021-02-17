---
title: 適用於 Microsoft HoloLens 的 Insider Preview
description: 瞭解如何開始使用測試人員版本，並為 HoloLens 的下一個主要作業系統更新提供寶貴的意見。
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
ms.date: 2/16/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 885f9a841c5f59f2816667256de0856f8a1f2612
ms.sourcegitcommit: ab35169529776f0682eeb8fa448c9d9e8f598513
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2021
ms.locfileid: "11340534"
---
# <span data-ttu-id="8295a-103">適用於 Microsoft HoloLens 的 Insider Preview</span><span class="sxs-lookup"><span data-stu-id="8295a-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="8295a-104">歡迎使用 HoloLens 的最新 Insider Preview 版本！</span><span class="sxs-lookup"><span data-stu-id="8295a-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="8295a-105">開始使用非常簡單，並為[](hololens-insider.md#start-receiving-insider-builds)HoloLens 的下一個主要作業系統更新提供寶貴的意見。</span><span class="sxs-lookup"><span data-stu-id="8295a-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <span data-ttu-id="8295a-106">Windows Insider Release Notes</span><span class="sxs-lookup"><span data-stu-id="8295a-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="8295a-107">我們很高興能再次開始向 Windows Insider 提供新功能。</span><span class="sxs-lookup"><span data-stu-id="8295a-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="8295a-108">新版將會測試到 Dev 通道，以尋找最新的更新。</span><span class="sxs-lookup"><span data-stu-id="8295a-108">New builds will be flighting to the Dev Channel for the latest updates.</span></span> <span data-ttu-id="8295a-109">隨著我們新增更多功能與更新至我們的 Windows 測試人員版本，我們會持續更新此頁面。</span><span class="sxs-lookup"><span data-stu-id="8295a-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span>  <span data-ttu-id="8295a-110">期待並準備好將這些更新混合到您的實境中。</span><span class="sxs-lookup"><span data-stu-id="8295a-110">Get excited and ready to mix these updates into your reality.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8295a-111">如果您先前在 Kiosk 中曾使用設定 App 或 Microsoft Edge 應用程式，我們已將這些應用程式取代為使用不同的應用程式識別碼的新應用程式。</span><span class="sxs-lookup"><span data-stu-id="8295a-111">If you were previously using either the Settings app or Microsoft Edge app in a Kiosk, we have replaced these apps with new apps which use a different App ID.</span></span> <span data-ttu-id="8295a-112">我們強烈建議您閱讀以下資訊站模式中新[App 的新 AUMIDS。](#use-the-new-settings-and-edge-apps-in-kiosk-modes)</span><span class="sxs-lookup"><span data-stu-id="8295a-112">We highly encourage you to read [New AUMIDs for new apps in Kiosk mode](#use-the-new-settings-and-edge-apps-in-kiosk-modes) below.</span></span> <span data-ttu-id="8295a-113">這可確保您繼續擁有 Kiosk 中的設定應用程式，或包含新的 Microsoft Edge 應用程式。</span><span class="sxs-lookup"><span data-stu-id="8295a-113">This will ensure you either continue to have the Settings app in your Kiosk, or include the new Microsoft Edge app.</span></span>

<br>

| <span data-ttu-id="8295a-114">功能名稱</span><span class="sxs-lookup"><span data-stu-id="8295a-114">Feature Name</span></span>                                              | <span data-ttu-id="8295a-115">簡短描述</span><span class="sxs-lookup"><span data-stu-id="8295a-115">Short description</span></span>                                                                      | <span data-ttu-id="8295a-116">可在建立中使用</span><span class="sxs-lookup"><span data-stu-id="8295a-116">Available in build</span></span> |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [<span data-ttu-id="8295a-117">新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8295a-117">New Microsoft Edge</span></span>](#introducing-the-new-microsoft-edge) | <span data-ttu-id="8295a-118">新的 Chromium 型 Microsoft Edge 現已適用于 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="8295a-118">The new, Chromium-based Microsoft Edge is now available for HoloLens 2</span></span>                         | <span data-ttu-id="8295a-119">20279.1006</span><span class="sxs-lookup"><span data-stu-id="8295a-119">20279.1006</span></span> |
| [<span data-ttu-id="8295a-120">WebXR 和 360 Viewer</span><span class="sxs-lookup"><span data-stu-id="8295a-120">WebXR and 360 Viewer</span></span>](#webxr-and-360-viewer)             | <span data-ttu-id="8295a-121">嘗試沉浸式網頁體驗和 360 影片播放</span><span class="sxs-lookup"><span data-stu-id="8295a-121">Try immersive web experiences and 360 video playback</span></span>                                           | <span data-ttu-id="8295a-122">20289.1000</span><span class="sxs-lookup"><span data-stu-id="8295a-122">20289.1000</span></span> |
| [<span data-ttu-id="8295a-123">新增設定應用程式</span><span class="sxs-lookup"><span data-stu-id="8295a-123">New Settings app</span></span>](#new-settings-app)                     | <span data-ttu-id="8295a-124">舊版的設定應用程式正由更新的版本取代為新功能和設定</span><span class="sxs-lookup"><span data-stu-id="8295a-124">The legacy Settings app is being replaced by an updated version with new features and settings</span></span> | <span data-ttu-id="8295a-125">20279.1006</span><span class="sxs-lookup"><span data-stu-id="8295a-125">20279.1006</span></span> |
| [<span data-ttu-id="8295a-126">顯示色彩校正</span><span class="sxs-lookup"><span data-stu-id="8295a-126">Display color calibration</span></span>](#display-color-calibration)   | <span data-ttu-id="8295a-127">選取 HoloLens 2 顯示器的替代色彩設定檔</span><span class="sxs-lookup"><span data-stu-id="8295a-127">Select an alternative color profile for your HoloLens 2 display</span></span>                                | <span data-ttu-id="8295a-128">20293.1000</span><span class="sxs-lookup"><span data-stu-id="8295a-128">20293.1000</span></span> |
| [<span data-ttu-id="8295a-129">預設應用程式選擇器</span><span class="sxs-lookup"><span data-stu-id="8295a-129">Default app picker</span></span>](#default-app-picker)                 | <span data-ttu-id="8295a-130">選擇每個檔案或連結類型應啟動的應用程式</span><span class="sxs-lookup"><span data-stu-id="8295a-130">Choose which app should launch for each file or link type</span></span>                                      | <span data-ttu-id="8295a-131">20279.1006</span><span class="sxs-lookup"><span data-stu-id="8295a-131">20279.1006</span></span> |
| [<span data-ttu-id="8295a-132">Office Web App</span><span class="sxs-lookup"><span data-stu-id="8295a-132">Office web app</span></span>](#office-web-app)                         | <span data-ttu-id="8295a-133">Office Web App 的快捷方式現在會列在 「所有應用程式」中</span><span class="sxs-lookup"><span data-stu-id="8295a-133">A shortcut to the Office web app is now listed in "All apps"</span></span>                                   | <span data-ttu-id="8295a-134">20279.1006</span><span class="sxs-lookup"><span data-stu-id="8295a-134">20279.1006</span></span> |
| [<span data-ttu-id="8295a-135">滑動以輸入</span><span class="sxs-lookup"><span data-stu-id="8295a-135">Swipe to type</span></span>](#swipe-to-type)                           | <span data-ttu-id="8295a-136">使用手指的提示在全攝影鍵盤上「滑動」文字</span><span class="sxs-lookup"><span data-stu-id="8295a-136">Use the tip of your finger to "swipe" words on the holographic keyboard</span></span>                        | <span data-ttu-id="8295a-137">20279.1006</span><span class="sxs-lookup"><span data-stu-id="8295a-137">20279.1006</span></span> |
| [<span data-ttu-id="8295a-138">USB-C 外接麥克風支援</span><span class="sxs-lookup"><span data-stu-id="8295a-138">USB-C External Microphone Support</span></span>](#usb-c-external-microphone-support) | <span data-ttu-id="8295a-139">針對應用程式和/或遠端輔助使用 USB-C 麥克風。</span><span class="sxs-lookup"><span data-stu-id="8295a-139">Use USB-C microphones for apps and / or Remote Assist.</span></span>| <span data-ttu-id="8295a-140">20279.1006</span><span class="sxs-lookup"><span data-stu-id="8295a-140">20279.1006</span></span> |
| [<span data-ttu-id="8295a-141">Kiosk 模式中新 App 的新 AUMID</span><span class="sxs-lookup"><span data-stu-id="8295a-141">New AUMIDs for new apps in Kiosk mode</span></span>](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | <span data-ttu-id="8295a-142">適用于新設定和 Edge 應用程式的 AUMID</span><span class="sxs-lookup"><span data-stu-id="8295a-142">AUMIDs for new Settings and Edge apps</span></span> | <span data-ttu-id="8295a-143">20279.1006</span><span class="sxs-lookup"><span data-stu-id="8295a-143">20279.1006</span></span> |
| [<span data-ttu-id="8295a-144">頁面設定可見度的新設定URIS</span><span class="sxs-lookup"><span data-stu-id="8295a-144">New SettingsURIs for Page Settings Visibility</span></span>](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | <span data-ttu-id="8295a-145">20+ 個新的 SettingsURIs for Settings/PageVisibilityList policy</span><span class="sxs-lookup"><span data-stu-id="8295a-145">20+ new SettingsURIs for Settings/PageVisibilityList policy</span></span> | <span data-ttu-id="8295a-146">20289.1000</span><span class="sxs-lookup"><span data-stu-id="8295a-146">20289.1000</span></span> |
| [<span data-ttu-id="8295a-147">改良的 Kiosk 模式失敗交還</span><span class="sxs-lookup"><span data-stu-id="8295a-147">Improved Kiosk mode failure handing</span></span>](#kiosk-mode-behavior-changes-for-handling-of-failures) | <span data-ttu-id="8295a-148">Kiosk 模式會先尋找全域指派的 Access，然後再尋找空白的開始功能表。</span><span class="sxs-lookup"><span data-stu-id="8295a-148">Kiosk mode looks for Global Assigned Access before empty start menu.</span></span> | <span data-ttu-id="8295a-149">20279.1006</span><span class="sxs-lookup"><span data-stu-id="8295a-149">20279.1006</span></span> |
| [<span data-ttu-id="8295a-150">設定後背診斷</span><span class="sxs-lookup"><span data-stu-id="8295a-150">Configure Fallback Diagnostics</span></span>](#configuring-fallback-diagnostics-via-settings-app) | <span data-ttu-id="8295a-151">在設定應用程式中設定後背診斷行為</span><span class="sxs-lookup"><span data-stu-id="8295a-151">Setting Fallback Diagnostic Behavior in Settings App</span></span> | <span data-ttu-id="8295a-152">20279.1006</span><span class="sxs-lookup"><span data-stu-id="8295a-152">20279.1006</span></span> |
| [<span data-ttu-id="8295a-153">與附近的裝置共用專案</span><span class="sxs-lookup"><span data-stu-id="8295a-153">Share things with nearby devices</span></span>](#share-things-with-nearby-devices) | <span data-ttu-id="8295a-154">從 HoloLens 共用檔案或 URL 到電腦</span><span class="sxs-lookup"><span data-stu-id="8295a-154">Share files or URLs from a HoloLens to a PC</span></span> | <span data-ttu-id="8295a-155">20279.1006</span><span class="sxs-lookup"><span data-stu-id="8295a-155">20279.1006</span></span> |
| [<span data-ttu-id="8295a-156">新的 OS Update 疑難排解員</span><span class="sxs-lookup"><span data-stu-id="8295a-156">New OS Update troubleshooter</span></span>](#new-os-update-troubleshooter) | <span data-ttu-id="8295a-157">OS 更新設定中的新疑難排解員</span><span class="sxs-lookup"><span data-stu-id="8295a-157">New troubleshooter in Settings for OS updates</span></span> | <span data-ttu-id="8295a-158">20279.1006</span><span class="sxs-lookup"><span data-stu-id="8295a-158">20279.1006</span></span> |
| [<span data-ttu-id="8295a-159">更新中的改良與修正</span><span class="sxs-lookup"><span data-stu-id="8295a-159">Improvements and fixes in the update</span></span>](#improvements-and-fixes-in-the-update) | <span data-ttu-id="8295a-160">更新中的其他修正。</span><span class="sxs-lookup"><span data-stu-id="8295a-160">Additional fixes in the update.</span></span> | <span data-ttu-id="8295a-161">20279.1006</span><span class="sxs-lookup"><span data-stu-id="8295a-161">20279.1006</span></span> |

### <span data-ttu-id="8295a-162">全新 Microsoft Edge 的介紹</span><span class="sxs-lookup"><span data-stu-id="8295a-162">Introducing the new Microsoft Edge</span></span>

![新 Microsoft Edge 標誌的舊版 Microsoft Edge 標誌動畫](images/new-edge.gif)

<span data-ttu-id="8295a-164">新的 Microsoft Edge [採用 Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) 開放來源專案，為客戶建立更佳的相容性，以及減少網頁開發人員的網路分散程度。</span><span class="sxs-lookup"><span data-stu-id="8295a-164">The new Microsoft Edge [adopts the Chromium open source project](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) to create better compatibility for customers and less fragmentation of the web for web developers.</span></span>

<span data-ttu-id="8295a-165">有了此 Insider Preview，HoloLens 2 客戶第一次可以使用新的 Microsoft Edge！</span><span class="sxs-lookup"><span data-stu-id="8295a-165">With this Insider preview, the new Microsoft Edge is available to HoloLens 2 customers for the first time!</span></span> <span data-ttu-id="8295a-166">雖然新的 Microsoft Edge 最終將會取代 HoloLens 2 上的舊版 Microsoft Edge，但測試人員目前可以使用這兩種瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="8295a-166">While the new Microsoft Edge will eventually replace legacy Microsoft Edge on HoloLens 2, both browsers are currently available to Insiders.</span></span> <span data-ttu-id="8295a-167">請透過新 Microsoft Edge 中的傳送\*\*\*\* 意見回饋功能，或透過意見回饋中心，與小組分享[意見和錯誤。](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="8295a-167">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge or via [Feedback Hub](hololens-feedback.md).</span></span>

![新的 Microsoft Edge 螢幕擷取畫面](images/new-edge-ui.png)

#### <span data-ttu-id="8295a-169">啟動新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8295a-169">Launching the new Microsoft Edge</span></span>

<span data-ttu-id="8295a-170">測試人員可以使用兩個版本的 Microsoft Edge：新的 Microsoft Edge 新 Microsoft Edge 圖示 (以藍色和綠色旋轉圖示) 和舊版 Microsoft Edge (以白色 ![ ](images/new_edge_logo.png) "e" 圖示) 表示。</span><span class="sxs-lookup"><span data-stu-id="8295a-170">There are two versions of Microsoft Edge available to Insiders: the new Microsoft Edge ![new Microsoft Edge icon](images/new_edge_logo.png) (represented by a blue and green swirl icon) and legacy Microsoft Edge (represented by the white "e" icon).</span></span> <span data-ttu-id="8295a-171">新的 Microsoft Edge 已釘釘到開始功能表，且會在您啟用網頁連結時自動啟動。</span><span class="sxs-lookup"><span data-stu-id="8295a-171">The new Microsoft Edge is pinned to the Start menu and will automatically launch when you activate a web link.</span></span> <span data-ttu-id="8295a-172">如果您想要還原成使用舊版 Microsoft Edge 做為預設網頁瀏覽器，請參閱下列重設預設應用程式 [的指示](#default-app-picker)。</span><span class="sxs-lookup"><span data-stu-id="8295a-172">If you would like to revert to using legacy Microsoft Edge as your default web browser, see the instructions below for [resetting default apps](#default-app-picker).</span></span>

> [!NOTE]
> <span data-ttu-id="8295a-173">當您第一次在 HoloLens 2 上啟動新的 Microsoft Edge 時，您的設定和資料將會從舊版 Microsoft Edge 中匯出。</span><span class="sxs-lookup"><span data-stu-id="8295a-173">When you first launch the new Microsoft Edge on HoloLens 2, your settings and data will be imported from legacy Microsoft Edge.</span></span> <span data-ttu-id="8295a-174">如果您在啟動新的 Microsoft Edge 之後繼續使用舊版 Microsoft Edge，新資料將不會從舊版 Microsoft Edge 同步處理到新的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="8295a-174">If you continue to use legacy Microsoft Edge after launching the new Microsoft Edge, that new data will not be synced from legacy Microsoft Edge to the new Microsoft Edge.</span></span>

#### <span data-ttu-id="8295a-175">設定新 Microsoft Edge 的策略設定</span><span class="sxs-lookup"><span data-stu-id="8295a-175">Configuring policy settings for the new Microsoft Edge</span></span>

<span data-ttu-id="8295a-176">新的 Microsoft Edge 提供 IT 系統管理員在 HoloLens 2 上的瀏覽器政策，比舊版 Microsoft Edge 提供的範圍更加廣泛。</span><span class="sxs-lookup"><span data-stu-id="8295a-176">The new Microsoft Edge offers IT admins a much broader set of browser policies on HoloLens 2 than were previously available with legacy Microsoft Edge.</span></span>

<span data-ttu-id="8295a-177">以下是一些實用的資源，可進一步學習管理新 Microsoft Edge 之策略設定：</span><span class="sxs-lookup"><span data-stu-id="8295a-177">Here are some helpful resources for learning more about managing policy settings for the new Microsoft Edge:</span></span>

- [<span data-ttu-id="8295a-178">使用 Microsoft Intune 設定 Microsoft Edge 原則設定</span><span class="sxs-lookup"><span data-stu-id="8295a-178">Configure Microsoft Edge policy settings with Microsoft Intune</span></span>](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [<span data-ttu-id="8295a-179">舊版 Microsoft Edge 與 Microsoft Edge 的原則對應</span><span class="sxs-lookup"><span data-stu-id="8295a-179">Microsoft Edge Legacy to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [<span data-ttu-id="8295a-180">Google Chrome 與 Microsoft Edge 的原則對應</span><span class="sxs-lookup"><span data-stu-id="8295a-180">Google Chrome to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- <span data-ttu-id="8295a-181">完整的 [Microsoft Edge Enterprise 檔](https://docs.microsoft.com/deployedge/)</span><span class="sxs-lookup"><span data-stu-id="8295a-181">Full [Microsoft Edge Enterprise documentation](https://docs.microsoft.com/deployedge/)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8295a-182">由於新 Microsoft Edge 支援的瀏覽器策略量大，我們的小組無法保證每一個新策略在 HoloLens 2 上運作。</span><span class="sxs-lookup"><span data-stu-id="8295a-182">Because of the volume of browser policies supported by the new Microsoft Edge, our team is unable to guarantee that each new policy works on HoloLens 2.</span></span> <span data-ttu-id="8295a-183">不過，相及于新 Microsoft Edge 中先前在 HoloLens 2 上支援的每個舊版 Microsoft Edge 政策，我們已測試及確認其功能如預期。</span><span class="sxs-lookup"><span data-stu-id="8295a-183">However, we've tested and confirmed than the new Microsoft Edge equivalent of each legacy Microsoft Edge policy previously supported on HoloLens 2 work as expected.</span></span> <span data-ttu-id="8295a-184">請參閱 [Microsoft Edge 舊版與 Microsoft Edge 策略](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) 對應，以尋找與 HoloLens 2 一同使用之每個舊版 Microsoft Edge 瀏覽器政策的新 Microsoft Edge 對應。</span><span class="sxs-lookup"><span data-stu-id="8295a-184">See [Microsoft Edge Legacy to Microsoft Edge policy mapping](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) to find the new Microsoft Edge equivalent of each legacy Microsoft Edge browser policy you were using with HoloLens 2.</span></span>
>
> <span data-ttu-id="8295a-185">我們知道至少有兩個新的 Microsoft Edge 政策無法與\*\* HoloLens 2 一起使用：</span><span class="sxs-lookup"><span data-stu-id="8295a-185">There are at least two new Microsoft Edge policies that we know *will not* work with HoloLens 2:</span></span>
> - <span data-ttu-id="8295a-186">EnterpriseModeSiteList</span><span class="sxs-lookup"><span data-stu-id="8295a-186">EnterpriseModeSiteList</span></span>
> - <span data-ttu-id="8295a-187">EnterpriseSiteListServiceURL</span><span class="sxs-lookup"><span data-stu-id="8295a-187">EnterpriseSiteListServiceURL</span></span>

#### <span data-ttu-id="8295a-188">HoloLens 2 上新 Microsoft Edge 的預計功能</span><span class="sxs-lookup"><span data-stu-id="8295a-188">What to expect from the new Microsoft Edge on HoloLens 2</span></span>

<span data-ttu-id="8295a-189">由於新的 Microsoft Edge 是原生 Win32 應用程式，具有新的 UWP 介面卡圖層，允許它在 UWP 裝置上執行，例如 HoloLens 2，因此可能無法立即使用某些功能。</span><span class="sxs-lookup"><span data-stu-id="8295a-189">Because the new Microsoft Edge is a native Win32 app with a new UWP adapter layer allowing it to run on UWP-only devices like HoloLens 2, some features may not be immediately available.</span></span> <span data-ttu-id="8295a-190">我們將支援未來幾個月的新案例和功能，因此請查看此空間以尋找最新資訊。</span><span class="sxs-lookup"><span data-stu-id="8295a-190">We'll be supporting new scenarios and features over the coming months, so check this space for up-to-date information.</span></span>

**<span data-ttu-id="8295a-191">預期可得的情境和功能：</span><span class="sxs-lookup"><span data-stu-id="8295a-191">Scenarios and features expected to work:</span></span>**
- <span data-ttu-id="8295a-192">第一次執行體驗、登出設定檔，以及同步</span><span class="sxs-lookup"><span data-stu-id="8295a-192">First-run experience, sign in to profile, and sync</span></span>
- <span data-ttu-id="8295a-193">網站應呈現並如預期行為</span><span class="sxs-lookup"><span data-stu-id="8295a-193">Websites should render and behave as expected</span></span>
- <span data-ttu-id="8295a-194">大部分瀏覽器功能 (我的最愛、歷程記錄等) 應該會如預期地使用</span><span class="sxs-lookup"><span data-stu-id="8295a-194">Most browser functionality (Favorites, History, etc.) should work as expected</span></span>
- <span data-ttu-id="8295a-195">深色模式</span><span class="sxs-lookup"><span data-stu-id="8295a-195">Dark mode</span></span>
- <span data-ttu-id="8295a-196">將 Web App 安裝到裝置</span><span class="sxs-lookup"><span data-stu-id="8295a-196">Installing web apps to the device</span></span>
- <span data-ttu-id="8295a-197">安裝擴充 (請告知我們您是否使用任何在 HoloLens 2 或 HoloLens 2 上無法正常運作的) </span><span class="sxs-lookup"><span data-stu-id="8295a-197">Installing extensions (please let us know if you use any extensions that don't work properly on HoloLens 2)</span></span>
- <span data-ttu-id="8295a-198">檢視和標記 PDF</span><span class="sxs-lookup"><span data-stu-id="8295a-198">Viewing and marking up a PDF</span></span>
- <span data-ttu-id="8295a-199">單一瀏覽器視窗的空間音效</span><span class="sxs-lookup"><span data-stu-id="8295a-199">Spatial sound from a single browser window</span></span>
- <span data-ttu-id="8295a-200">瀏覽器的自動和手動更新</span><span class="sxs-lookup"><span data-stu-id="8295a-200">Automatic and manual updating of the browser</span></span>
- <span data-ttu-id="8295a-201">使用 「儲存至 PDF」選項 (從列印功能表儲存 PDF) </span><span class="sxs-lookup"><span data-stu-id="8295a-201">Saving a PDF from the Print menu (using "Save to PDF" option)</span></span>

**<span data-ttu-id="8295a-202">即將推出案例和功能：</span><span class="sxs-lookup"><span data-stu-id="8295a-202">Scenarios and features coming soon:</span></span>**
- <span data-ttu-id="8295a-203">WebXR 和 360 Viewer 擴充功能</span><span class="sxs-lookup"><span data-stu-id="8295a-203">WebXR and 360 Viewer extension</span></span>
- <span data-ttu-id="8295a-204">當您流覽環境中多個視窗時，內容還原以修正視窗</span><span class="sxs-lookup"><span data-stu-id="8295a-204">Content restoration to correct window when browsing across multiple windows placed in your environment</span></span>

**<span data-ttu-id="8295a-205">無法預期的案例和功能：</span><span class="sxs-lookup"><span data-stu-id="8295a-205">Scenarios and features not expected to work:</span></span>**
- <span data-ttu-id="8295a-206">包含同時音訊流的多個視窗的空間音效</span><span class="sxs-lookup"><span data-stu-id="8295a-206">Spatial sound from multiple windows with simultaneous audio streams</span></span>
- <span data-ttu-id="8295a-207">「請看，說吧」</span><span class="sxs-lookup"><span data-stu-id="8295a-207">"See it, say it"</span></span>
- <span data-ttu-id="8295a-208">列印</span><span class="sxs-lookup"><span data-stu-id="8295a-208">Printing</span></span>

**<span data-ttu-id="8295a-209">已知瀏覽器的熱門問題：</span><span class="sxs-lookup"><span data-stu-id="8295a-209">Top known browser issues:</span></span>**
- <span data-ttu-id="8295a-210">重設您的裝置將會移除新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8295a-210">Resetting your device will remove the new Microsoft Edge</span></span>
- <span data-ttu-id="8295a-211">全攝影鍵盤中的放大鏡預覽顯示不正確的內容</span><span class="sxs-lookup"><span data-stu-id="8295a-211">The magnifier preview in the holographic keyboard shows incorrect content</span></span>

#### <span data-ttu-id="8295a-212">Microsoft Edge Insider Channels</span><span class="sxs-lookup"><span data-stu-id="8295a-212">Microsoft Edge Insider channels</span></span>

<span data-ttu-id="8295a-213">Microsoft Edge 小組提供三個預覽通道給 Edge 測試人員社群：Beta、Dev 和 Canary。</span><span class="sxs-lookup"><span data-stu-id="8295a-213">The Microsoft Edge team makes three preview channels available to the Edge Insider community: Beta, Dev, and Canary.</span></span> <span data-ttu-id="8295a-214">安裝預覽通道不會卸載 HoloLens 2 上已發佈的 Microsoft Edge 版本，而且您可以同時安裝多個版本。</span><span class="sxs-lookup"><span data-stu-id="8295a-214">Installing a preview channel doesn't uninstall the released version of Microsoft Edge on your HoloLens 2, and you can install more than one at the same time.</span></span> 

<span data-ttu-id="8295a-215">請流覽 [Microsoft Edge Insider 首頁](https://www.microsoftedgeinsider.com) ，深入瞭解 Microsoft Edge Insider 社群。</span><span class="sxs-lookup"><span data-stu-id="8295a-215">Visit the [Microsoft Edge Insider homepage](https://www.microsoftedgeinsider.com) to learn more about the Edge Insider community.</span></span> <span data-ttu-id="8295a-216">若要深入瞭解不同的 Edge Insider 通道並開始使用，請流覽 [Edge Insider 下載頁面](https://www.microsoftedgeinsider.com/download)。</span><span class="sxs-lookup"><span data-stu-id="8295a-216">To learn more about the different Edge Insider channels and get started, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download).</span></span>

<span data-ttu-id="8295a-217">有幾個方法可用於將 Microsoft Edge 測試人員通道安裝到 HoloLens 2：</span><span class="sxs-lookup"><span data-stu-id="8295a-217">There are a couple methods available for installing Microsoft Edge Insider channels to HoloLens 2:</span></span>

**<span data-ttu-id="8295a-218">直接安裝在裝置 (目前僅適用于未管理裝置) </span><span class="sxs-lookup"><span data-stu-id="8295a-218">Direct install on device (currently only available to unmanaged devices)</span></span>**
  1. <span data-ttu-id="8295a-219">在 HoloLens 2 上，流覽 [Edge Insider 下載頁面](https://www.microsoftedgeinsider.com/download)。</span><span class="sxs-lookup"><span data-stu-id="8295a-219">On your HoloLens 2, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download).</span></span>
  1. <span data-ttu-id="8295a-220">選取要安裝之 Edge Insider 通道的 **HoloLens 2** 下載按鈕。</span><span class="sxs-lookup"><span data-stu-id="8295a-220">Select the **Download for HoloLens 2** button for the Edge Insider channel you wish to install.</span></span>
  1. <span data-ttu-id="8295a-221">從 Edge 下載佇列或裝置上的 「下載」資料夾啟動下載的 .msix 檔案， (檔案檔案) 。</span><span class="sxs-lookup"><span data-stu-id="8295a-221">Launch the downloaded .msix file from the Edge download queue or from your device's "Downloads" folder (using File Explorer).</span></span>
  1. <span data-ttu-id="8295a-222">[應用程式安裝程式](app-deploy-app-installer.md) 將會啟動。</span><span class="sxs-lookup"><span data-stu-id="8295a-222">[App installer](app-deploy-app-installer.md) will launch.</span></span>
  1. <span data-ttu-id="8295a-223">選取安裝 **按鈕** 。</span><span class="sxs-lookup"><span data-stu-id="8295a-223">Select the **Install** button.</span></span>
  1. <span data-ttu-id="8295a-224">成功安裝之後，您可以在開始功能表的所有應用程式清單中，將 Microsoft Edge Beta 版、Dev\*\*\*\* 或 Canary 視為個別專案。</span><span class="sxs-lookup"><span data-stu-id="8295a-224">After successful install, you'll find Microsoft Edge Beta, Dev, or Canary as a separate entry in the **All apps** list of the Start menu.</span></span>

**<span data-ttu-id="8295a-225">透過電腦使用 Windows 裝置入口網站 (需要啟用[](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)HoloLens 2 應用程式上的開發人員) </span><span class="sxs-lookup"><span data-stu-id="8295a-225">Install via PC with Windows Device Portal (requires [developer mode](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) to be enabled on HoloLens 2)</span></span>**
  1. <span data-ttu-id="8295a-226">在您的電腦上，流覽 [Edge Insider 下載頁面](https://www.microsoftedgeinsider.com/download)。</span><span class="sxs-lookup"><span data-stu-id="8295a-226">On your PC, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download).</span></span>
  1. <span data-ttu-id="8295a-227">針對要安裝的 Edge **Insider** 通道，選取 「下載 Windows 10」按鈕旁的下拉式箭號按鈕。</span><span class="sxs-lookup"><span data-stu-id="8295a-227">Select the **drop-down arrow button** next to the "Download for Windows 10" button for the Edge Insider channel you wish to install.</span></span>
  1. <span data-ttu-id="8295a-228">在**下拉式功能表中選取 HoloLens 2。**</span><span class="sxs-lookup"><span data-stu-id="8295a-228">Select **HoloLens 2** in the drop-down menu.</span></span>
  1. <span data-ttu-id="8295a-229">將 .msix 檔案儲存到您電腦中的 「下載」資料夾 (或另一個您可以輕鬆地找到) 。</span><span class="sxs-lookup"><span data-stu-id="8295a-229">Save the .msix file to the "Downloads" folder of your PC (or another folder you can easily find).</span></span>
  1. <span data-ttu-id="8295a-230">使用 [您電腦中的 Windows](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) 裝置入口網站在 HoloLens 2 上安裝下載的 .msix 檔案。</span><span class="sxs-lookup"><span data-stu-id="8295a-230">Use [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) on your PC to install the downloaded .msix file on HoloLens 2.</span></span>
  1. <span data-ttu-id="8295a-231">成功安裝之後，您可以在開始功能表的所有應用程式清單中，將 Microsoft Edge Beta、Dev 或\*\*\*\* Canary 視為個別專案。</span><span class="sxs-lookup"><span data-stu-id="8295a-231">After successful install, you'll find Microsoft Edge Beta, Dev, or Canary as a separate entry in the **All apps** list of the Start menu.</span></span>

> [!NOTE]
> <span data-ttu-id="8295a-232">在 HoloLens 2 的 Windows 測試人員預覽版期間，您裝置上的 Microsoft Edge 版本可能高於某些 (或 Microsoft Edge 測試人員) 中提供的版本。</span><span class="sxs-lookup"><span data-stu-id="8295a-232">During this Windows Insider preview for HoloLens 2, the version of Microsoft Edge on your device may be higher than those available in some (or all) of the Microsoft Edge Insider channels.</span></span> <span data-ttu-id="8295a-233">這是為了確保專為 HoloLens 2 的網頁瀏覽器所設計的新功能和修正程式能儘快連至我們的 Windows 測試人員。</span><span class="sxs-lookup"><span data-stu-id="8295a-233">This is to ensure new features and fixes specifically targeting the web browser on HoloLens 2 are getting to our Windows Insiders as quickly as possible.</span></span> <span data-ttu-id="8295a-234">下一次 Windows 更新公開發行之後，Microsoft Edge 測試人員通道版本將會超越並超越 HoloLens 2 上的 Microsoft Edge 版本。</span><span class="sxs-lookup"><span data-stu-id="8295a-234">Shortly after the public release of the next Windows update, the Microsoft Edge Insider channel builds will surpass, and stay ahead of, the version of Microsoft Edge on your HoloLens 2.</span></span>

### <span data-ttu-id="8295a-235">WebXR 和 360 Viewer</span><span class="sxs-lookup"><span data-stu-id="8295a-235">WebXR and 360 Viewer</span></span>

*<span data-ttu-id="8295a-236">在 Windows Insider Build 20289.1000 中新增</span><span class="sxs-lookup"><span data-stu-id="8295a-236">Added in Windows Insider build 20289.1000</span></span>*

<span data-ttu-id="8295a-237">新的 Microsoft Edge 支援 WebXR，這是建立取代 WebVR (網頁體驗的新) 。</span><span class="sxs-lookup"><span data-stu-id="8295a-237">The new Microsoft Edge includes support for WebXR, which is the new standard for creating immersive web experiences (replacing WebVR).</span></span> <span data-ttu-id="8295a-238">許多沉浸式網頁體驗在設計時都考慮到 VR， (以虛擬環境) 取代您的視野，但 HoloLens 2 也支援這些體驗。</span><span class="sxs-lookup"><span data-stu-id="8295a-238">Many immersive web experiences were designed with VR in mind (they replace your field of view with a virtual environment), but these experiences are also supported by HoloLens 2.</span></span> <span data-ttu-id="8295a-239">WebXR 標準也可啟用使用您實體環境的增強和混合實境沉浸式 Web 體驗。</span><span class="sxs-lookup"><span data-stu-id="8295a-239">The WebXR standard also enables augmented and mixed reality immersive web experiences that use your physical environment.</span></span> <span data-ttu-id="8295a-240">隨著開發人員花更多時間使用 WebXR，我們預期新的增強和混合實境沉浸式體驗將送達 HoloLens 2 客戶嘗試！</span><span class="sxs-lookup"><span data-stu-id="8295a-240">As developers spend more time with WebXR, we anticipate new augmented and mixed reality immersive experiences will arrive for HoloLens 2 customers to try!</span></span>

<span data-ttu-id="8295a-241">360 檢視器擴充功能建立在 WebXR 上，會自動與 HoloLens 2 上的新 Microsoft Edge 一起安裝。</span><span class="sxs-lookup"><span data-stu-id="8295a-241">The 360 Viewer extension is built on WebXR and automatically installs alongside the new Microsoft Edge on HoloLens 2.</span></span> <span data-ttu-id="8295a-242">此 Web 擴充功能讓您能沉浸于 360 度影片中。</span><span class="sxs-lookup"><span data-stu-id="8295a-242">This web extension gives you the ability to immerse yourself in 360-degree videos.</span></span> <span data-ttu-id="8295a-243">YouTube 提供最多 360 個影片選擇，因此我們建議您從該影片開始。</span><span class="sxs-lookup"><span data-stu-id="8295a-243">YouTube offers the largest selection of 360 videos, so we encourage you to start there.</span></span>

#### <span data-ttu-id="8295a-244">如何使用 WebXR</span><span class="sxs-lookup"><span data-stu-id="8295a-244">How to use WebXR</span></span>

1. <span data-ttu-id="8295a-245">使用 WebXR 支援流覽至網站。</span><span class="sxs-lookup"><span data-stu-id="8295a-245">Navigate to a website with WebXR support.</span></span>
1. <span data-ttu-id="8295a-246">選取網站的 **Enter VR** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="8295a-246">Select the **Enter VR** button on the website.</span></span> <span data-ttu-id="8295a-247">這個按鈕的位置和視覺呈現方式會因網站而異，但看起來可能類似：</span><span class="sxs-lookup"><span data-stu-id="8295a-247">The location and visual representation of this button may vary per website, but it may look similar to:</span></span>

    ![輸入 VR 按鈕範例](images/75px-enter-vr.png)

1. <span data-ttu-id="8295a-249">當您第一次嘗試啟動特定網域上的 WebXR 體驗時，瀏覽器會要求同意進入沉浸式視圖，**選取允許。**</span><span class="sxs-lookup"><span data-stu-id="8295a-249">The first time you try to launch a WebXR experience on a specific domain, the browser will ask for consent to enter an immersive view, select **Allow**.</span></span>
1. <span data-ttu-id="8295a-250">使用 [HoloLens 2 手勢](hololens2-basic-usage.md#the-hand-tracking-frame) 操作體驗。</span><span class="sxs-lookup"><span data-stu-id="8295a-250">Use [HoloLens 2 gestures](hololens2-basic-usage.md#the-hand-tracking-frame) to manipulate the experience.</span></span>
1. <span data-ttu-id="8295a-251">如果體驗沒有離開 **按鈕，請使用** 開始 [手勢](hololens2-basic-usage.md#start-gesture) 返回首頁。</span><span class="sxs-lookup"><span data-stu-id="8295a-251">If the experience doesn't have an **Exit** button, use the [Start gesture](hololens2-basic-usage.md#start-gesture) to return home.</span></span>

**<span data-ttu-id="8295a-252">建議的 WebXR 範例</span><span class="sxs-lookup"><span data-stu-id="8295a-252">Recommended WebXR samples</span></span>**
- <span data-ttu-id="8295a-253">360 檢視器 (查看下一節) </span><span class="sxs-lookup"><span data-stu-id="8295a-253">360 Viewer (see next section)</span></span>
- [<span data-ttu-id="8295a-254">XR 小龍</span><span class="sxs-lookup"><span data-stu-id="8295a-254">XR Dinosaurs</span></span>](https://www.xrdinosaurs.com/)
- [<span data-ttu-id="8295a-255">Barista Express</span><span class="sxs-lookup"><span data-stu-id="8295a-255">Barista Express</span></span>](https://constructarca.de/game/barista-express/)
- [<span data-ttu-id="8295a-256">WebXR 小圖</span><span class="sxs-lookup"><span data-stu-id="8295a-256">WebXR Paint</span></span>](https://threejs.org/examples/webxr_vr_paint.html)

#### <span data-ttu-id="8295a-257">如何使用 360 Viewer</span><span class="sxs-lookup"><span data-stu-id="8295a-257">How to use 360 Viewer</span></span>

1. <span data-ttu-id="8295a-258">流覽至 YouTube 上的 360 度影片。</span><span class="sxs-lookup"><span data-stu-id="8295a-258">Navigate to a 360-degree video on YouTube.</span></span>
1. <span data-ttu-id="8295a-259">在視訊畫面中，選取混合實境耳機按鈕：</span><span class="sxs-lookup"><span data-stu-id="8295a-259">In the video frame, select the mixed reality headset button:</span></span>

    ![啟用 360 檢視器的按鈕](images/enter-360-viewer.jpg)

1. <span data-ttu-id="8295a-261">當您第一次嘗試在特定的網域上啟動 360 Viewer 時，瀏覽器會要求同意進入沉浸式檢視。</span><span class="sxs-lookup"><span data-stu-id="8295a-261">The first time you try to launch 360 Viewer on a specific domain, the browser will ask for consent to enter an immersive view.</span></span> <span data-ttu-id="8295a-262">選取 **允許**。</span><span class="sxs-lookup"><span data-stu-id="8295a-262">Select **Allow**.</span></span>
1. <span data-ttu-id="8295a-263">[點兩](hololens2-basic-usage.md#select-using-air-tap) 下以顯示播放控制項。</span><span class="sxs-lookup"><span data-stu-id="8295a-263">[Air tap](hololens2-basic-usage.md#select-using-air-tap) to bring up the playback controls.</span></span> <span data-ttu-id="8295a-264">使用 [手](hololens2-basic-usage.md#select-using-air-tap) 拍和空中點兩下來播放/暫停、向前/向後跳、開啟/關閉輔助字幕，或 (結束沉浸式) 。</span><span class="sxs-lookup"><span data-stu-id="8295a-264">Use [hand rays and air tap](hololens2-basic-usage.md#select-using-air-tap) to play/pause, skip forward/back, turn captions on/off, or stop the experience (which exits the immersive view).</span></span> <span data-ttu-id="8295a-265">播放控制項會在閒置數秒後消失。</span><span class="sxs-lookup"><span data-stu-id="8295a-265">The playback controls will disappear after a few seconds of inactivity.</span></span>

#### <span data-ttu-id="8295a-266">WebXR 和 360 檢視器已知問題</span><span class="sxs-lookup"><span data-stu-id="8295a-266">Top WebXR and 360 Viewer known issues</span></span>
- <span data-ttu-id="8295a-267">在 WebXR 體驗中，當您傾斜頭部或四處移動時，全形影像可能會移動或傾斜。</span><span class="sxs-lookup"><span data-stu-id="8295a-267">In WebXR experiences, holograms may shift or tilt when you tilt your head or move around your environment.</span></span>
- <span data-ttu-id="8295a-268">根據 WebXR 體驗的複雜度，框架速率可能會降低或斷斷續續。</span><span class="sxs-lookup"><span data-stu-id="8295a-268">Depending on the complexity of the WebXR experience, the framerate may drop or stutter.</span></span>
- <span data-ttu-id="8295a-269">WebXR 目前還無法提供手寫手部連接。</span><span class="sxs-lookup"><span data-stu-id="8295a-269">Articulated hand joints are not yet available in WebXR.</span></span>
- <span data-ttu-id="8295a-270">在離開 WebXR 或 360 檢視器體驗時，混合實境首頁中的全形影像可能需要 30 秒或更長時間重新出現。</span><span class="sxs-lookup"><span data-stu-id="8295a-270">When exiting a WebXR or 360 Viewer experience, it may take 30 seconds or more for holograms in the mixed reality home to reappear.</span></span>
- <span data-ttu-id="8295a-271">YouTube 外網站的 360 個影片可能無法如預期地播放。</span><span class="sxs-lookup"><span data-stu-id="8295a-271">360 videos from websites other than YouTube may not work as expected.</span></span>
- <span data-ttu-id="8295a-272">如果 360 影片未進入沉浸式 (或混合實境耳機按鈕未顯示在) ，請嘗試重新組織頁面。</span><span class="sxs-lookup"><span data-stu-id="8295a-272">If 360 videos don't enter immersive view (or the mixed reality headset button doesn't appear), try refreshing the page.</span></span>
- <span data-ttu-id="8295a-273">在 HoloLens 2 上的 360 Viewer 中還看不到標題。</span><span class="sxs-lookup"><span data-stu-id="8295a-273">Captions are not yet visible in 360 Viewer on HoloLens 2.</span></span>
- <span data-ttu-id="8295a-274">在 360 Viewer 中暫停影片會停止影片的顯示 (但選取播放按鈕會正確繼續播放) 。</span><span class="sxs-lookup"><span data-stu-id="8295a-274">Pausing a video in 360 Viewer stops the video from rendering (but selecting the play button correctly resumes playback).</span></span>
- <span data-ttu-id="8295a-275">360 Viewer 中的 「下一段影片」按鈕目前無法工作。</span><span class="sxs-lookup"><span data-stu-id="8295a-275">The "next video" button in 360 Viewer does not currently work.</span></span>
- <span data-ttu-id="8295a-276">您可以在沉浸式「影區」模式中播放 2D 影片，但框架速率小於 30 fps。</span><span class="sxs-lookup"><span data-stu-id="8295a-276">You can play 2D videos in an immersive "theater" mode, but the framerate will be less than 30 fps.</span></span>

#### <span data-ttu-id="8295a-277">在 WebXR 和 360 Viewer 上提供意見回饋</span><span class="sxs-lookup"><span data-stu-id="8295a-277">Providing feedback on WebXR and 360 Viewer</span></span>

<span data-ttu-id="8295a-278">請透過新 Microsoft Edge 中的傳送\*\*\*\* 意見回饋功能，與小組分享意見回饋和錯誤。</span><span class="sxs-lookup"><span data-stu-id="8295a-278">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge.</span></span>

### <span data-ttu-id="8295a-279">新增設定應用程式</span><span class="sxs-lookup"><span data-stu-id="8295a-279">New Settings app</span></span>

<span data-ttu-id="8295a-280">此版本推出後，我們將推出新版的設定應用程式。</span><span class="sxs-lookup"><span data-stu-id="8295a-280">With this release, we're introducing a new version of the Settings app.</span></span> <span data-ttu-id="8295a-281">新的設定應用程式包含 HoloLens 2 的新功能和下列領域的擴充設定：音效、Power & 睡眠、網路 & 網際網路、應用程式、帳戶、輕鬆存取等等。</span><span class="sxs-lookup"><span data-stu-id="8295a-281">The new Settings app includes new features and expanded settings for HoloLens 2 in the following areas: Sound, Power & sleep, Network & Internet, Apps, Accounts, Ease of Access, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="8295a-282">由於新的設定應用程式與舊版的設定應用程式不同，因此您先前置於環境周圍的任何設定視窗，都會在更新時移除。</span><span class="sxs-lookup"><span data-stu-id="8295a-282">Because the new Settings app is distinct from the legacy Settings app, any Settings windows you previously placed around your environment will be removed upon update.</span></span>

![新的設定應用程式首頁](images/new-settings-app.png)

**<span data-ttu-id="8295a-284">新功能和設定</span><span class="sxs-lookup"><span data-stu-id="8295a-284">New features and settings</span></span>**
- <span data-ttu-id="8295a-285">設定搜尋：使用關鍵字或設定名稱從 [設定首頁搜尋設定。</span><span class="sxs-lookup"><span data-stu-id="8295a-285">Settings search: search for settings from the Settings homepage using keywords or the setting's name.</span></span>
- <span data-ttu-id="8295a-286">系統>音效：</span><span class="sxs-lookup"><span data-stu-id="8295a-286">System > Sound:</span></span>
  - <span data-ttu-id="8295a-287">輸入和輸出音訊裝置：獨立選擇您的輸入和輸出音訊裝置 (例如，透過藍牙耳機聆聽音訊，或使用 USB-C 麥克風進行音訊輸入) 。</span><span class="sxs-lookup"><span data-stu-id="8295a-287">Input and output audio devices: independently choose your input and output audio devices (for example, listen to audio via Bluetooth headphones or use a USB-C microphone for audio input).</span></span>
    > [!NOTE]
    > <span data-ttu-id="8295a-288">HoloLens 2 不支援藍牙麥克風。</span><span class="sxs-lookup"><span data-stu-id="8295a-288">Bluetooth microphones are not supported by HoloLens 2.</span></span>
  - <span data-ttu-id="8295a-289">應用程式音量：分別調整每個 App 的音量。</span><span class="sxs-lookup"><span data-stu-id="8295a-289">App volume: independently adjust the volume of each app.</span></span>
- <span data-ttu-id="8295a-290">系統>電源&：選擇裝置閒置一段時間後應該進入睡眠狀態。</span><span class="sxs-lookup"><span data-stu-id="8295a-290">System > Power & sleep: choose when the device should go to sleep after a period of inactivity.</span></span>
- <span data-ttu-id="8295a-291">系統>：手動啟用省電模式或設定電池閾值，此時省電模式會自動開啟。</span><span class="sxs-lookup"><span data-stu-id="8295a-291">System > Battery: manually enable battery saver mode or set a battery threshold at which point battery saver mode turns on automatically.</span></span>
- <span data-ttu-id="8295a-292">USB 裝置>：您預設可以停用 USB 連接。</span><span class="sxs-lookup"><span data-stu-id="8295a-292">Devices > USB: you can disable USB connections by default.</span></span>
- <span data-ttu-id="8295a-293">網路&網際網路：</span><span class="sxs-lookup"><span data-stu-id="8295a-293">Network & Internet:</span></span>
  - <span data-ttu-id="8295a-294">USB-C 乙太網路介面卡現在會出現在網際網路&中。</span><span class="sxs-lookup"><span data-stu-id="8295a-294">USB-C Ethernet adapters will now appear in Network & Internet.</span></span>
  - <span data-ttu-id="8295a-295">USB-C 乙太網路介面卡設定現已提供，包括其 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8295a-295">USB-C Ethernet adapter settings are now available, including its IP address.</span></span>
  - <span data-ttu-id="8295a-296">現在您可以在 HoloLens 2 上啟用飛航模式。</span><span class="sxs-lookup"><span data-stu-id="8295a-296">You can now enable airplane mode on HoloLens 2.</span></span>
- <span data-ttu-id="8295a-297">應用程式：您可以重設用於檔案和連結類型的預設應用程式。</span><span class="sxs-lookup"><span data-stu-id="8295a-297">Apps: you can reset the default apps used for file and link types.</span></span> <span data-ttu-id="8295a-298">詳細資訊請參閱預設 [應用程式選擇器](#default-app-picker)。</span><span class="sxs-lookup"><span data-stu-id="8295a-298">For more information see [Default app picker](#default-app-picker).</span></span>
- <span data-ttu-id="8295a-299">帳戶>：裝置擁有者可以新增使用者、將標準使用者升級為裝置擁有者、將裝置擁有者降級為標準使用者，以及移除使用者。</span><span class="sxs-lookup"><span data-stu-id="8295a-299">Accounts > Other users: device owners can add users, upgrade standard users to device owners, downgrade device owners to standard users, and remove users.</span></span>
- <span data-ttu-id="8295a-300">輕鬆存取：變更文字大小和一些視覺效果。</span><span class="sxs-lookup"><span data-stu-id="8295a-300">Ease of Access: change text size and some visual effects.</span></span>

**<span data-ttu-id="8295a-301">已知問題</span><span class="sxs-lookup"><span data-stu-id="8295a-301">Known issues</span></span>**
- <span data-ttu-id="8295a-302">先前放置的設定視窗將會移除 (上方的備註) 。</span><span class="sxs-lookup"><span data-stu-id="8295a-302">Previously placed Settings windows will be removed (see note above).</span></span>
- <span data-ttu-id="8295a-303">流覽通知頁面可能會導致設定應用程式當機 (調查) 。</span><span class="sxs-lookup"><span data-stu-id="8295a-303">Visiting the Notifications page may crash the Settings app (investigating).</span></span>
- <span data-ttu-id="8295a-304">乙太網路頁面目前不會顯示 (修正) 。</span><span class="sxs-lookup"><span data-stu-id="8295a-304">The Ethernet page currently doesn't show up (to be fixed soon).</span></span>
- <span data-ttu-id="8295a-305">您無法再使用設定應用程式重新命名您的裝置 (IT 系統管理員可以使用部署套件或 MDM 來重新命名裝置) 。</span><span class="sxs-lookup"><span data-stu-id="8295a-305">You can no longer rename your device with the Settings app (IT admins can use provisioning packages or MDM to rename devices).</span></span>
- <span data-ttu-id="8295a-306">新版 Microsoft Edge 的電池使用量可能無法正確無誤，因為其性質是 UWP 介面卡圖層支援的 Win32 桌面應用程式， (預期近期將修正) 。</span><span class="sxs-lookup"><span data-stu-id="8295a-306">Battery usage for the new Microsoft Edge may not be accurate, due to its nature as a Win32 desktop application supported by a UWP adapter layer (no fix anticipated soon).</span></span>

### <span data-ttu-id="8295a-307">顯示色彩校正</span><span class="sxs-lookup"><span data-stu-id="8295a-307">Display color calibration</span></span>

*<span data-ttu-id="8295a-308">在 Windows Insider Build 20293.1000 中新增</span><span class="sxs-lookup"><span data-stu-id="8295a-308">Added in Windows Insider build 20293.1000</span></span>*

<span data-ttu-id="8295a-309">有了這個新設定，您可以選取 HoloLens 2 顯示器的替代色彩設定檔。</span><span class="sxs-lookup"><span data-stu-id="8295a-309">With this new setting, you can select an alternative color profile for your HoloLens 2 display.</span></span> <span data-ttu-id="8295a-310">這可協助色彩顯示更精確，尤其是在較低的顯示亮度等級。</span><span class="sxs-lookup"><span data-stu-id="8295a-310">This may help colors appear more accurate, especially at lower display brightness levels.</span></span> <span data-ttu-id="8295a-311">顯示色彩校正可在設定 App 的系統調整>頁面上找到。</span><span class="sxs-lookup"><span data-stu-id="8295a-311">Display color calibration can be found in the Settings app, on the System > Calibration page.</span></span>

#### <span data-ttu-id="8295a-312">如何使用顯示色彩校正</span><span class="sxs-lookup"><span data-stu-id="8295a-312">How to use display color calibration</span></span>

1. <span data-ttu-id="8295a-313">啟動設定 **應用程式** ，然後流覽至 **系統>校正**。</span><span class="sxs-lookup"><span data-stu-id="8295a-313">Launch the **Settings** app and navigate to **System > Calibration**.</span></span>
1. <span data-ttu-id="8295a-314">在 **顯示色彩校正下**，選取執行 **顯示色彩校正** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="8295a-314">Under **Display color calibration**, select the **Run display color calibration** button.</span></span>
1. <span data-ttu-id="8295a-315">顯示色彩校正體驗將會啟動，並鼓勵您確認您的 Visor 處於正確的位置。</span><span class="sxs-lookup"><span data-stu-id="8295a-315">The display color calibration experience will launch and encourage you to make sure your visor is in the correct position.</span></span>
1. <span data-ttu-id="8295a-316">在您繼續進行指示對話方塊後，您的顯示器會自動變暗為 30% 的亮度。</span><span class="sxs-lookup"><span data-stu-id="8295a-316">After you proceed through the instruction dialog boxes, your display will automatically be dimmed to 30% brightness.</span></span>
    > [!TIP]
    > <span data-ttu-id="8295a-317">如果您無法看到環境中變暗的場景，您可以使用裝置左側的亮度按鈕，手動調整 HoloLens 2 的亮度等級。</span><span class="sxs-lookup"><span data-stu-id="8295a-317">If you're having trouble seeing the dimmed scene in your environment, you can manually adjust the brightness level of HoloLens 2 using the brightness buttons on the left side of the device.</span></span>
1. <span data-ttu-id="8295a-318">選取按鈕 1 到 6 以立即試用每個色彩設定檔，並找出最適合您眼睛的設定檔 (這通常表示協助場景呈現最中立的設定檔，而灰階圖樣和色調看起來如預期。) </span><span class="sxs-lookup"><span data-stu-id="8295a-318">Select buttons 1-6 to instantly try out each color profile, and find one that looks the best to your eyes (this usually means the profile that helps the scene appear most neutral, with the grayscale pattern and skin tones looking as expected.)</span></span>

    ![顯示色彩校正場景](images/color-cal-ui.png)
    
1. <span data-ttu-id="8295a-320">當您對選取的設定檔滿意時，請選取儲存&**按鈕**</span><span class="sxs-lookup"><span data-stu-id="8295a-320">When you're happy with the selected profile, select the **Save & Exit** button</span></span>
1. <span data-ttu-id="8295a-321">如果您不想進行變更，請選取取消& **按鈕** ，您的變更將會還原</span><span class="sxs-lookup"><span data-stu-id="8295a-321">If you prefer not to make changes, select the **Cancel & Exit** button and your changes will be reverted</span></span>

> [!TIP]
> <span data-ttu-id="8295a-322">以下是使用顯示色彩校正設定時請記住的一些實用秘訣：</span><span class="sxs-lookup"><span data-stu-id="8295a-322">Here are some helpful tips to keep in mind while using the display color calibration setting:</span></span>
> - <span data-ttu-id="8295a-323">您可以隨時從設定重新執行顯示色彩校正</span><span class="sxs-lookup"><span data-stu-id="8295a-323">You can re-run display color calibration from Settings whenever you'd like</span></span>
> - <span data-ttu-id="8295a-324">如果裝置上的任何人先前曾使用設定來變更色彩設定檔，最新變更的日期/時間會反映在設定頁面上</span><span class="sxs-lookup"><span data-stu-id="8295a-324">If anyone on the device has previously used the setting to change color profiles, the date/time of the most recent change will be reflected on the Settings page</span></span>
> - <span data-ttu-id="8295a-325">當您重新執行顯示色彩校正時，先前儲存的色彩設定檔會反顯示，而設定檔 0 不會顯示為 (因為設定檔 0 代表顯示器的原始色彩設定檔) </span><span class="sxs-lookup"><span data-stu-id="8295a-325">When you re-run display color calibration, the color profile that was previously saved will be highlighted and Profile 0 will not appear (as Profile 0 represents the display's original color profile)</span></span>
> - <span data-ttu-id="8295a-326">如果您想要還原為顯示器的原始色彩設定檔，可以從設定頁面執行此 [ (瞭解如何重](#how-to-reset-color-profile) 設色彩設定檔) </span><span class="sxs-lookup"><span data-stu-id="8295a-326">If you want to revert to the display's original color profile, you can do so from the Settings page (see [how to reset color profile](#how-to-reset-color-profile))</span></span>

#### <span data-ttu-id="8295a-327">如何重設色彩設定檔</span><span class="sxs-lookup"><span data-stu-id="8295a-327">How to reset color profile</span></span>

<span data-ttu-id="8295a-328">如果您不滿意儲存到 HoloLens 2 的自訂色彩設定檔，您可以還原裝置的原始色彩設定檔：</span><span class="sxs-lookup"><span data-stu-id="8295a-328">If you're unhappy with the custom color profile saved to your HoloLens 2, you can restore the device's original color profile:</span></span>
1. <span data-ttu-id="8295a-329">啟動設定 **應用程式** ，然後流覽至 **系統>校正**。</span><span class="sxs-lookup"><span data-stu-id="8295a-329">Launch the **Settings** app and navigate to **System > Calibration**.</span></span>
1. <span data-ttu-id="8295a-330">在 **顯示色彩校正下**，選取重 **設成預設色彩設定檔** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="8295a-330">Under **Display color calibration**, select the **Reset to default color profile** button.</span></span>
1. <span data-ttu-id="8295a-331">您的顯示器在重設時會關閉幾秒鐘。</span><span class="sxs-lookup"><span data-stu-id="8295a-331">Your display will turn off for several seconds as it resets.</span></span> <span data-ttu-id="8295a-332">我們建議您在顯示器重新開啟後重新開機\*\* 裝置， ([已知問題) 。](#top-display-color-calibration-known-issues)</span><span class="sxs-lookup"><span data-stu-id="8295a-332">We recommend you also restart your device *after* the display turns back on (see [known issues](#top-display-color-calibration-known-issues)).</span></span>

#### <span data-ttu-id="8295a-333">顯示色彩校正已知問題</span><span class="sxs-lookup"><span data-stu-id="8295a-333">Top display color calibration known issues</span></span>

- <span data-ttu-id="8295a-334">在設定頁面上，告訴您上次變更色彩設定檔時間的狀態字串將會過期，直到您重載該設定頁面為止</span><span class="sxs-lookup"><span data-stu-id="8295a-334">On the Settings page, the status string that tells you when the color profile was last changed will be out of date until you reload that page of Settings</span></span> 
    - <span data-ttu-id="8295a-335">解決方法：選取另一個設定頁面，然後重新選取校正頁面。</span><span class="sxs-lookup"><span data-stu-id="8295a-335">Workaround: Select another Settings page and then re-select the Calibration page.</span></span>
- <span data-ttu-id="8295a-336">[重設成預設色彩設定檔> 按鈕會開啟一個沒有文字的對話方塊。</span><span class="sxs-lookup"><span data-stu-id="8295a-336">The "Reset to default color profile" button opens a dialog box which has no text.</span></span> <span data-ttu-id="8295a-337">不過，對話方塊中的 [重設> 按鈕會如預期運作。</span><span class="sxs-lookup"><span data-stu-id="8295a-337">The "Reset" button in the dialog box works as intended, however.</span></span>
- <span data-ttu-id="8295a-338">選取 「重設」按鈕後，您的顯示器可能會空白 5-10 秒，您可能會注意到混合實境首頁中的非預期行為。</span><span class="sxs-lookup"><span data-stu-id="8295a-338">After you select the "Reset" button, your display may go blank for 5-10 seconds and you may notice unexpected behavior in the mixed reality home.</span></span> <span data-ttu-id="8295a-339">使用 「重設」按鈕後，請重新開機您的裝置 (我們即將修正這個問題，以自動重新開機您的裝置，我們會更新設定文字，) 。</span><span class="sxs-lookup"><span data-stu-id="8295a-339">Please restart your device after using the “Reset” button (we’ll be fixing this soon to automatically restart your device and we'll update the Settings text accordingly).</span></span>
- <span data-ttu-id="8295a-340">如果您的 HoloLens 2 在執行顯示色彩校正時進入睡眠狀態，它稍後會繼續到混合實境首頁，您的顯示亮度等級仍然會變暗。</span><span class="sxs-lookup"><span data-stu-id="8295a-340">If your HoloLens 2 goes to sleep while running display color calibration, it will later resume into the mixed reality home and your display brightness level will still be dimmed.</span></span>
- <span data-ttu-id="8295a-341">您可能需要嘗試向上/向下按下裝置左側的亮度按鈕數次，才能如預期地工作。</span><span class="sxs-lookup"><span data-stu-id="8295a-341">You may need to try pressing the brightness buttons on the left side of your device up/down a few times before they work as expected.</span></span>

### <span data-ttu-id="8295a-342">預設應用程式選擇器</span><span class="sxs-lookup"><span data-stu-id="8295a-342">Default app picker</span></span>

<span data-ttu-id="8295a-343">當您啟用超連結或開啟具有多個已安裝應用程式的檔案類型時 ，會看到一個新視窗開啟，提示您選取該安裝的應用程式應處理檔案或連結類型。</span><span class="sxs-lookup"><span data-stu-id="8295a-343">When you activate a hyperlink or open a file type with more than one installed app, which supports it, you will see a new window open prompting you to select which installed app should handle the file or link type.</span></span> <span data-ttu-id="8295a-344">在此視窗中，您也可以選擇讓選取的應用程式處理檔案或連結類型「一次」或「永遠」。</span><span class="sxs-lookup"><span data-stu-id="8295a-344">In this window, you can also choose to have the selected app handle the file or link type "Once" or "Always."</span></span>

![應用程式選擇器視窗](images/default-app-picker.png)

<span data-ttu-id="8295a-346">如果您選擇 「Always」，但稍後想要變更處理特定檔案或連結類型的應用程式，您可以在應用程式設定中重 **設>預設值**。</span><span class="sxs-lookup"><span data-stu-id="8295a-346">If you choose "Always" but later want to change which app handles a particular file or link type, you can reset your saved defaults in **Settings > Apps**.</span></span> <span data-ttu-id="8295a-347">卷卷至頁面底部，然後選取 「\*\*\*\* 檔案類型的預設應用程式」和/或「連結類型的預設應用程式」下的清除按鈕。</span><span class="sxs-lookup"><span data-stu-id="8295a-347">Scroll to the bottom of the page and select the **Clear** button under "Default apps for file types" and/or "Default apps for link types."</span></span> <span data-ttu-id="8295a-348">不同于桌上型電腦中的類似設定，您無法重設個別檔案類型的預設值。</span><span class="sxs-lookup"><span data-stu-id="8295a-348">Unlike the similar setting on desktop PCs, you can't reset individual file type defaults.</span></span>

### <span data-ttu-id="8295a-349">Office Web App</span><span class="sxs-lookup"><span data-stu-id="8295a-349">Office web app</span></span>

<span data-ttu-id="8295a-350">Office Web App 已新增到開始功能表中的 「所有應用程式」清單。</span><span class="sxs-lookup"><span data-stu-id="8295a-350">The Office web app has been added to the "All apps" list in the Start menu.</span></span> <span data-ttu-id="8295a-351">這個 Web 應用程式也可以釘釘到開始或卸載。</span><span class="sxs-lookup"><span data-stu-id="8295a-351">This web app can also be pinned to Start or uninstalled.</span></span> <span data-ttu-id="8295a-352">由於這是 Web 應用程式，因此其功能會完全符合您流覽時的體驗 https://www.office.com 。</span><span class="sxs-lookup"><span data-stu-id="8295a-352">Because this is a web app, its functionality matches exactly what you'd experience by visiting https://www.office.com.</span></span> <span data-ttu-id="8295a-353">Office Web App 功能只有在 HoloLens 2 有有效的網際網路連接時才能使用。</span><span class="sxs-lookup"><span data-stu-id="8295a-353">Office web app functionality is only available when your HoloLens 2 has an active internet connection.</span></span>

### <span data-ttu-id="8295a-354">滑動以輸入</span><span class="sxs-lookup"><span data-stu-id="8295a-354">Swipe to type</span></span>

<span data-ttu-id="8295a-355">有些客戶會滑動想要輸入之字詞的形狀，以在虛擬鍵盤上更快速地「輸入」，我們正在預覽全攝影鍵盤的這項功能。</span><span class="sxs-lookup"><span data-stu-id="8295a-355">Some customers find it faster to "type" on virtual keyboards by swiping the shape of the word they intend to type, and we're previewing this feature for the holographic keyboard.</span></span> <span data-ttu-id="8295a-356">您可以一次滑動一個字，將手指的筆尖透過全攝影鍵盤的螢幕、滑動文字的形狀，然後從鍵盤上收回手指的提示。</span><span class="sxs-lookup"><span data-stu-id="8295a-356">You can swipe one word at a time by passing the tip of your finger through the plane of the holographic keyboard, swiping the shape of the word, and then withdrawing the tip of your finger from the plane of the keyboard.</span></span> <span data-ttu-id="8295a-357">您可以將手指從鍵盤上移除，以在文字之間移動，不需要按空格鍵，即可滑動後續文字。</span><span class="sxs-lookup"><span data-stu-id="8295a-357">You can swipe follow up words without needing to press the spacebar by removing your finger from the keyboard between words.</span></span> <span data-ttu-id="8295a-358">如果您看到手指在鍵盤上移動後看到滑動軌跡，就會知道此功能是否正常。</span><span class="sxs-lookup"><span data-stu-id="8295a-358">You will know the feature is working if you see a swipe trail following your finger's movement on the keyboard.</span></span>

<span data-ttu-id="8295a-359">請注意，由於全像攝影鍵盤的性質，您不會因為手指而感到受威脅，因此使用和主控這項功能可能會有些難度 (手機顯示器和手機) 。</span><span class="sxs-lookup"><span data-stu-id="8295a-359">Please note, this feature can be tricky to use and master because of the nature of a holographic keyboard where you don't feel resistance against your finger (unlike a mobile phone display).</span></span> <span data-ttu-id="8295a-360">我們正在評估這項公開發行功能，因此您的意見至關重要;您是否覺得這項功能實用或您的意見有建設性的意見，請透過意見回饋中心 [讓我們知道](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="8295a-360">We are evaluating this feature for public release, so your feedback is important; whether you find the feature useful or you have constructive feedback, please let us know via [Feedback Hub](hololens-feedback.md).</span></span>

### <span data-ttu-id="8295a-361">USB-C 外接麥克風支援</span><span class="sxs-lookup"><span data-stu-id="8295a-361">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8295a-362">插入 USB **麥克風並不會自動將其設定為輸入裝置**。</span><span class="sxs-lookup"><span data-stu-id="8295a-362">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="8295a-363">插入一組 USB-C 耳機時，使用者會注意到耳機的音訊會自動重新導向至耳機，但 HoloLens OS 會將內部麥克風陣列優先排列于任何其他輸入裝置上方。</span><span class="sxs-lookup"><span data-stu-id="8295a-363">When plugging in a set of USB-C headphones users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> **<span data-ttu-id="8295a-364">若要使用 USB-C 麥克風，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="8295a-364">In order to use a USB-C microphone follow the steps below.</span></span>**

<span data-ttu-id="8295a-365">使用者可以使用聲音設定面板選取 USB-C 連接 **的外部** 麥克風。</span><span class="sxs-lookup"><span data-stu-id="8295a-365">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="8295a-366">USB-C 麥克風可用於通話、錄製等。</span><span class="sxs-lookup"><span data-stu-id="8295a-366">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="8295a-367">開啟設定**應用程式\*\*\*\*，然後選取**系統  ->  **音效**。</span><span class="sxs-lookup"><span data-stu-id="8295a-367">Open the **Settings** app and select **System** -> **Sound**.</span></span>

![音效設定](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="8295a-369">若要使用外接式麥克風與 **遠端**輔助，使用者必須按一下 [管理音效裝置」 超連結。</span><span class="sxs-lookup"><span data-stu-id="8295a-369">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="8295a-370">然後使用下拉式選項將外部麥克風設為**預設或\*\*\*\*通訊預設值。**</span><span class="sxs-lookup"><span data-stu-id="8295a-370">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="8295a-371">選擇 **預設值** 表示外接式麥克風會用於所有位置。</span><span class="sxs-lookup"><span data-stu-id="8295a-371">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="8295a-372">選擇 **通訊** 預設值表示外接麥克風將用於遠端輔助和其他通訊應用程式，但 HoloLens 麥克風陣列可能仍然可用於其他工作。</span><span class="sxs-lookup"><span data-stu-id="8295a-372">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![管理音效裝置](images/usbc-mic-2.png)

<br>

![將麥克風設為預設值](images/usbc-mic-3.jpg)

#### <span data-ttu-id="8295a-375">藍牙麥克風支援呢？</span><span class="sxs-lookup"><span data-stu-id="8295a-375">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="8295a-376">很抱歉，HoloLens 2 目前仍不支援藍牙麥克風。</span><span class="sxs-lookup"><span data-stu-id="8295a-376">Unfortunately Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

#### <span data-ttu-id="8295a-377">USB-C 麥克風疑難排解</span><span class="sxs-lookup"><span data-stu-id="8295a-377">Troubleshooting USB-C microphones</span></span>

<span data-ttu-id="8295a-378">請注意，有些 USB-C 麥克風無法正確報告本身為麥克風和喇\*\* 叭。</span><span class="sxs-lookup"><span data-stu-id="8295a-378">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="8295a-379">這是麥克風的問題，而非 HoloLens 的問題。</span><span class="sxs-lookup"><span data-stu-id="8295a-379">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="8295a-380">將其中一個麥克風插入 HoloLens 時，可能會遺失聲音。</span><span class="sxs-lookup"><span data-stu-id="8295a-380">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="8295a-381">幸好有一個簡單的修正程式。</span><span class="sxs-lookup"><span data-stu-id="8295a-381">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="8295a-382">在**設定**系統音效中，將內建喇叭 ( ->  \*\*\*\*  ->  \*\* \*\*\*\*類比功能音訊**驅動程式) 預設**裝置\*\*。</span><span class="sxs-lookup"><span data-stu-id="8295a-382">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="8295a-383">HoloLens 應該會記住這項設定，即使麥克風稍後已移除並重新連接也一樣。</span><span class="sxs-lookup"><span data-stu-id="8295a-383">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![USB-C 麥克風疑難排解](images/usbc-mic-4.png)

### <span data-ttu-id="8295a-385">在 Kiosk 模式中使用新的設定和 Edge 應用程式</span><span class="sxs-lookup"><span data-stu-id="8295a-385">Use the new Settings and Edge apps in Kiosk modes</span></span>

<span data-ttu-id="8295a-386">在 Kiosks 中加入 [應用程式時](hololens-kiosk.md)，IT 系統管理員通常會將應用程式新增到 Kiosk，但使用其應用程式使用者模型識別碼 (AUMID) 。</span><span class="sxs-lookup"><span data-stu-id="8295a-386">When including apps in [Kiosks](hololens-kiosk.md), an IT Admin often adds the app to the Kiosk but using it's App User Model ID (AUMID).</span></span> <span data-ttu-id="8295a-387">因為設定應用程式和 Microsoft Edge 應用程式都視為新的應用程式，而且與那些應用程式使用 AUMIDs 的舊版 App Kiosk 不同，因此必須更新以使用新的 AUMID。</span><span class="sxs-lookup"><span data-stu-id="8295a-387">Because both the Settings app and Microsoft Edge app are considered new apps and different than the older apps Kiosks that use AUMIDs for those apps will need to be updated to use the new AUMID.</span></span>

<span data-ttu-id="8295a-388">修改 Kiosk 以包含新 App 時，建議您新增新 AUMID，並離開舊的 AUMID。</span><span class="sxs-lookup"><span data-stu-id="8295a-388">When modifying a Kiosk to include the new apps, we recommend adding in the new AUMID as well as leaving the old one.</span></span> <span data-ttu-id="8295a-389">這可讓使用者在更新作業系統時輕鬆進行轉換，而且不需要收到新政策，就如預期一樣持續使用 Kiosk。</span><span class="sxs-lookup"><span data-stu-id="8295a-389">This will create an easy transition when users update the OS and won't need to receive new policies to keep using the Kiosk as intended.</span></span>

| <span data-ttu-id="8295a-390">應用程式</span><span class="sxs-lookup"><span data-stu-id="8295a-390">App</span></span>                    | <span data-ttu-id="8295a-391">AUMID</span><span class="sxs-lookup"><span data-stu-id="8295a-391">AUMID</span></span>                                                  |
|------------------------|--------------------------------------------------------|
| <span data-ttu-id="8295a-392">舊設定應用程式</span><span class="sxs-lookup"><span data-stu-id="8295a-392">Old Settings App</span></span>       | <span data-ttu-id="8295a-393">HolographicSystemSettings_cw5n1h2txyewy！應用程式</span><span class="sxs-lookup"><span data-stu-id="8295a-393">HolographicSystemSettings_cw5n1h2txyewy!App</span></span>            |
| <span data-ttu-id="8295a-394">新增設定應用程式</span><span class="sxs-lookup"><span data-stu-id="8295a-394">New Settings App</span></span>       | <span data-ttu-id="8295a-395">BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy！應用程式</span><span class="sxs-lookup"><span data-stu-id="8295a-395">BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App</span></span> |
| <span data-ttu-id="8295a-396">舊的 Microsoft Edge 應用程式</span><span class="sxs-lookup"><span data-stu-id="8295a-396">Old Microsoft Edge app</span></span> | <span data-ttu-id="8295a-397">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span><span class="sxs-lookup"><span data-stu-id="8295a-397">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span></span>    |
| <span data-ttu-id="8295a-398">新的 Microsoft Edge 應用程式</span><span class="sxs-lookup"><span data-stu-id="8295a-398">New Microsoft Edge app</span></span> | <span data-ttu-id="8295a-399">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE</span><span class="sxs-lookup"><span data-stu-id="8295a-399">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE</span></span>    |

### <span data-ttu-id="8295a-400">頁面設定可見度的新設定URIS</span><span class="sxs-lookup"><span data-stu-id="8295a-400">New SettingsURIs for Page Settings Visibility</span></span>

<span data-ttu-id="8295a-401">在 [Windows 全攝影版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 中，我們新增 [了設定/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) 政策，以限制在設定應用程式內看到的頁面。</span><span class="sxs-lookup"><span data-stu-id="8295a-401">In [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) we added the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="8295a-402">PageVisibilityList 為一種原則，可讓 IT 系統管理員禁止顯示或存取 [系統設定] 應用程式中的特定頁面，或對特定頁面外的所有頁面執行此動作。</span><span class="sxs-lookup"><span data-stu-id="8295a-402">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

<span data-ttu-id="8295a-403">如果您流覽 [頁面設定可見度](settings-uri-list.md)，您可以找到使用此 CSP 的指示，以及先前版本中提供的 URI 清單。</span><span class="sxs-lookup"><span data-stu-id="8295a-403">If you visit [Page Settings Visibility](settings-uri-list.md), you can find instructions to use this CSP and the list of URIs available in previous releases.</span></span>

<span data-ttu-id="8295a-404">在 Windows 測試人員建立中，我們正在展開可用的設定 URI 清單清單，IT 系統管理員可以管理該清單。</span><span class="sxs-lookup"><span data-stu-id="8295a-404">In Windows Insider builds we are expanding upon the list of list of available Settings URIs, which IT Admins can manage.</span></span> <span data-ttu-id="8295a-405">其中一些 URI 適用于新設定應用程式內的新可用區域。</span><span class="sxs-lookup"><span data-stu-id="8295a-405">Some of these URIs are for newly available areas within the new Settings app.</span></span> <span data-ttu-id="8295a-406">如果您使用的是設定/PageVisibilityList 政策，請查閱下列清單，並根據需要調整允許或封鎖的頁面。</span><span class="sxs-lookup"><span data-stu-id="8295a-406">If you are using Settings/PageVisibilityList policy, review the following list and adjust your allowed or blocked pages as needed.</span></span>

> [!NOTE]
> **<span data-ttu-id="8295a-407">已替代：ms-settings：network-Proxy</span><span class="sxs-lookup"><span data-stu-id="8295a-407">Deprecated: ms-settings:network-proxy</span></span>**
>
> <span data-ttu-id="8295a-408">在這些較新的版本內，有一個設定頁面已由它所替代。</span><span class="sxs-lookup"><span data-stu-id="8295a-408">One settings page is deprecated in these newer builds.</span></span> <span data-ttu-id="8295a-409">已不再**提供&** Internet  >  **Proxy**頁面做為全域設定。</span><span class="sxs-lookup"><span data-stu-id="8295a-409">The old **Network & Internet** > **Proxy** page is no longer available as a global setting.</span></span> <span data-ttu-id="8295a-410">您可以在 Network & **Internet**  >  **Wi-Fi**屬性或網際網路乙太網路屬性&找到新的每  >  \*\* \*\* **&**  >  \*\*\*\*  >  **設定**。</span><span class="sxs-lookup"><span data-stu-id="8295a-410">The new per-connection proxy settings can be found under **Network & Internet** > **Wi-Fi** > **Properties** or **Network & Internet** > **Ethernet** > **Properties**.</span></span>

<br>

| <span data-ttu-id="8295a-411">設定頁面</span><span class="sxs-lookup"><span data-stu-id="8295a-411">Settings page</span></span>                                        | <span data-ttu-id="8295a-412">URI</span><span class="sxs-lookup"><span data-stu-id="8295a-412">URI</span></span>                                              |
|------------------------------------------------------|--------------------------------------------------|
| <span data-ttu-id="8295a-413">應用程式>應用程式&功能</span><span class="sxs-lookup"><span data-stu-id="8295a-413">Apps > Apps & features</span></span>                               | `ms-settings:appsfeatures`                         |
| <span data-ttu-id="8295a-414">應用程式>應用程式&進>選項的功能</span><span class="sxs-lookup"><span data-stu-id="8295a-414">Apps > Apps & features > Advanced options</span></span>          | `ms-settings:appsfeatures-app`                     |
| <span data-ttu-id="8295a-415">離線>應用程式</span><span class="sxs-lookup"><span data-stu-id="8295a-415">Apps > Offline maps</span></span>                                  | `ms-settings:maps`                                 |
| <span data-ttu-id="8295a-416">離線>應用程式>下載地圖</span><span class="sxs-lookup"><span data-stu-id="8295a-416">Apps > Offline maps > Download maps</span></span>                  | `ms-settings:maps-downloadmaps`                    |
| <span data-ttu-id="8295a-417">使用滑鼠>裝置</span><span class="sxs-lookup"><span data-stu-id="8295a-417">Devices > Mouse</span></span>                                      | `ms-settings:mouse`                                |
| <span data-ttu-id="8295a-418">USB >裝置</span><span class="sxs-lookup"><span data-stu-id="8295a-418">Devices > USB</span></span>                                        | `ms-settings:usb`                                  |
| <span data-ttu-id="8295a-419">網路&網際網路>飛航模式</span><span class="sxs-lookup"><span data-stu-id="8295a-419">Network & Internet > Airplane mode</span></span>                   | `ms-settings:network-airplanemode`                 |
| <span data-ttu-id="8295a-420">隱私權>一般</span><span class="sxs-lookup"><span data-stu-id="8295a-420">Privacy > General</span></span>                                    | `ms-settings:privacy-general`                      |
| <span data-ttu-id="8295a-421">輸入>筆&隱私權</span><span class="sxs-lookup"><span data-stu-id="8295a-421">Privacy > Ink & typing personalization</span></span>             | `ms-settings:privacy-speechtyping`                 |
| <span data-ttu-id="8295a-422">隱私權>動作</span><span class="sxs-lookup"><span data-stu-id="8295a-422">Privacy > Motion</span></span>                                     | `ms-settings:privacy-motion`                       |
| <span data-ttu-id="8295a-423">隱私權>螢幕擷取畫面邊框</span><span class="sxs-lookup"><span data-stu-id="8295a-423">Privacy > Screenshot borders</span></span>                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| <span data-ttu-id="8295a-424">螢幕>和應用程式的隱私權</span><span class="sxs-lookup"><span data-stu-id="8295a-424">Privacy > Screenshots and apps</span></span>                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| <span data-ttu-id="8295a-425">系統>電池</span><span class="sxs-lookup"><span data-stu-id="8295a-425">System > Battery</span></span>                                     | `ms-settings:batterysaver`                         |
| <span data-ttu-id="8295a-426">系統>電池</span><span class="sxs-lookup"><span data-stu-id="8295a-426">System > Battery</span></span>                                     | `ms-settings:batterysaver-settings`                |
| <span data-ttu-id="8295a-427">系統>音效</span><span class="sxs-lookup"><span data-stu-id="8295a-427">System > Sound</span></span>                                       | `ms-settings:sound`                                |
| <span data-ttu-id="8295a-428">系統>音效> App 音量和裝置喜好設定</span><span class="sxs-lookup"><span data-stu-id="8295a-428">System > Sound > App volume and device preferences</span></span> | `ms-settings:apps-volume`                          |
| <span data-ttu-id="8295a-429">系統>音效>管理音效裝置</span><span class="sxs-lookup"><span data-stu-id="8295a-429">System > Sound > Manage sound   devices</span></span>              | `ms-settings:sound-devices`                        |
| <span data-ttu-id="8295a-430">系統>儲存空間>設定儲存感知</span><span class="sxs-lookup"><span data-stu-id="8295a-430">System > Storage > Configure Storage Sense</span></span>         | `ms-settings:storagepolicies`                      |
| <span data-ttu-id="8295a-431">語言&日期>時間&時間</span><span class="sxs-lookup"><span data-stu-id="8295a-431">Time & Language > Date & time</span></span>                        | `ms-settings:dateandtime`                          |
| <span data-ttu-id="8295a-432">語言&鍵盤>時間</span><span class="sxs-lookup"><span data-stu-id="8295a-432">Time & Language > Keyboard</span></span>                           | `ms-settings:keyboard`                             |
| <span data-ttu-id="8295a-433">語言&時間>語言</span><span class="sxs-lookup"><span data-stu-id="8295a-433">Time & Language > Language</span></span>                           | `ms-settings:language`                             |
| <span data-ttu-id="8295a-434">語言&時間>語言</span><span class="sxs-lookup"><span data-stu-id="8295a-434">Time & Language > Language</span></span>                           | `ms-settings:regionlanguage-languageoptions`       |
| <span data-ttu-id="8295a-435">更新&安全性>重&復原</span><span class="sxs-lookup"><span data-stu-id="8295a-435">Update & Security > Reset & recovery</span></span>               | `ms-settings:reset`                                |

#### <span data-ttu-id="8295a-436">更新的 URI</span><span class="sxs-lookup"><span data-stu-id="8295a-436">Updated URIs</span></span>

<span data-ttu-id="8295a-437">之前，下列兩個 URI 不會將使用者直接帶至指示的頁面，但只會封鎖主要更新頁面。</span><span class="sxs-lookup"><span data-stu-id="8295a-437">Previously the following two URIs would not take a user directly to the pages indicated but only blocked the main updates page.</span></span> <span data-ttu-id="8295a-438">下列專案已更新為直接顯示至其頁面：</span><span class="sxs-lookup"><span data-stu-id="8295a-438">The following items have been updated to direct to their pages:</span></span>

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <span data-ttu-id="8295a-439">資訊站模式行為變更處理失敗</span><span class="sxs-lookup"><span data-stu-id="8295a-439">Kiosk mode behavior changes for handling of failures</span></span>

<span data-ttu-id="8295a-440">在較舊的建立中，如果裝置有資訊站組式 ，這是全域指派的存取權和 AAD 群組成員指派存取權的組合，如果決定 AAD 群組成員資格失敗，使用者[](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)會看到「開始」功能表中沒有顯示任何內容。</span><span class="sxs-lookup"><span data-stu-id="8295a-440">In older builds, if a device had a kiosk configuration, which is a combination of both global assigned access and AAD group member assigned access, if determining AAD group membership failed, the user would see “[nothing shown in start](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)” menu.</span></span>

<span data-ttu-id="8295a-441">從 Windows 測試人員發行開始，如果 AAD 群組資訊站模式失敗 (資訊站) 資訊站體驗會備份到全域資訊站組配置。</span><span class="sxs-lookup"><span data-stu-id="8295a-441">Starting in Windows Insider release, the kiosk experience will fallback to global kiosk configuration (if present) in case of failures during AAD group kiosk mode.</span></span>

### <span data-ttu-id="8295a-442">透過設定應用程式設定後背診斷</span><span class="sxs-lookup"><span data-stu-id="8295a-442">Configuring Fallback Diagnostics via Settings app</span></span>

<span data-ttu-id="8295a-443">現在，使用者可以在設定 App 中設定後背 [診斷的行為](hololens-diagnostic-logs.md)。</span><span class="sxs-lookup"><span data-stu-id="8295a-443">Now in Settings App, a user can configure the behavior of [Fallback Diagnostics](hololens-diagnostic-logs.md).</span></span> <span data-ttu-id="8295a-444">在設定 App 中流覽至**隱私權**  ->  **疑難排解頁面**以設定此設定。</span><span class="sxs-lookup"><span data-stu-id="8295a-444">In the Settings app navigate to **Privacy** -> **Troubleshooting** page to configure this setting.</span></span>

> [!NOTE]
> <span data-ttu-id="8295a-445">如果有針對裝置所配置的 MDM 規則，使用者將無法覆蓋該行為。</span><span class="sxs-lookup"><span data-stu-id="8295a-445">If there is MDM policy configured for the device, user will not be able to override that behavior.</span></span>  

### <span data-ttu-id="8295a-446">與附近的裝置共用專案</span><span class="sxs-lookup"><span data-stu-id="8295a-446">Share things with nearby devices</span></span>

<span data-ttu-id="8295a-447">與 Windows 10 裝置附近共用專案，包括執行 HoloLens Insider builds 20279.1006+ 的 PC 和其他 HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="8295a-447">Share things with near by Windows 10 devices, including both PCs and other HoloLens 2 devices running HoloLens Insider builds 20279.1006+.</span></span> <span data-ttu-id="8295a-448">您可以在設定**系統共用體驗**中試用，以將 HoloLens 的檔案或  ->  \*\*\*\*  ->  \*\* \*\*URL 共用至電腦。</span><span class="sxs-lookup"><span data-stu-id="8295a-448">You can try it out in **Settings** -> **System** -> **Shared Experiences** to share files or URLs from a HoloLens to a PC.</span></span> <span data-ttu-id="8295a-449">若要進一步閱讀詳細資料，請參閱如何在 [Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)中與附近的裝置共用專案。</span><span class="sxs-lookup"><span data-stu-id="8295a-449">For more details read more about how to [Share things with nearby devices in Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).</span></span>

<span data-ttu-id="8295a-450">此功能可透過 [Connectivity/AllowConnectedDevices 管理](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)。</span><span class="sxs-lookup"><span data-stu-id="8295a-450">This feature can be managed via [Connectivity/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).</span></span>

### <span data-ttu-id="8295a-451">新的 OS Update 疑難排解員</span><span class="sxs-lookup"><span data-stu-id="8295a-451">New OS Update troubleshooter</span></span>

<span data-ttu-id="8295a-452">除了設定應用程式中先前的疑難排解員之外，系統還加入了新的疑難排解員，並新增了 OS 更新的新設定應用程式。</span><span class="sxs-lookup"><span data-stu-id="8295a-452">In addition to the previous troubleshooters within the Settings app, a new troubleshooter has been added with the addition of the new Settings app for OS Updates.</span></span> <span data-ttu-id="8295a-453">流覽至**設定**  ->  **更新 &amp; 安全性**  ->  **疑難排解**  ->  **Windows Update，** 然後選取開始。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8295a-453">Navigate to **Settings** -> **Update &amp; Security** -> **Troubleshoot** -> **Windows Update** and select **Start**.</span></span> <span data-ttu-id="8295a-454">這可讓您在重現作業系統更新問題時收集追蹤，以協助您針對 IT 或支援進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="8295a-454">This allows you to collect traces while reproducing your issue with OS Updates to assist better in troubleshooting with your IT or support.</span></span>

### <span data-ttu-id="8295a-455">更新中的改良與修正：</span><span class="sxs-lookup"><span data-stu-id="8295a-455">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="8295a-456">[離線診斷](hololens-diagnostic-logs.md#offline-diagnostics) 也會包含序號和作業系統版本的其他裝置資訊。</span><span class="sxs-lookup"><span data-stu-id="8295a-456">[Offline diagnostics](hololens-diagnostic-logs.md#offline-diagnostics) will also include additional device information for serial number and OS version.</span></span>






## <span data-ttu-id="8295a-457">開始接收測試人員建立</span><span class="sxs-lookup"><span data-stu-id="8295a-457">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="8295a-458">如果您最近未更新，請重新開機裝置以更新狀態並取得最新版。</span><span class="sxs-lookup"><span data-stu-id="8295a-458">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="8295a-459">「重新開機裝置」語音命令運作正常。</span><span class="sxs-lookup"><span data-stu-id="8295a-459">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="8295a-460">您也可以選擇設定/Windows Insider Program 中的重新開機按鈕。</span><span class="sxs-lookup"><span data-stu-id="8295a-460">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="8295a-461">我們在後端遇到您可能會遇到的錯誤，這將會讓系統復原正軌。</span><span class="sxs-lookup"><span data-stu-id="8295a-461">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="8295a-462">在 HoloLens 2 裝置\*\*\*\* 上，& Windows 測試人員計畫的設定更新，然後  >  \*\*\*\*  >  \*\*\*\* 選取開始。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8295a-462">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="8295a-463">連結您用來註冊為 Windows Insider 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="8295a-463">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="8295a-464">Windows Insider 目前正在移往頻道。</span><span class="sxs-lookup"><span data-stu-id="8295a-464">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="8295a-465">快速**通道**會變成**開發人員**通道，慢速通道會變成\*\*\*\*\*\*Beta**通道，而發行**預覽**通道會變成發行**預覽通道\*\*。</span><span class="sxs-lookup"><span data-stu-id="8295a-465">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="8295a-466">以下是該地圖的外觀：</span><span class="sxs-lookup"><span data-stu-id="8295a-466">Here is what that mapping looks like:</span></span>

![Windows Insider Channels 說明](images/WindowsInsiderChannels.png)

<span data-ttu-id="8295a-468">詳細資訊請參閱 Windows 部落格 [上的 Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 介紹。</span><span class="sxs-lookup"><span data-stu-id="8295a-468">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>

<span data-ttu-id="8295a-469">然後，選取 **Windows 的進行**中開發，選擇您是否要接收 **開發通道** 或 **Beta 通道** 版本，並審查計畫條款。</span><span class="sxs-lookup"><span data-stu-id="8295a-469">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="8295a-470">選取 **確認>立即重新開機** 以完成。</span><span class="sxs-lookup"><span data-stu-id="8295a-470">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="8295a-471">重新開機裝置之後，請>更新& **安全性>檢查更新** 以取得最新版。</span><span class="sxs-lookup"><span data-stu-id="8295a-471">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

### <span data-ttu-id="8295a-472">更新錯誤0x80070490處理</span><span class="sxs-lookup"><span data-stu-id="8295a-472">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="8295a-473">如果您在更新 Dev 或 Beta 0x80070490時遇到更新錯誤，請嘗試下列短期工作。</span><span class="sxs-lookup"><span data-stu-id="8295a-473">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="8295a-474">這涉及移動您的測試人員通道、選取更新，然後將您的測試人員通道移回。</span><span class="sxs-lookup"><span data-stu-id="8295a-474">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>

#### <span data-ttu-id="8295a-475">階段 1 - 發行預覽版</span><span class="sxs-lookup"><span data-stu-id="8295a-475">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="8295a-476">設定、更新&、Windows Insider Program、選取 **發行預覽通道**。</span><span class="sxs-lookup"><span data-stu-id="8295a-476">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="8295a-477">設定、更新&安全性、Windows **Update、檢查更新**。</span><span class="sxs-lookup"><span data-stu-id="8295a-477">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="8295a-478">更新之後，繼續進行階段 2。</span><span class="sxs-lookup"><span data-stu-id="8295a-478">After the update, continue on to Stage two.</span></span>

#### <span data-ttu-id="8295a-479">階段 2 - 開發人員通道</span><span class="sxs-lookup"><span data-stu-id="8295a-479">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="8295a-480">設定、更新&、Windows 測試人員計畫、選取 **開發人員通道**。</span><span class="sxs-lookup"><span data-stu-id="8295a-480">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="8295a-481">設定、更新&安全性、Windows **Update、檢查更新**。</span><span class="sxs-lookup"><span data-stu-id="8295a-481">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>

## <span data-ttu-id="8295a-482">FFU 下載和快速指示</span><span class="sxs-lookup"><span data-stu-id="8295a-482">FFU download and flash directions</span></span>
<span data-ttu-id="8295a-483">若要使用已簽署 Ffu 的班機測試，您首先必須先將裝置解除鎖定，才能閃爍已簽署之航班的 ffu。</span><span class="sxs-lookup"><span data-stu-id="8295a-483">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="8295a-484">在 PC 上：</span><span class="sxs-lookup"><span data-stu-id="8295a-484">On PC:</span></span>

    1. <span data-ttu-id="8295a-485">從 下載 ffu 到您的電腦 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。</span><span class="sxs-lookup"><span data-stu-id="8295a-485">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="8295a-486">從 Microsoft store (ARC) 進一步修復小夥伴 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) ：.</span><span class="sxs-lookup"><span data-stu-id="8295a-486">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="8295a-487">在 HoloLens - 航班解除鎖定 **：開啟設定**更新  >  **&**  >  **安全性 Windows 測試人員計畫**，然後註冊、重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="8295a-487">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="8295a-488">Flash FFU - 現在您可以使用 ARC 快速閃爍正式航班簽署的 FFU。</span><span class="sxs-lookup"><span data-stu-id="8295a-488">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

## <span data-ttu-id="8295a-489">提供意見回饋與報告問題</span><span class="sxs-lookup"><span data-stu-id="8295a-489">Provide feedback and report issues</span></span>

<span data-ttu-id="8295a-490">請使用 [HoloLens](hololens-feedback.md) 上的意見回饋中樞應用程式，提供意見回饋及報告問題。</span><span class="sxs-lookup"><span data-stu-id="8295a-490">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="8295a-491">使用意見中樞可確保包含所有必要的診斷資訊，協助我們的工程師快速進行診斷並解決問題。</span><span class="sxs-lookup"><span data-stu-id="8295a-491">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="8295a-492">中文版和日文版的 HoloLens 問題應該以相同方式報告。</span><span class="sxs-lookup"><span data-stu-id="8295a-492">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="8295a-493">請務必接受詢問您是否要意見回應中樞存取您的檔資料夾的提示， (系統提示時選取) 。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8295a-493">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="8295a-494">開發人員注意事項</span><span class="sxs-lookup"><span data-stu-id="8295a-494">Note for developers</span></span>

<span data-ttu-id="8295a-495">歡迎並鼓勵您嘗試使用 HoloLens 測試人員建立來開發您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="8295a-495">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="8295a-496">請參閱 [HoloLens 開發人員檔](https://developer.microsoft.com/windows/mixed-reality/development) 以開始使用。</span><span class="sxs-lookup"><span data-stu-id="8295a-496">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="8295a-497">這些相同的指示可與 HoloLens 測試人員建立一起使用。</span><span class="sxs-lookup"><span data-stu-id="8295a-497">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="8295a-498">您可以使用與 HoloLens 開發中一樣使用的同一個同一個製作平臺。。</span><span class="sxs-lookup"><span data-stu-id="8295a-498">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <span data-ttu-id="8295a-499">停止接收測試人員建立</span><span class="sxs-lookup"><span data-stu-id="8295a-499">Stop receiving Insider builds</span></span>

<span data-ttu-id="8295a-500">如果您不想再收到 Windows 全攝影版的測試人員版本，您可以選擇在 HoloLens 執行生產版時退出，或者您可以使用進一步[](hololens-recovery.md)修復小夥伴復原您的裝置，將裝置復原為非測試人員版本的 Windows 全攝影版。</span><span class="sxs-lookup"><span data-stu-id="8295a-500">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="8295a-501">有一個已知問題，在手動重新安裝全新預覽版之後，從 Insider Preview 建立取消註冊的使用者，會遇到藍色畫面。</span><span class="sxs-lookup"><span data-stu-id="8295a-501">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="8295a-502">之後，他們必須手動復原裝置。</span><span class="sxs-lookup"><span data-stu-id="8295a-502">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="8295a-503">如需有關您是否會受到影響的完整詳細資料，請進一步查看此 [已知問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)。</span><span class="sxs-lookup"><span data-stu-id="8295a-503">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="8295a-504">若要確認您的 HoloLens 正在進行生產建立：</span><span class="sxs-lookup"><span data-stu-id="8295a-504">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="8295a-505">請前往 **系統>的>，** 並尋找建組編號。</span><span class="sxs-lookup"><span data-stu-id="8295a-505">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="8295a-506">[請參閱生產版組號版本資訊](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="8295a-506">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="8295a-507">若要退出測試人員建立：</span><span class="sxs-lookup"><span data-stu-id="8295a-507">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="8295a-508">在執行生產建制的 HoloLens 上，> Windows 測試人員計畫 **&更新>，** 然後選取停止測試人員 **建立**。</span><span class="sxs-lookup"><span data-stu-id="8295a-508">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="8295a-509">請遵循指示退出宣告您的裝置。</span><span class="sxs-lookup"><span data-stu-id="8295a-509">Follow the instructions to opt out your device.</span></span>
