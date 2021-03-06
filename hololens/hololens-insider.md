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
ms.date: 3/4/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 7c11dfbdb78e59493d648fb3a172d3e1f73048c8
ms.sourcegitcommit: 07ffe1bf2f45dcb2ba9d7fbe54b4773a0fb9d525
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393877"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="0ed36-103">適用於 Microsoft HoloLens 的 Insider Preview</span><span class="sxs-lookup"><span data-stu-id="0ed36-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="0ed36-104">歡迎使用 HoloLens 的最新 Insider Preview 版本！</span><span class="sxs-lookup"><span data-stu-id="0ed36-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="0ed36-105">開始使用非常簡單，並為[](hololens-insider.md#start-receiving-insider-builds)HoloLens 的下一個主要作業系統更新提供寶貴的意見。</span><span class="sxs-lookup"><span data-stu-id="0ed36-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="0ed36-106">Windows Insider Release Notes</span><span class="sxs-lookup"><span data-stu-id="0ed36-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="0ed36-107">我們很高興能再次開始向 Windows Insider 提供新功能。</span><span class="sxs-lookup"><span data-stu-id="0ed36-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="0ed36-108">新版將會測試到 Dev 通道，以尋找最新的更新。</span><span class="sxs-lookup"><span data-stu-id="0ed36-108">New builds will be flighting to the Dev Channel for the latest updates.</span></span> <span data-ttu-id="0ed36-109">隨著我們新增更多功能與更新至我們的 Windows 測試人員版本，我們會持續更新此頁面。</span><span class="sxs-lookup"><span data-stu-id="0ed36-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span>  <span data-ttu-id="0ed36-110">期待並準備好將這些更新混合到您的實境中。</span><span class="sxs-lookup"><span data-stu-id="0ed36-110">Get excited and ready to mix these updates into your reality.</span></span>

