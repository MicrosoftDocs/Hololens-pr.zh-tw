---
title: 常見的基礎結構部署案例
description: 根據不同常見基礎結構的一些常見部署案例
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 11/04/2020
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
ms.openlocfilehash: a7d847e2d2d335f2e2388535a5cf9d5246bb330b
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253070"
---
# 常見的基礎結構部署案例概述

下列資訊提供在企業中部署和管理 Microsoft HoloLens 2 裝置的三種常見案例的高層結構概覽。 您管理裝置的方式，以及如何存取貴組織的資源，主要是由現有的因素決定。 根據現有的基礎結構，我們會邀請您在下列案例中審查常見的裝置管理樣式，並嘗試在符合您需求的案例中部署輔助線。

## 案例

下圖代表 HoloLens 2 部署的三種典型案例。
![案例圖表](images/scenarios.jpg)

### 案例 A：部署到雲端連接裝置

已部署 HoloLens 2，主要用於公司網路中的外部環境。 公司資源無法存取，或可能受 VPN 限制。 此部署與公司中受管理的行動裝置類似。
 * 基本常見設定
   * Wi-Fi 的網路通常會完全開啟網際網路和雲端服務。
   * 使用 MDM 自動註冊的 Azure AD 聯接--MDM (Intune) 管理
   * 使用者以自己的公司帳戶登入 (Azure AD) 
     * 每個裝置支援單一或多個使用者
   * 根據特定的使用案例，從完全開啟到單一應用程式亭，就會套用各種不同的裝置鎖定設定等級。
   * 一或多個應用程式是透過 MDM 部署

* 常見的難題
   * 根據案例需求決定要套用至 HoloLens 2 的 MDM 設定。

對於類似案例的部署指南，請參閱 [與「遠端協助」配合雲端連線的 HoloLens](hololens2-cloud-connected-overview.md)指南。

> [!div class="nextstepaction"]
> [部署指南–雲端連線的 HoloLens 2 （含遠端協助）](hololens2-cloud-connected-overview.md)

### 案例 B：在貴組織的網路內部部署

HoloLens 2 已部署，主要用於公司網路，可存取內部公司資源。 網際網路和雲端服務可能受到限制。 此部署是大多數 Windows 10 電腦的典型部署。

 * 基本常見設定
   * Wi-Fi 網路是內部公司網路，可存取內部資源，以及網際網路或雲端服務的有限存取權。
   * 使用 MDM 自動註冊的 Azure AD 加入
   * MDM (Intune) 管理
   * 使用者以自己的公司帳戶登入 (Azure AD) 
     * 每個裝置支援單一或多個使用者
   * 根據特定的使用案例，從完全開啟到單一應用程式亭，就會套用各種不同的裝置鎖定設定等級。
   * 一或多個應用程式是透過 MDM 部署

 * 常見的難題
   * HoloLens 2 不支援內部部署廣告連接或 SCCM。 僅限使用 MDM 的 Azure AD 加入。 目前許多公司都會在這個案例中部署 Windows 10 電腦，就像是內部部署廣告連接裝置一樣，由 System Center Configuration Manager () SCCM 所管理，而且可能不會透過雲端的 MDM 解決方案部署/設定基礎結構來管理內部 Windows 10 裝置。
   * 因為 HoloLens 2 是雲端第一個裝置，所以它大量依賴網際網路和雲端聯機服務來進行使用者驗證、作業系統更新、MDM 管理等。連線至公司網路時，最可能需要調整 Proxy/防火牆規則，才能啟用 HoloLens 2 以及在其上執行的應用程式的存取權。
   * 企業 Wi-Fi 連線通常需要認證，才能向網路驗證裝置或使用者。 透過 MDM 將憑證部署到 Windows 10 裝置所需的基礎結構或設定，可能很難設定。

### 案例 C：在安全的離線環境中部署

HoloLens 2 已部署，主要用於離線使用，沒有網路或網際網路存取。 這是高度安全或機密位置的典型部署。
 * 基本常見設定
   * Wi-Fi 連線性已停用。 如有需要，可透過 USB 的乙太網路進行局域網連線。
   * 未管理。
   * 裝置登入的本機使用者帳戶。
     * HoloLens 2 只支援一個本機帳戶。
   * 根據特定使用案例，會透過置備套件來套用不同的裝置鎖定設定等級。 由於安全的環境需求，這些設定通常會受到很大的限制。
   * 一或多個應用程式是透過 [預配套件] 來部署

 * 常見的難題
   * 您可以透過預配套件使用一組有限的設定
   * 雲端服務無法被利用，因此限制 HoloLens 2 的功能。
   * 更高的管理負荷，因為這些裝置必須手動設定、設定及更新。

如需與此案例類似的部署指南，請參閱我們的 [離線安全部署指南](hololens-common-scenarios-offline-secure.md)。

> [!div class="nextstepaction"]
> [部署指南–離線安全 HoloLens 2](hololens-common-scenarios-offline-secure.md)
