---
title: 連線至藍牙和 USB-C 裝置
description: 開始從您的 HoloLens 混合現實裝置連接到藍牙和 USB 裝置和配件。
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
ms.openlocfilehash: 5fed56d7a0beeda0a0d96eddc63aaee872f3e52d
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639092"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="48863-103">連線至藍牙和 USB-C 裝置</span><span class="sxs-lookup"><span data-stu-id="48863-103">Connect to Bluetooth and USB-C devices</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="48863-104">配對藍牙裝置</span><span class="sxs-lookup"><span data-stu-id="48863-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="48863-105">HoloLens 2 支援下列藍牙裝置類別：</span><span class="sxs-lookup"><span data-stu-id="48863-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="48863-106">[HID](/windows-hardware/drivers/hid/)：</span><span class="sxs-lookup"><span data-stu-id="48863-106">[HID](/windows-hardware/drivers/hid/):</span></span>
    - <span data-ttu-id="48863-107">滑鼠</span><span class="sxs-lookup"><span data-stu-id="48863-107">Mouse</span></span>
    - <span data-ttu-id="48863-108">鍵盤</span><span class="sxs-lookup"><span data-stu-id="48863-108">Keyboard</span></span>
- <span data-ttu-id="48863-109">音訊輸出 (A2DP) 裝置</span><span class="sxs-lookup"><span data-stu-id="48863-109">Audio output (A2DP) devices</span></span>

