---
title: 在 HoloLens 上尋找並儲存檔案
description: 瞭解如何在 HoloLens 上使用檔案資源管理器來開啟、查看及管理混合式現實裝置上的檔案。
keywords: 操作說明、檔案選擇器、檔案、相片、影片、圖片、OneDrive、儲存、檔案資源管理器、hololens
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283524"
---
# <span data-ttu-id="cbc2e-104">在 HoloLens 上尋找、開啟和儲存檔案</span><span class="sxs-lookup"><span data-stu-id="cbc2e-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="cbc2e-105">您在 HoloLens 上建立的檔案（包括相片和影片）會直接儲存到您的 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="cbc2e-106">以您管理 Windows 10 上的檔案的方式來查看及管理它們：</span><span class="sxs-lookup"><span data-stu-id="cbc2e-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="cbc2e-107">使用 [檔案資源管理器] app 來存取本機資料夾。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="cbc2e-108">在 app 的儲存區中。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-108">Within an app's storage.</span></span>
- <span data-ttu-id="cbc2e-109">在特殊資料夾中 (例如 [影片] 或 [音樂] 文件庫) 。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="cbc2e-110">使用包含 app 和檔案選擇器的儲存服務 (例如 OneDrive) 。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="cbc2e-111">使用採用 MTP (媒體傳輸通訊協定) 支援使用 USB 纜線連線到您 HoloLens 的桌上型電腦。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <span data-ttu-id="cbc2e-112">使用檔資源管理器在 HoloLens 上查看檔案</span><span class="sxs-lookup"><span data-stu-id="cbc2e-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="cbc2e-113">適用于 [2018 年4月更新 (RS4) （hololens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)）的所有 HoloLens 2 裝置和 hololens (1 gen) 。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="cbc2e-114">您可以在 HoloLens 上使用檔案資源管理器來查看及管理裝置上的檔案，包括3D 物件、檔及圖片。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="cbc2e-115">移至 [**啟動**   >  **所有 app**] 檔案   >  **瀏覽器**以開始使用。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="cbc2e-116">如果檔案資源管理器中沒有列出任何檔案，請在左上窗格中選取 [ **此裝置** ]。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="cbc2e-117">如果您在檔案資源管理器中沒有看到任何檔案，則 [最近的] 篩選可能處於作用中 (時鐘圖示會在左窗格) 中醒目提示。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="cbc2e-118">若要修正此問題，請在左窗格中選取 [ **此裝置** 檔] 圖示， ([時鐘] 圖示下方) ，或開啟功能表，然後選取 [ **此裝置**]。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <span data-ttu-id="cbc2e-119">尋找及查看您的相片和影片</span><span class="sxs-lookup"><span data-stu-id="cbc2e-119">Find and view your photos and videos</span></span>

<span data-ttu-id="cbc2e-120">[混合現實捕獲](holographic-photos-and-videos.md) 可讓您在 HoloLens 上拍攝混合現實相片和影片。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="cbc2e-121">這些相片和影片會儲存在裝置的 [相機] 滾動資料夾中。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="cbc2e-122">您可以透過以下方式存取使用 HoloLens 製作的相片和影片：</span><span class="sxs-lookup"><span data-stu-id="cbc2e-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="cbc2e-123">透過 [相片 app](holographic-photos-and-videos.md)直接存取相機。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="cbc2e-124">將相片和影片同步處理至 OneDrive，以將相片和影片上傳到雲端儲存空間。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="cbc2e-125">使用 [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)的 [混合現實捕獲] 頁面。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-125">using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <span data-ttu-id="cbc2e-126">相片 App</span><span class="sxs-lookup"><span data-stu-id="cbc2e-126">Photos app</span></span>

<span data-ttu-id="cbc2e-127">[相片] 應用程式是 [ **開始** ] 功能表上的其中一個預設 app，並隨附于 HoloLens 內建。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="cbc2e-128">深入瞭解 [如何使用相片 app 來查看內容](holographic-photos-and-videos.md)。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="cbc2e-129">您也可以從 Microsoft 網上商店安裝 [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) ，以將相片同步處理到其他裝置。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <span data-ttu-id="cbc2e-130">OneDrive 應用程式。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-130">OneDrive app</span></span>

