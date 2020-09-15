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
ms.openlocfilehash: 0db64ffb4113ff948651c708c28b91da535cb09b
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009521"
---
# 將 HoloLens 連線到網路

若要在 HoloLens 上執行大部分作業，您必須連線到網路。 本指南將協助您：

- 使用 Wi-Fi 或 (僅限 HoloLens 2) 透過 USB-C 的乙太網路連線至網路
- 停用和重新啟用 Wi-Fi

閱讀更多關於[離線使用 HoloLens](hololens-offline.md) 的資訊。

## 首次連線

第一次使用 HoloLens 時，系統會引導您連線至 Wi-Fi 網路。 如果您在安裝期間無法連線到 Wi-Fi，請確認您的網路是已開啟且有密碼保護的網路，還是網頁驗證入口網路。 確定網路不會要求您使用憑證來連線。 安裝之後，您可以連線至其他類型的 Wi-Fi 網路。

在 HoloLens 2 裝置上，使用者也可能[使用 USB-C 轉乙太網路卡](hololens-connect-devices.md#hololens-2-connect-usb-c-devices)直接連線至 Wi-Fi，以協助您設定裝置。 當裝置設定完成後，使用者可以繼續使用介面卡，或可以在設定後將裝置與介面卡斷開，並[連線到 Wi-Fii](hololens-network.md#connecting-to-wi-fi-after-setup)。 

## 在安裝後連線到 Wi-Fi

1. 執行 [啟動手勢]**** 然後選取 [設定]****。 [設定] 應用程式會自動放置在您面前。
1. 選取 **[網路和網際網路]** > **[Wi-Fi]**。 確定已開啟 Wi-Fi。 如果沒有看到您的網路，請向下捲動清單。
1. 選取網路，然後選取 **[連線]**。
1. 如果系統提示您輸入網路密碼，請輸入密碼，然後選取 **[下一步]**。

HoloLens 包含 802.11ac 功能，2x2 Wi-Fi 無線電。 將 HoloLens 連線到 Wi-Fi 網路與將 Windows 10 Desktop 或行動裝置連線到 Wi-Fi 網路很類似。

![HoloLens Wi-Fi 設定](./images/wifi-hololens-600px.jpg)

您也可以在 [開始]**** 功能表中檢查 Wi-Fi 狀態，確認您已連線到 Wi-Fi 網路：

1. 開啟 [開始]**** 功能表。
1. 查看 [開始]**** 功能表左上角的 Wi-Fi 狀態。 會顯示 Wi-Fi 的狀態和已連線網路的 SSID。

## 疑難排解您與 Wi-Fi 的連線

如果您遇到連線到 Wi-Fi 的問題，請參閱[我無法連線至 Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi)。

當您登入該裝置上的企業或組織帳戶時，可能也會套用「行動裝置管理 (MDM)」原則 (如果該原則是由您的 IT 系統管理員設定)。

## VPN
VPN 連線可協助提供更安全的連線，並能存取公司的網路和網際網路。 HoloLens 2 支援內建的 VPN 用戶端和通用 Windows 平台 (UWP) VPN 外掛程式。 

支援的內建 VPN 通訊協定：
- IKEv2
- L2TP
- PPTP

如果使用憑證來驗證內建 VPN 用戶端，則需要將所需的用戶端憑證新增至 [使用者憑證存放區]。 若要找出第三方 VPN 外掛程式是否支援 HoloLens 2，請移至 Microsoft Store 尋找 VPN 應用程式，並查看是否已將 HoloLens 列為支援的裝置，以及在 [系統需求] 頁面中，應用程式支援 ARM 或 ARM64 架構。 HoloLens 僅支援適用於第三方 VPN 的通用 Windows 平台應用程式。

VPN 預設不會啟用，但是您可以開啟 [設定]**** 應用程式，並瀏覽至 [網路與網際網路] -> [VPN]****，以手動啟用。 您可以透過 MDM 的 [設定/允許 VPN][](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 來管理 VPN，並透過 [Vpnv2-csp 原則][](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp) 來設定 VPN。
深入了解如何使用[這些指南](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)[設定 VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn)。  

## 在 HoloLens (第 1 代) 上停用 Wi-Fi

### 在 HoloLens 上使用 [設定] 應用程式

1. 開啟 [開始]**** 功能表。
1. 從 [開始]**** 或從 [開始]**** 功能表右側的 [所有應用程式]**** 清單中，選取 [設定]**** 應用程式。 [設定]**** 應用程式會自動放置在您面前。
1. 選取 [網路和網際網路]****。
1. 選取 Wi-Fi 滑桿開關，將它移到 [關閉]**** 位置。 這會關閉 Wi-Fi 無線電的 RF 元件，並在 HoloLens 上停用所有 Wi-Fi 功能。

    > [!WARNING]
    > 當 Wi-Fi 無線電停用時，HoloLens 將無法自動載入您的[空間](hololens-spaces.md)。

1. 將滑桿開關移至 [開啟]**** 位置，以開啟 Wi-Fi 無線電並還原 Microsoft HoloLens 的 Wi-Fi 功能。 選取的 Wi-Fi 無線電狀態 ([開啟]**** 或 [關閉]****) 在重新開機後會保留。

## 在 Wi-Fi 網路上識別 HoloLens 的 IP 位址

### 使用 [設定] 應用程式

1. 開啟 [開始]**** 功能表。
1. 從 [開始]**** 或從 [開始]**** 功能表右側的 [所有應用程式]**** 清單中，選取 [設定]**** 應用程式。 [設定]**** 應用程式會自動放置在您面前。
1. 選取 [網路和網際網路]****。
1. 向下捲動至可用 Wi-Fi 網路清單下方，然後選取 [硬體內容]****。

    ![Wi-Fi 設定中的硬體內容](./images/wifi-hololens-hwdetails.jpg)

   IP 位址會顯示在 [IPv4 位址]**** 的旁邊。

### 使用語音命令

視您的裝置組建而定，您可以使用內建的語音命令或 Cortana 來顯示您的 IP 位址。 在 [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 之後的組建中，說出「我的 IP 位址是什麼？」 位址隨即顯示。 針對較舊的組建或 HoloLens (第 1 代)，請說出「嗨 Cortana，我的 IP 位址是什麼？」 Cortana 就會顯示並讀出您的 IP 位址。

### 使用 Windows 裝置入口網站

1. 在電腦的網頁瀏覽器中，開啟[裝置入口網站](/windows/mixed-reality/using-the-windows-device-portal.md#networking)。
1. 瀏覽至 [網路]**** 區段。  
   此區段會顯示您的 IP 位址及其他網路資訊。 使用這個方法，您可以複製並貼上開發電腦上的 IP 位址。