<span data-ttu-id="48863-110">HoloLens 2 支援下列藍牙 api：</span><span class="sxs-lookup"><span data-stu-id="48863-110">HoloLens 2 supports the following Bluetooth APIs:</span></span>
- <span data-ttu-id="48863-111">GATT [伺服器](/windows/uwp/devices-sensors/gatt-server) 和 [用戶端](/windows/uwp/devices-sensors/gatt-client)</span><span class="sxs-lookup"><span data-stu-id="48863-111">GATT [Server](/windows/uwp/devices-sensors/gatt-server) and [Client](/windows/uwp/devices-sensors/gatt-client)</span></span>
- [<span data-ttu-id="48863-112">RFCOMM</span><span class="sxs-lookup"><span data-stu-id="48863-112">RFCOMM</span></span>](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> <span data-ttu-id="48863-113">您可能必須從 Microsoft Store 安裝對應的附屬應用程式，才能實際使用 HID 和 GATT 裝置。</span><span class="sxs-lookup"><span data-stu-id="48863-113">You may have to install corresponding companion apps from Microsoft Store to actually use the HID and GATT devices.</span></span>

<span data-ttu-id="48863-114">HoloLens (第1代) 支援下列藍牙裝置類別：</span><span class="sxs-lookup"><span data-stu-id="48863-114">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="48863-115">滑鼠</span><span class="sxs-lookup"><span data-stu-id="48863-115">Mouse</span></span>
- <span data-ttu-id="48863-116">鍵盤</span><span class="sxs-lookup"><span data-stu-id="48863-116">Keyboard</span></span>
- [<span data-ttu-id="48863-117">HoloLens (第1代) clicker</span><span class="sxs-lookup"><span data-stu-id="48863-117">HoloLens (1st gen) clicker</span></span>](hololens1-clicker.md)

> [!NOTE]
> <span data-ttu-id="48863-118">其他類型的藍牙裝置，例如喇叭、耳機、智慧型手機和遊戲台，可能會在 HoloLens 設定中列為可用。</span><span class="sxs-lookup"><span data-stu-id="48863-118">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="48863-119">不過，HoloLens (第一代) 不支援這些裝置。</span><span class="sxs-lookup"><span data-stu-id="48863-119">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="48863-120">如需詳細資訊，請參閱[HoloLens 設定列出可用的裝置，但裝置無法運作](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)。</span><span class="sxs-lookup"><span data-stu-id="48863-120">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="48863-121">配對藍牙鍵盤或滑鼠</span><span class="sxs-lookup"><span data-stu-id="48863-121">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="48863-122">開啟鍵盤或滑鼠，並讓它變成可探索。</span><span class="sxs-lookup"><span data-stu-id="48863-122">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="48863-123">若要瞭解如何讓裝置可供探索，請尋找裝置 (或其檔) 的相關資訊，或流覽製造商的網站。</span><span class="sxs-lookup"><span data-stu-id="48863-123">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="48863-124">使用 bloom 手勢 (HoloLens (第一代) ) 或開始手勢 (HoloLens 2) 移至 [**開始**]，然後選取 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="48863-124">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="48863-125">選取 [**裝置**]，並確定藍牙是 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="48863-125">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="48863-126">當您看到裝置名稱時，請選取 [ **配對**]，然後依照指示進行。</span><span class="sxs-lookup"><span data-stu-id="48863-126">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="48863-127">停用藍牙</span><span class="sxs-lookup"><span data-stu-id="48863-127">Disable Bluetooth</span></span>

<span data-ttu-id="48863-128">此程式會關閉藍牙無線電的 RF 元件，並停用 Microsoft HoloLens 上的所有藍牙功能。</span><span class="sxs-lookup"><span data-stu-id="48863-128">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="48863-129">使用 bloom 手勢 (HoloLens (第一代) ) 或開始手勢 (HoloLens 2) 移至 [**開始**]，然後選取 [**設定**  >  **裝置**]。</span><span class="sxs-lookup"><span data-stu-id="48863-129">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="48863-130">將 **藍牙** 的滑杆開關移至 **Off** 位置。</span><span class="sxs-lookup"><span data-stu-id="48863-130">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="48863-131">HoloLens 2：連線 USB-C 裝置</span><span class="sxs-lookup"><span data-stu-id="48863-131">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="48863-132">HoloLens 2 支援下列 USB-C 裝置類別：</span><span class="sxs-lookup"><span data-stu-id="48863-132">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="48863-133">大型儲存裝置 (例如拇指磁片磁碟機) </span><span class="sxs-lookup"><span data-stu-id="48863-133">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="48863-134">乙太網路介面卡 (包括乙太網路和充電) </span><span class="sxs-lookup"><span data-stu-id="48863-134">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="48863-135">USB-C-到 3.5 mm 數位音訊介面卡</span><span class="sxs-lookup"><span data-stu-id="48863-135">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="48863-136">USB-C 數位音訊耳機 (包括耳機卡和充電) </span><span class="sxs-lookup"><span data-stu-id="48863-136">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="48863-137">USB-C 外部麥克風 ([Windows 全像21H1 版和更新版本的](hololens-release-notes.md#windows-holographic-version-21h1)) </span><span class="sxs-lookup"><span data-stu-id="48863-137">USB-C External Microphones ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher)</span></span>
- <span data-ttu-id="48863-138">有線滑鼠</span><span class="sxs-lookup"><span data-stu-id="48863-138">Wired mouse</span></span>
- <span data-ttu-id="48863-139">有線鍵盤</span><span class="sxs-lookup"><span data-stu-id="48863-139">Wired keyboard</span></span>
- <span data-ttu-id="48863-140">結合 PD 中樞 (USB A plus PD 充電) </span><span class="sxs-lookup"><span data-stu-id="48863-140">Combination PD hubs (USB A plus PD charging)</span></span>


> [!NOTE]
> <span data-ttu-id="48863-141">為了回應客戶的意見反應，我們已啟用對行動電話連接的有限支援行動網卡直接透過 USB-C 進行 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="48863-141">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="48863-142">如需詳細資訊，請參閱[行動電話和5G 連線](hololens-cellular.md)。</span><span class="sxs-lookup"><span data-stu-id="48863-142">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="48863-143">USB-C 外部麥克風支援</span><span class="sxs-lookup"><span data-stu-id="48863-143">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="48863-144">插入 **USB mic 並不會自動將它設定為輸入裝置**。</span><span class="sxs-lookup"><span data-stu-id="48863-144">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="48863-145">當插入一組 USB-C 耳機時，使用者會發現耳機的音訊會自動重新導向到耳機，但 HoloLens OS 會將內部麥克風陣列的優先順序排列在任何其他輸入裝置上方。</span><span class="sxs-lookup"><span data-stu-id="48863-145">When plugging in a set of USB-C headphones, users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> <span data-ttu-id="48863-146">**若要使用 USB 麥克風，請遵循下列步驟。**</span><span class="sxs-lookup"><span data-stu-id="48863-146">**In order to use a USB-C microphone follow the steps below.**</span></span>

> [!NOTE]
> <span data-ttu-id="48863-147">在 Windows 全像21H1 版和更高[版本之前，](hololens-release-notes.md#windows-holographic-version-21h1)不能在組建中使用外部麥克風。</span><span class="sxs-lookup"><span data-stu-id="48863-147">External microphones cannot be used in builds prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher.</span></span> 

<span data-ttu-id="48863-148">使用者可以使用 [ **音效** 設定] 面板來選取 USB-C 連接的外部麥克風。</span><span class="sxs-lookup"><span data-stu-id="48863-148">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="48863-149">USB-C 麥克風可以用來呼叫、錄製等等。</span><span class="sxs-lookup"><span data-stu-id="48863-149">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="48863-150">開啟 **設定** 應用程式，然後選取 [**系統**  >  **音效**]。</span><span class="sxs-lookup"><span data-stu-id="48863-150">Open the **Settings** app and select **System** > **Sound**.</span></span>

![音效設定](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="48863-152">若要搭配使用外部麥克風與 **遠端協助**，使用者必須按一下 [管理音效裝置] 超連結。</span><span class="sxs-lookup"><span data-stu-id="48863-152">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="48863-153">然後使用下拉式清單將外部麥克風設定為 [ **預設** ] 或 [ **通訊] 預設值。**</span><span class="sxs-lookup"><span data-stu-id="48863-153">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="48863-154">選擇 [ **預設值** ] 表示外部麥克風將用於所有位置。</span><span class="sxs-lookup"><span data-stu-id="48863-154">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="48863-155">選擇 [**通訊預設值**] 表示外部麥克風將用於遠端協助和其他通訊應用程式，但 HoloLens mic 陣列仍可用於其他工作。</span><span class="sxs-lookup"><span data-stu-id="48863-155">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![管理音效裝置](images/usbc-mic-2.png)

<br>

![設定麥克風預設值](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="48863-158">藍牙麥克風支援呢？</span><span class="sxs-lookup"><span data-stu-id="48863-158">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="48863-159">可惜的是，HoloLens 2 上目前仍不支援藍牙的麥克風。</span><span class="sxs-lookup"><span data-stu-id="48863-159">Unfortunately, Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="48863-160">USB-C 中樞</span><span class="sxs-lookup"><span data-stu-id="48863-160">USB-C Hubs</span></span>

<span data-ttu-id="48863-161">有些使用者可能需要一次連接多個裝置。</span><span class="sxs-lookup"><span data-stu-id="48863-161">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="48863-162">如果使用者想要使用 [usb 麥克風](#usb-c-external-microphone-support) 以及另一部連線的裝置，則可能符合客戶的需求。</span><span class="sxs-lookup"><span data-stu-id="48863-162">For users who would like to use a [USB-C microphone](#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="48863-163">Microsoft 尚未測試這些裝置，也不能建議任何特定品牌。</span><span class="sxs-lookup"><span data-stu-id="48863-163">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

<span data-ttu-id="48863-164">**USB-C 中樞和連線裝置的需求：**</span><span class="sxs-lookup"><span data-stu-id="48863-164">**Requirements for USB-C hub and connected devices:**</span></span>

- <span data-ttu-id="48863-165">連接的裝置不一定需要安裝驅動程式。</span><span class="sxs-lookup"><span data-stu-id="48863-165">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="48863-166">所有已連線裝置的耗電量總計必須低於4.5 瓦。</span><span class="sxs-lookup"><span data-stu-id="48863-166">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="48863-167">連線至 Miracast</span><span class="sxs-lookup"><span data-stu-id="48863-167">Connect to Miracast</span></span>

<span data-ttu-id="48863-168">若要使用 Miracast，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="48863-168">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="48863-169">執行下列其中一個動作：</span><span class="sxs-lookup"><span data-stu-id="48863-169">Do one of the following:</span></span>  

   - <span data-ttu-id="48863-170">開啟 [ **開始** ] 功能表，然後選取 [ **顯示** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="48863-170">Open the **Start** menu, and select the **Display** icon.</span></span>
   - <span data-ttu-id="48863-171">當您注視 [開始] 功能表時，請說 **「連線」** 。</span><span class="sxs-lookup"><span data-stu-id="48863-171">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="48863-172">在出現的裝置清單中，選取可用的裝置。</span><span class="sxs-lookup"><span data-stu-id="48863-172">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="48863-173">完成配對以開始投射。</span><span class="sxs-lookup"><span data-stu-id="48863-173">Complete the pairing to begin projecting.</span></span>
