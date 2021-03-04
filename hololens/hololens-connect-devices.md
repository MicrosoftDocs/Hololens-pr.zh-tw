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
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>連線至藍牙與 USB-C 裝置

> [!NOTE]
> 無法使用外部麥克風。 HoloLens 2 使用其內建[麥克風陣列](hololens2-hardware.md#audio-and-speech)。

## <a name="pair-bluetooth-devices"></a>配對 [藍牙] 裝置

HoloLens 2 支援下列 [藍牙] 裝置類型：

- 滑鼠
- 鍵盤
- [藍牙] 音訊輸出（A2DP）裝置

HoloLens （第 1 代）支援下列 [藍牙] 裝置類型：

- 滑鼠
- 鍵盤
- [HoloLens (第 1 代) 簡報導覽裝置](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> 其他類型的 [藍牙] 裝置，例如 喇叭、耳機、智慧型手機和遊戲台，可能會在 HoloLens 設定中列為可用裝置。 不過，HoloLens （第1代）並不支援這些裝置。 如需詳細資訊，可參照 [HoloLens 設定中列為可用裝置，但此裝置無法使用](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)。

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>配對 [藍牙] 鍵盤或滑鼠

1. 開啟您的鍵盤或滑鼠，並將它設為可搜尋的。 若要瞭解如何讓裝置設為可搜尋的，請在裝置（或其文件）中尋找相關資訊，或造訪製造商的網站。

1. 使用綻開手勢（HoloLens (第 1 代)）或開始手勢（HoloLens 2）移至 **開始**，然後選取 **設定**。

1. 選取 **裝置**，並確定藍牙已開啟。  

1. 當您看到裝置名稱時，請選取 **配對**，然後按照指示操作。

## <a name="disable-bluetooth"></a>停用 [藍牙] 

此程式會關閉 [藍牙] 無線電裝置的 RF 元件，並停用 Microsoft HoloLens 中的所有藍牙功能。

1. 使用綻開手勢（HoloLens (第 1 代)）或開始手勢（HoloLens 2）並移至 **開始**，然後選取 **設定** > **裝置**。

1. 將 **藍牙** 的滑杆開關移至 **[關閉]** 位置。

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2：連接 USB-C 裝置

HoloLens 2 支援下列 USB-C 裝置類型：

- 大量儲存裝置（例如隨身碟）
- 乙太網路介面卡（包括乙太網路和充電）
- USB-C-3.5 毫米數位音訊介面卡
- USB-C 數位音訊耳機（包括耳機轉接器加上充電）
- 有線滑鼠
- 有線鍵盤
- 組合 PD 集線器 (USB A 加 PD 充電)

> [!NOTE]
> 針對客戶意見反應，我們已為 [行動數據連線能力] 啟用部分支援，並透過 USB-C 直接連結到 HoloLens。 請參閱 [連接至行動電話和 5G](hololens-cellular.md) 以瞭解更多資訊。

### <a name="usb-c-hubs"></a>USB-C 集線器

有些使用者可能需要一次連線多個裝置。 對於希望預覽測試人員功能並[將 USB-C 麥克風](hololens-insider.md#usb-c-external-microphone-support)與其他連線裝置一起使用的使用者，USB-C 集線器可能適合客戶的需求。 Microsoft 尚未測試這些裝置，我們也無法建議任何特定品牌。

**USB-C 集線器與已連線裝置的需求：**

- 已連線裝置必須不需要安裝驅動程式。
- 所有連線裝置的總功耗必須低於 4.5 瓦特。

## <a name="connect-to-miracast"></a>連線到 Miracast

若要使用 Miracast，請按照下列步驟操作：

1. 執行下列其中一項：  

   - 開啟 **開始** 功能表，並選取顯示器圖示。
   - 在您注視 **開始** 功能表時說出「連線」。  

1. 在出現的裝置清單中，選取可用的裝置。

1. 完成配對並開始投影。
