---
title: 更新 HoloLens 2
description: 瞭解如何檢查您的 HoloLens 組建編號、掌握最新的裝置更新、加入測試人員計畫，以及回復更新。
keywords: 作法、更新、復原、HoloLens、檢查組建、組建編號
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924106"
---
# <a name="update-hololens-2"></a><span data-ttu-id="37b1d-104">更新 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="37b1d-104">Update HoloLens 2</span></span>

<span data-ttu-id="37b1d-105">HoloLens 使用 Windows Update，就像其他 Windows 10 裝置一樣。</span><span class="sxs-lookup"><span data-stu-id="37b1d-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="37b1d-106">當您的 HoloLens 進入電源並聯機到網際網路時，您的 HoloLens 將會自動下載並安裝系統更新，即使它處於待命狀態也一樣。</span><span class="sxs-lookup"><span data-stu-id="37b1d-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="37b1d-107">本文將逐步解說 HoloLens 工具：</span><span class="sxs-lookup"><span data-stu-id="37b1d-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="37b1d-108">查看您目前的作業系統版本 (組建編號) </span><span class="sxs-lookup"><span data-stu-id="37b1d-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="37b1d-109">檢查更新</span><span class="sxs-lookup"><span data-stu-id="37b1d-109">checking for updates</span></span>
- <span data-ttu-id="37b1d-110">手動更新 HoloLens</span><span class="sxs-lookup"><span data-stu-id="37b1d-110">manually updating HoloLens</span></span>
- <span data-ttu-id="37b1d-111">回復為較舊的更新</span><span class="sxs-lookup"><span data-stu-id="37b1d-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="37b1d-112">檢查您的作業系統版本 (組建編號) </span><span class="sxs-lookup"><span data-stu-id="37b1d-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="37b1d-113">您可以開啟 [設定] 應用程式並選取 [**系統**]，以確認系統版本號碼 (組建編號)  >  \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="37b1d-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="37b1d-114">檢查更新並手動更新</span><span class="sxs-lookup"><span data-stu-id="37b1d-114">Check for updates and manually update</span></span>

<span data-ttu-id="37b1d-115">您可以在設定中隨時檢查更新。</span><span class="sxs-lookup"><span data-stu-id="37b1d-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="37b1d-116">若要查看可用的更新並檢查是否有新的更新：</span><span class="sxs-lookup"><span data-stu-id="37b1d-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="37b1d-117">開啟 [設定]  應用程式。</span><span class="sxs-lookup"><span data-stu-id="37b1d-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="37b1d-118">流覽至 **更新 & 安全性**  >  **Windows Update**。</span><span class="sxs-lookup"><span data-stu-id="37b1d-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="37b1d-119">選取 [檢查更新]。</span><span class="sxs-lookup"><span data-stu-id="37b1d-119">Select **Check for updates**.</span></span>

<span data-ttu-id="37b1d-120">如果有可用的更新，則會開始下載新的版本。</span><span class="sxs-lookup"><span data-stu-id="37b1d-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="37b1d-121">下載完成之後，請選取 [ **立即重新開機** ] 按鈕來觸發安裝。</span><span class="sxs-lookup"><span data-stu-id="37b1d-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="37b1d-122">如果您的裝置低於40% 且未插入，則重新開機不會開始安裝更新。</span><span class="sxs-lookup"><span data-stu-id="37b1d-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="37b1d-123">當 HoloLens 正在安裝更新時，它會顯示旋轉的齒輪和進度指標。</span><span class="sxs-lookup"><span data-stu-id="37b1d-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="37b1d-124">在這段期間，請勿關閉 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="37b1d-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="37b1d-125">它會在安裝完成後自動重新開機。</span><span class="sxs-lookup"><span data-stu-id="37b1d-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="37b1d-126">HoloLens 一次只會套用一項更新。</span><span class="sxs-lookup"><span data-stu-id="37b1d-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="37b1d-127">如果 HoloLens 超過最新版本，您可能需要多次執行更新程式，才能讓它完全保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="37b1d-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version"></a><span data-ttu-id="37b1d-128">返回為先前的版本</span><span class="sxs-lookup"><span data-stu-id="37b1d-128">Go back to a previous version</span></span>

<span data-ttu-id="37b1d-129">在某些情況下，您可能會想要回到先前版本的 HoloLens 軟體。</span><span class="sxs-lookup"><span data-stu-id="37b1d-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="37b1d-130">建議的步驟如下：</span><span class="sxs-lookup"><span data-stu-id="37b1d-130">The recommended steps are:</span></span>

