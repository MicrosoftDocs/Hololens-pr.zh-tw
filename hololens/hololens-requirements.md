---
title: 常見部署案例
description: 深入瞭解如何在企業環境中部署和管理 HoloLens，包括基礎結構、Azure Active Directory 和行動裝置管理。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bgener
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 4b8975d8eb362212eaf91966f4efa0bc22236327
ms.sourcegitcommit: 3f21b692be2f1b7f9c382f2b735b4c10339d4a78
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2021
ms.locfileid: "127934063"
---
# <a name="common-deployment-scenarios"></a>常見部署案例

## <a name="overview"></a>概觀

當您第一次嘗試時，瞭解如何部署新的裝置可能會很困難。 在這裡，我們將共用不同的方式來部署和管理組織內 Microsoft HoloLens 2 個裝置。

您想要大規模部署方案。 我們想要讓您瞭解。 讓我們先討論部署裝置的步驟，也就是全像全像，以達成目標混合現實案例的價值。 無論您是使用 D365 遠端協助、指南或您建立的 Azure mixed reality 啟用服務的應用程式，我們的常見部署案例都將引導您進行旅程。

您可能是想要在組織內採用 HoloLens 的商務決策者、IT 專業人員或創新團隊。 當您從概念證明到調整的部署建立時，我們的部署指南在您的 IT 基礎結構中有意義 HoloLens-無論大小或規模為何。 以下是最常見的部署案例：

| 案例 |使用方式 | 重點 |
|---------|---------|---------|
| [案例 A：雲端連接的裝置](hololens2-cloud-connected-overview.md) | 當您第一次開始部署時，您可能會從小規模開始，並部署連線至雲端的單一裝置，以查看基本程式。 | 裝置將會連接到雲端服務和公用網際網路。 這最適合客戶使用案例、現場服務和概念證明。|
| [案例 B：組織的網路](hololens2-corp-connected-overview.md) | 當您大規模部署到生產環境時，您可能需要與自己組織的網路整合。 | 裝置會連線到「公司」 wi-fi 網路。 這最適合內部使用者，或在公司環境內使用。|
| [案例 C：離線安全環境](hololens-common-scenarios-offline-secure.md) | 某些任務關鍵性進程或某些公司原則可能會要求使用離線環境。 | 裝置會連線到高度受限的網路，或單純的離線裝置。 這最適合用於高度安全的環境，或遠端區域中的網際網路連線限制。 |

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>案例 A：部署至雲端連接的裝置

此案例相當於在公司內部署受管理的行動裝置。 HoloLens 2 部署為主要用於公司網路外部的環境。 公司資源無法存取，或可能會透過 VPN 來限制。