<span data-ttu-id="cbc2e-131">[OneDrive](https://onedrive.live.com/) 可讓您使用任何裝置和任何使用者來存取、管理及共用您的相片和影片。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="cbc2e-132">若要存取 HoloLens 上捕獲的相片和影片，請從 HoloLens 上的 Microsoft Store 下載 [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) 。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="cbc2e-133">下載之後，請開啟 OneDrive 應用程式，然後選取 [**設定**  >  **相機上傳**]，然後開啟 **[相機上傳**]。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <span data-ttu-id="cbc2e-134">連接到電腦</span><span class="sxs-lookup"><span data-stu-id="cbc2e-134">Connect to a PC</span></span>

<span data-ttu-id="cbc2e-135">如果您的 HoloLens 執行的是 [windows 10 四月2018更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) 或更新版本，您可以使用 USB 纜線將您的 hololens 連線到 WINDOWS 10 電腦，方法是使用 MTP (媒體傳輸通訊協定) 來流覽裝置上的相片和影片。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-135">If your HoloLens is running the [Windows 10 April 2018 update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="cbc2e-136">如果您在裝置上設定 PIN 或密碼，您必須確認裝置已解除鎖定，才能流覽檔案。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="cbc2e-137">如果您已啟用 [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)，您可以使用它來流覽、檢索及管理儲存在您裝置上的相片和影片。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-137">If you have enabled the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <span data-ttu-id="cbc2e-138">存取 app 內的檔案</span><span class="sxs-lookup"><span data-stu-id="cbc2e-138">Access files within an app</span></span>

<span data-ttu-id="cbc2e-139">如果應用程式將檔案儲存在您的裝置上，您可以使用該應用程式來存取檔案。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <span data-ttu-id="cbc2e-140">從另一個應用程式要求檔案</span><span class="sxs-lookup"><span data-stu-id="cbc2e-140">Requesting files from another app</span></span>

<span data-ttu-id="cbc2e-141">應用程式可以使用檔案選擇器要求儲存檔 [案，或](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)從其他 app 開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-141">An application can request to save a file or open a file from another app by using [file pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span></span>

### <span data-ttu-id="cbc2e-142">已知資料夾</span><span class="sxs-lookup"><span data-stu-id="cbc2e-142">Known folders</span></span>

<span data-ttu-id="cbc2e-143">HoloLens 支援多個 [已知資料夾](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) ，這些應用程式可以要求存取權。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-143">HoloLens supports a number of [known folders](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <span data-ttu-id="cbc2e-144">在您的電腦上查看 HoloLens 檔案</span><span class="sxs-lookup"><span data-stu-id="cbc2e-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="cbc2e-145">與其他行動裝置類似，請使用 MTP 將 HoloLens 連線到桌上型電腦 (媒體傳輸通訊協定) ，然後在電腦上開啟檔案資源管理器，以輕鬆傳送。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="cbc2e-146">若要在您電腦上的檔案資源管理器中查看您的 HoloLens 檔案：</span><span class="sxs-lookup"><span data-stu-id="cbc2e-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="cbc2e-147">登入 HoloLens，然後使用 HoloLens 隨附的 USB 纜線將它插入電腦。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="cbc2e-148">選取 [ **開啟裝置] 以使用檔案瀏覽器來查看**檔案，或在 PC 上開啟檔案資源管理器，然後流覽至裝置。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="cbc2e-149">若要查看 HoloLens 的相關資訊，請在您電腦上的檔案資源管理器中，以滑鼠右鍵按一下裝置名稱，然後選取 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="cbc2e-150">HoloLens (1 gen) 不支援連接至外部硬碟或 SD 記憶卡。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <span data-ttu-id="cbc2e-151">同步處理到雲端</span><span class="sxs-lookup"><span data-stu-id="cbc2e-151">Sync to the cloud</span></span>

<span data-ttu-id="cbc2e-152">若要將您的 HoloLens 中的相片和其他檔案同步處理到雲端，請在 HoloLens 上安裝並設定 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="cbc2e-153">若要取得 OneDrive，請在您的 HoloLens 的 Microsoft Store 中搜尋。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="cbc2e-154">HoloLens 不會備份應用程式檔案和資料，因此最好將重要的內容儲存到 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="cbc2e-155">如此一來，如果您重設裝置或卸載應用程式，就會備份您的資訊。</span><span class="sxs-lookup"><span data-stu-id="cbc2e-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
