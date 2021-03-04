---
title: 連接至行動電話和 5G
description: 從 HoloLens 混合實境裝置連接至行動電話網路。
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
ms.openlocfilehash: 3fd5f6baf05277bcbf2bf4152ba4735ca91e5bd0
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385637"
---
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="d7d62-103">連接至行動電話和 5G</span><span class="sxs-lookup"><span data-stu-id="d7d62-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="d7d62-104">HoloLens 2 支援兩種連接至行動電話和 5G 網路的方法：</span><span class="sxs-lookup"><span data-stu-id="d7d62-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="d7d62-105">由行動電話裝置提供的臨時 WiFi 網路，通常稱為「熱點」</span><span class="sxs-lookup"><span data-stu-id="d7d62-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="d7d62-106">USB-C 繫連裝置有限支援</span><span class="sxs-lookup"><span data-stu-id="d7d62-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="d7d62-107">熱點 (WiFi)</span><span class="sxs-lookup"><span data-stu-id="d7d62-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="d7d62-108">熱點可以滿足大多數的行動電話的連線需求。</span><span class="sxs-lookup"><span data-stu-id="d7d62-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="d7d62-109">HoloLens 2 WiFi 支援 802.11ac，可提供大多數常見使用案例所需的頻寬和延遲需求。</span><span class="sxs-lookup"><span data-stu-id="d7d62-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="d7d62-110">WiFi 也不含纜線，而且能與數量最多的行動電話裝置相容。</span><span class="sxs-lookup"><span data-stu-id="d7d62-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="d7d62-111">正在連接至熱點</span><span class="sxs-lookup"><span data-stu-id="d7d62-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="d7d62-112">請參閱裝置手冊，瞭解如何啟用其熱點模式。</span><span class="sxs-lookup"><span data-stu-id="d7d62-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="d7d62-113">啟用熱點模式，提供網路名稱和已知密碼。</span><span class="sxs-lookup"><span data-stu-id="d7d62-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="d7d62-114">在 HoloLens 2 網路設定中，找出步驟 2 中所建立的 WiFi 網路並加入。</span><span class="sxs-lookup"><span data-stu-id="d7d62-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="d7d62-115">USB-C 繫連</span><span class="sxs-lookup"><span data-stu-id="d7d62-115">USB-C Tethering</span></span>

<span data-ttu-id="d7d62-116">USB-C 繫連可以為需要該功能的進階工作負載提供較低的延遲。</span><span class="sxs-lookup"><span data-stu-id="d7d62-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="d7d62-117">例如，[Azure 遠端轉譯](https://azure.microsoft.com/services/remote-rendering)可受益于繫連功能。</span><span class="sxs-lookup"><span data-stu-id="d7d62-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="d7d62-118">請注意，進行繫連需要在行動電話裝置和 HoloLens 之間使用纜線，且繫連可支援有限裝置數量。</span><span class="sxs-lookup"><span data-stu-id="d7d62-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="d7d62-119">USB-C 相容性</span><span class="sxs-lookup"><span data-stu-id="d7d62-119">USB-C compatibility</span></span>

<span data-ttu-id="d7d62-120">以乙太網路介面卡呈現的裝置可以與 Windows Holographic 版 2004 及更新版本一起使用。</span><span class="sxs-lookup"><span data-stu-id="d7d62-120">Devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="d7d62-121">未以乙太網路介面卡呈現的裝置必須支援一般 Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) 驅動程式。</span><span class="sxs-lookup"><span data-stu-id="d7d62-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="d7d62-122">請洽詢您的裝置製造商，以瞭解是否支援一般通用的 Microsoft RNDIS 驅動程式。</span><span class="sxs-lookup"><span data-stu-id="d7d62-122">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="d7d62-123">不支援與 RNDIS 不相容或需要安裝驅動程式或應用程式的裝置。</span><span class="sxs-lookup"><span data-stu-id="d7d62-123">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="d7d62-124">雖然 Microsoft 不存留相容裝置的清單，但[這裡](https://aka.ms/HLCommunityCell) 具有針對該主題的社群討論。</span><span class="sxs-lookup"><span data-stu-id="d7d62-124">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="d7d62-125">連接到繫連裝置</span><span class="sxs-lookup"><span data-stu-id="d7d62-125">Connecting to a tethered device</span></span>

1. <span data-ttu-id="d7d62-126">請參閱裝置手冊，瞭解如何啟用 USB 資料共用。</span><span class="sxs-lookup"><span data-stu-id="d7d62-126">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="d7d62-127">此設定通常稱為「USB 繫連」、「資料共用」或「USB 數據機」。</span><span class="sxs-lookup"><span data-stu-id="d7d62-127">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="d7d62-128">啟用 USB 資料共用。</span><span class="sxs-lookup"><span data-stu-id="d7d62-128">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="d7d62-129">將裝置連接到 HoloLens USB-C 埠。</span><span class="sxs-lookup"><span data-stu-id="d7d62-129">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="d7d62-130">在 HoloLens 2 網路設定中，裝置會自動顯示為乙太網路連線。</span><span class="sxs-lookup"><span data-stu-id="d7d62-130">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
