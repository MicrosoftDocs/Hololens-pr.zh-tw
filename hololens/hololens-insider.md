---
title: 適用於 Microsoft HoloLens 的 Insider Preview
description: 瞭解如何開始使用 Insider build，並針對 HoloLens 的下一個重大作業系統更新，提供寶貴的意見反應。
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
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: a4949ab68121cb772fdb8a62411ed70868a6ccb6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924361"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="2f7cd-103">適用於 Microsoft HoloLens 的 Insider Preview</span><span class="sxs-lookup"><span data-stu-id="2f7cd-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="2f7cd-104">歡迎使用 HoloLens 的最新 Insider preview 組建！</span><span class="sxs-lookup"><span data-stu-id="2f7cd-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="2f7cd-105">您可以輕鬆地 [開始](hololens-insider.md#start-receiving-insider-builds) 使用，並針對 HoloLens 的下一次重大作業系統更新提供寶貴的意見反應。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="2f7cd-106">Windows 測試人員版本資訊</span><span class="sxs-lookup"><span data-stu-id="2f7cd-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="2f7cd-107">我們很高興能再次開始試驗 Windows 測試人員的新功能。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="2f7cd-108">新組建將會試驗至開發和搶鮮版（Beta）通道，以取得最新的更新。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="2f7cd-109">當我們在 Windows 測試人員組建中新增更多功能和更新時，我們會繼續更新此頁面。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="2f7cd-110">取得驚喜，並準備好將這些更新混合到您的現實中。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-110">Get excited and ready to mix these updates into your reality.</span></span> 

### <a name="csp-changes-on-hololens"></a><span data-ttu-id="2f7cd-111">HoloLens 上的 CSP 變更</span><span class="sxs-lookup"><span data-stu-id="2f7cd-111">CSP changes on HoloLens</span></span>
 
- <span data-ttu-id="2f7cd-112">在 Windows 測試人員組建20348.1403 中引進</span><span class="sxs-lookup"><span data-stu-id="2f7cd-112">Introduced in Windows Insider build, 20348.1403</span></span>

#### <a name="devdetail-csp"></a><span data-ttu-id="2f7cd-113">DevDetail CSP</span><span class="sxs-lookup"><span data-stu-id="2f7cd-113">DevDetail CSP</span></span>

<span data-ttu-id="2f7cd-114">DevDetail CSP 現在也會報告 HoloLens 裝置上的可用儲存空間。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-114">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="2f7cd-115">這應該與 [設定] 應用程式的 [儲存體] 頁面中顯示的值大約相符。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-115">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="2f7cd-116">以下是包含這項資訊的特定節點。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-116">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="2f7cd-117">。/DevDetail/Ext/Microsoft/FreeStorage (僅取得作業) </span><span class="sxs-lookup"><span data-stu-id="2f7cd-117">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp"></a><span data-ttu-id="2f7cd-118">DeviceStatus CSP</span><span class="sxs-lookup"><span data-stu-id="2f7cd-118">DeviceStatus CSP</span></span>

<span data-ttu-id="2f7cd-119">DeviceStatus CSP 現在也會報告與 HoloLens 主動連線的 Wifi 網路的 SSID 和 BSSID。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-119">DeviceStatus CSP now also reports SSID and BSSID of Wifi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="2f7cd-120">以下是包含這項資訊的特定節點。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-120">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="2f7cd-121">/Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*介面卡的 mac 位址/SSID Wi-Fi*</span><span class="sxs-lookup"><span data-stu-id="2f7cd-121">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="2f7cd-122">/Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*介面卡的 mac 位址/BSSID Wi-Fi*</span><span class="sxs-lookup"><span data-stu-id="2f7cd-122">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="2f7cd-123">MDM 廠商的 syncml blob (範例) 查詢 NetworkIdentifiers</span><span class="sxs-lookup"><span data-stu-id="2f7cd-123">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="fixes-and-improvements"></a><span data-ttu-id="2f7cd-124">修正和改善：</span><span class="sxs-lookup"><span data-stu-id="2f7cd-124">Fixes and improvements:</span></span>

