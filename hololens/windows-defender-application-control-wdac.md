---
title: Windows Defender應用程式控制-WDAC
description: 概述什麼是 Windows Defender 應用程式控制，以及如何使用它來管理 HoloLens 的混合現實裝置。
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
ms.openlocfilehash: a27a16913873c5245f734dbe084eb2b7ed007c20
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639925"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender應用程式控制-WDAC

WDAC 可讓 IT 系統管理員設定其裝置，以封鎖在裝置上啟動應用程式。 這與裝置限制的方法不同，例如 Kiosk 模式，其中使用者會看到 UI 來隱藏裝置上的應用程式，但仍可啟動。 在執行 WDAC 的同時，應用程式仍會顯示在 [所有應用程式] 清單中，但 WDAC 會停止這些應用程式和進程，使其無法由裝置使用者啟動。

可能指派一個以上的 WDAC 原則給裝置。 如果系統上設定了多個 WDAC 原則，則最嚴格的原則會生效。 

> [!NOTE]
> 當使用者嘗試啟動由 WDAC 封鎖的應用程式時，HoloLens 不會收到有關無法啟動該應用程式的通知。

下列指南可讓使用者瞭解如何[使用 WDAC 和 Windows PowerShell，在 HoloLens 2 裝置上使用 Microsoft Intune 來允許或封鎖應用程式](/mem/intune/configuration/custom-profile-hololens)。

當使用者使用第一個範例步驟搜尋安裝在其 Windows 10 電腦上的應用程式時，可能需要進行幾次嘗試縮小結果的範圍。

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

如果您不知道封裝的完整名稱，您可能需要執行 ' Add-appxpackage-name \* YourBestGuess \* ' 數次，才能找到它。 然後，一旦您的名稱執行 ' $package 1 = Get-AppxPackage-name PackageName '

例如，執行下列 Microsoft Edge 將會傳回一個以上的結果，但從該清單中，您可以識別出所需的完整名稱是 MicrosoftEdge。

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>HoloLens 上應用程式的套件系列名稱

在上方連結的指南中，您可以手動編輯 newPolicy.xml，並為僅安裝在 HoloLens 上的應用程式新增其套件系列名稱的規則。 有時您可以使用的應用程式不在您想要新增至原則的桌上型電腦上。

以下是 HoloLens 2 裝置常用且 In-Box 的應用程式清單。

| 應用程式名稱                   | 套件家族名稱                                |
|----------------------------|----------------------------------------------------|
| 3D 檢視器                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| 應用程式安裝程式              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup>         |
| Calendar                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| 相機                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 Guides        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| 意見反應中樞               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| 檔案總管              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| 電子郵件                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| 電影與電視                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| 照片                     | 微軟。Windows。Photos_8wekyb3d8bbwe             |
| 設定                   | HolographicSystemSettings_cw5n1h2txyewy            |
| 提示                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1-封鎖應用程式安裝程式只會封鎖應用程式安裝程式應用程式，而不會封鎖從其他來源（例如 Microsoft Store 或您的 MDM 解決方案）安裝的應用程式。

### <a name="how-to-find-a-package-family-name"></a>如何尋找套件系列名稱

如果應用程式不在此清單中，則使用者可能會使用裝置入口網站，連接到已安裝要封鎖之應用程式的 HoloLens 2，以判斷 PackageRelativeID 以及從中取得 PackageFamilyName。

1. 在 HoloLens 2 裝置上安裝應用程式。 
1. 開啟適用于開發人員的設定 > 更新 & 安全性 >，並啟用 **開發人員模式**，然後再啟用 **裝置入口網站**。 
    1. 如需更多詳細資訊 [，請參閱這裡的設定和使用裝置入口網站](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。
1. 裝置入口網站連線之後，請流覽至 **Views** 然後再流覽至 [ **應用程式**]。 
1. 在 [已安裝的應用程式] 面板中，使用下拉式清單來選取已安裝的應用程式。 
1. 找出 PackageRelativeID。 
1. 將應用程式字元複製到！之前，這些字元將會是您的 PackageFamilyName。


