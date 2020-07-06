---
title: 連線至藍牙與 USB-C 裝置
description: 本指南將逐步引導您連線至 [藍牙] 和 USB-C 裝置和附件。
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: d4c5441c1df198ae1c85be5d8f4fe38f10f0be4b
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827815"
---
# <span data-ttu-id="6282a-103">連線至藍牙與 USB-C 裝置</span><span class="sxs-lookup"><span data-stu-id="6282a-103">Connect to Bluetooth and USB-C devices</span></span>

## <span data-ttu-id="6282a-104">配對 [藍牙] 裝置</span><span class="sxs-lookup"><span data-stu-id="6282a-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="6282a-105">HoloLens 2 支援下列 [藍牙] 裝置類型：</span><span class="sxs-lookup"><span data-stu-id="6282a-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="6282a-106">滑鼠</span><span class="sxs-lookup"><span data-stu-id="6282a-106">Mouse</span></span>
- <span data-ttu-id="6282a-107">鍵盤</span><span class="sxs-lookup"><span data-stu-id="6282a-107">Keyboard</span></span>
- <span data-ttu-id="6282a-108">[藍牙] 音訊輸出（A2DP）裝置</span><span class="sxs-lookup"><span data-stu-id="6282a-108">Bluetooth audio output (A2DP) devices</span></span>

<span data-ttu-id="6282a-109">HoloLens （第 1 代）支援下列 [藍牙] 裝置類型：</span><span class="sxs-lookup"><span data-stu-id="6282a-109">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="6282a-110">滑鼠</span><span class="sxs-lookup"><span data-stu-id="6282a-110">Mouse</span></span>
- <span data-ttu-id="6282a-111">鍵盤</span><span class="sxs-lookup"><span data-stu-id="6282a-111">Keyboard</span></span>
- <span data-ttu-id="6282a-112">HoloLens (第 1 代) 簡報導覽裝置</span><span class="sxs-lookup"><span data-stu-id="6282a-112">HoloLens (1st gen) clicker</span></span>

> [!NOTE]
> <span data-ttu-id="6282a-113">其他類型的 [藍牙] 裝置，例如 喇叭、耳機、智慧型手機和遊戲台，可能會在 HoloLens 設定中列為可用裝置。</span><span class="sxs-lookup"><span data-stu-id="6282a-113">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="6282a-114">不過，HoloLens （第1代）並不支援這些裝置。</span><span class="sxs-lookup"><span data-stu-id="6282a-114">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="6282a-115">如需詳細資訊，可參照 [HoloLens 設定中列為可用裝置，但此裝置無法使用](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)。</span><span class="sxs-lookup"><span data-stu-id="6282a-115">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <span data-ttu-id="6282a-116">配對 [藍牙] 鍵盤或滑鼠</span><span class="sxs-lookup"><span data-stu-id="6282a-116">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="6282a-117">開啟您的鍵盤或滑鼠，並將它設為可搜尋的。</span><span class="sxs-lookup"><span data-stu-id="6282a-117">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="6282a-118">若要瞭解如何讓裝置設為可搜尋的，請在裝置（或其文件）中尋找相關資訊，或造訪製造商的網站。</span><span class="sxs-lookup"><span data-stu-id="6282a-118">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="6282a-119">使用綻開手勢（HoloLens (第 1 代)）或開始手勢（HoloLens 2）移至 **開始**，然後選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="6282a-119">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>
1. <span data-ttu-id="6282a-120">選取 **裝置**，並確定藍牙已開啟。</span><span class="sxs-lookup"><span data-stu-id="6282a-120">Select **Devices**, and make sure that Bluetooth is on.</span></span>  
1. <span data-ttu-id="6282a-121">當您看到裝置名稱時，請選取 **配對**，然後按照指示操作。</span><span class="sxs-lookup"><span data-stu-id="6282a-121">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

### <span data-ttu-id="6282a-122">HoloLens（第 1 代）：配對簡報導覽裝置</span><span class="sxs-lookup"><span data-stu-id="6282a-122">HoloLens (1st gen): Pair the clicker</span></span>

1. <span data-ttu-id="6282a-123">使用綻開手勢並移至 **開始**，然後選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="6282a-123">Use the bloom gesture to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="6282a-124">選取 **裝置**，並確定藍牙已開啟。</span><span class="sxs-lookup"><span data-stu-id="6282a-124">Select **Devices**, and make sure that Bluetooth is on.</span></span>

1. <span data-ttu-id="6282a-125">使用筆尖壓住 [簡報導覽裝置] 的配對按鈕並按住不放，直到 [簡報導覽裝置] 狀態燈號呈白色閃爍。</span><span class="sxs-lookup"><span data-stu-id="6282a-125">Use the tip of a pen to press and hold the clicker pairing button until the clicker status light blinks white.</span></span> <span data-ttu-id="6282a-126">請務必按住按鈕直到燈號出現閃爍為止。</span><span class="sxs-lookup"><span data-stu-id="6282a-126">Make sure to hold down the button until the light starts blinking.</span></span>  

   <span data-ttu-id="6282a-127">[配對] 按鈕位於 [簡報導覽裝置] 的下方、手指環旁邊。</span><span class="sxs-lookup"><span data-stu-id="6282a-127">The pairing button is on the underside of the clicker, next to the finger loop.</span></span>
   
   ![配對按鈕位於手指環的旁邊](images/use-hololens-clicker-1.png)
   
