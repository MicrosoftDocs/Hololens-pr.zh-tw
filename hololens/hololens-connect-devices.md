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
ms.openlocfilehash: d9c8b813ba54edbcfef8d1a32e641dad39a7f193
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428539"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>連線至藍牙和 USB-C 裝置

## <a name="pair-bluetooth-devices"></a>配對藍牙裝置

HoloLens 2 支援下列藍牙裝置類別：

- [HID](/windows-hardware/drivers/hid/)：
    - 滑鼠
    - 鍵盤
- 音訊輸出 (A2DP) 裝置

HoloLens 2 支援下列藍牙 api：
- GATT [伺服器](/windows/uwp/devices-sensors/gatt-server) 和 [用戶端](/windows/uwp/devices-sensors/gatt-client)
- [RFCOMM](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> 您可能必須從 Microsoft Store 安裝對應的附屬應用程式，才能實際使用 HID 和 GATT 裝置。

HoloLens (第1代) 支援下列藍牙裝置類別：

- 滑鼠
- 鍵盤
- [HoloLens (第1代) clicker](hololens1-clicker.md)

> [!NOTE]
> 其他類型的藍牙裝置，例如喇叭、耳機、智慧型手機和遊戲台，可能會在 HoloLens 設定中列為可用。 不過，HoloLens (第一代) 不支援這些裝置。 如需詳細資訊，請參閱[HoloLens 設定列出可用的裝置，但裝置無法運作](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)。

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>配對藍牙鍵盤或滑鼠

1. 開啟鍵盤或滑鼠，並讓它變成可探索。 若要瞭解如何讓裝置可供探索，請尋找裝置 (或其檔) 的相關資訊，或流覽製造商的網站。

1. 使用 bloom 手勢 (HoloLens (第一代) ) 或開始手勢 (HoloLens 2) 移至 [**開始**]，然後選取 [**設定**]。

1. 選取 [**裝置**]，並確定藍牙是 [開啟]。  

1. 當您看到裝置名稱時，請選取 [ **配對**]，然後依照指示進行。

## <a name="disable-bluetooth"></a>停用藍牙

此程式會關閉藍牙無線電的 RF 元件，並停用 Microsoft HoloLens 上的所有藍牙功能。

1. 使用 bloom 手勢 (HoloLens (第一代) ) 或開始手勢 (HoloLens 2) 移至 [**開始**]，然後選取 [**設定**  >  **裝置**]。

1. 將 **藍牙** 的滑杆開關移至 **Off** 位置。

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2：連線 USB-C 裝置

HoloLens 2 支援下列 USB-C 裝置類別：

- 大型儲存裝置 (例如拇指磁片磁碟機) 
- 乙太網路介面卡 (包括乙太網路和充電) 
- USB-C-到 3.5 mm 數位音訊介面卡
- USB-C 數位音訊耳機 (包括耳機卡和充電) 
- USB-C 外部麥克風 ([Windows 全像21H1 版和更新版本的](hololens-release-notes.md#windows-holographic-version-21h1)) 
- 有線滑鼠
- 有線鍵盤
- 結合 PD 中樞 (USB A plus PD 充電) 


> [!NOTE]
> 為了回應客戶的意見反應，我們已啟用對行動電話連接的有限支援行動網卡直接透過 USB-C 進行 HoloLens。 如需詳細資訊，請參閱[行動電話和5G 連線](hololens-cellular.md)。

### <a name="usb-c-external-microphone-support"></a>USB-C 外部麥克風支援

> [!IMPORTANT]
> 插入 **USB mic 並不會自動將它設定為輸入裝置**。 當插入一組 USB-C 耳機時，使用者會發現耳機的音訊會自動重新導向到耳機，但 HoloLens OS 會將內部麥克風陣列的優先順序排列在任何其他輸入裝置上方。 **若要使用 USB 麥克風，請遵循下列步驟。**

> [!NOTE]
> 在 Windows 全像21H1 版和更高[版本之前，](hololens-release-notes.md#windows-holographic-version-21h1)不能在組建中使用外部麥克風。 

使用者可以使用 [ **音效** 設定] 面板來選取 USB-C 連接的外部麥克風。 USB-C 麥克風可以用來呼叫、錄製等等。

開啟 **設定** 應用程式，然後選取 [**系統**  >  **音效**]。

![音效設定。](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> 若要搭配使用外部麥克風與 **遠端協助**，使用者必須按一下 [管理音效裝置] 超連結。
>
> 然後使用下拉式清單將外部麥克風設定為 [ **預設** ] 或 [ **通訊] 預設值。** 選擇 [ **預設值** ] 表示外部麥克風將用於所有位置。
>
> 選擇 [**通訊預設值**] 表示外部麥克風將用於遠端協助和其他通訊應用程式，但 HoloLens mic 陣列仍可用於其他工作。

![管理音效裝置。](images/usbc-mic-2.png)

<br>

![設定麥克風預設值。](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>藍牙麥克風支援呢？

可惜的是，HoloLens 2 上目前仍不支援藍牙的麥克風。

### <a name="usb-c-hubs"></a>USB-C 中樞

有些使用者可能需要一次連接多個裝置。 如果使用者想要使用 [usb 麥克風](#usb-c-external-microphone-support) 以及另一部連線的裝置，則可能符合客戶的需求。 Microsoft 尚未測試這些裝置，也不能建議任何特定品牌。

**USB-C 中樞和連線裝置的需求：**

- 連接的裝置不一定需要安裝驅動程式。
- 所有已連線裝置的耗電量總計必須低於4.5 瓦。

## <a name="connect-to-miracast"></a>連線至 Miracast

若要使用 Miracast，請遵循下列步驟：

1. 執行下列其中一個動作：  

   - 開啟 [ **開始** ] 功能表，然後選取 [ **顯示** ] 圖示。
   - 當您注視 [開始] 功能表時，請說 **「連線」** 。  

1. 在出現的裝置清單中，選取可用的裝置。

1. 完成配對以開始投射。
