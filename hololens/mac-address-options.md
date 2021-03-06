---
title: 在 MAC 位址受限 Wi-Fi 環境中的 HoloLens 裝置企業注冊
description: 如何在 HoloLens 2 裝置上實現網絡 MAC 地址
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: fe365248332f8e78b15ab362f169b84e48dfe594
ms.sourcegitcommit: 07ffe1bf2f45dcb2ba9d7fbe54b4773a0fb9d525
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393837"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>在 MAC 位址受限 Wi-Fi 環境中的 HoloLens 裝置企業注冊

本文件將描述我們在客戶環境中發現的常見案例，其中 Wi-Fi 受MAC 位址限制，或者需要證書才能加入無線網路。

## <a name="example-scenario"></a>示範案例

許多在安全環境中的客戶對無線或有線網路有限制，僅允許核准的裝置 (基於 MAC 位址) 成功連接。 這項功能可能會透過無線存取點上的 MAC 位址篩選，或透過 DHCP 伺服器強制執行。 此外，某些無線網路可以受到 PEAP 保護，這需要在驗證無線網路之前，先將憑證應用至裝置。

在此情境中，將 HoloLens 裝置加入至網路時，有兩項關鍵需求可能會導致延遲或需要手動介入：

- 在裝置成功加入無線網路之前，必須將無線 PEAP 憑證套用至裝置。
- 必須註冊 HoloLens Wi-Fi 配接器的 MAC 位址。

上述需求的核心挑戰為：

1. MAC 位址目前只能從裝置上的 [設定] 應用程式或在成功註冊的 Intune 上識別。
2. 沒有 MAC 位址，裝置就無法加入 Wi-Fi 網路來開始註冊。
3. 針對這些問題的手動解決方法需要技術人員與裝置互動。

## <a name="solutions"></a>解決方案

根據環境中可用的基礎結構，有許多方法可以改善這種情況。

| 解決方案 | 優點 | 需求 |
| --- | --- | --- |
| 具有乙太網路配接器的佈建套件 | 改善 OOBE 體驗，並允許更快的技術人員體驗。 | 與 HoloLens 相容的 USB-C Hub + 乙太網路配接器，而技術人員仍然需與裝置進行互動，以便進行 MAC 擷取和 OOBE 最終處理 |
| 乙太網路上具有 Intune 注册的 Autopilot  | 這是裝置與客戶環境的單一步驟連接和註冊。 MAC 擷取可以在不需與裝置互動的情況下完成 | 為客戶 AAD 租用戶和與 HoloLens 相容的 USB-C 乙太網路配接器啟用 Intune |
| 自動報告 MAC 位址 | 當裝置使用 Intune 租用戶註冊時，腳本可以向技術人員報告 MAC 位址。 | Intune Powershell Commandlets |

## <a name="provisioning-package-with-ethernet-adaptor"></a>具有乙太網路配接器的佈建套件

> [!NOTE] 
> 如果有線網路也受到 MAC 限制，則 USB-C Hub + 乙太網路配接器的 MAC 位址也需要預先核准。 請小心使用這個介面卡，因為它會允許從其他裝置存取網路。

### <a name="requirements"></a>需求

- 可存取客戶網路的有線網路連接埠
- 與 HoloLens 相容的 USB-C 集線器與乙太網路配接器 – 任何不需要額外驅動程式或應用程式安裝的配接器都應適用。
- 佈建套件包含：
  - 包含無線網路資訊和憑證
  - 可選地包含組織和 Azure AD 的注册資訊
  - 包含任何其他必要的預配設定

### <a name="process"></a>Process

