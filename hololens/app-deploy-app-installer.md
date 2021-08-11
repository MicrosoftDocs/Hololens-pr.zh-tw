---
title: 如何透過 HoloLens 2 應用程式安裝程式側載和安裝應用程式
description: 瞭解如何使用應用程式安裝程式和側載，以及透過 UI 安裝應用程式，來安裝應用程式並對其進行疑難排解。
keywords: 應用程式管理、應用程式、hololens、應用程式安裝程式
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0b0de9039ce4d0c1eeab968b0f7c2f5eee8cdc34739391b6022b409325955350
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665262"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>透過應用程式安裝程式在 HoloLens 2 上安裝應用程式

> [!NOTE]
> 這項功能已在 Windows 全像[20H2 版–2020年12月更新](hololens-release-notes.md)中提供。 確定您的裝置已 [更新](hololens-update-hololens.md) 為使用此功能。

我們 **新增了 (應用程式安裝程式) 的新功能，可讓您更順暢地** 在 HoloLens 2 裝置上安裝應用程式。 **預設會針對未受管理的裝置開啟** 此功能。 為了避免對企業造成中斷， **受控裝置** 目前無法使用應用程式安裝程式。  

如果下列 **任一** 條件成立，則會將裝置視為「受控」：

- 已[註冊](hololens-enroll-mdm.md)MDM
- 已設定布建 [套件](hololens-provisioning.md)
- 使用者身分 [識別](hololens-identity.md) 為 Azure AD

您現在可以安裝應用程式，而不需要啟用開發人員模式或使用裝置入口網站。  下載 (over USB 或透過 Microsoft Edge) Appx 套件組合移至您的裝置，並流覽至檔案總管中的 appx 配套，以提示開始安裝。  或者， [從網頁起始安裝](/windows/msix/app-installer/installing-windows10-apps-web)。 就像您使用 MDM 的 LOB 應用程式部署功能從 Microsoft Store 或側載安裝的應用程式，應用程式必須使用[簽署工具](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)進行數位簽署，而[用來簽署的憑證必須](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)由 HoloLens 裝置信任，才能部署應用程式。

## <a name="requirements"></a>規格需求

### <a name="for-your-devices"></a>針對您的裝置：

這項功能目前適用于 HoloLens 2 裝置 Windows 全像20H2 組建。 請確定使用此方法的任何裝置都已 [更新](hololens-update-hololens.md)。

### <a name="for-your-apps"></a>針對您的應用程式：

您應用程式的解決方案設定必須是 **Master** 或 **Release** ，因為應用程式安裝程式會使用存放區的相依性。 深入瞭解如何 [建立應用程式套件](/windows/msix/app-installer/create-appinstallerfile-vs)。

透過此方法安裝的應用程式必須經過數位簽署。 您必須使用憑證來簽署應用程式。 您可以從「 [MS 受信任的 CA」清單](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)取得憑證，在這種情況下，您不需要採取任何額外的動作。 或者，您也可以簽署自己的憑證，但憑證需要推入裝置上。

- 如何[使用簽署工具](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)簽署應用程式。

**憑證選項：**

- [MS 受信任 CA 清單](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**挑選憑證部署方法。**

- 布建[套件](hololens-provisioning.md)可以套用至本機裝置。
- MDM 可以用來 [將憑證](/mem/intune/protect/certificates-configure)套用至裝置設定。
- 在裝置 [憑證管理員](certificate-manager.md)上使用。

## <a name="installation-method"></a>安裝方法

1. 檢查您的裝置是否未被視為受管理。
1. 檢查您的 HoloLens 2 裝置已開啟電源且已登入。
1. 在您的電腦上，流覽至您的自訂應用程式，並將 yourapp 複製到 yourdevicename\Internal 儲存體 \Downloads。
    完成檔案複製後，您可能會中斷裝置連線，並于稍後完成安裝。
1. 從您的 HoloLens 2 裝置開啟 [**開始] 功能表**，選取 [**所有應用程式**]，然後啟動 **檔案總管** 應用程式。
1. 流覽至 [下載] 資料夾。 您可能需要在應用程式的左側面板上先選取 **此裝置** ，然後流覽至 [下載]。
1. 選取 yourapp .appxbundle 檔。
1. 將會啟動應用程式安裝程式。 選取 [ **安裝** ] 按鈕以安裝您的應用程式。

已安裝的應用程式會在安裝完成時自動啟動。

![透過應用程式安裝程式安裝 MRTK 範例](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>安裝疑難排解

如果您的應用程式無法安裝，請檢查下列各項以進行疑難排解：

- 您的應用程式可以是主要或發行組建。
- 您的裝置已更新為可使用此功能的組建。
- 您已 [連線到網際網路](hololens-network.md)。
- 已正確設定[Microsoft Store 的端點](hololens-offline.md)。  

## <a name="web-installer"></a>Web 安裝程式

使用者可以直接從 web 伺服器安裝應用程式。 此流程會使用應用程式安裝程式結合簡單的下載和安裝散發方法。

### <a name="how-to-set-up-web-install"></a>如何設定 web 安裝：

1. 確定已正確設定您的應用程式以進行安裝。
1. 請遵循下列 [步驟，以從網頁啟用安裝](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。

### <a name="end-user-experience"></a>終端使用者體驗：

1. 使用者會使用先前選擇的方法，來接收並安裝憑證至裝置。
1. 使用者造訪上述步驟所建立的 URL。

應用程式現在會安裝到裝置。 若要尋找應用程式，請開啟 **[開始] 功能表**，然後選取 [**所有應用程式**] 按鈕以尋找您的應用程式。

- 如需針對應用程式安裝程式安裝方法進行疑難排解的詳細說明，請造訪 [應用程式安裝程式問題疑難排解](/windows/msix/app-installer/troubleshoot-appinstaller-issues)。

> [!NOTE]
> 不支援更新程式期間的 UI。 因此不支援 [這個頁面](/windows/msix/app-installer/update-settings) 上的 ShowPrompt 選項和相關的選項。

## <a name="sample-apps"></a>範例應用程式

使用其中一個可用的範例應用程式來嘗試應用程式安裝程式。 
> [!div class="nextstepaction"]
> [範例應用程式](/windows/mixed-reality/develop/features-and-samples)
