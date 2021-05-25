---
title: 連接至行動資料和5G
description: 從 HoloLens 混合現實裝置連接到行動電話通訊網路。
ms.assetid: f1aaadce-8762-41f8-bfeb-3b6067a2ec78
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 02/24/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 8318d011d6a593c1036b6bcf6f7973870b0dc294
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397489"
---
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="9b7cc-103">連接至行動資料和5G</span><span class="sxs-lookup"><span data-stu-id="9b7cc-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="9b7cc-104">HoloLens 2 支援兩種連線到行動電話和5G 網路的方法：</span><span class="sxs-lookup"><span data-stu-id="9b7cc-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="9b7cc-105">行動電話裝置所提供的臨機操作 WiFi 網路，通常稱為「熱點」</span><span class="sxs-lookup"><span data-stu-id="9b7cc-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="9b7cc-106">USB-C 行動網卡裝置的有限支援</span><span class="sxs-lookup"><span data-stu-id="9b7cc-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="9b7cc-107">熱點 (WiFi) </span><span class="sxs-lookup"><span data-stu-id="9b7cc-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="9b7cc-108">熱點可符合大部分的行動電話連接需求。</span><span class="sxs-lookup"><span data-stu-id="9b7cc-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="9b7cc-109">HoloLens 2 WiFi 支援 802.11 a c，可提供最常見使用案例所需的頻寬和延遲需求。</span><span class="sxs-lookup"><span data-stu-id="9b7cc-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="9b7cc-110">WiFi 也是無纜線，可提供與最大量行動電話裝置的相容性。</span><span class="sxs-lookup"><span data-stu-id="9b7cc-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="9b7cc-111">連接到熱點</span><span class="sxs-lookup"><span data-stu-id="9b7cc-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="9b7cc-112">請參閱您的裝置手冊，以瞭解如何啟用其熱點模式。</span><span class="sxs-lookup"><span data-stu-id="9b7cc-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="9b7cc-113">啟用作用點模式，提供網路的名稱以及已知的密碼。</span><span class="sxs-lookup"><span data-stu-id="9b7cc-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="9b7cc-114">在 [HoloLens 2 網路設定] 中，找出在步驟2中建立並加入的 WiFi 網路。</span><span class="sxs-lookup"><span data-stu-id="9b7cc-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="9b7cc-115">USB-C 的網際網路共用</span><span class="sxs-lookup"><span data-stu-id="9b7cc-115">USB-C Tethering</span></span>

<span data-ttu-id="9b7cc-116">USB-C 網際網路共用可以為需要的工作負載提供較低的延遲。</span><span class="sxs-lookup"><span data-stu-id="9b7cc-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="9b7cc-117">例如， [Azure 遠端轉譯](https://azure.microsoft.com/services/remote-rendering)可受益于網際網路共用。</span><span class="sxs-lookup"><span data-stu-id="9b7cc-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="9b7cc-118">請注意，網際網路共用需要行動電話裝置和 HoloLens 之間的纜線，而網際網路共用支援的裝置數量有限。</span><span class="sxs-lookup"><span data-stu-id="9b7cc-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="9b7cc-119">USB-C 相容性</span><span class="sxs-lookup"><span data-stu-id="9b7cc-119">USB-C compatibility</span></span>

<span data-ttu-id="9b7cc-120">以乙太網路介面卡形式呈現本身的裝置數量有限，可搭配 Windows 全像2004版和更新版本使用。</span><span class="sxs-lookup"><span data-stu-id="9b7cc-120">A limited number of devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="9b7cc-121">不是以乙太網路介面卡的形式呈現的裝置必須支援一般 Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) 驅動程式。</span><span class="sxs-lookup"><span data-stu-id="9b7cc-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="9b7cc-122">但是，只有有限數量的裝置會與 HoloLens 2 相容。</span><span class="sxs-lookup"><span data-stu-id="9b7cc-122">But, only a limited number of those devices are compatible with HoloLens 2.</span></span> <span data-ttu-id="9b7cc-123">請洽詢您裝置的製造商，以取得其是否支援一般 Microsoft RNDIS 驅動程式的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="9b7cc-123">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="9b7cc-124">不支援與 RNDIS 不相容的裝置，或需要安裝的驅動程式或應用程式。</span><span class="sxs-lookup"><span data-stu-id="9b7cc-124">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="9b7cc-125">雖然 Microsoft 不會維護相容裝置的清單，但 [這裡](https://aka.ms/HLCommunityCell)有一項主題討論。</span><span class="sxs-lookup"><span data-stu-id="9b7cc-125">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="9b7cc-126">連接至行動網卡裝置</span><span class="sxs-lookup"><span data-stu-id="9b7cc-126">Connecting to a tethered device</span></span>

1. <span data-ttu-id="9b7cc-127">請參閱您的裝置手冊，以瞭解如何啟用透過 USB 的資料共用。</span><span class="sxs-lookup"><span data-stu-id="9b7cc-127">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="9b7cc-128">這項設定通常稱為「USB 網際網路共用」、「資料共用」或「USB 數據機」。</span><span class="sxs-lookup"><span data-stu-id="9b7cc-128">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="9b7cc-129">啟用透過 USB 的資料共用。</span><span class="sxs-lookup"><span data-stu-id="9b7cc-129">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="9b7cc-130">將您的裝置連線到 HoloLens USB-C 埠。</span><span class="sxs-lookup"><span data-stu-id="9b7cc-130">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="9b7cc-131">在 [HoloLens 2 網路] 設定中，裝置會自動顯示為乙太網路連接。</span><span class="sxs-lookup"><span data-stu-id="9b7cc-131">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