1. <span data-ttu-id="6282a-129">在配對的畫面上，選取 **簡報導覽裝置** > **配對**。</span><span class="sxs-lookup"><span data-stu-id="6282a-129">On the pairing screen, select **Clicker** > **Pair**.</span></span>

## <span data-ttu-id="6282a-130">HoloLens 2：連接 USB-C 裝置</span><span class="sxs-lookup"><span data-stu-id="6282a-130">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="6282a-131">HoloLens 2 支援下列 USB-C 裝置類型：</span><span class="sxs-lookup"><span data-stu-id="6282a-131">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="6282a-132">大量儲存裝置（例如隨身碟）</span><span class="sxs-lookup"><span data-stu-id="6282a-132">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="6282a-133">乙太網路介面卡（包括乙太網路和充電）</span><span class="sxs-lookup"><span data-stu-id="6282a-133">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="6282a-134">USB-C-3.5 毫米數位音訊介面卡</span><span class="sxs-lookup"><span data-stu-id="6282a-134">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="6282a-135">USB-C 數位音訊耳機（包括耳機轉接器加上充電）</span><span class="sxs-lookup"><span data-stu-id="6282a-135">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="6282a-136">有線滑鼠</span><span class="sxs-lookup"><span data-stu-id="6282a-136">Wired mouse</span></span>
- <span data-ttu-id="6282a-137">有線鍵盤</span><span class="sxs-lookup"><span data-stu-id="6282a-137">Wired keyboard</span></span>
- <span data-ttu-id="6282a-138">組合 PD 集線器（USB A 加 PD 充電）</span><span class="sxs-lookup"><span data-stu-id="6282a-138">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="6282a-139">部份具有 USB-C 連線的行動裝置，本身就會以乙太網配接器的形式顯示在 HoloLens 上，因此可在 [網際網路共用] 設定中使用，以 Windows 全像攝影版（版本 2004）開始。</span><span class="sxs-lookup"><span data-stu-id="6282a-139">Some mobile devices with USB-C connections present themselves to the HoloLens as ethernet adaptors, and therefore could be used in a tethering configuration, starting with Windows Holographic, version 2004.</span></span> <span data-ttu-id="6282a-140">不支援需要單獨驅動程式的 USB LTE 數據機，和/或設定用的已安裝應用程式</span><span class="sxs-lookup"><span data-stu-id="6282a-140">USB LTE modems that require a separate driver, and/or application installed for configuration are not supported</span></span>

## <span data-ttu-id="6282a-141">連線到 Miracast</span><span class="sxs-lookup"><span data-stu-id="6282a-141">Connect to Miracast</span></span>

<span data-ttu-id="6282a-142">若要使用 Miracast，請按照下列步驟操作：</span><span class="sxs-lookup"><span data-stu-id="6282a-142">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="6282a-143">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="6282a-143">Do one of the following:</span></span>  

   - <span data-ttu-id="6282a-144">開啟 **開始** 功能表，並選取顯示器圖示。</span><span class="sxs-lookup"><span data-stu-id="6282a-144">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="6282a-145">在您注視 **開始** 功能表時說出「連線」。</span><span class="sxs-lookup"><span data-stu-id="6282a-145">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="6282a-146">在出現的裝置清單中，選取可用的裝置。</span><span class="sxs-lookup"><span data-stu-id="6282a-146">On the list of devices that appears, select an available device.</span></span>
1. <span data-ttu-id="6282a-147">完成配對並開始投影。</span><span class="sxs-lookup"><span data-stu-id="6282a-147">Complete the pairing to begin projecting.</span></span>

## <span data-ttu-id="6282a-148">停用 [藍牙] </span><span class="sxs-lookup"><span data-stu-id="6282a-148">Disable Bluetooth</span></span>

<span data-ttu-id="6282a-149">此程式會關閉 [藍牙] 無線電裝置的 RF 元件，並停用 Microsoft HoloLens 中的所有藍牙功能。</span><span class="sxs-lookup"><span data-stu-id="6282a-149">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="6282a-150">使用綻開手勢（HoloLens (第 1 代)）或開始手勢（HoloLens 2）並移至 **開始**，然後選取 **設定** > **裝置**。</span><span class="sxs-lookup"><span data-stu-id="6282a-150">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>
1. <span data-ttu-id="6282a-151">將 **藍牙** 的滑杆開關移至 **[關閉]** 位置。</span><span class="sxs-lookup"><span data-stu-id="6282a-151">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>
