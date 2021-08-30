---
title: Enterprise以 MAC 位址限制的 HoloLens 裝置註冊 Wi-Fi 環境
description: HoloLens 2 裝置上網路的 MAC 位址
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
ms.openlocfilehash: d21a63aae94f5ea5269f61fe319a9036626de1b4
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189523"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>Enterprise以 MAC 位址限制的 HoloLens 裝置註冊 Wi-Fi 環境

本檔將說明我們在客戶環境中識別的常見案例，其中 Wi-Fi 受 MAC 位址限制，或必須有憑證才能加入無線網路。

## <a name="example-scenario"></a>範例案例

在安全的環境中，許多客戶對於其無線或有線網路有限制，因此只允許以 MAC 位址為基礎的核准裝置 (，) 成功連接。 這可以透過無線存取點上的 MAC 位址篩選，或透過 DHCP 伺服器來強制執行。 此外，某些無線網路可以使用 PEAP 保護，這會要求在無線網路上進行驗證之前，先將憑證套用至裝置。

在此案例中，兩個主要需求可能會導致延遲，或將 HoloLens 裝置加入網路時需要手動介入：

- 在裝置成功加入無線網路之前，必須先將無線 PEAP 憑證套用至裝置。
- 必須註冊 HoloLens Wi-Fi 配接器的 MAC 位址。

上述需求的核心挑戰如下：

1. 目前只能從裝置上的設定應用程式，或在成功註冊之後從 Intune 識別 MAC 位址。

2. 如果沒有 MAC 位址，裝置就無法加入 Wi-Fi 網路以開始註冊。

3. 這些挑戰的手動因應措施需要技術人員與裝置互動。

## <a name="solutions"></a>方案

有許多方法可以改善這種情況，視環境內的可用基礎結構而定。

| 解決方案 | 優點 | 規格需求 |
| --- | --- | --- |
| 使用乙太網路介面卡布建套件 | 改善 OOBE 體驗，並讓技術人員體驗更快。 | HoloLens 相容的 USB-C 中樞 + 乙太網路介面卡，且技術人員仍需要與裝置互動，以進行 MAC 捕獲和 OOBE 最終處理 |
| 透過乙太網路進行 Intune 註冊的 Autopilot | 這是對客戶環境進行的單一步驟連接和註冊裝置。 MAC capture 可以完成，而不需要與裝置互動 | 已針對客戶 AAD 租使用者啟用 Intune，並 HoloLens 相容的 USB-C 乙太網路介面卡 |
| 自動報告 MAC 位址 | 當裝置向 Intune 租使用者註冊時，腳本可以向技術人員報告 MAC 位址。 | Intune PowerShell Cmdlet |

## <a name="provisioning-package-with-ethernet-adaptor"></a>使用乙太網路介面卡布建套件

> [!NOTE] 
> 如果有線網路也受到 MAC 限制，則也需要預先核准 USB Hub + 乙太網路介面卡的 MAC 位址。 請小心使用此介面卡，因為它可讓您從其他裝置存取網路。

### <a name="requirements"></a>規格需求

- 具有客戶網路存取權的有線網路埠
- HoloLens相容的 USB-C 中樞與乙太網路介面卡—任何不需要任何額外驅動程式或應用程式安裝的介面卡都應該適用。
- 布建套件包含：
  - 包含無線網路資訊和憑證
  - 選擇性地包含組織 Azure AD 的註冊資訊
  - 包含任何其他必要的布建設定

### <a name="process"></a>處理序

