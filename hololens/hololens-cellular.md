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
# <a name="connect-to-cellular-and-5g"></a>連接至行動資料和5G

HoloLens 2 支援兩種連線到行動電話和5G 網路的方法：

- 行動電話裝置所提供的臨機操作 WiFi 網路，通常稱為「熱點」
- USB-C 行動網卡裝置的有限支援

## <a name="hotspot-wifi"></a>熱點 (WiFi) 

熱點可符合大部分的行動電話連接需求。 HoloLens 2 WiFi 支援 802.11 a c，可提供最常見使用案例所需的頻寬和延遲需求。 WiFi 也是無纜線，可提供與最大量行動電話裝置的相容性。

### <a name="connecting-to-a-hotspot"></a>連接到熱點

1. 請參閱您的裝置手冊，以瞭解如何啟用其熱點模式。
1. 啟用作用點模式，提供網路的名稱以及已知的密碼。
1. 在 [HoloLens 2 網路設定] 中，找出在步驟2中建立並加入的 WiFi 網路。

## <a name="usb-c-tethering"></a>USB-C 的網際網路共用

USB-C 網際網路共用可以為需要的工作負載提供較低的延遲。 例如， [Azure 遠端轉譯](https://azure.microsoft.com/services/remote-rendering)可受益于網際網路共用。 請注意，網際網路共用需要行動電話裝置和 HoloLens 之間的纜線，而網際網路共用支援的裝置數量有限。

### <a name="usb-c-compatibility"></a>USB-C 相容性

以乙太網路介面卡形式呈現本身的裝置數量有限，可搭配 Windows 全像2004版和更新版本使用。

不是以乙太網路介面卡的形式呈現的裝置必須支援一般 Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) 驅動程式。 但是，只有有限數量的裝置會與 HoloLens 2 相容。 請洽詢您裝置的製造商，以取得其是否支援一般 Microsoft RNDIS 驅動程式的詳細資料。

不支援與 RNDIS 不相容的裝置，或需要安裝的驅動程式或應用程式。

雖然 Microsoft 不會維護相容裝置的清單，但 [這裡](https://aka.ms/HLCommunityCell)有一項主題討論。

### <a name="connecting-to-a-tethered-device"></a>連接至行動網卡裝置

1. 請參閱您的裝置手冊，以瞭解如何啟用透過 USB 的資料共用。 這項設定通常稱為「USB 網際網路共用」、「資料共用」或「USB 數據機」。
1. 啟用透過 USB 的資料共用。
1. 將您的裝置連線到 HoloLens USB-C 埠。
1. 在 [HoloLens 2 網路] 設定中，裝置會自動顯示為乙太網路連接。
