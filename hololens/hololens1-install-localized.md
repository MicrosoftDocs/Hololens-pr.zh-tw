---
title: 安裝 HoloLens 的當地語系化版本
description: 了解如何安裝當地語系化版本的 HoloLens (第 1 代)，包括中文版和日文版。
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
ms.sourcegitcommit: 01c0b0a789e156a9d29aaf6f61e36dfd09b8c01a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439009"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a><span data-ttu-id="2bbe4-103">安裝 HoloLens (第 1 代) 的當地語系化版本</span><span class="sxs-lookup"><span data-stu-id="2bbe4-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="2bbe4-104">若要切換到中文或日文版的 HoloLens，您必須使用 Windows Device Recovery Tool (WDRT) 在電腦上下載語言組建，然後將它安裝在 HoloLens 上。</span><span class="sxs-lookup"><span data-stu-id="2bbe4-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2bbe4-105">使用 WDRT 安裝 HoloLens 的中文或日文版時，會從 HoloLens 刪除現有的資料，例如個人檔案和設定。</span><span class="sxs-lookup"><span data-stu-id="2bbe4-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="2bbe4-106">在您的電腦上，下載並安裝 [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)。</span><span class="sxs-lookup"><span data-stu-id="2bbe4-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="2bbe4-107">下載您想要的語言套件到電腦上：[簡體中文](https://aka.ms/hololensdownload-ch)或[日文](https://aka.ms/hololensdownload-jp)。</span><span class="sxs-lookup"><span data-stu-id="2bbe4-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="2bbe4-108">下載完成後，選取 **[檔案總管]** > **[下載]**。</span><span class="sxs-lookup"><span data-stu-id="2bbe4-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="2bbe4-109">以滑鼠右鍵按一下您剛剛下載的壓縮資料夾，然後選取 **[解壓縮全部]** > **[解壓縮]** 以將它解壓縮。</span><span class="sxs-lookup"><span data-stu-id="2bbe4-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="2bbe4-110">使用隨附的 micro-USB 纜線，將 HoloLens 連接至電腦。</span><span class="sxs-lookup"><span data-stu-id="2bbe4-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="2bbe4-111">(即使您已使用其他纜線來連接 HoloLens，這仍是最適合的纜線)。</span><span class="sxs-lookup"><span data-stu-id="2bbe4-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="2bbe4-112">工具自動偵測到 HoloLens 之後，選取 [Microsoft HoloLens] 磚。</span><span class="sxs-lookup"><span data-stu-id="2bbe4-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="2bbe4-113">在下一個畫面中，選取  **[手動封裝選取]** ，然後選取位於步驟 4 中解壓縮之資料夾中的安裝檔。</span><span class="sxs-lookup"><span data-stu-id="2bbe4-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="2bbe4-114">(尋找副檔名為 ".ffu" 的檔案)。</span><span class="sxs-lookup"><span data-stu-id="2bbe4-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="2bbe4-115">選取  **[安裝軟體]**，然後依照指示進行。</span><span class="sxs-lookup"><span data-stu-id="2bbe4-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="2bbe4-116">在安裝組建之後，HoloLens 安裝程式會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="2bbe4-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="2bbe4-117">放在裝置上，然後依照設定指示進行。</span><span class="sxs-lookup"><span data-stu-id="2bbe4-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="2bbe4-118">完成設定後，請移至 **[設定]** > **[更新與安全性]** > **[Windows 測試人員計畫]**，並檢查您是否已設定為接收最新的預覽版。</span><span class="sxs-lookup"><span data-stu-id="2bbe4-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="2bbe4-119">就像英文預覽版一樣，Windows 測試人員計畫會將您的中文和日文版 HoloLens 保持在最新的預覽版組建。</span><span class="sxs-lookup"><span data-stu-id="2bbe4-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="2bbe4-120">您無法使用 [設定] 應用程式在英文、日文和中文之間變更系統語言。</span><span class="sxs-lookup"><span data-stu-id="2bbe4-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="2bbe4-121">刷新新組建是唯一支援的變更裝置系統語言的方法。</span><span class="sxs-lookup"><span data-stu-id="2bbe4-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="2bbe4-122">雖然您可以使用螢幕拼音鍵盤來輸入簡體中文或日文文字，但目前不支援使用藍牙硬體鍵盤輸入簡體中文或日文文字。</span><span class="sxs-lookup"><span data-stu-id="2bbe4-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="2bbe4-123">不過，在中文或日文 HoloLens 中，您可以繼續使用藍牙鍵盤輸入英文 (若要將硬體鍵盤切換為以英文輸入，請按 ~ 鍵)。</span><span class="sxs-lookup"><span data-stu-id="2bbe4-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
