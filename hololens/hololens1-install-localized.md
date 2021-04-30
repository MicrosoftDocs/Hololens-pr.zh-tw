---
title: 安裝 HoloLens 的當地語系化版本
description: 瞭解如何安裝 HoloLens (第一代) 的當地語系化版本，包括中文和日文版本。
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 74eb003aafd23218b90988abe113d35f1fc3035a
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309046"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a><span data-ttu-id="1b765-103">安裝當地語系化版本的 HoloLens (第1代) </span><span class="sxs-lookup"><span data-stu-id="1b765-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="1b765-104">若要切換到中文或日文版的 HoloLens，您必須使用 Windows 裝置復原工具 (WDRT) 在電腦上下載語言的組建，然後將它安裝在 HoloLens 上。</span><span class="sxs-lookup"><span data-stu-id="1b765-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1b765-105">使用 WDRT 安裝 HoloLens 的中文或日文版時，會從您的 HoloLens 刪除現有的資料，例如個人檔案和設定。</span><span class="sxs-lookup"><span data-stu-id="1b765-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="1b765-106">在您的電腦上，下載並安裝 [Windows 裝置修復工具 (WDRT) ](https://support.microsoft.com/help/12379)。</span><span class="sxs-lookup"><span data-stu-id="1b765-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="1b765-107">將您想要的語言套件下載到您的電腦：  [簡體中文](https://aka.ms/hololensdownload-ch) 或 [日文](https://aka.ms/hololensdownload-jp)。</span><span class="sxs-lookup"><span data-stu-id="1b765-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="1b765-108">當下載完成時，請選取 **檔案總管**  >  **下載**。</span><span class="sxs-lookup"><span data-stu-id="1b765-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="1b765-109">在您剛剛下載的壓縮資料夾上按一下滑鼠右鍵，然後選取 [**解壓縮全部**  >  **解壓縮**] 將它解壓縮。</span><span class="sxs-lookup"><span data-stu-id="1b765-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="1b765-110">使用隨附的微型 USB 纜線將 HoloLens 連接到您的電腦。</span><span class="sxs-lookup"><span data-stu-id="1b765-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="1b765-111"> (即使您已經使用其他纜線連接 HoloLens，這項功能的效果最好。 ) </span><span class="sxs-lookup"><span data-stu-id="1b765-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="1b765-112">工具自動偵測到 HoloLens 之後，請選取 Microsoft HoloLens 圖格。</span><span class="sxs-lookup"><span data-stu-id="1b765-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="1b765-113">在下一個畫面中，選取 [ **手動封裝選取**]，   然後選取您在步驟4解壓縮之資料夾中的安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="1b765-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="1b765-114"> (尋找副檔名為 ". ffu" 的檔案 ) </span><span class="sxs-lookup"><span data-stu-id="1b765-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="1b765-115">選取 [ **安裝軟體** ]，然後依照指示執行。</span><span class="sxs-lookup"><span data-stu-id="1b765-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="1b765-116">組建安裝之後，會自動啟動 HoloLens 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="1b765-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="1b765-117">放在裝置上，並遵循安裝指示。</span><span class="sxs-lookup"><span data-stu-id="1b765-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="1b765-118">當您完成安裝時，請移至 [**設定**  >  **更新 & 安全性**  >  **Windows 測試人員計畫**]，並確認您已設定為接收最新的預覽組建。</span><span class="sxs-lookup"><span data-stu-id="1b765-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="1b765-119">就像英文版的預覽組建一樣，Windows 測試人員計畫使用最新的預覽組建將 HoloLens 的中文和日文版本保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="1b765-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="1b765-120">您無法使用 [設定] 應用程式來變更英文、日文和中文之間的系統語言。</span><span class="sxs-lookup"><span data-stu-id="1b765-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="1b765-121">將新組建閃爍是唯一支援變更裝置系統語言的方式。</span><span class="sxs-lookup"><span data-stu-id="1b765-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="1b765-122">雖然您可以使用螢幕上的拼音鍵盤來輸入簡體中文或日文文字，但目前不支援使用藍牙硬體鍵盤來輸入簡體中文或日文文字。</span><span class="sxs-lookup"><span data-stu-id="1b765-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="1b765-123">不過，在中文或日文 HoloLens 上，您可以繼續使用藍牙鍵盤輸入英文 (若要切換硬體鍵盤來輸入英文，請按 [~] 鍵) 。</span><span class="sxs-lookup"><span data-stu-id="1b765-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
