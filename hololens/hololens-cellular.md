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
# <a name="connect-to-cellular-and-5g"></a>連接至行動電話和 5G

HoloLens 2 支援兩種連接至行動電話和 5G 網路的方法：

- 由行動電話裝置提供的臨時 WiFi 網路，通常稱為「熱點」
- USB-C 繫連裝置有限支援

## <a name="hotspot-wifi"></a>熱點 (WiFi)

熱點可以滿足大多數的行動電話的連線需求。 HoloLens 2 WiFi 支援 802.11ac，可提供大多數常見使用案例所需的頻寬和延遲需求。 WiFi 也不含纜線，而且能與數量最多的行動電話裝置相容。

### <a name="connecting-to-a-hotspot"></a>正在連接至熱點

1. 請參閱裝置手冊，瞭解如何啟用其熱點模式。
1. 啟用熱點模式，提供網路名稱和已知密碼。
1. 在 HoloLens 2 網路設定中，找出步驟 2 中所建立的 WiFi 網路並加入。

## <a name="usb-c-tethering"></a>USB-C 繫連

USB-C 繫連可以為需要該功能的進階工作負載提供較低的延遲。 例如，[Azure 遠端轉譯](https://azure.microsoft.com/services/remote-rendering)可受益于繫連功能。 請注意，進行繫連需要在行動電話裝置和 HoloLens 之間使用纜線，且繫連可支援有限裝置數量。

### <a name="usb-c-compatibility"></a>USB-C 相容性

以乙太網路介面卡呈現的裝置可以與 Windows Holographic 版 2004 及更新版本一起使用。

未以乙太網路介面卡呈現的裝置必須支援一般 Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) 驅動程式。 請洽詢您的裝置製造商，以瞭解是否支援一般通用的 Microsoft RNDIS 驅動程式。

不支援與 RNDIS 不相容或需要安裝驅動程式或應用程式的裝置。

雖然 Microsoft 不存留相容裝置的清單，但[這裡](https://aka.ms/HLCommunityCell) 具有針對該主題的社群討論。

### <a name="connecting-to-a-tethered-device"></a>連接到繫連裝置

1. 請參閱裝置手冊，瞭解如何啟用 USB 資料共用。 此設定通常稱為「USB 繫連」、「資料共用」或「USB 數據機」。
1. 啟用 USB 資料共用。
1. 將裝置連接到 HoloLens USB-C 埠。
1. 在 HoloLens 2 網路設定中，裝置會自動顯示為乙太網路連線。
