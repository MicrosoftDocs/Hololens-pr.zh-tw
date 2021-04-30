---
title: 在 HoloLens 上尋找和儲存檔案
description: 瞭解如何使用 HoloLens 上的檔案總管來開啟、查看和管理混合現實裝置上的檔案。
keywords: how to、file 選擇器、檔案、相片、影片、圖片、OneDrive、存放裝置、檔案瀏覽器、hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2d979b2cffd20589ddef7f11db5c7206eaea23cb
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308313"
---
# <a name="find-open-and-save-files-on-hololens"></a><span data-ttu-id="f7d1e-104">在 HoloLens 上尋找、開啟及儲存檔案</span><span class="sxs-lookup"><span data-stu-id="f7d1e-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="f7d1e-105">您在 HoloLens 上建立的檔案（包括相片和影片）都會直接儲存到 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="f7d1e-106">以您在 Windows 10 上管理檔案的相同方式來加以查看和管理：</span><span class="sxs-lookup"><span data-stu-id="f7d1e-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="f7d1e-107">使用檔案總管應用程式來存取本機資料夾。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="f7d1e-108">在應用程式的儲存體內。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-108">Within an app's storage.</span></span>
- <span data-ttu-id="f7d1e-109">在特殊資料夾中 (例如影片或音樂媒體櫃) 。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="f7d1e-110">使用包含應用程式和檔案選擇器 (的儲存體服務，例如 OneDrive) 。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="f7d1e-111">使用透過 USB 纜線連接到 HoloLens 的桌上型電腦，使用 MTP (媒體傳輸通訊協定) 支援。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <a name="view-files-on-hololens-using-file-explorer"></a><span data-ttu-id="f7d1e-112">使用檔案總管在 HoloLens 上查看檔案</span><span class="sxs-lookup"><span data-stu-id="f7d1e-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="f7d1e-113">適用于所有 HoloLens 2 裝置和 HoloLens (第1代) ，從 [Windows 10 2018 年4月更新 (RS4) 到 hololens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="f7d1e-114">使用 HoloLens 上的檔案總管來查看和管理裝置上的檔案，包括3D 物件、檔和圖片。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="f7d1e-115">移至 [**開始**]   >  **所有應用程式**   >  **檔案總管** 開始使用。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="f7d1e-116">如果檔案總管中沒有列出任何檔案，請在左上方的窗格中選取 **此裝置** 。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="f7d1e-117">如果您在檔案總管中看不到任何檔案，則 [最近] 篩選器可能會在左窗格中反白顯示 (時鐘圖示) 。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="f7d1e-118">若要修正此問題，請選取左窗格中的 [ **此裝置** 檔] 圖示 (時鐘圖示) 下方，或開啟功能表並選取 **此裝置**。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <a name="find-and-view-your-photos-and-videos"></a><span data-ttu-id="f7d1e-119">尋找並觀看您的相片和影片</span><span class="sxs-lookup"><span data-stu-id="f7d1e-119">Find and view your photos and videos</span></span>

<span data-ttu-id="f7d1e-120">[Mixed reality capture](holographic-photos-and-videos.md) 可讓您在 HoloLens 上採用混合的現實照片和影片。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="f7d1e-121">這些相片和影片會儲存至裝置的相機滾動資料夾。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="f7d1e-122">您可以透過下列方式，存取透過 HoloLens 所拍攝的相片和影片：</span><span class="sxs-lookup"><span data-stu-id="f7d1e-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="f7d1e-123">直接透過 [相片應用程式](holographic-photos-and-videos.md)存取相機。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="f7d1e-124">將相片和影片同步至 OneDrive，以將相片和影片上傳至雲端存放裝置。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="f7d1e-125">使用 [Windows 裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)的 [混合實境擷取] 頁面。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-125">using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <a name="photos-app"></a><span data-ttu-id="f7d1e-126">相片 App</span><span class="sxs-lookup"><span data-stu-id="f7d1e-126">Photos app</span></span>

<span data-ttu-id="f7d1e-127">相片應用程式是 [ **開始** ] 功能表上的其中一個預設應用程式，並內建于 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="f7d1e-128">深入瞭解 [如何使用相片應用程式來查看內容](holographic-photos-and-videos.md)。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="f7d1e-129">您也可以從 Microsoft Store 安裝 [OneDrive 應用程式](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) ，以將相片同步處理到其他裝置。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <a name="onedrive-app"></a><span data-ttu-id="f7d1e-130">OneDrive 應用程式。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-130">OneDrive app</span></span>

