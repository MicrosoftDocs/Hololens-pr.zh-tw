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
ms.openlocfilehash: 5da96d2838cbe1a02956a3e567c6ecf6da9d6b10
ms.sourcegitcommit: c93f23fe7c27dfa45fef300a4fc91aa811bc8126
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/14/2021
ms.locfileid: "11269478"
---
# <span data-ttu-id="a5945-103">適用於 Microsoft HoloLens 的 Insider Preview</span><span class="sxs-lookup"><span data-stu-id="a5945-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="a5945-104">歡迎使用 HoloLens 的最新 Insider Preview 組建！</span><span class="sxs-lookup"><span data-stu-id="a5945-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="a5945-105">[開始](hololens-insider.md#start-receiving-insider-builds)使用並為我們的下一個重要作業系統更新提供寶貴的意見反應，這是一件簡單的工作。</span><span class="sxs-lookup"><span data-stu-id="a5945-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <span data-ttu-id="a5945-106">Windows 測試人員版本資訊</span><span class="sxs-lookup"><span data-stu-id="a5945-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="a5945-107">我們很高興能再次開始將新功能正式給 Windows 測試人員。</span><span class="sxs-lookup"><span data-stu-id="a5945-107">We are excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="a5945-108">我們將會正式至開發人員通道，以取得最新的更新。</span><span class="sxs-lookup"><span data-stu-id="a5945-108">We will be flighting to the Dev Channel for the latest updates.</span></span> <span data-ttu-id="a5945-109">我們會繼續更新此頁面，因為我們會在我們的 Windows 測試人員組建中新增更多功能與更新。</span><span class="sxs-lookup"><span data-stu-id="a5945-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span>  <span data-ttu-id="a5945-110">令您興奮並準備好將這些更新混合在您的現實中。</span><span class="sxs-lookup"><span data-stu-id="a5945-110">Get excited and ready to mix these updates into your reality.</span></span> 