<span data-ttu-id="0ed36-111">這項功能更新包含兩個目標物件的功能。</span><span class="sxs-lookup"><span data-stu-id="0ed36-111">This feature update contains features for two target audiences.</span></span> <span data-ttu-id="0ed36-112">使用者可在裝置上使用的功能，以及 IT 系統管理員可配置的新裝置管理選項。</span><span class="sxs-lookup"><span data-stu-id="0ed36-112">Features that can be used by anyone on a device by the end user, and new device management options that can be configured by IT Admins.</span></span> <span data-ttu-id="0ed36-113">下方功能表格會說明哪些物件能夠使用每項新功能。</span><span class="sxs-lookup"><span data-stu-id="0ed36-113">The feature table below specifics the audiences with who be able to use each new feature.</span></span> <span data-ttu-id="0ed36-114">如果您是 IT 系統管理員，請查看我們的 IT 系統管理員 [- 更新檢查清單](#it-admin---update-checklist)</span><span class="sxs-lookup"><span data-stu-id="0ed36-114">If you are an IT Admin, please take a look at our [IT Admin - Update Checklist](#it-admin---update-checklist)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ed36-115">如果您先前在 Kiosk 中曾使用設定 App 或 Microsoft Edge 應用程式，我們已將這些應用程式取代為使用不同的應用程式識別碼的新應用程式。</span><span class="sxs-lookup"><span data-stu-id="0ed36-115">If you were previously using either the Settings app or Microsoft Edge app in a Kiosk, we have replaced these apps with new apps which use a different App ID.</span></span> <span data-ttu-id="0ed36-116">我們強烈建議您閱讀以下資訊站模式中新[App 的新 AUMIDS。](#use-the-new-settings-and-edge-apps-in-kiosk-modes)</span><span class="sxs-lookup"><span data-stu-id="0ed36-116">We highly encourage you to read [New AUMIDs for new apps in Kiosk mode](#use-the-new-settings-and-edge-apps-in-kiosk-modes) below.</span></span> <span data-ttu-id="0ed36-117">這可確保您繼續擁有 Kiosk 中的設定應用程式，或包含新的 Microsoft Edge 應用程式。</span><span class="sxs-lookup"><span data-stu-id="0ed36-117">This will ensure you either continue to have the Settings app in your Kiosk, or include the new Microsoft Edge app.</span></span>

<br>

| <span data-ttu-id="0ed36-118">功能名稱</span><span class="sxs-lookup"><span data-stu-id="0ed36-118">Feature Name</span></span>                                              | <span data-ttu-id="0ed36-119">簡短描述</span><span class="sxs-lookup"><span data-stu-id="0ed36-119">Short description</span></span>                                                                      | <span data-ttu-id="0ed36-120">目標物件</span><span class="sxs-lookup"><span data-stu-id="0ed36-120">Target Audience</span></span> | <span data-ttu-id="0ed36-121">可在建立中使用</span><span class="sxs-lookup"><span data-stu-id="0ed36-121">Available in build</span></span> |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|------|
| [<span data-ttu-id="0ed36-122">新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0ed36-122">New Microsoft Edge</span></span>](#introducing-the-new-microsoft-edge) | <span data-ttu-id="0ed36-123">新的 Chromium 型 Microsoft Edge 現已適用于 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="0ed36-123">The new, Chromium-based Microsoft Edge is now available for HoloLens 2</span></span>                         | <span data-ttu-id="0ed36-124">使用者</span><span class="sxs-lookup"><span data-stu-id="0ed36-124">End User</span></span> | <span data-ttu-id="0ed36-125">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0ed36-125">20279.1006</span></span> |
| [<span data-ttu-id="0ed36-126">WebXR 和 360 Viewer</span><span class="sxs-lookup"><span data-stu-id="0ed36-126">WebXR and 360 Viewer</span></span>](#webxr-and-360-viewer)             | <span data-ttu-id="0ed36-127">嘗試沉浸式網頁體驗和 360 影片播放</span><span class="sxs-lookup"><span data-stu-id="0ed36-127">Try immersive web experiences and 360 video playback</span></span>                                           | <span data-ttu-id="0ed36-128">使用者</span><span class="sxs-lookup"><span data-stu-id="0ed36-128">End User</span></span> | <span data-ttu-id="0ed36-129">20289.1000</span><span class="sxs-lookup"><span data-stu-id="0ed36-129">20289.1000</span></span> |
| [<span data-ttu-id="0ed36-130">新增設定應用程式</span><span class="sxs-lookup"><span data-stu-id="0ed36-130">New Settings app</span></span>](#new-settings-app)                     | <span data-ttu-id="0ed36-131">舊版的設定應用程式正由更新的版本取代為新功能和設定</span><span class="sxs-lookup"><span data-stu-id="0ed36-131">The legacy Settings app is being replaced by an updated version with new features and settings</span></span> | <span data-ttu-id="0ed36-132">使用者</span><span class="sxs-lookup"><span data-stu-id="0ed36-132">End User</span></span> | <span data-ttu-id="0ed36-133">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0ed36-133">20279.1006</span></span> |
| [<span data-ttu-id="0ed36-134">顯示色彩校正</span><span class="sxs-lookup"><span data-stu-id="0ed36-134">Display color calibration</span></span>](#display-color-calibration)   | <span data-ttu-id="0ed36-135">選取 HoloLens 2 顯示器的替代色彩設定檔</span><span class="sxs-lookup"><span data-stu-id="0ed36-135">Select an alternative color profile for your HoloLens 2 display</span></span>                                | <span data-ttu-id="0ed36-136">使用者</span><span class="sxs-lookup"><span data-stu-id="0ed36-136">End User</span></span> | <span data-ttu-id="0ed36-137">20293.1000</span><span class="sxs-lookup"><span data-stu-id="0ed36-137">20293.1000</span></span> |
| [<span data-ttu-id="0ed36-138">預設應用程式選擇器</span><span class="sxs-lookup"><span data-stu-id="0ed36-138">Default app picker</span></span>](#default-app-picker)                 | <span data-ttu-id="0ed36-139">選擇每個檔案或連結類型應啟動的應用程式</span><span class="sxs-lookup"><span data-stu-id="0ed36-139">Choose which app should launch for each file or link type</span></span>                                      | <span data-ttu-id="0ed36-140">使用者</span><span class="sxs-lookup"><span data-stu-id="0ed36-140">End User</span></span> | <span data-ttu-id="0ed36-141">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0ed36-141">20279.1006</span></span> |
| [<span data-ttu-id="0ed36-142">每個 App 音量控制</span><span class="sxs-lookup"><span data-stu-id="0ed36-142">Per app volume control</span></span>](#per-app-volume-control) |  <span data-ttu-id="0ed36-143">與系統音量無關控制應用程式層級音量</span><span class="sxs-lookup"><span data-stu-id="0ed36-143">Control app level volume independently from system volume</span></span> | <span data-ttu-id="0ed36-144">使用者</span><span class="sxs-lookup"><span data-stu-id="0ed36-144">End User</span></span> | <span data-ttu-id="0ed36-145">20293.1000</span><span class="sxs-lookup"><span data-stu-id="0ed36-145">20293.1000</span></span> |
| [<span data-ttu-id="0ed36-146">Office Web App</span><span class="sxs-lookup"><span data-stu-id="0ed36-146">Office web app</span></span>](#office-web-app)                         | <span data-ttu-id="0ed36-147">Office Web App 的快捷方式現在會列在 「所有應用程式」中</span><span class="sxs-lookup"><span data-stu-id="0ed36-147">A shortcut to the Office web app is now listed in "All apps"</span></span>                                   | <span data-ttu-id="0ed36-148">使用者</span><span class="sxs-lookup"><span data-stu-id="0ed36-148">End User</span></span> | <span data-ttu-id="0ed36-149">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0ed36-149">20279.1006</span></span> |
| [<span data-ttu-id="0ed36-150">滑動以輸入</span><span class="sxs-lookup"><span data-stu-id="0ed36-150">Swipe to type</span></span>](#swipe-to-type)                           | <span data-ttu-id="0ed36-151">使用手指的提示在全攝影鍵盤上「滑動」文字</span><span class="sxs-lookup"><span data-stu-id="0ed36-151">Use the tip of your finger to "swipe" words on the holographic keyboard</span></span>                        | <span data-ttu-id="0ed36-152">使用者</span><span class="sxs-lookup"><span data-stu-id="0ed36-152">End User</span></span> | <span data-ttu-id="0ed36-153">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0ed36-153">20279.1006</span></span> |
| [<span data-ttu-id="0ed36-154">從開始功能表的電源功能表</span><span class="sxs-lookup"><span data-stu-id="0ed36-154">Power menu from Start</span></span>](#power-menu-from-start) | <span data-ttu-id="0ed36-155">在開始功能表上，重新開機並關閉 HoloLens 裝置</span><span class="sxs-lookup"><span data-stu-id="0ed36-155">On Start Menu, restart and shut down HoloLens device</span></span> | <span data-ttu-id="0ed36-156">使用者</span><span class="sxs-lookup"><span data-stu-id="0ed36-156">End User</span></span> | <span data-ttu-id="0ed36-157">20293.1000</span><span class="sxs-lookup"><span data-stu-id="0ed36-157">20293.1000</span></span> |
| [<span data-ttu-id="0ed36-158">列在登錄畫面上的多個使用者</span><span class="sxs-lookup"><span data-stu-id="0ed36-158">Multiple users listed on Sign in screen</span></span>](#multiple-users-listed-on-sign-in-screen) | <span data-ttu-id="0ed36-159">在登錄畫面上顯示多個使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="0ed36-159">Display multiple user accounts on the Sign in screen</span></span> | <span data-ttu-id="0ed36-160">使用者</span><span class="sxs-lookup"><span data-stu-id="0ed36-160">End User</span></span> | <span data-ttu-id="0ed36-161">20293.1000</span><span class="sxs-lookup"><span data-stu-id="0ed36-161">20293.1000</span></span> |
| [<span data-ttu-id="0ed36-162">USB-C 外接麥克風支援</span><span class="sxs-lookup"><span data-stu-id="0ed36-162">USB-C External Microphone Support</span></span>](#usb-c-external-microphone-support) | <span data-ttu-id="0ed36-163">針對應用程式和/或遠端輔助使用 USB-C 麥克風。</span><span class="sxs-lookup"><span data-stu-id="0ed36-163">Use USB-C microphones for apps and / or Remote Assist.</span></span>| <span data-ttu-id="0ed36-164">使用者</span><span class="sxs-lookup"><span data-stu-id="0ed36-164">End User</span></span> | <span data-ttu-id="0ed36-165">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0ed36-165">20279.1006</span></span> |
| [<span data-ttu-id="0ed36-166">資訊站的訪客自動登入</span><span class="sxs-lookup"><span data-stu-id="0ed36-166">Visitor Auto-logon for Kiosks</span></span>](#visitor-auto-logon-for-kiosks)                          | <span data-ttu-id="0ed36-167">啟用訪客帳戶的自動登入，以用於 Kiosk 模式。</span><span class="sxs-lookup"><span data-stu-id="0ed36-167">Enables the auto-logon on Visitor accounts to be used for Kiosk modes.</span></span>                         | <span data-ttu-id="0ed36-168">IT 系統管理員</span><span class="sxs-lookup"><span data-stu-id="0ed36-168">IT Admin</span></span> | <span data-ttu-id="0ed36-169">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0ed36-169">20279.1006</span></span>                 |
| [<span data-ttu-id="0ed36-170">Kiosk 模式中新 App 的新 AUMID</span><span class="sxs-lookup"><span data-stu-id="0ed36-170">New AUMIDs for new apps in Kiosk mode</span></span>](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | <span data-ttu-id="0ed36-171">適用于新設定和 Edge 應用程式的 AUMIDs</span><span class="sxs-lookup"><span data-stu-id="0ed36-171">AUMIDs for new Settings and Edge apps</span></span> | <span data-ttu-id="0ed36-172">IT 系統管理員</span><span class="sxs-lookup"><span data-stu-id="0ed36-172">IT Admin</span></span> | <span data-ttu-id="0ed36-173">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0ed36-173">20279.1006</span></span> |
| [<span data-ttu-id="0ed36-174">改良的 Kiosk 模式失敗交還</span><span class="sxs-lookup"><span data-stu-id="0ed36-174">Improved Kiosk mode failure handing</span></span>](#kiosk-mode-behavior-changes-for-handling-of-failures) | <span data-ttu-id="0ed36-175">Kiosk 模式會先尋找全域指派的 Access，再尋找空白的開始功能表。</span><span class="sxs-lookup"><span data-stu-id="0ed36-175">Kiosk mode looks for Global Assigned Access before empty start menu.</span></span> | <span data-ttu-id="0ed36-176">IT 系統管理員</span><span class="sxs-lookup"><span data-stu-id="0ed36-176">IT Admin</span></span> | <span data-ttu-id="0ed36-177">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0ed36-177">20279.1006</span></span> |
| [<span data-ttu-id="0ed36-178">頁面設定可見度的新設定URIS</span><span class="sxs-lookup"><span data-stu-id="0ed36-178">New SettingsURIs for Page Settings Visibility</span></span>](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | <span data-ttu-id="0ed36-179">20+ 個新的 SettingsURIs for Settings/PageVisibilityList policy</span><span class="sxs-lookup"><span data-stu-id="0ed36-179">20+ new SettingsURIs for Settings/PageVisibilityList policy</span></span> | <span data-ttu-id="0ed36-180">IT 系統管理員</span><span class="sxs-lookup"><span data-stu-id="0ed36-180">IT Admin</span></span> | <span data-ttu-id="0ed36-181">20289.1000</span><span class="sxs-lookup"><span data-stu-id="0ed36-181">20289.1000</span></span> |
| [<span data-ttu-id="0ed36-182">設定後背診斷</span><span class="sxs-lookup"><span data-stu-id="0ed36-182">Configure Fallback Diagnostics</span></span>](#configuring-fallback-diagnostics-via-settings-app) | <span data-ttu-id="0ed36-183">在設定應用程式中設定後背診斷行為</span><span class="sxs-lookup"><span data-stu-id="0ed36-183">Setting Fallback Diagnostic Behavior in Settings App</span></span> | <span data-ttu-id="0ed36-184">IT 系統管理員</span><span class="sxs-lookup"><span data-stu-id="0ed36-184">IT Admin</span></span> | <span data-ttu-id="0ed36-185">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0ed36-185">20279.1006</span></span> |
| [<span data-ttu-id="0ed36-186">與附近的裝置共用專案</span><span class="sxs-lookup"><span data-stu-id="0ed36-186">Share things with nearby devices</span></span>](#share-things-with-nearby-devices) | <span data-ttu-id="0ed36-187">從 HoloLens 共用檔案或 URL 到電腦</span><span class="sxs-lookup"><span data-stu-id="0ed36-187">Share files or URLs from a HoloLens to a PC</span></span> | <span data-ttu-id="0ed36-188">全部</span><span class="sxs-lookup"><span data-stu-id="0ed36-188">All</span></span> | <span data-ttu-id="0ed36-189">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0ed36-189">20279.1006</span></span> |
| [<span data-ttu-id="0ed36-190">新的 OS Update 疑難排解員</span><span class="sxs-lookup"><span data-stu-id="0ed36-190">New OS Update troubleshooter</span></span>](#new-os-update-troubleshooter) | <span data-ttu-id="0ed36-191">作業系統更新設定中的新疑難排解員</span><span class="sxs-lookup"><span data-stu-id="0ed36-191">New troubleshooter in Settings for OS updates</span></span> | <span data-ttu-id="0ed36-192">IT 系統管理員</span><span class="sxs-lookup"><span data-stu-id="0ed36-192">IT Admin</span></span> | <span data-ttu-id="0ed36-193">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0ed36-193">20279.1006</span></span> |
| [<span data-ttu-id="0ed36-194">傳遞優化預覽</span><span class="sxs-lookup"><span data-stu-id="0ed36-194">Delivery Optimization Preview</span></span>](#delivery-optimization-preview) | <span data-ttu-id="0ed36-195">減少從多個 HoloLens 裝置下載的頻寬耗用</span><span class="sxs-lookup"><span data-stu-id="0ed36-195">Reduce bandwidth consumption for downloads from multiple HoloLens devices</span></span> | <span data-ttu-id="0ed36-196">IT 系統管理員</span><span class="sxs-lookup"><span data-stu-id="0ed36-196">IT Admin</span></span> | <span data-ttu-id="0ed36-197">20301.1000</span><span class="sxs-lookup"><span data-stu-id="0ed36-197">20301.1000</span></span> |
| [<span data-ttu-id="0ed36-198">更新中的改良與修正</span><span class="sxs-lookup"><span data-stu-id="0ed36-198">Improvements and fixes in the update</span></span>](#improvements-and-fixes-in-the-update) | <span data-ttu-id="0ed36-199">更新中的其他修正。</span><span class="sxs-lookup"><span data-stu-id="0ed36-199">Additional fixes in the update.</span></span> | <span data-ttu-id="0ed36-200">全部</span><span class="sxs-lookup"><span data-stu-id="0ed36-200">All</span></span> | <span data-ttu-id="0ed36-201">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0ed36-201">20279.1006</span></span> |

### <a name="it-admin---update-checklist"></a><span data-ttu-id="0ed36-202">IT 系統管理員 - 更新檢查清單</span><span class="sxs-lookup"><span data-stu-id="0ed36-202">IT Admin - Update Checklist</span></span>

<span data-ttu-id="0ed36-203">這份檢查清單可協助您瞭解這項功能更新中新增的功能可能會影響您目前裝置管理配置的新功能，或您可能想要開始使用的新功能。</span><span class="sxs-lookup"><span data-stu-id="0ed36-203">This checklist will help you know the new items that features that are being added in this feature update that may affect your current device management configurations, or new features you might wish to start using.</span></span>

#### <a name="updates-to-kiosk-mode"></a><span data-ttu-id="0ed36-204">Kiosk 模式的更新</span><span class="sxs-lookup"><span data-stu-id="0ed36-204">Updates to Kiosk mode</span></span>

[**<span data-ttu-id="0ed36-205">Kiosk 模式中新 App 的新 AUMID</span><span class="sxs-lookup"><span data-stu-id="0ed36-205">New AUMIDs for new apps in Kiosk mode</span></span>**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

<span data-ttu-id="0ed36-206">如果您先前在 Kiosk 中曾使用設定 App 或 Microsoft Edge 應用程式，我們已將這些應用程式取代為使用不同的應用程式識別碼的新應用程式。</span><span class="sxs-lookup"><span data-stu-id="0ed36-206">If you were previously using either the Settings app or Microsoft Edge app in a Kiosk, we have replaced these apps with new apps which use a different App ID.</span></span> <span data-ttu-id="0ed36-207">我們強烈建議您閱讀以下資訊站模式中新[App 的新 AUMIDS。](#use-the-new-settings-and-edge-apps-in-kiosk-modes)</span><span class="sxs-lookup"><span data-stu-id="0ed36-207">We highly encourage you to read [New AUMIDs for new apps in Kiosk mode](#use-the-new-settings-and-edge-apps-in-kiosk-modes) below.</span></span> <span data-ttu-id="0ed36-208">這可確保您繼續擁有 Kiosk 中的設定應用程式，或包含新的 Microsoft Edge 應用程式。</span><span class="sxs-lookup"><span data-stu-id="0ed36-208">This will ensure you either continue to have the Settings app in your Kiosk, or include the new Microsoft Edge app.</span></span>

<span data-ttu-id="0ed36-209">這些變更可以立即完成，並部署到所有裝置，並可在更新時更順暢地轉換。</span><span class="sxs-lookup"><span data-stu-id="0ed36-209">These changes can be done now, and deployed to all devices and allow for a smoother transition on update.</span></span>

[**<span data-ttu-id="0ed36-210">資訊站的訪客自動登入</span><span class="sxs-lookup"><span data-stu-id="0ed36-210">Visitor Auto-logon for Kiosks</span></span>**](#visitor-auto-logon-for-kiosks)

<span data-ttu-id="0ed36-211">訪客現在可以自動登入 Kiosk。</span><span class="sxs-lookup"><span data-stu-id="0ed36-211">Visitors can now be automatically logged into a Kiosk.</span></span> <span data-ttu-id="0ed36-212">此行為預設為啟用，但可以管理並停用。</span><span class="sxs-lookup"><span data-stu-id="0ed36-212">This behavior is on by default but can be managed and disabled.</span></span>

[**<span data-ttu-id="0ed36-213">改良的 Kiosk 模式失敗交還</span><span class="sxs-lookup"><span data-stu-id="0ed36-213">Improved Kiosk mode failure handing</span></span>**](#kiosk-mode-behavior-changes-for-handling-of-failures)

<span data-ttu-id="0ed36-214">此更新現在讓裝置受到 Kiosk 模式的控制，允許它回到不同類型的 Kiosk，然後再展示空白的 Kiosk。</span><span class="sxs-lookup"><span data-stu-id="0ed36-214">This update now keeps devices more controlled by Kiosk mode, allowing for it to fall back to different types of Kiosks before simply presenting an empty Kiosk.</span></span> <span data-ttu-id="0ed36-215">雖然這無法管理，但如果您以可能適用于您的組配置的方式使用 Kiosk，這可能會告知您的支援部門。</span><span class="sxs-lookup"><span data-stu-id="0ed36-215">While this is not manageable, this may be something to inform your support department if you are using Kiosks in a way this may apply to your configuration.</span></span>

#### <a name="updates-to-page-settings-visibility"></a><span data-ttu-id="0ed36-216">頁面設定可見度更新</span><span class="sxs-lookup"><span data-stu-id="0ed36-216">Updates to Page Settings Visibility</span></span>

[**<span data-ttu-id="0ed36-217">頁面設定可見度的新設定URIS</span><span class="sxs-lookup"><span data-stu-id="0ed36-217">New SettingsURIs for Page Settings Visibility</span></span>**](hololens-insider.md#new-settingsuris-for-page-settings-visibility)

<span data-ttu-id="0ed36-218">如果您目前使用頁面 [設定可見度](settings-uri-list.md) ，您可能會想要調整您允許或封鎖的現有 URI。</span><span class="sxs-lookup"><span data-stu-id="0ed36-218">IF you are currently using [Page Settings Visibility](settings-uri-list.md) then you may wish to make adjustments to your existing URIs you have either allowed or blocked.</span></span>

#### <a name="updates-for-your-wdac-policy"></a><span data-ttu-id="0ed36-219">WDAC 策略的更新</span><span class="sxs-lookup"><span data-stu-id="0ed36-219">Updates for your WDAC policy</span></span>

<span data-ttu-id="0ed36-220">如果您先前曾透過 WDAC 封鎖 Microsoft Edge，您將要更新您的 WDAC 政策。</span><span class="sxs-lookup"><span data-stu-id="0ed36-220">If you were previously blocking Microsoft Edge via WDAC, you'll want to update your WDAC policy.</span></span> <span data-ttu-id="0ed36-221">請 [查閱下列內容](#using-wdac-to-block-new-microsoft-edge) ，並使用提供的範例代碼。</span><span class="sxs-lookup"><span data-stu-id="0ed36-221">Please [review the following](#using-wdac-to-block-new-microsoft-edge) and use the sample code provided.</span></span>

#### <a name="newly-configurable-items"></a><span data-ttu-id="0ed36-222">新可配置的專案</span><span class="sxs-lookup"><span data-stu-id="0ed36-222">Newly configurable items</span></span>

- [<span data-ttu-id="0ed36-223">設定後背診斷</span><span class="sxs-lookup"><span data-stu-id="0ed36-223">Configure Fallback Diagnostics</span></span>](#configuring-fallback-diagnostics-via-settings-app)
  - <span data-ttu-id="0ed36-224">您可以設定是否收集及誰可能收集退後診斷。</span><span class="sxs-lookup"><span data-stu-id="0ed36-224">You may configure if and who may collect Fallback Diagnostics.</span></span>
- [<span data-ttu-id="0ed36-225">與附近的裝置共用專案</span><span class="sxs-lookup"><span data-stu-id="0ed36-225">Share things with nearby devices</span></span>](#share-things-with-nearby-devices)
  - <span data-ttu-id="0ed36-226">您可以停用附近的新共用功能。</span><span class="sxs-lookup"><span data-stu-id="0ed36-226">You may disable the new nearby sharing feature.</span></span>
- [<span data-ttu-id="0ed36-227">設定新 Microsoft Edge 的策略設定</span><span class="sxs-lookup"><span data-stu-id="0ed36-227">Configuring policy settings for the new Microsoft Edge</span></span>](#configuring-policy-settings-for-the-new-microsoft-edge)
  - <span data-ttu-id="0ed36-228">請閱閱 Microsoft Edge 提供的新組配置。</span><span class="sxs-lookup"><span data-stu-id="0ed36-228">Review the newly configurations available for Microsoft Edge.</span></span>

#### <a name="new-diagnostic-tool"></a><span data-ttu-id="0ed36-229">新的診斷工具</span><span class="sxs-lookup"><span data-stu-id="0ed36-229">New diagnostic tool</span></span>

- [<span data-ttu-id="0ed36-230">新的 OS Update 疑難排解員</span><span class="sxs-lookup"><span data-stu-id="0ed36-230">New OS Update troubleshooter</span></span>](#new-os-update-troubleshooter)
  - <span data-ttu-id="0ed36-231">收集與作業系統更新相關的記錄</span><span class="sxs-lookup"><span data-stu-id="0ed36-231">Collect logs related to OS Updates</span></span>

### <a name="introducing-the-new-microsoft-edge"></a><span data-ttu-id="0ed36-232">全新 Microsoft Edge 的介紹</span><span class="sxs-lookup"><span data-stu-id="0ed36-232">Introducing the new Microsoft Edge</span></span>

![將舊版 Microsoft Edge 標誌動畫新到新的 Microsoft Edge 標誌](images/new-edge.gif)

<span data-ttu-id="0ed36-234">新的 Microsoft Edge [採用 Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) 開放來源專案，為客戶建立更佳的相容性，以及減少網頁開發人員的網路分散程度。</span><span class="sxs-lookup"><span data-stu-id="0ed36-234">The new Microsoft Edge [adopts the Chromium open source project](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) to create better compatibility for customers and less fragmentation of the web for web developers.</span></span>

<span data-ttu-id="0ed36-235">有了此 Insider Preview，HoloLens 2 客戶第一次可以使用新的 Microsoft Edge！</span><span class="sxs-lookup"><span data-stu-id="0ed36-235">With this Insider preview, the new Microsoft Edge is available to HoloLens 2 customers for the first time!</span></span> <span data-ttu-id="0ed36-236">雖然新的 Microsoft Edge 最終會取代 HoloLens 2 上的舊版 Microsoft Edge，但測試人員目前可以使用這兩種瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="0ed36-236">While the new Microsoft Edge will eventually replace legacy Microsoft Edge on HoloLens 2, both browsers are currently available to Insiders.</span></span> <span data-ttu-id="0ed36-237">請透過新 Microsoft Edge 中的傳送\*\*\*\* 意見回饋功能，或透過意見回饋中心，與小組分享[意見和錯誤。](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="0ed36-237">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge or via [Feedback Hub](hololens-feedback.md).</span></span>

![新的 Microsoft Edge 螢幕擷取畫面](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a><span data-ttu-id="0ed36-239">啟動新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0ed36-239">Launching the new Microsoft Edge</span></span>

<span data-ttu-id="0ed36-240">測試人員可以使用兩個版本的 Microsoft Edge：新的 Microsoft Edge 新 Microsoft Edge 圖示 (以藍色和綠色旋轉圖示) 和舊版 Microsoft Edge (以白色 ![ ](images/new_edge_logo.png) "e" 圖示) 表示。</span><span class="sxs-lookup"><span data-stu-id="0ed36-240">There are two versions of Microsoft Edge available to Insiders: the new Microsoft Edge ![new Microsoft Edge icon](images/new_edge_logo.png) (represented by a blue and green swirl icon) and legacy Microsoft Edge (represented by the white "e" icon).</span></span> <span data-ttu-id="0ed36-241">新的 Microsoft Edge 已釘釘到開始功能表，且會在您啟用網頁連結時自動啟動。</span><span class="sxs-lookup"><span data-stu-id="0ed36-241">The new Microsoft Edge is pinned to the Start menu and will automatically launch when you activate a web link.</span></span> <span data-ttu-id="0ed36-242">如果您想要還原成使用舊版 Microsoft Edge 做為預設網頁瀏覽器，請參閱下列指示 [以重設預設應用程式](#default-app-picker)。</span><span class="sxs-lookup"><span data-stu-id="0ed36-242">If you would like to revert to using legacy Microsoft Edge as your default web browser, see the instructions below for [resetting default apps](#default-app-picker).</span></span>

> [!NOTE]
> <span data-ttu-id="0ed36-243">當您第一次在 HoloLens 2 上啟動新的 Microsoft Edge 時，您的設定和資料將會從舊版 Microsoft Edge 中匯出。</span><span class="sxs-lookup"><span data-stu-id="0ed36-243">When you first launch the new Microsoft Edge on HoloLens 2, your settings and data will be imported from legacy Microsoft Edge.</span></span> <span data-ttu-id="0ed36-244">如果您在啟動新的 Microsoft Edge 之後繼續使用舊版 Microsoft Edge，新資料將不會從舊版 Microsoft Edge 同步處理到新的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="0ed36-244">If you continue to use legacy Microsoft Edge after launching the new Microsoft Edge, that new data will not be synced from legacy Microsoft Edge to the new Microsoft Edge.</span></span>

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a><span data-ttu-id="0ed36-245">設定新 Microsoft Edge 的策略設定</span><span class="sxs-lookup"><span data-stu-id="0ed36-245">Configuring policy settings for the new Microsoft Edge</span></span>

<span data-ttu-id="0ed36-246">新的 Microsoft Edge 為 IT 系統管理員提供了一組更寬廣的 HoloLens 2 瀏覽器政策，比舊版 Microsoft Edge 提供的範圍更大。</span><span class="sxs-lookup"><span data-stu-id="0ed36-246">The new Microsoft Edge offers IT admins a much broader set of browser policies on HoloLens 2 than were previously available with legacy Microsoft Edge.</span></span>

<span data-ttu-id="0ed36-247">以下是一些實用的資源，可進一步學習管理新 Microsoft Edge 之策略設定：</span><span class="sxs-lookup"><span data-stu-id="0ed36-247">Here are some helpful resources for learning more about managing policy settings for the new Microsoft Edge:</span></span>

- [<span data-ttu-id="0ed36-248">使用 Microsoft Intune 設定 Microsoft Edge 原則設定</span><span class="sxs-lookup"><span data-stu-id="0ed36-248">Configure Microsoft Edge policy settings with Microsoft Intune</span></span>](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [<span data-ttu-id="0ed36-249">舊版 Microsoft Edge 與 Microsoft Edge 的原則對應</span><span class="sxs-lookup"><span data-stu-id="0ed36-249">Microsoft Edge Legacy to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [<span data-ttu-id="0ed36-250">Google Chrome 與 Microsoft Edge 的原則對應</span><span class="sxs-lookup"><span data-stu-id="0ed36-250">Google Chrome to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- <span data-ttu-id="0ed36-251">完整的 [Microsoft Edge Enterprise 檔](https://docs.microsoft.com/deployedge/)</span><span class="sxs-lookup"><span data-stu-id="0ed36-251">Full [Microsoft Edge Enterprise documentation](https://docs.microsoft.com/deployedge/)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ed36-252">由於新 Microsoft Edge 支援的瀏覽器策略量大，因此我們的小組無法保證每一個新策略都適用于 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="0ed36-252">Because of the volume of browser policies supported by the new Microsoft Edge, our team is unable to guarantee that each new policy works on HoloLens 2.</span></span> <span data-ttu-id="0ed36-253">不過，相及于新 Microsoft Edge 中先前在 HoloLens 2 上支援的每個舊版 Microsoft Edge 政策，我們已測試及確認其功能如預期。</span><span class="sxs-lookup"><span data-stu-id="0ed36-253">However, we've tested and confirmed than the new Microsoft Edge equivalent of each legacy Microsoft Edge policy previously supported on HoloLens 2 work as expected.</span></span> <span data-ttu-id="0ed36-254">請參閱 [Microsoft Edge 舊版與 Microsoft Edge 策略](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) 對應，以尋找與 HoloLens 2 一同使用之每個舊版 Microsoft Edge 瀏覽器政策的新 Microsoft Edge 對應。</span><span class="sxs-lookup"><span data-stu-id="0ed36-254">See [Microsoft Edge Legacy to Microsoft Edge policy mapping](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) to find the new Microsoft Edge equivalent of each legacy Microsoft Edge browser policy you were using with HoloLens 2.</span></span>
>
> <span data-ttu-id="0ed36-255">我們知道至少有兩個新的 Microsoft Edge 政策無法與\*\* HoloLens 2 一起使用：</span><span class="sxs-lookup"><span data-stu-id="0ed36-255">There are at least two new Microsoft Edge policies that we know *will not* work with HoloLens 2:</span></span>
> - <span data-ttu-id="0ed36-256">EnterpriseModeSiteList</span><span class="sxs-lookup"><span data-stu-id="0ed36-256">EnterpriseModeSiteList</span></span>
> - <span data-ttu-id="0ed36-257">EnterpriseSiteListServiceURL</span><span class="sxs-lookup"><span data-stu-id="0ed36-257">EnterpriseSiteListServiceURL</span></span>

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a><span data-ttu-id="0ed36-258">HoloLens 2 上新 Microsoft Edge 的預計功能</span><span class="sxs-lookup"><span data-stu-id="0ed36-258">What to expect from the new Microsoft Edge on HoloLens 2</span></span>

<span data-ttu-id="0ed36-259">由於新的 Microsoft Edge 是原生 Win32 應用程式，具有新的 UWP 介面卡層，允許它在 UWP 裝置上執行，例如 HoloLens 2，因此可能無法立即使用某些功能。</span><span class="sxs-lookup"><span data-stu-id="0ed36-259">Because the new Microsoft Edge is a native Win32 app with a new UWP adapter layer allowing it to run on UWP-only devices like HoloLens 2, some features may not be immediately available.</span></span> <span data-ttu-id="0ed36-260">我們將支援未來幾個月的新案例和功能，因此請查看此空間以尋找最新資訊。</span><span class="sxs-lookup"><span data-stu-id="0ed36-260">We'll be supporting new scenarios and features over the coming months, so check this space for up-to-date information.</span></span>

**<span data-ttu-id="0ed36-261">預期可得的情境和功能：</span><span class="sxs-lookup"><span data-stu-id="0ed36-261">Scenarios and features expected to work:</span></span>**
- <span data-ttu-id="0ed36-262">第一次執行體驗、登出設定檔，以及同步</span><span class="sxs-lookup"><span data-stu-id="0ed36-262">First-run experience, sign in to profile, and sync</span></span>
- <span data-ttu-id="0ed36-263">網站應呈現並如預期行為</span><span class="sxs-lookup"><span data-stu-id="0ed36-263">Websites should render and behave as expected</span></span>
- <span data-ttu-id="0ed36-264">大部分瀏覽器功能 (我的最愛、歷程記錄等) 應該會如預期地使用</span><span class="sxs-lookup"><span data-stu-id="0ed36-264">Most browser functionality (Favorites, History, etc.) should work as expected</span></span>
- <span data-ttu-id="0ed36-265">深色模式</span><span class="sxs-lookup"><span data-stu-id="0ed36-265">Dark mode</span></span>
- <span data-ttu-id="0ed36-266">將 Web App 安裝到裝置</span><span class="sxs-lookup"><span data-stu-id="0ed36-266">Installing web apps to the device</span></span>
- <span data-ttu-id="0ed36-267">安裝擴充 (請告知我們您是否使用任何在 HoloLens 2 或 HoloLens 2 上無法正常運作的) </span><span class="sxs-lookup"><span data-stu-id="0ed36-267">Installing extensions (please let us know if you use any extensions that don't work properly on HoloLens 2)</span></span>
- <span data-ttu-id="0ed36-268">檢視和標記 PDF</span><span class="sxs-lookup"><span data-stu-id="0ed36-268">Viewing and marking up a PDF</span></span>
- <span data-ttu-id="0ed36-269">單一瀏覽器視窗的空間音效</span><span class="sxs-lookup"><span data-stu-id="0ed36-269">Spatial sound from a single browser window</span></span>
- <span data-ttu-id="0ed36-270">瀏覽器的自動和手動更新</span><span class="sxs-lookup"><span data-stu-id="0ed36-270">Automatic and manual updating of the browser</span></span>
- <span data-ttu-id="0ed36-271">使用 「儲存至 PDF」選項 (從列印功能表儲存 PDF) </span><span class="sxs-lookup"><span data-stu-id="0ed36-271">Saving a PDF from the Print menu (using "Save to PDF" option)</span></span>
- <span data-ttu-id="0ed36-272">WebXR 和 360 Viewer 擴充功能</span><span class="sxs-lookup"><span data-stu-id="0ed36-272">WebXR and 360 Viewer extension</span></span>
- <span data-ttu-id="0ed36-273">當您流覽環境中多個視窗時，內容還原以修正視窗</span><span class="sxs-lookup"><span data-stu-id="0ed36-273">Content restoration to correct window, when browsing across multiple windows placed in your environment</span></span>

**<span data-ttu-id="0ed36-274">無法預期的案例和功能：</span><span class="sxs-lookup"><span data-stu-id="0ed36-274">Scenarios and features not expected to work:</span></span>**
- <span data-ttu-id="0ed36-275">同時有音訊流的多個視窗的空間音效</span><span class="sxs-lookup"><span data-stu-id="0ed36-275">Spatial sound from multiple windows with simultaneous audio streams</span></span>
- <span data-ttu-id="0ed36-276">「看到它，說出它」</span><span class="sxs-lookup"><span data-stu-id="0ed36-276">"See it, say it"</span></span>
- <span data-ttu-id="0ed36-277">列印</span><span class="sxs-lookup"><span data-stu-id="0ed36-277">Printing</span></span>

**<span data-ttu-id="0ed36-278">已知瀏覽器的熱門問題：</span><span class="sxs-lookup"><span data-stu-id="0ed36-278">Top known browser issues:</span></span>**
- <span data-ttu-id="0ed36-279">重設您的裝置將會移除新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0ed36-279">Resetting your device will remove the new Microsoft Edge</span></span>
- <span data-ttu-id="0ed36-280">全攝影鍵盤中的放大鏡預覽顯示不正確的內容</span><span class="sxs-lookup"><span data-stu-id="0ed36-280">The magnifier preview in the holographic keyboard shows incorrect content</span></span>
- <span data-ttu-id="0ed36-281">卷軸有時可能會斷斷續續</span><span class="sxs-lookup"><span data-stu-id="0ed36-281">Scrolling can sometimes stutter</span></span>
- <span data-ttu-id="0ed36-282">Microsoft Store 應用程式中的網頁連結可能無法啟動瀏覽器</span><span class="sxs-lookup"><span data-stu-id="0ed36-282">Web links in the Microsoft Store app may not launch the browser</span></span>
- <span data-ttu-id="0ed36-283">如果您先前從不同的瀏覽器視窗播放音訊，音訊可能會從錯誤的瀏覽器視窗播放</span><span class="sxs-lookup"><span data-stu-id="0ed36-283">Audio may play from the wrong browser window if you've previously played audio from a different browser window</span></span>

#### <a name="microsoft-edge-insider-channels"></a><span data-ttu-id="0ed36-284">Microsoft Edge Insider Channels</span><span class="sxs-lookup"><span data-stu-id="0ed36-284">Microsoft Edge Insider channels</span></span>

<span data-ttu-id="0ed36-285">Microsoft Edge 小組提供三個預覽通道給 Edge 測試人員社群：Beta、Dev 和 Canary。</span><span class="sxs-lookup"><span data-stu-id="0ed36-285">The Microsoft Edge team makes three preview channels available to the Edge Insider community: Beta, Dev, and Canary.</span></span> <span data-ttu-id="0ed36-286">安裝預覽通道不會卸載 HoloLens 2 上已發佈的 Microsoft Edge 版本，而且您可以同時安裝多個版本。</span><span class="sxs-lookup"><span data-stu-id="0ed36-286">Installing a preview channel doesn't uninstall the released version of Microsoft Edge on your HoloLens 2, and you can install more than one at the same time.</span></span> 

<span data-ttu-id="0ed36-287">請流覽 [Microsoft Edge Insider 首頁](https://www.microsoftedgeinsider.com) ，深入瞭解 Microsoft Edge Insider 社群。</span><span class="sxs-lookup"><span data-stu-id="0ed36-287">Visit the [Microsoft Edge Insider homepage](https://www.microsoftedgeinsider.com) to learn more about the Edge Insider community.</span></span> <span data-ttu-id="0ed36-288">若要深入瞭解不同的 Edge Insider 通道並開始使用，請流覽 [Edge Insider 下載頁面](https://www.microsoftedgeinsider.com/download)。</span><span class="sxs-lookup"><span data-stu-id="0ed36-288">To learn more about the different Edge Insider channels and get started, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download).</span></span>

<span data-ttu-id="0ed36-289">有幾個方法可用於將 Microsoft Edge 測試人員通道安裝到 HoloLens 2：</span><span class="sxs-lookup"><span data-stu-id="0ed36-289">There are a couple methods available for installing Microsoft Edge Insider channels to HoloLens 2:</span></span>

**<span data-ttu-id="0ed36-290">直接安裝在裝置 (目前僅適用于未管理裝置) </span><span class="sxs-lookup"><span data-stu-id="0ed36-290">Direct install on device (currently only available to unmanaged devices)</span></span>**
  1. <span data-ttu-id="0ed36-291">在 HoloLens 2 上，流覽 [Edge Insider 下載頁面](https://www.microsoftedgeinsider.com/download)。</span><span class="sxs-lookup"><span data-stu-id="0ed36-291">On your HoloLens 2, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download).</span></span>
  1. <span data-ttu-id="0ed36-292">選取要安裝之 Edge Insider 通道的 **HoloLens 2** 下載按鈕。</span><span class="sxs-lookup"><span data-stu-id="0ed36-292">Select the **Download for HoloLens 2** button for the Edge Insider channel you wish to install.</span></span>
  1. <span data-ttu-id="0ed36-293">從 Edge 下載佇列或裝置上的 「下載」資料夾啟動下載的 .msix 檔案， (檔案檔案) 。</span><span class="sxs-lookup"><span data-stu-id="0ed36-293">Launch the downloaded .msix file from the Edge download queue or from your device's "Downloads" folder (using File Explorer).</span></span>
  1. <span data-ttu-id="0ed36-294">[應用程式安裝程式](app-deploy-app-installer.md) 將會啟動。</span><span class="sxs-lookup"><span data-stu-id="0ed36-294">[App installer](app-deploy-app-installer.md) will launch.</span></span>
  1. <span data-ttu-id="0ed36-295">選取安裝 **按鈕** 。</span><span class="sxs-lookup"><span data-stu-id="0ed36-295">Select the **Install** button.</span></span>
  1. <span data-ttu-id="0ed36-296">成功安裝之後，您可以在開始功能表的所有應用程式清單中，將 Microsoft Edge Beta 版、Dev\*\*\*\* 或 Canary 視為個別專案。</span><span class="sxs-lookup"><span data-stu-id="0ed36-296">After successful install, you'll find Microsoft Edge Beta, Dev, or Canary as a separate entry in the **All apps** list of the Start menu.</span></span>

**<span data-ttu-id="0ed36-297">透過電腦使用 Windows 裝置入口網站 (需要啟用[](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)HoloLens 2 應用程式上的開發人員) </span><span class="sxs-lookup"><span data-stu-id="0ed36-297">Install via PC with Windows Device Portal (requires [developer mode](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) to be enabled on HoloLens 2)</span></span>**
  1. <span data-ttu-id="0ed36-298">在您的電腦上，流覽 [Edge Insider 下載頁面](https://www.microsoftedgeinsider.com/download)。</span><span class="sxs-lookup"><span data-stu-id="0ed36-298">On your PC, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download).</span></span>
  1. <span data-ttu-id="0ed36-299">針對要安裝的 Edge **Insider** 通道，選取 「下載 Windows 10」按鈕旁的下拉式箭號按鈕。</span><span class="sxs-lookup"><span data-stu-id="0ed36-299">Select the **drop-down arrow button** next to the "Download for Windows 10" button for the Edge Insider channel you wish to install.</span></span>
  1. <span data-ttu-id="0ed36-300">在**下拉式功能表中選取 HoloLens 2。**</span><span class="sxs-lookup"><span data-stu-id="0ed36-300">Select **HoloLens 2** in the drop-down menu.</span></span>
  1. <span data-ttu-id="0ed36-301">將 .msix 檔案儲存到您的電腦的 「下載」資料夾 (或另一個您可以輕鬆地找到) 。</span><span class="sxs-lookup"><span data-stu-id="0ed36-301">Save the .msix file to the "Downloads" folder of your PC (or another folder you can easily find).</span></span>
  1. <span data-ttu-id="0ed36-302">使用 [您電腦中的 Windows](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) 裝置入口網站在 HoloLens 2 上安裝下載的 .msix 檔案。</span><span class="sxs-lookup"><span data-stu-id="0ed36-302">Use [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) on your PC to install the downloaded .msix file on HoloLens 2.</span></span>
  1. <span data-ttu-id="0ed36-303">成功安裝之後，您可以在開始功能表的所有應用程式清單中，將 Microsoft Edge Beta 版、Dev\*\*\*\* 或 Canary 視為個別專案。</span><span class="sxs-lookup"><span data-stu-id="0ed36-303">After successful install, you'll find Microsoft Edge Beta, Dev, or Canary as a separate entry in the **All apps** list of the Start menu.</span></span>

> [!NOTE]
> <span data-ttu-id="0ed36-304">在 HoloLens 2 的 Windows 測試人員預覽版期間，您裝置上的 Microsoft Edge 版本可能高於某些 (或 Microsoft Edge 測試人員) 中提供的版本。</span><span class="sxs-lookup"><span data-stu-id="0ed36-304">During this Windows Insider preview for HoloLens 2, the version of Microsoft Edge on your device may be higher than those available in some (or all) of the Microsoft Edge Insider channels.</span></span> <span data-ttu-id="0ed36-305">這是為了確保專為 HoloLens 2 的網頁瀏覽器所設計的新功能和修正程式能儘快連至我們的 Windows 測試人員。</span><span class="sxs-lookup"><span data-stu-id="0ed36-305">This is to ensure new features and fixes specifically targeting the web browser on HoloLens 2 are getting to our Windows Insiders as quickly as possible.</span></span> <span data-ttu-id="0ed36-306">下一次 Windows 更新公開發行之後，Microsoft Edge 測試人員通道版本將會超越 HoloLens 2 上的 Microsoft Edge 版本，並維持超前狀態。</span><span class="sxs-lookup"><span data-stu-id="0ed36-306">Shortly after the public release of the next Windows update, the Microsoft Edge Insider channel builds will surpass, and stay ahead of, the version of Microsoft Edge on your HoloLens 2.</span></span>

#### <a name="using-wdac-to-block-new-microsoft-edge"></a><span data-ttu-id="0ed36-307">使用 WDAC 封鎖新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0ed36-307">Using WDAC to block new Microsoft Edge</span></span>

<span data-ttu-id="0ed36-308">對於想要更新 [WDAC](windows-defender-application-control-wdac.md) 策略以封鎖新 Microsoft Edge App 的 IT 系統管理員，您必須將下列專案新增到您的策略中。</span><span class="sxs-lookup"><span data-stu-id="0ed36-308">For IT Admins looking to update their [WDAC policy](windows-defender-application-control-wdac.md) to block the new Microsoft Edge app, you'll need to add the following to your policy.</span></span>

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

### <a name="webxr-and-360-viewer"></a><span data-ttu-id="0ed36-309">WebXR 和 360 Viewer</span><span class="sxs-lookup"><span data-stu-id="0ed36-309">WebXR and 360 Viewer</span></span>

*<span data-ttu-id="0ed36-310">在 Windows Insider Build 20289.1000 中新增</span><span class="sxs-lookup"><span data-stu-id="0ed36-310">Added in Windows Insider build 20289.1000</span></span>*

<span data-ttu-id="0ed36-311">新的 Microsoft Edge 支援 WebXR，這是建立取代 WebVR (網頁體驗的新) 。</span><span class="sxs-lookup"><span data-stu-id="0ed36-311">The new Microsoft Edge includes support for WebXR, which is the new standard for creating immersive web experiences (replacing WebVR).</span></span> <span data-ttu-id="0ed36-312">許多沉浸式網頁體驗在設計時都考慮到 VR， (以虛擬環境) 取代您的視野，但 HoloLens 2 也支援這些體驗。</span><span class="sxs-lookup"><span data-stu-id="0ed36-312">Many immersive web experiences were designed with VR in mind (they replace your field of view with a virtual environment), but these experiences are also supported by HoloLens 2.</span></span> <span data-ttu-id="0ed36-313">WebXR 標準也可啟用使用您實體環境的增強和混合實境沉浸式 Web 體驗。</span><span class="sxs-lookup"><span data-stu-id="0ed36-313">The WebXR standard also enables augmented and mixed reality immersive web experiences that use your physical environment.</span></span> <span data-ttu-id="0ed36-314">隨著開發人員花更多時間使用 WebXR，我們預期新的增強和混合實境沉浸式體驗將送達 HoloLens 2 客戶嘗試！</span><span class="sxs-lookup"><span data-stu-id="0ed36-314">As developers spend more time with WebXR, we anticipate new augmented and mixed reality immersive experiences will arrive for HoloLens 2 customers to try!</span></span>

<span data-ttu-id="0ed36-315">360 檢視器擴充功能建立在 WebXR 上，會自動與 HoloLens 2 上的新 Microsoft Edge 一起安裝。</span><span class="sxs-lookup"><span data-stu-id="0ed36-315">The 360 Viewer extension is built on WebXR and automatically installs alongside the new Microsoft Edge on HoloLens 2.</span></span> <span data-ttu-id="0ed36-316">此 Web 擴充功能讓您能沉浸于 360 度影片中。</span><span class="sxs-lookup"><span data-stu-id="0ed36-316">This web extension gives you the ability to immerse yourself in 360-degree videos.</span></span> <span data-ttu-id="0ed36-317">YouTube 提供最多 360 個影片選擇，因此我們建議您從該影片開始。</span><span class="sxs-lookup"><span data-stu-id="0ed36-317">YouTube offers the largest selection of 360 videos, so we encourage you to start there.</span></span>

#### <a name="how-to-use-webxr"></a><span data-ttu-id="0ed36-318">如何使用 WebXR</span><span class="sxs-lookup"><span data-stu-id="0ed36-318">How to use WebXR</span></span>

1. <span data-ttu-id="0ed36-319">使用 WebXR 支援流覽至網站。</span><span class="sxs-lookup"><span data-stu-id="0ed36-319">Navigate to a website with WebXR support.</span></span>
1. <span data-ttu-id="0ed36-320">選取網站的 **Enter VR** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="0ed36-320">Select the **Enter VR** button on the website.</span></span> <span data-ttu-id="0ed36-321">這個按鈕的位置和視覺呈現方式會因網站而異，但看起來可能類似：</span><span class="sxs-lookup"><span data-stu-id="0ed36-321">The location and visual representation of this button may vary per website, but it may look similar to:</span></span>

    ![輸入 VR 按鈕範例](images/75px-enter-vr.png)

1. <span data-ttu-id="0ed36-323">當您第一次嘗試啟動特定網域上的 WebXR 體驗時，瀏覽器會要求同意進入沉浸式視圖，**選取允許。**</span><span class="sxs-lookup"><span data-stu-id="0ed36-323">The first time you try to launch a WebXR experience on a specific domain, the browser will ask for consent to enter an immersive view, select **Allow**.</span></span>
1. <span data-ttu-id="0ed36-324">使用 [HoloLens 2 手勢](hololens2-basic-usage.md#the-hand-tracking-frame) 操作體驗。</span><span class="sxs-lookup"><span data-stu-id="0ed36-324">Use [HoloLens 2 gestures](hololens2-basic-usage.md#the-hand-tracking-frame) to manipulate the experience.</span></span>
1. <span data-ttu-id="0ed36-325">如果體驗沒有 **離開按鈕，** 請使用開始 [手勢](hololens2-basic-usage.md#start-gesture) 返回首頁。</span><span class="sxs-lookup"><span data-stu-id="0ed36-325">If the experience doesn't have an **Exit** button, use the [Start gesture](hololens2-basic-usage.md#start-gesture) to return home.</span></span>

**<span data-ttu-id="0ed36-326">建議的 WebXR 範例</span><span class="sxs-lookup"><span data-stu-id="0ed36-326">Recommended WebXR samples</span></span>**
- <span data-ttu-id="0ed36-327">360 檢視器 (查看下一節) </span><span class="sxs-lookup"><span data-stu-id="0ed36-327">360 Viewer (see next section)</span></span>
- [<span data-ttu-id="0ed36-328">XR 小龍</span><span class="sxs-lookup"><span data-stu-id="0ed36-328">XR Dinosaurs</span></span>](https://www.xrdinosaurs.com/)
- [<span data-ttu-id="0ed36-329">Barista Express</span><span class="sxs-lookup"><span data-stu-id="0ed36-329">Barista Express</span></span>](https://constructarca.de/game/barista-express/)
- [<span data-ttu-id="0ed36-330">WebXR 小圖</span><span class="sxs-lookup"><span data-stu-id="0ed36-330">WebXR Paint</span></span>](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a><span data-ttu-id="0ed36-331">如何使用 360 Viewer</span><span class="sxs-lookup"><span data-stu-id="0ed36-331">How to use 360 Viewer</span></span>

1. <span data-ttu-id="0ed36-332">流覽至 YouTube 上的 360 度影片。</span><span class="sxs-lookup"><span data-stu-id="0ed36-332">Navigate to a 360-degree video on YouTube.</span></span>
1. <span data-ttu-id="0ed36-333">在視訊畫面中，選取混合實境耳機按鈕：</span><span class="sxs-lookup"><span data-stu-id="0ed36-333">In the video frame, select the mixed reality headset button:</span></span>

    ![啟用 360 檢視器的按鈕](images/enter-360-viewer.jpg)

1. <span data-ttu-id="0ed36-335">當您第一次嘗試在特定的網域上啟動 360 Viewer 時，瀏覽器會要求同意進入沉浸式檢視。</span><span class="sxs-lookup"><span data-stu-id="0ed36-335">The first time you try to launch 360 Viewer on a specific domain, the browser will ask for consent to enter an immersive view.</span></span> <span data-ttu-id="0ed36-336">選取 **允許**。</span><span class="sxs-lookup"><span data-stu-id="0ed36-336">Select **Allow**.</span></span>
1. <span data-ttu-id="0ed36-337">[空中點兩](hololens2-basic-usage.md#select-using-air-tap) 下可顯示播放控制項。</span><span class="sxs-lookup"><span data-stu-id="0ed36-337">[Air tap](hololens2-basic-usage.md#select-using-air-tap) to bring up the playback controls.</span></span> <span data-ttu-id="0ed36-338">使用 [手](hololens2-basic-usage.md#select-using-air-tap) 拍和空中點兩下來播放/暫停、向前/向後跳、開啟/關閉輔助字幕，或 (結束沉浸式) 。</span><span class="sxs-lookup"><span data-stu-id="0ed36-338">Use [hand rays and air tap](hololens2-basic-usage.md#select-using-air-tap) to play/pause, skip forward/back, turn captions on/off, or stop the experience (which exits the immersive view).</span></span> <span data-ttu-id="0ed36-339">播放控制項會在閒置數秒後消失。</span><span class="sxs-lookup"><span data-stu-id="0ed36-339">The playback controls will disappear after a few seconds of inactivity.</span></span>

#### <a name="top-webxr-and-360-viewer-known-issues"></a><span data-ttu-id="0ed36-340">WebXR 和 360 檢視器已知問題</span><span class="sxs-lookup"><span data-stu-id="0ed36-340">Top WebXR and 360 Viewer known issues</span></span>
- <span data-ttu-id="0ed36-341">在 WebXR 體驗中，當您傾斜頭部或四處移動時，全形影像可能會移動或傾斜。</span><span class="sxs-lookup"><span data-stu-id="0ed36-341">In WebXR experiences, holograms may shift or tilt when you tilt your head or move around your environment.</span></span>
- <span data-ttu-id="0ed36-342">根據 WebXR 體驗的複雜度，框架速率可能會降低或斷斷續續。</span><span class="sxs-lookup"><span data-stu-id="0ed36-342">Depending on the complexity of the WebXR experience, the framerate may drop or stutter.</span></span>
- <span data-ttu-id="0ed36-343">WebXR 目前還無法提供手寫手部連接。</span><span class="sxs-lookup"><span data-stu-id="0ed36-343">Articulated hand joints are not yet available in WebXR.</span></span>
- <span data-ttu-id="0ed36-344">在離開 WebXR 或 360 檢視器體驗時，混合實境首頁中的全形影像可能需要 30 秒或更長時間重新出現。</span><span class="sxs-lookup"><span data-stu-id="0ed36-344">When exiting a WebXR or 360 Viewer experience, it may take 30 seconds or more for holograms in the mixed reality home to reappear.</span></span>
- <span data-ttu-id="0ed36-345">YouTube 外網站的 360 個影片可能無法如預期地播放。</span><span class="sxs-lookup"><span data-stu-id="0ed36-345">360 videos from websites other than YouTube may not work as expected.</span></span>
- <span data-ttu-id="0ed36-346">如果 360 影片未進入沉浸式 (或混合實境耳機按鈕未顯示在) ，請嘗試重新組織頁面。</span><span class="sxs-lookup"><span data-stu-id="0ed36-346">If 360 videos don't enter immersive view (or the mixed reality headset button doesn't appear), try refreshing the page.</span></span>
- <span data-ttu-id="0ed36-347">在 HoloLens 2 上的 360 Viewer 中還看不到標題。</span><span class="sxs-lookup"><span data-stu-id="0ed36-347">Captions are not yet visible in 360 Viewer on HoloLens 2.</span></span>
- <span data-ttu-id="0ed36-348">在 360 Viewer 中暫停影片會停止顯示視 (但選取播放按鈕可正確繼續播放) 。</span><span class="sxs-lookup"><span data-stu-id="0ed36-348">Pausing a video in 360 Viewer stops the video from rendering (but selecting the play button correctly resumes playback).</span></span>
- <span data-ttu-id="0ed36-349">360 Viewer 中的 「下一段影片」按鈕目前無法工作。</span><span class="sxs-lookup"><span data-stu-id="0ed36-349">The "next video" button in 360 Viewer does not currently work.</span></span>
- <span data-ttu-id="0ed36-350">您可以在沉浸式「影區」模式中播放 2D 影片，但框架速率小於 30 fps。</span><span class="sxs-lookup"><span data-stu-id="0ed36-350">You can play 2D videos in an immersive "theater" mode, but the framerate will be less than 30 fps.</span></span>

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a><span data-ttu-id="0ed36-351">在 WebXR 和 360 Viewer 上提供意見回饋</span><span class="sxs-lookup"><span data-stu-id="0ed36-351">Providing feedback on WebXR and 360 Viewer</span></span>

<span data-ttu-id="0ed36-352">請透過新 Microsoft Edge 中的傳送\*\*\*\* 意見回饋功能，與小組分享意見回饋和錯誤。</span><span class="sxs-lookup"><span data-stu-id="0ed36-352">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge.</span></span>

### <a name="new-settings-app"></a><span data-ttu-id="0ed36-353">新增設定應用程式</span><span class="sxs-lookup"><span data-stu-id="0ed36-353">New Settings app</span></span>

<span data-ttu-id="0ed36-354">此版本推出後，我們將推出新版的設定應用程式。</span><span class="sxs-lookup"><span data-stu-id="0ed36-354">With this release, we're introducing a new version of the Settings app.</span></span> <span data-ttu-id="0ed36-355">新的設定應用程式包含 HoloLens 2 的新功能和下列領域的擴充設定：音效、Power & 睡眠、網路 & 網際網路、應用程式、帳戶、輕鬆存取等等。</span><span class="sxs-lookup"><span data-stu-id="0ed36-355">The new Settings app includes new features and expanded settings for HoloLens 2 in the following areas: Sound, Power & sleep, Network & Internet, Apps, Accounts, Ease of Access, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="0ed36-356">由於新的設定應用程式與舊版的設定應用程式不同，因此您先前置於環境中的任何設定視窗都會在更新時移除。</span><span class="sxs-lookup"><span data-stu-id="0ed36-356">Because the new Settings app is distinct from the legacy Settings app, any Settings windows you previously placed around your environment will be removed upon update.</span></span>

![新的設定應用程式首頁](images/new-settings-app.png)

**<span data-ttu-id="0ed36-358">新功能和設定</span><span class="sxs-lookup"><span data-stu-id="0ed36-358">New features and settings</span></span>**
- <span data-ttu-id="0ed36-359">設定搜尋：使用關鍵字或設定名稱從 [設定首頁搜尋設定。</span><span class="sxs-lookup"><span data-stu-id="0ed36-359">Settings search: search for settings from the Settings homepage using keywords or the setting's name.</span></span>
- <span data-ttu-id="0ed36-360">系統>音效：</span><span class="sxs-lookup"><span data-stu-id="0ed36-360">System > Sound:</span></span>
  - <span data-ttu-id="0ed36-361">輸入和輸出音訊裝置：獨立選擇您的輸入和輸出音訊裝置 (例如，透過藍牙耳機聆聽音訊，或使用 USB-C 麥克風進行音訊輸入) 。</span><span class="sxs-lookup"><span data-stu-id="0ed36-361">Input and output audio devices: independently choose your input and output audio devices (for example, listen to audio via Bluetooth headphones or use a USB-C microphone for audio input).</span></span>
    > [!NOTE]
    > <span data-ttu-id="0ed36-362">HoloLens 2 不支援藍牙麥克風。</span><span class="sxs-lookup"><span data-stu-id="0ed36-362">Bluetooth microphones are not supported by HoloLens 2.</span></span>
  - <span data-ttu-id="0ed36-363">應用程式音量：分別調整每個 App 的音量。</span><span class="sxs-lookup"><span data-stu-id="0ed36-363">App volume: independently adjust the volume of each app.</span></span> <span data-ttu-id="0ed36-364">請參閱 [每個 App 音量控制](#per-app-volume-control)。</span><span class="sxs-lookup"><span data-stu-id="0ed36-364">See [per app volume control](#per-app-volume-control).</span></span>
- <span data-ttu-id="0ed36-365">系統>電源&：選擇裝置在閒置一段時間後應該進入睡眠狀態。</span><span class="sxs-lookup"><span data-stu-id="0ed36-365">System > Power & sleep: choose when the device should go to sleep after a period of inactivity.</span></span>
- <span data-ttu-id="0ed36-366">系統>：手動啟用省電模式或設定電池臨界值，此時省電模式會自動開啟。</span><span class="sxs-lookup"><span data-stu-id="0ed36-366">System > Battery: manually enable battery saver mode or set a battery threshold at which point battery saver mode turns on automatically.</span></span>
- <span data-ttu-id="0ed36-367">USB 裝置>：您預設可以停用 USB 連接。</span><span class="sxs-lookup"><span data-stu-id="0ed36-367">Devices > USB: you can disable USB connections by default.</span></span>
- <span data-ttu-id="0ed36-368">網路&網際網路：</span><span class="sxs-lookup"><span data-stu-id="0ed36-368">Network & Internet:</span></span>
  - <span data-ttu-id="0ed36-369">USB-C 乙太網路介面卡現在會出現在網際網路&中。</span><span class="sxs-lookup"><span data-stu-id="0ed36-369">USB-C Ethernet adapters will now appear in Network & Internet.</span></span>
  - <span data-ttu-id="0ed36-370">USB-C 乙太網路介面卡設定現已提供，包括其 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0ed36-370">USB-C Ethernet adapter settings are now available, including its IP address.</span></span>
  - <span data-ttu-id="0ed36-371">現在您可以在 HoloLens 2 上啟用飛航模式。</span><span class="sxs-lookup"><span data-stu-id="0ed36-371">You can now enable airplane mode on HoloLens 2.</span></span>
- <span data-ttu-id="0ed36-372">應用程式：您可以重設用於檔案和連結類型的預設應用程式。</span><span class="sxs-lookup"><span data-stu-id="0ed36-372">Apps: you can reset the default apps used for file and link types.</span></span> <span data-ttu-id="0ed36-373">詳細資訊請參閱預設 [應用程式選擇器](#default-app-picker)。</span><span class="sxs-lookup"><span data-stu-id="0ed36-373">For more information see [Default app picker](#default-app-picker).</span></span>
- <span data-ttu-id="0ed36-374">帳戶>：裝置擁有者可以新增使用者、將標準使用者升級為裝置擁有者、將裝置擁有者降級為標準使用者，以及移除使用者。</span><span class="sxs-lookup"><span data-stu-id="0ed36-374">Accounts > Other users: device owners can add users, upgrade standard users to device owners, downgrade device owners to standard users, and remove users.</span></span>
- <span data-ttu-id="0ed36-375">輕鬆存取：變更文字大小和一些視覺效果。</span><span class="sxs-lookup"><span data-stu-id="0ed36-375">Ease of Access: change text size and some visual effects.</span></span>

**<span data-ttu-id="0ed36-376">已知問題</span><span class="sxs-lookup"><span data-stu-id="0ed36-376">Known issues</span></span>**
- <span data-ttu-id="0ed36-377">先前放置的設定視窗將會移除 (上方的備註) 。</span><span class="sxs-lookup"><span data-stu-id="0ed36-377">Previously placed Settings windows will be removed (see note above).</span></span>
- <span data-ttu-id="0ed36-378">您無法再使用設定應用程式重新命名您的裝置。</span><span class="sxs-lookup"><span data-stu-id="0ed36-378">You can no longer rename your device with the Settings app.</span></span> <span data-ttu-id="0ed36-379">IT 系統管理員可以使用 [HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) 裝置名稱範本的 Windows Autopilot 或 MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName 節點來重新命名裝置。</span><span class="sxs-lookup"><span data-stu-id="0ed36-379">IT admins can rename devices by using the [Windows Autopilot for HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) device name template or the MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName node.</span></span>
- <span data-ttu-id="0ed36-380">乙太網路頁面會一 (「usbNcm」) 虛擬乙太網路裝置。</span><span class="sxs-lookup"><span data-stu-id="0ed36-380">The Ethernet page shows a virtual Ethernet device ("UsbNcm") at all times.</span></span>
- <span data-ttu-id="0ed36-381">新版 Microsoft Edge 的電池使用量可能不太正確，因為其性質是 UWP 介面卡圖層支援的 Win32 桌面應用程式， (預期近期將修正) 。</span><span class="sxs-lookup"><span data-stu-id="0ed36-381">Battery usage for the new Microsoft Edge may not be accurate, due to its nature as a Win32 desktop application supported by a UWP adapter layer (no fix anticipated soon).</span></span>

### <a name="display-color-calibration"></a><span data-ttu-id="0ed36-382">顯示色彩校正</span><span class="sxs-lookup"><span data-stu-id="0ed36-382">Display color calibration</span></span>

*<span data-ttu-id="0ed36-383">在 Windows Insider Build 20293.1000 中新增</span><span class="sxs-lookup"><span data-stu-id="0ed36-383">Added in Windows Insider build 20293.1000</span></span>*

<span data-ttu-id="0ed36-384">有了這個新設定，您可以選取 HoloLens 2 顯示器的替代色彩設定檔。</span><span class="sxs-lookup"><span data-stu-id="0ed36-384">With this new setting, you can select an alternative color profile for your HoloLens 2 display.</span></span> <span data-ttu-id="0ed36-385">這可協助色彩顯示更精確，尤其是在較低的顯示亮度等級。</span><span class="sxs-lookup"><span data-stu-id="0ed36-385">This may help colors appear more accurate, especially at lower display brightness levels.</span></span> <span data-ttu-id="0ed36-386">顯示色彩校正可以在設定 App 的系統校正頁面上找到>校正。</span><span class="sxs-lookup"><span data-stu-id="0ed36-386">Display color calibration can be found in the Settings app, on the System > Calibration page.</span></span>

> [!NOTE]
> <span data-ttu-id="0ed36-387">由於此設定會將新的色彩設定檔存到您的顯示中，因此它是每個裝置設定 (，並非每個使用者帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="0ed36-387">Because this setting saves a new color profile to your display firmware, it is a per-device setting (and not unique to each user account).</span></span>

#### <a name="how-to-use-display-color-calibration"></a><span data-ttu-id="0ed36-388">如何使用顯示色彩校正</span><span class="sxs-lookup"><span data-stu-id="0ed36-388">How to use display color calibration</span></span>

1. <span data-ttu-id="0ed36-389">啟動設定 **應用程式** ，然後流覽至 **系統>校正**。</span><span class="sxs-lookup"><span data-stu-id="0ed36-389">Launch the **Settings** app and navigate to **System > Calibration**.</span></span>
1. <span data-ttu-id="0ed36-390">在 **顯示色彩校正下**，選取執行 **顯示色彩校正** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="0ed36-390">Under **Display color calibration**, select the **Run display color calibration** button.</span></span>
1. <span data-ttu-id="0ed36-391">顯示色彩校正體驗將會啟動，並鼓勵您確認您的 Visor 處於正確的位置。</span><span class="sxs-lookup"><span data-stu-id="0ed36-391">The display color calibration experience will launch and encourage you to make sure your visor is in the correct position.</span></span>
1. <span data-ttu-id="0ed36-392">在您繼續進行指示對話方塊後，您的顯示器會自動變暗為 30% 的亮度。</span><span class="sxs-lookup"><span data-stu-id="0ed36-392">After you proceed through the instruction dialog boxes, your display will automatically be dimmed to 30% brightness.</span></span>
    > [!TIP]
    > <span data-ttu-id="0ed36-393">如果您無法看到環境中變暗的場景，您可以使用裝置左側的亮度按鈕，手動調整 HoloLens 2 的亮度等級。</span><span class="sxs-lookup"><span data-stu-id="0ed36-393">If you're having trouble seeing the dimmed scene in your environment, you can manually adjust the brightness level of HoloLens 2 using the brightness buttons on the left side of the device.</span></span>
1. <span data-ttu-id="0ed36-394">選取按鈕 1 到 6 以立即試用每個色彩設定檔，並找出最適合您眼睛的設定檔 (這通常表示協助場景呈現最中立的設定檔，而灰階圖樣和色調看起來如預期。) </span><span class="sxs-lookup"><span data-stu-id="0ed36-394">Select buttons 1-6 to instantly try out each color profile, and find one that looks the best to your eyes (this usually means the profile that helps the scene appear most neutral, with the grayscale pattern and skin tones looking as expected.)</span></span>

    ![顯示色彩校正場景](images/color-cal-ui.png)
    
1. <span data-ttu-id="0ed36-396">當您對選取的設定檔滿意時，請選取儲存&**按鈕**</span><span class="sxs-lookup"><span data-stu-id="0ed36-396">When you're happy with the selected profile, select the **Save & Exit** button</span></span>
1. <span data-ttu-id="0ed36-397">如果您不想進行變更，請選取取消& **按鈕** ，您的變更將會還原</span><span class="sxs-lookup"><span data-stu-id="0ed36-397">If you prefer not to make changes, select the **Cancel & Exit** button and your changes will be reverted</span></span>

> [!TIP]
> <span data-ttu-id="0ed36-398">以下是使用顯示色彩校正設定時請記住的一些實用秘訣：</span><span class="sxs-lookup"><span data-stu-id="0ed36-398">Here are some helpful tips to keep in mind while using the display color calibration setting:</span></span>
> - <span data-ttu-id="0ed36-399">您可以隨時從設定重新執行顯示色彩校正</span><span class="sxs-lookup"><span data-stu-id="0ed36-399">You can re-run display color calibration from Settings whenever you'd like</span></span>
> - <span data-ttu-id="0ed36-400">如果裝置上的任何人先前曾使用設定來變更色彩設定檔，最新變更的日期/時間會反映在設定頁面上</span><span class="sxs-lookup"><span data-stu-id="0ed36-400">If anyone on the device has previously used the setting to change color profiles, the date/time of the most recent change will be reflected on the Settings page</span></span>
> - <span data-ttu-id="0ed36-401">當您重新執行顯示色彩校正時，先前儲存的色彩設定檔會反顯示，而設定檔 0 不會顯示為 (因為設定檔 0 代表顯示器的原始色彩設定檔) </span><span class="sxs-lookup"><span data-stu-id="0ed36-401">When you re-run display color calibration, the color profile that was previously saved will be highlighted and Profile 0 will not appear (as Profile 0 represents the display's original color profile)</span></span>
> - <span data-ttu-id="0ed36-402">如果您想要還原為顯示器的原始色彩設定檔，可以從設定頁面執行此 [ (瞭解如何重](#how-to-reset-color-profile) 設色彩設定檔) </span><span class="sxs-lookup"><span data-stu-id="0ed36-402">If you want to revert to the display's original color profile, you can do so from the Settings page (see [how to reset color profile](#how-to-reset-color-profile))</span></span>

#### <a name="how-to-reset-color-profile"></a><span data-ttu-id="0ed36-403">如何重設色彩設定檔</span><span class="sxs-lookup"><span data-stu-id="0ed36-403">How to reset color profile</span></span>

<span data-ttu-id="0ed36-404">如果您不滿意儲存到 HoloLens 2 的自訂色彩設定檔，您可以還原裝置的原始色彩設定檔：</span><span class="sxs-lookup"><span data-stu-id="0ed36-404">If you're unhappy with the custom color profile saved to your HoloLens 2, you can restore the device's original color profile:</span></span>
1. <span data-ttu-id="0ed36-405">啟動設定 **應用程式** ，然後流覽至 **系統>校正**。</span><span class="sxs-lookup"><span data-stu-id="0ed36-405">Launch the **Settings** app and navigate to **System > Calibration**.</span></span>
1. <span data-ttu-id="0ed36-406">在 **顯示色彩校正下**，選取重 **設成預設色彩設定檔** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="0ed36-406">Under **Display color calibration**, select the **Reset to default color profile** button.</span></span>
1. <span data-ttu-id="0ed36-407">對話方塊開啟時，如果您已準備好重新開機\*\*\*\* HoloLens 2 並套用變更，請選取 [重新開機。</span><span class="sxs-lookup"><span data-stu-id="0ed36-407">When the dialog box opens, select **Restart** if you're ready to restart HoloLens 2 and apply your changes.</span></span>

#### <a name="top-display-color-calibration-known-issues"></a><span data-ttu-id="0ed36-408">顯示色彩校正已知問題</span><span class="sxs-lookup"><span data-stu-id="0ed36-408">Top display color calibration known issues</span></span>

- <span data-ttu-id="0ed36-409">在設定頁面上，告訴您上次變更色彩設定檔時間的狀態字串將會過期，直到您重載該設定頁面為止</span><span class="sxs-lookup"><span data-stu-id="0ed36-409">On the Settings page, the status string that tells you when the color profile was last changed will be out of date until you reload that page of Settings</span></span> 
    - <span data-ttu-id="0ed36-410">解決方法：選取另一個設定頁面，然後重新選取校正頁面。</span><span class="sxs-lookup"><span data-stu-id="0ed36-410">Workaround: Select another Settings page and then re-select the Calibration page.</span></span>
- <span data-ttu-id="0ed36-411">如果您的 HoloLens 2 在執行顯示色彩校正時進入睡眠狀態，它稍後會繼續到混合實境首頁，您的顯示亮度等級仍然會變暗。</span><span class="sxs-lookup"><span data-stu-id="0ed36-411">If your HoloLens 2 goes to sleep while running display color calibration, it will later resume into the mixed reality home and your display brightness level will still be dimmed.</span></span>
- <span data-ttu-id="0ed36-412">您可能需要嘗試向上/向下按下裝置左側的亮度按鈕數次，才能如預期地工作。</span><span class="sxs-lookup"><span data-stu-id="0ed36-412">You may need to try pressing the brightness buttons on the left side of your device up/down a few times before they work as expected.</span></span>
- <span data-ttu-id="0ed36-413">並非所有市場都完成當地語系化</span><span class="sxs-lookup"><span data-stu-id="0ed36-413">Localization is not complete for all markets</span></span>

### <a name="default-app-picker"></a><span data-ttu-id="0ed36-414">預設應用程式選擇器</span><span class="sxs-lookup"><span data-stu-id="0ed36-414">Default app picker</span></span>

<span data-ttu-id="0ed36-415">當您啟用超連結或開啟具有多個已安裝應用程式的檔案類型時 ，會看到一個新視窗開啟，提示您選取該安裝的應用程式應處理檔案或連結類型。</span><span class="sxs-lookup"><span data-stu-id="0ed36-415">When you activate a hyperlink or open a file type with more than one installed app, which supports it, you will see a new window open prompting you to select which installed app should handle the file or link type.</span></span> <span data-ttu-id="0ed36-416">在此視窗中，您也可以選擇讓選取的應用程式處理檔案或連結類型「一次」或「永遠」。</span><span class="sxs-lookup"><span data-stu-id="0ed36-416">In this window, you can also choose to have the selected app handle the file or link type "Once" or "Always."</span></span>

![應用程式選擇器視窗](images/default-app-picker.png)

<span data-ttu-id="0ed36-418">如果您選擇 「Always」，但稍後想要變更處理特定檔案或連結類型的應用程式，您可以在應用程式設定中重 **設>預設值**。</span><span class="sxs-lookup"><span data-stu-id="0ed36-418">If you choose "Always" but later want to change which app handles a particular file or link type, you can reset your saved defaults in **Settings > Apps**.</span></span> <span data-ttu-id="0ed36-419">卷卷至頁面底部，然後選取 「\*\*\*\* 檔案類型的預設應用程式」和/或「連結類型的預設應用程式」下的清除按鈕。</span><span class="sxs-lookup"><span data-stu-id="0ed36-419">Scroll to the bottom of the page and select the **Clear** button under "Default apps for file types" and/or "Default apps for link types."</span></span> <span data-ttu-id="0ed36-420">不同于桌上型電腦中的類似設定，您無法重設個別檔案類型的預設值。</span><span class="sxs-lookup"><span data-stu-id="0ed36-420">Unlike the similar setting on desktop PCs, you can't reset individual file type defaults.</span></span>

### <a name="per-app-volume-control"></a><span data-ttu-id="0ed36-421">每個 App 音量控制</span><span class="sxs-lookup"><span data-stu-id="0ed36-421">Per app volume control</span></span>

<span data-ttu-id="0ed36-422">現在，在這個 Windows 測試人員建立中，使用者可以手動調整每個應用程式的音量層級。</span><span class="sxs-lookup"><span data-stu-id="0ed36-422">Now in this Windows Insider build users can manually adjust the volume level of each app.</span></span> <span data-ttu-id="0ed36-423">這可讓使用者更專注于所需的應用程式，或在使用多個 App 時更聆聽。</span><span class="sxs-lookup"><span data-stu-id="0ed36-423">This allows for users to better focus on the apps that they need to, or better hear when using multiple apps.</span></span> <span data-ttu-id="0ed36-424">例如，需要關閉一個 App 的音量，同時呼叫另一個人在另一個應用程式中進行遠端協助。</span><span class="sxs-lookup"><span data-stu-id="0ed36-424">Such as needing to turn down volume of one app while calling another person for remote assistance in another.</span></span>

<span data-ttu-id="0ed36-425">若要設定個別 App 的音量，請\*\*\*\* 流覽至設定系統音效，並在進一步  ->  \*\*\*\*  ->  \*\*\*\* 音效選項下選取**應用程式音量和裝置喜好設定**。</span><span class="sxs-lookup"><span data-stu-id="0ed36-425">To set the volume of an individual app navigate to **Settings** -> **System** -> **Sound**, and under Advanced sound options select **App volume and device preferences**.</span></span>

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

### <a name="office-web-app"></a><span data-ttu-id="0ed36-426">Office Web App</span><span class="sxs-lookup"><span data-stu-id="0ed36-426">Office web app</span></span>

<span data-ttu-id="0ed36-427">Office Web App 已新增到開始功能表中的 「所有應用程式」清單。</span><span class="sxs-lookup"><span data-stu-id="0ed36-427">The Office web app has been added to the "All apps" list in the Start menu.</span></span> <span data-ttu-id="0ed36-428">這個 Web 應用程式也可以釘釘到開始或卸載。</span><span class="sxs-lookup"><span data-stu-id="0ed36-428">This web app can also be pinned to Start or uninstalled.</span></span> <span data-ttu-id="0ed36-429">由於這是 Web 應用程式，因此其功能會完全符合您流覽時的體驗 https://www.office.com 。</span><span class="sxs-lookup"><span data-stu-id="0ed36-429">Because this is a web app, its functionality matches exactly what you'd experience by visiting https://www.office.com.</span></span> <span data-ttu-id="0ed36-430">Office Web App 功能只有在 HoloLens 2 有有效的網際網路連接時才能使用。</span><span class="sxs-lookup"><span data-stu-id="0ed36-430">Office web app functionality is only available when your HoloLens 2 has an active internet connection.</span></span>

**<span data-ttu-id="0ed36-431">已知問題</span><span class="sxs-lookup"><span data-stu-id="0ed36-431">Known issue</span></span>**
- <span data-ttu-id="0ed36-432">重設您的裝置將會移除 Office Web App</span><span class="sxs-lookup"><span data-stu-id="0ed36-432">Resetting your device will remove the Office web app</span></span>

### <a name="swipe-to-type"></a><span data-ttu-id="0ed36-433">滑動以輸入</span><span class="sxs-lookup"><span data-stu-id="0ed36-433">Swipe to type</span></span>

<span data-ttu-id="0ed36-434">有些客戶會滑動想要輸入之字詞的形狀，以在虛擬鍵盤上更快速地「輸入」，我們正在預覽全攝影鍵盤的這項功能。</span><span class="sxs-lookup"><span data-stu-id="0ed36-434">Some customers find it faster to "type" on virtual keyboards by swiping the shape of the word they intend to type, and we're previewing this feature for the holographic keyboard.</span></span> <span data-ttu-id="0ed36-435">您可以一次滑動一個字，將手指的筆尖透過全攝影鍵盤的螢幕、滑動文字的形狀，然後從鍵盤上收回手指的提示。</span><span class="sxs-lookup"><span data-stu-id="0ed36-435">You can swipe one word at a time by passing the tip of your finger through the plane of the holographic keyboard, swiping the shape of the word, and then withdrawing the tip of your finger from the plane of the keyboard.</span></span> <span data-ttu-id="0ed36-436">您可以將手指從鍵盤移除文字，即可在後續文字之間滑動，而不需要按空格鍵。</span><span class="sxs-lookup"><span data-stu-id="0ed36-436">You can swipe follow up words without needing to press the space bar by removing your finger from the keyboard between words.</span></span> <span data-ttu-id="0ed36-437">如果您看到手指在鍵盤上移動後看到滑動軌跡，就會知道此功能正在使用中。</span><span class="sxs-lookup"><span data-stu-id="0ed36-437">You will know the feature is working if you see a swipe trail following your finger's movement on the keyboard.</span></span>

<span data-ttu-id="0ed36-438">請注意，由於全像攝影鍵盤的性質，您不會因為手指而感到受威脅，因此使用和主控這項功能可能會有些難度 (手機顯示器和手機) 。</span><span class="sxs-lookup"><span data-stu-id="0ed36-438">Please note, this feature can be tricky to use and master because of the nature of a holographic keyboard where you don't feel resistance against your finger (unlike a mobile phone display).</span></span> <span data-ttu-id="0ed36-439">我們正在評估這項公開發行功能，因此您的意見至關重要;您是否覺得這項功能實用或您的意見有建設性的意見，請透過意見回饋中心 [讓我們知道](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="0ed36-439">We are evaluating this feature for public release, so your feedback is important; whether you find the feature useful or you have constructive feedback, please let us know via [Feedback Hub](hololens-feedback.md).</span></span>

### <a name="power-menu-from-start"></a><span data-ttu-id="0ed36-440">從開始功能表的電源功能表</span><span class="sxs-lookup"><span data-stu-id="0ed36-440">Power menu from Start</span></span>

<span data-ttu-id="0ed36-441">新的功能表，可讓使用者登出、關機並重新啟動裝置。</span><span class="sxs-lookup"><span data-stu-id="0ed36-441">A new menu that allows the user to sign out, shut down and restart the device.</span></span> <span data-ttu-id="0ed36-442">HoloLens 開始畫面中的指示器，顯示系統更新可用時間。</span><span class="sxs-lookup"><span data-stu-id="0ed36-442">An indicator in the HoloLens Start screen that shows when a system update is available.</span></span>

#### <a name="how-to-use"></a><span data-ttu-id="0ed36-443">如何使用</span><span class="sxs-lookup"><span data-stu-id="0ed36-443">How to use</span></span>

1. <span data-ttu-id="0ed36-444">使用開始手勢或說「前往開始」來[](hololens2-basic-usage.md#start-gesture)開啟 HoloLens 開始畫面。</span><span class="sxs-lookup"><span data-stu-id="0ed36-444">Open the HoloLens Start screen using the [Start gesture](hololens2-basic-usage.md#start-gesture) or saying "Go to Start".</span></span>

2. <span data-ttu-id="0ed36-445">請注意，使用者設定檔 (...) 旁的省略號圖示：</span><span class="sxs-lookup"><span data-stu-id="0ed36-445">Notice the ellipsis icon (...) next to the user profile picture:</span></span>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. <span data-ttu-id="0ed36-446">使用您的雙手或語音命令 「Power」選取使用者設定檔圖片。</span><span class="sxs-lookup"><span data-stu-id="0ed36-446">Select the user profile picture using your hands or the voice command "Power".</span></span>

4. <span data-ttu-id="0ed36-447">功能表會顯示，並包含登出、重新開機或關閉裝置的選項：</span><span class="sxs-lookup"><span data-stu-id="0ed36-447">A menu appears with options to Sign out, Restart or Shut down the device:</span></span>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. <span data-ttu-id="0ed36-448">選取功能表選項以登出、重新開機或關閉 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="0ed36-448">Select the menu options to sign out, restart or shut down your HoloLens.</span></span> <span data-ttu-id="0ed36-449">如果裝置是針對單一 Microsoft 帳戶或 [MSA](hololens-identity.md)帳戶設定 (登出) 選項。</span><span class="sxs-lookup"><span data-stu-id="0ed36-449">The Sign out option might not be available, if the device is set up for a [single Microsoft Account (MSA) or local account](hololens-identity.md).</span></span>

6. <span data-ttu-id="0ed36-450">輕觸其他位置，或以開始手勢關閉開始功能表，即可關閉功能表。</span><span class="sxs-lookup"><span data-stu-id="0ed36-450">Dismiss the menu by touching anywhere else or closing the Start menu with the Start gesture.</span></span>

#### <a name="update-indicator"></a><span data-ttu-id="0ed36-451">更新指示器</span><span class="sxs-lookup"><span data-stu-id="0ed36-451">Update indicator</span></span>

<span data-ttu-id="0ed36-452">更新可用時，省略號圖示會亮起，表示重新開機將會安裝更新。功能表選項也會變更以反映更新的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="0ed36-452">When an update is available, the ellipsis icon will light up to indicate that a restart will install the update The menu options also change to reflect the presence of the update.</span></span><br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a><span data-ttu-id="0ed36-453">列在登錄畫面上的多個使用者</span><span class="sxs-lookup"><span data-stu-id="0ed36-453">Multiple users listed on Sign in screen</span></span>

<span data-ttu-id="0ed36-454">之前，The Sign In screen 只會顯示最近已登錄的使用者，以及 'Other user' 進入點。</span><span class="sxs-lookup"><span data-stu-id="0ed36-454">Previously the Sign In screen showed only the most recently signed in user, as well as an 'Other user' entry point.</span></span> <span data-ttu-id="0ed36-455">我們已收到客戶的意見回饋，指出如果有多個使用者已登錄裝置，這項功能就不足。</span><span class="sxs-lookup"><span data-stu-id="0ed36-455">We have received customer feedback that this not sufficient if multiple users have signed into the device.</span></span> <span data-ttu-id="0ed36-456">他們仍然需要重新輸入使用者名稱等。</span><span class="sxs-lookup"><span data-stu-id="0ed36-456">They were still required to retype their username etc.</span></span>

<span data-ttu-id="0ed36-457">此 Windows 測試人員建立推出時\*\*\*\*，選取位於 PIN 專案欄位右邊的其他使用者時，即會顯示先前已登錄裝置的多個使用者。</span><span class="sxs-lookup"><span data-stu-id="0ed36-457">Introduced in this Windows Insider build, when selecting **Other user** which is located to the right of the PIN entry field, the Sign in screen will display multiple users with have previously signed into the device.</span></span> <span data-ttu-id="0ed36-458">這可讓使用者選取其使用者設定檔，然後使用他們的 Windows Hello 認證來登錄。</span><span class="sxs-lookup"><span data-stu-id="0ed36-458">This allows users to select their user profile and then sign-in using their Windows Hello credentials.</span></span> <span data-ttu-id="0ed36-459">您也可以透過此其他使用者頁面，透過新增帳戶按鈕，將新使用者新 **加入** 裝置。</span><span class="sxs-lookup"><span data-stu-id="0ed36-459">A new user can also be added to the device from this Other users page via the **Add account** button.</span></span>

<span data-ttu-id="0ed36-460">在其他使用者功能表中時，其他使用者按鈕會顯示最後一個已簽署裝置的使用者。</span><span class="sxs-lookup"><span data-stu-id="0ed36-460">When in the Other users menu, the Other users button will display the last user signed into the device.</span></span> <span data-ttu-id="0ed36-461">選取此按鈕以返回此使用者的登錄畫面。</span><span class="sxs-lookup"><span data-stu-id="0ed36-461">Select this button to return to the Sign in screen for this user.</span></span>

![預設登錄畫面](./images/multiusers1.jpg)

<br>

![其他使用者的登錄畫面](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="0ed36-464">USB-C 外接麥克風支援</span><span class="sxs-lookup"><span data-stu-id="0ed36-464">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ed36-465">插入 USB **麥克風並不會自動將其設定為輸入裝置**。</span><span class="sxs-lookup"><span data-stu-id="0ed36-465">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="0ed36-466">插入一組 USB-C 耳機時，使用者會注意到耳機的音訊會自動重新導向至耳機，但 HoloLens OS 會將內部麥克風陣列優先排列于任何其他輸入裝置上方。</span><span class="sxs-lookup"><span data-stu-id="0ed36-466">When plugging in a set of USB-C headphones users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> **<span data-ttu-id="0ed36-467">若要使用 USB-C 麥克風，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="0ed36-467">In order to use a USB-C microphone follow the steps below.</span></span>**

<span data-ttu-id="0ed36-468">使用者可以使用聲音設定面板選取 USB-C 連接 **的外部** 麥克風。</span><span class="sxs-lookup"><span data-stu-id="0ed36-468">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="0ed36-469">USB-C 麥克風可用於通話、錄製等。</span><span class="sxs-lookup"><span data-stu-id="0ed36-469">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="0ed36-470">開啟設定**應用程式\*\*\*\*，然後選取**系統  >  **音效**。</span><span class="sxs-lookup"><span data-stu-id="0ed36-470">Open the **Settings** app and select **System** > **Sound**.</span></span>

![音效設定](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="0ed36-472">若要使用外接式麥克風與 **遠端**輔助，使用者必須按一下 [管理音效裝置」 超連結。</span><span class="sxs-lookup"><span data-stu-id="0ed36-472">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="0ed36-473">然後使用下拉式選項將外部麥克風設為**預設或\*\*\*\*通訊預設值。**</span><span class="sxs-lookup"><span data-stu-id="0ed36-473">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="0ed36-474">選擇 **預設值** 表示外接式麥克風會用於所有位置。</span><span class="sxs-lookup"><span data-stu-id="0ed36-474">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="0ed36-475">選擇 **通訊** 預設值表示外部麥克風將用於遠端輔助和其他通訊應用程式，但 HoloLens 麥克風陣列可能仍然用於其他工作。</span><span class="sxs-lookup"><span data-stu-id="0ed36-475">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![管理音效裝置](images/usbc-mic-2.png)

<br>

![將麥克風設為預設值](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="0ed36-478">藍牙麥克風支援呢？</span><span class="sxs-lookup"><span data-stu-id="0ed36-478">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="0ed36-479">很抱歉，HoloLens 2 目前仍不支援藍牙麥克風。</span><span class="sxs-lookup"><span data-stu-id="0ed36-479">Unfortunately Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

#### <a name="troubleshooting-usb-c-microphones"></a><span data-ttu-id="0ed36-480">USB-C 麥克風疑難排解</span><span class="sxs-lookup"><span data-stu-id="0ed36-480">Troubleshooting USB-C microphones</span></span>

<span data-ttu-id="0ed36-481">請注意，有些 USB-C 麥克風無法正確報告本身為麥克風和喇\*\* 叭。</span><span class="sxs-lookup"><span data-stu-id="0ed36-481">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="0ed36-482">這是麥克風的問題，而非 HoloLens 的問題。</span><span class="sxs-lookup"><span data-stu-id="0ed36-482">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="0ed36-483">將其中一個麥克風插入 HoloLens 時，可能會遺失聲音。</span><span class="sxs-lookup"><span data-stu-id="0ed36-483">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="0ed36-484">幸好有一個簡單的修正程式。</span><span class="sxs-lookup"><span data-stu-id="0ed36-484">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="0ed36-485">在**設定**系統音效中，將內建喇叭 ( ->  \*\*\*\*  ->  \*\* \*\*\*\*類比功能音訊**驅動程式) 設為**預設裝置\*\*。</span><span class="sxs-lookup"><span data-stu-id="0ed36-485">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="0ed36-486">HoloLens 應該會記住這項設定，即使麥克風稍後已移除並重新連接也一樣。</span><span class="sxs-lookup"><span data-stu-id="0ed36-486">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![USB-C 麥克風疑難排解](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a><span data-ttu-id="0ed36-488">資訊站的訪客自動登入</span><span class="sxs-lookup"><span data-stu-id="0ed36-488">Visitor Auto logon for Kiosks</span></span>

<span data-ttu-id="0ed36-489">這項新功能可讓訪客帳戶的自動登入功能用於 Kiosk 模式。</span><span class="sxs-lookup"><span data-stu-id="0ed36-489">This new feature enables the auto logon on Visitor accounts to be used for Kiosk modes.</span></span>

<span data-ttu-id="0ed36-490">針對非 AAD 設定，若要設定訪客自動登入的裝置：</span><span class="sxs-lookup"><span data-stu-id="0ed36-490">For a non-AAD configuration, to configure a device for visitor auto-logon:</span></span>

1. <span data-ttu-id="0ed36-491">建立一個提供套件，該套件：</span><span class="sxs-lookup"><span data-stu-id="0ed36-491">Create a provisioning package that:</span></span>
    1. <span data-ttu-id="0ed36-492">設定 **Runtime 設定/AssignedAccess 以** 允許訪客帳戶。</span><span class="sxs-lookup"><span data-stu-id="0ed36-492">Configures **Runtime settings/AssignedAccess** to allow Visitor accounts.</span></span>
    1. <span data-ttu-id="0ed36-493">您也可以選擇在 MDM (\*\* Runtime 設定/工作場所/ \*\* 註冊) 註冊裝置，以便日後管理。</span><span class="sxs-lookup"><span data-stu-id="0ed36-493">Optionally enrolls the device in MDM **(Runtime settings/Workplace/Enrollments)** so that it can be managed later.</span></span>
    1. <span data-ttu-id="0ed36-494">請勿建立本地帳戶</span><span class="sxs-lookup"><span data-stu-id="0ed36-494">Do not create a local account</span></span>
1. <span data-ttu-id="0ed36-495">[套用設置套件](hololens-provisioning.md)。</span><span class="sxs-lookup"><span data-stu-id="0ed36-495">[Apply the provisioning package](hololens-provisioning.md).</span></span>

<span data-ttu-id="0ed36-496">針對 AAD 組配置，使用者不需要進行此變更，即可在今天達到類似此目的。</span><span class="sxs-lookup"><span data-stu-id="0ed36-496">For an AAD configuration, users can achieve something similar to this today without this change.</span></span> <span data-ttu-id="0ed36-497">針對資訊站模式所配置的 AAD 已加入裝置，只需從登錄畫面點選單一按鈕，即可進入訪客帳戶。</span><span class="sxs-lookup"><span data-stu-id="0ed36-497">AAD joined devices configured for kiosk mode can sign in a Visitor account with a single button tap from the sign in screen.</span></span> <span data-ttu-id="0ed36-498">一旦登出訪客帳戶，裝置不會提示再次輸入，直到訪客從開始功能表明確登出或裝置重新開機。</span><span class="sxs-lookup"><span data-stu-id="0ed36-498">Once signed in to the visitor account, the device will not prompt for sign in again until the Visitor is explicitly signed out from the start menu or the device is restarted.</span></span>

<span data-ttu-id="0ed36-499">訪客自動登入可以透過自訂 [OMA-URI](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) 策略管理：</span><span class="sxs-lookup"><span data-stu-id="0ed36-499">Visitor Auto logon can be managed via [custom OMA-URI](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) policy:</span></span>

- <span data-ttu-id="0ed36-500">URI 值：./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon</span><span class="sxs-lookup"><span data-stu-id="0ed36-500">URI value: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon</span></span>

| <span data-ttu-id="0ed36-501">原則</span><span class="sxs-lookup"><span data-stu-id="0ed36-501">Policy</span></span>  | <span data-ttu-id="0ed36-502">描述</span><span class="sxs-lookup"><span data-stu-id="0ed36-502">Description</span></span>   | <span data-ttu-id="0ed36-503">設定</span><span class="sxs-lookup"><span data-stu-id="0ed36-503">Configurations</span></span>  |
|---|---|---|
| <span data-ttu-id="0ed36-504">MixedReality/VisitorAutoLogon</span><span class="sxs-lookup"><span data-stu-id="0ed36-504">MixedReality/VisitorAutoLogon</span></span>  | <span data-ttu-id="0ed36-505">允許訪客自動登入 Kiosk</span><span class="sxs-lookup"><span data-stu-id="0ed36-505">Allows for a Visitor to Auto logon to a Kiosk</span></span>   | <span data-ttu-id="0ed36-506">1 (是) ，0 (否，預設值.) </span><span class="sxs-lookup"><span data-stu-id="0ed36-506">1 (Yes), 0 (No, default.)</span></span>  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a><span data-ttu-id="0ed36-507">在 Kiosk 模式中使用新的設定和 Edge 應用程式</span><span class="sxs-lookup"><span data-stu-id="0ed36-507">Use the new Settings and Edge apps in Kiosk modes</span></span>

<span data-ttu-id="0ed36-508">在 [Kiosks](hololens-kiosk.md)中加入應用程式時，IT 系統管理員通常會將應用程式新增到 Kiosk，但使用其應用程式使用者模型識別碼 (AUMID) 。</span><span class="sxs-lookup"><span data-stu-id="0ed36-508">When including apps in [Kiosks](hololens-kiosk.md), an IT Admin often adds the app to the Kiosk but using it's App User Model ID (AUMID).</span></span> <span data-ttu-id="0ed36-509">因為設定應用程式和 Microsoft Edge 應用程式都視為新的應用程式，而且不同于那些應用程式使用 AUMIDs 的舊版 App Kiosk，因此必須更新以使用新的 AUMID。</span><span class="sxs-lookup"><span data-stu-id="0ed36-509">Because both the Settings app and Microsoft Edge app are considered new apps and different than the older apps Kiosks that use AUMIDs for those apps will need to be updated to use the new AUMID.</span></span>

<span data-ttu-id="0ed36-510">修改 Kiosk 以包含新 App 時，建議您新增新 AUMID，並離開舊的 AUMID。</span><span class="sxs-lookup"><span data-stu-id="0ed36-510">When modifying a Kiosk to include the new apps, we recommend adding in the new AUMID as well as leaving the old one.</span></span> <span data-ttu-id="0ed36-511">這可讓使用者在更新作業系統時輕鬆進行轉換，而且不需要收到新政策，就如預期一樣持續使用 Kiosk。</span><span class="sxs-lookup"><span data-stu-id="0ed36-511">This will create an easy transition when users update the OS and won't need to receive new policies to keep using the Kiosk as intended.</span></span>

| <span data-ttu-id="0ed36-512">應用程式</span><span class="sxs-lookup"><span data-stu-id="0ed36-512">App</span></span>                    | <span data-ttu-id="0ed36-513">AUMID</span><span class="sxs-lookup"><span data-stu-id="0ed36-513">AUMID</span></span>                                                  |
|------------------------|--------------------------------------------------------|
| <span data-ttu-id="0ed36-514">舊設定應用程式</span><span class="sxs-lookup"><span data-stu-id="0ed36-514">Old Settings App</span></span>       | <span data-ttu-id="0ed36-515">HolographicSystemSettings_cw5n1h2txyewy！應用程式</span><span class="sxs-lookup"><span data-stu-id="0ed36-515">HolographicSystemSettings_cw5n1h2txyewy!App</span></span>            |
| <span data-ttu-id="0ed36-516">新增設定應用程式</span><span class="sxs-lookup"><span data-stu-id="0ed36-516">New Settings App</span></span>       | <span data-ttu-id="0ed36-517">BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy！應用程式</span><span class="sxs-lookup"><span data-stu-id="0ed36-517">BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App</span></span> |
| <span data-ttu-id="0ed36-518">舊的 Microsoft Edge 應用程式</span><span class="sxs-lookup"><span data-stu-id="0ed36-518">Old Microsoft Edge app</span></span> | <span data-ttu-id="0ed36-519">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span><span class="sxs-lookup"><span data-stu-id="0ed36-519">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span></span>    |
| <span data-ttu-id="0ed36-520">新的 Microsoft Edge 應用程式</span><span class="sxs-lookup"><span data-stu-id="0ed36-520">New Microsoft Edge app</span></span> | <span data-ttu-id="0ed36-521">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE</span><span class="sxs-lookup"><span data-stu-id="0ed36-521">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE</span></span>    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a><span data-ttu-id="0ed36-522">資訊站模式行為變更處理失敗</span><span class="sxs-lookup"><span data-stu-id="0ed36-522">Kiosk mode behavior changes for handling of failures</span></span>

<span data-ttu-id="0ed36-523">在較舊的建立中，如果裝置有資訊站組式 ，這是全域指派的存取權和 AAD 群組成員指派存取權的組合，如果決定 AAD 群組成員資格失敗，使用者[](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)會看到「開始」功能表中沒有顯示任何內容。</span><span class="sxs-lookup"><span data-stu-id="0ed36-523">In older builds, if a device had a kiosk configuration, which is a combination of both global assigned access and AAD group member assigned access, if determining AAD group membership failed, the user would see “[nothing shown in start](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)” menu.</span></span>

<span data-ttu-id="0ed36-524">從 Windows 測試人員發行開始，如果 AAD 群組資訊站模式失敗 (資訊站) 資訊站體驗會備份到全域資訊站組配置。</span><span class="sxs-lookup"><span data-stu-id="0ed36-524">Starting in Windows Insider release, the kiosk experience will fallback to global kiosk configuration (if present) in case of failures during AAD group kiosk mode.</span></span>

### <a name="new-settingsuris-for-page-settings-visibility"></a><span data-ttu-id="0ed36-525">頁面設定可見度的新設定URIS</span><span class="sxs-lookup"><span data-stu-id="0ed36-525">New SettingsURIs for Page Settings Visibility</span></span>

<span data-ttu-id="0ed36-526">在 [Windows 全攝影版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 中，我們新增 [了設定/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) 政策，以限制在設定應用程式內看到的頁面。</span><span class="sxs-lookup"><span data-stu-id="0ed36-526">In [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) we added the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="0ed36-527">PageVisibilityList 為一種原則，可讓 IT 系統管理員禁止顯示或存取 [系統設定] 應用程式中的特定頁面，或對特定頁面外的所有頁面執行此動作。</span><span class="sxs-lookup"><span data-stu-id="0ed36-527">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

<span data-ttu-id="0ed36-528">如果您流覽 [頁面設定可見度](settings-uri-list.md)，您可以找到使用此 CSP 的指示，以及先前版本中提供的 URI 清單。</span><span class="sxs-lookup"><span data-stu-id="0ed36-528">If you visit [Page Settings Visibility](settings-uri-list.md), you can find instructions to use this CSP and the list of URIs available in previous releases.</span></span>

<span data-ttu-id="0ed36-529">在 Windows 測試人員建立中，我們正在展開可用的設定 URI 清單清單，IT 系統管理員可以管理該清單。</span><span class="sxs-lookup"><span data-stu-id="0ed36-529">In Windows Insider builds we are expanding upon the list of list of available Settings URIs, which IT Admins can manage.</span></span> <span data-ttu-id="0ed36-530">其中一些 URI 適用于新設定應用程式內的新可用區域。</span><span class="sxs-lookup"><span data-stu-id="0ed36-530">Some of these URIs are for newly available areas within the new Settings app.</span></span> <span data-ttu-id="0ed36-531">如果您使用的是設定/PageVisibilityList 策略，請查閱下列清單，並根據需要調整允許或封鎖的頁面。</span><span class="sxs-lookup"><span data-stu-id="0ed36-531">If you are using Settings/PageVisibilityList policy, review the following list and adjust your allowed or blocked pages as needed.</span></span>

> [!NOTE]
> **<span data-ttu-id="0ed36-532">已替代：ms-settings：network-Proxy</span><span class="sxs-lookup"><span data-stu-id="0ed36-532">Deprecated: ms-settings:network-proxy</span></span>**
>
> <span data-ttu-id="0ed36-533">在這些較新的版本內，有一個設定頁面已由它所替代。</span><span class="sxs-lookup"><span data-stu-id="0ed36-533">One settings page is deprecated in these newer builds.</span></span> <span data-ttu-id="0ed36-534">已不再**提供&** Internet  >  **Proxy**頁面做為全域設定。</span><span class="sxs-lookup"><span data-stu-id="0ed36-534">The old **Network & Internet** > **Proxy** page is no longer available as a global setting.</span></span> <span data-ttu-id="0ed36-535">您可以在 Network & **Internet**  >  **Wi-Fi**屬性或網際網路乙太網路屬性&找到新的每  >  \*\* \*\* **&**  >  \*\*\*\*  >  **設定**。</span><span class="sxs-lookup"><span data-stu-id="0ed36-535">The new per-connection proxy settings can be found under **Network & Internet** > **Wi-Fi** > **Properties** or **Network & Internet** > **Ethernet** > **Properties**.</span></span>

<br>

| <span data-ttu-id="0ed36-536">設定頁面</span><span class="sxs-lookup"><span data-stu-id="0ed36-536">Settings page</span></span>                                        | <span data-ttu-id="0ed36-537">URI</span><span class="sxs-lookup"><span data-stu-id="0ed36-537">URI</span></span>                                              |
|------------------------------------------------------|--------------------------------------------------|
| <span data-ttu-id="0ed36-538">應用程式>應用程式&功能</span><span class="sxs-lookup"><span data-stu-id="0ed36-538">Apps > Apps & features</span></span>                               | `ms-settings:appsfeatures`                         |
| <span data-ttu-id="0ed36-539">應用程式>應用程式&進>選項的功能</span><span class="sxs-lookup"><span data-stu-id="0ed36-539">Apps > Apps & features > Advanced options</span></span>          | `ms-settings:appsfeatures-app`                     |
| <span data-ttu-id="0ed36-540">離線>應用程式</span><span class="sxs-lookup"><span data-stu-id="0ed36-540">Apps > Offline maps</span></span>                                  | `ms-settings:maps`                                 |
| <span data-ttu-id="0ed36-541">離線>應用程式>下載地圖</span><span class="sxs-lookup"><span data-stu-id="0ed36-541">Apps > Offline maps > Download maps</span></span>                  | `ms-settings:maps-downloadmaps`                    |
| <span data-ttu-id="0ed36-542">使用滑鼠>裝置</span><span class="sxs-lookup"><span data-stu-id="0ed36-542">Devices > Mouse</span></span>                                      | `ms-settings:mouse`                                |
| <span data-ttu-id="0ed36-543">USB >裝置</span><span class="sxs-lookup"><span data-stu-id="0ed36-543">Devices > USB</span></span>                                        | `ms-settings:usb`                                  |
| <span data-ttu-id="0ed36-544">網路&網際網路>飛航模式</span><span class="sxs-lookup"><span data-stu-id="0ed36-544">Network & Internet > Airplane mode</span></span>                   | `ms-settings:network-airplanemode`                 |
| <span data-ttu-id="0ed36-545">隱私權>一般</span><span class="sxs-lookup"><span data-stu-id="0ed36-545">Privacy > General</span></span>                                    | `ms-settings:privacy-general`                      |
| <span data-ttu-id="0ed36-546">輸入>筆&隱私權</span><span class="sxs-lookup"><span data-stu-id="0ed36-546">Privacy > Ink & typing personalization</span></span>             | `ms-settings:privacy-speechtyping`                 |
| <span data-ttu-id="0ed36-547">隱私權>動作</span><span class="sxs-lookup"><span data-stu-id="0ed36-547">Privacy > Motion</span></span>                                     | `ms-settings:privacy-motion`                       |
| <span data-ttu-id="0ed36-548">隱私權>螢幕擷取畫面邊框</span><span class="sxs-lookup"><span data-stu-id="0ed36-548">Privacy > Screenshot borders</span></span>                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| <span data-ttu-id="0ed36-549">螢幕>和應用程式的隱私權</span><span class="sxs-lookup"><span data-stu-id="0ed36-549">Privacy > Screenshots and apps</span></span>                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| <span data-ttu-id="0ed36-550">系統>電池</span><span class="sxs-lookup"><span data-stu-id="0ed36-550">System > Battery</span></span>                                     | `ms-settings:batterysaver`                         |
| <span data-ttu-id="0ed36-551">系統>電池</span><span class="sxs-lookup"><span data-stu-id="0ed36-551">System > Battery</span></span>                                     | `ms-settings:batterysaver-settings`                |
| <span data-ttu-id="0ed36-552">系統>音效</span><span class="sxs-lookup"><span data-stu-id="0ed36-552">System > Sound</span></span>                                       | `ms-settings:sound`                                |
| <span data-ttu-id="0ed36-553">系統>音效> App 音量和裝置喜好設定</span><span class="sxs-lookup"><span data-stu-id="0ed36-553">System > Sound > App volume and device preferences</span></span> | `ms-settings:apps-volume`                          |
| <span data-ttu-id="0ed36-554">系統>音效>管理音效裝置</span><span class="sxs-lookup"><span data-stu-id="0ed36-554">System > Sound > Manage sound   devices</span></span>              | `ms-settings:sound-devices`                        |
| <span data-ttu-id="0ed36-555">系統>儲存空間>設定儲存感知</span><span class="sxs-lookup"><span data-stu-id="0ed36-555">System > Storage > Configure Storage Sense</span></span>         | `ms-settings:storagepolicies`                      |
| <span data-ttu-id="0ed36-556">語言&日期>時間&時間</span><span class="sxs-lookup"><span data-stu-id="0ed36-556">Time & Language > Date & time</span></span>                        | `ms-settings:dateandtime`                          |
| <span data-ttu-id="0ed36-557">語言&鍵盤>時間</span><span class="sxs-lookup"><span data-stu-id="0ed36-557">Time & Language > Keyboard</span></span>                           | `ms-settings:keyboard`                             |
| <span data-ttu-id="0ed36-558">語言&時間>語言</span><span class="sxs-lookup"><span data-stu-id="0ed36-558">Time & Language > Language</span></span>                           | `ms-settings:language`                             |
| <span data-ttu-id="0ed36-559">語言&時間>語言</span><span class="sxs-lookup"><span data-stu-id="0ed36-559">Time & Language > Language</span></span>                           | `ms-settings:regionlanguage-languageoptions`       |
| <span data-ttu-id="0ed36-560">更新&安全性>重&復原</span><span class="sxs-lookup"><span data-stu-id="0ed36-560">Update & Security > Reset & recovery</span></span>               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a><span data-ttu-id="0ed36-561">更新的 URI</span><span class="sxs-lookup"><span data-stu-id="0ed36-561">Updated URIs</span></span>

<span data-ttu-id="0ed36-562">之前，下列兩個 URI 不會將使用者直接帶至指示的頁面，但只會封鎖主要更新頁面。</span><span class="sxs-lookup"><span data-stu-id="0ed36-562">Previously the following two URIs would not take a user directly to the pages indicated but only blocked the main updates page.</span></span> <span data-ttu-id="0ed36-563">下列專案已更新為直接顯示至其頁面：</span><span class="sxs-lookup"><span data-stu-id="0ed36-563">The following items have been updated to direct to their pages:</span></span>

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a><span data-ttu-id="0ed36-564">透過設定應用程式設定後背診斷</span><span class="sxs-lookup"><span data-stu-id="0ed36-564">Configuring Fallback Diagnostics via Settings app</span></span>

<span data-ttu-id="0ed36-565">現在，在設定 App 中，使用者可以設定 [後背診斷的行為](hololens-diagnostic-logs.md)。</span><span class="sxs-lookup"><span data-stu-id="0ed36-565">Now in Settings App, a user can configure the behavior of [Fallback Diagnostics](hololens-diagnostic-logs.md).</span></span> <span data-ttu-id="0ed36-566">在設定 App 中流覽至**隱私權**  ->  **疑難排解頁面**以設定此設定。</span><span class="sxs-lookup"><span data-stu-id="0ed36-566">In the Settings app navigate to **Privacy** -> **Troubleshooting** page to configure this setting.</span></span>

> [!NOTE]
> <span data-ttu-id="0ed36-567">如果有針對裝置所配置的 MDM 規則，使用者將無法覆蓋該行為。</span><span class="sxs-lookup"><span data-stu-id="0ed36-567">If there is MDM policy configured for the device, user will not be able to override that behavior.</span></span>  

### <a name="share-things-with-nearby-devices"></a><span data-ttu-id="0ed36-568">與附近的裝置共用專案</span><span class="sxs-lookup"><span data-stu-id="0ed36-568">Share things with nearby devices</span></span>

<span data-ttu-id="0ed36-569">與 Windows 10 裝置附近共用專案，包括執行 HoloLens Insider builds 20279.1006+ 的 PC 和其他 HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="0ed36-569">Share things with near by Windows 10 devices, including both PCs and other HoloLens 2 devices running HoloLens Insider builds 20279.1006+.</span></span> <span data-ttu-id="0ed36-570">您可以在設定**系統共用體驗**中試用，以將 HoloLens 的檔案或  ->  \*\*\*\*  ->  \*\* \*\*URL 共用至電腦。</span><span class="sxs-lookup"><span data-stu-id="0ed36-570">You can try it out in **Settings** -> **System** -> **Shared Experiences** to share files or URLs from a HoloLens to a PC.</span></span> <span data-ttu-id="0ed36-571">若要進一步閱讀詳細資料，請參閱如何在 [Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)中與附近的裝置共用專案。</span><span class="sxs-lookup"><span data-stu-id="0ed36-571">For more details read more about how to [Share things with nearby devices in Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).</span></span>

<span data-ttu-id="0ed36-572">此功能可透過 [Connectivity/AllowConnectedDevices 管理](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)。</span><span class="sxs-lookup"><span data-stu-id="0ed36-572">This feature can be managed via [Connectivity/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).</span></span>

### <a name="new-os-update-troubleshooter"></a><span data-ttu-id="0ed36-573">新的 OS Update 疑難排解員</span><span class="sxs-lookup"><span data-stu-id="0ed36-573">New OS Update troubleshooter</span></span>

<span data-ttu-id="0ed36-574">除了設定應用程式中先前的疑難排解員之外，我們新增了新的疑難排解員，並新增了 OS 更新的新設定應用程式。</span><span class="sxs-lookup"><span data-stu-id="0ed36-574">In addition to the previous troubleshooters within the Settings app, a new troubleshooter has been added with the addition of the new Settings app for OS Updates.</span></span> <span data-ttu-id="0ed36-575">流覽至**設定**  ->  **更新 &amp; 安全性**  >  **疑難排解**  >  **Windows Update，** 然後選取開始。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0ed36-575">Navigate to **Settings** -> **Update &amp; Security** > **Troubleshoot** > **Windows Update** and select **Start**.</span></span> <span data-ttu-id="0ed36-576">這可讓您在重現作業系統更新問題時收集追蹤，以協助您針對 IT 或支援進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="0ed36-576">This allows you to collect traces while reproducing your issue with OS Updates to assist better in troubleshooting with your IT or support.</span></span>

### <a name="delivery-optimization-preview"></a><span data-ttu-id="0ed36-577">傳遞優化預覽</span><span class="sxs-lookup"><span data-stu-id="0ed36-577">Delivery Optimization Preview</span></span>

<span data-ttu-id="0ed36-578">在此 HoloLens 測試人員更新中，商務用 Windows Holographic 可針對傳遞優化設定提供早期預覽，以減少從多個 HoloLens 裝置下載的頻寬耗用。</span><span class="sxs-lookup"><span data-stu-id="0ed36-578">With this HoloLens Insider update, Windows Holographic for Business enables an early preview for delivery optimization settings to reduce bandwidth consumption for downloads from multiple HoloLens devices.</span></span> <span data-ttu-id="0ed36-579">以下提供此功能的完整描述以及建議的網路組 [配置：Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)的傳遞優化更新。</span><span class="sxs-lookup"><span data-stu-id="0ed36-579">A fuller description of this functionality along with the recommended network configuration is available here: [Delivery Optimization for Windows 10 updates](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization).</span></span>

<span data-ttu-id="0ed36-580">下列設定會做為管理表的一部分啟用， [而且可以從 Intune 進行設定](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)：</span><span class="sxs-lookup"><span data-stu-id="0ed36-580">The following settings are enabled as part of the management surface and [can be configured from Intune](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings):</span></span>

- [<span data-ttu-id="0ed36-581">DOCacheHost</span><span class="sxs-lookup"><span data-stu-id="0ed36-581">DOCacheHost</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [<span data-ttu-id="0ed36-582">DOCacheHostSource</span><span class="sxs-lookup"><span data-stu-id="0ed36-582">DOCacheHostSource</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [<span data-ttu-id="0ed36-583">DODelayCacheServerFallbackBackground</span><span class="sxs-lookup"><span data-stu-id="0ed36-583">DODelayCacheServerFallbackBackground</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [<span data-ttu-id="0ed36-584">DODelayCacheServerFallbackForeground</span><span class="sxs-lookup"><span data-stu-id="0ed36-584">DODelayCacheServerFallbackForeground</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [<span data-ttu-id="0ed36-585">DODownloadMode</span><span class="sxs-lookup"><span data-stu-id="0ed36-585">DODownloadMode</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [<span data-ttu-id="0ed36-586">DOMaxBackgroundDownloadBandwidth</span><span class="sxs-lookup"><span data-stu-id="0ed36-586">DOMaxBackgroundDownloadBandwidth</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [<span data-ttu-id="0ed36-587">DOMaxForegroundDownloadBandwidth</span><span class="sxs-lookup"><span data-stu-id="0ed36-587">DOMaxForegroundDownloadBandwidth</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [<span data-ttu-id="0ed36-588">DOPercentageMaxBackgroundBandwidth</span><span class="sxs-lookup"><span data-stu-id="0ed36-588">DOPercentageMaxBackgroundBandwidth</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [<span data-ttu-id="0ed36-589">DOPercentageMaxForegroundBandwidth</span><span class="sxs-lookup"><span data-stu-id="0ed36-589">DOPercentageMaxForegroundBandwidth</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [<span data-ttu-id="0ed36-590">DOSetHoursToLimitForegroundDownloadBandwidth</span><span class="sxs-lookup"><span data-stu-id="0ed36-590">DOSetHoursToLimitForegroundDownloadBandwidth</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [<span data-ttu-id="0ed36-591">DOSetHoursToLimitBackgroundDownloadBandwidth</span><span class="sxs-lookup"><span data-stu-id="0ed36-591">DOSetHoursToLimitBackgroundDownloadBandwidth</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

<span data-ttu-id="0ed36-592">關於此預覽版方案，有一些警告：</span><span class="sxs-lookup"><span data-stu-id="0ed36-592">A few caveats about this preview offering:</span></span>

- <span data-ttu-id="0ed36-593">HoloLens 支援在此預覽版中僅限於作業系統更新。</span><span class="sxs-lookup"><span data-stu-id="0ed36-593">HoloLens support is limited in this preview to OS updates only.</span></span>
- <span data-ttu-id="0ed36-594">商務用 Windows 全圖僅支援 HTTP 下載模式，以及 [從 Microsoft 連結的緩存端點下載](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache);HoloLens 裝置目前不支援對等下載模式和群組指派。</span><span class="sxs-lookup"><span data-stu-id="0ed36-594">Windows Holographic for Business only supports HTTP download modes and downloads from a [Microsoft Connected Cache endpoint](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache); peer-to-peer download modes and group assignments are not supported for HoloLens devices at this time.</span></span>
- <span data-ttu-id="0ed36-595">HoloLens 不支援 Windows Server Update Services 端點的部署或傳遞優化。</span><span class="sxs-lookup"><span data-stu-id="0ed36-595">HoloLens does not support deployment or delivery optimization for Windows Server Update Services endpoints.</span></span>
- <span data-ttu-id="0ed36-596">疑難排解會要求在已連接的快取伺服器上進行診斷，或透過 Windows Update 的設定更新或安全性疑難\*\*\*\* 解答& HoloLens 上的追蹤  >  \*\*\*\*  >   \*\*\*\*  >   \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="0ed36-596">Troubleshooting will require either diagnostics on the Connected Cache server or collecting a trace on HoloLens on HoloLens via **Settings** > **Update & Security** >  **Troubleshooting** >  **Windows Update**.</span></span>

### <a name="improvements-and-fixes-in-the-update"></a><span data-ttu-id="0ed36-597">更新中的改良與修正：</span><span class="sxs-lookup"><span data-stu-id="0ed36-597">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="0ed36-598">[離線診斷](hololens-diagnostic-logs.md#offline-diagnostics) 也會包含序號和作業系統版本的其他裝置資訊。</span><span class="sxs-lookup"><span data-stu-id="0ed36-598">[Offline diagnostics](hololens-diagnostic-logs.md#offline-diagnostics) will also include additional device information for serial number and OS version.</span></span>






## <a name="start-receiving-insider-builds"></a><span data-ttu-id="0ed36-599">開始接收測試人員建立</span><span class="sxs-lookup"><span data-stu-id="0ed36-599">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="0ed36-600">如果您最近未更新，請重新開機裝置以更新狀態並取得最新版。</span><span class="sxs-lookup"><span data-stu-id="0ed36-600">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="0ed36-601">「重新開機裝置」語音命令運作正常。</span><span class="sxs-lookup"><span data-stu-id="0ed36-601">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="0ed36-602">您也可以選擇設定/Windows Insider Program 中的重新開機按鈕。</span><span class="sxs-lookup"><span data-stu-id="0ed36-602">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="0ed36-603">我們在後端遇到您可能會遇到的錯誤，這將會讓系統復原正軌。</span><span class="sxs-lookup"><span data-stu-id="0ed36-603">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="0ed36-604">在 HoloLens 2 裝置\*\*\*\* 上，& Windows 測試人員計畫的設定更新，然後  >  \*\*\*\*  >  \*\*\*\* 選取開始。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0ed36-604">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="0ed36-605">連結您用來註冊為 Windows Insider 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="0ed36-605">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="0ed36-606">Windows Insider 目前正在移往頻道。</span><span class="sxs-lookup"><span data-stu-id="0ed36-606">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="0ed36-607">快速**通道**會變成**開發人員**通道，慢速通道會變成\*\*\*\*\*\*Beta**通道，而發行**預覽**通道將會變成**發行預覽通道\*\*。</span><span class="sxs-lookup"><span data-stu-id="0ed36-607">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="0ed36-608">以下是該地圖的外觀：</span><span class="sxs-lookup"><span data-stu-id="0ed36-608">Here is what that mapping looks like:</span></span>

![Windows Insider Channels 說明](images/WindowsInsiderChannels.png)

<span data-ttu-id="0ed36-610">詳細資訊請參閱 Windows 部落格上的 [Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 介紹。</span><span class="sxs-lookup"><span data-stu-id="0ed36-610">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>

<span data-ttu-id="0ed36-611">然後，選取 **Windows 的主動**開發，選擇您是否要接收 **開發通道** 或 **Beta 通道** 版本，並審查計畫條款。</span><span class="sxs-lookup"><span data-stu-id="0ed36-611">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="0ed36-612">選取 **確認>立即重新開機** 以完成。</span><span class="sxs-lookup"><span data-stu-id="0ed36-612">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="0ed36-613">重新開機裝置之後，請>更新& **安全性>檢查更新** 以取得最新版。</span><span class="sxs-lookup"><span data-stu-id="0ed36-613">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="0ed36-614">更新錯誤0x80070490處理</span><span class="sxs-lookup"><span data-stu-id="0ed36-614">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="0ed36-615">如果您在更新 Dev 或 Beta 0x80070490時遇到更新錯誤，請嘗試下列短期工作。</span><span class="sxs-lookup"><span data-stu-id="0ed36-615">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="0ed36-616">這涉及移動您的測試人員通道、選取更新，然後將您的測試人員通道移回。</span><span class="sxs-lookup"><span data-stu-id="0ed36-616">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>

#### <a name="stage-one---release-preview"></a><span data-ttu-id="0ed36-617">階段 1 - 發行預覽版</span><span class="sxs-lookup"><span data-stu-id="0ed36-617">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="0ed36-618">設定、更新&、Windows Insider Program、選取 **發行預覽通道**。</span><span class="sxs-lookup"><span data-stu-id="0ed36-618">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="0ed36-619">設定、更新&安全性、Windows **Update、檢查更新**。</span><span class="sxs-lookup"><span data-stu-id="0ed36-619">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="0ed36-620">更新之後，請繼續到階段 2。</span><span class="sxs-lookup"><span data-stu-id="0ed36-620">After the update, continue on to Stage two.</span></span>

#### <a name="stage-two---dev-channel"></a><span data-ttu-id="0ed36-621">階段 2 - 開發人員通道</span><span class="sxs-lookup"><span data-stu-id="0ed36-621">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="0ed36-622">設定、更新&、Windows 測試人員計畫、選取 **開發人員通道**。</span><span class="sxs-lookup"><span data-stu-id="0ed36-622">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="0ed36-623">設定、更新&安全性、Windows **Update、檢查更新**。</span><span class="sxs-lookup"><span data-stu-id="0ed36-623">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>

## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="0ed36-624">FFU 下載和快速指示</span><span class="sxs-lookup"><span data-stu-id="0ed36-624">FFU download and flash directions</span></span>
<span data-ttu-id="0ed36-625">若要使用已簽署 Ffu 的班機測試，您首先必須先將裝置解除鎖定，才能閃爍已簽署之航班的 ffu。</span><span class="sxs-lookup"><span data-stu-id="0ed36-625">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="0ed36-626">在 PC 上：</span><span class="sxs-lookup"><span data-stu-id="0ed36-626">On PC:</span></span>

    1. <span data-ttu-id="0ed36-627">從 下載 ffu 到您的電腦 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。</span><span class="sxs-lookup"><span data-stu-id="0ed36-627">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="0ed36-628">從 Microsoft store (ARC) 進一步修復小夥伴 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) ：.</span><span class="sxs-lookup"><span data-stu-id="0ed36-628">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="0ed36-629">在 HoloLens - 航班解除鎖定 **：開啟設定**更新  >  **&**  >  **安全性 Windows 測試人員計畫**，然後註冊、重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="0ed36-629">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="0ed36-630">Flash FFU - 現在您可以使用 ARC 快速閃爍正式航班簽署的 FFU。</span><span class="sxs-lookup"><span data-stu-id="0ed36-630">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

## <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="0ed36-631">提供意見回饋與報告問題</span><span class="sxs-lookup"><span data-stu-id="0ed36-631">Provide feedback and report issues</span></span>

<span data-ttu-id="0ed36-632">請使用 [HoloLens](hololens-feedback.md) 上的意見回饋中樞應用程式，提供意見回饋及報告問題。</span><span class="sxs-lookup"><span data-stu-id="0ed36-632">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="0ed36-633">使用意見中樞可確保包含所有必要的診斷資訊，協助我們的工程師快速進行診斷並解決問題。</span><span class="sxs-lookup"><span data-stu-id="0ed36-633">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="0ed36-634">中文版和日文版的 HoloLens 問題應該以相同方式報告。</span><span class="sxs-lookup"><span data-stu-id="0ed36-634">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="0ed36-635">請務必接受詢問您是否希望意見回應中樞存取您的檔資料夾的提示， (系統提示時選取) 。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0ed36-635">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <a name="note-for-developers"></a><span data-ttu-id="0ed36-636">開發人員注意事項</span><span class="sxs-lookup"><span data-stu-id="0ed36-636">Note for developers</span></span>

<span data-ttu-id="0ed36-637">歡迎並鼓勵您嘗試使用 HoloLens 測試人員建立來開發您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="0ed36-637">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="0ed36-638">請參閱 [HoloLens 開發人員檔](https://developer.microsoft.com/windows/mixed-reality/development) 以開始使用。</span><span class="sxs-lookup"><span data-stu-id="0ed36-638">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="0ed36-639">這些相同的指示可與 HoloLens 測試人員建立一起使用。</span><span class="sxs-lookup"><span data-stu-id="0ed36-639">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="0ed36-640">您可以使用與 HoloLens 開發中一樣使用的同一個單一和 Visual Studio 版本。</span><span class="sxs-lookup"><span data-stu-id="0ed36-640">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="0ed36-641">停止接收測試人員建立</span><span class="sxs-lookup"><span data-stu-id="0ed36-641">Stop receiving Insider builds</span></span>

<span data-ttu-id="0ed36-642">如果您不想再收到 Windows 全攝影版的測試人員版本，您可以選擇在 HoloLens 執行生產版時退出，或者您可以使用進一步[](hololens-recovery.md)修復小夥伴復原您的裝置，將裝置復原為非測試人員版本的 Windows 全攝影版。</span><span class="sxs-lookup"><span data-stu-id="0ed36-642">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="0ed36-643">有一個已知問題，在手動重新安裝全新預覽版之後，從 Insider Preview 版本取消註冊的使用者會遇到藍色畫面。</span><span class="sxs-lookup"><span data-stu-id="0ed36-643">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="0ed36-644">之後，他們必須手動復原裝置。</span><span class="sxs-lookup"><span data-stu-id="0ed36-644">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="0ed36-645">如需有關您是否會受到影響的完整詳細資料，請進一步查看此 [已知問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)。</span><span class="sxs-lookup"><span data-stu-id="0ed36-645">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="0ed36-646">若要確認您的 HoloLens 正在進行生產建立：</span><span class="sxs-lookup"><span data-stu-id="0ed36-646">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="0ed36-647">請前往 **系統>的>，** 並尋找建組編號。</span><span class="sxs-lookup"><span data-stu-id="0ed36-647">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="0ed36-648">[請參閱生產版組號版本資訊](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="0ed36-648">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="0ed36-649">若要退出測試人員建立：</span><span class="sxs-lookup"><span data-stu-id="0ed36-649">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="0ed36-650">在執行生產建制的 HoloLens 上，> Windows 測試人員計畫 **&更新>，** 然後選取停止測試人員 **建立**。</span><span class="sxs-lookup"><span data-stu-id="0ed36-650">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="0ed36-651">請遵循指示退出宣告您的裝置。</span><span class="sxs-lookup"><span data-stu-id="0ed36-651">Follow the instructions to opt out your device.</span></span>