1. <span data-ttu-id="37b1d-131">請聯絡支援人員，看看他們是否可以修正您的問題。</span><span class="sxs-lookup"><span data-stu-id="37b1d-131">Contact Support to see if they can fix your issue.</span></span>
    1. <span data-ttu-id="37b1d-132">確定已啟用 **選擇性** 或 **完整** 遙測，如此可讓您的 bug 更具可操作，而且更容易讓工程師進行診斷。</span><span class="sxs-lookup"><span data-stu-id="37b1d-132">Ensure that **Optional** or **Full** telemetry is enabled -  this makes your bug more actionable and easier for engineers to diagnose.</span></span>
    1. <span data-ttu-id="37b1d-133">檔案[意見](hololens-feedback.md)反應應盡可能描述。</span><span class="sxs-lookup"><span data-stu-id="37b1d-133">[File Feedback](hololens-feedback.md) being as descriptive as possible.</span></span> <span data-ttu-id="37b1d-134">記下標題或使用「共用」功能，讓您可以與支援人員分享您的 bug。</span><span class="sxs-lookup"><span data-stu-id="37b1d-134">Take note of the title or use the share feature so you can share your bug with Support.</span></span>
    1. <span data-ttu-id="37b1d-135">請聯絡 [支援](https://aka.ms/hlsupport)人員。</span><span class="sxs-lookup"><span data-stu-id="37b1d-135">Contact [Support](https://aka.ms/hlsupport).</span></span> <span data-ttu-id="37b1d-136">如果您的問題是因為回到先前的版本而需要解決的問題，他們可以提供 FFU 來讓您的裝置閃爍。</span><span class="sxs-lookup"><span data-stu-id="37b1d-136">If your issue is one that needs to be solved by returning to a previous version, they can supply you the FFU to flash your device.</span></span>

1. <span data-ttu-id="37b1d-137">如果無法運作，請 [使用 Advanced Recovery 隨附的方式重設或重新刷新您的 HoloLens 2](hololens-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="37b1d-137">If that does not work, then [reset or reflash your HoloLens 2 with the Advanced Recovery Companion](hololens-recovery.md).</span></span>
    1. <span data-ttu-id="37b1d-138">在您的電腦上，下載 Microsoft Store 的 [Advanced Recovery 附隨](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 。</span><span class="sxs-lookup"><span data-stu-id="37b1d-138">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
    1. <span data-ttu-id="37b1d-139">確定您的電腦未插入任何電話或 Windows 裝置。</span><span class="sxs-lookup"><span data-stu-id="37b1d-139">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
    1. <span data-ttu-id="37b1d-140">選擇您想要閃爍的版本：</span><span class="sxs-lookup"><span data-stu-id="37b1d-140">Choose which version you want to flash to:</span></span>
        1. <span data-ttu-id="37b1d-141">您可以下載 [最新的 HoloLens 2 版本](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="37b1d-141">You can download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
        1. <span data-ttu-id="37b1d-142">您可以使用 ARC 主機的預設組建。</span><span class="sxs-lookup"><span data-stu-id="37b1d-142">You can use the default build that ARC hosts.</span></span> <span data-ttu-id="37b1d-143"> (如果您選擇此選項，請略過下一個步驟。 ) </span><span class="sxs-lookup"><span data-stu-id="37b1d-143">(If you choose this option skip the next step.)</span></span>
        1. <span data-ttu-id="37b1d-144">您可以使用所提供的組建支援。</span><span class="sxs-lookup"><span data-stu-id="37b1d-144">You can use a build Support provided you with.</span></span>
    1. <span data-ttu-id="37b1d-145">當您完成這些下載時，請開啟 **檔案總管**  >  **下載**。</span><span class="sxs-lookup"><span data-stu-id="37b1d-145">When you have finished these downloads, open **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="37b1d-146">在您剛剛下載的壓縮資料夾上按一下滑鼠右鍵，然後選取 [**解壓縮全部**  >  **解壓縮**] 將它解壓縮。</span><span class="sxs-lookup"><span data-stu-id="37b1d-146">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
    1. <span data-ttu-id="37b1d-147">使用 USB-A 至 USB-C 纜線將 HoloLens 連接到您的電腦。</span><span class="sxs-lookup"><span data-stu-id="37b1d-147">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="37b1d-148"> (即使您已經使用其他纜線連接 HoloLens，這項功能的效果最好。 ) </span><span class="sxs-lookup"><span data-stu-id="37b1d-148">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
    1. <span data-ttu-id="37b1d-149">Advanced Recovery 隨附會自動偵測您的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="37b1d-149">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="37b1d-150">選取 **Microsoft HoloLens** 圖格。</span><span class="sxs-lookup"><span data-stu-id="37b1d-150">Select the **Microsoft HoloLens** tile.</span></span>
    1. <span data-ttu-id="37b1d-151">在下一個畫面中，選取 [ **手動封裝選取** ]，然後選取您在步驟4解壓縮的資料夾中所包含的安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="37b1d-151">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="37b1d-152"> (尋找副檔名為 ffu 的檔案 ) </span><span class="sxs-lookup"><span data-stu-id="37b1d-152">(Look for a file with the .ffu extension.)</span></span>
    1. <span data-ttu-id="37b1d-153">選取 [ **安裝軟體**]，並遵循指示進行。</span><span class="sxs-lookup"><span data-stu-id="37b1d-153">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="37b1d-154">回到較舊的版本會刪除您的個人檔案和設定。</span><span class="sxs-lookup"><span data-stu-id="37b1d-154">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="37b1d-155">此外，如果您想要保留目前安裝的版本，您也可以手動 [暫停更新](hololens-updates.md#pause-updates-via-device)。</span><span class="sxs-lookup"><span data-stu-id="37b1d-155">Additionally, if you would like to stay on your currently installed release, you can also manually [pause updates](hololens-updates.md#pause-updates-via-device).</span></span> <span data-ttu-id="37b1d-156">這可讓工程小組時間修正問題。</span><span class="sxs-lookup"><span data-stu-id="37b1d-156">This will give the Engineering Team time to fix the issue.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="37b1d-157">HoloLens 上的 Windows 測試人員計畫</span><span class="sxs-lookup"><span data-stu-id="37b1d-157">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="37b1d-158">想要查看 HoloLens 中的最新功能嗎？</span><span class="sxs-lookup"><span data-stu-id="37b1d-158">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="37b1d-159">如果是，請加入 Windows 測試人員計畫;您將可在正式運作之前，存取 HoloLens 軟體更新的預覽組建。</span><span class="sxs-lookup"><span data-stu-id="37b1d-159">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="37b1d-160">[取得 Microsoft HoloLens 的 Windows 測試人員預覽](hololens-insider.md)。</span><span class="sxs-lookup"><span data-stu-id="37b1d-160">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
