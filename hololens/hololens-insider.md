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
ms.date: 2/2/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 3d7c4b5347019682896bb695690190e633c80677
ms.sourcegitcommit: 23ee06b659d7a51f3000d386c8f67cbf212d5aa4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327397"
---
# <span data-ttu-id="c64a3-103">適用於 Microsoft HoloLens 的 Insider Preview</span><span class="sxs-lookup"><span data-stu-id="c64a3-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="c64a3-104">歡迎使用 HoloLens 的最新 Insider Preview 版本！</span><span class="sxs-lookup"><span data-stu-id="c64a3-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="c64a3-105">開始使用非常簡單，並為[](hololens-insider.md#start-receiving-insider-builds)HoloLens 的下一個主要作業系統更新提供寶貴的意見。</span><span class="sxs-lookup"><span data-stu-id="c64a3-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <span data-ttu-id="c64a3-106">Windows Insider Release Notes</span><span class="sxs-lookup"><span data-stu-id="c64a3-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="c64a3-107">我們很高興能再次開始向 Windows Insider 提供新功能。</span><span class="sxs-lookup"><span data-stu-id="c64a3-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="c64a3-108">新版將會測試到 Dev 通道，以尋找最新的更新。</span><span class="sxs-lookup"><span data-stu-id="c64a3-108">New builds will be flighting to the Dev Channel for the latest updates.</span></span> <span data-ttu-id="c64a3-109">隨著我們新增更多功能與更新至我們的 Windows 測試人員版本，我們會持續更新此頁面。</span><span class="sxs-lookup"><span data-stu-id="c64a3-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span>  <span data-ttu-id="c64a3-110">期待並準備好將這些更新混合到您的實境中。</span><span class="sxs-lookup"><span data-stu-id="c64a3-110">Get excited and ready to mix these updates into your reality.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c64a3-111">如果您先前在 Kiosk 中曾使用設定 App 或 Microsoft Edge 應用程式，我們已將這些應用程式取代為使用不同的應用程式識別碼的新應用程式。</span><span class="sxs-lookup"><span data-stu-id="c64a3-111">If you were previously using either the Settings app or Microsoft Edge app in a Kiosk, we have replaced these apps with new apps which use a different App ID.</span></span> <span data-ttu-id="c64a3-112">我們強烈建議您閱讀以下資訊站模式中新[App 的新 AUMIDS。](#use-the-new-settings-and-edge-apps-in-kiosk-modes)</span><span class="sxs-lookup"><span data-stu-id="c64a3-112">We highly encourage you to read [New AUMIDs for new apps in Kiosk mode](#use-the-new-settings-and-edge-apps-in-kiosk-modes) below.</span></span> <span data-ttu-id="c64a3-113">這可確保您繼續擁有 Kiosk 中的設定應用程式，或包含新的 Microsoft Edge 應用程式。</span><span class="sxs-lookup"><span data-stu-id="c64a3-113">This will ensure you either continue to have the Settings app in your Kiosk, or include the new Microsoft Edge app.</span></span>

<br>

