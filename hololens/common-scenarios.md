---
title: 常見的基礎結構部署案例
description: 根據混合現實的不同基礎結構部署，瞭解一些最常見的部署案例。
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
keywords: hololens
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: v-evmill
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 30a35fb0fe5d5b669249df25ebff0228b552596c
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397413"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>常見的基礎結構部署案例總覽

在部署和管理企業內的 Microsoft HoloLens 2 裝置時，下列資訊可提供三種常見案例的高階架構總覽。 通常，您管理裝置的方式，以及如何存取組織的資源，主要取決於已有的因素。 根據現有的基礎結構，我們會在下列案例中邀請您複習一般裝置管理樣式，並嘗試在符合您需求的案例中進行部署的指南。

## <a name="scenarios"></a>案例

下圖代表 HoloLens 2 部署的兩個典型受控案例。
 

另外還有第三種情況允許離線的安全部署。

### <a name="scenario-a-deploy-to-cloud-connected-devices"></a>案例 A：部署至雲端連接的裝置

HoloLens 2 部署為主要用於公司網路外部的環境。 公司資源無法存取，或可能會透過 VPN 來限制。 此部署與公司內受管理的行動裝置類似。
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

如需類似于此案例的部署指南，請參閱《 [雲端連線環境部署指南](hololens2-cloud-connected-overview.md)》的指南。

> [!div class="nextstepaction"]
> [雲端連線環境部署指南](hololens2-cloud-connected-overview.md)
> [!div class="nextstepaction"]
> [雲端連線環境 (外部用戶端) 部署指南](hololens2-deployment-guide.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a>案例 B：在組織的網路內部署

HoloLens 2 部署在公司網路上，可存取內部公司資源。 網際網路和雲端服務可能會受到限制。 此部署是大多數 Windows 10 電腦的一般部署。

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

如需類似于此案例的部署指南，請參閱《 [商業網路部署指南](hololens2-corp-connected-overview.md)》的指南。

> [!div class="nextstepaction"]
> [公司網路部署指南](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a>案例 C：在安全的離線環境中部署

部署 HoloLens 2，主要用於離線且無法存取網路或網際網路。 這是高度安全或機密位置的一般部署。
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

如需類似于此案例的部署指南，請參閱我們的 [離線安全環境部署指南](hololens-common-scenarios-offline-secure.md)。

> [!div class="nextstepaction"]
> [離線安全環境部署指南](hololens-common-scenarios-offline-secure.md)
