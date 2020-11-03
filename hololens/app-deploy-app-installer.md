---
title: 如何透過 HoloLens 2 App 安裝程式載入並安裝應用程式
description: 透過 UI 進行投影片載入和安裝應用程式
keywords: app 管理、app、hololens、app 安裝程式
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 10/26/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 415733bb2809b7ae2808edc097423f8928910c57
ms.sourcegitcommit: c4fd9a87bb7c728c73418f95a1b15dd93b0af7c6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "11150914"
---
# 透過 App 安裝程式在 HoloLens 2 上安裝應用程式

> [!IMPORTANT]
> 此功能目前僅適用于 Windows 測試人員組建 19041.1377 + 中的 avalible。 [深入瞭解如何在 Windows 測試人員組建中註冊](hololens-insider.md)。

在我們的 Windows 測試人員發行版本中，我們 **新增了 (App 安裝程式) 的新功能，可讓您在 HoloLens 2 裝置上更順暢地安裝應用程式** 。 預設會將 **未受管理的裝置的功能預設為開啟**。 為了避免中斷企業，目前 **不會對受管理的裝置提供** app 安裝程式。  

如果下列 **任一** 條件成立，裝置就會被視為「受管理」：
- 已[註冊](hololens-enroll-mdm.md)MDM
- 使用[預配套件](hololens-provisioning.md)進行設定
- 使用者身分 [識別](hololens-identity.md) 為 AAD

您現在可以安裝應用程式，而不需要啟用開發人員模式或使用 Device Portal。  只要透過 USB 或邊緣) 將 (下載到您的裝置，然後在檔案資源管理器中流覽至 Appx 套件，就會提示您啟動安裝。  或者， [從網頁啟動安裝](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。  就像從 Microsoft Store 或側載使用 MDM 的 LOB 應用程式部署功能所安裝的應用程式，應用程式必須使用 [簽署工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 進行數位簽署，而且在部署 App 之前，必須由 HoloLens 裝置 [信任用來簽署的憑證](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) 。   

## 需求

### 針對您的裝置： 
> [!NOTE]
> 此功能目前僅適用于 Windows 測試人員組建 19041.1377 + 中的 avalible。 [深入瞭解如何在 Windows 測試人員組建中註冊](hololens-insider.md)。

### 針對您的應用程式： 
您 app 的解決方案設定必須是 [ **主版** ] 或 [ **發行** ]，因為 app 安裝程式會使用市集中的相依性。 查看更多關於 [建立應用程式套件](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)的資訊。

透過此方法所安裝的應用程式必須經過數位簽章。 您必須使用憑證來簽署 app。 您可以從 [MS 信任的 CA 清單](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)中取得證書，在這種情況下，您不需要採取任何其他動作。 或者，您也可以簽署您自己的憑證，但必須將憑證推送到裝置上。 
- 如何[使用 [簽署工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)] 簽署 app。

**憑證選項：** 
- [MS 受信任的 CA 清單](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**挑選證書部署方法。** 
- 您可以將[預配套件](hololens-provisioning.md)套用到本機裝置。
- MDM 可用來 [將憑證與裝置](https://docs.microsoft.com/mem/intune/protect/certificates-configure)設定搭配使用。
- 使用 [裝置 [憑證管理員](hololens-insider.md#certificate-manager)]。 

## 安裝方法

1.  確定您的裝置未被視為已管理。
1.  確定您的 HoloLens 2 裝置已通電且已登入。
1.  在您的電腦上流覽至您的自訂應用程式，並將 yourapp 複製到 yourdevicename\Internal Storage\Downloads。 
    完成檔案複製之後，您可能會中斷裝置連線，並在稍後完成安裝。
1.  從您的 HoloLens 2 裝置開啟 [ **開始] 功能表**，選取 [ **所有應用程式** ]，然後啟動檔案 **資源管理器** 應用程式。
1.  流覽至 [下載] 資料夾。 您可能需要在應用程式的左面板上，選取 [ **此裝置** ]，然後流覽至 [下載]。
1.  選取 yourapp 檔案。 
1.  App 安裝程式將會啟動。 選取 [ **安裝** ] 按鈕來安裝您的 app。 

已安裝的應用程式會在安裝完成後自動啟動。 

![透過 App 安裝程式安裝 MRTK 範例](images/hololens-app-installer-picture.jpg)

### 疑難排解安裝
如果您的 app 安裝失敗，請檢查下列專案：
-   您的應用程式是主版本或發行組建。
- 您的裝置已更新為可使用此功能的組建。 
-   您已 [連線至網際網路](hololens-network.md)。
-   您 [的 Microsoft Store 端點](hololens-offline.md) 已正確設定。  

## Web 安裝程式

使用者可以直接從 web 伺服器安裝應用程式。 這會將 App 安裝程式與簡單的下載和安裝分發方法結合使用。 

### 如何設定網路安裝：
1.  確定您的 app 已正確設定為 [安裝]。
1.  請依照下列 [步驟在網頁上啟用此操作](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。 

### 使用者體驗：
1. 使用者使用先前選取的方法，接收並將憑證安裝到裝置。 
1. 使用者造訪上述步驟所建立的 URL。

App 現在將會安裝到裝置上。 若要尋找應用程式，請開啟 [ **開始] 功能表** ，然後選取 [ **所有應用程式** ] 按鈕來尋找您的應用程式。 

-   如需此安裝方法的疑難排解說明，請參閱 [app 安裝程式問題疑難排解](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)。 

> [!NOTE]
> 更新程式中不支援 UI。 所以不支援 [此頁面](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 上的 [ShowPrompt] 選項和相關選項。

## 範例應用程式

如果您想要使用一些範例應用程式試試，請查看一些可用的範例：
- [MRTK 範例中心](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [表面](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [可用於測試的 UWP 範例應用程式](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
