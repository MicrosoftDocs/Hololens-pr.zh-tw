---
title: Windows Defender 應用程式控制 (WDAC)
description: 瞭解 WDAC 是什麼，以及如何使用它來管理 HoloLens 裝置。
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
ms.openlocfilehash: dc1deb2b159d3d41b1a1f73c33f1cd44731f8e4d
ms.sourcegitcommit: 72ae5a270f869393872eac160e43076eaa35fe4c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135566"
---
# Windows Defender 應用程式控制 (WDAC)

WDAC 可讓 IT 系統管理員設定其裝置，以封鎖裝置上的應用程式啟動。 這與裝置限制的方法不同（例如 Kiosk 模式），使用者會在其中提供隱藏裝置上 app 的 UI，但仍可啟動這些應用程式。 在已實現 WDAC 的情況下，應用程式仍會顯示在 [所有應用程式] 清單中，但 WDAC 會停止由裝置使用者啟動這些 app 和進程。

> [!NOTE]
> 當使用者嘗試啟動由 WDAC 封鎖的應用程式時，他們將不會收到無法啟動該應用程式的通知。

以下是使用者瞭解如何在使用 [Microsoft Intune 的 HoloLens 2 裝置上使用 WDAC 和 Windows PowerShell 來允許或封鎖 app](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)的指南。

當使用者使用第一個範例搜尋安裝在 Windows 10 電腦上的應用程式時，可能需要進行幾個嘗試來縮小結果範圍。

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

如果您不知道套件的完整名稱，您可能需要執行數次「Add-appxpackage-name \ * YourBestGuess \ *」才能進行尋找。 當您的名稱為「$package 1 = Get-AppxPackage 名稱實際 PackageName "

例如，執行下列 for Edge 會傳回多個結果，但在該清單中，您可以找出您所需的完整名稱是 MicrosoftEdge。 

```powershell
Get-AppxPackage -name *edge*
``` 

## 在 HoloLens 上應用程式的套件系列名稱

在上述連結的指南中，您可以手動編輯 newPolicy.xml，以及新增只安裝在 HoloLens 及其套件系列名稱的應用程式規則。 有時候，您可能會使用的 app 不在桌上型電腦上，您想要新增至原則。 

以下是適用于 HoloLens 2 裝置的常用和 In-Box 應用程式清單。

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

- 1封鎖 App 安裝程式只會封鎖 App 安裝程式應用程式，而不會封鎖從其他來源（例如 Microsoft Store 或您的 MDM 解決方案）所安裝的應用程式。

### 如何尋找套件系列名稱

如果應用程式不在此清單中，則使用者可以使用 Device Portal，連線至已安裝想要封鎖之 app 的 HoloLens 2，以判斷 PackageRelativeID，並從該處取得 PackageFamilyName。

1. 在您的 HoloLens 2 裝置上安裝應用程式。 
1. 開啟 [設定]-> 更新 & Securtiy-> 供開發人員使用，並啟用 [ **開發人員模式]** 和 [ **裝置入口網站**]。 
    1. 更多詳細資訊指示請參閱 [在這裡設定及使用 device portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。
1. 連接裝置入口網站之後，請流覽至 [ **視圖** ]，然後流覽至 [ **app**]。 
1. 在 [已安裝的應用程式] 面板中，使用下拉式清單來選取已安裝的應用程式。 
1. 找出 PackageRelativeID。 
1. 在！之前複製應用程式字元，這將是您的 PackageFamilyName。

## 樣本封鎖 App 安裝程式

舉例來說，您可能會想要封鎖 [App 安裝](app-deploy-app-installer.md) 程式 App。 我們已在這個範例中加入了一些範例程式碼。 請在 [這個範例下載這些程式碼範例](https://aka.ms/HoloLensDocs-Sample-WDAC-App-Installer)。 在 zip 檔案中，您會看到：

| 檔案 | 用法 |
|-|-|
| compiledPolicy | [在步驟9中建立，在最後步驟10中使用。](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) |
| mergedPolicy.xml | [在步驟6中建立。](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) |
| WDAC_Set syncml | 在 WDAC 中未使用，但可用於 [ENTERPRISEMODERNAPPMANAGEMENT CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp) |

如果您想要立即封鎖 app，在此案例中，請使用 compiledPolicy 檔案，然後跳至上述連結中的步驟10。 這可讓您測試自訂原則，並確保群組指派與原則配置正確無誤。 

如果您想要將針對封鎖 App 安裝程式的 WDAC 原則與上述清單中的其他 app 結合，或任何其他應用程式，您可以使用 mergedPolicy.xml 檔案並繼續合併新的原則。 如上述的 WDAC 原則所述，不需要這麼做。 

由於 App 安裝程式 app 是透過嘗試開啟檔案來啟動，因此會出現提示。 視 WDAC 封鎖的上述 App 所述，不會顯示已封鎖的提示，但由於使用者嘗試在其裝置上開啟檔案，因此會出現開啟檔案時的錯誤。 

![應用程式安裝已從 WDAC 封鎖](images\wdac-app-installer-no-launch.jpg)

如果您不想使用 WDAC，您可以選擇使用 [ENTERPRISEMODERNAPPMANAGEMENT CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp) 來移除 App 安裝程式 UX （畢竟是 app）。 如此一來，應用程式安裝程式 app 就會從裝置中卸載。 .appx、msix、msixbundle 及其他副檔名，以及 web 到 app 啟動的通訊協定將不會再由應用程式安裝程式來處理。 使用者會收到在市集中搜尋檔案副檔名/通訊協定的程式提示，因為沒有列出該應用程式。