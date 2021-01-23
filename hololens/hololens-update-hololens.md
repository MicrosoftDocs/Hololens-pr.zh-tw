---
title: 更新 HoloLens
description: 瞭解如何檢查您的 HoloLens 組建編號、與裝置更新保持最新狀態、加入測試人員計畫，以及回滾更新。
keywords: 操作說明、更新、回滾、HoloLens、檢查組建、組建編號
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283934"
---
# <span data-ttu-id="e5510-104">更新 HoloLens</span><span class="sxs-lookup"><span data-stu-id="e5510-104">Update HoloLens</span></span>

<span data-ttu-id="e5510-105">HoloLens 使用 Windows Update，就像其他 Windows 10 裝置一樣。</span><span class="sxs-lookup"><span data-stu-id="e5510-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="e5510-106">您的 HoloLens 會在插入電源並聯機至網際網路時，自動下載並安裝系統更新（即使是處於待機狀態）。</span><span class="sxs-lookup"><span data-stu-id="e5510-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="e5510-107">本文將逐步說明 HoloLens 工具，以進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="e5510-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="e5510-108">在 (組建編號) 中查看您目前的作業系統版本</span><span class="sxs-lookup"><span data-stu-id="e5510-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="e5510-109">檢查更新</span><span class="sxs-lookup"><span data-stu-id="e5510-109">checking for updates</span></span>
- <span data-ttu-id="e5510-110">手動更新 HoloLens</span><span class="sxs-lookup"><span data-stu-id="e5510-110">manually updating HoloLens</span></span>
- <span data-ttu-id="e5510-111">回退到較舊的更新</span><span class="sxs-lookup"><span data-stu-id="e5510-111">rolling back to an older update</span></span>

## <span data-ttu-id="e5510-112">檢查您的作業系統版本 (組建編號) </span><span class="sxs-lookup"><span data-stu-id="e5510-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="e5510-113">您可以開啟 [設定] 應用程式，然後選取 [**系統**]，以驗證系統版本號碼 () 組建編號  >  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="e5510-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <span data-ttu-id="e5510-114">檢查更新並手動更新</span><span class="sxs-lookup"><span data-stu-id="e5510-114">Check for updates and manually update</span></span>

<span data-ttu-id="e5510-115">您可以在 [設定] 中隨時檢查是否有更新。</span><span class="sxs-lookup"><span data-stu-id="e5510-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="e5510-116">若要查看可用的更新並檢查是否有新的更新：</span><span class="sxs-lookup"><span data-stu-id="e5510-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="e5510-117">開啟 [ **設定** ] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="e5510-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="e5510-118">流覽至 [**更新 & 安全性**]  >  **Windows Update**。</span><span class="sxs-lookup"><span data-stu-id="e5510-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="e5510-119">選取 [ **檢查更新**]。</span><span class="sxs-lookup"><span data-stu-id="e5510-119">Select **Check for updates**.</span></span>

