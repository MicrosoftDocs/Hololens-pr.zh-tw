---
title: 更新 HoloLens
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308810"
---
# <a name="update-hololens"></a><span data-ttu-id="6bb8a-104">更新 HoloLens</span><span class="sxs-lookup"><span data-stu-id="6bb8a-104">Update HoloLens</span></span>

<span data-ttu-id="6bb8a-105">HoloLens 使用 Windows Update，就像其他 Windows 10 裝置一樣。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="6bb8a-106">當您的 HoloLens 進入電源並聯機到網際網路時，您的 HoloLens 將會自動下載並安裝系統更新，即使它處於待命狀態也一樣。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="6bb8a-107">本文將逐步解說 HoloLens 工具：</span><span class="sxs-lookup"><span data-stu-id="6bb8a-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="6bb8a-108">查看您目前的作業系統版本 (組建編號) </span><span class="sxs-lookup"><span data-stu-id="6bb8a-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="6bb8a-109">檢查更新</span><span class="sxs-lookup"><span data-stu-id="6bb8a-109">checking for updates</span></span>
- <span data-ttu-id="6bb8a-110">手動更新 HoloLens</span><span class="sxs-lookup"><span data-stu-id="6bb8a-110">manually updating HoloLens</span></span>
- <span data-ttu-id="6bb8a-111">回復為較舊的更新</span><span class="sxs-lookup"><span data-stu-id="6bb8a-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="6bb8a-112">檢查您的作業系統版本 (組建編號) </span><span class="sxs-lookup"><span data-stu-id="6bb8a-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="6bb8a-113">您可以開啟 [設定] 應用程式並選取 [**系統**]，以確認系統版本號碼 (組建編號)  >  \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="6bb8a-114">檢查更新並手動更新</span><span class="sxs-lookup"><span data-stu-id="6bb8a-114">Check for updates and manually update</span></span>

<span data-ttu-id="6bb8a-115">您可以在設定中隨時檢查更新。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="6bb8a-116">若要查看可用的更新並檢查是否有新的更新：</span><span class="sxs-lookup"><span data-stu-id="6bb8a-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="6bb8a-117">開啟 [設定]  應用程式。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="6bb8a-118">流覽至 **更新 & 安全性**  >  **Windows Update**。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="6bb8a-119">選取 [檢查更新]。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-119">Select **Check for updates**.</span></span>

