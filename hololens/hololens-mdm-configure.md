---
title: 使用 Microsoft 的端點管理員 Intune 管理 HoloLens 裝置
description: 使用 MDM 來設定 CSP 與原則，並依比例管理 HoloLens。
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
ms.openlocfilehash: 4fda0b271e915e82350f806418d2f02cbdd5a796
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009633"
---
# 使用 Microsoft 的端點管理員 Intune 管理 HoloLens 裝置

您可以透過 MDM 管理多種不同的設定。 您可以將 Intune 裝置組成群組，並將配置部署到這些使用者或裝置群組。 您也可以部署和管理 app、設定裝置以連線至您的網路，以及將更新設定為在所需的時間，以及在需要更新環路時進行。 

## 如何透過 Intune 管理

### 裝置類別和群組
使用 Intune，您可以建立裝置類別，根據您建立的類別（例如工程、醫學、開發人員等），自動將裝置新增到群組中。 其目的是讓您更容易管理執行 Windows 全息版的裝置。
延伸閱讀：將 [裝置分類成群組](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)

### 裝置設定設定檔
Intune 包含您可以在組織內的不同裝置上啟用或停用的設定和功能。 這些設定和功能是使用設定檔來管理。 例如，您可以建立可在執行 Windows 全息版的裝置上啟用 Cortana 或使用 Microsoft Defender Smart 螢幕的設定檔。
在您的設定檔中，您可以使用 OMA-URI 來自訂部分設定、建立裝置限制，以及設定虛擬私人網路 (VPN) 和 Wi-fi。
[開始使用設定檔](https://docs.microsoft.com/mem/intune/configuration/device-profiles)和 [設定檔概覽](https://docs.microsoft.com/mem/intune/configuration/device-profile-create)。

## 可管理和設定的範例

使用 MDM 管理裝置可提供大量的專案供您選取。 

### Wi-Fi
[Wi-fi 設定](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) 會將無線網路設定指派給使用者和裝置。 當您指派 Wi-fi 設定檔時，使用者可以在不需自行設定的情況下，取得您公司的 Wi-fi 存取權。
進一步瞭解如何 [針對 HoloLens 設定您的網路](hololens-commercial-infrastructure.md)

### 憑證
認證：提供帳戶驗證、Wi-fi 驗證、VPN 加密及網頁內容 SSL 加密，以協助改善安全性。 雖然系統管理員可以透過預配套件手動管理裝置上的憑證，但最佳做法是使用您的 MDM system 在整個週期中管理這些憑證，從註冊到更新和吊銷等。 您可以註冊 (裝置之後，您的 MDM 系統就能自動將這些憑證部署到裝置的憑證存放區，只要 MDM system 支援簡單憑證註冊通訊協定 (SCEP) 或公開金鑰加密標準 #12 (# A5 的) PKCS # 12。 MDM 也可以在目前的憑證過期前，查詢及刪除已註冊的用戶端憑證，或觸發新的註冊要求。 

### Proxy
大多數公司內部網路都利用 proxy 來管理內部流量。 使用 HoloLens 2，您可以設定乙太網與 Wi-fi 連線的 proxy 伺服器。 這些設定不會套用至 VPN 連線。 如需 Windows 10 proxy 設定的詳細資訊，請參閱 [NETWORKPROXY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)。

### VPN
組織通常會使用 VPN，來控制對其公司內部網路上 app 與資源的存取權。 HoloLens 2 支援 SSL VPN 連線，這需要來自 Microsoft Store 的可下載外掛程式，而且是您選擇的 VPN 廠商專用的。 
- 閱讀更多有關 [HoloLens 上 VPN 的](hololens-network.md#vpn)資訊。
- 如需有關 VPN 設定檔的詳細資訊，請參閱 [VPNV2 CSP](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)。

### 部署及管理 app
使用 Intune，您可以在執行 Windows 全息版的裝置上新增應用程式。 MDM 方案可讓 IT 決策者和系統管理員自行自動安裝 (推) 其內部、行業內應用程式，或透過使用者群組的商店購買 app。 部署應用程式的方法有很多種，包括：
-   [Intune 和公司入口網站]( app-deploy-intune.md)
-   [商務用 Microsoft Store]( app-deploy-store-business.md)

深入瞭解透過 Intune 進行的 app 管理。
-   [將應用程式新增至 Intune](https://docs.microsoft.com/mem/intune/apps/apps-add)
-   [新增 Microsoft Store 應用程式](https://docs.microsoft.com/mem/intune/apps/store-apps-windows)
-   [新增您建立的應用程式](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
- [將應用程式指派給群組](https://docs.microsoft.com/mem/intune/apps/apps-deploy)

### 軟體更新
Intune 包括 Windows 10 裝置的「更新響鈴」功能。 這些更新鈴響包括一組決定如何安裝更新的設定。 例如，您可以建立要安裝更新的維護時段，或選擇在安裝更新後重新開機。 更新環可以套用到執行 Windows 全息企業版的多個裝置。
進一步瞭解如何 [管理 HoloLens 更新](hololens-updates.md) 及透過 [Intune 管理軟體更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。

### 設定 Kiosk 模式
使用 Intune 中提供的共用或來賓電腦功能，您可以將 Windows 全息版裝置設定為以展臺方式執行。 這些裝置可以 (單一 app kiosk 模式) 執行一個 app，或執行多個 app (多重 app kiosk 模式) 。 Kiosk 模式是一個 UI，可控制哪些身分預設可以存取哪些 app。
瞭解如何 [將 HoloLens 設定為 kiosk]( hololens-kiosk.md)

