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
# 連線至藍牙與 USB-C 裝置

## 配對 [藍牙] 裝置

HoloLens 2 支援下列 [藍牙] 裝置類型：

- 滑鼠
- 鍵盤
- [藍牙] 音訊輸出（A2DP）裝置

HoloLens （第 1 代）支援下列 [藍牙] 裝置類型：

- 滑鼠
- 鍵盤
- HoloLens (第 1 代) 簡報導覽裝置

> [!NOTE]
> 其他類型的 [藍牙] 裝置，例如 喇叭、耳機、智慧型手機和遊戲台，可能會在 HoloLens 設定中列為可用裝置。 不過，HoloLens （第1代）並不支援這些裝置。 如需詳細資訊，可參照 [HoloLens 設定中列為可用裝置，但此裝置無法使用](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)。

### 配對 [藍牙] 鍵盤或滑鼠

1. 開啟您的鍵盤或滑鼠，並將它設為可搜尋的。 若要瞭解如何讓裝置設為可搜尋的，請在裝置（或其文件）中尋找相關資訊，或造訪製造商的網站。

1. 使用綻開手勢（HoloLens (第 1 代)）或開始手勢（HoloLens 2）移至 **開始**，然後選取 **設定**。
1. 選取 **裝置**，並確定藍牙已開啟。  
1. 當您看到裝置名稱時，請選取 **配對**，然後按照指示操作。

### HoloLens（第 1 代）：配對簡報導覽裝置

1. 使用綻開手勢並移至 **開始**，然後選取 **設定**。

1. 選取 **裝置**，並確定藍牙已開啟。

1. 使用筆尖壓住 [簡報導覽裝置] 的配對按鈕並按住不放，直到 [簡報導覽裝置] 狀態燈號呈白色閃爍。 請務必按住按鈕直到燈號出現閃爍為止。  

   [配對] 按鈕位於 [簡報導覽裝置] 的下方、手指環旁邊。
   
   ![配對按鈕位於手指環的旁邊](images/use-hololens-clicker-1.png)
   
1. 在配對的畫面上，選取 **簡報導覽裝置** > **配對**。

## HoloLens 2：連接 USB-C 裝置

HoloLens 2 支援下列 USB-C 裝置類型：

- 大量儲存裝置（例如隨身碟）
- 乙太網路介面卡（包括乙太網路和充電）
- USB-C-3.5 毫米數位音訊介面卡
- USB-C 數位音訊耳機（包括耳機轉接器加上充電）
- 有線滑鼠
- 有線鍵盤
- 組合 PD 集線器（USB A 加 PD 充電）

> [!NOTE]
> 部份具有 USB-C 連線的行動裝置，本身就會以乙太網配接器的形式顯示在 HoloLens 上，因此可在 [網際網路共用] 設定中使用，以 Windows 全像攝影版（版本 2004）開始。 不支援需要單獨驅動程式的 USB LTE 數據機，和/或設定用的已安裝應用程式

## 連線到 Miracast

若要使用 Miracast，請按照下列步驟操作：

1. 執行下列其中一項：  

   - 開啟 **開始** 功能表，並選取顯示器圖示。
   - 在您注視 **開始** 功能表時說出「連線」。  

1. 在出現的裝置清單中，選取可用的裝置。
1. 完成配對並開始投影。

## 停用 [藍牙] 

此程式會關閉 [藍牙] 無線電裝置的 RF 元件，並停用 Microsoft HoloLens 中的所有藍牙功能。

1. 使用綻開手勢（HoloLens (第 1 代)）或開始手勢（HoloLens 2）並移至 **開始**，然後選取 **設定** > **裝置**。
1. 將 **藍牙** 的滑杆開關移至 **[關閉]** 位置。
