---
title: Windows Defender 應用程式控制 (WDAC)
description: 概觀瞭解何者是 Windows Defender 應用程式控制項，以及如何使用它來管理 HoloLens 混合實境裝置。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 23c9a274387424e8f084a4729ee621e130820716
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284134"
---
# Windows Defender 應用程式控制 (WDAC)

WDAC 可讓 IT 系統管理員設定其裝置，以封鎖裝置上的應用程式啟動。 這和裝置限制方法不同，例如 Kiosk 模式，使用者會以 UI 呈現，此 UI 會隱藏裝置上的應用程式，但仍可以啟動。 執行 WDAC 時，這些應用程式仍然顯示在所有應用程式清單中，但 WDAC 會停止這些 App 與程式，裝置使用者無法啟動這些 App 與程式。

裝置可指派多個 WDAC 政策。 如果在一個系統上設定了多個 WDAC 策略，則限制最多的策略會生效。 

> [!NOTE]
> 當使用者嘗試啟動由 WDAC 封鎖的應用程式時，在 HoloLens 上，不會收到無法啟動該應用程式的通知。

以下指南供使用者瞭解如何使用 WDAC 和 Windows PowerShell 來允許或封鎖 [HoloLens 2](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)裝置上的應用程式與 Microsoft Intune。

當使用者使用第一個範例步驟搜尋安裝在其 Windows 10 PC 上的 App 時，可能需要嘗試幾次來縮小結果範圍。

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

如果您不知道套件的完整名稱，您可能需要執行幾次 Get-AppxPackage -name \*YourBestGuess\*' 才能找到它。 接著，一旦有名稱執行 '$package 1 = Get-AppxPackage -name Actual.PackageName'

例如，針對 Microsoft Edge 執行下列操作將會返回多個結果，但從該清單您可以確認您需要的全名是 Microsoft.MicrosoftEdge。

```powershell
Get-AppxPackage -name *edge*
``` 

## HoloLens 上的應用程式套件系列名稱

在上方連結的指南中，您可以手動編輯newPolicy.xml並新增只有在 HoloLens 上以套件系列名稱安裝之應用程式的規則。 有時候您可能會使用非桌上型電腦中要新加入至策略的應用程式。

以下是 HoloLens 2 In-Box常用和常用應用程式的清單。

| 應用程式名稱                   | 套件系列名稱                                |
|----------------------------|----------------------------------------------------|
| 3D 檢視器                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| 應用程式安裝程式              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</sup>         |
| 行事曆                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| 相機                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 Guides        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| 意見反應中樞               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| 檔案總管              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Mail                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| 電影與電視                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| 相片                     | Microsoft.Windows.Photos_8wekyb3d8bbwe             |
| 設定                   | HolographicSystemSettings_cw5n1h2txyewy            |
| 提示                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1 - 封鎖應用程式安裝程式只會封鎖應用程式安裝程式應用程式，不會封鎖從其他來源安裝的應用程式，例如 Microsoft Store 或 MDM 解決方案。

### 如何尋找套件系列名稱

如果清單中沒有應用程式，則使用者可能會使用裝置入口網站，連接至已安裝要封鎖之應用程式的 HoloLens 2，以判斷 PackageRelativeID，並在那裡取得 PackageFamilyName。

1. 在您的 HoloLens 2 裝置上安裝應用程式。 
1. 開啟設定 ->更新&安全性 ->開發人員，並啟用 **開發人員模式** ，然後 **啟用裝置入口網站**。 
    1. 在此閱讀更多有關裝置入口網站 [設定及使用的詳細資訊指示](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。
1. 一旦連接裝置入口網站，請流覽至流覽至流覽 **視圖** ，然後流覽 **至應用程式**。 
1. 在安裝的應用程式面板中，使用下拉式清單選取已安裝的應用程式。 
1. 找到 PackageRelativeID。 
1. 在 ！之前複製 App 字元，這些字元就會是您的 PackageFamilyName。