[![情節圖。](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

### <a name="when-to-use"></a>使用時機

請考慮以下的部署模型：

* 部署概念證明、試驗和現場服務
* 部署 [遠端協助](hololens2-options-remote-assist.md)

### <a name="basic-common-configurations"></a>基本的一般設定

* Wi-Fi 的網路通常完全開放到網際網路和雲端服務
* Azure AD 與行動裝置管理 (MDM) 自動註冊的聯結--MDM (Intune) 受控
* 使用者以自己的公司帳戶登入 (Azure AD) 
  * 每個裝置支援的單一或多個使用者
* 不同層級的裝置鎖定設定會根據特定使用案例套用，從完全開放到單一應用程式 Kiosk。
* 透過 MDM 部署一或多個應用程式

### <a name="common-challenges"></a>常見的挑戰

* 根據案例需求，判斷要套用至 HoloLens 2 的 MDM 設定

對應的雲端連接指南會說明如何在裝置管理中註冊 HoloLens 2、視需要套用授權，以及驗證您的終端使用者是否能夠在裝置設定時立即使用遠端協助。

> [!div class="nextstepaction"]
> [雲端連線部署指南](hololens2-cloud-connected-overview.md)

使用外部用戶端指南將裝置部署到遠端網站，以進行短期或長期外部使用。

> [!div class="nextstepaction"]
> [雲端連線 (外部用戶端) 部署指南](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>案例 B：在組織的網路內部署

此案例與大多數 Windows 10 電腦的傳統部署完全相同。 HoloLens 2 部署在公司網路上，可存取內部公司資源。 網際網路和雲端服務可能會受到限制。 

[![案例 B1 圖表。](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![案例 B2 圖表。](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

### <a name="when-to-use"></a>使用時機

請考慮以下的部署模型：

* 內部使用者
* 在公司環境內大規模部署 (試驗和生產環境) 

### <a name="basic-common-configurations"></a>基本的一般設定

* Wi-Fi network 是內部公司網路，可存取內部資源，並限制存取網際網路或雲端服務。
* 使用 MDM 自動註冊 Azure AD 聯結
* MDM (Intune) 受控
* 使用者以自己的公司帳戶登入 (Azure AD) 
  * 每個裝置支援的單一或多個使用者
* 不同層級的裝置鎖定設定會根據特定使用案例套用，從完全開放到單一應用程式 Kiosk。
* 透過 MDM 部署一或多個應用程式

### <a name="common-challenges"></a>常見的挑戰

* HoloLens 2 不支援內部部署 AD join 或 System Center Configuration Manager (SCCM) 。 僅 Azure AD 與 MDM 聯結。 現今許多公司仍將此案例中的 Windows 10 電腦部署為內部部署 AD 加入的裝置（由 SCCM 管理），而且可能不會部署/設定基礎結構，以透過雲端式 MDM 解決方案來管理內部 Windows 10 裝置。
* 由於 HoloLens 2 是雲端的第一部裝置，因此其高度依賴網際網路和雲端聯機服務來進行使用者驗證、作業系統更新、MDM 管理等等。 連線到公司網路時，可能需要調整 proxy/防火牆規則，才能啟用 HoloLens 2 的存取，以及對其執行的應用程式。
* 公司 Wi-Fi 連線通常需要憑證來向網路驗證裝置或使用者。 透過 MDM 將憑證部署到 Windows 10 裝置所需的基礎結構或設定，可能是設定的挑戰。

對應的公司連接指南會指示如何註冊 HoloLens 2 到您現有的裝置管理、視需要套用授權，以及驗證您的終端使用者是否能夠在裝置設定之後，操作 Dynamics 365 指南，以及使用自訂的企業營運應用程式。

> [!div class="nextstepaction"]
> [公司連線部署指南](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>案例 C：在安全的離線環境中部署

這是高度安全或機密位置的一般部署。 部署 HoloLens 2，主要用於離線且無法存取網路或網際網路。

[![離線安全圖1。](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

### <a name="when-to-use"></a>使用時機

請考慮以下的部署模型：

* 高度安全的環境，需要將資料保留在內部
* 公開將使用裝置的「體驗」
* 遠端區域中的網際網路連線問題

### <a name="basic-common-configurations"></a>基本的一般設定

* Wi-Fi 連接已停用。 如有必要，可透過 USB 啟用 Ethernet 以進行 LAN 連線
* 未受管理
* 裝置登入的本機使用者帳戶
  * HoloLens 2 只支援一個本機帳戶
* 不同層級的裝置鎖定設定會透過根據特定使用案例提供的布建套件來套用。 這些設定通常會因為安全的環境需求而受到限制
* 透過布建套件部署一或多個應用程式

### <a name="common-challenges"></a>常見的挑戰

* 布建套件提供一組有限的設定
* 無法使用雲端服務，因此會限制 HoloLens 2 的功能。
* 更高的系統管理負荷，因為這些裝置必須手動設定、設定和更新。

相對應的離線安全指南提供了套用範例布建套件的指示，可鎖定 HoloLens 2 以在安全環境中使用。

> [!div class="nextstepaction"]
> [離線安全環境部署指南](hololens-common-scenarios-offline-secure.md)
