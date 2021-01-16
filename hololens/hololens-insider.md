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
ms.date: 1/13/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 6df24d3a8640edeb9196834f940500aa51e85af7
ms.sourcegitcommit: 50e4d61a31b94d5007776064b4012e26cf9ecbbb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271698"
---
# <span data-ttu-id="a836f-103">適用於 Microsoft HoloLens 的 Insider Preview</span><span class="sxs-lookup"><span data-stu-id="a836f-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="a836f-104">歡迎使用 HoloLens 的最新 Insider Preview 組建！</span><span class="sxs-lookup"><span data-stu-id="a836f-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="a836f-105">[開始](hololens-insider.md#start-receiving-insider-builds)使用並為我們的下一個重要作業系統更新提供寶貴的意見反應，這是一件簡單的工作。</span><span class="sxs-lookup"><span data-stu-id="a836f-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <span data-ttu-id="a836f-106">Windows 測試人員版本資訊</span><span class="sxs-lookup"><span data-stu-id="a836f-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="a836f-107">我們很高興能再次開始將新功能正式給 Windows 測試人員。</span><span class="sxs-lookup"><span data-stu-id="a836f-107">We are excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="a836f-108">我們將會正式至開發人員通道，以取得最新的更新。</span><span class="sxs-lookup"><span data-stu-id="a836f-108">We will be flighting to the Dev Channel for the latest updates.</span></span> <span data-ttu-id="a836f-109">我們會繼續更新此頁面，因為我們會在我們的 Windows 測試人員組建中新增更多功能與更新。</span><span class="sxs-lookup"><span data-stu-id="a836f-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span>  <span data-ttu-id="a836f-110">令您興奮並準備好將這些更新混合在您的現實中。</span><span class="sxs-lookup"><span data-stu-id="a836f-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="a836f-111">功能名稱</span><span class="sxs-lookup"><span data-stu-id="a836f-111">Feature Name</span></span>                                              | <span data-ttu-id="a836f-112">簡短描述</span><span class="sxs-lookup"><span data-stu-id="a836f-112">Short description</span></span>                                                                      | <span data-ttu-id="a836f-113">可在組建中使用</span><span class="sxs-lookup"><span data-stu-id="a836f-113">Available in build</span></span> |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [<span data-ttu-id="a836f-114">新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a836f-114">New Microsoft Edge</span></span>](#introducing-the-new-microsoft-edge) | <span data-ttu-id="a836f-115">新的、以 Chromium 為基礎的 Microsoft Edge 現已提供于 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="a836f-115">The new, Chromium-based Microsoft Edge is now available for HoloLens 2</span></span>                         | <span data-ttu-id="a836f-116">20279.1006</span><span class="sxs-lookup"><span data-stu-id="a836f-116">20279.1006</span></span> |
| [<span data-ttu-id="a836f-117">新的 [設定] 應用程式</span><span class="sxs-lookup"><span data-stu-id="a836f-117">New Settings app</span></span>](#new-settings-app)                     | <span data-ttu-id="a836f-118">舊版設定應用程式將由含新功能和設定的更新版本取代</span><span class="sxs-lookup"><span data-stu-id="a836f-118">The legacy Settings app is being replaced by an updated version with new features and settings</span></span> | <span data-ttu-id="a836f-119">20279.1006</span><span class="sxs-lookup"><span data-stu-id="a836f-119">20279.1006</span></span> |
| [<span data-ttu-id="a836f-120">預設的應用程式選擇器</span><span class="sxs-lookup"><span data-stu-id="a836f-120">Default app picker</span></span>](#default-app-picker)                 | <span data-ttu-id="a836f-121">針對每個檔案或連結類型選擇要啟動的應用程式</span><span class="sxs-lookup"><span data-stu-id="a836f-121">Choose which app should launch for each file or link type</span></span>                                      | <span data-ttu-id="a836f-122">20279.1006</span><span class="sxs-lookup"><span data-stu-id="a836f-122">20279.1006</span></span> |
| [<span data-ttu-id="a836f-123">Office web app</span><span class="sxs-lookup"><span data-stu-id="a836f-123">Office web app</span></span>](#office-web-app)                         | <span data-ttu-id="a836f-124">Office web app 的快捷方式現已列在 [所有應用程式] 中。</span><span class="sxs-lookup"><span data-stu-id="a836f-124">A shortcut to the Office web app is now listed in "All apps"</span></span>                                   | <span data-ttu-id="a836f-125">20279.1006</span><span class="sxs-lookup"><span data-stu-id="a836f-125">20279.1006</span></span> |
| [<span data-ttu-id="a836f-126">向類型滑動</span><span class="sxs-lookup"><span data-stu-id="a836f-126">Swipe to type</span></span>](#swipe-to-type)                           | <span data-ttu-id="a836f-127">使用手指的秘訣在全息鍵盤上「滑動」字</span><span class="sxs-lookup"><span data-stu-id="a836f-127">Use the tip of your finger to "swipe" words on the holographic keyboard</span></span>                        | <span data-ttu-id="a836f-128">20279.1006</span><span class="sxs-lookup"><span data-stu-id="a836f-128">20279.1006</span></span> |
| [<span data-ttu-id="a836f-129">USB-C 外部麥克風支援</span><span class="sxs-lookup"><span data-stu-id="a836f-129">USB-C External Microphone Support</span></span>](#usb-c-external-microphone-support) | <span data-ttu-id="a836f-130">針對 app 和/或遠端協助使用 USB-C 麥克風。</span><span class="sxs-lookup"><span data-stu-id="a836f-130">Use USB-C microphones for apps and / or Remote Assist.</span></span>| <span data-ttu-id="a836f-131">20279.1006</span><span class="sxs-lookup"><span data-stu-id="a836f-131">20279.1006</span></span> |
| [<span data-ttu-id="a836f-132">在 Kiosk 模式中新應用程式的新 Aumid</span><span class="sxs-lookup"><span data-stu-id="a836f-132">New AUMIDs for new apps in Kiosk mode</span></span>](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | <span data-ttu-id="a836f-133">新設定與邊緣 app 的 Aumid</span><span class="sxs-lookup"><span data-stu-id="a836f-133">AUMIDs for new Settings and Edge apps</span></span> | <span data-ttu-id="a836f-134">20279.1006</span><span class="sxs-lookup"><span data-stu-id="a836f-134">20279.1006</span></span> |
| [<span data-ttu-id="a836f-135">改良的 Kiosk 模式失敗處理</span><span class="sxs-lookup"><span data-stu-id="a836f-135">Improved Kiosk mode failure handing</span></span>](#kiosk-mode-behavior-changes-for-handling-of-failures) | <span data-ttu-id="a836f-136">展臺模式會在清空 [開始] 功能表前尋找全域指派的存取權。</span><span class="sxs-lookup"><span data-stu-id="a836f-136">Kiosk mode looks for Global Assigned Access before empty start menu.</span></span> | <span data-ttu-id="a836f-137">20279.1006</span><span class="sxs-lookup"><span data-stu-id="a836f-137">20279.1006</span></span> |
| [<span data-ttu-id="a836f-138">設定回退診斷</span><span class="sxs-lookup"><span data-stu-id="a836f-138">Configure Fallback Diagnostics</span></span>](#configuring-fallback-diagnostics-via-settings-app) | <span data-ttu-id="a836f-139">在 [設定] App 中設定回退診斷行為</span><span class="sxs-lookup"><span data-stu-id="a836f-139">Setting Fallback Diagnostic Behavior in Settings App</span></span> | <span data-ttu-id="a836f-140">20279.1006</span><span class="sxs-lookup"><span data-stu-id="a836f-140">20279.1006</span></span> |

### <span data-ttu-id="a836f-141">新的 Microsoft Edge 簡介</span><span class="sxs-lookup"><span data-stu-id="a836f-141">Introducing the new Microsoft Edge</span></span>

![舊版 Microsoft Edge 標誌的動畫至新的 Microsoft Edge 標誌](images/new-edge.gif)

<span data-ttu-id="a836f-143">新的 Microsoft Edge 會 [採用 Chromium 的「開啟來源」專案](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) ，為客戶建立更佳的相容性，並為 網頁程式開發人員提供較少的網路碎片。</span><span class="sxs-lookup"><span data-stu-id="a836f-143">The new Microsoft Edge [adopts the Chromium open source project](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) to create better compatibility for customers and less fragmentation of the web for web developers.</span></span>

<span data-ttu-id="a836f-144">透過此測試人員預覽版，第一次可將新的 Microsoft Edge 提供給 HoloLens 2 客戶！</span><span class="sxs-lookup"><span data-stu-id="a836f-144">With this Insider preview, the new Microsoft Edge is available to HoloLens 2 customers for the first time!</span></span> <span data-ttu-id="a836f-145">雖然新的 Microsoft Edge 最終會取代 HoloLens 2 上舊版的 Microsoft Edge，但測試人員目前都可使用這兩種瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="a836f-145">While the new Microsoft Edge will eventually replace legacy Microsoft Edge on HoloLens 2, both browsers are currently available to Insiders.</span></span> <span data-ttu-id="a836f-146">請透過新的 Microsoft Edge 或透過[意見反應中樞](hololens-feedback.md)中的 [**傳送意見**反應] 功能，與我們的小組共用意見反應和錯誤。</span><span class="sxs-lookup"><span data-stu-id="a836f-146">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge or via [Feedback Hub](hololens-feedback.md).</span></span>

![新的 Microsoft Edge 螢幕擷取畫面](images/new-edge-ui.png)

#### <span data-ttu-id="a836f-148">啟動新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a836f-148">Launching the new Microsoft Edge</span></span>

<span data-ttu-id="a836f-149">有兩個版本的 Microsoft Edge 可供測試人員使用：新的 Microsoft Edge ![ 新的 Microsoft edge 圖示 ](images/new_edge_logo.png) (以藍色和綠色的漩渦圖示) 與舊版 Microsoft edge 所代表 (由白色 "e" 圖示) 所代表。</span><span class="sxs-lookup"><span data-stu-id="a836f-149">There are two versions of Microsoft Edge available to Insiders: the new Microsoft Edge ![new Microsoft Edge icon](images/new_edge_logo.png) (represented by a blue and green swirl icon) and legacy Microsoft Edge (represented by the white "e" icon).</span></span> <span data-ttu-id="a836f-150">新的 Microsoft Edge 會釘選到 [開始] 功能表，當您啟動網頁連結時，系統會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="a836f-150">The new Microsoft Edge is pinned to the Start menu and will automatically launch when you activate a web link.</span></span> <span data-ttu-id="a836f-151">如果您想要還原為使用舊版 Microsoft Edge 做為預設的網頁瀏覽器，請參閱以下指示來 [重設預設 app](#default-app-picker)。</span><span class="sxs-lookup"><span data-stu-id="a836f-151">If you would like to revert to using legacy Microsoft Edge as your default web browser, see the instructions below for [resetting default apps](#default-app-picker).</span></span>

> [!NOTE]
> <span data-ttu-id="a836f-152">當您第一次在 HoloLens 2 上啟動新的 Microsoft Edge 時，您的設定和資料將會從舊版 Microsoft Edge 中匯入。</span><span class="sxs-lookup"><span data-stu-id="a836f-152">When you first launch the new Microsoft Edge on HoloLens 2, your settings and data will be imported from legacy Microsoft Edge.</span></span> <span data-ttu-id="a836f-153">如果您在啟動新的 Microsoft Edge 後繼續使用舊版 Microsoft Edge，新的資料將不會從舊版 Microsoft Edge 同步處理至新的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="a836f-153">If you continue to use legacy Microsoft Edge after launching the new Microsoft Edge, that new data will not be synced from legacy Microsoft Edge to the new Microsoft Edge.</span></span>

#### <span data-ttu-id="a836f-154">設定新 Microsoft Edge 的原則設定</span><span class="sxs-lookup"><span data-stu-id="a836f-154">Configuring policy settings for the new Microsoft Edge</span></span>

<span data-ttu-id="a836f-155">新的 Microsoft Edge 為 IT 管理員提供與舊版 Microsoft Edge 相比，在 HoloLens 2 上更廣泛的瀏覽器原則。</span><span class="sxs-lookup"><span data-stu-id="a836f-155">The new Microsoft Edge offers IT admins a much broader set of browser policies on HoloLens 2 than were previously available with legacy Microsoft Edge.</span></span>

<span data-ttu-id="a836f-156">以下是一些有用的資源，可讓您深入瞭解如何管理新 Microsoft Edge 的原則設定：</span><span class="sxs-lookup"><span data-stu-id="a836f-156">Here are some helpful resources for learning more about managing policy settings for the new Microsoft Edge:</span></span>

- [<span data-ttu-id="a836f-157">使用 Microsoft Intune 設定 Microsoft Edge 原則設定</span><span class="sxs-lookup"><span data-stu-id="a836f-157">Configure Microsoft Edge policy settings with Microsoft Intune</span></span>](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [<span data-ttu-id="a836f-158">舊版 Microsoft Edge 與 Microsoft Edge 的原則對應</span><span class="sxs-lookup"><span data-stu-id="a836f-158">Microsoft Edge Legacy to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [<span data-ttu-id="a836f-159">Google Chrome 與 Microsoft Edge 的原則對應</span><span class="sxs-lookup"><span data-stu-id="a836f-159">Google Chrome to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- <span data-ttu-id="a836f-160">完整的 [Microsoft Edge 企業檔](https://docs.microsoft.com/deployedge/)</span><span class="sxs-lookup"><span data-stu-id="a836f-160">Full [Microsoft Edge Enterprise documentation](https://docs.microsoft.com/deployedge/)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a836f-161">由於新 Microsoft Edge 支援的瀏覽器策略數量，我們的小組無法保證每個新原則在 HoloLens 2 上都能正常運作。</span><span class="sxs-lookup"><span data-stu-id="a836f-161">Because of the volume of browser policies supported by the new Microsoft Edge, our team is unable to guarantee that each new policy works on HoloLens 2.</span></span> <span data-ttu-id="a836f-162">不過，我們已測試並確認您先前在 HoloLens 2 上支援的每個舊版 Microsoft Edge 原則的新 Microsoft Edge 對，都會如期運作。</span><span class="sxs-lookup"><span data-stu-id="a836f-162">However, we've tested and confirmed that the new Microsoft Edge equivalent of each legacy Microsoft Edge policy previously supported on HoloLens 2 work as expected.</span></span> <span data-ttu-id="a836f-163">請參閱 microsoft [Edge 舊版至 Microsoft edge 原則對應](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) ，以找出您在 HoloLens 2 使用的每個舊版 microsoft edge 瀏覽器原則的新 Microsoft edge 對等專案。</span><span class="sxs-lookup"><span data-stu-id="a836f-163">See [Microsoft Edge Legacy to Microsoft Edge policy mapping](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) to find the new Microsoft Edge equivalent of each legacy Microsoft Edge browser policy you were using with HoloLens 2.</span></span>
>
> <span data-ttu-id="a836f-164">我們至少知道有兩個新的 Microsoft Edge 原則 *無法* 搭配 HoloLens 2 使用：</span><span class="sxs-lookup"><span data-stu-id="a836f-164">There are at least two new Microsoft Edge policies that we know *will not* work with HoloLens 2:</span></span>
> - <span data-ttu-id="a836f-165">EnterpriseModeSiteList</span><span class="sxs-lookup"><span data-stu-id="a836f-165">EnterpriseModeSiteList</span></span>
> - <span data-ttu-id="a836f-166">EnterpriseSiteListServiceURL</span><span class="sxs-lookup"><span data-stu-id="a836f-166">EnterpriseSiteListServiceURL</span></span>

#### <span data-ttu-id="a836f-167">從 HoloLens 2 上的新 Microsoft Edge 預期的目標</span><span class="sxs-lookup"><span data-stu-id="a836f-167">What to expect from the new Microsoft Edge on HoloLens 2</span></span>

<span data-ttu-id="a836f-168">由於新的 Microsoft Edge 是具有新 UWP 配接器層的原生 Win32 app，可讓它在只有 HoloLens 的裝置上執行，例如 HoloLens 2，某些功能可能無法立即使用。</span><span class="sxs-lookup"><span data-stu-id="a836f-168">Because the new Microsoft Edge is a native Win32 app with a new UWP adapter layer allowing it to run on UWP-only devices like HoloLens 2, some features may not be immediately available.</span></span> <span data-ttu-id="a836f-169">我們將在未來幾個月內支援新的案例與功能，請查看此空間以取得最新資訊。</span><span class="sxs-lookup"><span data-stu-id="a836f-169">We'll be supporting new scenarios and features over the coming months, so please check this space for up-to-date information.</span></span>

**<span data-ttu-id="a836f-170">預期會運作的案例與功能：</span><span class="sxs-lookup"><span data-stu-id="a836f-170">Scenarios and features expected to work:</span></span>**
- <span data-ttu-id="a836f-171">首次執行體驗、登入設定檔及同步處理</span><span class="sxs-lookup"><span data-stu-id="a836f-171">First-run experience, sign-in to profile, and sync</span></span>
- <span data-ttu-id="a836f-172">網站應該按照預期的方式呈現及運作</span><span class="sxs-lookup"><span data-stu-id="a836f-172">Websites should render and behave as expected</span></span>
- <span data-ttu-id="a836f-173">大多數瀏覽器功能都 ([我的最愛]、[歷程記錄] 等。 ) 應如期運作</span><span class="sxs-lookup"><span data-stu-id="a836f-173">Most browser functionality (Favorites, History, etc.) should work as expected</span></span>
- <span data-ttu-id="a836f-174">深色模式</span><span class="sxs-lookup"><span data-stu-id="a836f-174">Dark mode</span></span>
- <span data-ttu-id="a836f-175">將 web 應用程式安裝到裝置</span><span class="sxs-lookup"><span data-stu-id="a836f-175">Installing web apps to the device</span></span>
- <span data-ttu-id="a836f-176">安裝延伸 (請告訴我們您是否使用任何在 HoloLens 2 上無法正常運作的延伸) </span><span class="sxs-lookup"><span data-stu-id="a836f-176">Installing extensions (please let us know if you use any extensions that don't work properly on HoloLens 2)</span></span>
- <span data-ttu-id="a836f-177">查看並標示 PDF</span><span class="sxs-lookup"><span data-stu-id="a836f-177">Viewing and marking up a PDF</span></span>
- <span data-ttu-id="a836f-178">從單一瀏覽器視窗中移除空間音效</span><span class="sxs-lookup"><span data-stu-id="a836f-178">Spatial sound from a single browser window</span></span>
- <span data-ttu-id="a836f-179">自動和手動更新瀏覽器</span><span class="sxs-lookup"><span data-stu-id="a836f-179">Automatic and manual updating of the browser</span></span>
- <span data-ttu-id="a836f-180">使用 [儲存成 PDF] 選項，從 [列印] 功能表中儲存 PDF () </span><span class="sxs-lookup"><span data-stu-id="a836f-180">Saving a PDF from the Print menu (using "Save to PDF" option)</span></span>

**<span data-ttu-id="a836f-181">即將推出的案例與功能：</span><span class="sxs-lookup"><span data-stu-id="a836f-181">Scenarios and features coming soon:</span></span>**
- <span data-ttu-id="a836f-182">WebXR 和360檢視器擴充功能</span><span class="sxs-lookup"><span data-stu-id="a836f-182">WebXR and 360 Viewer extension</span></span>
- <span data-ttu-id="a836f-183">在您的環境中流覽多個視窗時，內容還原以修正視窗</span><span class="sxs-lookup"><span data-stu-id="a836f-183">Content restoration to correct window when browsing across multiple windows placed in your environment</span></span>
- <span data-ttu-id="a836f-184">透過瀏覽器加入 Microsoft 團隊通話（含影片、混合現實捕獲或螢幕共用） (使用音訊加入通話的功能良好) </span><span class="sxs-lookup"><span data-stu-id="a836f-184">Joining a Microsoft Teams call via the browser with video, mixed reality capture, or screen-sharing (joining calls with audio works well)</span></span>

**<span data-ttu-id="a836f-185">預期無法運作的案例與功能：</span><span class="sxs-lookup"><span data-stu-id="a836f-185">Scenarios and features not expected to work:</span></span>**
- <span data-ttu-id="a836f-186">多個視窗中同時有音訊資料流程的空間音效</span><span class="sxs-lookup"><span data-stu-id="a836f-186">Spatial sound from multiple windows with simultaneous audio streams</span></span>
- <span data-ttu-id="a836f-187">「看看，請說出它」</span><span class="sxs-lookup"><span data-stu-id="a836f-187">"See it, say it"</span></span>
- <span data-ttu-id="a836f-188">列印</span><span class="sxs-lookup"><span data-stu-id="a836f-188">Printing</span></span>

**<span data-ttu-id="a836f-189">常見的已知瀏覽器問題：</span><span class="sxs-lookup"><span data-stu-id="a836f-189">Top known browser issues:</span></span>**
- <span data-ttu-id="a836f-190">重設裝置將會移除新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a836f-190">Resetting your device will remove the new Microsoft Edge</span></span>
- <span data-ttu-id="a836f-191">[全息鍵盤] 中的放大鏡預覽顯示不正確的內容</span><span class="sxs-lookup"><span data-stu-id="a836f-191">The magnifier preview in the holographic keyboard shows incorrect content</span></span>

### <span data-ttu-id="a836f-192">新的 [設定] 應用程式</span><span class="sxs-lookup"><span data-stu-id="a836f-192">New Settings app</span></span>

<span data-ttu-id="a836f-193">在這個版本中，我們會推出新版本的 [設定] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="a836f-193">With this release, we're introducing a new version of the Settings app.</span></span> <span data-ttu-id="a836f-194">新的 [設定] 應用程式在下欄區域中包含 HoloLens 2 的新功能和已展開的設定：聲音、Power & 睡眠、網路 & 網際網路、應用程式、帳戶、輕鬆存取等。</span><span class="sxs-lookup"><span data-stu-id="a836f-194">The new Settings app includes new features and expanded settings for HoloLens 2 in the following areas: Sound, Power & sleep, Network & Internet, Apps, Accounts, Ease of Access, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="a836f-195">由於新的 [設定] app 與舊版的 [設定] 應用程式不同，因此您先前在環境周圍的任何設定視窗都會在更新時移除。</span><span class="sxs-lookup"><span data-stu-id="a836f-195">Because the new Settings app is distinct from the legacy Settings app, any Settings windows you previously placed around your environment will be removed upon update.</span></span>

![新的設定 app 首頁](images/new-settings-app.png)

**<span data-ttu-id="a836f-197">新功能和設定</span><span class="sxs-lookup"><span data-stu-id="a836f-197">New features and settings</span></span>**
- <span data-ttu-id="a836f-198">[設定搜尋]：使用關鍵字或設定的名稱從 [設定] 首頁搜尋設定</span><span class="sxs-lookup"><span data-stu-id="a836f-198">Settings search: search for settings from the Settings homepage using keywords or the setting's name</span></span>
- <span data-ttu-id="a836f-199">系統 > 音效：</span><span class="sxs-lookup"><span data-stu-id="a836f-199">System > Sound:</span></span>
  - <span data-ttu-id="a836f-200">輸入和輸出音訊裝置：單獨選擇您的輸入和輸出音訊裝置 (例如，透過藍牙耳機收聽音訊，或使用 USB-C 麥克風進行音訊輸入) 。</span><span class="sxs-lookup"><span data-stu-id="a836f-200">Input and output audio devices: independently choose your input and output audio devices (for example, listen to audio via Bluetooth headphones or use a USB-C microphone for audio input).</span></span> <span data-ttu-id="a836f-201">注意： HoloLens 2 不支援藍牙麥克風。</span><span class="sxs-lookup"><span data-stu-id="a836f-201">Note: Bluetooth microphones are not supported by HoloLens 2.</span></span>
  - <span data-ttu-id="a836f-202">App 數量：獨立調整每個應用程式的音量</span><span class="sxs-lookup"><span data-stu-id="a836f-202">App volume: independently adjust the volume of each app</span></span>
- <span data-ttu-id="a836f-203">系統 > Power & 睡眠：選擇裝置應該在一段時間後進入睡眠狀態</span><span class="sxs-lookup"><span data-stu-id="a836f-203">System > Power & sleep: choose when the device should go to sleep after a period of inactivity</span></span>
- <span data-ttu-id="a836f-204">系統 > 電池：手動啟用節電模式，或設定節電模式自動開啟的電池閾值</span><span class="sxs-lookup"><span data-stu-id="a836f-204">System > Battery: manually enable battery saver mode or set a battery threshold at which point battery saver mode turns on automatically</span></span>
- <span data-ttu-id="a836f-205">裝置 > USB：您可以根據預設，停用 USB 連接</span><span class="sxs-lookup"><span data-stu-id="a836f-205">Devices > USB: you can disable USB connections by default</span></span>
- <span data-ttu-id="a836f-206">網路 & 網際網路：</span><span class="sxs-lookup"><span data-stu-id="a836f-206">Network & Internet:</span></span>
  - <span data-ttu-id="a836f-207">USB-C 乙太網卡現在會出現在網路 & 網際網路中</span><span class="sxs-lookup"><span data-stu-id="a836f-207">USB-C Ethernet adapters will now appear in Network & Internet</span></span>
  - <span data-ttu-id="a836f-208">USB-C 乙太網路介面卡設定現已提供，包括其 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a836f-208">USB-C Ethernet adapter settings are now available, including its IP address</span></span>
  - <span data-ttu-id="a836f-209">您現在可以在 HoloLens 2 上啟用飛安模式</span><span class="sxs-lookup"><span data-stu-id="a836f-209">You can now enable airplane mode on HoloLens 2</span></span>
- <span data-ttu-id="a836f-210">App：您可以重設用於檔案和連結類型的預設應用程式。</span><span class="sxs-lookup"><span data-stu-id="a836f-210">Apps: you can reset the default apps used for file and link types.</span></span> <span data-ttu-id="a836f-211">如需詳細資訊，請參閱 [預設的 app 選擇器](#default-app-picker) 。</span><span class="sxs-lookup"><span data-stu-id="a836f-211">See [Default app picker](#default-app-picker) for more information.</span></span>
- <span data-ttu-id="a836f-212">帳戶 > 其他使用者：裝置擁有者可以新增使用者、將標準使用者升級至裝置擁有者、將裝置擁有者降級為標準使用者，以及移除使用者。</span><span class="sxs-lookup"><span data-stu-id="a836f-212">Accounts > Other users: device owners can add users, upgrade standard users to device owners, downgrade device owners to standard users, and remove users.</span></span>
- <span data-ttu-id="a836f-213">輕鬆存取：變更文字大小和一些視覺效果</span><span class="sxs-lookup"><span data-stu-id="a836f-213">Ease of Access: change text size and some visual effects</span></span>

**<span data-ttu-id="a836f-214">已知問題</span><span class="sxs-lookup"><span data-stu-id="a836f-214">Known issues</span></span>**
- <span data-ttu-id="a836f-215">先前設定的視窗將會被移除 (請參閱上方的記事) </span><span class="sxs-lookup"><span data-stu-id="a836f-215">Previously placed Settings windows will be removed (see note above)</span></span>
- <span data-ttu-id="a836f-216">[造訪通知] 頁面可能會造成 [設定] 應用程式 (調查) </span><span class="sxs-lookup"><span data-stu-id="a836f-216">Visiting the Notifications page may crash the Settings app (investigating)</span></span>
- <span data-ttu-id="a836f-217">[乙太網] 頁面目前沒有顯示 (要立即修正) </span><span class="sxs-lookup"><span data-stu-id="a836f-217">The Ethernet page currently doesn't show up (to be fixed soon)</span></span>
- <span data-ttu-id="a836f-218">新 Microsoft Edge 的電池使用量可能不准確，因為它的性質是由 UWP 配接器層支援的 Win32 桌面應用程式 (沒有立即預期的修正) </span><span class="sxs-lookup"><span data-stu-id="a836f-218">Battery usage for the new Microsoft Edge may not be accurate, due to its nature as a Win32 desktop application supported by a UWP adapter layer (no fix anticipated soon)</span></span>

### <span data-ttu-id="a836f-219">預設的應用程式選擇器</span><span class="sxs-lookup"><span data-stu-id="a836f-219">Default app picker</span></span>

<span data-ttu-id="a836f-220">當您啟動超連結或開啟的檔案類型有多個已安裝的應用程式（支援它）時，系統會顯示一個開啟的新視窗，提示您選取哪些已安裝的應用程式應該處理檔案或連結類型。</span><span class="sxs-lookup"><span data-stu-id="a836f-220">When you activate a hyperlink or open a file type with more than one installed app which supports it, you will see a new window open prompting you to select which installed app should handle the file or link type.</span></span> <span data-ttu-id="a836f-221">在這個視窗中，您也可以選擇讓所選取的應用程式處理檔案或連結類型「一次」或「永遠」。</span><span class="sxs-lookup"><span data-stu-id="a836f-221">In this window you can also choose to have the selected app handle the file or link type "Once" or "Always."</span></span>

![App 選擇器視窗](images/default-app-picker.png)

<span data-ttu-id="a836f-223">如果您選擇 [永遠]，但稍後想要變更處理特定檔案或連結類型的應用程式，您可以在 [設定] **> 應用程式**中重設儲存的預設值。</span><span class="sxs-lookup"><span data-stu-id="a836f-223">If you choose "Always" but later want to change which app handles a particular file or link type, you can reset your saved defaults in **Settings > Apps**.</span></span> <span data-ttu-id="a836f-224">滾動至頁面底部，然後選取 [檔案類型的預設應用程式] 和/或 "連結類型的預設應用程式] 底下的 [ **清除** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a836f-224">Scroll to the bottom of the page and select the **Clear** button under "Default apps for file types" and/or "Default apps for link types."</span></span> <span data-ttu-id="a836f-225">與桌上型電腦上類似的設定不同，您無法重設個別檔案類型的預設值。</span><span class="sxs-lookup"><span data-stu-id="a836f-225">Unlike the similar setting on desktop PCs, you can't reset individual file type defaults.</span></span>

### <span data-ttu-id="a836f-226">Office web app</span><span class="sxs-lookup"><span data-stu-id="a836f-226">Office web app</span></span>

<span data-ttu-id="a836f-227">Office web app 已新增至 [開始] 功能表中的 [所有應用程式] 清單中。</span><span class="sxs-lookup"><span data-stu-id="a836f-227">The Office web app has been added to the "All apps" list in the Start menu.</span></span> <span data-ttu-id="a836f-228">此 web 應用程式也可以釘選到 [啟動] 或 [卸載]。</span><span class="sxs-lookup"><span data-stu-id="a836f-228">This web app can also be pinned to Start or uninstalled.</span></span> <span data-ttu-id="a836f-229">因為這是 web 應用程式，所以其功能完全符合您要取得的效果 https://www.office.com 。</span><span class="sxs-lookup"><span data-stu-id="a836f-229">Because this is a web app, its functionality matches exactly what you'd experience by visiting https://www.office.com.</span></span> <span data-ttu-id="a836f-230">只有當您的 HoloLens 2 擁有有效的網際網路連線時，才能使用 Office web app 的功能。</span><span class="sxs-lookup"><span data-stu-id="a836f-230">Office web app functionality is only available when your HoloLens 2 has an active internet connection.</span></span>

### <span data-ttu-id="a836f-231">向類型滑動</span><span class="sxs-lookup"><span data-stu-id="a836f-231">Swipe to type</span></span>

<span data-ttu-id="a836f-232">有些客戶會透過輕掃想要輸入的單字圖形，在虛擬鍵盤上快速找出「輸入」，並為全息鍵盤預覽此功能。</span><span class="sxs-lookup"><span data-stu-id="a836f-232">Some customers find it faster to "type" on virtual keyboards by swiping the shape of the word they intend to type, and we're previewing this feature for the holographic keyboard.</span></span> <span data-ttu-id="a836f-233">您可以一次在一個單字上滑動一個字，方法是將手指放在全息鍵盤的平面上，輕觸該單字的圖案，然後從鍵盤平面 withdrawing 您的手指秘訣。</span><span class="sxs-lookup"><span data-stu-id="a836f-233">You can swipe one word at a time by passing the tip of your finger through the plane of the holographic keyboard, swiping the shape of the word, and then withdrawing the tip of your finger from the plane of the keyboard.</span></span> <span data-ttu-id="a836f-234">您可以透過在文字之間的鍵盤移除手指，不需按下空格鍵，即可輕觸後續字詞。</span><span class="sxs-lookup"><span data-stu-id="a836f-234">You can swipe follow-up words without needing to press the spacebar by removing your finger from the keyboard between words.</span></span> <span data-ttu-id="a836f-235">如果您在鍵盤上的手指移動之後看到滑動軌跡，您就會知道該功能已正常運作。</span><span class="sxs-lookup"><span data-stu-id="a836f-235">You will know the feature is working if you see a swipe trail following your finger's movement on the keyboard.</span></span>

<span data-ttu-id="a836f-236">請注意，這項功能可能會因您不會對 (手指感到阻力的情況下（不像是) 的手機顯示幕）而使用。</span><span class="sxs-lookup"><span data-stu-id="a836f-236">Please note, this feature can be tricky to use and master because of the nature of a holographic keyboard where you don't feel resistance against your finger (unlike a mobile phone display).</span></span> <span data-ttu-id="a836f-237">我們正在評估此功能以供公開發行，所以您的意見反應很重要;如果您發現該功能對您有所説明，或是您有建設性的意見反應，請透過 [意見反應中樞](hololens-feedback.md)告知我們。</span><span class="sxs-lookup"><span data-stu-id="a836f-237">We are evaluating this feature for public release, so your feedback is important; whether you find the feature useful or you have constructive feedback, please let us know via [Feedback Hub](hololens-feedback.md).</span></span>

### <span data-ttu-id="a836f-238">USB-C 外部麥克風支援</span><span class="sxs-lookup"><span data-stu-id="a836f-238">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a836f-239">插入 **USB 麥克風時，不會自動將它設定為輸入裝置**。</span><span class="sxs-lookup"><span data-stu-id="a836f-239">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="a836f-240">當您在一組 USB-C 耳機中插入時，系統會看到耳機的音訊會自動重新導向至耳機，但 HoloLens OS 會將內部麥克風陣列的優先順序設為任何其他輸入裝置的上方。</span><span class="sxs-lookup"><span data-stu-id="a836f-240">When plugging in a set of USB-C headphones users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> **<span data-ttu-id="a836f-241">若要使用 USB-C 麥克風，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="a836f-241">In order to use a USB-C microphone follow the steps below.</span></span>**

<span data-ttu-id="a836f-242">使用者現在可以使用 [ **音效** 設定] 面板選取 [與 USB 連接的外部麥克風]。</span><span class="sxs-lookup"><span data-stu-id="a836f-242">Users can now select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="a836f-243">這可讓使用者使用自己的麥克風連接，但在錄製和應用程式中則是 USB。</span><span class="sxs-lookup"><span data-stu-id="a836f-243">This allows users to use their own microphone connected but USB in recording and apps.</span></span> <span data-ttu-id="a836f-244">USB-C 麥克風很容易啟用和使用。</span><span class="sxs-lookup"><span data-stu-id="a836f-244">USB-C microphones are easy to enabled and use.</span></span>

<span data-ttu-id="a836f-245">開啟 [**設定**] 應用程式，然後選取 [**系統**  ->  **音效**]。</span><span class="sxs-lookup"><span data-stu-id="a836f-245">Open the **Settings** app and select **System** -> **Sound**.</span></span>

![音效設定](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="a836f-247">若要將外部麥克風與 **遠端協助**程式搭配使用，使用者將需要按一下 [管理聲音裝置] 超連結。</span><span class="sxs-lookup"><span data-stu-id="a836f-247">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="a836f-248">然後使用下拉式清單將外部麥克風設定為 **預設** 或 **通訊預設值。**</span><span class="sxs-lookup"><span data-stu-id="a836f-248">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="a836f-249">選擇 [ **預設值** ] 表示將在所有位置使用外部麥克風。</span><span class="sxs-lookup"><span data-stu-id="a836f-249">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="a836f-250">選擇 [ **通訊預設值** ] 表示將在遠端協助和其他通訊 app 中使用外部麥克風，但 HoloLens 麥克風陣列可能仍會用於其他工作。</span><span class="sxs-lookup"><span data-stu-id="a836f-250">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens Mic Array may still be used for other tasks.</span></span>

![管理聲音裝置](images/usbc-mic-2.png)

<br>

![設定麥克風預設值](images/usbc-mic-3.jpg)

#### <span data-ttu-id="a836f-253">藍牙麥克風支援怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="a836f-253">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="a836f-254">遺憾的是，目前尚不支援 HoloLens 2 上的藍牙麥克風。</span><span class="sxs-lookup"><span data-stu-id="a836f-254">Unfortunately Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

#### <span data-ttu-id="a836f-255">USB-C 麥克風疑難排解</span><span class="sxs-lookup"><span data-stu-id="a836f-255">Troubleshooting USB-C microphones</span></span>

<span data-ttu-id="a836f-256">請注意，某些 USB C 麥克風無法正確地將自己報告為麥克風 *和* 喇叭。</span><span class="sxs-lookup"><span data-stu-id="a836f-256">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="a836f-257">這是麥克風而不是 HoloLens 的問題。</span><span class="sxs-lookup"><span data-stu-id="a836f-257">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="a836f-258">將其中一個麥克風插入 HoloLens 時，可能會遺失聲音。</span><span class="sxs-lookup"><span data-stu-id="a836f-258">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="a836f-259">幸運的是，有一個簡單的修正程式。</span><span class="sxs-lookup"><span data-stu-id="a836f-259">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="a836f-260">在 [**設定**  ->  **系統**  ->  **音效**] 中，將內建的喇叭明確設定\*\* (類比功能音訊驅動程式) **做為**預設裝置\*\*。</span><span class="sxs-lookup"><span data-stu-id="a836f-260">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="a836f-261">即使隨後移除並重新連接麥克風，HoloLens 也應記住此設定。</span><span class="sxs-lookup"><span data-stu-id="a836f-261">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![USB-C 麥克風疑難排解](images/usbc-mic-4.png)

### <span data-ttu-id="a836f-263">在 Kiosk 模式中使用新的設定和邊緣 app</span><span class="sxs-lookup"><span data-stu-id="a836f-263">Use the new Settings and Edge apps in Kiosk modes</span></span>

<span data-ttu-id="a836f-264">當您在 [亭](hololens-kiosk.md)中包含應用程式時，IT 系統管理員通常會將 app 新增到展臺，但使用它的 App 使用者模型識別碼 (AUMID) 。</span><span class="sxs-lookup"><span data-stu-id="a836f-264">When including apps in in [Kiosks](hololens-kiosk.md), an IT Admin often adds the app to the Kiosk but using it's App User Model ID (AUMID).</span></span> <span data-ttu-id="a836f-265">因為 [設定] 應用程式和 Microsoft Edge 應用程式都被視為新的應用程式，而與這些應用程式使用 Aumid 的舊版 app 亭一樣，則需要更新，才能使用新的 AUMID。</span><span class="sxs-lookup"><span data-stu-id="a836f-265">Because both the Settings app and Microsoft Edge app are considered new apps and different that the older apps Kiosks that use AUMIDs for those apps will need to be updated to use the new AUMID.</span></span>

<span data-ttu-id="a836f-266">修改 Kiosk 以包含新的應用程式時，建議您在新的 AUMID 中新增，並留下舊的 app。</span><span class="sxs-lookup"><span data-stu-id="a836f-266">When modifying a Kiosk to include the new apps, we recommend adding in the new AUMID as well as leaving the old one.</span></span> <span data-ttu-id="a836f-267">這將會在使用者更新作業系統時建立輕鬆轉換，而且不需要接收新的原則就能持續使用 Kiosk。</span><span class="sxs-lookup"><span data-stu-id="a836f-267">This will create an easy transition when users update the OS and won't need to receive new policies to keep using the Kiosk as intended.</span></span>

| <span data-ttu-id="a836f-268">應用程式</span><span class="sxs-lookup"><span data-stu-id="a836f-268">App</span></span>                    | <span data-ttu-id="a836f-269">AUMID</span><span class="sxs-lookup"><span data-stu-id="a836f-269">AUMID</span></span>                                                  |
|------------------------|--------------------------------------------------------|
| <span data-ttu-id="a836f-270">舊版的 [設定] 應用程式</span><span class="sxs-lookup"><span data-stu-id="a836f-270">Old Settings App</span></span>       | <span data-ttu-id="a836f-271">HolographicSystemSettings_cw5n1h2txyewy！適用</span><span class="sxs-lookup"><span data-stu-id="a836f-271">HolographicSystemSettings_cw5n1h2txyewy!App</span></span>            |
| <span data-ttu-id="a836f-272">新的 [設定] 應用程式</span><span class="sxs-lookup"><span data-stu-id="a836f-272">New Settings App</span></span>       | <span data-ttu-id="a836f-273">BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy！適用</span><span class="sxs-lookup"><span data-stu-id="a836f-273">BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App</span></span> |
| <span data-ttu-id="a836f-274">舊版 Microsoft Edge 應用程式</span><span class="sxs-lookup"><span data-stu-id="a836f-274">Old Microsoft Edge app</span></span> | <span data-ttu-id="a836f-275">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span><span class="sxs-lookup"><span data-stu-id="a836f-275">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span></span>    |
| <span data-ttu-id="a836f-276">新的 Microsoft Edge 應用程式</span><span class="sxs-lookup"><span data-stu-id="a836f-276">New Microsoft Edge app</span></span> | <span data-ttu-id="a836f-277">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE</span><span class="sxs-lookup"><span data-stu-id="a836f-277">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE</span></span>    |

### <span data-ttu-id="a836f-278">管理失敗處理的 Kiosk 模式行為變更</span><span class="sxs-lookup"><span data-stu-id="a836f-278">Kiosk mode behavior changes for handling of failures</span></span>

<span data-ttu-id="a836f-279">在舊版組建中，如果裝置的 kiosk 設定是由全域指派的存取權和 AAD 群組成員所指派的存取權組成，則如果決定 AAD 群組成員資格失敗，使用者就會看到[「開始」功能表中的 [沒有顯示](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)]。</span><span class="sxs-lookup"><span data-stu-id="a836f-279">In older builds, if a device had a kiosk configuration, which is a combination of both global assigned access and AAD group member assigned access, if determining AAD group membership failed, the user would see “[nothing shown in start](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)” menu.</span></span>

<span data-ttu-id="a836f-280">從 Windows 測試人員發行版本開始，如果在 AAD 群組 kiosk 模式期間發生失敗，則 kiosk 體驗將會回退到全域 kiosk 設定 (（如果有) 的話）。</span><span class="sxs-lookup"><span data-stu-id="a836f-280">Starting in Windows Insider release, the kiosk experience will fallback to global kiosk configuration (if present) in case of failures during AAD group kiosk mode.</span></span>

### <span data-ttu-id="a836f-281">透過 [設定] 應用程式設定備用診斷</span><span class="sxs-lookup"><span data-stu-id="a836f-281">Configuring Fallback Diagnostics via Settings app</span></span>

<span data-ttu-id="a836f-282">現在，使用者可以在 [設定] App 中設定 [回退診斷](hololens-diagnostic-logs.md)的行為。</span><span class="sxs-lookup"><span data-stu-id="a836f-282">Now in Settings App, a user can configure the behavior of [Fallback Diagnostics](hololens-diagnostic-logs.md).</span></span> <span data-ttu-id="a836f-283">在 [設定] 應用程式中，流覽至 [**隱私權**  ->  **疑難排解**] 頁面以設定此設定。</span><span class="sxs-lookup"><span data-stu-id="a836f-283">In the Settings app navigate to **Privacy** -> **Troubleshooting** page to configure this setting.</span></span>

> [!NOTE]
> <span data-ttu-id="a836f-284">如果裝置已設定 MDM 原則，使用者將無法覆寫該行為。</span><span class="sxs-lookup"><span data-stu-id="a836f-284">If there is MDM policy configured for the device, user will not be able to override that behavior.</span></span>  






## <span data-ttu-id="a836f-285">開始接收測試人員組建</span><span class="sxs-lookup"><span data-stu-id="a836f-285">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="a836f-286">如果您最近沒有更新，請重新開機您的裝置以更新狀態，並取得最新的組建。</span><span class="sxs-lookup"><span data-stu-id="a836f-286">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="a836f-287">[重新開機裝置] 語音命令運作良好。</span><span class="sxs-lookup"><span data-stu-id="a836f-287">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="a836f-288">您也可以在 [設定/Windows 測試人員計畫] 中選擇 [重新開機] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a836f-288">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="a836f-289">我們在您可能遇到的後端有錯誤，這會讓您繼續進行追蹤。</span><span class="sxs-lookup"><span data-stu-id="a836f-289">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="a836f-290">在 HoloLens 2 裝置上，移至 [**設定**  >  **更新] & 安全性**  >  **Windows**測試人員計畫，然後選取 [**開始**使用]。</span><span class="sxs-lookup"><span data-stu-id="a836f-290">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="a836f-291">連結您用來註冊為「Windows 測試人員」的帳戶。</span><span class="sxs-lookup"><span data-stu-id="a836f-291">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="a836f-292">Windows 測試人員現在正在移至 [頻道]。</span><span class="sxs-lookup"><span data-stu-id="a836f-292">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="a836f-293">[ **快速** 響鈴] 會成為 **開發人員通道**， **慢速** 環將變成 **Beta 通道**，而 [ **放開預覽** ] 鈴聲將成為 **發行預覽頻道**。</span><span class="sxs-lookup"><span data-stu-id="a836f-293">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="a836f-294">對應如下：</span><span class="sxs-lookup"><span data-stu-id="a836f-294">Here is what that mapping looks like:</span></span>

![Windows 測試人員頻道說明](images/WindowsInsiderChannels.png)

<span data-ttu-id="a836f-296">如需詳細資訊，請參閱 Windows 博客上的 Windows 測試人員 [頻道簡介](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 。</span><span class="sxs-lookup"><span data-stu-id="a836f-296">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>

<span data-ttu-id="a836f-297">接著，選取 [Windows 作用中 **的開發**]，選擇您要接收 **開發人員通道** 或 **Beta 通道** 組建，並查看程式條款。</span><span class="sxs-lookup"><span data-stu-id="a836f-297">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="a836f-298">選取 [ **確認] > [立即重新開機** ] 完成。</span><span class="sxs-lookup"><span data-stu-id="a836f-298">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="a836f-299">重新開機裝置之後，請移至 [ **設定] > 更新 & 安全性 > 檢查更新** ，以取得最新的組建。</span><span class="sxs-lookup"><span data-stu-id="a836f-299">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

## <span data-ttu-id="a836f-300">FFU 下載和快閃路線</span><span class="sxs-lookup"><span data-stu-id="a836f-300">FFU download and flash directions</span></span>
<span data-ttu-id="a836f-301">若要使用 [航班式簽署 ffu] 進行測試，您必須先將裝置解除鎖定，然後才能閃爍 [航班已簽署] ffu。</span><span class="sxs-lookup"><span data-stu-id="a836f-301">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="a836f-302">在 PC 上：</span><span class="sxs-lookup"><span data-stu-id="a836f-302">On PC:</span></span>

    1. <span data-ttu-id="a836f-303">從下載 ffu 到您的電腦 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。</span><span class="sxs-lookup"><span data-stu-id="a836f-303">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="a836f-304">從 Microsoft 網上商店 ([高級恢復隨附) ] 安裝弧形。 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="a836f-304">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span></span>
    
1. <span data-ttu-id="a836f-305">在 HoloLens-航班解鎖：開啟**設定**  >  **更新 & 安全性**  >  **Windows**測試人員計畫，然後註冊、重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="a836f-305">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="a836f-306">快閃 FFU-現在您可以使用 ARC 來閃現已簽署的航班 FFU。</span><span class="sxs-lookup"><span data-stu-id="a836f-306">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

## <span data-ttu-id="a836f-307">提供意見反應與報告問題</span><span class="sxs-lookup"><span data-stu-id="a836f-307">Provide feedback and report issues</span></span>

<span data-ttu-id="a836f-308">請在您的 HoloLens 上使用「 [意見反應中樞」 app](hololens-feedback.md) ，以提供意見反應與報告問題。</span><span class="sxs-lookup"><span data-stu-id="a836f-308">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="a836f-309">使用意見反應中樞可確保所有必要的診斷資訊都包含在內，以協助我們的工程師快速調試並解決問題。</span><span class="sxs-lookup"><span data-stu-id="a836f-309">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="a836f-310">使用中文和日文版的 HoloLens 時，必須以相同的方式報告問題。</span><span class="sxs-lookup"><span data-stu-id="a836f-310">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="a836f-311">請務必接受詢問您是否希望意見反應中樞存取您的 [檔] 資料夾的提示， (在出現) 提示時，選取 **[是]** 。</span><span class="sxs-lookup"><span data-stu-id="a836f-311">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="a836f-312">開發人員注意事項</span><span class="sxs-lookup"><span data-stu-id="a836f-312">Note for developers</span></span>

<span data-ttu-id="a836f-313">歡迎與鼓勵您使用 HoloLens 測試人員組建來開發應用程式。</span><span class="sxs-lookup"><span data-stu-id="a836f-313">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="a836f-314">請參閱 [HoloLens 開發人員檔](https://developer.microsoft.com/windows/mixed-reality/development) 以開始使用。</span><span class="sxs-lookup"><span data-stu-id="a836f-314">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="a836f-315">這些相同的指示可與 HoloLens 測試人員組建搭配使用。</span><span class="sxs-lookup"><span data-stu-id="a836f-315">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="a836f-316">您可以使用與您已在 HoloLens 開發中使用的相同 Unity 與 Visual Studio 組建。</span><span class="sxs-lookup"><span data-stu-id="a836f-316">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <span data-ttu-id="a836f-317">停止接收測試人員組建</span><span class="sxs-lookup"><span data-stu-id="a836f-317">Stop receiving Insider builds</span></span>

<span data-ttu-id="a836f-318">如果您不想再收到 Windows 全息版的測試人員組建，您可以在 HoloLens 執行生產組建時退出宣告，或者，您可以 [使用 [](hololens-recovery.md) 高級恢復] 隨附的功能，將您的裝置復原至非測試人員版本的 Windows 全息版。</span><span class="sxs-lookup"><span data-stu-id="a836f-318">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="a836f-319">在手動重新安裝新的預覽組建之後，從測試人員預覽版中取消登錄的已知問題，將會出現藍屏。</span><span class="sxs-lookup"><span data-stu-id="a836f-319">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="a836f-320">之後，他們必須手動復原其裝置。</span><span class="sxs-lookup"><span data-stu-id="a836f-320">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="a836f-321">如需有關您是否會受到影響的完整詳細資料，請查看此 [已知問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a836f-321">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="a836f-322">若要確認您的 HoloLens 正在執行生產組建：</span><span class="sxs-lookup"><span data-stu-id="a836f-322">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="a836f-323">移至 [ **設定] > [系統 >**]，然後找出組建編號。</span><span class="sxs-lookup"><span data-stu-id="a836f-323">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="a836f-324">[請參閱生產組建編號的版本](hololens-release-notes.md)資訊。</span><span class="sxs-lookup"><span data-stu-id="a836f-324">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="a836f-325">若要退出宣告測試人員組建：</span><span class="sxs-lookup"><span data-stu-id="a836f-325">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="a836f-326">在運行生產組建的 HoloLens 中，移至 [ **設定] > 更新 & 安全性 > Windows**測試人員計畫，然後選取 [停止測試人員 **組建**]。</span><span class="sxs-lookup"><span data-stu-id="a836f-326">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="a836f-327">依照指示操作以選擇您的裝置。</span><span class="sxs-lookup"><span data-stu-id="a836f-327">Follow the instructions to opt out your device.</span></span>