| <span data-ttu-id="a5945-111">功能名稱</span><span class="sxs-lookup"><span data-stu-id="a5945-111">Feature Name</span></span>                                              | <span data-ttu-id="a5945-112">簡短描述</span><span class="sxs-lookup"><span data-stu-id="a5945-112">Short description</span></span>                                                                      | <span data-ttu-id="a5945-113">可在組建中使用</span><span class="sxs-lookup"><span data-stu-id="a5945-113">Available in build</span></span> |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [<span data-ttu-id="a5945-114">新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a5945-114">New Microsoft Edge</span></span>](#introducing-the-new-microsoft-edge) | <span data-ttu-id="a5945-115">新的、以 Chromium 為基礎的 Microsoft Edge 現已提供于 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="a5945-115">The new, Chromium-based Microsoft Edge is now available for HoloLens 2</span></span>                         | <span data-ttu-id="a5945-116">20279.1006</span><span class="sxs-lookup"><span data-stu-id="a5945-116">20279.1006</span></span> |
| [<span data-ttu-id="a5945-117">新的 [設定] 應用程式</span><span class="sxs-lookup"><span data-stu-id="a5945-117">New Settings app</span></span>](#new-settings-app)                     | <span data-ttu-id="a5945-118">舊版設定應用程式將由含新功能和設定的更新版本取代</span><span class="sxs-lookup"><span data-stu-id="a5945-118">The legacy Settings app is being replaced by an updated version with new features and settings</span></span> | <span data-ttu-id="a5945-119">20279.1006</span><span class="sxs-lookup"><span data-stu-id="a5945-119">20279.1006</span></span> |
| [<span data-ttu-id="a5945-120">預設的應用程式選擇器</span><span class="sxs-lookup"><span data-stu-id="a5945-120">Default app picker</span></span>](#default-app-picker)                 | <span data-ttu-id="a5945-121">針對每個檔案或連結類型選擇要啟動的應用程式</span><span class="sxs-lookup"><span data-stu-id="a5945-121">Choose which app should launch for each file or link type</span></span>                                      | <span data-ttu-id="a5945-122">20279.1006</span><span class="sxs-lookup"><span data-stu-id="a5945-122">20279.1006</span></span> |
| [<span data-ttu-id="a5945-123">Office web app</span><span class="sxs-lookup"><span data-stu-id="a5945-123">Office web app</span></span>](#office-web-app)                         | <span data-ttu-id="a5945-124">Office web app 的快捷方式現已列在 [所有應用程式] 中。</span><span class="sxs-lookup"><span data-stu-id="a5945-124">A shortcut to the Office web app is now listed in "All apps"</span></span>                                   | <span data-ttu-id="a5945-125">20279.1006</span><span class="sxs-lookup"><span data-stu-id="a5945-125">20279.1006</span></span> |
| [<span data-ttu-id="a5945-126">向類型滑動</span><span class="sxs-lookup"><span data-stu-id="a5945-126">Swipe to type</span></span>](#swipe-to-type)                           | <span data-ttu-id="a5945-127">使用手指的秘訣在全息鍵盤上「滑動」字</span><span class="sxs-lookup"><span data-stu-id="a5945-127">Use the tip of your finger to "swipe" words on the holographic keyboard</span></span>                        | <span data-ttu-id="a5945-128">20279.1006</span><span class="sxs-lookup"><span data-stu-id="a5945-128">20279.1006</span></span> |

### <span data-ttu-id="a5945-129">新的 Microsoft Edge 簡介</span><span class="sxs-lookup"><span data-stu-id="a5945-129">Introducing the new Microsoft Edge</span></span>

![舊版 Microsoft Edge 標誌的動畫至新的 Microsoft Edge 標誌](images/new-edge.gif)

<span data-ttu-id="a5945-131">新的 Microsoft Edge 會 [採用 Chromium 的「開啟來源」專案](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) ，為客戶建立更佳的相容性，並為 網頁程式開發人員提供較少的網路碎片。</span><span class="sxs-lookup"><span data-stu-id="a5945-131">The new Microsoft Edge [adopts the Chromium open source project](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) to create better compatibility for customers and less fragmentation of the web for web developers.</span></span> 

<span data-ttu-id="a5945-132">透過此測試人員預覽版，第一次可將新的 Microsoft Edge 提供給 HoloLens 2 客戶！</span><span class="sxs-lookup"><span data-stu-id="a5945-132">With this Insider preview, the new Microsoft Edge is available to HoloLens 2 customers for the first time!</span></span> <span data-ttu-id="a5945-133">雖然新的 Microsoft Edge 最終會取代 HoloLens 2 上舊版的 Microsoft Edge，但測試人員目前都可使用這兩種瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="a5945-133">While the new Microsoft Edge will eventually replace legacy Microsoft Edge on HoloLens 2, both browsers are currently available to Insiders.</span></span> <span data-ttu-id="a5945-134">請透過新的 Microsoft Edge 或透過[意見反應中樞](hololens-feedback.md)中的 [**傳送意見**反應] 功能，與我們的小組共用意見反應和錯誤。</span><span class="sxs-lookup"><span data-stu-id="a5945-134">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge or via [Feedback Hub](hololens-feedback.md).</span></span>

![新的 Microsoft Edge 螢幕擷取畫面](images/new-edge-ui.png)

#### <span data-ttu-id="a5945-136">啟動新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a5945-136">Launching the new Microsoft Edge</span></span>

<span data-ttu-id="a5945-137">有兩個版本的 Microsoft Edge 可供測試人員使用：新的 Microsoft Edge ![ 新的 Microsoft edge 圖示 ](images/new_edge_logo.png) (以藍色和綠色的漩渦圖示) ，而舊版的 microsoft edge (由白色 "e" 圖示) 所代表。</span><span class="sxs-lookup"><span data-stu-id="a5945-137">There are two versions of Microsoft Edge available to Insiders: the new Microsoft Edge ![new Microsoft Edge icon](images/new_edge_logo.png) (represented by a blue and green swirl icon) and the legacy Microsoft Edge (represented by the white "e" icon).</span></span> <span data-ttu-id="a5945-138">新的 Microsoft Edge 會釘選到 [開始] 功能表，當您啟動網頁連結時，系統會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="a5945-138">The new Microsoft Edge is pinned to the Start menu and will automatically launch when you activate a web link.</span></span> <span data-ttu-id="a5945-139">如果您想要還原為使用舊版 Microsoft Edge 做為預設的網頁瀏覽器，請參閱以下指示來 [重設預設 app](#default-app-picker)。</span><span class="sxs-lookup"><span data-stu-id="a5945-139">If you would like to revert to using legacy Microsoft Edge as your default web browser, see the instructions below for [resetting default apps](#default-app-picker).</span></span>

> [!NOTE]
> <span data-ttu-id="a5945-140">當您第一次在 HoloLens 2 上啟動新的 Microsoft Edge 時，您的設定和資料將會從舊版 Microsoft Edge 中匯入。</span><span class="sxs-lookup"><span data-stu-id="a5945-140">When you first launch the new Microsoft Edge on HoloLens 2, your settings and data will be imported from legacy Microsoft Edge.</span></span> <span data-ttu-id="a5945-141">如果您在啟動新的 Microsoft Edge 後繼續使用舊版 Microsoft Edge，新的資料將不會從舊版 Microsoft Edge 同步處理至新的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="a5945-141">If you continue to use legacy Microsoft Edge after launching the new Microsoft Edge, that new data will not be synced from legacy Microsoft Edge to the new Microsoft Edge.</span></span>

#### <span data-ttu-id="a5945-142">設定新 Microsoft Edge 的原則設定</span><span class="sxs-lookup"><span data-stu-id="a5945-142">Configuring policy settings for the new Microsoft Edge</span></span>

<span data-ttu-id="a5945-143">新的 Microsoft Edge 為 IT 專業人員提供與舊版 Microsoft Edge 相比，在 HoloLens 2 上更廣泛的瀏覽器原則。</span><span class="sxs-lookup"><span data-stu-id="a5945-143">The new Microsoft Edge offers IT Pros a much broader set of browser policies on HoloLens 2 than were previously available with legacy Microsoft Edge.</span></span> 

<span data-ttu-id="a5945-144">以下是一些有用的資源，可讓您深入瞭解如何管理新 Microsoft Edge 的原則設定：</span><span class="sxs-lookup"><span data-stu-id="a5945-144">Here are some helpful resources for learning more about managing policy settings for the new Microsoft Edge:</span></span>
- [<span data-ttu-id="a5945-145">使用 Microsoft Intune 設定 Microsoft Edge 原則設定</span><span class="sxs-lookup"><span data-stu-id="a5945-145">Configure Microsoft Edge policy settings with Microsoft Intune</span></span>](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [<span data-ttu-id="a5945-146">舊版 Microsoft Edge 與 Microsoft Edge 的原則對應</span><span class="sxs-lookup"><span data-stu-id="a5945-146">Microsoft Edge Legacy to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [<span data-ttu-id="a5945-147">Google Chrome 與 Microsoft Edge 的原則對應</span><span class="sxs-lookup"><span data-stu-id="a5945-147">Google Chrome to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- <span data-ttu-id="a5945-148">完整的 [Microsoft Edge 企業檔](https://docs.microsoft.com/deployedge/)</span><span class="sxs-lookup"><span data-stu-id="a5945-148">Full [Microsoft Edge Enterprise documentation](https://docs.microsoft.com/deployedge/)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5945-149">由於新 Microsoft Edge 支援的瀏覽器策略數量，我們的小組無法保證每個新原則在 HoloLens 2 上都能正常運作。</span><span class="sxs-lookup"><span data-stu-id="a5945-149">Because of the volume of browser policies supported by the new Microsoft Edge, our team is unable to guarantee that each new policy works on HoloLens 2.</span></span> <span data-ttu-id="a5945-150">不過，我們已測試並確認您先前在 HoloLens 2 上支援的每個舊版 Microsoft Edge 原則的新 Microsoft Edge 對，都會如期運作。</span><span class="sxs-lookup"><span data-stu-id="a5945-150">However, we've tested and confirmed that the new Microsoft Edge equivalent of each legacy Microsoft Edge policy previously supported on HoloLens 2 work as expected.</span></span> <span data-ttu-id="a5945-151">請參閱 microsoft [Edge 舊版至 Microsoft edge 原則對應](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) ，以找出您在 HoloLens 2 使用的每個舊版 microsoft edge 瀏覽器原則的新 Microsoft edge 對等專案。</span><span class="sxs-lookup"><span data-stu-id="a5945-151">See [Microsoft Edge Legacy to Microsoft Edge policy mapping](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) to find the new Microsoft Edge equivalent of each legacy Microsoft Edge browser policy you were using with HoloLens 2.</span></span>
>
> <span data-ttu-id="a5945-152">我們至少知道有兩個新的 Microsoft Edge 原則 *無法* 搭配 HoloLens 2 使用：</span><span class="sxs-lookup"><span data-stu-id="a5945-152">There are at least two new Microsoft Edge policies that we know *will not* work with HoloLens 2:</span></span>
> - <span data-ttu-id="a5945-153">EnterpriseModeSiteList</span><span class="sxs-lookup"><span data-stu-id="a5945-153">EnterpriseModeSiteList</span></span>
> - <span data-ttu-id="a5945-154">EnterpriseSiteListServiceURL</span><span class="sxs-lookup"><span data-stu-id="a5945-154">EnterpriseSiteListServiceURL</span></span>

#### <span data-ttu-id="a5945-155">從 HoloLens 2 上的新 Microsoft Edge 預期的目標</span><span class="sxs-lookup"><span data-stu-id="a5945-155">What to expect from the new Microsoft Edge on HoloLens 2</span></span>

<span data-ttu-id="a5945-156">由於新的 Microsoft Edge 是具有新 UWP 配接器層的原生 Win32 app，可讓它在只有 HoloLens 的裝置上執行，例如 HoloLens 2，某些功能可能無法立即使用。</span><span class="sxs-lookup"><span data-stu-id="a5945-156">Because the new Microsoft Edge is a native Win32 app with a new UWP adapter layer allowing it to run on UWP-only devices like HoloLens 2, some features may not be immediately available.</span></span> <span data-ttu-id="a5945-157">我們將在未來幾個月內支援新的案例與功能，請查看此空間以取得最新資訊。</span><span class="sxs-lookup"><span data-stu-id="a5945-157">We'll be supporting new scenarios and features over the coming months, so please check this space for up-to-date information.</span></span>

**<span data-ttu-id="a5945-158">預期會運作的案例與功能：</span><span class="sxs-lookup"><span data-stu-id="a5945-158">Scenarios and features expected to work:</span></span>**
- <span data-ttu-id="a5945-159">首次執行體驗、登入設定檔及同步處理</span><span class="sxs-lookup"><span data-stu-id="a5945-159">First-run experience, sign-in to profile, and sync</span></span>
- <span data-ttu-id="a5945-160">網站應該按照預期的方式呈現及運作</span><span class="sxs-lookup"><span data-stu-id="a5945-160">Websites should render and behave as expected</span></span>
- <span data-ttu-id="a5945-161">大多數瀏覽器功能都 ([我的最愛]、[歷程記錄] 等。 ) 應如期運作</span><span class="sxs-lookup"><span data-stu-id="a5945-161">Most browser functionality (Favorites, History, etc.) should work as expected</span></span>
- <span data-ttu-id="a5945-162">深色模式</span><span class="sxs-lookup"><span data-stu-id="a5945-162">Dark mode</span></span>
- <span data-ttu-id="a5945-163">將 web 應用程式安裝到裝置</span><span class="sxs-lookup"><span data-stu-id="a5945-163">Installing web apps to the device</span></span>
- <span data-ttu-id="a5945-164">安裝延伸 (請告訴我們您是否使用任何在 HoloLens 2 上無法正常運作的延伸) </span><span class="sxs-lookup"><span data-stu-id="a5945-164">Installing extensions (please let us know if you use any extensions that don't work properly on HoloLens 2)</span></span>
- <span data-ttu-id="a5945-165">查看並標示 PDF</span><span class="sxs-lookup"><span data-stu-id="a5945-165">Viewing and marking up a PDF</span></span>
- <span data-ttu-id="a5945-166">從單一瀏覽器視窗中移除空間音效</span><span class="sxs-lookup"><span data-stu-id="a5945-166">Spatial sound from a single browser window</span></span>
- <span data-ttu-id="a5945-167">自動和手動更新瀏覽器</span><span class="sxs-lookup"><span data-stu-id="a5945-167">Automatic and manual updating of the browser</span></span>
- <span data-ttu-id="a5945-168">使用 [儲存成 PDF] 選項，從 [列印] 功能表中儲存 PDF () </span><span class="sxs-lookup"><span data-stu-id="a5945-168">Saving a PDF from the Print menu (using "Save to PDF" option)</span></span>

**<span data-ttu-id="a5945-169">即將推出的案例與功能：</span><span class="sxs-lookup"><span data-stu-id="a5945-169">Scenarios and features coming soon:</span></span>**
- <span data-ttu-id="a5945-170">WebXR 和360檢視器擴充功能</span><span class="sxs-lookup"><span data-stu-id="a5945-170">WebXR and 360 Viewer extension</span></span>
- <span data-ttu-id="a5945-171">在您的環境中流覽多個視窗時，內容還原以修正視窗</span><span class="sxs-lookup"><span data-stu-id="a5945-171">Content restoration to correct window when browsing across multiple windows placed in your environment</span></span>
- <span data-ttu-id="a5945-172">多個視窗中同時有音訊資料流程的空間音效</span><span class="sxs-lookup"><span data-stu-id="a5945-172">Spatial sound for multiple windows with simultaneous audio streams</span></span>
- <span data-ttu-id="a5945-173">透過瀏覽器加入 Microsoft 團隊通話（含影片、混合現實捕獲或螢幕共用） (使用音訊加入通話的功能良好) </span><span class="sxs-lookup"><span data-stu-id="a5945-173">Joining a Microsoft Teams call via the browser with video, mixed reality capture, or screen-sharing (joining calls with audio works well)</span></span>
- <span data-ttu-id="a5945-174">「看看，請說出它」</span><span class="sxs-lookup"><span data-stu-id="a5945-174">"See it, say it"</span></span>
- <span data-ttu-id="a5945-175">列印</span><span class="sxs-lookup"><span data-stu-id="a5945-175">Printing</span></span>

**<span data-ttu-id="a5945-176">常見的已知瀏覽器問題：</span><span class="sxs-lookup"><span data-stu-id="a5945-176">Top known browser issues:</span></span>**
- <span data-ttu-id="a5945-177">重設裝置將會移除新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a5945-177">Resetting your device will remove the new Microsoft Edge</span></span>
- <span data-ttu-id="a5945-178">[全息鍵盤] 中的放大鏡預覽顯示不正確的內容</span><span class="sxs-lookup"><span data-stu-id="a5945-178">The magnifier preview in the holographic keyboard shows incorrect content</span></span>

### <span data-ttu-id="a5945-179">新的 [設定] 應用程式</span><span class="sxs-lookup"><span data-stu-id="a5945-179">New Settings app</span></span>

<span data-ttu-id="a5945-180">在這個版本中，我們會推出新版本的 [設定] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="a5945-180">With this release, we're introducing a new version of the Settings app.</span></span> <span data-ttu-id="a5945-181">新的 [設定] 應用程式在下欄區域中包含 HoloLens 2 的新功能和已展開的設定：聲音、Power & 睡眠、網路 & 網際網路、應用程式、帳戶、輕鬆存取等。</span><span class="sxs-lookup"><span data-stu-id="a5945-181">The new Settings app includes new features and expanded settings for HoloLens 2 in the following areas: Sound, Power & sleep, Network & Internet, Apps, Accounts, Ease of Access, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="a5945-182">由於新的 [設定] app 與舊版的 [設定] 應用程式不同，因此您先前在環境周圍的任何設定視窗都會在更新時移除。</span><span class="sxs-lookup"><span data-stu-id="a5945-182">Because the new Settings app is distinct from the legacy Settings app, any Settings windows you previously placed around your environment will be removed upon update.</span></span>

![新的設定 app 首頁](images/new-settings-app.png)

**<span data-ttu-id="a5945-184">新功能和設定</span><span class="sxs-lookup"><span data-stu-id="a5945-184">New features and settings</span></span>**
- <span data-ttu-id="a5945-185">[設定搜尋]：使用關鍵字或設定的名稱從 [設定] 首頁搜尋設定</span><span class="sxs-lookup"><span data-stu-id="a5945-185">Settings search: search for settings from the Settings homepage using keywords or the setting's name</span></span>
- <span data-ttu-id="a5945-186">系統 > 音效：</span><span class="sxs-lookup"><span data-stu-id="a5945-186">System > Sound:</span></span>
  - <span data-ttu-id="a5945-187">輸入和輸出音訊裝置：單獨選擇您的輸入和輸出音訊裝置 (例如，透過藍牙耳機收聽音訊，或使用 USB-C 麥克風進行音訊輸入) 。</span><span class="sxs-lookup"><span data-stu-id="a5945-187">Input and output audio devices: independently choose your input and output audio devices (for example, listen to audio via Bluetooth headphones or use a USB-C microphone for audio input).</span></span> <span data-ttu-id="a5945-188">注意： HoloLens 2 不支援藍牙麥克風。</span><span class="sxs-lookup"><span data-stu-id="a5945-188">Note: Bluetooth microphones are not supported by HoloLens 2.</span></span>
  - <span data-ttu-id="a5945-189">App 數量：獨立調整每個應用程式的音量</span><span class="sxs-lookup"><span data-stu-id="a5945-189">App volume: independently adjust the volume of each app</span></span>
- <span data-ttu-id="a5945-190">系統 > Power & 睡眠：選擇裝置應該在一段時間後進入睡眠狀態</span><span class="sxs-lookup"><span data-stu-id="a5945-190">System > Power & sleep: choose when the device should go to sleep after a period of inactivity</span></span>
- <span data-ttu-id="a5945-191">系統 > 電池：手動啟用節電模式，或設定節電模式自動開啟的電池閾值</span><span class="sxs-lookup"><span data-stu-id="a5945-191">System > Battery: manually enable battery saver mode or set a battery threshold at which point battery saver mode turns on automatically</span></span>
- <span data-ttu-id="a5945-192">裝置 > USB：您可以根據預設，停用 USB 連接</span><span class="sxs-lookup"><span data-stu-id="a5945-192">Devices > USB: you can disable USB connections by default</span></span>
- <span data-ttu-id="a5945-193">網路 & 網際網路：</span><span class="sxs-lookup"><span data-stu-id="a5945-193">Network & Internet:</span></span>
  - <span data-ttu-id="a5945-194">USB-C 乙太網卡現在會出現在網路 & 網際網路中</span><span class="sxs-lookup"><span data-stu-id="a5945-194">USB-C Ethernet adapters will now appear in Network & Internet</span></span>
  - <span data-ttu-id="a5945-195">USB-C 乙太網路介面卡設定現已提供，包括其 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a5945-195">USB-C Ethernet adapter settings are now available, including its IP address</span></span>
  - <span data-ttu-id="a5945-196">您現在可以在 HoloLens 2 上啟用飛安模式</span><span class="sxs-lookup"><span data-stu-id="a5945-196">You can now enable airplane mode on HoloLens 2</span></span>
- <span data-ttu-id="a5945-197">App：您可以重設用於檔案和連結類型的預設應用程式。</span><span class="sxs-lookup"><span data-stu-id="a5945-197">Apps: you can reset the default apps used for file and link types.</span></span> <span data-ttu-id="a5945-198">如需詳細資訊，請參閱 [預設的 app 選擇器](#default-app-picker) 。</span><span class="sxs-lookup"><span data-stu-id="a5945-198">See [Default app picker](#default-app-picker) for more information.</span></span>
- <span data-ttu-id="a5945-199">帳戶 > 其他使用者：裝置擁有者可以新增使用者、將標準使用者升級至裝置擁有者、將裝置擁有者降級為標準使用者，以及移除使用者。</span><span class="sxs-lookup"><span data-stu-id="a5945-199">Accounts > Other users: device owners can add users, upgrade standard users to device owners, downgrade device owners to standard users, and remove users.</span></span>
- <span data-ttu-id="a5945-200">輕鬆存取：變更文字大小和一些視覺效果</span><span class="sxs-lookup"><span data-stu-id="a5945-200">Ease of Access: change text size and some visual effects</span></span>

**<span data-ttu-id="a5945-201">已知問題</span><span class="sxs-lookup"><span data-stu-id="a5945-201">Known issues</span></span>**
- <span data-ttu-id="a5945-202">先前設定的視窗將會被移除 (請參閱上方的記事) </span><span class="sxs-lookup"><span data-stu-id="a5945-202">Previously placed Settings windows will be removed (see note above)</span></span>
- <span data-ttu-id="a5945-203">[造訪通知] 頁面可能會造成 [設定] 應用程式 (調查) </span><span class="sxs-lookup"><span data-stu-id="a5945-203">Visiting the Notifications page may crash the Settings app (investigating)</span></span>
- <span data-ttu-id="a5945-204">[乙太網] 頁面目前沒有顯示 (要立即修正) </span><span class="sxs-lookup"><span data-stu-id="a5945-204">The Ethernet page currently doesn't show up (to be fixed soon)</span></span>
- <span data-ttu-id="a5945-205">新 Microsoft Edge 的電池使用量可能不准確，因為它的性質是由 UWP 配接器層支援的 Win32 桌面應用程式 (沒有立即預期的修正) </span><span class="sxs-lookup"><span data-stu-id="a5945-205">Battery usage for the new Microsoft Edge may not be accurate, due to its nature as a Win32 desktop application supported by a UWP adapter layer (no fix anticipated soon)</span></span>

### <span data-ttu-id="a5945-206">預設的應用程式選擇器</span><span class="sxs-lookup"><span data-stu-id="a5945-206">Default app picker</span></span>

<span data-ttu-id="a5945-207">當您啟動超連結或開啟的檔案類型有多個已安裝的應用程式（支援它）時，系統會顯示一個開啟的新視窗，提示您選取哪些已安裝的應用程式應該處理檔案或連結類型。</span><span class="sxs-lookup"><span data-stu-id="a5945-207">When you activate a hyperlink or open a file type with more than one installed app which supports it, you will see a new window open prompting you to select which installed app should handle the file or link type.</span></span> <span data-ttu-id="a5945-208">在這個視窗中，您也可以選擇讓所選取的應用程式處理檔案或連結類型「一次」或「永遠」。</span><span class="sxs-lookup"><span data-stu-id="a5945-208">In this window you can also choose to have the selected app handle the file or link type "Once" or "Always."</span></span> 

![App 選擇器視窗](images/default-app-picker.png)

<span data-ttu-id="a5945-210">如果您選擇 [永遠]，但稍後想要變更處理特定檔案或連結類型的應用程式，您可以在 [設定] **> 應用程式**中重設儲存的預設值。</span><span class="sxs-lookup"><span data-stu-id="a5945-210">If you choose "Always" but later want to change which app handles a particular file or link type, you can reset your saved defaults in **Settings > Apps**.</span></span> <span data-ttu-id="a5945-211">滾動至頁面底部，然後選取 [檔案類型的預設應用程式] 和/或 "連結類型的預設應用程式] 底下的 [ **清除** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a5945-211">Scroll to the bottom of the page and select the **Clear** button under "Default apps for file types" and/or "Default apps for link types."</span></span> <span data-ttu-id="a5945-212">與桌上型電腦上類似的設定不同，您無法重設個別檔案類型的預設值。</span><span class="sxs-lookup"><span data-stu-id="a5945-212">Unlike the similar setting on desktop PCs, you can't reset individual file type defaults.</span></span>

### <span data-ttu-id="a5945-213">Office web app</span><span class="sxs-lookup"><span data-stu-id="a5945-213">Office web app</span></span>

<span data-ttu-id="a5945-214">Office web app 已新增至 [開始] 功能表中的 [所有應用程式] 清單中。</span><span class="sxs-lookup"><span data-stu-id="a5945-214">The Office web app has been added to the "All apps" list in the Start menu.</span></span> <span data-ttu-id="a5945-215">此 web 應用程式也可以釘選到 [啟動] 或 [卸載]。</span><span class="sxs-lookup"><span data-stu-id="a5945-215">This web app can also be pinned to Start or uninstalled.</span></span> <span data-ttu-id="a5945-216">因為這是 web 應用程式，所以其功能完全符合您要取得的效果 https://www.office.com 。</span><span class="sxs-lookup"><span data-stu-id="a5945-216">Because this is a web app, its functionality matches exactly what you'd experience by visiting https://www.office.com.</span></span> <span data-ttu-id="a5945-217">只有當您的 HoloLens 2 擁有有效的網際網路連線時，才能使用 Office web app 的功能。</span><span class="sxs-lookup"><span data-stu-id="a5945-217">Office web app functionality is only available when your HoloLens 2 has an active internet connection.</span></span>

### <span data-ttu-id="a5945-218">向類型滑動</span><span class="sxs-lookup"><span data-stu-id="a5945-218">Swipe to type</span></span>

<span data-ttu-id="a5945-219">有些客戶會透過輕掃想要輸入的單字圖形，在虛擬鍵盤上快速找出「輸入」，並為全息鍵盤預覽此功能。</span><span class="sxs-lookup"><span data-stu-id="a5945-219">Some customers find it faster to "type" on virtual keyboards by swiping the shape of the word they intend to type, and we're previewing this feature for the holographic keyboard.</span></span> <span data-ttu-id="a5945-220">您可以一次在一個單字上滑動一個字，方法是將手指放在全息鍵盤的平面上，輕觸該單字的圖案，然後從鍵盤平面 withdrawing 您的手指秘訣。</span><span class="sxs-lookup"><span data-stu-id="a5945-220">You can swipe one word at a time by passing the tip of your finger through the plane of the holographic keyboard, swiping the shape of the word, and then withdrawing the tip of your finger from the plane of the keyboard.</span></span> <span data-ttu-id="a5945-221">您可以透過在文字之間的鍵盤移除手指，不需按下空格鍵，即可輕觸後續字詞。</span><span class="sxs-lookup"><span data-stu-id="a5945-221">You can swipe follow-up words without needing to press the spacebar by removing your finger from the keyboard between words.</span></span> <span data-ttu-id="a5945-222">如果您在鍵盤上的手指移動之後看到滑動軌跡，您就會知道該功能已正常運作。</span><span class="sxs-lookup"><span data-stu-id="a5945-222">You will know the feature is working if you see a swipe trail following your finger's movement on the keyboard.</span></span>

<span data-ttu-id="a5945-223">請注意，這項功能可能會因您不會對 (手指感到阻力的情況下（不像是) 的手機顯示幕）而使用。</span><span class="sxs-lookup"><span data-stu-id="a5945-223">Please note, this feature can be tricky to use and master because of the nature of a holographic keyboard where you don't feel resistance against your finger (unlike a mobile phone display).</span></span> <span data-ttu-id="a5945-224">我們正在評估此功能以供公開發行，所以您的意見反應很重要;如果您發現該功能對您有所説明，或是您有建設性的意見反應，請透過 [意見反應中樞](hololens-feedback.md)告知我們。</span><span class="sxs-lookup"><span data-stu-id="a5945-224">We are evaluating this feature for public release, so your feedback is important; whether you find the feature useful or you have constructive feedback, please let us know via [Feedback Hub](hololens-feedback.md).</span></span>





## <span data-ttu-id="a5945-225">開始接收測試人員組建</span><span class="sxs-lookup"><span data-stu-id="a5945-225">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="a5945-226">如果您最近沒有更新，請重新開機您的裝置以更新狀態，並取得最新的組建。</span><span class="sxs-lookup"><span data-stu-id="a5945-226">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="a5945-227">[重新開機裝置] 語音命令運作良好。</span><span class="sxs-lookup"><span data-stu-id="a5945-227">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="a5945-228">您也可以在 [設定/Windows 測試人員計畫] 中選擇 [重新開機] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a5945-228">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="a5945-229">我們在您可能遇到的後端有錯誤，這會讓您繼續進行追蹤。</span><span class="sxs-lookup"><span data-stu-id="a5945-229">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="a5945-230">在 HoloLens 2 裝置上，移至 [**設定**  >  **更新] & 安全性**  >  **Windows**測試人員計畫，然後選取 [**開始**使用]。</span><span class="sxs-lookup"><span data-stu-id="a5945-230">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="a5945-231">連結您用來註冊為「Windows 測試人員」的帳戶。</span><span class="sxs-lookup"><span data-stu-id="a5945-231">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="a5945-232">Windows 測試人員現在正在移至 [頻道]。</span><span class="sxs-lookup"><span data-stu-id="a5945-232">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="a5945-233">[ **快速** 響鈴] 會成為 **開發人員通道**， **慢速** 環將變成 **Beta 通道**，而 [ **放開預覽** ] 鈴聲將成為 **發行預覽頻道**。</span><span class="sxs-lookup"><span data-stu-id="a5945-233">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="a5945-234">對應如下：</span><span class="sxs-lookup"><span data-stu-id="a5945-234">Here is what that mapping looks like:</span></span>

![Windows 測試人員頻道說明](images/WindowsInsiderChannels.png)

<span data-ttu-id="a5945-236">如需詳細資訊，請參閱 Windows 博客上的 Windows 測試人員 [頻道簡介](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 。</span><span class="sxs-lookup"><span data-stu-id="a5945-236">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>

<span data-ttu-id="a5945-237">接著，選取 [Windows 作用中 **的開發**]，選擇您要接收 **開發人員通道** 或 **Beta 通道** 組建，並查看程式條款。</span><span class="sxs-lookup"><span data-stu-id="a5945-237">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="a5945-238">選取 [ **確認] > [立即重新開機** ] 完成。</span><span class="sxs-lookup"><span data-stu-id="a5945-238">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="a5945-239">重新開機裝置之後，請移至 [ **設定] > 更新 & 安全性 > 檢查更新** ，以取得最新的組建。</span><span class="sxs-lookup"><span data-stu-id="a5945-239">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

## <span data-ttu-id="a5945-240">FFU 下載和快閃路線</span><span class="sxs-lookup"><span data-stu-id="a5945-240">FFU download and flash directions</span></span>
<span data-ttu-id="a5945-241">若要使用 [航班式簽署 ffu] 進行測試，您必須先將裝置解除鎖定，然後才能閃爍 [航班已簽署] ffu。</span><span class="sxs-lookup"><span data-stu-id="a5945-241">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="a5945-242">在 PC 上：</span><span class="sxs-lookup"><span data-stu-id="a5945-242">On PC:</span></span>

    1. <span data-ttu-id="a5945-243">從下載 ffu 到您的電腦 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。</span><span class="sxs-lookup"><span data-stu-id="a5945-243">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="a5945-244">從 Microsoft 網上商店 ([高級恢復隨附) ] 安裝弧形。 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="a5945-244">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span></span>
    
1. <span data-ttu-id="a5945-245">在 HoloLens-航班解鎖：開啟**設定**  >  **更新 & 安全性**  >  **Windows**測試人員計畫，然後註冊、重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="a5945-245">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="a5945-246">快閃 FFU-現在您可以使用 ARC 來閃現已簽署的航班 FFU。</span><span class="sxs-lookup"><span data-stu-id="a5945-246">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

## <span data-ttu-id="a5945-247">提供意見反應與報告問題</span><span class="sxs-lookup"><span data-stu-id="a5945-247">Provide feedback and report issues</span></span>

<span data-ttu-id="a5945-248">請在您的 HoloLens 上使用「 [意見反應中樞」 app](hololens-feedback.md) ，以提供意見反應與報告問題。</span><span class="sxs-lookup"><span data-stu-id="a5945-248">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="a5945-249">使用意見反應中樞可確保所有必要的診斷資訊都包含在內，以協助我們的工程師快速調試並解決問題。</span><span class="sxs-lookup"><span data-stu-id="a5945-249">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="a5945-250">使用中文和日文版的 HoloLens 時，必須以相同的方式報告問題。</span><span class="sxs-lookup"><span data-stu-id="a5945-250">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="a5945-251">請務必接受詢問您是否希望意見反應中樞存取您的 [檔] 資料夾的提示， (在出現) 提示時，選取 **[是]** 。</span><span class="sxs-lookup"><span data-stu-id="a5945-251">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="a5945-252">開發人員注意事項</span><span class="sxs-lookup"><span data-stu-id="a5945-252">Note for developers</span></span>

<span data-ttu-id="a5945-253">歡迎與鼓勵您使用 HoloLens 測試人員組建來開發應用程式。</span><span class="sxs-lookup"><span data-stu-id="a5945-253">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="a5945-254">請參閱 [HoloLens 開發人員檔](https://developer.microsoft.com/windows/mixed-reality/development) 以開始使用。</span><span class="sxs-lookup"><span data-stu-id="a5945-254">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="a5945-255">這些相同的指示可與 HoloLens 測試人員組建搭配使用。</span><span class="sxs-lookup"><span data-stu-id="a5945-255">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="a5945-256">您可以使用與您已在 HoloLens 開發中使用的相同 Unity 與 Visual Studio 組建。</span><span class="sxs-lookup"><span data-stu-id="a5945-256">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <span data-ttu-id="a5945-257">停止接收測試人員組建</span><span class="sxs-lookup"><span data-stu-id="a5945-257">Stop receiving Insider builds</span></span>

<span data-ttu-id="a5945-258">如果您不想再收到 Windows 全息版的測試人員組建，您可以在 HoloLens 執行生產組建時退出宣告，或者，您可以 [使用 [](hololens-recovery.md) 高級恢復] 隨附的功能，將您的裝置復原至非測試人員版本的 Windows 全息版。</span><span class="sxs-lookup"><span data-stu-id="a5945-258">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="a5945-259">在手動重新安裝新的預覽組建之後，從測試人員預覽版中取消登錄的已知問題，將會出現藍屏。</span><span class="sxs-lookup"><span data-stu-id="a5945-259">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="a5945-260">之後，他們必須手動復原其裝置。</span><span class="sxs-lookup"><span data-stu-id="a5945-260">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="a5945-261">如需有關您是否會受到影響的完整詳細資料，請查看此 [已知問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a5945-261">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="a5945-262">若要確認您的 HoloLens 正在執行生產組建：</span><span class="sxs-lookup"><span data-stu-id="a5945-262">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="a5945-263">移至 [ **設定] > [系統 >**]，然後找出組建編號。</span><span class="sxs-lookup"><span data-stu-id="a5945-263">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="a5945-264">[請參閱生產組建編號的版本](hololens-release-notes.md)資訊。</span><span class="sxs-lookup"><span data-stu-id="a5945-264">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="a5945-265">若要退出宣告測試人員組建：</span><span class="sxs-lookup"><span data-stu-id="a5945-265">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="a5945-266">在運行生產組建的 HoloLens 中，移至 [ **設定] > 更新 & 安全性 > Windows**測試人員計畫，然後選取 [停止測試人員 **組建**]。</span><span class="sxs-lookup"><span data-stu-id="a5945-266">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="a5945-267">依照指示操作以選擇您的裝置。</span><span class="sxs-lookup"><span data-stu-id="a5945-267">Follow the instructions to opt out your device.</span></span>