此程式可能會根據裝置的軟體層級而有所不同。 如果裝置的 [2004 更新](hololens-release-notes.md#windows-holographic-version-2004)，請遵循下列步驟。

1. 將布建套件置於 USB 駕駛的根目錄，然後插入中樞。
2. 連線將乙太網路纜線連接至中樞 + 乙太網路介面卡。
3. 連線USB-C 中樞至 HoloLens 裝置。
4. 開啟 HoloLens 並放在裝置上。
5. 按 [ **音量降低] 和 [電源] 按鈕** 以套用布建套件。
6. 技術人員現在可以遵循 OOBE，完成時，請開啟設定應用程式，以取得裝置的 MAC 位址。

如果裝置在 [2004 更新](hololens-release-notes.md#windows-holographic-version-2004)之前有 OS 組建，請遵循下列步驟。

1. 開啟 HoloLens，並將裝置插入電腦。
2. 裝置應該會在電腦上顯示為檔案儲存裝置。
3. 將布建套件複製到裝置
4. 連線將乙太網路纜線連接到中樞。
5. 連線USB-C 中樞至 HoloLens 裝置。
6. 放在 HoloLens
7. 按 [ **音量降低] 和 [電源** ] 按鈕以套用布建套件。
8. 技術人員現在可以遵循 OOBE，完成時，請開啟設定應用程式，以取得裝置的 MAC 位址。

### <a name="benefits"></a>優點

這會允許裝置的「單一觸控」，以套用正確的布建套件，並收集裝置的 MAC 位址。 [您可以遵循此處的指引來建立布建套件。](hololens-provisioning.md)

## <a name="autopilot-with-intune-enrollment"></a>使用 Intune 註冊的 Autopilot

### <a name="requirements"></a>規格需求

- 具有客戶網路存取權的有線網路埠
- HoloLens Windows 全像2004的裝置
- HoloLens相容的 USB-C 乙太網路介面卡
- 為客戶租使用者設定和啟用 Intune
- 註冊 Autopilot 並匯入至客戶租使用者的裝置
- 針對裝置定義的 Intune 原則：
   - 包含無線網路資訊和憑證
   - 包含任何其他必要的布建設定

這可讓具有 advanced 網路需求的客戶以實際操作、可擴充的方式註冊裝置

需要額外的先決條件，如下所示：
1. [啟用 Autopilot 預覽的租](hololens2-autopilot.md)使用者。
1. 建立 HoloLens 原則來取代 Intune 內的布建套件。
1. 建立 HoloLens Intune 原則。
1. 將裝置指派給正確的群組。

### <a name="process"></a>處理序

1. 連線乙太網路纜線連接至介面卡，並將介面卡插入 HoloLens 2 裝置上的 USB 埠。

2. 開啟 HoloLens。

3. 裝置應該會在 OOBE 期間透過乙太網路介面卡自動連接到網際網路。 它應該會偵測到 Autopilot 設定，並自動向 Azure AD 和 Intune 註冊。

4. 裝置會視需要將必要的 Wi-Fi 憑證和其他設定套用至 Intune。

5. 完成時，技術人員可以將 Intune (端點管理員) 入口網站，並在 **Home-> 裝置（> DeviceName-> 硬體）** 中深入探索裝置內容頁面。

6. 在 Intune 入口網站中會顯示 Wi-Fi MAC 位址。

   ![透過 Intune 的 MAC 位址。](images/mac-address-intune.jpg)

7. 技術人員會將此 MAC 位址新增為允許的裝置。

### <a name="benefits"></a>優點

這可為技術人員提供「頭部關閉」部署體驗，讓裝置能夠從 Azure AD 和 Intune 中註冊的方塊進入，而不需要技術人員讓裝置磨損或手動與 HoloLens 環境互動。

## <a name="reporting-of-mac-addresses-to-the-technician"></a>將 MAC 位址報告給技術人員

### <a name="requirements"></a>規格需求

- 對客戶租使用者的「Intune Graph PowerShell」授權
- 將 Intune Graph PowerShell 安裝在技術人員電腦上。
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Intune 的「受管理裝置」元素的讀取權限。  (服務台操作員或更高版本，或自訂角色) 

目前，沒有「簡單」的方式可根據 Intune 內的新裝置註冊來觸發自動化命令。 因此，此命令可讓技術人員在不需要登入入口網站的情況下，輕鬆地取出 MAC 位址，並以手動方式取得。

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

這會傳回在過去30天內註冊之任何 HoloLens 裝置的名稱和 MAC 位址。

![經由 PowerShell 的 MAC 位址。](images/mac-address-powershell.jpg)

### <a name="process"></a>處理序

完成 Intune 註冊之後，技術人員會執行上述腳本來取得 MAC 位址。
