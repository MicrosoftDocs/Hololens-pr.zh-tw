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
ms.openlocfilehash: 3e06540dd7dca8892cd69abaf9a318d46ca0f3f2
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253140"
---
# 在 MAC 位址受限 Wi-Fi 環境中的 HoloLens 裝置企業注冊

本文件將描述我們在客戶環境中發現的常見案例，其中 Wi-Fi 受MAC 位址限制，或者需要證書才能加入無線網路。

## 示範案例

安全環境中的許多客戶對其無線或有線網路有限制，僅允許經核准的裝置 (基於 MAC 位址) 成功連線 (在無綫存取點或 DHCP 伺服器上使用 MAC 位址篩選)。 另外，一些無線網路可由 PEAP 保護，這要求在能够成功地驗證無線網路之前，向裝置套用憑證。

HoloLens 裝置可能會出現兩個關鍵問題，這會導致將 HoloLens 裝置加入到網路時出現延遲和手動執行。

- 在裝置成功加入無線網路之前，必須將無線 PEAP 憑證套用至裝置。
- 必須註冊 HoloLens Wi-Fi 配接器的 MAC 位址。

這方面的主要挑戰如下：

1. 目前只能從裝置上的 [設定] 應用程式或 Intune 注册成功後從 Intune 識別 MAC 位址。
2. 沒有 MAC 位址，裝置就無法加入 Wi-Fi 網路來開始註冊。
3. 手動解决這些難題需要技術人員參與裝置。

## 解決方案

根據環境中可用的基礎結構，有許多方法可以改善這種情況。

| 解決方案 | 優點 | 需求 |
| --- | --- | --- |
| 具有乙太網路配接器的佈建套件 | 改善 OOBE 體驗，並允許更快的技術人員體驗。 | 與 HoloLens 相容的 USB C HubTechnician 仍需要與裝置進行互動，以便進行 MAC 擷取和 OOBE 完成 |
| 乙太網路上具有 Intune 注册的 Autopilot  | 裝置到客戶環境的單步連線和注册可以在不與裝置互動的情况下完成 MAC 擷取 | 為客戶 Azure AD TenantHoloLens 相容 USB-C 網路介面卡啟用 Intune |
| 自動報告 MAC 位址 | 在 Intune 租用戶中注册裝置後，請將 MAC 位址報告腳本給技術人員。 | Intune PowerShell Commandlets |

## 具有乙太網路配接器的佈建套件

> [!NOTE] 
> 如果有線網路也受到 MAC 限制，那麼需要預先核准 USB-C 乙太網路配接器/集線器的 MAC 位址。 請小心使用此集線器，因為這將允許從其他裝置存取網路。

### 需求

- 可存取客戶網路的有線網路連接埠
- HoloLens 相容的 USB-C 集線器包含乙太網路配接器 - 任何不需要任何額外驅動程式或應用程式安裝的集線器都應該適用。
- 佈建套件包含：
  - 包含無線網路資訊和憑證
  - 可選地包含組織和 Azure AD 的注册資訊
  - 包含任何其他必要的預配設定

### Process

該過程可能因裝置的軟體等級而异。 如果裝置有 [2004 年 5 月更新](hololens-release-notes.md#windows-holographic-version-2004)，請執行以下步驟。

1. 將佈建套件放在 USB 的根部，然後插入集線器。
2. 將乙太網纜線連線至集線器。
3. 將 USB-C 集線器連線至 HoloLens 裝置。
4. 開啟 HoloLens 裝置並佩戴裝置。
5. 按下 **[降低音量] 和 [電源] 按鈕** 以套用置佈建套件。
6. 技術人員現在可以遵循 OOBE，完成後請打開 [設定] 應用程式，並抓取裝置的 MAC 位址。

如果裝置具有 [2004 年 5 月更新](hololens-release-notes.md#windows-holographic-version-2004)之前的作業系統組建，請執行以下步驟。

1. 開啟 HoloLens 裝置，並將裝置插入電腦。
2. 裝置應在電腦上顯示為檔案存放裝置。
3. 將佈建套件複製到裝置
4. 將乙太網纜線連線至集線器。
5. 將 USB-C 集線器連線至 HoloLens 裝置。
6. 佩戴裝置。
7. 按下 **[降低音量] 和 [電源] 按鈕** 以套用置佈建套件。
8. 技術人員現在可以遵循 OOBE，完成後請打開 [設定] 應用程式，並抓取裝置的 MAC 位址。

### 優點

這允許裝置的&quot;單次觸控&quot;，以套用正確的佈建套件並收集裝置的 MAC 位址。 [您可以依照這裡的指導方針建立佈建套件。](https://docs.microsoft.com/hololens/hololens-provisioning)

## 具有 Intune 注冊的 Autopilot

### 需求

- 可存取客戶網路的有線網路連接埠
- 執行 Windows 全息攝像版 2004 的 HoloLens 裝置
- 與 HoloLens 相容的 USB-C 集線器
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

### Process

1. 將 USB-C 集線器和乙太網纜線插入 HoloLens 2 裝置。
2. 開啟 HoloLens 2。
3. 該裝置應透過乙太網路配接器自動連線到 OOBE 上的網際網路，偵測 Autopilot 設定，並自動注冊 Azure AD 和 Intune
4. 裝置會視需要透過 Intune 套用所需的 Wi-Fi 憑證和其他設定
5. 完成後，技術人員將能够載入 Intune（端點管理員）入口網站，並在 **首頁 -> 裝置 ->DeviceName-> 硬體** 裝置屬性頁鑽研。
6. Wi-Fi MAC 位址將在 Intune 入口網站中可見

![透過 Intune 的 MAC 位址](images/mac-address-intune.jpg)

7. 技術人員會將新增此 MAC 位址作爲允許使用的裝置。

### 優點

這將為技術人員提供&quot;無障礙&quot;的部署體驗，裝置能够從方塊進入 Azure AD 和 Intune 注冊，而無需技術人員佩戴裝置或手動與 HoloLens 環境互動。

## 向技術人員報告 MAC 位址

### 需求

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

### Process

Intune 注冊完成後，技術人員會執行上述腳本來取得 MAC 位址。
