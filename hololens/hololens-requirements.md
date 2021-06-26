---
title: 在商業環境中規劃 HoloLens 2 部署
description: 深入瞭解如何在企業環境中部署和管理 HoloLens，包括基礎結構、Azure Active Directory 和行動裝置管理。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bogenera
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 2a0933bb754043934621a22ffa7764c9c88d93da
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924599"
---
# <a name="common-deployment-scenarios"></a>常見部署案例

## <a name="overview"></a>概觀

本頁面提供在部署及管理企業內 Microsoft HoloLens 2 裝置時，三個常見案例的高階架構總覽。

通常，您管理裝置及存取組織資源的方式，主要取決於已有的因素。 根據您現有的基礎結構，我們邀請您在下列案例中查看一般裝置管理樣式 (MDM) ，然後閱讀在 [商業環境中規劃 HoloLens 2 部署](hololens-core-components.md) ，以判斷哪一個案例符合您的需求。 此外，您也可以在部署期間使用三個對應的指南。


 1. [雲端連線環境部署指南](hololens2-cloud-connected-overview.md)
     1. [雲端連線環境 (外部用戶端) 部署指南](hololens2-deployment-guide.md)
 1. [公司網路部署指南](hololens2-corp-connected-overview.md)
 1. [離線安全環境部署指南](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>案例 A：部署至雲端連接的裝置

此案例相當於在公司內部署受管理的行動裝置。 HoloLens 2 部署為主要用於公司網路外部的環境。 公司資源無法存取，或可能會透過 VPN 來限制。 
 * 基本的一般設定
   * Wi-Fi 的網路通常會完全開放到網際網路和雲端服務。
   * Azure AD 與行動裝置管理 (MDM) 自動註冊的聯結--MDM (Intune) 受控
   * 使用者以自己的公司帳戶登入 (Azure AD) 
     * 每個裝置支援的單一或多個使用者
   * 不同層級的裝置鎖定設定會根據特定使用案例套用，從完全開放到單一應用程式 Kiosk。
   * 透過 MDM 部署一或多個應用程式

* 常見的挑戰
   * 根據案例需求，判斷要套用至 HoloLens 2 的 MDM 設定。

[![案例圖 ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

對應的雲端連接指南會說明如何在裝置管理中註冊 HoloLens 2、視需要套用授權，以及驗證您的終端使用者是否能夠在裝置設定時立即使用遠端協助。 使用外部用戶端指南將裝置部署到遠端網站，以進行短期或長期外部使用。

> [!div class="nextstepaction"]
> [雲端連線環境部署指南](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [雲端連線環境 (外部用戶端) 部署指南](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>案例 B：在組織的網路內部署

此案例與大多數 Windows 10 電腦的傳統部署完全相同。 HoloLens 2 部署在公司網路上，可存取內部公司資源。 網際網路和雲端服務可能會受到限制。 

 * 基本的一般設定
   * Wi-Fi network 是內部公司網路，可存取內部資源，並限制存取網際網路或雲端服務。
   * 使用 MDM 自動註冊 Azure AD 聯結
   * MDM (Intune) 受控
   * 使用者以自己的公司帳戶登入 (Azure AD) 
     * 每個裝置支援的單一或多個使用者
   * 不同層級的裝置鎖定設定會根據特定使用案例套用，從完全開放到單一應用程式 Kiosk。
   * 透過 MDM 部署一或多個應用程式

 * 常見的挑戰
   * HoloLens 2 不支援內部部署 AD 聯結或 SCCM。 僅 Azure AD 與 MDM 聯結。 現今許多公司仍在此案例中部署 Windows 10 的電腦，就像內部部署 AD 加入的裝置一樣，由 System Center 設定管理員 (SCCM) 管理，而且可能不會部署/設定基礎結構，以透過雲端式 MDM 解決方案來管理內部 Windows 10 裝置。
   * 由於 HoloLens 2 是雲端的第一部裝置，因此其高度依賴網際網路和雲端聯機服務來進行使用者驗證、作業系統更新、MDM 管理等等。 連線到公司網路時，可能需要調整 Proxy/防火牆規則，才能啟用 HoloLens 2 的存取，以及對其執行的應用程式。
   * 公司 Wi-Fi 連線通常需要憑證來向網路驗證裝置或使用者。 透過 MDM 將憑證部署到 Windows 10 裝置所需的基礎結構或設定，可能是設定的挑戰。

[![案例 B1 圖表 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![案例 B2 圖表 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

對應的公司網路指南會指示如何註冊 HoloLens 2 到您現有的裝置管理、視需要套用授權，以及驗證您的終端使用者是否能夠在裝置設定之後，操作 Dynamics 365 指南，以及使用自訂的企業營運應用程式。

> [!div class="nextstepaction"]
> [公司網路部署指南](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>案例 C：在安全的離線環境中部署

這是高度安全或機密位置的一般部署。 部署 HoloLens 2，主要用於離線且無法存取網路或網際網路。 
 * 基本的一般設定
   * Wi-Fi 連接已停用。 如有需要，可透過 USB 來啟用乙太網路連線能力。
   * 未受管理。
   * 裝置登入的本機使用者帳戶。
     * HoloLens 2 只支援一個本機帳戶。
   * 不同層級的裝置鎖定設定會透過根據特定使用案例提供的布建套件來套用。 這些設定通常會因為安全的環境需求而受到限制。
   * 透過布建套件部署一或多個應用程式

 * 常見的挑戰
   * 布建套件提供一組有限的設定
   * 無法使用雲端服務，因此會限制 HoloLens 2 的功能。
   * 更高的系統管理負荷，因為這些裝置必須手動設定、設定和更新。

[![離線安全圖 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

相對應的離線安全指南提供了套用範例布建套件的指示，可鎖定 HoloLens 2 以在安全環境中使用。

> [!div class="nextstepaction"]
> [離線安全環境部署指南](hololens-common-scenarios-offline-secure.md)