| <span data-ttu-id="c64a3-114">功能名稱</span><span class="sxs-lookup"><span data-stu-id="c64a3-114">Feature Name</span></span>                                              | <span data-ttu-id="c64a3-115">簡短描述</span><span class="sxs-lookup"><span data-stu-id="c64a3-115">Short description</span></span>                                                                      | <span data-ttu-id="c64a3-116">可在建立中使用</span><span class="sxs-lookup"><span data-stu-id="c64a3-116">Available in build</span></span> |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [<span data-ttu-id="c64a3-117">新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c64a3-117">New Microsoft Edge</span></span>](#introducing-the-new-microsoft-edge) | <span data-ttu-id="c64a3-118">新的 Chromium 型 Microsoft Edge 現已適用于 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="c64a3-118">The new, Chromium-based Microsoft Edge is now available for HoloLens 2</span></span>                         | <span data-ttu-id="c64a3-119">20279.1006</span><span class="sxs-lookup"><span data-stu-id="c64a3-119">20279.1006</span></span> |
| [<span data-ttu-id="c64a3-120">WebXR 和 360 Viewer</span><span class="sxs-lookup"><span data-stu-id="c64a3-120">WebXR and 360 Viewer</span></span>](#webxr-and-360-viewer)             | <span data-ttu-id="c64a3-121">嘗試沉浸式網頁體驗和 360 影片播放</span><span class="sxs-lookup"><span data-stu-id="c64a3-121">Try immersive web experiences and 360 video playback</span></span>                                           | <span data-ttu-id="c64a3-122">20289.1000</span><span class="sxs-lookup"><span data-stu-id="c64a3-122">20289.1000</span></span> |
| [<span data-ttu-id="c64a3-123">新增設定應用程式</span><span class="sxs-lookup"><span data-stu-id="c64a3-123">New Settings app</span></span>](#new-settings-app)                     | <span data-ttu-id="c64a3-124">舊版的設定應用程式正由更新的版本取代為新功能和設定</span><span class="sxs-lookup"><span data-stu-id="c64a3-124">The legacy Settings app is being replaced by an updated version with new features and settings</span></span> | <span data-ttu-id="c64a3-125">20279.1006</span><span class="sxs-lookup"><span data-stu-id="c64a3-125">20279.1006</span></span> |
| [<span data-ttu-id="c64a3-126">預設應用程式選擇器</span><span class="sxs-lookup"><span data-stu-id="c64a3-126">Default app picker</span></span>](#default-app-picker)                 | <span data-ttu-id="c64a3-127">選擇每個檔案或連結類型應啟動的應用程式</span><span class="sxs-lookup"><span data-stu-id="c64a3-127">Choose which app should launch for each file or link type</span></span>                                      | <span data-ttu-id="c64a3-128">20279.1006</span><span class="sxs-lookup"><span data-stu-id="c64a3-128">20279.1006</span></span> |
| [<span data-ttu-id="c64a3-129">Office Web App</span><span class="sxs-lookup"><span data-stu-id="c64a3-129">Office web app</span></span>](#office-web-app)                         | <span data-ttu-id="c64a3-130">Office Web App 的快捷方式現在會列在 「所有應用程式」中</span><span class="sxs-lookup"><span data-stu-id="c64a3-130">A shortcut to the Office web app is now listed in "All apps"</span></span>                                   | <span data-ttu-id="c64a3-131">20279.1006</span><span class="sxs-lookup"><span data-stu-id="c64a3-131">20279.1006</span></span> |
| [<span data-ttu-id="c64a3-132">滑動以輸入</span><span class="sxs-lookup"><span data-stu-id="c64a3-132">Swipe to type</span></span>](#swipe-to-type)                           | <span data-ttu-id="c64a3-133">使用手指的提示在全攝影鍵盤上「滑動」文字</span><span class="sxs-lookup"><span data-stu-id="c64a3-133">Use the tip of your finger to "swipe" words on the holographic keyboard</span></span>                        | <span data-ttu-id="c64a3-134">20279.1006</span><span class="sxs-lookup"><span data-stu-id="c64a3-134">20279.1006</span></span> |
| [<span data-ttu-id="c64a3-135">USB-C 外接麥克風支援</span><span class="sxs-lookup"><span data-stu-id="c64a3-135">USB-C External Microphone Support</span></span>](#usb-c-external-microphone-support) | <span data-ttu-id="c64a3-136">針對應用程式和/或遠端輔助使用 USB-C 麥克風。</span><span class="sxs-lookup"><span data-stu-id="c64a3-136">Use USB-C microphones for apps and / or Remote Assist.</span></span>| <span data-ttu-id="c64a3-137">20279.1006</span><span class="sxs-lookup"><span data-stu-id="c64a3-137">20279.1006</span></span> |
| [<span data-ttu-id="c64a3-138">Kiosk 模式中新 App 的新 AUMID</span><span class="sxs-lookup"><span data-stu-id="c64a3-138">New AUMIDs for new apps in Kiosk mode</span></span>](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | <span data-ttu-id="c64a3-139">適用于新設定和 Edge 應用程式的 AUMID</span><span class="sxs-lookup"><span data-stu-id="c64a3-139">AUMIDs for new Settings and Edge apps</span></span> | <span data-ttu-id="c64a3-140">20279.1006</span><span class="sxs-lookup"><span data-stu-id="c64a3-140">20279.1006</span></span> |
| [<span data-ttu-id="c64a3-141">頁面設定可見度的新設定URIS</span><span class="sxs-lookup"><span data-stu-id="c64a3-141">New SettingsURIs for Page Settings Visibility</span></span>](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | <span data-ttu-id="c64a3-142">20+ 個新的 SettingsURIs for Settings/PageVisibilityList policy</span><span class="sxs-lookup"><span data-stu-id="c64a3-142">20+ new SettingsURIs for Settings/PageVisibilityList policy</span></span> | <span data-ttu-id="c64a3-143">20289.1000</span><span class="sxs-lookup"><span data-stu-id="c64a3-143">20289.1000</span></span> |
| [<span data-ttu-id="c64a3-144">改良的 Kiosk 模式失敗交還</span><span class="sxs-lookup"><span data-stu-id="c64a3-144">Improved Kiosk mode failure handing</span></span>](#kiosk-mode-behavior-changes-for-handling-of-failures) | <span data-ttu-id="c64a3-145">Kiosk 模式會先尋找全域指派的 Access，再尋找空白的開始功能表。</span><span class="sxs-lookup"><span data-stu-id="c64a3-145">Kiosk mode looks for Global Assigned Access before empty start menu.</span></span> | <span data-ttu-id="c64a3-146">20279.1006</span><span class="sxs-lookup"><span data-stu-id="c64a3-146">20279.1006</span></span> |
| [<span data-ttu-id="c64a3-147">設定後背診斷</span><span class="sxs-lookup"><span data-stu-id="c64a3-147">Configure Fallback Diagnostics</span></span>](#configuring-fallback-diagnostics-via-settings-app) | <span data-ttu-id="c64a3-148">在設定應用程式中設定後背診斷行為</span><span class="sxs-lookup"><span data-stu-id="c64a3-148">Setting Fallback Diagnostic Behavior in Settings App</span></span> | <span data-ttu-id="c64a3-149">20279.1006</span><span class="sxs-lookup"><span data-stu-id="c64a3-149">20279.1006</span></span> |
| [<span data-ttu-id="c64a3-150">與附近的裝置共用專案</span><span class="sxs-lookup"><span data-stu-id="c64a3-150">Share things with nearby devices</span></span>](#share-things-with-nearby-devices) | <span data-ttu-id="c64a3-151">從 HoloLens 共用檔案或 URL 到電腦</span><span class="sxs-lookup"><span data-stu-id="c64a3-151">Share files or URLs from a HoloLens to a PC</span></span> | <span data-ttu-id="c64a3-152">20279.1006</span><span class="sxs-lookup"><span data-stu-id="c64a3-152">20279.1006</span></span> |
| [<span data-ttu-id="c64a3-153">新的 OS Update 疑難排解員</span><span class="sxs-lookup"><span data-stu-id="c64a3-153">New OS Update troubleshooter</span></span>](#new-os-update-troubleshooter) | <span data-ttu-id="c64a3-154">作業系統更新設定中的新疑難排解員</span><span class="sxs-lookup"><span data-stu-id="c64a3-154">New troubleshooter in Settings for OS updates</span></span> | <span data-ttu-id="c64a3-155">20279.1006</span><span class="sxs-lookup"><span data-stu-id="c64a3-155">20279.1006</span></span> |
| [<span data-ttu-id="c64a3-156">更新中的改良與修正</span><span class="sxs-lookup"><span data-stu-id="c64a3-156">Improvements and fixes in the update</span></span>](#improvements-and-fixes-in-the-update) | <span data-ttu-id="c64a3-157">更新中的其他修正。</span><span class="sxs-lookup"><span data-stu-id="c64a3-157">Additional fixes in the update.</span></span> | <span data-ttu-id="c64a3-158">20279.1006</span><span class="sxs-lookup"><span data-stu-id="c64a3-158">20279.1006</span></span> |

### <span data-ttu-id="c64a3-159">全新 Microsoft Edge 的介紹</span><span class="sxs-lookup"><span data-stu-id="c64a3-159">Introducing the new Microsoft Edge</span></span>

![將舊版 Microsoft Edge 標誌動畫新到新的 Microsoft Edge 標誌](images/new-edge.gif)

<span data-ttu-id="c64a3-161">新的 Microsoft Edge [採用 Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) 開放來源專案，為客戶建立更佳的相容性，以及減少網頁開發人員的網路分散程度。</span><span class="sxs-lookup"><span data-stu-id="c64a3-161">The new Microsoft Edge [adopts the Chromium open source project](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) to create better compatibility for customers and less fragmentation of the web for web developers.</span></span>

<span data-ttu-id="c64a3-162">有了此 Insider Preview，HoloLens 2 客戶第一次可以使用新的 Microsoft Edge！</span><span class="sxs-lookup"><span data-stu-id="c64a3-162">With this Insider preview, the new Microsoft Edge is available to HoloLens 2 customers for the first time!</span></span> <span data-ttu-id="c64a3-163">雖然新的 Microsoft Edge 最終將會取代 HoloLens 2 上的舊版 Microsoft Edge，但測試人員目前可以使用這兩種瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="c64a3-163">While the new Microsoft Edge will eventually replace legacy Microsoft Edge on HoloLens 2, both browsers are currently available to Insiders.</span></span> <span data-ttu-id="c64a3-164">請透過新 Microsoft Edge 中的傳送\*\*\*\* 意見回饋功能，或透過意見回饋中心，與小組分享[意見和錯誤。](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="c64a3-164">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge or via [Feedback Hub](hololens-feedback.md).</span></span>

![新的 Microsoft Edge 螢幕擷取畫面](images/new-edge-ui.png)

#### <span data-ttu-id="c64a3-166">啟動新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c64a3-166">Launching the new Microsoft Edge</span></span>

<span data-ttu-id="c64a3-167">測試人員可以使用兩個版本的 Microsoft Edge：新的 Microsoft Edge 新 Microsoft Edge 圖示 (以藍色和綠色旋轉圖示) 和舊版 Microsoft Edge (以白色 ![ ](images/new_edge_logo.png) "e" 圖示) 表示。</span><span class="sxs-lookup"><span data-stu-id="c64a3-167">There are two versions of Microsoft Edge available to Insiders: the new Microsoft Edge ![new Microsoft Edge icon](images/new_edge_logo.png) (represented by a blue and green swirl icon) and legacy Microsoft Edge (represented by the white "e" icon).</span></span> <span data-ttu-id="c64a3-168">新的 Microsoft Edge 已釘釘到開始功能表，且會在您啟用網頁連結時自動啟動。</span><span class="sxs-lookup"><span data-stu-id="c64a3-168">The new Microsoft Edge is pinned to the Start menu and will automatically launch when you activate a web link.</span></span> <span data-ttu-id="c64a3-169">如果您想要還原成使用舊版 Microsoft Edge 做為預設網頁瀏覽器，請參閱下列指示 [以重設預設應用程式](#default-app-picker)。</span><span class="sxs-lookup"><span data-stu-id="c64a3-169">If you would like to revert to using legacy Microsoft Edge as your default web browser, see the instructions below for [resetting default apps](#default-app-picker).</span></span>

> [!NOTE]
> <span data-ttu-id="c64a3-170">當您第一次在 HoloLens 2 上啟動新的 Microsoft Edge 時，您的設定和資料將會從舊版 Microsoft Edge 中匯出。</span><span class="sxs-lookup"><span data-stu-id="c64a3-170">When you first launch the new Microsoft Edge on HoloLens 2, your settings and data will be imported from legacy Microsoft Edge.</span></span> <span data-ttu-id="c64a3-171">如果您在啟動新的 Microsoft Edge 之後繼續使用舊版 Microsoft Edge，新資料將不會從舊版 Microsoft Edge 同步處理到新的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="c64a3-171">If you continue to use legacy Microsoft Edge after launching the new Microsoft Edge, that new data will not be synced from legacy Microsoft Edge to the new Microsoft Edge.</span></span>

#### <span data-ttu-id="c64a3-172">設定新 Microsoft Edge 的策略設定</span><span class="sxs-lookup"><span data-stu-id="c64a3-172">Configuring policy settings for the new Microsoft Edge</span></span>

<span data-ttu-id="c64a3-173">新的 Microsoft Edge 提供 IT 系統管理員在 HoloLens 2 上的瀏覽器政策，比舊版 Microsoft Edge 提供的範圍更加廣泛。</span><span class="sxs-lookup"><span data-stu-id="c64a3-173">The new Microsoft Edge offers IT admins a much broader set of browser policies on HoloLens 2 than were previously available with legacy Microsoft Edge.</span></span>

<span data-ttu-id="c64a3-174">以下是一些實用的資源，可進一步學習管理新 Microsoft Edge 之策略設定：</span><span class="sxs-lookup"><span data-stu-id="c64a3-174">Here are some helpful resources for learning more about managing policy settings for the new Microsoft Edge:</span></span>

- [<span data-ttu-id="c64a3-175">使用 Microsoft Intune 設定 Microsoft Edge 原則設定</span><span class="sxs-lookup"><span data-stu-id="c64a3-175">Configure Microsoft Edge policy settings with Microsoft Intune</span></span>](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [<span data-ttu-id="c64a3-176">舊版 Microsoft Edge 與 Microsoft Edge 的原則對應</span><span class="sxs-lookup"><span data-stu-id="c64a3-176">Microsoft Edge Legacy to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [<span data-ttu-id="c64a3-177">Google Chrome 與 Microsoft Edge 的原則對應</span><span class="sxs-lookup"><span data-stu-id="c64a3-177">Google Chrome to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- <span data-ttu-id="c64a3-178">完整的 [Microsoft Edge Enterprise 檔](https://docs.microsoft.com/deployedge/)</span><span class="sxs-lookup"><span data-stu-id="c64a3-178">Full [Microsoft Edge Enterprise documentation](https://docs.microsoft.com/deployedge/)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c64a3-179">由於新 Microsoft Edge 支援的瀏覽器策略量大，因此我們的小組無法保證每一個新策略都適用于 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="c64a3-179">Because of the volume of browser policies supported by the new Microsoft Edge, our team is unable to guarantee that each new policy works on HoloLens 2.</span></span> <span data-ttu-id="c64a3-180">不過，相及于新 Microsoft Edge 中先前在 HoloLens 2 上支援的每個舊版 Microsoft Edge 政策，我們已測試及確認其功能會如預期地執行。</span><span class="sxs-lookup"><span data-stu-id="c64a3-180">However, we've tested and confirmed than the new Microsoft Edge equivalent of each legacy Microsoft Edge policy previously supported on HoloLens 2 work as expected.</span></span> <span data-ttu-id="c64a3-181">請參閱 [Microsoft Edge 舊版與 Microsoft Edge 策略](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) 對應，以尋找與 HoloLens 2 一同使用之每個舊版 Microsoft Edge 瀏覽器政策的新 Microsoft Edge 對應。</span><span class="sxs-lookup"><span data-stu-id="c64a3-181">See [Microsoft Edge Legacy to Microsoft Edge policy mapping](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) to find the new Microsoft Edge equivalent of each legacy Microsoft Edge browser policy you were using with HoloLens 2.</span></span>
>
> <span data-ttu-id="c64a3-182">我們知道至少有兩個新的 Microsoft Edge 政策無法與\*\* HoloLens 2 一起使用：</span><span class="sxs-lookup"><span data-stu-id="c64a3-182">There are at least two new Microsoft Edge policies that we know *will not* work with HoloLens 2:</span></span>
> - <span data-ttu-id="c64a3-183">EnterpriseModeSiteList</span><span class="sxs-lookup"><span data-stu-id="c64a3-183">EnterpriseModeSiteList</span></span>
> - <span data-ttu-id="c64a3-184">EnterpriseSiteListServiceURL</span><span class="sxs-lookup"><span data-stu-id="c64a3-184">EnterpriseSiteListServiceURL</span></span>

#### <span data-ttu-id="c64a3-185">HoloLens 2 上新 Microsoft Edge 的預計功能</span><span class="sxs-lookup"><span data-stu-id="c64a3-185">What to expect from the new Microsoft Edge on HoloLens 2</span></span>

<span data-ttu-id="c64a3-186">由於新的 Microsoft Edge 是原生 Win32 應用程式，具有新的 UWP 介面卡圖層，允許它在 UWP 裝置上執行，例如 HoloLens 2，因此可能無法立即使用某些功能。</span><span class="sxs-lookup"><span data-stu-id="c64a3-186">Because the new Microsoft Edge is a native Win32 app with a new UWP adapter layer allowing it to run on UWP-only devices like HoloLens 2, some features may not be immediately available.</span></span> <span data-ttu-id="c64a3-187">我們將支援未來幾個月的新案例和功能，因此請查看此空間以尋找最新資訊。</span><span class="sxs-lookup"><span data-stu-id="c64a3-187">We'll be supporting new scenarios and features over the coming months, so check this space for up-to-date information.</span></span>

**<span data-ttu-id="c64a3-188">預期可得的情境和功能：</span><span class="sxs-lookup"><span data-stu-id="c64a3-188">Scenarios and features expected to work:</span></span>**
- <span data-ttu-id="c64a3-189">第一次執行體驗、登出設定檔，以及同步</span><span class="sxs-lookup"><span data-stu-id="c64a3-189">First-run experience, sign in to profile, and sync</span></span>
- <span data-ttu-id="c64a3-190">網站應呈現並如預期行為</span><span class="sxs-lookup"><span data-stu-id="c64a3-190">Websites should render and behave as expected</span></span>
- <span data-ttu-id="c64a3-191">大部分瀏覽器功能 (我的最愛、歷程記錄等) 應該會如預期地使用</span><span class="sxs-lookup"><span data-stu-id="c64a3-191">Most browser functionality (Favorites, History, etc.) should work as expected</span></span>
- <span data-ttu-id="c64a3-192">深色模式</span><span class="sxs-lookup"><span data-stu-id="c64a3-192">Dark mode</span></span>
- <span data-ttu-id="c64a3-193">將 Web App 安裝到裝置</span><span class="sxs-lookup"><span data-stu-id="c64a3-193">Installing web apps to the device</span></span>
- <span data-ttu-id="c64a3-194">安裝擴充 (請告知我們您是否使用任何在 HoloLens 2 或 HoloLens 2 上無法正常運作的) </span><span class="sxs-lookup"><span data-stu-id="c64a3-194">Installing extensions (please let us know if you use any extensions that don't work properly on HoloLens 2)</span></span>
- <span data-ttu-id="c64a3-195">檢視和標記 PDF</span><span class="sxs-lookup"><span data-stu-id="c64a3-195">Viewing and marking up a PDF</span></span>
- <span data-ttu-id="c64a3-196">單一瀏覽器視窗的空間音效</span><span class="sxs-lookup"><span data-stu-id="c64a3-196">Spatial sound from a single browser window</span></span>
- <span data-ttu-id="c64a3-197">瀏覽器的自動和手動更新</span><span class="sxs-lookup"><span data-stu-id="c64a3-197">Automatic and manual updating of the browser</span></span>
- <span data-ttu-id="c64a3-198">使用 「儲存至 PDF」選項 (從列印功能表儲存 PDF) </span><span class="sxs-lookup"><span data-stu-id="c64a3-198">Saving a PDF from the Print menu (using "Save to PDF" option)</span></span>

**<span data-ttu-id="c64a3-199">即將推出案例和功能：</span><span class="sxs-lookup"><span data-stu-id="c64a3-199">Scenarios and features coming soon:</span></span>**
- <span data-ttu-id="c64a3-200">WebXR 和 360 Viewer 擴充功能</span><span class="sxs-lookup"><span data-stu-id="c64a3-200">WebXR and 360 Viewer extension</span></span>
- <span data-ttu-id="c64a3-201">當您流覽環境中多個視窗時，內容還原以修正視窗</span><span class="sxs-lookup"><span data-stu-id="c64a3-201">Content restoration to correct window when browsing across multiple windows placed in your environment</span></span>

**<span data-ttu-id="c64a3-202">無法預期的案例和功能：</span><span class="sxs-lookup"><span data-stu-id="c64a3-202">Scenarios and features not expected to work:</span></span>**
- <span data-ttu-id="c64a3-203">包含同時音訊流的多個視窗的空間音效</span><span class="sxs-lookup"><span data-stu-id="c64a3-203">Spatial sound from multiple windows with simultaneous audio streams</span></span>
- <span data-ttu-id="c64a3-204">「看到它，說出它」</span><span class="sxs-lookup"><span data-stu-id="c64a3-204">"See it, say it"</span></span>
- <span data-ttu-id="c64a3-205">列印</span><span class="sxs-lookup"><span data-stu-id="c64a3-205">Printing</span></span>

**<span data-ttu-id="c64a3-206">已知瀏覽器的熱門問題：</span><span class="sxs-lookup"><span data-stu-id="c64a3-206">Top known browser issues:</span></span>**
- <span data-ttu-id="c64a3-207">重設您的裝置將會移除新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c64a3-207">Resetting your device will remove the new Microsoft Edge</span></span>
- <span data-ttu-id="c64a3-208">全攝影鍵盤中的放大鏡預覽顯示不正確的內容</span><span class="sxs-lookup"><span data-stu-id="c64a3-208">The magnifier preview in the holographic keyboard shows incorrect content</span></span>

#### <span data-ttu-id="c64a3-209">Microsoft Edge Insider Channels</span><span class="sxs-lookup"><span data-stu-id="c64a3-209">Microsoft Edge Insider channels</span></span>

<span data-ttu-id="c64a3-210">Microsoft Edge 小組提供三個預覽通道給 Edge 測試人員社群：Beta、Dev 和 Canary。</span><span class="sxs-lookup"><span data-stu-id="c64a3-210">The Microsoft Edge team makes three preview channels available to the Edge Insider community: Beta, Dev, and Canary.</span></span> <span data-ttu-id="c64a3-211">安裝預覽通道不會卸載 HoloLens 2 上已發佈的 Microsoft Edge 版本，而且您可以同時安裝多個版本。</span><span class="sxs-lookup"><span data-stu-id="c64a3-211">Installing a preview channel doesn't uninstall the released version of Microsoft Edge on your HoloLens 2, and you can install more than one at the same time.</span></span> 

<span data-ttu-id="c64a3-212">請流覽 [Microsoft Edge Insider 首頁](https://www.microsoftedgeinsider.com) ，深入瞭解 Microsoft Edge Insider 社群。</span><span class="sxs-lookup"><span data-stu-id="c64a3-212">Visit the [Microsoft Edge Insider homepage](https://www.microsoftedgeinsider.com) to learn more about the Edge Insider community.</span></span> <span data-ttu-id="c64a3-213">若要深入瞭解不同的 Edge Insider 通道並開始使用，請流覽 [Edge Insider 下載頁面](https://www.microsoftedgeinsider.com/download)。</span><span class="sxs-lookup"><span data-stu-id="c64a3-213">To learn more about the different Edge Insider channels and get started, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download).</span></span>

<span data-ttu-id="c64a3-214">有幾個方法可用於將 Microsoft Edge 測試人員通道安裝到 HoloLens 2：</span><span class="sxs-lookup"><span data-stu-id="c64a3-214">There are a couple methods available for installing Microsoft Edge Insider channels to HoloLens 2:</span></span>

**<span data-ttu-id="c64a3-215">直接安裝在裝置 (目前僅適用于未管理裝置) </span><span class="sxs-lookup"><span data-stu-id="c64a3-215">Direct install on device (currently only available to unmanaged devices)</span></span>**
  1. <span data-ttu-id="c64a3-216">在 HoloLens 2 上，流覽 [Edge Insider 下載頁面](https://www.microsoftedgeinsider.com/download)。</span><span class="sxs-lookup"><span data-stu-id="c64a3-216">On your HoloLens 2, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download).</span></span>
  1. <span data-ttu-id="c64a3-217">選取要安裝之 Edge Insider 通道的 **HoloLens 2** 下載按鈕。</span><span class="sxs-lookup"><span data-stu-id="c64a3-217">Select the **Download for HoloLens 2** button for the Edge Insider channel you wish to install.</span></span>
  1. <span data-ttu-id="c64a3-218">從 Edge 下載佇列或裝置上的 「下載」資料夾啟動下載的 .msix 檔案， (檔案檔案) 。</span><span class="sxs-lookup"><span data-stu-id="c64a3-218">Launch the downloaded .msix file from the Edge download queue or from your device's "Downloads" folder (using File Explorer).</span></span>
  1. <span data-ttu-id="c64a3-219">[應用程式安裝程式](app-deploy-app-installer.md) 將會啟動。</span><span class="sxs-lookup"><span data-stu-id="c64a3-219">[App installer](app-deploy-app-installer.md) will launch.</span></span>
  1. <span data-ttu-id="c64a3-220">選取安裝 **按鈕** 。</span><span class="sxs-lookup"><span data-stu-id="c64a3-220">Select the **Install** button.</span></span>
  1. <span data-ttu-id="c64a3-221">成功安裝之後，您可以在開始功能表的所有應用程式清單中，將 Microsoft Edge Beta 版、Dev\*\*\*\* 或 Canary 視為個別專案。</span><span class="sxs-lookup"><span data-stu-id="c64a3-221">After successful install, you'll find Microsoft Edge Beta, Dev, or Canary as a separate entry in the **All apps** list of the Start menu.</span></span>

**<span data-ttu-id="c64a3-222">透過電腦使用 Windows 裝置入口網站 (需要啟用[](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)HoloLens 2 應用程式上的開發人員) </span><span class="sxs-lookup"><span data-stu-id="c64a3-222">Install via PC with Windows Device Portal (requires [developer mode](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) to be enabled on HoloLens 2)</span></span>**
  1. <span data-ttu-id="c64a3-223">在您的電腦上，流覽 [Edge Insider 下載頁面](https://www.microsoftedgeinsider.com/download)。</span><span class="sxs-lookup"><span data-stu-id="c64a3-223">On your PC, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download).</span></span>
  1. <span data-ttu-id="c64a3-224">選取 **要安裝之** Edge Insider 通道之 「下載 Windows 10」按鈕旁的下拉式箭號按鈕。</span><span class="sxs-lookup"><span data-stu-id="c64a3-224">Select the **drop-down arrow button** next to the "Download for Windows 10" button for the Edge Insider channel you wish to install.</span></span>
  1. <span data-ttu-id="c64a3-225">在**下拉式功能表中選取 HoloLens 2。**</span><span class="sxs-lookup"><span data-stu-id="c64a3-225">Select **HoloLens 2** in the drop-down menu.</span></span>
  1. <span data-ttu-id="c64a3-226">將 .msix 檔案儲存到您電腦中的 「下載」資料夾 (或另一個您可以輕鬆地找到) 。</span><span class="sxs-lookup"><span data-stu-id="c64a3-226">Save the .msix file to the "Downloads" folder of your PC (or another folder you can easily find).</span></span>
  1. <span data-ttu-id="c64a3-227">使用 [您電腦中的 Windows](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) 裝置入口網站在 HoloLens 2 上安裝下載的 .msix 檔案。</span><span class="sxs-lookup"><span data-stu-id="c64a3-227">Use [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) on your PC to install the downloaded .msix file on HoloLens 2.</span></span>
  1. <span data-ttu-id="c64a3-228">成功安裝之後，您可以在開始功能表的所有應用程式清單中，將 Microsoft Edge Beta、Dev 或\*\*\*\* Canary 視為個別專案。</span><span class="sxs-lookup"><span data-stu-id="c64a3-228">After successful install, you'll find Microsoft Edge Beta, Dev, or Canary as a separate entry in the **All apps** list of the Start menu.</span></span>

> [!NOTE]
> <span data-ttu-id="c64a3-229">在 HoloLens 2 的 Windows 測試人員預覽版期間，您裝置上的 Microsoft Edge 版本可能高於某些 (或 Microsoft Edge 測試人員) 中提供的版本。</span><span class="sxs-lookup"><span data-stu-id="c64a3-229">During this Windows Insider preview for HoloLens 2, the version of Microsoft Edge on your device may be higher than those available in some (or all) of the Microsoft Edge Insider channels.</span></span> <span data-ttu-id="c64a3-230">這是為了確保專為 HoloLens 2 的網頁瀏覽器所設計的新功能和修正程式能儘快連至我們的 Windows 測試人員。</span><span class="sxs-lookup"><span data-stu-id="c64a3-230">This is to ensure new features and fixes specifically targeting the web browser on HoloLens 2 are getting to our Windows Insiders as quickly as possible.</span></span> <span data-ttu-id="c64a3-231">下一次 Windows 更新公開發行之後，Microsoft Edge 測試人員通道版本將會超越並超越 HoloLens 2 上的 Microsoft Edge 版本。</span><span class="sxs-lookup"><span data-stu-id="c64a3-231">Shortly after the public release of the next Windows update, the Microsoft Edge Insider channel builds will surpass, and stay ahead of, the version of Microsoft Edge on your HoloLens 2.</span></span>

### <span data-ttu-id="c64a3-232">WebXR 和 360 Viewer</span><span class="sxs-lookup"><span data-stu-id="c64a3-232">WebXR and 360 Viewer</span></span>

*<span data-ttu-id="c64a3-233">在 Windows Insider Build 20289.1000 中新增</span><span class="sxs-lookup"><span data-stu-id="c64a3-233">Added in Windows Insider build 20289.1000</span></span>*

<span data-ttu-id="c64a3-234">新的 Microsoft Edge 支援 WebXR，這是建立取代 WebVR (網頁體驗的新) 。</span><span class="sxs-lookup"><span data-stu-id="c64a3-234">The new Microsoft Edge includes support for WebXR, which is the new standard for creating immersive web experiences (replacing WebVR).</span></span> <span data-ttu-id="c64a3-235">許多沉浸式網頁體驗在設計時都考慮到 VR， (以虛擬環境) 取代您的視野，但 HoloLens 2 也支援這些體驗。</span><span class="sxs-lookup"><span data-stu-id="c64a3-235">Many immersive web experiences were designed with VR in mind (they replace your field of view with a virtual environment), but these experiences are also supported by HoloLens 2.</span></span> <span data-ttu-id="c64a3-236">WebXR 標準也可啟用使用您實體環境的增強和混合實境沉浸式 Web 體驗。</span><span class="sxs-lookup"><span data-stu-id="c64a3-236">The WebXR standard also enables augmented and mixed reality immersive web experiences that use your physical environment.</span></span> <span data-ttu-id="c64a3-237">隨著開發人員花更多時間使用 WebXR，我們預期新的增強和混合實境沉浸式體驗將送達 HoloLens 2 客戶嘗試！</span><span class="sxs-lookup"><span data-stu-id="c64a3-237">As developers spend more time with WebXR, we anticipate new augmented and mixed reality immersive experiences will arrive for HoloLens 2 customers to try!</span></span>

<span data-ttu-id="c64a3-238">360 檢視器擴充功能建立在 WebXR 上，會自動與 HoloLens 2 上的新 Microsoft Edge 一起安裝。</span><span class="sxs-lookup"><span data-stu-id="c64a3-238">The 360 Viewer extension is built on WebXR and automatically installs alongside the new Microsoft Edge on HoloLens 2.</span></span> <span data-ttu-id="c64a3-239">此 Web 擴充功能讓您能沉浸于 360 度影片中。</span><span class="sxs-lookup"><span data-stu-id="c64a3-239">This web extension gives you the ability to immerse yourself in 360-degree videos.</span></span> <span data-ttu-id="c64a3-240">YouTube 提供最多 360 個影片選擇，因此我們建議您從該影片開始。</span><span class="sxs-lookup"><span data-stu-id="c64a3-240">YouTube offers the largest selection of 360 videos, so we encourage you to start there.</span></span>

#### <span data-ttu-id="c64a3-241">如何使用 WebXR</span><span class="sxs-lookup"><span data-stu-id="c64a3-241">How to use WebXR</span></span>

1. <span data-ttu-id="c64a3-242">使用 WebXR 支援流覽至網站。</span><span class="sxs-lookup"><span data-stu-id="c64a3-242">Navigate to a website with WebXR support.</span></span>
1. <span data-ttu-id="c64a3-243">選取網站的 **Enter VR** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c64a3-243">Select the **Enter VR** button on the website.</span></span> <span data-ttu-id="c64a3-244">這個按鈕的位置和視覺呈現方式會因網站而異，但看起來可能類似：</span><span class="sxs-lookup"><span data-stu-id="c64a3-244">The location and visual representation of this button may vary per website, but it may look similar to:</span></span>

    ![輸入 VR 按鈕範例](images/75px-enter-vr.png)

1. <span data-ttu-id="c64a3-246">當您第一次嘗試在特定的網域上啟動 WebXR 體驗時，瀏覽器會要求同意進入沉浸式視圖，**選取允許。**</span><span class="sxs-lookup"><span data-stu-id="c64a3-246">The first time you try to launch a WebXR experience on a specific domain, the browser will ask for consent to enter an immersive view, select **Allow**.</span></span>
1. <span data-ttu-id="c64a3-247">使用 [HoloLens 2 手勢](hololens2-basic-usage.md#the-hand-tracking-frame) 操作體驗。</span><span class="sxs-lookup"><span data-stu-id="c64a3-247">Use [HoloLens 2 gestures](hololens2-basic-usage.md#the-hand-tracking-frame) to manipulate the experience.</span></span>
1. <span data-ttu-id="c64a3-248">如果體驗沒有 **離開按鈕，** 請使用開始 [手勢](hololens2-basic-usage.md#start-gesture) 返回首頁。</span><span class="sxs-lookup"><span data-stu-id="c64a3-248">If the experience doesn't have an **Exit** button, use the [Start gesture](hololens2-basic-usage.md#start-gesture) to return home.</span></span>

**<span data-ttu-id="c64a3-249">建議的 WebXR 範例</span><span class="sxs-lookup"><span data-stu-id="c64a3-249">Recommended WebXR samples</span></span>**
- <span data-ttu-id="c64a3-250">360 Viewer (查看下一節) </span><span class="sxs-lookup"><span data-stu-id="c64a3-250">360 Viewer (see next section)</span></span>
- [<span data-ttu-id="c64a3-251">XR 小龍</span><span class="sxs-lookup"><span data-stu-id="c64a3-251">XR Dinosaurs</span></span>](https://www.xrdinosaurs.com/)
- [<span data-ttu-id="c64a3-252">Barista Express</span><span class="sxs-lookup"><span data-stu-id="c64a3-252">Barista Express</span></span>](https://constructarca.de/game/barista-express/)
- [<span data-ttu-id="c64a3-253">WebXR 小圖</span><span class="sxs-lookup"><span data-stu-id="c64a3-253">WebXR Paint</span></span>](https://threejs.org/examples/webxr_vr_paint.html)

#### <span data-ttu-id="c64a3-254">如何使用 360 Viewer</span><span class="sxs-lookup"><span data-stu-id="c64a3-254">How to use 360 Viewer</span></span>

1. <span data-ttu-id="c64a3-255">流覽至 YouTube 上的 360 度影片。</span><span class="sxs-lookup"><span data-stu-id="c64a3-255">Navigate to a 360-degree video on YouTube.</span></span>
1. <span data-ttu-id="c64a3-256">在視訊畫面中，選取混合實境耳機按鈕：</span><span class="sxs-lookup"><span data-stu-id="c64a3-256">In the video frame, select the mixed reality headset button:</span></span>

    ![啟用 360 檢視器的按鈕](images/enter-360-viewer.jpg)

1. <span data-ttu-id="c64a3-258">當您第一次嘗試在特定的網域上啟動 360 Viewer 時，瀏覽器會要求同意進入沉浸式檢視。</span><span class="sxs-lookup"><span data-stu-id="c64a3-258">The first time you try to launch 360 Viewer on a specific domain, the browser will ask for consent to enter an immersive view.</span></span> <span data-ttu-id="c64a3-259">選取 **允許**。</span><span class="sxs-lookup"><span data-stu-id="c64a3-259">Select **Allow**.</span></span>
1. <span data-ttu-id="c64a3-260">[空中點兩](hololens2-basic-usage.md#select-using-air-tap) 下可顯示播放控制項。</span><span class="sxs-lookup"><span data-stu-id="c64a3-260">[Air tap](hololens2-basic-usage.md#select-using-air-tap) to bring up the playback controls.</span></span> <span data-ttu-id="c64a3-261">使用 [手](hololens2-basic-usage.md#select-using-air-tap) 拍和空中點兩下來播放/暫停、向前/向後跳、開啟/關閉輔助字幕，或 (結束沉浸式) 。</span><span class="sxs-lookup"><span data-stu-id="c64a3-261">Use [hand rays and air tap](hololens2-basic-usage.md#select-using-air-tap) to play/pause, skip forward/back, turn captions on/off, or stop the experience (which exits the immersive view).</span></span> <span data-ttu-id="c64a3-262">播放控制項會在閒置幾秒鐘後消失。</span><span class="sxs-lookup"><span data-stu-id="c64a3-262">The playback controls will disappear after a few seconds of inactivity.</span></span>

#### <span data-ttu-id="c64a3-263">WebXR 和 360 檢視器已知問題</span><span class="sxs-lookup"><span data-stu-id="c64a3-263">Top WebXR and 360 Viewer known issues</span></span>
- <span data-ttu-id="c64a3-264">在 WebXR 體驗中，當您傾斜頭部或四處移動時，全形影像可能會移動或傾斜。</span><span class="sxs-lookup"><span data-stu-id="c64a3-264">In WebXR experiences, holograms may shift or tilt when you tilt your head or move around your environment.</span></span>
- <span data-ttu-id="c64a3-265">根據 WebXR 體驗的複雜度，框架速率可能會降低或斷斷續續。</span><span class="sxs-lookup"><span data-stu-id="c64a3-265">Depending on the complexity of the WebXR experience, the framerate may drop or stutter.</span></span>
- <span data-ttu-id="c64a3-266">WebXR 目前還無法提供手寫手部連接。</span><span class="sxs-lookup"><span data-stu-id="c64a3-266">Articulated hand joints are not yet available in WebXR.</span></span>
- <span data-ttu-id="c64a3-267">在離開 WebXR 或 360 檢視器體驗時，混合實境首頁中的全形影像可能需要 30 秒或更長時間重新出現。</span><span class="sxs-lookup"><span data-stu-id="c64a3-267">When exiting a WebXR or 360 Viewer experience, it may take 30 seconds or more for holograms in the mixed reality home to reappear.</span></span>
- <span data-ttu-id="c64a3-268">YouTube 外網站的 360 個影片可能無法如預期地播放。</span><span class="sxs-lookup"><span data-stu-id="c64a3-268">360 videos from websites other than YouTube may not work as expected.</span></span>
- <span data-ttu-id="c64a3-269">如果 360 影片未進入沉浸式 (或混合實境耳機按鈕未顯示在) ，請嘗試重新組織頁面。</span><span class="sxs-lookup"><span data-stu-id="c64a3-269">If 360 videos don't enter immersive view (or the mixed reality headset button doesn't appear), try refreshing the page.</span></span>
- <span data-ttu-id="c64a3-270">在 HoloLens 2 上的 360 Viewer 中還看不到標題。</span><span class="sxs-lookup"><span data-stu-id="c64a3-270">Captions are not yet visible in 360 Viewer on HoloLens 2.</span></span>
- <span data-ttu-id="c64a3-271">在 360 Viewer 中暫停影片會停止影片的顯示 (但選取播放按鈕會正確繼續播放) 。</span><span class="sxs-lookup"><span data-stu-id="c64a3-271">Pausing a video in 360 Viewer stops the video from rendering (but selecting the play button correctly resumes playback).</span></span>
- <span data-ttu-id="c64a3-272">360 Viewer 中的 「下一段影片」按鈕目前無法工作。</span><span class="sxs-lookup"><span data-stu-id="c64a3-272">The "next video" button in 360 Viewer does not currently work.</span></span>
- <span data-ttu-id="c64a3-273">您可以在沉浸式「影區」模式中播放 2D 影片，但框架速率小於 30 fps。</span><span class="sxs-lookup"><span data-stu-id="c64a3-273">You can play 2D videos in an immersive "theater" mode, but the framerate will be less than 30 fps.</span></span>

#### <span data-ttu-id="c64a3-274">在 WebXR 和 360 Viewer 上提供意見回饋</span><span class="sxs-lookup"><span data-stu-id="c64a3-274">Providing feedback on WebXR and 360 Viewer</span></span>

<span data-ttu-id="c64a3-275">請透過新 Microsoft Edge 中的傳送\*\*\*\* 意見回饋功能，與小組分享意見回饋和錯誤。</span><span class="sxs-lookup"><span data-stu-id="c64a3-275">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge.</span></span>

### <span data-ttu-id="c64a3-276">新增設定應用程式</span><span class="sxs-lookup"><span data-stu-id="c64a3-276">New Settings app</span></span>

<span data-ttu-id="c64a3-277">此版本推出後，我們將推出新版的設定應用程式。</span><span class="sxs-lookup"><span data-stu-id="c64a3-277">With this release, we're introducing a new version of the Settings app.</span></span> <span data-ttu-id="c64a3-278">新的設定應用程式包含 HoloLens 2 的新功能和下列領域的擴充設定：音效、Power & 睡眠、網路 & 網際網路、應用程式、帳戶、輕鬆存取等等。</span><span class="sxs-lookup"><span data-stu-id="c64a3-278">The new Settings app includes new features and expanded settings for HoloLens 2 in the following areas: Sound, Power & sleep, Network & Internet, Apps, Accounts, Ease of Access, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="c64a3-279">由於新的設定應用程式與舊版的設定應用程式不同，因此您先前置於環境周圍的任何設定視窗，都會在更新時移除。</span><span class="sxs-lookup"><span data-stu-id="c64a3-279">Because the new Settings app is distinct from the legacy Settings app, any Settings windows you previously placed around your environment will be removed upon update.</span></span>

![新的設定應用程式首頁](images/new-settings-app.png)

**<span data-ttu-id="c64a3-281">新功能和設定</span><span class="sxs-lookup"><span data-stu-id="c64a3-281">New features and settings</span></span>**
- <span data-ttu-id="c64a3-282">設定搜尋：使用關鍵字或設定名稱從 [設定首頁搜尋設定。</span><span class="sxs-lookup"><span data-stu-id="c64a3-282">Settings search: search for settings from the Settings homepage using keywords or the setting's name.</span></span>
- <span data-ttu-id="c64a3-283">系統>音效：</span><span class="sxs-lookup"><span data-stu-id="c64a3-283">System > Sound:</span></span>
  - <span data-ttu-id="c64a3-284">輸入和輸出音訊裝置：獨立選擇您的輸入和輸出音訊裝置 (例如，透過藍牙耳機聆聽音訊，或使用 USB-C 麥克風進行音訊輸入) 。</span><span class="sxs-lookup"><span data-stu-id="c64a3-284">Input and output audio devices: independently choose your input and output audio devices (for example, listen to audio via Bluetooth headphones or use a USB-C microphone for audio input).</span></span> 
    > [!NOTE]
    > <span data-ttu-id="c64a3-285">HoloLens 2 不支援藍牙麥克風。</span><span class="sxs-lookup"><span data-stu-id="c64a3-285">Bluetooth microphones are not supported by HoloLens 2.</span></span>
  - <span data-ttu-id="c64a3-286">應用程式音量：分別調整每個 App 的音量。</span><span class="sxs-lookup"><span data-stu-id="c64a3-286">App volume: independently adjust the volume of each app.</span></span>
- <span data-ttu-id="c64a3-287">系統>電源&：選擇裝置在閒置一段時間之後應該進入睡眠狀態。</span><span class="sxs-lookup"><span data-stu-id="c64a3-287">System > Power & sleep: choose when the device should go to sleep after a period of inactivity.</span></span>
- <span data-ttu-id="c64a3-288">系統>：手動啟用省電模式或設定電池閾值，此時省電模式會自動開啟。</span><span class="sxs-lookup"><span data-stu-id="c64a3-288">System > Battery: manually enable battery saver mode or set a battery threshold at which point battery saver mode turns on automatically.</span></span>
- <span data-ttu-id="c64a3-289">USB 裝置>：您預設可以停用 USB 連接。</span><span class="sxs-lookup"><span data-stu-id="c64a3-289">Devices > USB: you can disable USB connections by default.</span></span>
- <span data-ttu-id="c64a3-290">網路&網際網路：</span><span class="sxs-lookup"><span data-stu-id="c64a3-290">Network & Internet:</span></span>
  - <span data-ttu-id="c64a3-291">USB-C 乙太網路介面卡現在會出現在網際網路&中。</span><span class="sxs-lookup"><span data-stu-id="c64a3-291">USB-C Ethernet adapters will now appear in Network & Internet.</span></span>
  - <span data-ttu-id="c64a3-292">USB-C 乙太網路介面卡設定現已提供，包括其 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c64a3-292">USB-C Ethernet adapter settings are now available, including its IP address.</span></span>
  - <span data-ttu-id="c64a3-293">現在您可以在 HoloLens 2 上啟用飛航模式。</span><span class="sxs-lookup"><span data-stu-id="c64a3-293">You can now enable airplane mode on HoloLens 2.</span></span>
- <span data-ttu-id="c64a3-294">應用程式：您可以重設用於檔案和連結類型的預設應用程式。</span><span class="sxs-lookup"><span data-stu-id="c64a3-294">Apps: you can reset the default apps used for file and link types.</span></span> <span data-ttu-id="c64a3-295">詳細資訊請參閱預設 [應用程式選擇器](#default-app-picker)。</span><span class="sxs-lookup"><span data-stu-id="c64a3-295">For more information see [Default app picker](#default-app-picker).</span></span>
- <span data-ttu-id="c64a3-296">帳戶>：裝置擁有者可以新增使用者、將標準使用者升級為裝置擁有者、將裝置擁有者降級為標準使用者，以及移除使用者。</span><span class="sxs-lookup"><span data-stu-id="c64a3-296">Accounts > Other users: device owners can add users, upgrade standard users to device owners, downgrade device owners to standard users, and remove users.</span></span>
- <span data-ttu-id="c64a3-297">輕鬆存取：變更文字大小和一些視覺效果。</span><span class="sxs-lookup"><span data-stu-id="c64a3-297">Ease of Access: change text size and some visual effects.</span></span>

**<span data-ttu-id="c64a3-298">已知問題</span><span class="sxs-lookup"><span data-stu-id="c64a3-298">Known issues</span></span>**
- <span data-ttu-id="c64a3-299">先前放置的設定視窗將會移除 (上方的備註) 。</span><span class="sxs-lookup"><span data-stu-id="c64a3-299">Previously placed Settings windows will be removed (see note above).</span></span>
- <span data-ttu-id="c64a3-300">流覽通知頁面可能會導致設定應用程式當機 (調查) 。</span><span class="sxs-lookup"><span data-stu-id="c64a3-300">Visiting the Notifications page may crash the Settings app (investigating).</span></span>
- <span data-ttu-id="c64a3-301">乙太網路頁面目前不會顯示 (修正) 。</span><span class="sxs-lookup"><span data-stu-id="c64a3-301">The Ethernet page currently doesn't show up (to be fixed soon).</span></span>
- <span data-ttu-id="c64a3-302">您無法再使用設定應用程式重新命名您的裝置 (IT 系統管理員可以使用部署套件或 MDM 來重新命名裝置) 。</span><span class="sxs-lookup"><span data-stu-id="c64a3-302">You can no longer rename your device with the Settings app (IT admins can use provisioning packages or MDM to rename devices).</span></span>
- <span data-ttu-id="c64a3-303">新版 Microsoft Edge 的電池使用量可能不太正確，因為其性質是 UWP 介面卡圖層支援的 Win32 桌面應用程式， (預期近期將修正) 。</span><span class="sxs-lookup"><span data-stu-id="c64a3-303">Battery usage for the new Microsoft Edge may not be accurate, due to its nature as a Win32 desktop application supported by a UWP adapter layer (no fix anticipated soon).</span></span>

### <span data-ttu-id="c64a3-304">預設應用程式選擇器</span><span class="sxs-lookup"><span data-stu-id="c64a3-304">Default app picker</span></span>

<span data-ttu-id="c64a3-305">當您啟用超連結或開啟具有多個已安裝應用程式的檔案類型時 ，會看到一個新視窗開啟，提示您選取該安裝的應用程式應處理檔案或連結類型。</span><span class="sxs-lookup"><span data-stu-id="c64a3-305">When you activate a hyperlink or open a file type with more than one installed app, which supports it, you will see a new window open prompting you to select which installed app should handle the file or link type.</span></span> <span data-ttu-id="c64a3-306">在此視窗中，您也可以選擇讓選取的應用程式處理檔案或連結類型「一次」或「永遠」。</span><span class="sxs-lookup"><span data-stu-id="c64a3-306">In this window, you can also choose to have the selected app handle the file or link type "Once" or "Always."</span></span>

![應用程式選擇器視窗](images/default-app-picker.png)

<span data-ttu-id="c64a3-308">如果您選擇 「Always」，但稍後想要變更處理特定檔案或連結類型的應用程式，您可以在應用程式設定中重 **設>預設值**。</span><span class="sxs-lookup"><span data-stu-id="c64a3-308">If you choose "Always" but later want to change which app handles a particular file or link type, you can reset your saved defaults in **Settings > Apps**.</span></span> <span data-ttu-id="c64a3-309">卷卷至頁面底部，然後選取 「\*\*\*\* 檔案類型的預設應用程式」和/或「連結類型的預設應用程式」下的清除按鈕。</span><span class="sxs-lookup"><span data-stu-id="c64a3-309">Scroll to the bottom of the page and select the **Clear** button under "Default apps for file types" and/or "Default apps for link types."</span></span> <span data-ttu-id="c64a3-310">不同于桌上型電腦中的類似設定，您無法重設個別檔案類型的預設值。</span><span class="sxs-lookup"><span data-stu-id="c64a3-310">Unlike the similar setting on desktop PCs, you can't reset individual file type defaults.</span></span>

### <span data-ttu-id="c64a3-311">Office Web App</span><span class="sxs-lookup"><span data-stu-id="c64a3-311">Office web app</span></span>

<span data-ttu-id="c64a3-312">Office Web App 已新增到開始功能表中的 「所有應用程式」清單。</span><span class="sxs-lookup"><span data-stu-id="c64a3-312">The Office web app has been added to the "All apps" list in the Start menu.</span></span> <span data-ttu-id="c64a3-313">這個 Web 應用程式也可以釘釘到開始或卸載。</span><span class="sxs-lookup"><span data-stu-id="c64a3-313">This web app can also be pinned to Start or uninstalled.</span></span> <span data-ttu-id="c64a3-314">由於這是 Web 應用程式，因此其功能會完全符合您流覽時的體驗 https://www.office.com 。</span><span class="sxs-lookup"><span data-stu-id="c64a3-314">Because this is a web app, its functionality matches exactly what you'd experience by visiting https://www.office.com.</span></span> <span data-ttu-id="c64a3-315">Office Web App 功能只有在 HoloLens 2 有有效的網際網路連接時才能使用。</span><span class="sxs-lookup"><span data-stu-id="c64a3-315">Office web app functionality is only available when your HoloLens 2 has an active internet connection.</span></span>

### <span data-ttu-id="c64a3-316">滑動以輸入</span><span class="sxs-lookup"><span data-stu-id="c64a3-316">Swipe to type</span></span>

<span data-ttu-id="c64a3-317">有些客戶會滑動想要輸入之字詞的形狀，以在虛擬鍵盤上更快速地「輸入」，我們正在預覽全攝影鍵盤的這項功能。</span><span class="sxs-lookup"><span data-stu-id="c64a3-317">Some customers find it faster to "type" on virtual keyboards by swiping the shape of the word they intend to type, and we're previewing this feature for the holographic keyboard.</span></span> <span data-ttu-id="c64a3-318">您可以一次滑動一個字，將手指的筆尖透過全攝影鍵盤的螢幕、滑動文字的形狀，然後從鍵盤上收回手指的提示。</span><span class="sxs-lookup"><span data-stu-id="c64a3-318">You can swipe one word at a time by passing the tip of your finger through the plane of the holographic keyboard, swiping the shape of the word, and then withdrawing the tip of your finger from the plane of the keyboard.</span></span> <span data-ttu-id="c64a3-319">您可以將手指從鍵盤上移除，以在文字之間移動，不需要按空格鍵，即可滑動後續文字。</span><span class="sxs-lookup"><span data-stu-id="c64a3-319">You can swipe follow up words without needing to press the spacebar by removing your finger from the keyboard between words.</span></span> <span data-ttu-id="c64a3-320">如果您看到手指在鍵盤上移動後看到滑動軌跡，就會知道此功能正在使用中。</span><span class="sxs-lookup"><span data-stu-id="c64a3-320">You will know the feature is working if you see a swipe trail following your finger's movement on the keyboard.</span></span>

<span data-ttu-id="c64a3-321">請注意，由於全像攝影鍵盤的性質，您不會因為手指而感到受威脅，因此使用和掌握這項功能可能會有些難度 (手機顯示器和手機) 。</span><span class="sxs-lookup"><span data-stu-id="c64a3-321">Please note, this feature can be tricky to use and master because of the nature of a holographic keyboard where you don't feel resistance against your finger (unlike a mobile phone display).</span></span> <span data-ttu-id="c64a3-322">我們正在評估這項公開發行功能，因此您的意見至關重要;您是否覺得這項功能實用或您的意見有建設性的意見，請透過意見回饋中心 [讓我們知道](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="c64a3-322">We are evaluating this feature for public release, so your feedback is important; whether you find the feature useful or you have constructive feedback, please let us know via [Feedback Hub](hololens-feedback.md).</span></span>

### <span data-ttu-id="c64a3-323">USB-C 外接麥克風支援</span><span class="sxs-lookup"><span data-stu-id="c64a3-323">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c64a3-324">插入 USB **麥克風並不會自動將其設定為輸入裝置**。</span><span class="sxs-lookup"><span data-stu-id="c64a3-324">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="c64a3-325">插入一組 USB-C 耳機時，使用者會注意到耳機的音訊會自動重新導向至耳機，但 HoloLens OS 會將內部麥克風陣列優先排列于任何其他輸入裝置上方。</span><span class="sxs-lookup"><span data-stu-id="c64a3-325">When plugging in a set of USB-C headphones users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> **<span data-ttu-id="c64a3-326">若要使用 USB-C 麥克風，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="c64a3-326">In order to use a USB-C microphone follow the steps below.</span></span>**

<span data-ttu-id="c64a3-327">使用者可以使用聲音設定面板選取 USB-C 連接 **的外部** 麥克風。</span><span class="sxs-lookup"><span data-stu-id="c64a3-327">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="c64a3-328">USB-C 麥克風可用於通話、錄製等。</span><span class="sxs-lookup"><span data-stu-id="c64a3-328">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="c64a3-329">開啟設定**應用程式**，然後選取**系統**  ->  **音效**。</span><span class="sxs-lookup"><span data-stu-id="c64a3-329">Open the **Settings** app and select **System** -> **Sound**.</span></span>

![音效設定](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="c64a3-331">若要使用外接式麥克風與 **遠端**輔助，使用者必須按一下 [管理音效裝置」 超連結。</span><span class="sxs-lookup"><span data-stu-id="c64a3-331">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="c64a3-332">然後使用下拉式選項將外部麥克風設為**預設或\*\*\*\*通訊預設值。**</span><span class="sxs-lookup"><span data-stu-id="c64a3-332">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="c64a3-333">選擇 **預設值** 表示外接式麥克風會用於所有位置。</span><span class="sxs-lookup"><span data-stu-id="c64a3-333">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="c64a3-334">選擇 **通訊** 預設值表示外部麥克風將用於遠端輔助和其他通訊應用程式，但 HoloLens 麥克風陣列可能仍然用於其他工作。</span><span class="sxs-lookup"><span data-stu-id="c64a3-334">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![管理音效裝置](images/usbc-mic-2.png)

<br>

![將麥克風設為預設值](images/usbc-mic-3.jpg)

#### <span data-ttu-id="c64a3-337">藍牙麥克風支援呢？</span><span class="sxs-lookup"><span data-stu-id="c64a3-337">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="c64a3-338">很抱歉，HoloLens 2 目前仍不支援藍牙麥克風。</span><span class="sxs-lookup"><span data-stu-id="c64a3-338">Unfortunately Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

#### <span data-ttu-id="c64a3-339">USB-C 麥克風疑難排解</span><span class="sxs-lookup"><span data-stu-id="c64a3-339">Troubleshooting USB-C microphones</span></span>

<span data-ttu-id="c64a3-340">請注意，有些 USB-C 麥克風無法正確報告本身為麥克風和喇\*\* 叭。</span><span class="sxs-lookup"><span data-stu-id="c64a3-340">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="c64a3-341">這是麥克風的問題，而非 HoloLens 的問題。</span><span class="sxs-lookup"><span data-stu-id="c64a3-341">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="c64a3-342">將其中一個麥克風插入 HoloLens 時，可能會遺失聲音。</span><span class="sxs-lookup"><span data-stu-id="c64a3-342">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="c64a3-343">幸好有一個簡單的修正程式。</span><span class="sxs-lookup"><span data-stu-id="c64a3-343">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="c64a3-344">在**設定**系統音效中，將內建喇叭 ( ->  \*\*\*\*  ->  \*\* \*\*\*\*類比功能音訊**驅動程式) 預設**裝置\*\*。</span><span class="sxs-lookup"><span data-stu-id="c64a3-344">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="c64a3-345">HoloLens 應該會記住這項設定，即使麥克風稍後已移除並重新連接也一樣。</span><span class="sxs-lookup"><span data-stu-id="c64a3-345">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![USB-C 麥克風疑難排解](images/usbc-mic-4.png)

### <span data-ttu-id="c64a3-347">在 Kiosk 模式中使用新的設定和 Edge 應用程式</span><span class="sxs-lookup"><span data-stu-id="c64a3-347">Use the new Settings and Edge apps in Kiosk modes</span></span>

<span data-ttu-id="c64a3-348">在 [Kiosks](hololens-kiosk.md)中加入應用程式時，IT 系統管理員通常會將應用程式新增到 Kiosk，但使用其應用程式使用者模型識別碼 (AUMID) 。</span><span class="sxs-lookup"><span data-stu-id="c64a3-348">When including apps in [Kiosks](hololens-kiosk.md), an IT Admin often adds the app to the Kiosk but using it's App User Model ID (AUMID).</span></span> <span data-ttu-id="c64a3-349">因為設定應用程式和 Microsoft Edge 應用程式都視為新的應用程式，而且與那些應用程式使用 AUMIDs 的舊版 App Kiosk 不同，因此必須更新以使用新的 AUMID。</span><span class="sxs-lookup"><span data-stu-id="c64a3-349">Because both the Settings app and Microsoft Edge app are considered new apps and different than the older apps Kiosks that use AUMIDs for those apps will need to be updated to use the new AUMID.</span></span>

<span data-ttu-id="c64a3-350">修改 Kiosk 以包含新 App 時，我們建議您新增新 AUMID，以及離開舊的 AUMID。</span><span class="sxs-lookup"><span data-stu-id="c64a3-350">When modifying a Kiosk to include the new apps, we recommend adding in the new AUMID as well as leaving the old one.</span></span> <span data-ttu-id="c64a3-351">這可讓使用者在更新作業系統時輕鬆進行轉換，而且不需要收到新政策，就如預期一樣持續使用 Kiosk。</span><span class="sxs-lookup"><span data-stu-id="c64a3-351">This will create an easy transition when users update the OS and won't need to receive new policies to keep using the Kiosk as intended.</span></span>

| <span data-ttu-id="c64a3-352">應用程式</span><span class="sxs-lookup"><span data-stu-id="c64a3-352">App</span></span>                    | <span data-ttu-id="c64a3-353">AUMID</span><span class="sxs-lookup"><span data-stu-id="c64a3-353">AUMID</span></span>                                                  |
|------------------------|--------------------------------------------------------|
| <span data-ttu-id="c64a3-354">舊設定應用程式</span><span class="sxs-lookup"><span data-stu-id="c64a3-354">Old Settings App</span></span>       | <span data-ttu-id="c64a3-355">HolographicSystemSettings_cw5n1h2txyewy！應用程式</span><span class="sxs-lookup"><span data-stu-id="c64a3-355">HolographicSystemSettings_cw5n1h2txyewy!App</span></span>            |
| <span data-ttu-id="c64a3-356">新增設定應用程式</span><span class="sxs-lookup"><span data-stu-id="c64a3-356">New Settings App</span></span>       | <span data-ttu-id="c64a3-357">BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy！應用程式</span><span class="sxs-lookup"><span data-stu-id="c64a3-357">BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App</span></span> |
| <span data-ttu-id="c64a3-358">舊的 Microsoft Edge 應用程式</span><span class="sxs-lookup"><span data-stu-id="c64a3-358">Old Microsoft Edge app</span></span> | <span data-ttu-id="c64a3-359">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span><span class="sxs-lookup"><span data-stu-id="c64a3-359">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span></span>    |
| <span data-ttu-id="c64a3-360">新的 Microsoft Edge 應用程式</span><span class="sxs-lookup"><span data-stu-id="c64a3-360">New Microsoft Edge app</span></span> | <span data-ttu-id="c64a3-361">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE</span><span class="sxs-lookup"><span data-stu-id="c64a3-361">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE</span></span>    |

### <span data-ttu-id="c64a3-362">頁面設定可見度的新設定URIS</span><span class="sxs-lookup"><span data-stu-id="c64a3-362">New SettingsURIs for Page Settings Visibility</span></span>

<span data-ttu-id="c64a3-363">在 [Windows 全攝影版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 中，我們新增 [了設定/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) 政策，以限制在設定應用程式內看到的頁面。</span><span class="sxs-lookup"><span data-stu-id="c64a3-363">In [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) we added the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="c64a3-364">PageVisibilityList 為一種原則，可讓 IT 系統管理員禁止顯示或存取 [系統設定] 應用程式中的特定頁面，或對特定頁面外的所有頁面執行此動作。</span><span class="sxs-lookup"><span data-stu-id="c64a3-364">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

<span data-ttu-id="c64a3-365">如果您流覽 [頁面設定可見度](settings-uri-list.md)，您可以找到使用此 CSP 的指示，以及先前版本中提供的 URI 清單。</span><span class="sxs-lookup"><span data-stu-id="c64a3-365">If you visit [Page Settings Visibility](settings-uri-list.md), you can find instructions to use this CSP and the list of URIs available in previous releases.</span></span>

<span data-ttu-id="c64a3-366">在 Windows 測試人員建立中，我們正在展開可用的設定 URI 清單清單，IT 系統管理員可以管理該清單。</span><span class="sxs-lookup"><span data-stu-id="c64a3-366">In Windows Insider builds we are expanding upon the list of list of available Settings URIs, which IT Admins can manage.</span></span> <span data-ttu-id="c64a3-367">其中一些 URI 適用于新設定應用程式內的新可用區域。</span><span class="sxs-lookup"><span data-stu-id="c64a3-367">Some of these URIs are for newly available areas within the new Settings app.</span></span> <span data-ttu-id="c64a3-368">如果您使用的是設定/PageVisibilityList 策略，請查閱下列清單，並根據需要調整允許或封鎖的頁面。</span><span class="sxs-lookup"><span data-stu-id="c64a3-368">If you are using Settings/PageVisibilityList policy, review the following list and adjust your allowed or blocked pages as needed.</span></span>

> [!NOTE]
> **<span data-ttu-id="c64a3-369">已替代：ms-settings：network-Proxy</span><span class="sxs-lookup"><span data-stu-id="c64a3-369">Deprecated: ms-settings:network-proxy</span></span>**
>
> <span data-ttu-id="c64a3-370">在這些較新的版本內，有一個設定頁面已由它所替代。</span><span class="sxs-lookup"><span data-stu-id="c64a3-370">One settings page is deprecated in these newer builds.</span></span> <span data-ttu-id="c64a3-371">已不再**提供&** Internet  >  **Proxy**頁面做為全域設定。</span><span class="sxs-lookup"><span data-stu-id="c64a3-371">The old **Network & Internet** > **Proxy** page is no longer available as a global setting.</span></span> <span data-ttu-id="c64a3-372">您可以在 Network & **Internet**  >  **Wi-Fi**屬性或網際網路乙太網路屬性&找到新的每  >  \*\* \*\* **&**  >  \*\*\*\*  >  **設定**。</span><span class="sxs-lookup"><span data-stu-id="c64a3-372">The new per-connection proxy settings can be found under **Network & Internet** > **Wi-Fi** > **Properties** or **Network & Internet** > **Ethernet** > **Properties**.</span></span>

<br>

| <span data-ttu-id="c64a3-373">設定頁面</span><span class="sxs-lookup"><span data-stu-id="c64a3-373">Settings page</span></span>                                        | <span data-ttu-id="c64a3-374">URI</span><span class="sxs-lookup"><span data-stu-id="c64a3-374">URI</span></span>                                              |
|------------------------------------------------------|--------------------------------------------------|
| <span data-ttu-id="c64a3-375">應用程式>應用程式&功能</span><span class="sxs-lookup"><span data-stu-id="c64a3-375">Apps > Apps & features</span></span>                               | `ms-settings:appsfeatures`                         |
| <span data-ttu-id="c64a3-376">應用程式>應用程式&進>選項的功能</span><span class="sxs-lookup"><span data-stu-id="c64a3-376">Apps > Apps & features > Advanced options</span></span>          | `ms-settings:appsfeatures-app`                     |
| <span data-ttu-id="c64a3-377">離線>應用程式</span><span class="sxs-lookup"><span data-stu-id="c64a3-377">Apps > Offline maps</span></span>                                  | `ms-settings:maps`                                 |
| <span data-ttu-id="c64a3-378">離線>應用程式>下載地圖</span><span class="sxs-lookup"><span data-stu-id="c64a3-378">Apps > Offline maps > Download maps</span></span>                  | `ms-settings:maps-downloadmaps`                    |
| <span data-ttu-id="c64a3-379">使用滑鼠>裝置</span><span class="sxs-lookup"><span data-stu-id="c64a3-379">Devices > Mouse</span></span>                                      | `ms-settings:mouse`                                |
| <span data-ttu-id="c64a3-380">USB >裝置</span><span class="sxs-lookup"><span data-stu-id="c64a3-380">Devices > USB</span></span>                                        | `ms-settings:usb`                                  |
| <span data-ttu-id="c64a3-381">網路&網際網路>飛航模式</span><span class="sxs-lookup"><span data-stu-id="c64a3-381">Network & Internet > Airplane mode</span></span>                   | `ms-settings:network-airplanemode`                 |
| <span data-ttu-id="c64a3-382">隱私權>一般</span><span class="sxs-lookup"><span data-stu-id="c64a3-382">Privacy > General</span></span>                                    | `ms-settings:privacy-general`                      |
| <span data-ttu-id="c64a3-383">輸入>筆&隱私權</span><span class="sxs-lookup"><span data-stu-id="c64a3-383">Privacy > Ink & typing personalization</span></span>             | `ms-settings:privacy-speechtyping`                 |
| <span data-ttu-id="c64a3-384">隱私權>動作</span><span class="sxs-lookup"><span data-stu-id="c64a3-384">Privacy > Motion</span></span>                                     | `ms-settings:privacy-motion`                       |
| <span data-ttu-id="c64a3-385">隱私權>螢幕擷取畫面邊框</span><span class="sxs-lookup"><span data-stu-id="c64a3-385">Privacy > Screenshot borders</span></span>                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| <span data-ttu-id="c64a3-386">螢幕>與應用程式的隱私權</span><span class="sxs-lookup"><span data-stu-id="c64a3-386">Privacy > Screenshots and apps</span></span>                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| <span data-ttu-id="c64a3-387">系統>電池</span><span class="sxs-lookup"><span data-stu-id="c64a3-387">System > Battery</span></span>                                     | `ms-settings:batterysaver`                         |
| <span data-ttu-id="c64a3-388">系統>電池</span><span class="sxs-lookup"><span data-stu-id="c64a3-388">System > Battery</span></span>                                     | `ms-settings:batterysaver-settings`                |
| <span data-ttu-id="c64a3-389">系統>音效</span><span class="sxs-lookup"><span data-stu-id="c64a3-389">System > Sound</span></span>                                       | `ms-settings:sound`                                |
| <span data-ttu-id="c64a3-390">系統>音效> App 音量和裝置喜好設定</span><span class="sxs-lookup"><span data-stu-id="c64a3-390">System > Sound > App volume and device preferences</span></span> | `ms-settings:apps-volume`                          |
| <span data-ttu-id="c64a3-391">系統>音效>管理音效裝置</span><span class="sxs-lookup"><span data-stu-id="c64a3-391">System > Sound > Manage sound   devices</span></span>              | `ms-settings:sound-devices`                        |
| <span data-ttu-id="c64a3-392">系統>儲存空間>設定儲存感知</span><span class="sxs-lookup"><span data-stu-id="c64a3-392">System > Storage > Configure Storage Sense</span></span>         | `ms-settings:storagepolicies`                      |
| <span data-ttu-id="c64a3-393">語言&日期>時間&時間</span><span class="sxs-lookup"><span data-stu-id="c64a3-393">Time & Language > Date & time</span></span>                        | `ms-settings:dateandtime`                          |
| <span data-ttu-id="c64a3-394">語言&鍵盤>時間</span><span class="sxs-lookup"><span data-stu-id="c64a3-394">Time & Language > Keyboard</span></span>                           | `ms-settings:keyboard`                             |
| <span data-ttu-id="c64a3-395">語言&時間>語言</span><span class="sxs-lookup"><span data-stu-id="c64a3-395">Time & Language > Language</span></span>                           | `ms-settings:language`                             |
| <span data-ttu-id="c64a3-396">語言&時間>語言</span><span class="sxs-lookup"><span data-stu-id="c64a3-396">Time & Language > Language</span></span>                           | `ms-settings:regionlanguage-languageoptions`       |
| <span data-ttu-id="c64a3-397">更新&安全性>重&復原</span><span class="sxs-lookup"><span data-stu-id="c64a3-397">Update & Security > Reset & recovery</span></span>               | `ms-settings:reset`                                |

#### <span data-ttu-id="c64a3-398">更新的 URI</span><span class="sxs-lookup"><span data-stu-id="c64a3-398">Updated URIs</span></span>

<span data-ttu-id="c64a3-399">之前，下列兩個 URI 不會將使用者直接帶至指示的頁面，但只會封鎖主要更新頁面。</span><span class="sxs-lookup"><span data-stu-id="c64a3-399">Previously the following two URIs would not take a user directly to the pages indicated but only blocked the main updates page.</span></span> <span data-ttu-id="c64a3-400">下列專案已更新為直接顯示至其頁面：</span><span class="sxs-lookup"><span data-stu-id="c64a3-400">The following items have been updated to direct to their pages:</span></span>

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <span data-ttu-id="c64a3-401">資訊站模式行為變更處理失敗</span><span class="sxs-lookup"><span data-stu-id="c64a3-401">Kiosk mode behavior changes for handling of failures</span></span>

<span data-ttu-id="c64a3-402">在較舊的建立中，如果裝置有資訊站組式 ，這是全域指派的存取權和 AAD 群組成員指派存取權的組合，如果決定 AAD 群組成員資格失敗，使用者[](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)會看到「開始」功能表中沒有顯示任何內容。</span><span class="sxs-lookup"><span data-stu-id="c64a3-402">In older builds, if a device had a kiosk configuration, which is a combination of both global assigned access and AAD group member assigned access, if determining AAD group membership failed, the user would see “[nothing shown in start](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)” menu.</span></span>

<span data-ttu-id="c64a3-403">從 Windows 測試人員發行開始，如果 AAD 群組資訊站模式期間發生失敗 (資訊站) 資訊站體驗會備份到全域資訊站組配置。</span><span class="sxs-lookup"><span data-stu-id="c64a3-403">Starting in Windows Insider release, the kiosk experience will fallback to global kiosk configuration (if present) in case of failures during AAD group kiosk mode.</span></span>

### <span data-ttu-id="c64a3-404">透過設定應用程式設定後背診斷</span><span class="sxs-lookup"><span data-stu-id="c64a3-404">Configuring Fallback Diagnostics via Settings app</span></span>

<span data-ttu-id="c64a3-405">現在，在設定 App 中，使用者可以設定 [後背診斷的行為](hololens-diagnostic-logs.md)。</span><span class="sxs-lookup"><span data-stu-id="c64a3-405">Now in Settings App, a user can configure the behavior of [Fallback Diagnostics](hololens-diagnostic-logs.md).</span></span> <span data-ttu-id="c64a3-406">在設定應用程式中流覽至**隱私權**  ->  **疑難排解頁面**以設定此設定。</span><span class="sxs-lookup"><span data-stu-id="c64a3-406">In the Settings app navigate to **Privacy** -> **Troubleshooting** page to configure this setting.</span></span>

> [!NOTE]
> <span data-ttu-id="c64a3-407">如果有針對裝置所配置的 MDM 規則，使用者將無法覆蓋該行為。</span><span class="sxs-lookup"><span data-stu-id="c64a3-407">If there is MDM policy configured for the device, user will not be able to override that behavior.</span></span>  

### <span data-ttu-id="c64a3-408">與附近的裝置共用專案</span><span class="sxs-lookup"><span data-stu-id="c64a3-408">Share things with nearby devices</span></span>

<span data-ttu-id="c64a3-409">與 Windows 10 裝置附近共用專案，包括執行 HoloLens Insider builds 20279.1006+ 的 PC 和其他 HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="c64a3-409">Share things with near by Windows 10 devices, including both PCs and other HoloLens 2 devices running HoloLens Insider builds 20279.1006+.</span></span> <span data-ttu-id="c64a3-410">您可以在設定**系統共用體驗**中試用，以將 HoloLens 的檔案或  ->  \*\*\*\*  ->  \*\* \*\*URL 共用至電腦。</span><span class="sxs-lookup"><span data-stu-id="c64a3-410">You can try it out in **Settings** -> **System** -> **Shared Experiences** to share files or URLs from a HoloLens to a PC.</span></span> <span data-ttu-id="c64a3-411">若要進一步閱讀詳細資料，請參閱如何在 [Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)中與附近的裝置共用專案。</span><span class="sxs-lookup"><span data-stu-id="c64a3-411">For more details read more about how to [Share things with nearby devices in Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).</span></span>

<span data-ttu-id="c64a3-412">此功能可透過 [Connectivity/AllowConnectedDevices 管理](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)。</span><span class="sxs-lookup"><span data-stu-id="c64a3-412">This feature can be managed via [Connectivity/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).</span></span>

### <span data-ttu-id="c64a3-413">新的 OS Update 疑難排解員</span><span class="sxs-lookup"><span data-stu-id="c64a3-413">New OS Update troubleshooter</span></span>

<span data-ttu-id="c64a3-414">除了設定應用程式中先前的疑難排解員之外，系統還加入了新的疑難排解員，並新增了 OS 更新的新設定應用程式。</span><span class="sxs-lookup"><span data-stu-id="c64a3-414">In addition to the previous troubleshooters within the Settings app, a new troubleshooter has been added with the addition of the new Settings app for OS Updates.</span></span> <span data-ttu-id="c64a3-415">流覽至**設定**  ->  **更新 &amp; 安全性**  ->  **疑難排解**  ->  **Windows Update，** 然後選取開始。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c64a3-415">Navigate to **Settings** -> **Update &amp; Security** -> **Troubleshoot** -> **Windows Update** and select **Start**.</span></span> <span data-ttu-id="c64a3-416">這可讓您在重現作業系統更新問題時收集追蹤，以協助您針對 IT 或支援進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="c64a3-416">This allows you to collect traces while reproducing your issue with OS Updates to assist better in troubleshooting with your IT or support.</span></span>

### <span data-ttu-id="c64a3-417">更新中的改良與修正：</span><span class="sxs-lookup"><span data-stu-id="c64a3-417">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="c64a3-418">[離線診斷](hololens-diagnostic-logs.md#offline-diagnostics) 也會包含序號和作業系統版本的其他裝置資訊。</span><span class="sxs-lookup"><span data-stu-id="c64a3-418">[Offline diagnostics](hololens-diagnostic-logs.md#offline-diagnostics) will also include additional device information for serial number and OS version.</span></span>






## <span data-ttu-id="c64a3-419">開始接收測試人員建立</span><span class="sxs-lookup"><span data-stu-id="c64a3-419">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="c64a3-420">如果您最近未更新，請重新開機裝置以更新狀態並取得最新版。</span><span class="sxs-lookup"><span data-stu-id="c64a3-420">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="c64a3-421">「重新開機裝置」語音命令運作正常。</span><span class="sxs-lookup"><span data-stu-id="c64a3-421">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="c64a3-422">您也可以選擇設定/Windows Insider Program 中的重新開機按鈕。</span><span class="sxs-lookup"><span data-stu-id="c64a3-422">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="c64a3-423">我們在後端遇到您可能會遇到的錯誤，這將會讓系統復原正軌。</span><span class="sxs-lookup"><span data-stu-id="c64a3-423">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="c64a3-424">在 HoloLens 2 裝置\*\*\*\* 上，& Windows 測試人員計畫的設定更新，然後  >  \*\*\*\*  >  \*\*\*\* 選取開始。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c64a3-424">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="c64a3-425">連結您用來註冊為 Windows Insider 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="c64a3-425">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="c64a3-426">Windows Insider 目前正在移往頻道。</span><span class="sxs-lookup"><span data-stu-id="c64a3-426">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="c64a3-427">快速**通道**會變成**開發人員**通道，慢速通道會變成\*\*\*\*\*\*Beta**通道，而發行**預覽**通道將會變成**發行預覽通道\*\*。</span><span class="sxs-lookup"><span data-stu-id="c64a3-427">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="c64a3-428">以下是該地圖的外觀：</span><span class="sxs-lookup"><span data-stu-id="c64a3-428">Here is what that mapping looks like:</span></span>

![Windows Insider Channels 說明](images/WindowsInsiderChannels.png)

<span data-ttu-id="c64a3-430">詳細資訊請參閱 Windows 部落格 [上的 Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 介紹。</span><span class="sxs-lookup"><span data-stu-id="c64a3-430">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>

<span data-ttu-id="c64a3-431">然後，選取 **Windows 的主動**開發，選擇您是否要接收 **開發通道** 或 **Beta 通道** 版本，並審查計畫條款。</span><span class="sxs-lookup"><span data-stu-id="c64a3-431">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="c64a3-432">選取 **確認>立即重新開機** 以完成。</span><span class="sxs-lookup"><span data-stu-id="c64a3-432">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="c64a3-433">重新開機裝置之後，請>更新& **安全性>檢查更新** 以取得最新版。</span><span class="sxs-lookup"><span data-stu-id="c64a3-433">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

### <span data-ttu-id="c64a3-434">更新錯誤0x80070490處理</span><span class="sxs-lookup"><span data-stu-id="c64a3-434">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="c64a3-435">如果您在更新 Dev 或 Beta 0x80070490時遇到更新錯誤，請嘗試下列短期工作。</span><span class="sxs-lookup"><span data-stu-id="c64a3-435">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="c64a3-436">這涉及移動您的測試人員通道、選取更新，然後將您的測試人員通道移回。</span><span class="sxs-lookup"><span data-stu-id="c64a3-436">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>

#### <span data-ttu-id="c64a3-437">階段 1 - 發行預覽版</span><span class="sxs-lookup"><span data-stu-id="c64a3-437">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="c64a3-438">設定、更新&、Windows Insider Program、選取 **發行預覽通道**。</span><span class="sxs-lookup"><span data-stu-id="c64a3-438">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="c64a3-439">設定、更新&安全性、Windows **Update、檢查更新**。</span><span class="sxs-lookup"><span data-stu-id="c64a3-439">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="c64a3-440">更新之後，繼續進行階段 2。</span><span class="sxs-lookup"><span data-stu-id="c64a3-440">After the update, continue on to Stage two.</span></span>

#### <span data-ttu-id="c64a3-441">階段 2 - 開發人員通道</span><span class="sxs-lookup"><span data-stu-id="c64a3-441">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="c64a3-442">設定、更新&、Windows 測試人員計畫、選取 **開發人員通道**。</span><span class="sxs-lookup"><span data-stu-id="c64a3-442">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="c64a3-443">設定、更新&安全性、Windows **Update、檢查更新**。</span><span class="sxs-lookup"><span data-stu-id="c64a3-443">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>

## <span data-ttu-id="c64a3-444">FFU 下載和快速指示</span><span class="sxs-lookup"><span data-stu-id="c64a3-444">FFU download and flash directions</span></span>
<span data-ttu-id="c64a3-445">若要使用已簽署 Ffu 的班機測試，您首先必須先將裝置解除鎖定，才能閃爍已簽署之航班的 ffu。</span><span class="sxs-lookup"><span data-stu-id="c64a3-445">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="c64a3-446">在 PC 上：</span><span class="sxs-lookup"><span data-stu-id="c64a3-446">On PC:</span></span>

    1. <span data-ttu-id="c64a3-447">從 下載 ffu 到您的電腦 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。</span><span class="sxs-lookup"><span data-stu-id="c64a3-447">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="c64a3-448">從 Microsoft store (ARC) 進一步修復小夥伴 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) ：.</span><span class="sxs-lookup"><span data-stu-id="c64a3-448">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="c64a3-449">在 HoloLens - 航班解除鎖定 **：開啟設定**更新  >  **&**  >  **安全性 Windows 測試人員計畫**，然後註冊、重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="c64a3-449">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="c64a3-450">Flash FFU - 現在您可以使用 ARC 快速閃爍正式航班簽署的 FFU。</span><span class="sxs-lookup"><span data-stu-id="c64a3-450">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

## <span data-ttu-id="c64a3-451">提供意見回饋與報告問題</span><span class="sxs-lookup"><span data-stu-id="c64a3-451">Provide feedback and report issues</span></span>

<span data-ttu-id="c64a3-452">請使用 [HoloLens](hololens-feedback.md) 上的意見回饋中樞應用程式，提供意見回饋及報告問題。</span><span class="sxs-lookup"><span data-stu-id="c64a3-452">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="c64a3-453">使用意見中樞可確保包含所有必要的診斷資訊，協助我們的工程師快速進行診斷並解決問題。</span><span class="sxs-lookup"><span data-stu-id="c64a3-453">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="c64a3-454">中文版和日文版的 HoloLens 問題應該以相同方式報告。</span><span class="sxs-lookup"><span data-stu-id="c64a3-454">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="c64a3-455">請務必接受詢問您是否要意見回應中樞存取您的檔資料夾的提示， (系統提示時選取) 。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c64a3-455">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="c64a3-456">開發人員注意事項</span><span class="sxs-lookup"><span data-stu-id="c64a3-456">Note for developers</span></span>

<span data-ttu-id="c64a3-457">歡迎並鼓勵您嘗試使用 HoloLens 測試人員建立來開發您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="c64a3-457">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="c64a3-458">請參閱 [HoloLens 開發人員檔](https://developer.microsoft.com/windows/mixed-reality/development) 以開始使用。</span><span class="sxs-lookup"><span data-stu-id="c64a3-458">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="c64a3-459">這些相同的指示可與 HoloLens 測試人員建立一起使用。</span><span class="sxs-lookup"><span data-stu-id="c64a3-459">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="c64a3-460">您可以使用與 HoloLens 開發中一樣使用的同一個單一和 Visual Studio 版本。</span><span class="sxs-lookup"><span data-stu-id="c64a3-460">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <span data-ttu-id="c64a3-461">停止接收測試人員建立</span><span class="sxs-lookup"><span data-stu-id="c64a3-461">Stop receiving Insider builds</span></span>

<span data-ttu-id="c64a3-462">如果您不想再收到 Windows 全攝影版的測試人員版本，您可以選擇在 HoloLens 執行生產版時退出，或者您可以使用進一步[](hololens-recovery.md)修復小夥伴復原您的裝置，將裝置復原為非測試人員版本的 Windows 全攝影版。</span><span class="sxs-lookup"><span data-stu-id="c64a3-462">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="c64a3-463">有一個已知問題，在手動重新安裝全新預覽版之後，從 Insider Preview 建立取消註冊的使用者，會遇到藍色畫面。</span><span class="sxs-lookup"><span data-stu-id="c64a3-463">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="c64a3-464">之後，他們必須手動復原裝置。</span><span class="sxs-lookup"><span data-stu-id="c64a3-464">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="c64a3-465">如需有關您是否會受到影響的完整詳細資料，請進一步查看此 [已知問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)。</span><span class="sxs-lookup"><span data-stu-id="c64a3-465">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="c64a3-466">若要確認您的 HoloLens 正在進行生產建立：</span><span class="sxs-lookup"><span data-stu-id="c64a3-466">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="c64a3-467">請前往 **系統>的>，** 並尋找建組編號。</span><span class="sxs-lookup"><span data-stu-id="c64a3-467">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="c64a3-468">[請參閱生產版組號版本資訊](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="c64a3-468">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="c64a3-469">若要退出測試人員建立：</span><span class="sxs-lookup"><span data-stu-id="c64a3-469">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="c64a3-470">在執行生產建制的 HoloLens 上，> Windows 測試人員計畫 **&更新>，** 然後選取停止測試人員 **建立**。</span><span class="sxs-lookup"><span data-stu-id="c64a3-470">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="c64a3-471">請遵循指示退出宣告您的裝置。</span><span class="sxs-lookup"><span data-stu-id="c64a3-471">Follow the instructions to opt out your device.</span></span>