<span data-ttu-id="f7d1e-131">[OneDrive](https://onedrive.live.com/) 可讓您透過任何裝置和任何使用者來存取、管理及共用您的相片和影片。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="f7d1e-132">若要存取 HoloLens 上所捕獲的相片和影片，請從您的 HoloLens Microsoft Store 下載 [OneDrive 應用程式](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) 。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="f7d1e-133">下載之後，開啟 OneDrive 應用程式，並選取 [**設定**  >  **攝影機上傳**]，然後開啟 **相機上傳**。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <a name="connect-to-a-pc"></a><span data-ttu-id="f7d1e-134">連接到電腦</span><span class="sxs-lookup"><span data-stu-id="f7d1e-134">Connect to a PC</span></span>

<span data-ttu-id="f7d1e-135">如果 HoloLens 正在執行 [Windows 10 2018 年4月更新或更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) 版本，您可以使用 USB 纜線在裝置上使用 MTP (媒體傳輸通訊協定) ，來流覽裝置上的相片和影片，以將 hololens 連接到 WINDOWS 10 的電腦。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-135">If your HoloLens is running the [Windows 10 April 2018 update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="f7d1e-136">如果您的裝置上已設定 PIN 或密碼，您必須確定裝置已解除鎖定，以流覽檔案。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="f7d1e-137">如果您已啟用 [Windows 裝置入口網站](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)，您可以使用它來流覽、取出及管理裝置上儲存的相片和影片。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-137">If you have enabled the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <a name="access-files-within-an-app"></a><span data-ttu-id="f7d1e-138">存取應用程式內的檔案</span><span class="sxs-lookup"><span data-stu-id="f7d1e-138">Access files within an app</span></span>

<span data-ttu-id="f7d1e-139">如果應用程式將檔案儲存在您的裝置上，您可以使用該應用程式來存取它們。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <a name="requesting-files-from-another-app"></a><span data-ttu-id="f7d1e-140">從其他應用程式要求檔案</span><span class="sxs-lookup"><span data-stu-id="f7d1e-140">Requesting files from another app</span></span>

<span data-ttu-id="f7d1e-141">應用程式可以要求使用檔案選擇器來儲存檔案，或從另一個應用程式開啟[檔案。](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)</span><span class="sxs-lookup"><span data-stu-id="f7d1e-141">An application can request to save a file or open a file from another app by using [file pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span></span>

### <a name="known-folders"></a><span data-ttu-id="f7d1e-142">已知的資料夾</span><span class="sxs-lookup"><span data-stu-id="f7d1e-142">Known folders</span></span>

<span data-ttu-id="f7d1e-143">HoloLens 支援一些 [已知資料夾](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) ，讓應用程式可以要求存取權。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-143">HoloLens supports a number of [known folders](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <a name="view-hololens-files-on-your-pc"></a><span data-ttu-id="f7d1e-144">在您的電腦上查看 HoloLens 檔案</span><span class="sxs-lookup"><span data-stu-id="f7d1e-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="f7d1e-145">類似于其他行動裝置，請使用 MTP 將 HoloLens 連接到您的桌上型電腦 (媒體傳輸通訊協定) 並在電腦上開啟檔案總管，以存取 HoloLens 程式庫以輕鬆傳輸。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="f7d1e-146">若要在電腦上查看檔案總管中的 HoloLens 檔案：</span><span class="sxs-lookup"><span data-stu-id="f7d1e-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="f7d1e-147">登入 HoloLens，然後使用 HoloLens 隨附的 USB 纜線將它插到電腦上。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="f7d1e-148">選取 [ **開啟裝置] 以查看具有檔案總管** 的檔案，或開啟電腦上的檔案總管，然後流覽至裝置。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="f7d1e-149">若要查看 HoloLens 的相關資訊，請以滑鼠右鍵按一下電腦上檔案總管中的裝置名稱， **然後選取 [** 內容]。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="f7d1e-150">HoloLens (第1代) 不支援連接到外部硬碟或 SD 卡。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <a name="sync-to-the-cloud"></a><span data-ttu-id="f7d1e-151">同步至雲端</span><span class="sxs-lookup"><span data-stu-id="f7d1e-151">Sync to the cloud</span></span>

<span data-ttu-id="f7d1e-152">若要將相片和其他檔案從 HoloLens 同步至雲端，請在 HoloLens 上安裝並設定 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="f7d1e-153">若要取得 OneDrive，請在您 HoloLens 的 Microsoft Store 中搜尋。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="f7d1e-154">HoloLens 不會備份應用程式檔和資料，因此最好將重要的東西儲存到 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="f7d1e-155">如此一來，如果您重設裝置或卸載應用程式，將會備份您的資訊。</span><span class="sxs-lookup"><span data-stu-id="f7d1e-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
