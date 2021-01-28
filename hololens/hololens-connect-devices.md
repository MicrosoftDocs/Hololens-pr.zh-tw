---
title: 連線至藍牙與 USB-C 裝置
description: 開始從 HoloLens 混合實境裝置連接至藍牙與 USB-C 裝置和配件。
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
ms.openlocfilehash: 1b4f95f43fc60dffa2ca75322466857a0a20a0a7
ms.sourcegitcommit: 145bbabc390f626ba6633fa49423c38656cd2224
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "11302267"
---
# <span data-ttu-id="0e5c1-103">連線至藍牙與 USB-C 裝置</span><span class="sxs-lookup"><span data-stu-id="0e5c1-103">Connect to Bluetooth and USB-C devices</span></span>

> [!NOTE]
> <span data-ttu-id="0e5c1-104">無法使用外部麥克風。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-104">External microphones cannot be used.</span></span> <span data-ttu-id="0e5c1-105">HoloLens 2 使用其內建[麥克風陣列](hololens2-hardware.md#audio-and-speech)。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-105">HoloLens 2 uses its built-in [microphone array](hololens2-hardware.md#audio-and-speech).</span></span>

## <span data-ttu-id="0e5c1-106">配對 [藍牙] 裝置</span><span class="sxs-lookup"><span data-stu-id="0e5c1-106">Pair Bluetooth devices</span></span>

<span data-ttu-id="0e5c1-107">HoloLens 2 支援下列 [藍牙] 裝置類型：</span><span class="sxs-lookup"><span data-stu-id="0e5c1-107">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="0e5c1-108">滑鼠</span><span class="sxs-lookup"><span data-stu-id="0e5c1-108">Mouse</span></span>
- <span data-ttu-id="0e5c1-109">鍵盤</span><span class="sxs-lookup"><span data-stu-id="0e5c1-109">Keyboard</span></span>
- <span data-ttu-id="0e5c1-110">[藍牙] 音訊輸出（A2DP）裝置</span><span class="sxs-lookup"><span data-stu-id="0e5c1-110">Bluetooth audio output (A2DP) devices</span></span>

<span data-ttu-id="0e5c1-111">HoloLens （第 1 代）支援下列 [藍牙] 裝置類型：</span><span class="sxs-lookup"><span data-stu-id="0e5c1-111">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="0e5c1-112">滑鼠</span><span class="sxs-lookup"><span data-stu-id="0e5c1-112">Mouse</span></span>
- <span data-ttu-id="0e5c1-113">鍵盤</span><span class="sxs-lookup"><span data-stu-id="0e5c1-113">Keyboard</span></span>
- <span data-ttu-id="0e5c1-114">HoloLens (第 1 代) 簡報導覽裝置</span><span class="sxs-lookup"><span data-stu-id="0e5c1-114">HoloLens (1st gen) clicker</span></span>

> [!NOTE]
> <span data-ttu-id="0e5c1-115">其他類型的 [藍牙] 裝置，例如 喇叭、耳機、智慧型手機和遊戲台，可能會在 HoloLens 設定中列為可用裝置。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-115">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="0e5c1-116">不過，HoloLens （第1代）並不支援這些裝置。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-116">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="0e5c1-117">如需詳細資訊，可參照 [HoloLens 設定中列為可用裝置，但此裝置無法使用](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-117">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <span data-ttu-id="0e5c1-118">配對 [藍牙] 鍵盤或滑鼠</span><span class="sxs-lookup"><span data-stu-id="0e5c1-118">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="0e5c1-119">開啟您的鍵盤或滑鼠，並將它設為可搜尋的。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-119">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="0e5c1-120">若要瞭解如何讓裝置設為可搜尋的，請在裝置（或其文件）中尋找相關資訊，或造訪製造商的網站。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-120">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="0e5c1-121">使用綻開手勢（HoloLens (第 1 代)）或開始手勢（HoloLens 2）移至 **開始**，然後選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-121">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="0e5c1-122">選取 **裝置**，並確定藍牙已開啟。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-122">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="0e5c1-123">當您看到裝置名稱時，請選取 **配對**，然後按照指示操作。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-123">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

### <span data-ttu-id="0e5c1-124">HoloLens（第 1 代）：配對簡報導覽裝置</span><span class="sxs-lookup"><span data-stu-id="0e5c1-124">HoloLens (1st gen): Pair the clicker</span></span>

1. <span data-ttu-id="0e5c1-125">使用綻開手勢並移至 **開始**，然後選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-125">Use the bloom gesture to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="0e5c1-126">選取 **裝置**，並確定藍牙已開啟。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-126">Select **Devices**, and make sure that Bluetooth is on.</span></span>

1. <span data-ttu-id="0e5c1-127">使用筆尖壓住 [簡報導覽裝置] 的配對按鈕並按住不放，直到 [簡報導覽裝置] 狀態燈號呈白色閃爍。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-127">Use the tip of a pen to press and hold the clicker pairing button until the clicker status light blinks white.</span></span> <span data-ttu-id="0e5c1-128">請務必按住按鈕直到燈號出現閃爍為止。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-128">Make sure to hold down the button until the light starts blinking.</span></span>  

   <span data-ttu-id="0e5c1-129">[配對] 按鈕位於 [簡報導覽裝置] 的下方、手指環旁邊。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-129">The pairing button is on the underside of the clicker, next to the finger loop.</span></span>

   ![配對按鈕位於手指環的旁邊](images/use-hololens-clicker-1.png)

1. <span data-ttu-id="0e5c1-131">在配對的畫面上，選取 **簡報導覽裝置** > **配對**。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-131">On the pairing screen, select **Clicker** > **Pair**.</span></span>

## <span data-ttu-id="0e5c1-132">停用 [藍牙] </span><span class="sxs-lookup"><span data-stu-id="0e5c1-132">Disable Bluetooth</span></span>

<span data-ttu-id="0e5c1-133">此程式會關閉 [藍牙] 無線電裝置的 RF 元件，並停用 Microsoft HoloLens 中的所有藍牙功能。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-133">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="0e5c1-134">使用綻開手勢（HoloLens (第 1 代)）或開始手勢（HoloLens 2）並移至 **開始**，然後選取 **設定** > **裝置**。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-134">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="0e5c1-135">將 **藍牙** 的滑杆開關移至 **[關閉]** 位置。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-135">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <span data-ttu-id="0e5c1-136">HoloLens 2：連接 USB-C 裝置</span><span class="sxs-lookup"><span data-stu-id="0e5c1-136">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="0e5c1-137">HoloLens 2 支援下列 USB-C 裝置類型：</span><span class="sxs-lookup"><span data-stu-id="0e5c1-137">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="0e5c1-138">大量儲存裝置（例如隨身碟）</span><span class="sxs-lookup"><span data-stu-id="0e5c1-138">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="0e5c1-139">乙太網路介面卡（包括乙太網路和充電）</span><span class="sxs-lookup"><span data-stu-id="0e5c1-139">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="0e5c1-140">USB-C-3.5 毫米數位音訊介面卡</span><span class="sxs-lookup"><span data-stu-id="0e5c1-140">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="0e5c1-141">USB-C 數位音訊耳機（包括耳機轉接器加上充電）</span><span class="sxs-lookup"><span data-stu-id="0e5c1-141">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="0e5c1-142">有線滑鼠</span><span class="sxs-lookup"><span data-stu-id="0e5c1-142">Wired mouse</span></span>
- <span data-ttu-id="0e5c1-143">有線鍵盤</span><span class="sxs-lookup"><span data-stu-id="0e5c1-143">Wired keyboard</span></span>
- <span data-ttu-id="0e5c1-144">組合 PD 集線器（USB A 加 PD 充電）</span><span class="sxs-lookup"><span data-stu-id="0e5c1-144">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="0e5c1-145">部份具有 USB-C 連線的行動裝置，本身就會以乙太網配接器的形式顯示在 HoloLens 上，因此可在 [網際網路共用] 設定中使用，以 Windows 全像攝影版（版本 2004）開始。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-145">Some mobile devices with USB-C connections present themselves to the HoloLens as ethernet adaptors, and therefore could be used in a tethering configuration, starting with Windows Holographic, version 2004.</span></span> <span data-ttu-id="0e5c1-146">不支援需要單獨驅動程式，和/或安裝有用於設定之應用程式的 USB LTE 數據機。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-146">USB LTE modems that require a separate driver, and/or application installed for configuration are not supported.</span></span>

<span data-ttu-id="0e5c1-147">針對客戶意見反應，我們已為 [行動數據連線能力] 啟用部分支援，並透過 USB-C 直接連結到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-147">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span>  <span data-ttu-id="0e5c1-148">網路共享的連線能力只適用於支援一般的 Microsoft [ RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) 驅動程式執行，且不需要安裝任何其他驅動程式或應用程式。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-148">Tethered connectivity only works for devices that support the generic Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver implementation and that don’t require any additional drivers or application installs.</span></span>  <span data-ttu-id="0e5c1-149">當連線時，這些裝置會自動在 HoloLens 2 網路設定 UI 中顯示為一個新的乙太網連線。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-149">Such device, when connected, will automatically appear as a new Ethernet connection in the HoloLens 2 Network Settings UI.</span></span> <span data-ttu-id="0e5c1-150">請洽詢您的裝置製造商，以詳細瞭解是否支援一般通用的 Microsoft RNDIS 驅動程式。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-150">Please consult your device’s manufacturer for further details on whether it supports the generic Microsoft RNDIS driver.</span></span>

### <span data-ttu-id="0e5c1-151">USB-C 集線器</span><span class="sxs-lookup"><span data-stu-id="0e5c1-151">USB-C Hubs</span></span>

<span data-ttu-id="0e5c1-152">有些使用者可能需要一次連線多個裝置。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-152">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="0e5c1-153">對於希望預覽測試人員功能並[將 USB-C 麥克風](hololens-insider.md#usb-c-external-microphone-support)與其他連線裝置一起使用的使用者，USB-C 集線器可能適合客戶的需求。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-153">For users who would like to preview an Insider feature and [use a USB-C microphone](hololens-insider.md#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="0e5c1-154">Microsoft 尚未測試這些裝置，我們也無法建議任何特定品牌。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-154">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

**<span data-ttu-id="0e5c1-155">USB-C 集線器與已連線裝置的需求：</span><span class="sxs-lookup"><span data-stu-id="0e5c1-155">Requirements for USB-C hub and connected devices:</span></span>**

- <span data-ttu-id="0e5c1-156">已連線裝置必須不需要安裝驅動程式。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-156">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="0e5c1-157">所有連線裝置的總功耗必須低於 4.5 瓦特。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-157">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <span data-ttu-id="0e5c1-158">連線到 Miracast</span><span class="sxs-lookup"><span data-stu-id="0e5c1-158">Connect to Miracast</span></span>

<span data-ttu-id="0e5c1-159">若要使用 Miracast，請按照下列步驟操作：</span><span class="sxs-lookup"><span data-stu-id="0e5c1-159">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="0e5c1-160">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="0e5c1-160">Do one of the following:</span></span>  

   - <span data-ttu-id="0e5c1-161">開啟 **開始** 功能表，並選取顯示器圖示。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-161">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="0e5c1-162">在您注視 **開始** 功能表時說出「連線」。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-162">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="0e5c1-163">在出現的裝置清單中，選取可用的裝置。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-163">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="0e5c1-164">完成配對並開始投影。</span><span class="sxs-lookup"><span data-stu-id="0e5c1-164">Complete the pairing to begin projecting.</span></span>
