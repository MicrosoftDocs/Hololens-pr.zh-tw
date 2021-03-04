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
ms.openlocfilehash: 728bf8547315be96f879ff94a1290c1e2b3e7bf8
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385492"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="21ab0-103">連線至藍牙與 USB-C 裝置</span><span class="sxs-lookup"><span data-stu-id="21ab0-103">Connect to Bluetooth and USB-C devices</span></span>

> [!NOTE]
> <span data-ttu-id="21ab0-104">無法使用外部麥克風。</span><span class="sxs-lookup"><span data-stu-id="21ab0-104">External microphones cannot be used.</span></span> <span data-ttu-id="21ab0-105">HoloLens 2 使用其內建[麥克風陣列](hololens2-hardware.md#audio-and-speech)。</span><span class="sxs-lookup"><span data-stu-id="21ab0-105">HoloLens 2 uses its built-in [microphone array](hololens2-hardware.md#audio-and-speech).</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="21ab0-106">配對 [藍牙] 裝置</span><span class="sxs-lookup"><span data-stu-id="21ab0-106">Pair Bluetooth devices</span></span>

<span data-ttu-id="21ab0-107">HoloLens 2 支援下列 [藍牙] 裝置類型：</span><span class="sxs-lookup"><span data-stu-id="21ab0-107">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="21ab0-108">滑鼠</span><span class="sxs-lookup"><span data-stu-id="21ab0-108">Mouse</span></span>
- <span data-ttu-id="21ab0-109">鍵盤</span><span class="sxs-lookup"><span data-stu-id="21ab0-109">Keyboard</span></span>
- <span data-ttu-id="21ab0-110">[藍牙] 音訊輸出（A2DP）裝置</span><span class="sxs-lookup"><span data-stu-id="21ab0-110">Bluetooth audio output (A2DP) devices</span></span>

<span data-ttu-id="21ab0-111">HoloLens （第 1 代）支援下列 [藍牙] 裝置類型：</span><span class="sxs-lookup"><span data-stu-id="21ab0-111">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="21ab0-112">滑鼠</span><span class="sxs-lookup"><span data-stu-id="21ab0-112">Mouse</span></span>
- <span data-ttu-id="21ab0-113">鍵盤</span><span class="sxs-lookup"><span data-stu-id="21ab0-113">Keyboard</span></span>
- [<span data-ttu-id="21ab0-114">HoloLens (第 1 代) 簡報導覽裝置</span><span class="sxs-lookup"><span data-stu-id="21ab0-114">HoloLens (1st gen) clicker</span></span>](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> <span data-ttu-id="21ab0-115">其他類型的 [藍牙] 裝置，例如 喇叭、耳機、智慧型手機和遊戲台，可能會在 HoloLens 設定中列為可用裝置。</span><span class="sxs-lookup"><span data-stu-id="21ab0-115">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="21ab0-116">不過，HoloLens （第1代）並不支援這些裝置。</span><span class="sxs-lookup"><span data-stu-id="21ab0-116">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="21ab0-117">如需詳細資訊，可參照 [HoloLens 設定中列為可用裝置，但此裝置無法使用](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)。</span><span class="sxs-lookup"><span data-stu-id="21ab0-117">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="21ab0-118">配對 [藍牙] 鍵盤或滑鼠</span><span class="sxs-lookup"><span data-stu-id="21ab0-118">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="21ab0-119">開啟您的鍵盤或滑鼠，並將它設為可搜尋的。</span><span class="sxs-lookup"><span data-stu-id="21ab0-119">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="21ab0-120">若要瞭解如何讓裝置設為可搜尋的，請在裝置（或其文件）中尋找相關資訊，或造訪製造商的網站。</span><span class="sxs-lookup"><span data-stu-id="21ab0-120">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="21ab0-121">使用綻開手勢（HoloLens (第 1 代)）或開始手勢（HoloLens 2）移至 **開始**，然後選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="21ab0-121">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="21ab0-122">選取 **裝置**，並確定藍牙已開啟。</span><span class="sxs-lookup"><span data-stu-id="21ab0-122">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="21ab0-123">當您看到裝置名稱時，請選取 **配對**，然後按照指示操作。</span><span class="sxs-lookup"><span data-stu-id="21ab0-123">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="21ab0-124">停用 [藍牙] </span><span class="sxs-lookup"><span data-stu-id="21ab0-124">Disable Bluetooth</span></span>

<span data-ttu-id="21ab0-125">此程式會關閉 [藍牙] 無線電裝置的 RF 元件，並停用 Microsoft HoloLens 中的所有藍牙功能。</span><span class="sxs-lookup"><span data-stu-id="21ab0-125">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="21ab0-126">使用綻開手勢（HoloLens (第 1 代)）或開始手勢（HoloLens 2）並移至 **開始**，然後選取 **設定** > **裝置**。</span><span class="sxs-lookup"><span data-stu-id="21ab0-126">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="21ab0-127">將 **藍牙** 的滑杆開關移至 **[關閉]** 位置。</span><span class="sxs-lookup"><span data-stu-id="21ab0-127">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="21ab0-128">HoloLens 2：連接 USB-C 裝置</span><span class="sxs-lookup"><span data-stu-id="21ab0-128">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="21ab0-129">HoloLens 2 支援下列 USB-C 裝置類型：</span><span class="sxs-lookup"><span data-stu-id="21ab0-129">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="21ab0-130">大量儲存裝置（例如隨身碟）</span><span class="sxs-lookup"><span data-stu-id="21ab0-130">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="21ab0-131">乙太網路介面卡（包括乙太網路和充電）</span><span class="sxs-lookup"><span data-stu-id="21ab0-131">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="21ab0-132">USB-C-3.5 毫米數位音訊介面卡</span><span class="sxs-lookup"><span data-stu-id="21ab0-132">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="21ab0-133">USB-C 數位音訊耳機（包括耳機轉接器加上充電）</span><span class="sxs-lookup"><span data-stu-id="21ab0-133">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="21ab0-134">有線滑鼠</span><span class="sxs-lookup"><span data-stu-id="21ab0-134">Wired mouse</span></span>
- <span data-ttu-id="21ab0-135">有線鍵盤</span><span class="sxs-lookup"><span data-stu-id="21ab0-135">Wired keyboard</span></span>
- <span data-ttu-id="21ab0-136">組合 PD 集線器 (USB A 加 PD 充電)</span><span class="sxs-lookup"><span data-stu-id="21ab0-136">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="21ab0-137">針對客戶意見反應，我們已為 [行動數據連線能力] 啟用部分支援，並透過 USB-C 直接連結到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="21ab0-137">In response to customer feedback we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="21ab0-138">請參閱 [連接至行動電話和 5G](hololens-cellular.md) 以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="21ab0-138">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="21ab0-139">USB-C 集線器</span><span class="sxs-lookup"><span data-stu-id="21ab0-139">USB-C Hubs</span></span>

<span data-ttu-id="21ab0-140">有些使用者可能需要一次連線多個裝置。</span><span class="sxs-lookup"><span data-stu-id="21ab0-140">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="21ab0-141">對於希望預覽測試人員功能並[將 USB-C 麥克風](hololens-insider.md#usb-c-external-microphone-support)與其他連線裝置一起使用的使用者，USB-C 集線器可能適合客戶的需求。</span><span class="sxs-lookup"><span data-stu-id="21ab0-141">For users who would like to preview an Insider feature and [use a USB-C microphone](hololens-insider.md#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="21ab0-142">Microsoft 尚未測試這些裝置，我們也無法建議任何特定品牌。</span><span class="sxs-lookup"><span data-stu-id="21ab0-142">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

**<span data-ttu-id="21ab0-143">USB-C 集線器與已連線裝置的需求：</span><span class="sxs-lookup"><span data-stu-id="21ab0-143">Requirements for USB-C hub and connected devices:</span></span>**

- <span data-ttu-id="21ab0-144">已連線裝置必須不需要安裝驅動程式。</span><span class="sxs-lookup"><span data-stu-id="21ab0-144">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="21ab0-145">所有連線裝置的總功耗必須低於 4.5 瓦特。</span><span class="sxs-lookup"><span data-stu-id="21ab0-145">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="21ab0-146">連線到 Miracast</span><span class="sxs-lookup"><span data-stu-id="21ab0-146">Connect to Miracast</span></span>

<span data-ttu-id="21ab0-147">若要使用 Miracast，請按照下列步驟操作：</span><span class="sxs-lookup"><span data-stu-id="21ab0-147">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="21ab0-148">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="21ab0-148">Do one of the following:</span></span>  

   - <span data-ttu-id="21ab0-149">開啟 **開始** 功能表，並選取顯示器圖示。</span><span class="sxs-lookup"><span data-stu-id="21ab0-149">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="21ab0-150">在您注視 **開始** 功能表時說出「連線」。</span><span class="sxs-lookup"><span data-stu-id="21ab0-150">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="21ab0-151">在出現的裝置清單中，選取可用的裝置。</span><span class="sxs-lookup"><span data-stu-id="21ab0-151">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="21ab0-152">完成配對並開始投影。</span><span class="sxs-lookup"><span data-stu-id="21ab0-152">Complete the pairing to begin projecting.</span></span>
