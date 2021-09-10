---
title: 使用 Microsoft 的端點管理員 Intune 來管理 HoloLens 裝置
description: 瞭解如何使用 Intune 來大規模設定 CSP、原則，以及管理 HoloLens 混合現實裝置。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/9/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5485a4b2558a11a6c0545ec8b3405c120cff287c
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427373"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a>使用 Microsoft 的端點管理員 Intune 來管理 HoloLens 裝置

您可以透過 MDM 來管理許多不同的設定。 使用 Intune 裝置可群組在一起，並可將設定部署至這些使用者或裝置群組。 您也可以部署和管理應用程式、設定裝置以連接到您的網路，以及設定在需要的時間和更新通道上進行更新。 

## <a name="how-to-manage-via-intune"></a>如何透過 Intune 管理

### <a name="device-categories-and-groups"></a>裝置類別和群組
使用 Intune，您可以建立裝置類別，根據您所建立的類別（例如工程、醫療、開發人員等），自動將裝置新增至群組。 用意是讓您可以更輕鬆地管理執行 Windows Holographic for Business 的裝置。
深入瞭解：將 [裝置分類成群組](/mem/intune/enrollment/device-group-mapping)

### <a name="device-configuration-profiles"></a>裝置組態設定檔
Intune 包含您可以在組織內不同裝置上啟用或停用的設定及功能。 可使用設定檔來管理這些設定和功能。 例如，您可以在執行 Windows Holographic for Business 的裝置上，建立啟用 Cortana 或使用 Microsoft Defender SmartScreen 的設定檔。
在您的設定檔中，您可以使用 OMA-URI 來自訂一些設定、建立裝置限制，以及設定虛擬私人網路 (VPN) 和 Wi-Fi。
[開始使用](/mem/intune/configuration/device-profiles)設定設定檔和 [設定檔總覽](/mem/intune/configuration/device-profile-create)。

## <a name="examples-of-what-can-be-managed-and-configured"></a>可管理和設定的範例

使用 MDM 來管理裝置，可提供一系列可選取的專案。 

### <a name="wi-fi"></a>Wi-Fi
[Wi-Fi 設定](/mem/intune/configuration/wi-fi-settings-configure)指派給使用者和裝置的無線網路設定。 當您指派 Wi-Fi 設定檔時，使用者不需要自行設定，即可存取您的公司 Wi-Fi。
深入瞭解如何設定[網路以進行 HoloLens](hololens-commercial-infrastructure.md)

### <a name="certificates"></a>憑證
憑證藉由提供帳戶驗證、Wi-Fi 驗證、VPN 加密，以及 web 內容的 SSL 加密，來協助提升安全性。 雖然系統管理員可以透過布建套件手動管理裝置上的憑證，但最佳做法是使用您的 MDM 系統，在整個生命週期中管理這些憑證–從註冊到續約和撤銷。 只要 MDM 系統支援簡單憑證註冊通訊協定 (SCEP) 或公開金鑰加密標準 #12 (PKCS # 12) ) ，您的 MDM 系統就可以在您註冊 (裝置後，自動將這些憑證部署到裝置的憑證存放區。 MDM 也可以查詢和刪除已註冊的用戶端憑證，或在目前的憑證到期之前觸發新的註冊要求。 

### <a name="proxy"></a>Proxy
大部分的公司內部網路網路都利用 proxy 來管理內部流量。 您可以使用 HoloLens 2 設定適用于 ethernet 和 Wi-Fi 連線的 proxy 伺服器。 這些設定不會套用至 VPN 連線。 如需 Windows 10 proxy 設定的詳細資訊，請參閱[NetworkProxy CSP](/windows/client-management/mdm/networkproxy-csp)。

### <a name="vpn"></a>VPN
組織通常會使用 VPN，來控制對其公司內部網路上 app 與資源的存取權。 HoloLens 2 支援 SSL VPN 連線，這需要來自 Microsoft Store 的可下載外掛程式，且特定于您選擇的 VPN 廠商。 
- 深入瞭解[HoloLens 上的 VPN](hololens-network.md#vpn)。
- 如需 VPN 設定檔的詳細資訊，請參閱 [>VPNV2 CSP](/windows/client-management/mdm/vpnv2-csp)。

### <a name="deploy-and-manage-apps"></a>部署和管理 App
使用 Intune 時，您可以將應用程式新增至執行 Windows Holographic for Business 的裝置。 MDM 解決方案可讓 IT 決策者和系統管理員私下自動安裝 (推送) 其內部、企業營運應用程式，或透過使用者群組的商店購買應用程式。 有許多方式可以部署應用程式，包括：
-   [Intune 和公司入口網站]( app-deploy-intune.md)
-   [商務用 Microsoft Store]( app-deploy-store-business.md)

深入瞭解如何透過 Intune 進行應用程式管理。
-   [將應用程式新增至 Intune](/mem/intune/apps/apps-add)
-   [新增 Microsoft Store 應用程式](/mem/intune/apps/store-apps-windows)
-   [新增您建立的應用程式](/mem/intune/apps/lob-apps-windows)
- [將應用程式指派給群組](/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a>軟體更新
Intune 包含一項適用於 Windows 10 裝置的功能，稱為更新通道。 這些更新通道包含一組決定了更新安裝方式的設定。 例如，您可以建立一個維護期間來安裝更新，或選擇在安裝更新後重新啟動。 您可以將更新通道套用至多個執行 Windows Holographic for Business 的裝置。
深入瞭解如何透過 Intune[管理 HoloLens 更新](hololens-updates.md)和[管理軟體更新](/mem/intune/protect/windows-update-for-business-configure)。

### <a name="configure-kiosk-mode"></a>設定 kiosk 模式
使用 Intune 中可用的共用或來賓電腦功能，您可以設定 Windows Holographic for Business 裝置當做 kiosk 來執行。 這些裝置可以執行一個應用程式 (單一應用程式 kiosk 模式)，或執行多個應用程式 (多應用程式 kiosk 模式)。 Kiosk 模式是一個 UI，可控制哪些身分識別可以依預設存取哪些應用程式。
瞭解如何[將 HoloLens 設定為 kiosk]( hololens-kiosk.md)