<span data-ttu-id="e5510-120">如果有可用的更新，就會開始下載新版本。</span><span class="sxs-lookup"><span data-stu-id="e5510-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="e5510-121">下載完成後，請選取 [ **立即重新開機** ] 按鈕以觸發安裝。</span><span class="sxs-lookup"><span data-stu-id="e5510-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="e5510-122">如果您的裝置低於40% 且未插上，重新開機就不會開始安裝更新。</span><span class="sxs-lookup"><span data-stu-id="e5510-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="e5510-123">當您的 HoloLens 安裝更新時，會顯示旋轉的齒輪和進度指標。</span><span class="sxs-lookup"><span data-stu-id="e5510-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="e5510-124">請勿在這段期間關閉 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="e5510-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="e5510-125">完成安裝之後，就會自動重新開機。</span><span class="sxs-lookup"><span data-stu-id="e5510-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="e5510-126">HoloLens 一次套用一個更新。</span><span class="sxs-lookup"><span data-stu-id="e5510-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="e5510-127">如果您的 HoloLens 超過一個最新版本，您可能需要多次執行更新程式，才能讓它完全保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="e5510-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <span data-ttu-id="e5510-128">回到先前的版本-HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="e5510-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="e5510-129">在某些情況下，您可能會想還原到舊版的 HoloLens 軟體。</span><span class="sxs-lookup"><span data-stu-id="e5510-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="e5510-130">您可以使用 [高級恢復隨附]，將您的 HoloLens 重設為較舊的版本來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="e5510-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="e5510-131">回到較舊的版本，就會刪除您的個人檔案和設定。</span><span class="sxs-lookup"><span data-stu-id="e5510-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="e5510-132">若要返回先前版本的 HoloLens 2，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e5510-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="e5510-133">確認您沒有任何電話或 Windows 裝置插入您的電腦。</span><span class="sxs-lookup"><span data-stu-id="e5510-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="e5510-134">在您的電腦上，從 Microsoft 網上商店下載 [ [高級恢復隨附](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) ]。</span><span class="sxs-lookup"><span data-stu-id="e5510-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="e5510-135">下載[最新的 HoloLens 2 發行版本](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="e5510-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="e5510-136">完成這些下載後，請開啟檔案**資源管理器**  >  **下載**。</span><span class="sxs-lookup"><span data-stu-id="e5510-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="e5510-137">以滑鼠右鍵按一下您剛剛下載的壓縮資料夾，然後選取 **[解壓縮全部]** > **[解壓縮]** 以將它解壓縮。</span><span class="sxs-lookup"><span data-stu-id="e5510-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="e5510-138">使用 USB-A 至 USB-A 電纜將您的 HoloLens 連接至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="e5510-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="e5510-139">(即使您已使用其他纜線來連接 HoloLens，這仍是最適合的纜線)。</span><span class="sxs-lookup"><span data-stu-id="e5510-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="e5510-140">[高級恢復隨附] 會自動偵測您的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="e5510-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="e5510-141">選取 [Microsoft HoloLens]\*\*\*\* 動態磚。</span><span class="sxs-lookup"><span data-stu-id="e5510-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="e5510-142">在下一個畫面中，選取 [ **手動封裝選取** ]，然後選取您在步驟4中解壓縮之資料夾中所包含的安裝檔。</span><span class="sxs-lookup"><span data-stu-id="e5510-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="e5510-143"> (尋找副檔名為 ffu 的檔案 ) </span><span class="sxs-lookup"><span data-stu-id="e5510-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="e5510-144">選取 [ **安裝軟體**]，然後依照指示進行。</span><span class="sxs-lookup"><span data-stu-id="e5510-144">Select **Install software**, and follow the instructions.</span></span>

## <span data-ttu-id="e5510-145">回到先前的版本-HoloLens (1 Gen) </span><span class="sxs-lookup"><span data-stu-id="e5510-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="e5510-146">在某些情況下，您可能會想還原到舊版的 HoloLens 軟體。</span><span class="sxs-lookup"><span data-stu-id="e5510-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="e5510-147">您可以使用 Windows 裝置恢復工具，將您的 HoloLens 重設為較舊的版本來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="e5510-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="e5510-148">回到較舊的版本，就會刪除您的個人檔案和設定。</span><span class="sxs-lookup"><span data-stu-id="e5510-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="e5510-149">若要返回前一版的 HoloLens 1，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e5510-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="e5510-150">確認您沒有任何電話或 Windows 裝置插入您的電腦。</span><span class="sxs-lookup"><span data-stu-id="e5510-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="e5510-151">在您的電腦上，下載 [Windows 裝置復原工具 (WDRT) ](https://support.microsoft.com/help/12379)]。</span><span class="sxs-lookup"><span data-stu-id="e5510-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="e5510-152">下載 [HoloLens 年度更新版復原套件](https://aka.ms/hololensrecovery)。</span><span class="sxs-lookup"><span data-stu-id="e5510-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="e5510-153">下載完成後，請開啟檔案**資源管理器**  >  **下載**。</span><span class="sxs-lookup"><span data-stu-id="e5510-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="e5510-154">以滑鼠右鍵按一下您剛下載的壓縮資料夾，然後選取 [**解壓所有**  >  **解壓縮**] 以將它解壓縮。</span><span class="sxs-lookup"><span data-stu-id="e5510-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="e5510-155">使用其隨附的微 USB 纜線，將您的 HoloLens 連接至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="e5510-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="e5510-156">(即使您已使用其他纜線來連接 HoloLens，這仍是最適合的纜線)。</span><span class="sxs-lookup"><span data-stu-id="e5510-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="e5510-157">WDRT 會自動偵測到您的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="e5510-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="e5510-158">選取 [Microsoft HoloLens]\*\*\*\* 動態磚。</span><span class="sxs-lookup"><span data-stu-id="e5510-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="e5510-159">在下一個畫面中，選取 [ **手動封裝選取** ]，然後選擇您在步驟4中解壓縮之資料夾中所包含的安裝檔。</span><span class="sxs-lookup"><span data-stu-id="e5510-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="e5510-160"> (尋找副檔名為 ffu 的檔案 ) </span><span class="sxs-lookup"><span data-stu-id="e5510-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="e5510-161">選取 [ **安裝軟體**]，然後依照指示進行。</span><span class="sxs-lookup"><span data-stu-id="e5510-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="e5510-162">如果 WDRT 沒有偵測到您的 HoloLens，請嘗試重新開機您的電腦。</span><span class="sxs-lookup"><span data-stu-id="e5510-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="e5510-163">如果仍然無法解決問題，請選取 [沒有偵測到我的裝置]\*\*\*\*，選取 **Microsoft HoloLens**，然後按照指示進行。</span><span class="sxs-lookup"><span data-stu-id="e5510-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="e5510-164">HoloLens 上的 Windows 測試人員計畫</span><span class="sxs-lookup"><span data-stu-id="e5510-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="e5510-165">想要在 HoloLens 中查看最新功能嗎？</span><span class="sxs-lookup"><span data-stu-id="e5510-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="e5510-166">如果是，請加入 Windows 測試人員計畫;您將會在正式的公用提供 HoloLens 軟體更新之前，取得更新預覽版。</span><span class="sxs-lookup"><span data-stu-id="e5510-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="e5510-167">[取得 Microsoft HoloLens 的 Windows](hololens-insider.md)測試人員預覽版。</span><span class="sxs-lookup"><span data-stu-id="e5510-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