<span data-ttu-id="6bb8a-120">如果有可用的更新，則會開始下載新的版本。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="6bb8a-121">下載完成之後，請選取 [ **立即重新開機** ] 按鈕來觸發安裝。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="6bb8a-122">如果您的裝置低於40% 且未插入，則重新開機不會開始安裝更新。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="6bb8a-123">當 HoloLens 正在安裝更新時，它會顯示旋轉的齒輪和進度指標。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="6bb8a-124">在這段期間，請勿關閉 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="6bb8a-125">它會在安裝完成後自動重新開機。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="6bb8a-126">HoloLens 一次只會套用一項更新。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="6bb8a-127">如果 HoloLens 超過最新版本，您可能需要多次執行更新程式，才能讓它完全保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version---hololens-2"></a><span data-ttu-id="6bb8a-128">返回至上一版-HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="6bb8a-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="6bb8a-129">在某些情況下，您可能會想要回到先前版本的 HoloLens 軟體。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="6bb8a-130">若要這麼做，您可以使用 Advanced Recovery 附屬版，將 HoloLens 重設為舊版。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="6bb8a-131">回到較舊的版本會刪除您的個人檔案和設定。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="6bb8a-132">若要返回舊版 HoloLens 2，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6bb8a-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="6bb8a-133">確定您的電腦未插入任何電話或 Windows 裝置。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="6bb8a-134">在您的電腦上，下載 Microsoft Store 的 [Advanced Recovery 附隨](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="6bb8a-135">下載 [最新的 HoloLens 2 版本](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="6bb8a-136">當您完成這些下載時，請開啟 [檔案 **瀏覽器**  >  **下載**]。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="6bb8a-137">在您剛剛下載的壓縮資料夾上按一下滑鼠右鍵，然後選取 [**解壓縮全部**  >  **解壓縮**] 將它解壓縮。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="6bb8a-138">使用 USB-A 至 USB-C 纜線將 HoloLens 連接到您的電腦。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="6bb8a-139"> (即使您已經使用其他纜線連接 HoloLens，這項功能的效果最好。 ) </span><span class="sxs-lookup"><span data-stu-id="6bb8a-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="6bb8a-140">Advanced Recovery 隨附會自動偵測您的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="6bb8a-141">選取 **Microsoft HoloLens** 圖格。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="6bb8a-142">在下一個畫面中，選取 [ **手動封裝選取** ]，然後選取您在步驟4解壓縮的資料夾中所包含的安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="6bb8a-143"> (尋找副檔名為 ffu 的檔案 ) </span><span class="sxs-lookup"><span data-stu-id="6bb8a-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="6bb8a-144">選取 [ **安裝軟體**]，並遵循指示進行。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-144">Select **Install software**, and follow the instructions.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="6bb8a-145">返回為先前的版本-HoloLens (第1代) </span><span class="sxs-lookup"><span data-stu-id="6bb8a-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="6bb8a-146">在某些情況下，您可能會想要回到先前版本的 HoloLens 軟體。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="6bb8a-147">若要這麼做，您可以使用 Windows 裝置復原工具將 HoloLens 重設為較早的版本。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="6bb8a-148">回到較舊的版本會刪除您的個人檔案和設定。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="6bb8a-149">若要返回之前的 HoloLens 1 版本，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6bb8a-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="6bb8a-150">確定您的電腦未插入任何電話或 Windows 裝置。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="6bb8a-151">在您的電腦上，下載 [Windows 裝置修復工具 (WDRT) ](https://support.microsoft.com/help/12379)。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="6bb8a-152">下載 [HoloLens 年度更新修復套件](https://aka.ms/hololensrecovery)。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="6bb8a-153">當下載完成時，開啟 [檔案 **瀏覽器**  >  **下載**]。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="6bb8a-154">在您剛剛下載的壓縮資料夾上按一下滑鼠右鍵，然後選取 [**解壓縮全部**  >  **解壓縮**] 將它解壓縮。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="6bb8a-155">使用隨附的微型 USB 纜線將 HoloLens 連接到您的電腦。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="6bb8a-156"> (即使您已經使用其他纜線連接 HoloLens，這項功能的效果最好。 ) </span><span class="sxs-lookup"><span data-stu-id="6bb8a-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="6bb8a-157">WDRT 會自動偵測您的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="6bb8a-158">選取 **Microsoft HoloLens** 圖格。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="6bb8a-159">在下一個畫面中，選取 [ **手動封裝選取專案** ]，然後選擇您在步驟4解壓縮的資料夾中所包含的安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="6bb8a-160"> (尋找副檔名為 ffu 的檔案 ) </span><span class="sxs-lookup"><span data-stu-id="6bb8a-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="6bb8a-161">選取 [ **安裝軟體**]，並遵循指示進行。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="6bb8a-162">如果 WDRT 未偵測到 HoloLens，請嘗試重新開機您的電腦。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="6bb8a-163">如果無法運作，請選取 [ **未偵測到我的裝置**]，選取 [ **Microsoft HoloLens**]，然後依照指示進行。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="6bb8a-164">HoloLens 上的 Windows 測試人員計畫</span><span class="sxs-lookup"><span data-stu-id="6bb8a-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="6bb8a-165">想要查看 HoloLens 中的最新功能嗎？</span><span class="sxs-lookup"><span data-stu-id="6bb8a-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="6bb8a-166">如果是，請加入 Windows 測試人員計畫;您將可在正式運作之前，存取 HoloLens 軟體更新的預覽組建。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="6bb8a-167">[取得 Microsoft HoloLens 的 Windows 測試人員預覽](hololens-insider.md)。</span><span class="sxs-lookup"><span data-stu-id="6bb8a-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