- <span data-ttu-id="2f7cd-125">已修正未 [提示下載鎖定檔案的裝置入口網站已知問題。](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="2f7cd-125">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="2f7cd-126">已修正檔案 [上傳和下載超時的裝置入口網站已知問題。](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="2f7cd-126">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>

## <a name="start-receiving-insider-builds"></a><span data-ttu-id="2f7cd-127">開始接收 Insider build</span><span class="sxs-lookup"><span data-stu-id="2f7cd-127">Start receiving Insider builds</span></span>
> [!NOTE]
> <span data-ttu-id="2f7cd-128">如果您最近未更新，請重新開機您的裝置以更新狀態並取得最新組建。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-128">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="2f7cd-129">「重新開機裝置」聲音命令也可以正常運作。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-129">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="2f7cd-130">您也可以選擇 [設定]/[Windows 測試人員計畫] 中的 [重新開機] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-130">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="2f7cd-131">您可能遇到的後端有錯誤，這會讓您回到進度。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-131">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="2f7cd-132">在 HoloLens 2 裝置上，移至 [**設定**  >  **更新] & 安全性**  >  **Windows 測試人員計畫** 並選取 [**開始** 使用]。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-132">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="2f7cd-133">將您用來註冊的帳戶連結為 Windows 測試人員。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-133">Link the account you used to register as a Windows Insider.</span></span>
<span data-ttu-id="2f7cd-134">Windows insider 現在正在移至頻道。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-134">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="2f7cd-135">**快速** 環形會成為 **開發通道**，因此 **緩慢** 的通道會變成 **Beta 通道**，而 **發行預覽** 通道將會成為 **發行預覽通道**。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-135">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="2f7cd-136">對應如下所示：如需 ![ 詳細資訊 Windows 測試人員通道說明 ](images/WindowsInsiderChannels.png) ，請參閱 Windows blog 上的 [Windows 測試人員頻道簡介](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-136">Here is what that mapping looks like: ![Windows Insider Channels explanation](images/WindowsInsiderChannels.png) For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="2f7cd-137">然後，選取 [ **Windows 的主動式開發**]，選擇您是否要接收 **開發通道** 或 **Beta 版通道** 組建，並檢查方案條款。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-137">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="2f7cd-138">選取 [ **確認 > 立即重新開機** ] 以完成。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-138">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="2f7cd-139">裝置重新開機之後，請移至 [ **設定] > 更新 & 安全性 > 檢查更新** 以取得最新組建。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-139">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>
### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="2f7cd-140">更新錯誤0x80070490 解決</span><span class="sxs-lookup"><span data-stu-id="2f7cd-140">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="2f7cd-141">如果您在開發或搶鮮版（Beta）通道上更新時遇到更新錯誤0x80070490，請嘗試下列短期解決問題。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-141">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="2f7cd-142">它牽涉到移動您的 insider 頻道、挑選更新，然後將 Insider 頻道移回。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-142">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>
#### <a name="stage-one---release-preview"></a><span data-ttu-id="2f7cd-143">階段 1-發行預覽</span><span class="sxs-lookup"><span data-stu-id="2f7cd-143">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="2f7cd-144">[設定]、[更新 & 安全性]、[Windows 測試人員計畫]、[選取 **發行預覽頻道**]。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-144">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="2f7cd-145">設定、更新 & 安全性、Windows Update， **檢查是否有更新**。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-145">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="2f7cd-146">更新之後，請繼續進行第二階段。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-146">After the update, continue on to Stage two.</span></span>
#### <a name="stage-two---dev-channel"></a><span data-ttu-id="2f7cd-147">第二階段-開發通道</span><span class="sxs-lookup"><span data-stu-id="2f7cd-147">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="2f7cd-148">[設定]、[更新 & 安全性]、[Windows 測試人員計畫]、[選取 **開發通道**]。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-148">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="2f7cd-149">設定、更新 & 安全性、Windows Update， **檢查是否有更新**。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-149">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>
## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="2f7cd-150">FFU 下載和 flash 路線</span><span class="sxs-lookup"><span data-stu-id="2f7cd-150">FFU download and flash directions</span></span>
<span data-ttu-id="2f7cd-151">若要使用飛行簽署 ffu 進行測試，您必須先將裝置解除鎖定，再閃爍飛行簽署的 ffu。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-151">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="2f7cd-152">在電腦上：</span><span class="sxs-lookup"><span data-stu-id="2f7cd-152">On PC:</span></span>
    1. <span data-ttu-id="2f7cd-153">從下載 ffu 到您的電腦 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-153">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="2f7cd-154">從 Microsoft Store 安裝 ARC (Advanced Recovery 隨附) ： [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-154">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="2f7cd-155">在 HoloLens-飛行解除鎖定：開啟 **設定**  >  **更新 & 安全性**  >  **Windows 測試人員計畫** 然後註冊、重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-155">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>
1. <span data-ttu-id="2f7cd-156">Flash FFU-現在您可以使用弧線來閃爍飛行簽署的 FFU。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-156">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>
### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="2f7cd-157">提供意見反應和報告問題</span><span class="sxs-lookup"><span data-stu-id="2f7cd-157">Provide feedback and report issues</span></span>
<span data-ttu-id="2f7cd-158">請使用您 HoloLens 上 [的意見反應中樞應用程式](hololens-feedback.md) 來提供意見反應和回報問題。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-158">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="2f7cd-159">使用意見反應中樞可確保包含所有必要的診斷資訊，以協助我們的工程師快速地偵測和解決問題。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-159">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="2f7cd-160">您應以同樣的方式報告中文和日文版 HoloLens 的問題。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-160">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>
> [!NOTE]
> <span data-ttu-id="2f7cd-161">請務必接受提示，詢問您是否要意見反應中樞存取您的 [檔] 資料夾， (在出現提示時選取 **[是]**) 。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-161">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>
## <a name="note-for-developers"></a><span data-ttu-id="2f7cd-162">開發人員注意事項</span><span class="sxs-lookup"><span data-stu-id="2f7cd-162">Note for developers</span></span>
<span data-ttu-id="2f7cd-163">您歡迎使用並建議您嘗試使用 HoloLens 的 Insider 組建來開發應用程式。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-163">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="2f7cd-164">請參閱 [HoloLens 開發人員檔](https://developer.microsoft.com/windows/mixed-reality/development) ，以開始使用。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-164">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="2f7cd-165">這些相同的指示適用于 HoloLens 的 Insider 組建。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-165">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="2f7cd-166">您可以使用您已在 HoloLens 開發中使用的相同 Unity 和 Visual Studio 組建。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-166">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>
## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="2f7cd-167">停止接收 Insider 組建</span><span class="sxs-lookup"><span data-stu-id="2f7cd-167">Stop receiving Insider builds</span></span>
<span data-ttu-id="2f7cd-168">如果您不想再收到 Windows 全像攝影版，您可以選擇在 HoloLens 執行生產組建時退出，也可以使用先進的復原功能來 [復原您](hololens-recovery.md) 的裝置，以將裝置復原到非 Insider 版本的 windows 電腦。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-168">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>
> [!CAUTION]
> <span data-ttu-id="2f7cd-169">有一個已知問題，就是在手動重新安裝全新的預覽組建之後，從 Insider Preview 組建中取消註冊的使用者會遇到藍色畫面。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-169">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="2f7cd-170">之後，他們必須手動復原其裝置。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-170">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="2f7cd-171">如需受影響的完整詳細資訊，請參閱此 [已知問題](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-171">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>
<span data-ttu-id="2f7cd-172">若要確認 HoloLens 正在執行生產組建：</span><span class="sxs-lookup"><span data-stu-id="2f7cd-172">To verify that your HoloLens is running a production build:</span></span>
1. <span data-ttu-id="2f7cd-173">移至 [ **設定] > 系統 > 的相關資訊**，並尋找組建編號。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-173">Go to **Settings > System > About**, and find the build number.</span></span>
1. <span data-ttu-id="2f7cd-174">[請參閱生產組建編號的版本](hololens-release-notes.md)資訊。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-174">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>
<span data-ttu-id="2f7cd-175">退出宣告 Insider build：</span><span class="sxs-lookup"><span data-stu-id="2f7cd-175">To opt out of Insider builds:</span></span>
1. <span data-ttu-id="2f7cd-176">在執行生產組建的 HoloLens 上，移至 [ **設定] > 更新 & 安全性 > Windows 測試人員計畫**，然後選取 [ **停止 Insider build**]。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-176">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>
1. <span data-ttu-id="2f7cd-177">請依照指示退出宣告您的裝置。</span><span class="sxs-lookup"><span data-stu-id="2f7cd-177">Follow the instructions to opt out your device.</span></span>