該過程可能因裝置的軟體等級而异。 如果裝置有 [2004 年 5 月更新](hololens-release-notes.md#windows-holographic-version-2004)，請執行以下步驟。

1. 將佈建套件放在 USB 的根部，然後插入集線器。
2. 將乙太網路纜線連接到 Hub + 乙太網路介面卡。
3. 將 USB-C Hub 連接到 HoloLens 裝置。
4. 開啟 HoloLens 並將裝置戴上。
5. 按下 **[降低音量] 和 [電源] 按鈕** 以套用佈建套件。
6. 技術人員現在可以遵循 OOBE，完成後，請開啟 [設定] 應用程式以抓取裝置的 MAC 位址。

如果裝置具有 [2004 年 5 月更新](hololens-release-notes.md#windows-holographic-version-2004)之前的作業系統組建，請執行以下步驟。

1. 開啟 HoloLens，將裝置插入電腦。
2. 裝置應在電腦上顯示為檔案存放裝置。
3. 將佈建套件複製到裝置
4. 將乙太網纜線連線至集線器。
5. 將 USB-C Hub 連接到 HoloLens 裝置。
6. 戴上 HoloLens
7. 按下 **[降低音量] 和 [電源] 按鈕** 以套用佈建套件。
8. 技術人員現在可以遵循 OOBE，完成後，請開啟 [設定] 應用程式以抓取裝置的 MAC 位址。

### <a name="benefits"></a>優點

這允許裝置的&quot;單次觸控&quot;，以套用正確的佈建套件並收集裝置的 MAC 位址。 [您可以依照這裡的指導方針建立佈建套件。](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a>具有 Intune 注冊的 Autopilot

### <a name="requirements"></a>需求

- 可存取客戶網路的有線網路連接埠
- 執行 Windows 全息攝像版 2004 的 HoloLens 裝置
- 與 HoloLens 相容的 USB-C 乙太網路配接器
- 為客戶租用戶設定並啟用 Intune
- 已註冊 Autopilot 並匯入客戶租用戶的裝置
- 為裝置定義的 Intune 原則：
   - 包含無線網路資訊和憑證
   - 包含任何其他必要的預配設定

這將允許具有高級網路需求的客戶以無需干預、可調整的方式注册裝置

其他先決條件如下：
1. [為 Autopilot 預覽啟用租用戶](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. 建立 HoloLens 原則以取代 Intune 內的佈建套件。
1. 建立 HoloLens Intune 原則。
1. 將裝置指派給正確的群組。

### <a name="process"></a>處理程序

1. 將乙太網路纜線連接到配接器，將配接器插入 HoloLens 2 裝置上的 USB-C 埠。
2. 開啟 HoloLens。
3. 裝置應該會在 OOBE 期間透過乙太網路配接器自動連接至網際網路。 它應該會偵測 Autopilot 設定，並自動使用 Azure AD 和 Intune 註冊
4. 裝置會視需要透過 Intune 套用所需的 Wi-Fi 憑證和其他設定
5. 完成後，技術人員可以載入 Intune (端點管理員) 入口網站，並深入到 **首頁 -> 裝置 -> 裝置名稱 -> 硬體**的裝置內容頁面
6. Wifi MAC 位址將在 Intune 入口網站中可見

![透過 Intune 的 MAC 位址](images/mac-address-intune.jpg)

7. 技術人員會將新增此 MAC 位址作爲允許使用的裝置。

### <a name="benefits"></a>優點

這將為技術人員提供&quot;無障礙&quot;的部署體驗，裝置能够從方塊進入 Azure AD 和 Intune 注冊，而無需技術人員佩戴裝置或手動與 HoloLens 環境互動。

## <a name="reporting-of-mac-addresses-to-the-technician"></a>向技術人員報告 MAC 位址

### <a name="requirements"></a>需求

- 針對客戶租用戶授權 &quot;Intune Graph PowerShell&quot;
- 在技術人員機器上安裝 Intune Graph PowerShell。
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- 對 Intune 的&quot;受托管裝置&quot;元素的讀取存取權。 （協助技術支援人員或更高階層人員，或自訂角色）

目前沒有一種&quot;簡單&quot;的方法可以根據 Intune 中新裝置的注册來觸發自動化命令。 因此，此命令將為技術人員提供一種簡單的方法來取得 MAC 位址，而無需登入到入口網站並手動取得它。

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

這會傳回最近 30 天內註冊的任何 HoloLens 裝置名稱和 MAC 位址。

![透過 Powershell 的 MAC 位址](images/mac-address-powershell.jpg)

### <a name="process"></a>Process

Intune 注冊完成後，技術人員會執行上述腳本來取得 MAC 位址。
