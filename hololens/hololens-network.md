---
title: 將 HoloLens 連線到網路
description: 有關如何使用 HoloLens 連線至網際網路，以及如何識別裝置 IP 位址的指示。
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, wifi, 無線, 網際網路, ip, ip 位址
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 734176dcf8a789f130aa8b010f5f3c9ec1d22c72
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857791"
---
# 將 HoloLens 連線到網路

若要在 HoloLens 上執行大部分作業，您必須連線到網路。 本指南將協助您：

- 使用 Wi-Fi 或 (僅限 HoloLens 2) 透過 USB-C 的乙太網路連線至網路
- 停用和重新啟用 Wi-Fi

閱讀更多關於[離線使用 HoloLens](hololens-offline.md) 的資訊。

## 首次連線

第一次使用 HoloLens 時，系統會引導您連線至 Wi-Fi 網路。 如果您在安裝期間無法連線到 Wi-Fi，請確認您的網路是已開啟且有密碼保護的網路，還是網頁驗證入口網路。 確定網路不會要求您使用憑證來連線。 安裝之後，您可以連線至其他類型的 Wi-Fi 網路。

## 在安裝後連線到 Wi-Fi

1. 選取 **[開始]** > **[設定]**。
   - *僅限 HoloLens (第 1 代)*：使用注視來調整 [設定] 應用程式的位置，然後空中點選來放置它，或說「放置」。
1. 選取 **[網路和網際網路]** > **[Wi-Fi]**。 如果沒有看到您的網路，請向下捲動清單。
1. 選取網路，然後選取 **[連線]**。
1. 如果系統提示您輸入網路密碼，請輸入密碼，然後選取 **[下一步]**。

## 在 HoloLens (第 1 代) 上連線至 Wi-Fi

HoloLens 包含 802.11ac 功能，2x2 Wi-Fi 無線電。 將 HoloLens 連線到 Wi-Fi 網路與將 Windows 10 Desktop 或行動裝置連線到 Wi-Fi 網路很類似。

![HoloLens Wi-Fi 設定](./images/wifi-hololens-600px.jpg)

1. 開啟 **[開始]** 功能表。
1. 從 [開始]**** 或從 [開始]**** 功能表右側的 [所有應用程式]**** 清單中，選取 [設定] 應用程式。 [設定] 應用程式會自動放置在您面前。
1. 選取 [網路和網際網路]****。
1. 確定已開啟 Wi-Fi。
1. 從清單中選取 Wi-Fi 網路。
1. 如有需要，請輸入 Wi-Fi 網路密碼。

您也可以在 [開始]**** 功能表中檢查 Wi-Fi 狀態，確認您已連線到 Wi-Fi 網路：

1. 開啟 **[開始]** 功能表。
1. 查看 [開始]**** 功能表左上角的 Wi-Fi 狀態。 會顯示 Wi-Fi 的狀態和已連線網路的 SSID。

## 疑難排解您與 Wi-Fi 的連線

如果您遇到連線到 Wi-Fi 的問題，請參閱[我無法連線至 Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi)。

當您登入該裝置上的企業或組織帳戶時，可能也會套用「行動裝置管理 (MDM)」原則 (如果該原則是由您的 IT 系統管理員設定)。

## 在 HoloLens (第 1 代) 上停用 Wi-Fi

### 在 HoloLens 上使用 [設定] 應用程式

1. 開啟 **[開始]** 功能表。
1. 從 [開始]**** 或從 [開始]**** 功能表右側的 [所有應用程式]**** 清單中，選取 [設定]**** 應用程式。 [設定]**** 應用程式會自動放置在您面前。
1. 選取 [網路和網際網路]****。
1. 選取 Wi-Fi 滑桿開關，將它移到 [關閉]**** 位置。 這會關閉 Wi-Fi 無線電的 RF 元件，並在 HoloLens 上停用所有 Wi-Fi 功能。

    > [!WARNING]
    > 當 Wi-Fi 無線電停用時，HoloLens 將無法自動載入您的[空間](hololens-spaces.md)。

1. 將滑桿開關移至 [開啟]**** 位置，以開啟 Wi-Fi 無線電並還原 Microsoft HoloLens 的 Wi-Fi 功能。 選取的 Wi-Fi 無線電狀態 ([開啟]**** 或 [關閉]****) 在重新開機後會保留。

## 在 Wi-Fi 網路上識別 HoloLens 的 IP 位址

### 使用 [設定] 應用程式

1. 開啟 **[開始]** 功能表。
1. 從 [開始]**** 或從 [開始]**** 功能表右側的 [所有應用程式]**** 清單中，選取 [設定]**** 應用程式。 [設定]**** 應用程式會自動放置在您面前。
1. 選取 [網路和網際網路]****。
1. 向下捲動至可用 Wi-Fi 網路清單下方，然後選取 [硬體內容]****。

    ![Wi-Fi 設定中的硬體內容](./images/wifi-hololens-hwdetails.jpg)

   IP 位址會顯示在 [IPv4 位址]**** 的旁邊。

### 使用 Cortana

說「嗨 Cortana，我的 IP 位址是什麼？」 Cortana 就會顯示並讀出您的 IP 位址。

### 使用 Windows 裝置入口網站

1. 在電腦的網頁瀏覽器中，開啟[裝置入口網站](/windows/mixed-reality/using-the-windows-device-portal.md#networking)。
1. 瀏覽至 [網路]**** 區段。  
   此區段會顯示您的 IP 位址及其他網路資訊。 使用這個方法，您可以複製並貼上開發電腦上的 IP 位址。
